# System.Xaml.XamlXmlWriter::WriteNamespace

- ea: `0xf860`
- end: `0xf8e3`
- name: `System.Xaml.XamlXmlWriter::WriteNamespace`
- size: `131`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `registry_config`

## callees

- `0x6970`
- `0x6980`
- `0xf860`
- `0xf910`
- `0x11f20`
- `0x2cdf0`

## string_xrefs

- `0xf8c0`: `NamespaceDeclarationCannotBeXml`

## pseudocode

```c

```

## disassembly

```asm
0xf860  ldarg.0
0xf861  call     instance void System.Xaml.XamlXmlWriter::CheckIsDisposed()
0xf866  ldarg.1
0xf867  brtrue.s loc_F874
0xf869  ldstr    aNamespacedecla// "namespaceDeclaration"
0xf86e  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0xf873  throw
0xf874  ldarg.1
0xf875  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0xf87a  brtrue.s loc_F891
0xf87c  ldstr    aNamespacedecla_0// "NamespaceDeclarationPrefixCannotBeNull"
0xf881  call     string System.Xaml.SR::Get(string id)
0xf886  ldstr    aNamespacedecla// "namespaceDeclaration"
0xf88b  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xf890  throw
0xf891  ldarg.1
0xf892  callvirt instance string System.Xaml.NamespaceDeclaration::get_Namespace()
0xf897  brtrue.s loc_F8AE
0xf899  ldstr    aNamespacedecla_1// "NamespaceDeclarationNamespaceCannotBeNu"...
0xf89e  call     string System.Xaml.SR::Get(string id)
0xf8a3  ldstr    aNamespacedecla// "namespaceDeclaration"
0xf8a8  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xf8ad  throw
0xf8ae  ldarg.1
0xf8af  callvirt instance string System.Xaml.NamespaceDeclaration::get_Prefix()
0xf8b4  ldstr    aXml// "xml"
0xf8b9  call     bool [mscorlib]System.String::op_Equality(string, string)
0xf8be  brfalse.s loc_F8D5
0xf8c0  ldstr    aNamespacedecla_2// "NamespaceDeclarationCannotBeXml"
0xf8c5  call     string System.Xaml.SR::Get(string id)
0xf8ca  ldstr    aNamespacedecla// "namespaceDeclaration"
0xf8cf  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0xf8d4  throw
0xf8d5  ldarg.0
0xf8d6  ldfld    class WriterState System.Xaml.XamlXmlWriter::currentState
0xf8db  ldarg.0
0xf8dc  ldarg.1
0xf8dd  callvirt instance void WriterState::WriteNamespace(class System.Xaml.XamlXmlWriter writer, class System.Xaml.NamespaceDeclaration namespaceDeclaration)
0xf8e2  ret
```
