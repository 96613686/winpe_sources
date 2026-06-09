# System.Deployment.Application.ManifestValidatingReader::.cctor

- ea: `0x1a1d0`
- end: `0x1a1f4`
- name: `System.Deployment.Application.ManifestValidatingReader::.cctor`
- size: `36`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `registry_config`

## string_xrefs

- `0x1a1d8`: `manifest.2.0.0.15-pre.adaptive.xsd`

## pseudocode

```c

```

## disassembly

```asm
0x1a1d0  ldc.i4.1
0x1a1d1  newarr   [mscorlib]System.String
0x1a1d6  dup
0x1a1d7  ldc.i4.0
0x1a1d8  ldstr    aManifest20015P// "manifest.2.0.0.15-pre.adaptive.xsd"
0x1a1dd  stelem.ref
0x1a1de  stsfld   string[] System.Deployment.Application.ManifestValidatingReader::_manifestSchemas
0x1a1e3  ldnull
0x1a1e4  stsfld   class [System.Xml]System.Xml.Schema.XmlSchemaSet System.Deployment.Application.ManifestValidatingReader::_manifestSchemaSet
0x1a1e9  newobj   instance void [mscorlib]System.Object::.ctor()
0x1a1ee  stsfld   object System.Deployment.Application.ManifestValidatingReader::_manifestSchemaSetLock
0x1a1f3  ret
```
