# Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::Init

- ea: `0x26780`
- end: `0x26850`
- name: `Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::Init`
- size: `208`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x26030`
- `0x26290`
- `0x26780`

## string_xrefs

- `0x2679f`: `SPDistributedSecurityTokenCache is not in use.`
- `0x267c1`: `Trying to initialize SPDistributedSecurityTokenCache.`
- `0x267cb`: `Distributed Logon Token Cache`
- `0x267fc`: `Successfully to initialized SPDistributedSecurityTokenCache.`
- `0x26832`: `Token Cache: Failed to initialize SPDistributedSecurityTokenCache  Exception: '{0}'.`

## pseudocode

```c

```

## disassembly

```asm
0x26780  ldsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x26785  brfalse.s loc_2678C
0x26787  leave    loc_2684F
0x2678c  call     bool Microsoft.SharePoint.IdentityModel.SPTokenCache::get_UseDistributedCache()
0x26791  brtrue.s loc_267AE
0x26793  ldc.i4   0x71D093
0x26798  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x2679d  ldc.i4.s 0x32
0x2679f  ldstr    aSpdistributeds_1// "SPDistributedSecurityTokenCache is not "...
0x267a4  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x267a9  leave    loc_2684F
0x267ae  ldsfld   class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::_distributedTokenCache
0x267b3  brtrue.s loc_267F0
0x267b5  ldc.i4   0x211784
0x267ba  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x267bf  ldc.i4.s 0x64
0x267c1  ldstr    aTryingToInitia// "Trying to initialize SPDistributedSecur"...
0x267c6  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x267cb  ldstr    aDistributedLog// "Distributed Logon Token Cache"
0x267d0  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x267d5  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_WindowsTokenLifetime()
0x267da  ldc.i4.4
0x267db  ldc.i4.1
0x267dc  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_Local()
0x267e1  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.SharePoint]Microsoft.SharePoint.Administration.Claims.SPSecurityTokenServiceManager::get_LogonTokenCacheExpirationWindow()
0x267e6  newobj   instance void Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache::.ctor(string name, valuetype [mscorlib]System.TimeSpan timeToLive, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheContainerType containerType, bool encrptyData, valuetype [mscorlib]System.TimeSpan minimumTokenExpirationWindow)
0x267eb  stsfld   class Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCache Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::_distributedTokenCache
0x267f0  ldc.i4   0x211785
0x267f5  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x267fa  ldc.i4.s 0x64
0x267fc  ldstr    aSuccessfullyTo// "Successfully to initialized SPDistribut"...
0x26801  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string)
0x26806  ldc.i4.1
0x26807  stsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x2680c  leave.s  loc_2684F
0x2680e  stloc.0
0x2680f  ldc.i4.0
0x26810  stsfld   bool Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::IsInitialized
0x26815  ldsfld   class [mscorlib]System.Threading.Timer Microsoft.SharePoint.IdentityModel.SPDistributedSecurityTokenCacheInitializer::t
0x2681a  ldc.i4   0x3E8
0x2681f  ldc.i4.m1
0x26820  callvirt instance bool [mscorlib]System.Threading.Timer::Change(int32, int32)
0x26825  pop
0x26826  ldc.i4   0x211786
0x2682b  call     class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x26830  ldc.i4.s 0xF
0x26832  ldstr    aTokenCacheFail_15// "Token Cache: Failed to initialize SPDis"...
0x26837  ldc.i4.1
0x26838  newarr   [mscorlib]System.Object
0x2683d  stloc.1
0x2683e  ldloc.1
0x2683f  ldc.i4.0
0x26840  ldloc.0
0x26841  callvirt instance string [mscorlib]System.Object::ToString()
0x26846  stelem.ref
0x26847  ldloc.1
0x26848  call     void [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32, class [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSCatBase, valuetype [Microsoft.SharePoint]Microsoft.SharePoint.Diagnostics.ULSTraceLevel, string, object[])
0x2684d  leave.s  loc_2684F
0x2684f  ret
```
