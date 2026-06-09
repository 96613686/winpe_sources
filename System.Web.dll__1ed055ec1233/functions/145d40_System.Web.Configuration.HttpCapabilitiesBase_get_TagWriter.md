# System.Web.Configuration.HttpCapabilitiesBase::get_TagWriter

- ea: `0x145d40`
- end: `0x145dc6`
- name: `System.Web.Configuration.HttpCapabilitiesBase::get_TagWriter`
- size: `134`
- prototype: ``
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x3c80`
- `0x7ab00`
- `0x1455f0`

## callees

- `0x145560`
- `0x145b80`
- `0x145d40`
- `0x176030`

## string_xrefs

- `0x145d4b`: `tagwriter`
- `0x145db2`: `tagwriter`

## pseudocode

```c

```

## disassembly

```asm
0x145d40  ldarg.0
0x145d41  volatile.
0x145d43  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool System.Web.Configuration.HttpCapabilitiesBase::_havetagwriter
0x145d48  brtrue.s loc_145DAD
0x145d4a  ldarg.0
0x145d4b  ldstr    aTagwriter// "tagwriter"
0x145d50  callvirt instance string System.Web.Configuration.HttpCapabilitiesBase::get_Item(string key)
0x145d55  stloc.0
0x145d56  ldloc.0
0x145d57  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x145d5c  brfalse.s loc_145D69
0x145d5e  ldarg.0
0x145d5f  ldnull
0x145d60  volatile.
0x145d62  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Type System.Web.Configuration.HttpCapabilitiesBase::_tagwriter
0x145d67  br.s     loc_145DA4
0x145d69  ldloc.0
0x145d6a  ldtoken  System.Web.UI.HtmlTextWriter
0x145d6f  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x145d74  callvirt instance string [mscorlib]System.Type::get_FullName()
0x145d79  ldc.i4.4
0x145d7a  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x145d7f  brtrue.s loc_145D95
0x145d81  ldarg.0
0x145d82  ldtoken  System.Web.UI.HtmlTextWriter
0x145d87  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x145d8c  volatile.
0x145d8e  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Type System.Web.Configuration.HttpCapabilitiesBase::_tagwriter
0x145d93  br.s     loc_145DA4
0x145d95  ldarg.0
0x145d96  ldloc.0
0x145d97  ldc.i4.1
0x145d98  call     class [mscorlib]System.Type System.Web.Compilation.BuildManager::GetType(string typeName, bool throwOnError)
0x145d9d  volatile.
0x145d9f  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Type System.Web.Configuration.HttpCapabilitiesBase::_tagwriter
0x145da4  ldarg.0
0x145da5  ldc.i4.1
0x145da6  volatile.
0x145da8  stfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool System.Web.Configuration.HttpCapabilitiesBase::_havetagwriter
0x145dad  leave.s  loc_145DBD
0x145daf  stloc.1
0x145db0  ldarg.0
0x145db1  ldloc.1
0x145db2  ldstr    aTagwriter// "tagwriter"
0x145db7  call     instance class [mscorlib]System.Exception System.Web.Configuration.HttpCapabilitiesBase::BuildParseError(class [mscorlib]System.Exception e, string capsKey)
0x145dbc  throw
0x145dbd  ldarg.0
0x145dbe  volatile.
0x145dc0  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) class [mscorlib]System.Type System.Web.Configuration.HttpCapabilitiesBase::_tagwriter
0x145dc5  ret
```
