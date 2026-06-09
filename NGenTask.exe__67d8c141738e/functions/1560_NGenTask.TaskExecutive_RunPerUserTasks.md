# NGenTask.TaskExecutive::RunPerUserTasks

- ea: `0x1560`
- end: `0x19cc`
- name: `NGenTask.TaskExecutive::RunPerUserTasks`
- size: `1132`
- prototype: ``
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x310`

## callees

- `0x1560`
- `0x2270`
- `0x2c30`
- `0x3070`
- `0x30c0`
- `0x30f0`
- `0x3150`
- `0x3160`
- `0x3170`
- `0x3180`
- `0x3190`
- `0x31b0`
- `0x3230`
- `0x3240`
- `0x3250`
- `0x3260`
- `0x3270`
- `0x40b0`

## string_xrefs

- `0x1561`: `Looking for active user sessions, and run per-user tasks`
- `0x1589`: `Unable to enumerate user sessions (error {0}), will not run per-user tasks`
- `0x1649`: `Unable to retrieve user token for session {0} (error {1})`
- `0x16e9`: `Unable to create event object (error {0})`
- `0x17e5`: `Unable to create Safer level (error {0})`
- `0x1823`: `Unable to compute Safer token from level (error {0})`
- `0x1873`: `Creating child NGen Task, command line: {0}`
- `0x18bb`: `Unable to crete per-user NGen Task for session {0} (error {1})`
- `0x18f2`: `Created child NGen Task, process ID {0}`
- `0x19bb`: `Finished running all per-user tasks`

## pseudocode

```c

```

## disassembly

```asm
0x1560  ldc.i4.3
0x1561  ldstr    aLookingForActi// "Looking for active user sessions, and r"...
0x1566  ldc.i4.0
0x1567  newarr   [mscorlib]System.Object
0x156c  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1571  ldc.i4.0
0x1572  conv.u
0x1573  stloc.0
0x1574  ldc.i4.0
0x1575  stloc.1
0x1576  ldsfld   native int NGenTask.Win32Native::WTS_CURRENT_SERVER_HANDLE
0x157b  ldc.i4.0
0x157c  ldc.i4.1
0x157d  ldloca.s 0
0x157f  ldloca.s 1
0x1581  call     bool NGenTask.Win32Native::WTSEnumerateSessions(native int hServer, unsigned int32 reserved, unsigned int32 version, [out] valuetype WTS_SESSION_INFO*& ppSessionInfo, [out] unsigned int32& count)
0x1586  brtrue.s loc_15A7
0x1588  ldc.i4.0
0x1589  ldstr    aUnableToEnumer// "Unable to enumerate user sessions (erro"...
0x158e  ldc.i4.1
0x158f  newarr   [mscorlib]System.Object
0x1594  dup
0x1595  ldc.i4.0
0x1596  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x159b  box      [mscorlib]System.Int32
0x15a0  stelem.ref
0x15a1  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x15a6  ret
0x15a7  nop
0x15a8  ldc.i4.0
0x15a9  stloc.2
0x15aa  br       loc_19AA
0x15af  ldarg.0
0x15b0  volatile.
0x15b2  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x15b7  brfalse.s loc_15BE
0x15b9  leave    loc_19CB
0x15be  ldloc.0
0x15bf  ldloc.2
0x15c0  conv.u8
0x15c1  sizeof   WTS_SESSION_INFO
0x15c7  conv.i8
0x15c8  mul
0x15c9  conv.i
0x15ca  add
0x15cb  ldfld    valuetype WTS_CONNECTSTATE_CLASS WTS_SESSION_INFO::State
0x15d0  brfalse.s loc_15EA
0x15d2  ldloc.0
0x15d3  ldloc.2
0x15d4  conv.u8
0x15d5  sizeof   WTS_SESSION_INFO
0x15db  conv.i8
0x15dc  mul
0x15dd  conv.i
0x15de  add
0x15df  ldfld    valuetype WTS_CONNECTSTATE_CLASS WTS_SESSION_INFO::State
0x15e4  ldc.i4.4
0x15e5  bne.un   loc_19A6
0x15ea  ldloc.0
0x15eb  ldloc.2
0x15ec  conv.u8
0x15ed  sizeof   WTS_SESSION_INFO
0x15f3  conv.i8
0x15f4  mul
0x15f5  conv.i
0x15f6  add
0x15f7  ldfld    unsigned int32 WTS_SESSION_INFO::SessionId
0x15fc  stloc.3
0x15fd  ldloc.3
0x15fe  brfalse  loc_19A6
0x1603  ldc.i4.3
0x1604  ldstr    aSession0Is1// "Session {0} is {1}"
0x1609  ldc.i4.2
0x160a  newarr   [mscorlib]System.Object
0x160f  dup
0x1610  ldc.i4.0
0x1611  ldloc.3
0x1612  box      [mscorlib]System.UInt32
0x1617  stelem.ref
0x1618  dup
0x1619  ldc.i4.1
0x161a  ldloc.0
0x161b  ldloc.2
0x161c  conv.u8
0x161d  sizeof   WTS_SESSION_INFO
0x1623  conv.i8
0x1624  mul
0x1625  conv.i
0x1626  add
0x1627  ldfld    valuetype WTS_CONNECTSTATE_CLASS WTS_SESSION_INFO::State
0x162c  box      WTS_CONNECTSTATE_CLASS
0x1631  stelem.ref
0x1632  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1637  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x163c  stloc.s  4
0x163e  ldloc.3
0x163f  ldloca.s 4
0x1641  call     bool NGenTask.Win32Native::WTSQueryUserToken(unsigned int32 SessionId, [out] native int& hToken)
0x1646  brtrue.s loc_1674
0x1648  ldc.i4.0
0x1649  ldstr    aUnableToRetrie// "Unable to retrieve user token for sessi"...
0x164e  ldc.i4.2
0x164f  newarr   [mscorlib]System.Object
0x1654  dup
0x1655  ldc.i4.0
0x1656  ldloc.3
0x1657  box      [mscorlib]System.UInt32
0x165c  stelem.ref
0x165d  dup
0x165e  ldc.i4.1
0x165f  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1664  box      [mscorlib]System.Int32
0x1669  stelem.ref
0x166a  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x166f  br       loc_19A6
0x1674  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1679  stloc.s  5
0x167b  ldarg.0
0x167c  ldfld    object NGenTask.TaskExecutive::m_stopLock
0x1681  stloc.s  6
0x1683  ldc.i4.0
0x1684  stloc.s  7
0x1686  ldloc.s  6
0x1688  ldloca.s 7
0x168a  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x168f  ldarg.0
0x1690  volatile.
0x1692  ldfld    modreq([mscorlib]System.Runtime.CompilerServices.IsVolatile) bool NGenTask.TaskExecutive::m_stopRequested
0x1697  brfalse.s loc_169E
0x1699  leave    loc_19CB
0x169e  ldarg.0
0x169f  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x16a4  brtrue.s loc_16B2
0x16a6  ldarg.0
0x16a7  ldc.i4.0
0x16a8  newobj   instance void [mscorlib]System.Threading.ManualResetEvent::.ctor(bool)
0x16ad  stfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x16b2  newobj   instance void SECURITY_ATTRIBUTES::.ctor()
0x16b7  stloc.s  8
0x16b9  ldloc.s  8
0x16bb  ldc.i4.1
0x16bc  stfld    int32 SECURITY_ATTRIBUTES::bInheritHandle
0x16c1  ldarg.0
0x16c2  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x16c7  ldloc.s  8
0x16c9  ldc.i4.1
0x16ca  ldc.i4.0
0x16cb  ldnull
0x16cc  call     class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle NGenTask.Win32Native::CreateEvent(class SECURITY_ATTRIBUTES lpSecurityAttributes, bool isManualReset, bool initialState, string name)
0x16d1  callvirt instance void [mscorlib]System.Threading.WaitHandle::set_SafeWaitHandle(class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle)
0x16d6  ldarg.0
0x16d7  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x16dc  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle [mscorlib]System.Threading.WaitHandle::get_SafeWaitHandle()
0x16e1  callvirt instance bool [mscorlib]System.Runtime.InteropServices.SafeHandle::get_IsInvalid()
0x16e6  brfalse.s loc_170B
0x16e8  ldc.i4.0
0x16e9  ldstr    aUnableToCreate// "Unable to create event object (error {0"...
0x16ee  ldc.i4.1
0x16ef  newarr   [mscorlib]System.Object
0x16f4  dup
0x16f5  ldc.i4.0
0x16f6  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x16fb  box      [mscorlib]System.Int32
0x1700  stelem.ref
0x1701  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1706  leave    loc_19BA
0x170b  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x1710  stloc.s  9
0x1712  ldloc.s  9
0x1714  ldc.i4.s 0x22
0x1716  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x171b  call     class [mscorlib]System.Reflection.Assembly [mscorlib]System.Reflection.Assembly::GetExecutingAssembly()
0x1720  callvirt instance string [mscorlib]System.Reflection.Assembly::get_Location()
0x1725  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x172a  ldc.i4.s 0x22
0x172c  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(char)
0x1731  pop
0x1732  ldloc.s  9
0x1734  ldarg.1
0x1735  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x173a  pop
0x173b  ldloc.s  9
0x173d  ldstr    aStopevent0// " /StopEvent:{0}"
0x1742  ldarg.0
0x1743  ldfld    class [mscorlib]System.Threading.ManualResetEvent NGenTask.TaskExecutive::m_childStopEvent
0x1748  callvirt instance class [mscorlib]Microsoft.Win32.SafeHandles.SafeWaitHandle [mscorlib]System.Threading.WaitHandle::get_SafeWaitHandle()
0x174d  callvirt instance native int [mscorlib]System.Runtime.InteropServices.SafeHandle::DangerousGetHandle()
0x1752  box      [mscorlib]System.IntPtr
0x1757  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::AppendFormat(string, object)
0x175c  pop
0x175d  ldloca.s 0xA
0x175f  initobj  STARTUPINFO
0x1765  ldloca.s 0xA
0x1767  ldtoken  STARTUPINFO
0x176c  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x1771  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::SizeOf(class [mscorlib]System.Type)
0x1776  stfld    int32 STARTUPINFO::cb
0x177b  ldloca.s 0xA
0x177d  ldstr    aWinsta0Default// "WinSta0\\Default"
0x1782  stfld    string STARTUPINFO::lpDesktop
0x1787  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x178c  stloc.s  0xC
0x178e  ldloca.s 0xC
0x1790  ldloc.s  4
0x1792  ldc.i4.0
0x1793  call     bool NGenTask.Win32Native::CreateEnvironmentBlock([out] native int& lpEnvironment, native int hToken, bool bInherit)
0x1798  brtrue.s loc_17BD
0x179a  ldc.i4.0
0x179b  ldstr    aUnableToCreteE// "Unable to crete environment block (erro"...
0x17a0  ldc.i4.1
0x17a1  newarr   [mscorlib]System.Object
0x17a6  dup
0x17a7  ldc.i4.0
0x17a8  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x17ad  box      [mscorlib]System.Int32
0x17b2  stelem.ref
0x17b3  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x17b8  leave    loc_19BA
0x17bd  ldarg.0
0x17be  call     instance bool NGenTask.TaskExecutive::IsTaskUserImpersonationDisabled()
0x17c3  brtrue   loc_1871
0x17c8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x17cd  stloc.s  0xD
0x17cf  ldc.i4.2
0x17d0  ldc.i4   0x20000
0x17d5  ldc.i4.1
0x17d6  ldloca.s 0xD
0x17d8  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x17dd  call     bool NGenTask.Win32Native::SaferCreateLevel([hasfieldmarshal] valuetype SaferScopeEnum, valuetype SaferLevelEnum dwScopeId, valuetype SaferOpenFlags dwLevelId, native int& OpenFlags, [out] native int pLevelHandle)
0x17e2  brtrue.s loc_1807
0x17e4  ldc.i4.0
0x17e5  ldstr    aUnableToCreate_0// "Unable to create Safer level (error {0}"...
0x17ea  ldc.i4.1
0x17eb  newarr   [mscorlib]System.Object
0x17f0  dup
0x17f1  ldc.i4.0
0x17f2  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x17f7  box      [mscorlib]System.Int32
0x17fc  stelem.ref
0x17fd  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1802  leave    loc_19BA
0x1807  ldloc.s  0xD
0x1809  ldloc.s  4
0x180b  ldloca.s 5
0x180d  ldc.i4.0
0x180e  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1813  call     bool NGenTask.Win32Native::SaferComputeTokenFromLevel([hasfieldmarshal] native int, native int LevelHandle, native int& InAccessToken, [out] int32 OutAccessToken, native int dwFlags)
0x1818  brtrue.s loc_1845
0x181a  ldloc.s  0xD
0x181c  call     bool NGenTask.Win32Native::SaferCloseLevel([hasfieldmarshal] native int)
0x1821  pop
0x1822  ldc.i4.0
0x1823  ldstr    aUnableToComput// "Unable to compute Safer token from leve"...
0x1828  ldc.i4.1
0x1829  newarr   [mscorlib]System.Object
0x182e  dup
0x182f  ldc.i4.0
0x1830  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1835  box      [mscorlib]System.Int32
0x183a  stelem.ref
0x183b  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x1840  leave    loc_19BA
0x1845  ldloc.s  0xD
0x1847  call     bool NGenTask.Win32Native::SaferCloseLevel([hasfieldmarshal] native int)
0x184c  brtrue.s loc_1871
0x184e  ldc.i4.0
0x184f  ldstr    aUnableToCloseS// "Unable to close Safer level (error {0})"
0x1854  ldc.i4.1
0x1855  newarr   [mscorlib]System.Object
0x185a  dup
0x185b  ldc.i4.0
0x185c  call     int32 [mscorlib]System.Runtime.InteropServices.Marshal::GetLastWin32Error()
0x1861  box      [mscorlib]System.Int32
0x1866  stelem.ref
0x1867  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x186c  leave    loc_19BA
0x1871  nop
0x1872  ldc.i4.3
0x1873  ldstr    aCreatingChildN// "Creating child NGen Task, command line:"...
0x1878  ldc.i4.1
0x1879  newarr   [mscorlib]System.Object
0x187e  dup
0x187f  ldc.i4.0
0x1880  ldloc.s  9
0x1882  callvirt instance string [mscorlib]System.Object::ToString()
0x1887  stelem.ref
0x1888  call     void NGenTask.Logger::Log(valuetype LogLevel level, string format, object[] args)
0x188d  ldloc.s  5
0x188f  ldsfld   native int [mscorlib]System.IntPtr::Zero
0x1894  call     bool [mscorlib]System.IntPtr::op_Inequality(native int, native int)
0x1899  brtrue.s loc_189F
0x189b  ldloc.s  4
0x189d  br.s     loc_18A1
0x189f  ldloc.s  5
0x18a1  ldnull
0x18a2  ldloc.s  9
0x18a4  ldnull
0x18a5  ldnull
0x18a6  ldc.i4.1
0x18a7  ldc.i4   0x8000400
  ... truncated ...
```
