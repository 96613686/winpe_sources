# <GetUserProfileDirectories>d__10::MoveNext

- ea: `0x4fe0`
- end: `0x5203`
- name: `<GetUserProfileDirectories>d__10::MoveNext`
- size: `547`
- prototype: ``
- caller_count: `0`
- callee_count: `6`
- tags: `broker_com_uri`

## callees

- `0x2c30`
- `0x2c60`
- `0x3fb0`
- `0x4fc0`
- `0x4fe0`
- `0x5210`

## string_xrefs

- `0x5051`: `Invalid user profile path "{0}"`
- `0x5172`: `Invalid user profile path "{0}"`
- `0x50dd`: `LocalPath`
- `0x5119`: `Unable to retrieve complete list of user profiles`

## pseudocode

```c

```

## disassembly

```asm
0x4fe0  ldarg.0
0x4fe1  ldfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x4fe6  stloc.1
0x4fe7  ldarg.0
0x4fe8  ldfld    class NGenTask.AppDataDirectoryWalker <GetUserProfileDirectories>d__10::<>4__this
0x4fed  stloc.2
0x4fee  ldloc.1
0x4fef  switch   loc_5007, loc_5082, loc_51AF
0x5000  ldc.i4.0
0x5001  stloc.0
0x5002  leave    loc_5201
0x5007  ldarg.0
0x5008  ldc.i4.m1
0x5009  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x500e  ldc.i4.3
0x500f  ldstr    aGatheringUserP// "Gathering User Profile Directories"
0x5014  ldc.i4.0
0x5015  newarr   [mscorlib]System.Object
0x501a  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x501f  ldloc.2
0x5020  ldfld    bool NGenTask.AppDataDirectoryWalker::m_userLocal
0x5025  brfalse.s loc_508E
0x5027  ldc.i4.s 0x28
0x5029  call     string [mscorlib]System.Environment::GetFolderPath(valuetype [mscorlib]System.Environment/SpecialFolder)
0x502e  stloc.3
0x502f  ldloc.2
0x5030  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x5035  brtrue.s loc_503A
0x5037  ldloc.3
0x5038  brtrue.s loc_5041
0x503a  ldc.i4.0
0x503b  stloc.0
0x503c  leave    loc_5201
0x5041  nop
0x5042  ldloc.3
0x5043  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x5048  stloc.s  4
0x504a  leave.s  loc_506C
0x504c  stloc.s  5
0x504e  ldc.i4.0
0x504f  ldloc.s  5
0x5051  ldstr    aInvalidUserPro// "Invalid user profile path \"{0}\""
0x5056  ldc.i4.1
0x5057  newarr   [mscorlib]System.Object
0x505c  dup
0x505d  ldc.i4.0
0x505e  ldloc.3
0x505f  stelem.ref
0x5060  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x5065  ldc.i4.0
0x5066  stloc.0
0x5067  leave    loc_5201
0x506c  ldarg.0
0x506d  ldloc.s  4
0x506f  stfld    class [mscorlib]System.IO.DirectoryInfo <GetUserProfileDirectories>d__10::<>2__current
0x5074  ldarg.0
0x5075  ldc.i4.1
0x5076  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x507b  ldc.i4.1
0x507c  stloc.0
0x507d  leave    loc_5201
0x5082  ldarg.0
0x5083  ldc.i4.m1
0x5084  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x5089  br       loc_51F6
0x508e  ldc.i4.3
0x508f  ldstr    aSearchingAllUs// "Searching all users"
0x5094  ldc.i4.0
0x5095  newarr   [mscorlib]System.Object
0x509a  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x509f  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<string>::.ctor()
0x50a4  stloc.s  6
0x50a6  ldstr    aSelectFromWin3// "select * from Win32_UserProfile"
0x50ab  newobj   instance void [System.Management]System.Management.ManagementObjectSearcher::.ctor(string)
0x50b0  call     instance class [System.Management]System.Management.ManagementObjectCollection [System.Management]System.Management.ManagementObjectSearcher::Get()
0x50b5  callvirt instance class [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator [System.Management]System.Management.ManagementObjectCollection::GetEnumerator()
0x50ba  stloc.s  7
0x50bc  br.s     loc_50FB
0x50be  ldloc.s  7
0x50c0  callvirt instance class [System.Management]System.Management.ManagementBaseObject [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::get_Current()
0x50c5  castclass [System.Management]System.Management.ManagementObject
0x50ca  stloc.s  8
0x50cc  ldloc.2
0x50cd  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x50d2  brfalse.s loc_50DB
0x50d4  ldc.i4.0
0x50d5  stloc.0
0x50d6  leave    loc_5201
0x50db  ldloc.s  8
0x50dd  ldstr    aLocalpath// "LocalPath"
0x50e2  callvirt instance object [System.Management]System.Management.ManagementBaseObject::get_Item(string)
0x50e7  castclass [mscorlib]System.String
0x50ec  stloc.s  9
0x50ee  ldloc.s  9
0x50f0  brfalse.s loc_50FB
0x50f2  ldloc.s  6
0x50f4  ldloc.s  9
0x50f6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<string>::Add(var<u1>)
0x50fb  ldloc.s  7
0x50fd  callvirt instance bool [System.Management]System.Management.ManagementObjectCollection/ManagementObjectEnumerator::MoveNext()
0x5102  brtrue.s loc_50BE
0x5104  leave.s  loc_5112
0x5106  ldloc.s  7
0x5108  brfalse.s loc_5111
0x510a  ldloc.s  7
0x510c  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x5111  endfinally
0x5112  leave.s  loc_512B
0x5114  stloc.s  0xA
0x5116  ldc.i4.0
0x5117  ldloc.s  0xA
0x5119  ldstr    aUnableToRetrie_0// "Unable to retrieve complete list of use"...
0x511e  ldc.i4.0
0x511f  newarr   [mscorlib]System.Object
0x5124  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x5129  leave.s  loc_512B
0x512b  ldarg.0
0x512c  ldloc.s  6
0x512e  callvirt instance valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<var<u1>> class [mscorlib]System.Collections.Generic.List`1<string>::GetEnumerator()
0x5133  stfld    valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string> <GetUserProfileDirectories>d__10::<>7__wrap1
0x5138  ldarg.0
0x5139  ldc.i4.s 0xFD
0x513b  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x5140  br       loc_51CA
0x5145  ldarg.0
0x5146  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string> <GetUserProfileDirectories>d__10::<>7__wrap1
0x514b  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::get_Current()
0x5150  stloc.s  0xB
0x5152  ldloc.2
0x5153  call     instance bool NGenTask.AppDataDirectoryWalker::IsStopRequested()
0x5158  brfalse.s loc_5161
0x515a  ldc.i4.0
0x515b  stloc.0
0x515c  br       loc_51E2
0x5161  nop
0x5162  ldloc.s  0xB
0x5164  newobj   instance void [mscorlib]System.IO.DirectoryInfo::.ctor(string)
0x5169  stloc.s  0xC
0x516b  leave.s  loc_5189
0x516d  stloc.s  0xD
0x516f  ldc.i4.0
0x5170  ldloc.s  0xD
0x5172  ldstr    aInvalidUserPro// "Invalid user profile path \"{0}\""
0x5177  ldc.i4.1
0x5178  newarr   [mscorlib]System.Object
0x517d  dup
0x517e  ldc.i4.0
0x517f  ldloc.s  0xB
0x5181  stelem.ref
0x5182  call     void NGenTask.Logger::Log(valuetype LogLevel level, class [mscorlib]System.Exception ex, string format, object[] args)
0x5187  leave.s  loc_51CA
0x5189  ldloc.s  0xC
0x518b  callvirt instance string [mscorlib]System.IO.FileSystemInfo::get_FullName()
0x5190  ldstr    asc_9C9C// "\\\\"
0x5195  callvirt instance bool [mscorlib]System.String::StartsWith(string)
0x519a  brtrue.s loc_51B9
0x519c  ldarg.0
0x519d  ldloc.s  0xC
0x519f  stfld    class [mscorlib]System.IO.DirectoryInfo <GetUserProfileDirectories>d__10::<>2__current
0x51a4  ldarg.0
0x51a5  ldc.i4.2
0x51a6  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x51ab  ldc.i4.1
0x51ac  stloc.0
0x51ad  leave.s  loc_5201
0x51af  ldarg.0
0x51b0  ldc.i4.s 0xFD
0x51b2  stfld    int32 <GetUserProfileDirectories>d__10::<>1__state
0x51b7  br.s     loc_51CA
0x51b9  ldc.i4.3
0x51ba  ldstr    aNotProcessingL// "Not processing log for user with remote"...
0x51bf  ldc.i4.0
0x51c0  newarr   [mscorlib]System.Object
0x51c5  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x51ca  ldarg.0
0x51cb  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string> <GetUserProfileDirectories>d__10::<>7__wrap1
0x51d0  call     instance bool valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>::MoveNext()
0x51d5  brtrue   loc_5145
0x51da  ldarg.0
0x51db  call     instance void <GetUserProfileDirectories>d__10::<>m__Finally1()
0x51e0  br.s     loc_51EA
0x51e2  ldarg.0
0x51e3  call     instance void <GetUserProfileDirectories>d__10::<>m__Finally1()
0x51e8  leave.s  loc_5201
0x51ea  ldarg.0
0x51eb  ldflda   valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string> <GetUserProfileDirectories>d__10::<>7__wrap1
0x51f0  initobj  valuetype [mscorlib]System.Collections.Generic.List`1/Enumerator<string>
0x51f6  ldc.i4.0
0x51f7  stloc.0
0x51f8  leave.s  loc_5201
0x51fa  ldarg.0
0x51fb  call     instance void <GetUserProfileDirectories>d__10::System.IDisposable.Dispose()
0x5200  endfinally
0x5201  ldloc.0
0x5202  ret
```
