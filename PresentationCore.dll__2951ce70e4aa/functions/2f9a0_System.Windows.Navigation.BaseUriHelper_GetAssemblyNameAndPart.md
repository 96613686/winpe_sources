# System.Windows.Navigation.BaseUriHelper::GetAssemblyNameAndPart

- ea: `0x2f9a0`
- end: `0x2fae4`
- name: `System.Windows.Navigation.BaseUriHelper::GetAssemblyNameAndPart`
- size: `324`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x2f900`
- `0x2fcb0`

## callees

- `0x2f9a0`
- `0x146e40`

## string_xrefs

- `0x2f9b5`: `This method accepts relative uri only.`
- `0x2fa1d`: `;component`

## pseudocode

```c

```

## disassembly

```asm
0x2f9a0  ldarg.0
0x2f9a1  ldnull
0x2f9a2  call     bool [System]System.Uri::op_Inequality(class [System]System.Uri, class [System]System.Uri)
0x2f9a7  brfalse.s loc_2F9B4
0x2f9a9  ldarg.0
0x2f9aa  callvirt instance bool [System]System.Uri::get_IsAbsoluteUri()
0x2f9af  ldc.i4.0
0x2f9b0  ceq
0x2f9b2  br.s     loc_2F9B5
0x2f9b4  ldc.i4.0
0x2f9b5  ldstr    aThisMethodAcce// "This method accepts relative uri only."
0x2f9ba  call     void [WindowsBase]MS.Internal.Invariant::Assert(bool, string)
0x2f9bf  ldarg.0
0x2f9c0  callvirt instance string [mscorlib]System.Object::ToString()
0x2f9c5  stloc.3
0x2f9c6  ldc.i4.0
0x2f9c7  stloc.2
0x2f9c8  ldloc.3
0x2f9c9  ldc.i4.0
0x2f9ca  callvirt instance char [mscorlib]System.String::get_Chars(int32)
0x2f9cf  ldc.i4.s 0x2F
0x2f9d1  bne.un.s loc_2F9D5
0x2f9d3  ldc.i4.1
0x2f9d4  stloc.2
0x2f9d5  ldarg.1
0x2f9d6  ldloc.3
0x2f9d7  ldloc.2
0x2f9d8  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2f9dd  stind.ref
0x2f9de  ldarg.2
0x2f9df  ldsfld   string [mscorlib]System.String::Empty
0x2f9e4  stind.ref
0x2f9e5  ldarg.3
0x2f9e6  ldsfld   string [mscorlib]System.String::Empty
0x2f9eb  stind.ref
0x2f9ec  ldarg.s  4
0x2f9ee  ldsfld   string [mscorlib]System.String::Empty
0x2f9f3  stind.ref
0x2f9f4  ldloc.3
0x2f9f5  ldc.i4.s 0x2F
0x2f9f7  ldloc.2
0x2f9f8  callvirt instance int32 [mscorlib]System.String::IndexOf(char, int32)
0x2f9fd  stloc.s  6
0x2f9ff  ldsfld   string [mscorlib]System.String::Empty
0x2fa04  stloc.s  5
0x2fa06  ldc.i4.0
0x2fa07  stloc.s  7
0x2fa09  ldloc.s  6
0x2fa0b  ldc.i4.0
0x2fa0c  ble.s    loc_2FA39
0x2fa0e  ldloc.3
0x2fa0f  ldloc.2
0x2fa10  ldloc.s  6
0x2fa12  ldloc.2
0x2fa13  sub
0x2fa14  callvirt instance string [mscorlib]System.String::Substring(int32, int32)
0x2fa19  stloc.s  5
0x2fa1b  ldloc.s  5
0x2fa1d  ldstr    aComponent// ";component"
0x2fa22  ldc.i4.5
0x2fa23  callvirt instance bool [mscorlib]System.String::EndsWith(string, valuetype [mscorlib]System.StringComparison)
0x2fa28  brfalse.s loc_2FA39
0x2fa2a  ldarg.1
0x2fa2b  ldloc.3
0x2fa2c  ldloc.s  6
0x2fa2e  ldc.i4.1
0x2fa2f  add
0x2fa30  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2fa35  stind.ref
0x2fa36  ldc.i4.1
0x2fa37  stloc.s  7
0x2fa39  ldloc.s  7
0x2fa3b  brfalse  loc_2FAE3
0x2fa40  ldloc.s  5
0x2fa42  ldc.i4.1
0x2fa43  newarr   [mscorlib]System.Char
0x2fa48  dup
0x2fa49  ldc.i4.0
0x2fa4a  ldc.i4.s 0x3B
0x2fa4c  stelem.i2
0x2fa4d  callvirt instance string[] [mscorlib]System.String::Split(char[])
0x2fa52  stloc.1
0x2fa53  ldloc.1
0x2fa54  ldlen
0x2fa55  conv.i4
0x2fa56  stloc.s  4
0x2fa58  ldloc.s  4
0x2fa5a  ldc.i4.4
0x2fa5b  bgt.s    loc_2FA62
0x2fa5d  ldloc.s  4
0x2fa5f  ldc.i4.2
0x2fa60  bge.s    loc_2FA72
0x2fa62  ldstr    aWrongfirstsegm// "WrongFirstSegment"
0x2fa67  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2fa6c  newobj   instance void [System]System.UriFormatException::.ctor(string)
0x2fa71  throw
0x2fa72  ldarg.2
0x2fa73  ldloc.1
0x2fa74  ldc.i4.0
0x2fa75  ldelem.ref
0x2fa76  call     string [System]System.Uri::UnescapeDataString(string)
0x2fa7b  stind.ref
0x2fa7c  ldc.i4.1
0x2fa7d  stloc.0
0x2fa7e  br.s     loc_2FADC
0x2fa80  ldloc.1
0x2fa81  ldloc.0
0x2fa82  ldelem.ref
0x2fa83  ldstr    aV// "v"
0x2fa88  ldc.i4.5
0x2fa89  callvirt instance bool [mscorlib]System.String::StartsWith(string, valuetype [mscorlib]System.StringComparison)
0x2fa8e  brfalse.s loc_2FAB6
0x2fa90  ldarg.3
0x2fa91  ldind.ref
0x2fa92  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fa97  brfalse.s loc_2FAA6
0x2fa99  ldarg.3
0x2fa9a  ldloc.1
0x2fa9b  ldloc.0
0x2fa9c  ldelem.ref
0x2fa9d  ldc.i4.1
0x2fa9e  callvirt instance string [mscorlib]System.String::Substring(int32)
0x2faa3  stind.ref
0x2faa4  br.s     loc_2FAD8
0x2faa6  ldstr    aWrongfirstsegm// "WrongFirstSegment"
0x2faab  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2fab0  newobj   instance void [System]System.UriFormatException::.ctor(string)
0x2fab5  throw
0x2fab6  ldarg.s  4
0x2fab8  ldind.ref
0x2fab9  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x2fabe  brfalse.s loc_2FAC8
0x2fac0  ldarg.s  4
0x2fac2  ldloc.1
0x2fac3  ldloc.0
0x2fac4  ldelem.ref
0x2fac5  stind.ref
0x2fac6  br.s     loc_2FAD8
0x2fac8  ldstr    aWrongfirstsegm// "WrongFirstSegment"
0x2facd  call     string MS.Internal.PresentationCore.SR::Get(string id)
0x2fad2  newobj   instance void [System]System.UriFormatException::.ctor(string)
0x2fad7  throw
0x2fad8  ldloc.0
0x2fad9  ldc.i4.1
0x2fada  add
0x2fadb  stloc.0
0x2fadc  ldloc.0
0x2fadd  ldloc.s  4
0x2fadf  ldc.i4.1
0x2fae0  sub
0x2fae1  blt.s    loc_2FA80
0x2fae3  ret
```
