# System.Deployment.Application.PlatformDetector::IsSupportedProcessorArchitecture

- ea: `0x1b560`
- end: `0x1b68a`
- name: `System.Deployment.Application.PlatformDetector::IsSupportedProcessorArchitecture`
- size: `298`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x25bc0`

## callees

- `0x17d40`
- `0x1a210`
- `0x1a220`
- `0x1a230`
- `0x1b560`

## string_xrefs

- `0x1b5e9`: `In IsSupportedProcessorArchitecture: GetNativeSystemInfo API from kernel32.dll is not found.`
- `0x1b606`: `In IsSupportedProcessorArchitecture: GetNativeSystemInfo API from kernel32.dll is not found.`

## pseudocode

```c

```

## disassembly

```asm
0x1b560  ldarg.0
0x1b561  ldstr    aMsil// "msil"
0x1b566  ldc.i4.5
0x1b567  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b56c  brfalse.s loc_1B57C
0x1b56e  ldarg.0
0x1b56f  ldstr    aX86// "x86"
0x1b574  ldc.i4.5
0x1b575  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b57a  brtrue.s loc_1B57E
0x1b57c  ldc.i4.1
0x1b57d  ret
0x1b57e  ldloca.s 0
0x1b580  initobj  SYSTEM_INFO
0x1b586  ldc.i4.0
0x1b587  stloc.1
0x1b588  ldc.i4.m1
0x1b589  newobj   instance void [mscorlib]System.IntPtr::.ctor(int32)
0x1b58e  ldloca.s 3
0x1b590  ldloca.s 2
0x1b592  call     bool System.Deployment.Application.NativeMethods::IsWow64Process2([hasfieldmarshal] native int, unsigned int16& processHandle, [out] unsigned int16& pProcessMachine)
0x1b597  brfalse.s loc_1B5E6
0x1b599  ldloc.2
0x1b59a  ldc.i4   0x14C
0x1b59f  beq.s    loc_1B5B3
0x1b5a1  ldloc.2
0x1b5a2  ldc.i4   0x8664
0x1b5a7  beq.s    loc_1B5C4
0x1b5a9  ldloc.2
0x1b5aa  ldc.i4   0xAA64
0x1b5af  beq.s    loc_1B5D6
0x1b5b1  br.s     loc_1B5E6
0x1b5b3  ldloca.s 0
0x1b5b5  ldflda   valuetype _PROCESSOR_INFO_UNION SYSTEM_INFO::uProcessorInfo
0x1b5ba  ldc.i4.0
0x1b5bb  stfld    unsigned int16 _PROCESSOR_INFO_UNION::wProcessorArchitecture
0x1b5c0  ldc.i4.1
0x1b5c1  stloc.1
0x1b5c2  br.s     loc_1B5E6
0x1b5c4  ldloca.s 0
0x1b5c6  ldflda   valuetype _PROCESSOR_INFO_UNION SYSTEM_INFO::uProcessorInfo
0x1b5cb  ldc.i4.s 9
0x1b5cd  stfld    unsigned int16 _PROCESSOR_INFO_UNION::wProcessorArchitecture
0x1b5d2  ldc.i4.1
0x1b5d3  stloc.1
0x1b5d4  br.s     loc_1B5E6
0x1b5d6  ldloca.s 0
0x1b5d8  ldflda   valuetype _PROCESSOR_INFO_UNION SYSTEM_INFO::uProcessorInfo
0x1b5dd  ldc.i4.s 0xC
0x1b5df  stfld    unsigned int16 _PROCESSOR_INFO_UNION::wProcessorArchitecture
0x1b5e4  ldc.i4.1
0x1b5e5  stloc.1
0x1b5e6  leave.s  loc_1B5F7
0x1b5e8  pop
0x1b5e9  ldstr    aInIssupportedp// "In IsSupportedProcessorArchitecture: Ge"...
0x1b5ee  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1b5f3  ldc.i4.0
0x1b5f4  stloc.1
0x1b5f5  leave.s  loc_1B5F7
0x1b5f7  ldloc.1
0x1b5f8  brtrue.s loc_1B614
0x1b5fa  ldloca.s 0
0x1b5fc  call     void System.Deployment.Application.NativeMethods::GetNativeSystemInfo([hasfieldmarshal] valuetype SYSTEM_INFO& sysInfo)
0x1b601  ldc.i4.1
0x1b602  stloc.1
0x1b603  leave.s  loc_1B614
0x1b605  pop
0x1b606  ldstr    aInIssupportedp// "In IsSupportedProcessorArchitecture: Ge"...
0x1b60b  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1b610  ldc.i4.0
0x1b611  stloc.1
0x1b612  leave.s  loc_1B614
0x1b614  ldloc.1
0x1b615  brtrue.s loc_1B628
0x1b617  ldloca.s 0
0x1b619  call     void System.Deployment.Application.NativeMethods::GetSystemInfo([hasfieldmarshal] valuetype SYSTEM_INFO& sysInfo)
0x1b61e  ldstr    aInIssupportedp_0// "In IsSupportedProcessorArchitecture: Ge"...
0x1b623  call     void System.Deployment.Application.Logger::AddInternalState(string message)
0x1b628  ldloc.0
0x1b629  ldfld    valuetype _PROCESSOR_INFO_UNION SYSTEM_INFO::uProcessorInfo
0x1b62e  ldfld    unsigned int16 _PROCESSOR_INFO_UNION::wProcessorArchitecture
0x1b633  stloc.s  4
0x1b635  ldloc.s  4
0x1b637  ldc.i4.6
0x1b638  beq.s    loc_1B648
0x1b63a  ldloc.s  4
0x1b63c  ldc.i4.s 9
0x1b63e  beq.s    loc_1B658
0x1b640  ldloc.s  4
0x1b642  ldc.i4.s 0xC
0x1b644  beq.s    loc_1B668
0x1b646  br.s     loc_1B688
0x1b648  ldarg.0
0x1b649  ldstr    aIa64// "ia64"
0x1b64e  ldc.i4.5
0x1b64f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b654  ldc.i4.0
0x1b655  ceq
0x1b657  ret
0x1b658  ldarg.0
0x1b659  ldstr    aAmd64// "amd64"
0x1b65e  ldc.i4.5
0x1b65f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b664  ldc.i4.0
0x1b665  ceq
0x1b667  ret
0x1b668  ldarg.0
0x1b669  ldstr    aArm64// "arm64"
0x1b66e  ldc.i4.5
0x1b66f  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b674  brfalse.s loc_1B686
0x1b676  ldarg.0
0x1b677  ldstr    aAmd64// "amd64"
0x1b67c  ldc.i4.5
0x1b67d  call     int32 [mscorlib]System.String::Compare(string, string, valuetype [mscorlib]System.StringComparison)
0x1b682  ldc.i4.0
0x1b683  ceq
0x1b685  ret
0x1b686  ldc.i4.1
0x1b687  ret
0x1b688  ldc.i4.0
0x1b689  ret
```
