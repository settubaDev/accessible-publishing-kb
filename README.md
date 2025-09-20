# Goal of the Fork

Turn DAISY knowledge bases into [gemini protocol(0.24.1)](/protocol-specification-0.24.1.gmi) compliant [gemtex (0.24.1)](/gemtex-specification-0.24.1.gmi) files.

> *Note*: Additional Requirements we aspire to follow for the HTML conversion to Gemini. When we mention Servers/ Clients we mean those subject to the latest Gemini protocol and accompanied compositional Specifications

- [subscription.gmi](/subscription.gmi)

## Filenames

>Gemini servers need to inform clients of the MIME type of the files they are serving. 

The most convenient way for servers to figure out the MIME type of
files is via the extension of the filename.  These mappings are mostly
well-standardised (and unix-like systems often have an `/etc/mime.types` file full of them), but the question remains as to how servers should recognise files to be served with the text/gemini type defined by Gemini.

> Current Gemini servers seem to use .gmi or .gemini extensions for this purpose, and new servers are strongly encouraged to support one or both of these options instead of adding a new one to the mix.

Following the convention for webservers, if a request is received for a path
which maps to a directory in the server's filesystem and a file named index.gmi
or index.gemini exists in that directory, it is served up for that path.

## File size 

> Gemini servers do not inform clients of the size of files they are serving, which can make it difficult to detect if a connection is closed prematurely due to a server fault. The risk of this happening increases with file size.

Gemini also has no support for compression of large files, or support for
checksums to enable detection of file corruption, the risk of which also
increases with file size.

For all of these reasons, Gemini is not well suited to the transfer of "very
large" files.  Exactly what counts as "very large" depends to some extent on
the speed and reliability of the internet connections involved, and the
patience of the users. As a rule of thumb, files larger than 100MiB might be
thought of as best served some other way.

Of course, because Gemini supports linking to other online content via any
protocol with a URL scheme, it's still possible to link from a Gemini document
to a large file served via BitTorrent, IPFS or other providers or custom specifications.

> TODO: Work-arounds need to be specified here for transparency

## Text encoding

> Gemini supports any text encoding via the "charset" parameter of text/* MIME types, but we enforce UTF-8 ONLY

## Redirects

### General remarks

We will avoid Redirects if possible including cross-protocol redirects, URL-shorteners, for security and transparency reasons. Audits are more tractable by community members, readers and security specialists alike.

> Gemini Clients need to implement a robust strategy to prevent strategy against malicious Gemini servers (un)knowlingy trapping clients in infinite loop of redirects.

> Clients may refuse redirects with depth N>5 - inline with RFC-2068. 

We will follow similar practises for the Gemtex Conversion and provide automated audit-logs for static capsule redirect topology with [static generators](https://github.com/ironcamel/Graph-Easy?tab=readme-ov-file). 

### Network Stack

> TODO: for a tractable Network Topology our clients/ servers will be built on top of [swift-nio-transport-services](https://github.com/apple/swift-nio-transport-services) with [low-level primitives for watchOs](https://developer.apple.com/documentation/technotes/tn3135-low-level-networking-on-watchos) 

Much Investigation is still needed here since we would want this conversion to work alongside models other than [peer-2-peer or client/server.](https://developer.apple.com/documentation/Technotes/tn3151-choosing-the-right-networking-api)

# Knowledge Base (kb)

## |Accessible Publishing|

> Note: This is a Best Effort Attempt

WIP 

--- 

## DAISY Knowledge Bases

A Fork that contains the mere html plain-text files for the following DAISY knowledge bases:

- [Accessible Publishing](/publishing) from kb dot daisy dot org slash publishing



