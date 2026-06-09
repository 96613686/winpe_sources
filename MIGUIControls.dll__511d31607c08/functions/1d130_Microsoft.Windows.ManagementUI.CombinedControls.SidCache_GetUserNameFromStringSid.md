# Microsoft.Windows.ManagementUI.CombinedControls.SidCache::GetUserNameFromStringSid

- ea: `0x1d130`
- end: `0x1d255`
- name: `Microsoft.Windows.ManagementUI.CombinedControls.SidCache::GetUserNameFromStringSid`
- size: `293`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1d0c0`

## callees

- `0x1cdb0`
- `0x1cef0`
- `0x1d010`
- `0x1d040`
- `0x1d130`
- `0x1d3e0`
- `0x9fef0`

## string_xrefs

- `0x1d19a`: `SidCache`
- `0x1d204`: `SidCache`
- `0x1d19f`: `FormattedUserNameFromStringSid`
- `0x1d209`: `FormattedUserNameFromStringSid`

## pseudocode

```c

```

## disassembly

```asm
0x1d130  ldsfld   string [mscorlib]System.String::Empty
0x1d135  stloc.0
0x1d136  ldarg.1
0x1d137  brtrue.s loc_1D140
0x1d139  ldsfld   string [mscorlib]System.String::Empty
0x1d13e  starg.s  1
0x1d140  ldarg.0
0x1d141  stloc.1
0x1d142  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nameToSid
0x1d147  stloc.2
0x1d148  ldc.i4.0
0x1d149  stloc.3
0x1d14a  ldloc.2
0x1d14b  ldloca.s 3
0x1d14d  call     void [mscorlib]System.Threading.Monitor::Enter(object, bool&)
0x1d152  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nameToSid
0x1d157  ldloc.1
0x1d158  ldloca.s 0
0x1d15a  callvirt instance bool class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::TryGetValue(var<u1>, !!T0)
0x1d15f  brfalse.s loc_1D172
0x1d161  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nHits
0x1d166  ldc.i4.1
0x1d167  add
0x1d168  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nHits
0x1d16d  leave    loc_1D253
0x1d172  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nMisses
0x1d177  ldc.i4.1
0x1d178  add
0x1d179  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nMisses
0x1d17e  ldarg.1
0x1d17f  call     bool Microsoft.Windows.ManagementUI.CombinedControls.SidCache::CheckRpcLookupFailed(string computerName)
0x1d184  brtrue.s loc_1D1B3
0x1d186  ldarg.1
0x1d187  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d18c  brtrue.s loc_1D19A
0x1d18e  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nRemoteLookups
0x1d193  ldc.i4.1
0x1d194  add
0x1d195  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nRemoteLookups
0x1d19a  ldstr    aSidcache// "SidCache"
0x1d19f  ldstr    aFormattedusern// "FormattedUserNameFromStringSid"
0x1d1a4  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::StartMethod(string className, string methodName)
0x1d1a9  ldarg.0
0x1d1aa  ldarg.1
0x1d1ab  call     string SIDLookup::FormattedUserNameFromStringSid(string incomingSid, string computerName)
0x1d1b0  stloc.0
0x1d1b1  br.s     loc_1D1BF
0x1d1b3  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_rpcAvoidedLookups
0x1d1b8  ldc.i4.1
0x1d1b9  add
0x1d1ba  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_rpcAvoidedLookups
0x1d1bf  leave.s  loc_1D214
0x1d1c1  pop
0x1d1c2  ldarg.1
0x1d1c3  call     void Microsoft.Windows.ManagementUI.CombinedControls.SidCache::SetRpcLookupFailed(string computerName)
0x1d1c8  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nFailedLookups
0x1d1cd  ldc.i4.1
0x1d1ce  add
0x1d1cf  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nFailedLookups
0x1d1d4  leave.s  loc_1D214
0x1d1d6  callvirt instance int32 [System]System.ComponentModel.Win32Exception::get_NativeErrorCode()
0x1d1db  ldc.i4   0x534
0x1d1e0  bne.un.s loc_1D1F0
0x1d1e2  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nFailedLookups
0x1d1e7  ldc.i4.1
0x1d1e8  add
0x1d1e9  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nFailedLookups
0x1d1ee  br.s     loc_1D202
0x1d1f0  ldarg.1
0x1d1f1  call     void Microsoft.Windows.ManagementUI.CombinedControls.SidCache::SetRpcLookupFailed(string computerName)
0x1d1f6  ldsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nFailedLookups
0x1d1fb  ldc.i4.1
0x1d1fc  add
0x1d1fd  stsfld   int32 Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nFailedLookups
0x1d202  leave.s  loc_1D214
0x1d204  ldstr    aSidcache// "SidCache"
0x1d209  ldstr    aFormattedusern// "FormattedUserNameFromStringSid"
0x1d20e  call     void Microsoft.Windows.ManagementUI.CombinedControls.TimeTrace::EndMethod(string className, string methodName)
0x1d213  endfinally
0x1d214  ldloc.0
0x1d215  call     bool [mscorlib]System.String::IsNullOrEmpty(string)
0x1d21a  brfalse.s loc_1D220
0x1d21c  ldarg.0
0x1d21d  stloc.0
0x1d21e  leave.s  loc_1D253
0x1d220  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nameToSid
0x1d225  callvirt instance class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::get_Keys()
0x1d22a  callvirt instance int32 class [mscorlib]System.Collections.Generic.Dictionary`2/KeyCollection<string, string>::get_Count()
0x1d22f  ldc.i4   0x400
0x1d234  blt.s    loc_1D23B
0x1d236  call     void Microsoft.Windows.ManagementUI.CombinedControls.SidCache::ClearCache()
0x1d23b  ldsfld   class [mscorlib]System.Collections.Generic.Dictionary`2<string, string> Microsoft.Windows.ManagementUI.CombinedControls.SidCache::_nameToSid
0x1d240  ldloc.1
0x1d241  ldloc.0
0x1d242  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, string>::Add(var<u1>, !!T0)
0x1d247  leave.s  loc_1D253
0x1d249  ldloc.3
0x1d24a  brfalse.s loc_1D252
0x1d24c  ldloc.2
0x1d24d  call     void [mscorlib]System.Threading.Monitor::Exit(object)
0x1d252  endfinally
0x1d253  ldloc.0
0x1d254  ret
```
