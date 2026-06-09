# System.Net.Http.Formatting.MediaTypeConstants::.cctor

- ea: `0x7cb0`
- end: `0x7d1a`
- name: `System.Net.Http.Formatting.MediaTypeConstants::.cctor`
- size: `106`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x7cb0`: `application/xml`
- `0x7cbf`: `text/xml`
- `0x7cce`: `application/json`
- `0x7cdd`: `text/json`

## pseudocode

```c

```

## disassembly

```asm
0x7cb0  ldstr    aApplicationXml// "application/xml"
0x7cb5  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7cba  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultApplicationXmlMediaType
0x7cbf  ldstr    aTextXml// "text/xml"
0x7cc4  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7cc9  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultTextXmlMediaType
0x7cce  ldstr    aApplicationJso// "application/json"
0x7cd3  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7cd8  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultApplicationJsonMediaType
0x7cdd  ldstr    aTextJson// "text/json"
0x7ce2  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7ce7  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultTextJsonMediaType
0x7cec  ldstr    aApplicationOct// "application/octet-stream"
0x7cf1  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7cf6  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultApplicationOctetStreamMediaType
0x7cfb  ldstr    aApplicationXWw// "application/x-www-form-urlencoded"
0x7d00  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7d05  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultApplicationFormUrlEncodedMediaType
0x7d0a  ldstr    aApplicationBso// "application/bson"
0x7d0f  newobj   instance void [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue::.ctor(string)
0x7d14  stsfld   class [System.Net.Http]System.Net.Http.Headers.MediaTypeHeaderValue System.Net.Http.Formatting.MediaTypeConstants::_defaultApplicationBsonMediaType
0x7d19  ret
```
