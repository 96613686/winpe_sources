# MS.Internal.AssemblyHelper::LoadExtensionFor

- ea: `0xea00`
- end: `0xea6e`
- name: `MS.Internal.AssemblyHelper::LoadExtensionFor`
- size: `110`
- prototype: ``
- caller_count: `5`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0xe910`
- `0xe940`
- `0xe970`
- `0xe9a0`
- `0xe9d0`

## callees

- `0xea00`

## string_xrefs

- `0xea44`: `Extension`

## pseudocode

```c

```

## disassembly

```asm
0xea00  ldc.i4.1
0xea01  newobj   instance void [mscorlib]System.Security.PermissionSet::.ctor(valuetype [mscorlib]System.Security.Permissions.PermissionState)
0xea06  stloc.0
0xea07  ldloc.0
0xea08  callvirt instance void [mscorlib]System.Security.PermissionSet::Assert()
0xea0d  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0xea12  callvirt instance string [mscorlib]System.Reflection.Assembly::get_FullName()
0xea17  stloc.1
0xea18  ldloc.1
0xea19  ldstr    aWindowsbase// "WindowsBase"
0xea1e  ldstr    aPresentationfr// "PresentationFramework-"
0xea23  ldarg.0
0xea24  call     string [mscorlib]System.String::Concat(string, string)
0xea29  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xea2e  ldstr    a31bf3856ad364e// "31bf3856ad364e35"
0xea33  ldstr    aB77a5c561934e0// "b77a5c561934e089"
0xea38  callvirt instance string [mscorlib]System.String::Replace(string, string)
0xea3d  stloc.2
0xea3e  ldstr    aMsInternal// "MS.Internal."
0xea43  ldarg.0
0xea44  ldstr    aExtension// "Extension"
0xea49  call     string [mscorlib]System.String::Concat(string, string, string)
0xea4e  stloc.3
0xea4f  ldloc.2
0xea50  ldloc.3
0xea51  call     class [mscorlib]System.Runtime.Remoting.ObjectHandle [mscorlib]System.Activator::CreateInstance(string, string)
0xea56  stloc.s  4
0xea58  leave.s  loc_EA60
0xea5a  pop
0xea5b  ldnull
0xea5c  stloc.s  4
0xea5e  leave.s  loc_EA60
0xea60  ldloc.s  4
0xea62  brtrue.s loc_EA66
0xea64  ldnull
0xea65  ret
0xea66  ldloc.s  4
0xea68  callvirt instance object [mscorlib]System.Runtime.Remoting.ObjectHandle::Unwrap()
0xea6d  ret
```
