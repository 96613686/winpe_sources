# System.Windows.Media.GlyphTypeface::set_FontUri

- ea: `0x9ac40`
- end: `0x9ac84`
- name: `System.Windows.Media.GlyphTypeface::set_FontUri`
- size: `68`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x9ac40`
- `0x9bbe0`
- `0x146e40`

## string_xrefs

- `0x9ac62`: `UriNotAbsolute`

## pseudocode

```c

```

## disassembly

```asm
0x9ac40  ldarg.0
0x9ac41  call     instance void System.Windows.Media.GlyphTypeface::CheckInitializing()
0x9ac46  ldarg.1
0x9ac47  ldnull
0x9ac48  call     bool [System]System.Uri::op_Equality(class [System]System.Uri, class [System]System.Uri)
0x9ac4d  brfalse.s loc_9AC5A
0x9ac4f  ldstr    aValue// "value"
0x9ac54  newobj   instance void [mscorlib]System.ArgumentNullException::.ctor(string)
0x9ac59  throw
0x9ac5a  ldarg.1
0x9ac5b  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x9ac60  brtrue.s loc_9AC77
0x9ac62  ldstr    aUrinotabsolute// "UriNotAbsolute"
0x9ac67  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x9ac6c  ldstr    aValue// "value"
0x9ac71  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x9ac76  throw
0x9ac77  ldarg.0
0x9ac78  ldarg.1
0x9ac79  newobj   instance void class [WindowsBase]MS.Internal.SecurityCriticalDataClass`1<class [System]System.Uri>::.ctor(var<u1>)
0x9ac7e  stfld    class [WindowsBase]MS.Internal.SecurityCriticalDataClass`1<class [System]System.Uri> System.Windows.Media.GlyphTypeface::_originalUri
0x9ac83  ret
```
