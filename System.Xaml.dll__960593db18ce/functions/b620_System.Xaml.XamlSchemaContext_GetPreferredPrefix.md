# System.Xaml.XamlSchemaContext::GetPreferredPrefix

- ea: `0xb620`
- end: `0xb694`
- name: `System.Xaml.XamlSchemaContext::GetPreferredPrefix`
- size: `116`
- prototype: ``
- caller_count: `2`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0xfce0`
- `0x2be50`

## callees

- `0x8920`
- `0xb620`
- `0xb6a0`
- `0xb740`
- `0xc5f0`
- `0x16490`

## string_xrefs

- `0xb623`: `xmlns`

## pseudocode

```c

```

## disassembly

```asm
0xb620  ldarg.1
0xb621  brtrue.s loc_B62E
0xb623  ldstr    aXmlns// "xmlns"
0xb628  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xb62d  throw
0xb62e  ldarg.0
0xb62f  call     instance void System.Xaml.XamlSchemaContext::UpdateXmlNsInfo()
0xb634  ldarg.0
0xb635  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string> System.Xaml.XamlSchemaContext::_preferredPrefixes
0xb63a  brtrue.s loc_B642
0xb63c  ldarg.0
0xb63d  call     instance void System.Xaml.XamlSchemaContext::InitializePreferredPrefixes()
0xb642  ldarg.0
0xb643  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string> System.Xaml.XamlSchemaContext::_preferredPrefixes
0xb648  ldarg.1
0xb649  ldloca.s 0
0xb64b  callvirt instance bool class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0xb650  brtrue.s loc_B692
0xb652  call     class [mscorlib]System.Collections.Generic.IList`1<string> System.Xaml.XamlLanguage::get_XamlNamespaces()
0xb657  ldarg.1
0xb658  callvirt instance bool class [mscorlib]System.Collections.Generic.ICollection`1<string>::Contains(var<u1>)
0xb65d  brfalse.s loc_B667
0xb65f  ldstr    aX// "x"
0xb664  stloc.0
0xb665  br.s     loc_B684
0xb667  ldarg.1
0xb668  ldloca.s 1
0xb66a  ldloca.s 2
0xb66c  call     bool System.Xaml.Schema.ClrNamespaceUriParser::TryParseUri(string uriInput, [out] string& clrNs, [out] string& assemblyName)
0xb671  brfalse.s loc_B67E
0xb673  ldarg.0
0xb674  ldloc.1
0xb675  ldloc.2
0xb676  call     instance string System.Xaml.XamlSchemaContext::GetPrefixForClrNs(string clrNs, string assemblyName)
0xb67b  stloc.0
0xb67c  br.s     loc_B684
0xb67e  ldstr    aP// "p"
0xb683  stloc.0
0xb684  ldarg.0
0xb685  ldfld    class [mscorlib]System.Collections.Concurrent.ConcurrentDictionary`2<string, string> System.Xaml.XamlSchemaContext::_preferredPrefixes
0xb68a  ldarg.1
0xb68b  ldloc.0
0xb68c  call     T0x2B00000B
0xb691  stloc.0
0xb692  ldloc.0
0xb693  ret
```
