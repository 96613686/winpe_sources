# System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseXmlWriterForFixedPage

- ea: `0x2f8a0`
- end: `0x2f917`
- name: `System.Windows.Xps.Serialization.NullPackagingPolicy::ReleaseXmlWriterForFixedPage`
- size: `119`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `registry_config`

## callees

- `0x1eee0`
- `0x1ef70`
- `0x2f8a0`
- `0x2fe90`

## string_xrefs

- `0x2f906`: `ReachSerialization_CannotReleaseXmlWriter`

## pseudocode

```c

```

## disassembly

```asm
0x2f8a0  ldarg.0
0x2f8a1  ldfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriter
0x2f8a6  brfalse.s loc_2F906
0x2f8a8  ldarg.0
0x2f8a9  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriterRef
0x2f8ae  ldc.i4.0
0x2f8af  ble.s    loc_2F906
0x2f8b1  ldarg.0
0x2f8b2  ldarg.0
0x2f8b3  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriterRef
0x2f8b8  ldc.i4.1
0x2f8b9  sub
0x2f8ba  stfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriterRef
0x2f8bf  ldarg.0
0x2f8c0  ldfld    int32 System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriterRef
0x2f8c5  brtrue.s loc_2F916
0x2f8c7  ldarg.0
0x2f8c8  ldnull
0x2f8c9  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_currentFixedPageWriter
0x2f8ce  ldarg.0
0x2f8cf  ldnull
0x2f8d0  stfld    class [mscorlib]System.Collections.Generic.IList`1<string> System.Windows.Xps.Serialization.NullPackagingPolicy::_linkTargetStream
0x2f8d5  ldarg.0
0x2f8d6  ldnull
0x2f8d7  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_resourceStream
0x2f8dc  ldarg.0
0x2f8dd  ldnull
0x2f8de  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_resourceXmlWriter
0x2f8e3  ldarg.0
0x2f8e4  ldnull
0x2f8e5  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_resourceDictionaryStream
0x2f8ea  ldarg.0
0x2f8eb  ldnull
0x2f8ec  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_resourceDictionaryXmlWriter
0x2f8f1  ldarg.0
0x2f8f2  ldnull
0x2f8f3  stfld    class [mscorlib]System.IO.StringWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_pageStream
0x2f8f8  ldarg.0
0x2f8f9  ldnull
0x2f8fa  stfld    class [System.Xml]System.Xml.XmlWriter System.Windows.Xps.Serialization.NullPackagingPolicy::_pageXmlWriter
0x2f8ff  ldarg.0
0x2f900  call     instance void System.Windows.Xps.Serialization.NullPackagingPolicy::InitializeResourceReferences()
0x2f905  ret
0x2f906  ldstr    aReachserializa// "ReachSerialization_CannotReleaseXmlWrit"...
0x2f90b  call     string System.Windows.Xps.SR::Get(string id)
0x2f910  newobj   instance void System.Windows.Xps.XpsSerializationException::.ctor(string message)
0x2f915  throw
0x2f916  ret
```
