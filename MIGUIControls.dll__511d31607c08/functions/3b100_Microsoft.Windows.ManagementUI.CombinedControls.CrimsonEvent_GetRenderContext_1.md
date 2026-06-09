# Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetRenderContext_1

- ea: `0x3b100`
- end: `0x3b307`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.CrimsonEvent::GetRenderContext_1`
- size: `519`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x3b350`

## callees

- `0x12840`
- `0x12860`
- `0x13510`
- `0x3b100`
- `0x4d1c0`

## string_xrefs

- `0x3b172`: `Unable to create render context for property `
- `0x3b1e6`: `Unable to create render context for property `
- `0x3b25b`: `Unable to create render context for property `
- `0x3b2ce`: `Unable to create render context for property `

## pseudocode

```c

```

## disassembly

```asm
0x3b100  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b105  stloc.0
0x3b106  ldc.i4.1
0x3b107  newarr   [mscorlib]System.String
0x3b10c  stloc.1
0x3b10d  call     void [mscorlib]System.Runtime.CompilerServices.RuntimeHelpers::PrepareConstrainedRegions()
0x3b112  leave    loc_3B305
0x3b117  ldarg.0
0x3b118  ldc.i4.1
0x3b119  sub
0x3b11a  switch   loc_3B304, loc_3B138, loc_3B220, loc_3B1AC, loc_3B293
0x3b133  br       loc_3B304
0x3b138  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeLevelContext
0x3b13d  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b142  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b147  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b14c  brfalse.s loc_3B19C
0x3b14e  ldloc.1
0x3b14f  ldc.i4.0
0x3b150  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::LevelsPath
0x3b155  stelem.ref
0x3b156  ldc.i4.1
0x3b157  ldloc.1
0x3b158  ldc.i4.0
0x3b159  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x3b15e  stloc.0
0x3b15f  ldloc.0
0x3b160  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b165  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b16a  brfalse.s loc_3B191
0x3b16c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b171  stloc.2
0x3b172  ldstr    aUnableToCreate// "Unable to create render context for pro"...
0x3b177  ldloc.1
0x3b178  dup
0x3b179  brtrue.s loc_3B17F
0x3b17b  pop
0x3b17c  ldnull
0x3b17d  br.s     loc_3B184
0x3b17f  callvirt instance string [mscorlib]System.Object::ToString()
0x3b184  call     string [mscorlib]System.String::Concat(string, string)
0x3b189  ldloc.2
0x3b18a  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3b18f  br.s     loc_3B19C
0x3b191  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeLevelContext
0x3b196  ldloc.0
0x3b197  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x3b19c  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeLevelContext
0x3b1a1  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b1a6  stloc.0
0x3b1a7  br       loc_3B304
0x3b1ac  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeOpcodeContext
0x3b1b1  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b1b6  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b1bb  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b1c0  brfalse.s loc_3B210
0x3b1c2  ldloc.1
0x3b1c3  ldc.i4.0
0x3b1c4  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::OpcodePath
0x3b1c9  stelem.ref
0x3b1ca  ldc.i4.1
0x3b1cb  ldloc.1
0x3b1cc  ldc.i4.0
0x3b1cd  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x3b1d2  stloc.0
0x3b1d3  ldloc.0
0x3b1d4  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b1d9  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b1de  brfalse.s loc_3B205
0x3b1e0  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b1e5  stloc.3
0x3b1e6  ldstr    aUnableToCreate// "Unable to create render context for pro"...
0x3b1eb  ldloc.1
0x3b1ec  dup
0x3b1ed  brtrue.s loc_3B1F3
0x3b1ef  pop
0x3b1f0  ldnull
0x3b1f1  br.s     loc_3B1F8
0x3b1f3  callvirt instance string [mscorlib]System.Object::ToString()
0x3b1f8  call     string [mscorlib]System.String::Concat(string, string)
0x3b1fd  ldloc.3
0x3b1fe  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3b203  br.s     loc_3B210
0x3b205  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeOpcodeContext
0x3b20a  ldloc.0
0x3b20b  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x3b210  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeOpcodeContext
0x3b215  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b21a  stloc.0
0x3b21b  br       loc_3B304
0x3b220  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeTaskContext
0x3b225  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b22a  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b22f  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b234  brfalse.s loc_3B286
0x3b236  ldloc.1
0x3b237  ldc.i4.0
0x3b238  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::TasksPath
0x3b23d  stelem.ref
0x3b23e  ldc.i4.1
0x3b23f  ldloc.1
0x3b240  ldc.i4.0
0x3b241  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x3b246  stloc.0
0x3b247  ldloc.0
0x3b248  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b24d  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b252  brfalse.s loc_3B27B
0x3b254  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b259  stloc.s  4
0x3b25b  ldstr    aUnableToCreate// "Unable to create render context for pro"...
0x3b260  ldloc.1
0x3b261  dup
0x3b262  brtrue.s loc_3B268
0x3b264  pop
0x3b265  ldnull
0x3b266  br.s     loc_3B26D
0x3b268  callvirt instance string [mscorlib]System.Object::ToString()
0x3b26d  call     string [mscorlib]System.String::Concat(string, string)
0x3b272  ldloc.s  4
0x3b274  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3b279  br.s     loc_3B286
0x3b27b  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeTaskContext
0x3b280  ldloc.0
0x3b281  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x3b286  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeTaskContext
0x3b28b  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b290  stloc.0
0x3b291  br.s     loc_3B304
0x3b293  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeKeyWordContext
0x3b298  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b29d  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b2a2  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b2a7  brfalse.s loc_3B2F9
0x3b2a9  ldloc.1
0x3b2aa  ldc.i4.0
0x3b2ab  ldsfld   string Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::KeywordsPath
0x3b2b0  stelem.ref
0x3b2b1  ldc.i4.1
0x3b2b2  ldloc.1
0x3b2b3  ldc.i4.0
0x3b2b4  call     native int Microsoft.Windows.ManagementUI.CombinedControls.SafeNativeMethods::CreateRenderContext(int32 countOfValues, string[] valuePaths, int32 flags)
0x3b2b9  stloc.0
0x3b2ba  ldloc.0
0x3b2bb  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x3b2c0  call     bool [mscorlib]System.IntPtr::op_Equality(native int, native int)
0x3b2c5  brfalse.s loc_3B2EE
0x3b2c7  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x3b2cc  stloc.s  5
0x3b2ce  ldstr    aUnableToCreate// "Unable to create render context for pro"...
0x3b2d3  ldloc.1
0x3b2d4  dup
0x3b2d5  brtrue.s loc_3B2DB
0x3b2d7  pop
0x3b2d8  ldnull
0x3b2d9  br.s     loc_3B2E0
0x3b2db  callvirt instance string [mscorlib]System.Object::ToString()
0x3b2e0  call     string [mscorlib]System.String::Concat(string, string)
0x3b2e5  ldloc.s  5
0x3b2e7  call     void Microsoft.Windows.ManagementUI.CombinedControls.DisplayError::TraceWin32Error(string errString, int32 errorNumber)
0x3b2ec  br.s     loc_3B2F9
0x3b2ee  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeKeyWordContext
0x3b2f3  ldloc.0
0x3b2f4  callvirt instance void Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::InitHandle(native int crimsonHandle)
0x3b2f9  ldsfld   class Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle Microsoft.Windows.ManagementUI.CombinedControls.CrimsonRenderingInfo::safeKeyWordContext
0x3b2fe  callvirt instance native int Microsoft.Windows.ManagementUI.CombinedControls.SafeCrimsonHandle::get_Handle()
0x3b303  stloc.0
0x3b304  endfinally
0x3b305  ldloc.0
0x3b306  ret
```
