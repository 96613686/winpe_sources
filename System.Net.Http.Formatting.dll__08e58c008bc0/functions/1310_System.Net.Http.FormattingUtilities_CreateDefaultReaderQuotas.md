# System.Net.Http.FormattingUtilities::CreateDefaultReaderQuotas

- ea: `0x1310`
- end: `0x134d`
- name: `System.Net.Http.FormattingUtilities::CreateDefaultReaderQuotas`
- size: `61`
- prototype: ``
- caller_count: `4`
- callee_count: `0`
- tags: ``

## callers

- `0x7740`
- `0x77a0`
- `0x9000`
- `0x9090`

## pseudocode

```c

```

## disassembly

```asm
0x1310  newobj   instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::.ctor()
0x1315  dup
0x1316  ldc.i4   0x7FFFFFFF
0x131b  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxArrayLength(int32)
0x1320  dup
0x1321  ldc.i4   0x7FFFFFFF
0x1326  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxBytesPerRead(int32)
0x132b  dup
0x132c  ldc.i4   0x100
0x1331  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxDepth(int32)
0x1336  dup
0x1337  ldc.i4   0x7FFFFFFF
0x133c  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxNameTableCharCount(int32)
0x1341  dup
0x1342  ldc.i4   0x7FFFFFFF
0x1347  callvirt instance void [System.Runtime.Serialization]System.Xml.XmlDictionaryReaderQuotas::set_MaxStringContentLength(int32)
0x134c  ret
```
