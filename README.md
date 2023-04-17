# NOM: Nostr Open Media Specification

_Draft v0.1_

The goal of this spec is to create a document schema that provides Nostr clients with a standard, readable event that contains all the metadata required to present multimedia such as music or video to users. The schema described below is intended to be published as a content string in a standard Nostr event per existing [NIP specifications](https://github.com/nostr-protocol/nips). Specfically, the [Parameterized Replaceable Event kind](https://github.com/nostr-protocol/nips/blob/master/33.md) appears well-suited to housing this type of document. Many of the labels are taken directly from or inspired by the structure of [RSS feeds for podcasting](https://github.com/Podcastindex-org/podcast-namespace/blob/main/docs/1.0.md).

The following concerns are not included in this specification:

- How to handle payments
- Digital rights management (i.e. paywalls)
- Content distribution implementations

### Document Schema

```json
{
    title: <string>, // Name of content
    guid: <string>, // Application-specific unique identifier
    creator: <string>, // Artist name
    type: <string>, // MIME type (example: "audio/mpeg")
    duration: <integer>, // Length of media in seconds
    pubDate: <integer>, // Unix timestamp
    link: <string>, // URL to hosting site for media (example: "https://mysite.com/my-song-page")
    enclosure: <string>, // URL to media content file (example: "https://cdn.com/mysong.mp3")
    version: <string>, // Schema version to maintain compatibility with clients
}
```
