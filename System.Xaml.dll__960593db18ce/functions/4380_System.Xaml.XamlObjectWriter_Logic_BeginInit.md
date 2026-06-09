# System.Xaml.XamlObjectWriter::Logic_BeginInit

- ea: `0x4380`
- end: `0x43d7`
- name: `System.Xaml.XamlObjectWriter::Logic_BeginInit`
- size: `87`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x2a90`
- `0x3c80`

## callees

- `0x2710`
- `0x2870`
- `0x4380`
- `0x5030`
- `0x202d0`
- `0x20360`
- `0x215d0`
- `0x216d0`
- `0x21a30`
- `0x21d70`

## pseudocode

```c

```

## disassembly

```asm
0x4380  ldarg.1
0x4381  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentInstance()
0x4386  stloc.0
0x4387  ldarg.1
0x4388  callvirt instance class System.Xaml.XamlType MS.Internal.Xaml.Context.ObjectWriterContext::get_CurrentType()
0x438d  stloc.1
0x438e  ldarg.0
0x438f  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x4394  ldloc.1
0x4395  ldloc.0
0x4396  ldc.i4.1
0x4397  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::InitializationGuard(class System.Xaml.XamlType xamlType, object obj, bool begin)
0x439c  ldarg.1
0x439d  callvirt instance class [System]System.Uri MS.Internal.Xaml.Context.ObjectWriterContext::get_BaseUri()
0x43a2  ldnull
0x43a3  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x43a8  brfalse.s loc_43BD
0x43aa  ldarg.0
0x43ab  call     instance class MS.Internal.Xaml.Runtime.XamlRuntime System.Xaml.XamlObjectWriter::get_Runtime()
0x43b0  ldloc.1
0x43b1  ldloc.0
0x43b2  ldarg.1
0x43b3  callvirt instance class [System]System.Uri MS.Internal.Xaml.Context.ObjectWriterContext::get_BaseUri()
0x43b8  callvirt instance void MS.Internal.Xaml.Runtime.XamlRuntime::SetUriBase(class System.Xaml.XamlType xamlType, object obj, class [System]System.Uri baseUri)
0x43bd  ldloc.0
0x43be  ldarg.1
0x43bf  callvirt instance object MS.Internal.Xaml.Context.ObjectWriterContext::get_RootInstance()
0x43c4  bne.un.s loc_43CF
0x43c6  ldarg.0
0x43c7  ldarg.1
0x43c8  ldc.i4.0
0x43c9  ldloc.0
0x43ca  call     instance void System.Xaml.XamlObjectWriter::Logic_SetConnectionId(class MS.Internal.Xaml.Context.ObjectWriterContext ctx, int32 connectionId, object instance)
0x43cf  ldarg.0
0x43d0  ldloc.0
0x43d1  callvirt instance void System.Xaml.XamlObjectWriter::OnAfterBeginInit(object value)
0x43d6  ret
```
