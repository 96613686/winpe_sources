# Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::Initialize

- ea: `0x15330`
- end: `0x1543f`
- name: `Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::Initialize`
- size: `271`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x152e0`

## callees

- `0x15210`
- `0x15230`
- `0x15250`
- `0x15270`
- `0x15290`
- `0x152b0`
- `0x15330`

## string_xrefs

- `0x15350`: `[Marketplace] Getting token from STS and setting Thread Identity`
- `0x15398`: `[S2S] Getting token from STS and setting Thread Identity`
- `0x153e0`: `[Loopback] Getting token from STS and setting Thread Identity`
- `0x15428`: `[NativeFlow] Getting token from STS and setting Thread Identity`
- `0x15434`: `tokenType`

## pseudocode

```c

```

## disassembly

```asm
0x15330  ldarg.1
0x15331  stloc.0
0x15332  ldloc.0
0x15333  ldc.i4.1
0x15334  sub
0x15335  switch   loc_1534F, loc_15397, loc_153DF, loc_15427
0x1534a  br       loc_15433
0x1534f  ldarg.0
0x15350  ldstr    aMarketplaceGet// "[Marketplace] Getting token from STS an"...
0x15355  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeName(string value)
0x1535a  ldarg.0
0x1535b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold::get_Local()
0x15360  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold::get_MarketplaceIncomingThreshold()
0x15365  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeThreshold(unsigned int32 value)
0x1536a  ldarg.0
0x1536b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_MarketplaceIncomingTokensRPS()
0x15370  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_RequestsPerSecondPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x15375  ldarg.0
0x15376  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_MarketplaceIncomingTokensAverageLatency()
0x1537b  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_LatencyPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x15380  ldarg.0
0x15381  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_MarketplaceIncomingTokensHitCount()
0x15386  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_RequestsPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x1538b  ldarg.0
0x1538c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_MarketplaceIncomingTokensExceedingHitCount()
0x15391  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_ExceedingRequestsPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x15396  ret
0x15397  ldarg.0
0x15398  ldstr    aS2sGettingToke// "[S2S] Getting token from STS and settin"...
0x1539d  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeName(string value)
0x153a2  ldarg.0
0x153a3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold::get_Local()
0x153a8  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold::get_ServerToServerIncomingThreshold()
0x153ad  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeThreshold(unsigned int32 value)
0x153b2  ldarg.0
0x153b3  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_S2SIncomingTokensRPS()
0x153b8  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_RequestsPerSecondPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x153bd  ldarg.0
0x153be  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_S2SIncomingTokensAverageLatency()
0x153c3  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_LatencyPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x153c8  ldarg.0
0x153c9  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_S2SIncomingTokensHitCount()
0x153ce  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_RequestsPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x153d3  ldarg.0
0x153d4  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_S2SIncomingTokensExceedingHitCount()
0x153d9  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_ExceedingRequestsPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x153de  ret
0x153df  ldarg.0
0x153e0  ldstr    aLoopbackGettin// "[Loopback] Getting token from STS and s"...
0x153e5  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeName(string value)
0x153ea  ldarg.0
0x153eb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold::get_Local()
0x153f0  callvirt instance unsigned int32 [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPMonitoredScopeThreshold::get_LoopbackIncomingThreshold()
0x153f5  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeThreshold(unsigned int32 value)
0x153fa  ldarg.0
0x153fb  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_LoopbackIncomingTokensRPS()
0x15400  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_RequestsPerSecondPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x15405  ldarg.0
0x15406  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_LoopbackIncomingTokensAverageLatency()
0x1540b  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_LatencyPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x15410  ldarg.0
0x15411  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_LoopbackIncomingTokensHitCount()
0x15416  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_RequestsPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x1541b  ldarg.0
0x1541c  call     class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounterSet::get_LoopbackIncomingTokensExceedingHitCount()
0x15421  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_ExceedingRequestsPerformanceCounter(class [Microsoft.SharePoint]Microsoft.SharePoint.IdentityModel.SPOAuthPerformanceCounter value)
0x15426  ret
0x15427  ldarg.0
0x15428  ldstr    aNativeflowGett// "[NativeFlow] Getting token from STS and"...
0x1542d  call     instance void Microsoft.SharePoint.IdentityModel.SPIncomingTokenPerformanceScope::set_MonitoredScopeName(string value)
0x15432  ret
0x15433  ldnull
0x15434  ldstr    aTokentype// "tokenType"
0x15439  newobj   instance void [mscorlib]System.ArgumentException::.ctor(string, string)
0x1543e  throw
```
