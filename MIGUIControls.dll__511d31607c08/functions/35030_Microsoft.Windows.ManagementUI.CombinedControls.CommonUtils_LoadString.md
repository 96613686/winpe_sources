# Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::LoadString

- ea: `0x35030`
- end: `0x350cb`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CommonUtils::LoadString`
- size: `155`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x351d0`

## callees

- `0x11f30`
- `0x12130`
- `0x13510`
- `0x35030`

## string_xrefs

- `0x35078`: `Unable to load Library for reading resource`
- `0x350b5`: `Unable to load string for reading resource`

## pseudocode

```c

```

## disassembly

```asm
0x35030  ldsfld   string [mscorlib]System.String::Empty
0x35035  stloc.0
0x35036  ldarg.1
0x35037  callvirt instance string [mscorlib]System.String::Trim()
0x3503c  starg.s  1
0x3503e  ldc.i4.0
0x3503f  stloc.1
0x35040  ldarg.0
0x35041  ldind.i
0x35042  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x35047  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3504c  brfalse.s loc_35088
0x3504e  ldarg.1
0x3504f  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x35054  brtrue.s loc_35088
0x35056  ldarg.0
0x35057  ldarg.1
0x35058  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3505d  ldc.i4.2
0x3505e  call     native int Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::LoadLibraryEx([hasfieldmarshal] string lpFileName, native int hFile, unsigned int32 dwFlags)
0x35063  stind.i
0x35064  ldarg.0
0x35065  ldind.i
0x35066  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3506b  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x35070  brfalse.s loc_35083
0x35072  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x35077  stloc.1
0x35078  ldstr    aUnableToLoadLi// "Unable to load Library for reading reso"...
0x3507d  ldloc.1
0x3507e  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x35083  leave.s  loc_35088
0x35085  pop
0x35086  leave.s  loc_35088
0x35088  ldarg.0
0x35089  ldind.i
0x3508a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3508f  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x35094  brfalse.s loc_350C9
0x35096  ldc.i4   0x3E8
0x3509b  stloc.2
0x3509c  ldloc.2
0x3509d  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(int32)
0x350a2  stloc.3
0x350a3  ldarg.0
0x350a4  ldind.i
0x350a5  ldarg.2
0x350a6  ldloc.3
0x350a7  ldloc.2
0x350a8  call     int32 Microsoft.Windows.ManagementUI.CombinedControls.NativeMethods::LoadString(native int hModule, int32 resourceID, class [mscorlib]System.Text.StringBuilder resourceValue, int32 len)
0x350ad  brtrue.s loc_350C2
0x350af  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x350b4  stloc.1
0x350b5  ldstr    aUnableToLoadSt// "Unable to load string for reading resou"...
0x350ba  ldloc.1
0x350bb  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x350c0  br.s     loc_350C9
0x350c2  ldloc.3
0x350c3  callvirt instance string [mscorlib]System.Object::ToString()
0x350c8  stloc.0
0x350c9  ldloc.0
0x350ca  ret
```
