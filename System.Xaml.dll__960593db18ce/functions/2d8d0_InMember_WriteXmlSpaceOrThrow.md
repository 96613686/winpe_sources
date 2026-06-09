# InMember::WriteXmlSpaceOrThrow

- ea: `0x2d8d0`
- end: `0x2d90b`
- name: `InMember::WriteXmlSpaceOrThrow`
- size: `59`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x2d730`

## callees

- `0x8860`
- `0xfa70`
- `0x11f50`
- `0x2cb30`
- `0x2cb70`
- `0x2d8d0`
- `0x2d910`

## string_xrefs

- `0x2d8e1`: `CannotWriteXmlSpacePreserveOnMember`

## pseudocode

```c

```

## disassembly

```asm
0x2d8d0  ldarg.0
0x2d8d1  ldarg.1
0x2d8d2  call     instance class Frame InMember::FindFrameWithXmlSpacePreserve(class System.Xaml.XamlXmlWriter writer)
0x2d8d7  stloc.0
0x2d8d8  ldloc.0
0x2d8d9  callvirt instance valuetype System.Xaml.XamlNodeType Frame::get_AllocatingNodeType()
0x2d8de  ldc.i4.4
0x2d8df  bne.un.s loc_2D904
0x2d8e1  ldstr    aCannotwritexml// "CannotWriteXmlSpacePreserveOnMember"
0x2d8e6  ldc.i4.2
0x2d8e7  newarr   [mscorlib]System.Object
0x2d8ec  dup
0x2d8ed  ldc.i4.0
0x2d8ee  ldloc.0
0x2d8ef  callvirt instance class System.Xaml.XamlMember Frame::get_Member()
0x2d8f4  stelem.ref
0x2d8f5  dup
0x2d8f6  ldc.i4.1
0x2d8f7  ldarg.2
0x2d8f8  stelem.ref
0x2d8f9  call     string System.Xaml.SR::Get(string id, object[] args)
0x2d8fe  newobj   instance void System.Xaml.XamlXmlWriterException::.ctor(string message)
0x2d903  throw
0x2d904  ldarg.1
0x2d905  call     void System.Xaml.XamlXmlWriter::WriteXmlSpace(class System.Xaml.XamlXmlWriter writer)
0x2d90a  ret
```
