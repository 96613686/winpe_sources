# System.Xaml.Permissions.XamlAccessLevel::ToXml

- ea: `0x125b0`
- end: `0x125e7`
- name: `System.Xaml.Permissions.XamlAccessLevel::ToXml`
- size: `55`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x12aa0`

## callees

- `0x12470`
- `0x12490`
- `0x125b0`

## string_xrefs

- `0x125b0`: `XamlAccessLevel`

## pseudocode

```c

```

## disassembly

```asm
0x125b0  ldstr    aXamlaccessleve// "XamlAccessLevel"
0x125b5  newobj   instance void [mscorlib]System.Security.SecurityElement::.ctor(string)
0x125ba  stloc.0
0x125bb  ldloc.0
0x125bc  ldstr    aAssemblyname_0// "AssemblyName"
0x125c1  ldarg.0
0x125c2  call     instance string System.Xaml.Permissions.XamlAccessLevel::get_AssemblyNameString()
0x125c7  callvirt instance void [mscorlib]System.Security.SecurityElement::AddAttribute(string, string)
0x125cc  ldarg.0
0x125cd  call     instance string System.Xaml.Permissions.XamlAccessLevel::get_PrivateAccessToTypeName()
0x125d2  brfalse.s loc_125E5
0x125d4  ldloc.0
0x125d5  ldstr    aTypename_0// "TypeName"
0x125da  ldarg.0
0x125db  call     instance string System.Xaml.Permissions.XamlAccessLevel::get_PrivateAccessToTypeName()
0x125e0  callvirt instance void [mscorlib]System.Security.SecurityElement::AddAttribute(string, string)
0x125e5  ldloc.0
0x125e6  ret
```
