# System.Windows.Documents.XpsS0Schema::.cctor

- ea: `0xd28c0`
- end: `0xd2984`
- name: `System.Windows.Documents.XpsS0Schema::.cctor`
- size: `196`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0xd28c0`: `application/vnd.ms-opentype`
- `0xd28de`: `application/vnd.ms-package.obfuscated-opentype`
- `0xd2929`: `application/vnd.ms-package.xps-fixeddocumentsequence+xml`
- `0xd2938`: `application/vnd.ms-package.xps-fixeddocument+xml`
- `0xd2947`: `application/vnd.ms-package.xps-fixedpage+xml`
- `0xd2956`: `application/vnd.ms-package.xps-resourcedictionary+xml`
- `0xd2965`: `application/vnd.ms-printing.printticket+xml`
- `0xd2974`: `application/vnd.ms-package.xps-discard-control+xml`

## pseudocode

```c

```

## disassembly

```asm
0xd28c0  ldstr    aApplicationVnd_1// "application/vnd.ms-opentype"
0xd28c5  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd28ca  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fontContentType
0xd28cf  ldstr    aApplicationVnd_2// "application/vnd.ms-color.iccprofile"
0xd28d4  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd28d9  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_colorContextContentType
0xd28de  ldstr    aApplicationVnd_3// "application/vnd.ms-package.obfuscated-o"...
0xd28e3  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd28e8  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_obfuscatedContentType
0xd28ed  ldstr    aImageJpeg// "image/jpeg"
0xd28f2  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd28f7  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_jpgContentType
0xd28fc  ldstr    aImagePng// "image/png"
0xd2901  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2906  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_pngContentType
0xd290b  ldstr    aImageTiff// "image/tiff"
0xd2910  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2915  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_tifContentType
0xd291a  ldstr    aImageVndMsPhot// "image/vnd.ms-photo"
0xd291f  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2924  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_wmpContentType
0xd2929  ldstr    aApplicationVnd_4// "application/vnd.ms-package.xps-fixeddoc"...
0xd292e  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2933  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fixedDocumentSequenceContentType
0xd2938  ldstr    aApplicationVnd_5// "application/vnd.ms-package.xps-fixeddoc"...
0xd293d  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2942  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fixedDocumentContentType
0xd2947  ldstr    aApplicationVnd_6// "application/vnd.ms-package.xps-fixedpag"...
0xd294c  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2951  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_fixedPageContentType
0xd2956  ldstr    aApplicationVnd_7// "application/vnd.ms-package.xps-resource"...
0xd295b  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd2960  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_resourceDictionaryContentType
0xd2965  ldstr    aApplicationVnd_8// "application/vnd.ms-printing.printticket"...
0xd296a  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd296f  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_printTicketContentType
0xd2974  ldstr    aApplicationVnd_9// "application/vnd.ms-package.xps-discard-"...
0xd2979  newobj   instance void [WindowsBase]MS.Internal.ContentType::.ctor(string)
0xd297e  stsfld   class [WindowsBase]MS.Internal.ContentType System.Windows.Documents.XpsS0Schema::_discardControlContentType
0xd2983  ret
```
