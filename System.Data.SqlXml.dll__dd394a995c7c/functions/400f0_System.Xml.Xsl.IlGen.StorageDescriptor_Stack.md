# System.Xml.Xsl.IlGen.StorageDescriptor::Stack

- ea: `0x400f0`
- end: `0x40112`
- name: `System.Xml.Xsl.IlGen.StorageDescriptor::Stack`
- size: `34`
- prototype: ``
- caller_count: `38`
- callee_count: `0`
- tags: `registry_config`

## callers

- `0x401e0`
- `0x403f0`
- `0x4aff0`
- `0x4b1b0`
- `0x4b280`
- `0x4b300`
- `0x4b380`
- `0x4b3c0`
- `0x4b3f0`
- `0x4b430`
- `0x4b470`
- `0x4b4a0`
- `0x4b5c0`
- `0x4b620`
- `0x4b750`
- `0x4bbe0`
- `0x4bd70`
- `0x4bdc0`
- `0x4c350`
- `0x4c490`
- `0x4c520`
- `0x4c570`
- `0x4c5b0`
- `0x4c800`
- `0x4cc30`
- `0x4d910`
- `0x4dc70`
- `0x4df60`
- `0x4e510`
- `0x4e600`
- `0x4eb20`
- `0x4ece0`
- `0x4ee70`
- `0x4efa0`
- `0x4f110`
- `0x4f610`
- `0x4fee0`
- `0x50130`

## pseudocode

```c

```

## disassembly

```asm
0x400f0  ldloca.s 0
0x400f2  initobj  System.Xml.Xsl.IlGen.StorageDescriptor
0x400f8  ldloca.s 0
0x400fa  ldc.i4.1
0x400fb  stfld    valuetype System.Xml.Xsl.IlGen.ItemLocation System.Xml.Xsl.IlGen.StorageDescriptor::location
0x40100  ldloca.s 0
0x40102  ldarg.0
0x40103  stfld    class [mscorlib]System.Type System.Xml.Xsl.IlGen.StorageDescriptor::itemStorageType
0x40108  ldloca.s 0
0x4010a  ldarg.1
0x4010b  stfld    bool System.Xml.Xsl.IlGen.StorageDescriptor::isCached
0x40110  ldloc.0
0x40111  ret
```
