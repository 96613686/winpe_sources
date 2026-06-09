# SerializerContext::ReserveDefaultPrefixForRootObject

- ea: `0x2bc10`
- end: `0x2bc52`
- name: `SerializerContext::ReserveDefaultPrefixForRootObject`
- size: `66`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x2b4a0`

## callees

- `0xd080`
- `0x2bc10`
- `0x2bf00`

## string_xrefs

- `0x2bc23`: `http://schemas.microsoft.com/winfx/2006/xaml`

## pseudocode

```c

```

## disassembly

```asm
0x2bc10  ldarg.0
0x2bc11  ldarg.1
0x2bc12  callvirt instance class [mscorlib]System.Type [mscorlib]System.Object::GetType()
0x2bc17  call     instance class System.Xaml.XamlType SerializerContext::GetXamlType(class [mscorlib]System.Type clrType)
0x2bc1c  callvirt instance string System.Xaml.XamlType::get_PreferredXamlNamespace()
0x2bc21  stloc.0
0x2bc22  ldloc.0
0x2bc23  ldstr    aHttpSchemasMic// "http://schemas.microsoft.com/winfx/2006"...
0x2bc28  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x2bc2d  brfalse.s loc_2BC51
0x2bc2f  ldarg.0
0x2bc30  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> SerializerContext::namespaceToPrefixMap
0x2bc35  ldloc.0
0x2bc36  ldsfld   string [mscorlib]System.String::Empty
0x2bc3b  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2bc40  ldarg.0
0x2bc41  ldfld    class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> SerializerContext::prefixToNamespaceMap
0x2bc46  ldsfld   string [mscorlib]System.String::Empty
0x2bc4b  ldloc.0
0x2bc4c  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x2bc51  ret
```
