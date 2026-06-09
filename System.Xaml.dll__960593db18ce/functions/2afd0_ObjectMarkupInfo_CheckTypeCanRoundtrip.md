# ObjectMarkupInfo::CheckTypeCanRoundtrip

- ea: `0x2afd0`
- end: `0x2b081`
- name: `ObjectMarkupInfo::CheckTypeCanRoundtrip`
- size: `177`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x2b4a0`

## callees

- `0x2290`
- `0x8810`
- `0xd070`
- `0xd0b0`
- `0xd120`
- `0x11f50`
- `0x29220`
- `0x29fa0`
- `0x2a0f0`
- `0x2afd0`

## string_xrefs

- `0x2b042`: `ObjectReaderTypeIsNested`
- `0x2b061`: `ObjectReaderTypeCannotRoundtrip`

## pseudocode

```c

```

## disassembly

```asm
0x2afd0  ldarg.0
0x2afd1  callvirt instance valuetype System.Xaml.XamlNode MarkupInfo::get_XamlNode()
0x2afd6  stloc.1
0x2afd7  ldloca.s 1
0x2afd9  call     instance class System.Xaml.XamlType System.Xaml.XamlNode::get_XamlType()
0x2afde  stloc.0
0x2afdf  ldloc.0
0x2afe0  callvirt instance bool System.Xaml.XamlType::get_IsConstructible()
0x2afe5  brtrue   loc_2B080
0x2afea  ldarg.0
0x2afeb  callvirt instance class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo> ObjectMarkupInfo::get_Properties()
0x2aff0  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<class MarkupInfo>::GetEnumerator()
0x2aff5  stloc.2
0x2aff6  br.s     loc_2B01C
0x2aff8  ldloca.s 2
0x2affa  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::get_Current()
0x2afff  stloc.3
0x2b000  ldloc.3
0x2b001  castclass MemberMarkupInfo
0x2b006  callvirt instance bool MemberMarkupInfo::get_IsFactoryMethod()
0x2b00b  brfalse.s loc_2B01C
0x2b00d  ldloc.0
0x2b00e  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2b013  callvirt instance bool [mscorlib]System.Type::get_IsNested()
0x2b018  brtrue.s loc_2B01C
0x2b01a  leave.s  loc_2B080
0x2b01c  ldloca.s 2
0x2b01e  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>::MoveNext()
0x2b023  brtrue.s loc_2AFF8
0x2b025  leave.s  loc_2B035
0x2b027  ldloca.s 2
0x2b029  constrained. valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<class MarkupInfo>
0x2b02f  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x2b034  endfinally
0x2b035  ldloc.0
0x2b036  callvirt instance class [mscorlib]System.Type System.Xaml.XamlType::get_UnderlyingType()
0x2b03b  callvirt instance bool [mscorlib]System.Type::get_IsNested()
0x2b040  brfalse.s loc_2B061
0x2b042  ldstr    aObjectreaderty// "ObjectReaderTypeIsNested"
0x2b047  ldc.i4.1
0x2b048  newarr   [mscorlib]System.Object
0x2b04d  dup
0x2b04e  ldc.i4.0
0x2b04f  ldloc.0
0x2b050  callvirt instance string System.Xaml.XamlType::get_Name()
0x2b055  stelem.ref
0x2b056  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b05b  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2b060  throw
0x2b061  ldstr    aObjectreaderty_0// "ObjectReaderTypeCannotRoundtrip"
0x2b066  ldc.i4.1
0x2b067  newarr   [mscorlib]System.Object
0x2b06c  dup
0x2b06d  ldc.i4.0
0x2b06e  ldloc.0
0x2b06f  callvirt instance string System.Xaml.XamlType::get_Name()
0x2b074  stelem.ref
0x2b075  call     string System.Xaml.SR::Get(string id, object[] args)
0x2b07a  newobj   instance void System.Xaml.XamlObjectReaderException::.ctor(string message)
0x2b07f  throw
0x2b080  ret
```
