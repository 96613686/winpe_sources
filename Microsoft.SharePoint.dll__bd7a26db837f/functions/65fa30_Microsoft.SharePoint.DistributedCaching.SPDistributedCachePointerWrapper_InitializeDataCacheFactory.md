# Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::InitializeDataCacheFactory

- ea: `0x65fa30`
- end: `0x660059`
- name: `Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::InitializeDataCacheFactory`
- size: `1577`
- prototype: ``
- caller_count: `1`
- callee_count: `32`
- tags: `registry_config, broker_com_uri`

## callers

- `0x65f9f0`

## callees

- `0x1c8540`
- `0x1c89b0`
- `0x29d0f0`
- `0x2ebad0`
- `0x65fa30`
- `0x660190`
- `0x6601b0`
- `0x6601d0`
- `0x6601f0`
- `0x660210`
- `0x660230`
- `0x660250`
- `0x660270`
- `0x660290`
- `0x660af0`
- `0x660e30`
- `0x661060`
- `0x661180`
- `0x661190`
- `0x6616b0`
- `0x661720`
- `0x6617b0`
- `0x661bc0`
- `0x661be0`
- `0x661c80`
- `0x663dc0`
- `0x665750`
- `0x93dab0`
- `0x93dae0`
- `0x945c80`
- `0x957530`
- `0x957930`

## string_xrefs

- `0x65fa51`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - SPDistributedCacheClusterInfoManager is null.`
- `0x65fa5b`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - SPDistributedCacheClusterInfoManager is null.`
- `0x65fa87`: `SPDistributedCacheClientFactory::InitializeDataCacheFactory - SPDistributedCacheClusterInfo is null.`
- `0x65fa91`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - SPDistributedCacheClusterInfo is null.`
- `0x65facc`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - No cache hosts are present in the farm.`
- `0x65fad6`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - No cache hosts present in the farm.`
- `0x65fb0a`: `cache host Name: '{0}' Running status '{1}'`
- `0x65fb68`: `DistributedCacheClient is currently using cache host '{0}'`
- `0x65fbb6`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - No cache hosts are present or running in the farm.`
- `0x65fbc0`: `SPDistributedCachePointerWrapper::InitializeDataCacheFactory - No cache hosts are present or running in the farm.`
- `0x65fc29`: `DistributedCacheClient ChannelOpenTimeout '{0}'.`
- `0x65fc6b`: `DistributedCacheClient RequestTimeout '{0}'.`
- `0x65fcad`: `DistributedCacheClient MaxConnectionsToServer '{0}'.`
- `0x65fd67`: `DistributedCacheClient TransportProperties- ChannelInitializationTimeout '{0}', ConnectionBufferSize '{1}', \n                                MaxBufferPoolSize '{2}', MaxBufferSize '{3}', MaxOutputDelay '{4}',ReceiveTimeout '{5}'.`
- `0x65fe05`: `IsDataCacheSecurityEnabled '{0}'.`
- `0x65fe2d`: `CacheConfig_{0:N}.xml`
- `0x65fe76`: `securityProperties`
- `0x65feab`: `securityProperties`
- `0x65ff49`: `Unexpected Exception in getting cache cluster security config - Exception '{0}'.`
- `0x660028`: `Unexpected Exception in SPDistributedCachePointerWrapper::InitializeDataCacheFactory for usage '{0}' - Exception '{1}'.`

## pseudocode

```c

```

## disassembly

```asm
0x65fa30  call     class Microsoft.SharePoint.Utilities.SecurityContext Microsoft.SharePoint.Utilities.SecurityContext::RevertToSelf()
0x65fa35  stloc.0
0x65fa36  call     class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterInfoManager Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterInfoManager::get_Local()
0x65fa3b  stloc.1
0x65fa3c  ldloc.1
0x65fa3d  ldnull
0x65fa3e  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x65fa43  brfalse.s loc_65FA66
0x65fa45  ldc.i4   0x1DC78E
0x65fa4a  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fa4f  ldc.i4.s 0xA
0x65fa51  ldstr    aSpdistributedc// "SPDistributedCachePointerWrapper::Initi"...
0x65fa56  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x65fa5b  ldstr    aSpdistributedc// "SPDistributedCachePointerWrapper::Initi"...
0x65fa60  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65fa65  throw
0x65fa66  ldloc.1
0x65fa67  call     string Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterConfigHelper::get_SPDistributedCacheClusterName()
0x65fa6c  callvirt instance class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterInfo Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterInfoManager::GetSPDistributedCacheClusterInfo(string clusterName)
0x65fa71  stloc.2
0x65fa72  ldloc.2
0x65fa73  ldnull
0x65fa74  call     bool Microsoft.SharePoint.Administration.SPPersistedObject::op_Equality(class Microsoft.SharePoint.Administration.SPPersistedObject a, class Microsoft.SharePoint.Administration.SPPersistedObject b)
0x65fa79  brfalse.s loc_65FA9C
0x65fa7b  ldc.i4   0x1DC78F
0x65fa80  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fa85  ldc.i4.s 0xA
0x65fa87  ldstr    aSpdistributedc_7// "SPDistributedCacheClientFactory::Initia"...
0x65fa8c  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x65fa91  ldstr    aSpdistributedc_8// "SPDistributedCachePointerWrapper::Initi"...
0x65fa96  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65fa9b  throw
0x65fa9c  ldarg.0
0x65fa9d  ldloc.1
0x65fa9e  ldarg.0
0x65fa9f  ldfld    valuetype Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheContainerType Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_containerType
0x65faa4  callvirt instance class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterInfoManager::GetSPDistributedCacheClientConfigurationSettings(valuetype Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheContainerType type)
0x65faa9  stfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65faae  ldloc.2
0x65faaf  callvirt instance class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfoCollection Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClusterInfo::get_CacheHostsInfoCollection()
0x65fab4  stloc.3
0x65fab5  ldloc.3
0x65fab6  brfalse.s loc_65FAC0
0x65fab8  ldloc.3
0x65fab9  callvirt instance int32 class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo>::get_Count()
0x65fabe  brtrue.s loc_65FAE1
0x65fac0  ldc.i4   0x1DC790
0x65fac5  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65faca  ldc.i4.s 0xA
0x65facc  ldstr    aSpdistributedc_9// "SPDistributedCachePointerWrapper::Initi"...
0x65fad1  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x65fad6  ldstr    aSpdistributedc_10// "SPDistributedCachePointerWrapper::Initi"...
0x65fadb  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65fae0  throw
0x65fae1  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheServerEndpoint>::.ctor()
0x65fae6  stloc.s  4
0x65fae8  ldloc.3
0x65fae9  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<var<u1>> class Microsoft.SharePoint.Administration.SPPersistedObjectCollection`1<class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo>::GetEnumerator()
0x65faee  stloc.s  0x10
0x65faf0  br       loc_65FB87
0x65faf5  ldloc.s  0x10
0x65faf7  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo>::get_Current()
0x65fafc  stloc.s  5
0x65fafe  ldc.i4   0x1DC791
0x65fb03  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fb08  ldc.i4.s 0x64
0x65fb0a  ldstr    aCacheHostName0// "cache host Name: '{0}' Running status '"...
0x65fb0f  ldc.i4.2
0x65fb10  newarr   [mscorlib]System.Object
0x65fb15  stloc.s  0x11
0x65fb17  ldloc.s  0x11
0x65fb19  ldc.i4.0
0x65fb1a  ldloc.s  5
0x65fb1c  callvirt instance string Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo::get_HostName()
0x65fb21  stelem.ref
0x65fb22  ldloc.s  0x11
0x65fb24  ldc.i4.1
0x65fb25  ldloc.s  5
0x65fb27  callvirt instance valuetype Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostStatus Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo::get_CacheHostStatus()
0x65fb2c  box      Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostStatus
0x65fb31  stelem.ref
0x65fb32  ldloc.s  0x11
0x65fb34  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x65fb39  ldloc.s  5
0x65fb3b  callvirt instance valuetype Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostStatus Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo::get_CacheHostStatus()
0x65fb40  brtrue.s loc_65FB87
0x65fb42  ldloc.s  4
0x65fb44  ldloc.s  5
0x65fb46  callvirt instance string Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo::get_HostName()
0x65fb4b  ldloc.s  5
0x65fb4d  callvirt instance int32 Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo::get_CachePort()
0x65fb52  newobj   instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheServerEndpoint::.ctor(string, int32)
0x65fb57  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheServerEndpoint>::Add(var<u1>)
0x65fb5c  ldc.i4   0x875C2
0x65fb61  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fb66  ldc.i4.s 0x64
0x65fb68  ldstr    aDistributedcac_11// "DistributedCacheClient is currently usi"...
0x65fb6d  ldc.i4.1
0x65fb6e  newarr   [mscorlib]System.Object
0x65fb73  stloc.s  0x12
0x65fb75  ldloc.s  0x12
0x65fb77  ldc.i4.0
0x65fb78  ldloc.s  5
0x65fb7a  callvirt instance string Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheHostInfo::get_HostName()
0x65fb7f  stelem.ref
0x65fb80  ldloc.s  0x12
0x65fb82  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x65fb87  ldloc.s  0x10
0x65fb89  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0x65fb8e  brtrue   loc_65FAF5
0x65fb93  leave.s  loc_65FBA1
0x65fb95  ldloc.s  0x10
0x65fb97  brfalse.s loc_65FBA0
0x65fb99  ldloc.s  0x10
0x65fb9b  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0x65fba0  endfinally
0x65fba1  ldloc.s  4
0x65fba3  callvirt instance int32 class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheServerEndpoint>::get_Count()
0x65fba8  brtrue.s loc_65FBCB
0x65fbaa  ldc.i4   0x78A090
0x65fbaf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fbb4  ldc.i4.s 0xA
0x65fbb6  ldstr    aSpdistributedc_11// "SPDistributedCachePointerWrapper::Initi"...
0x65fbbb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x65fbc0  ldstr    aSpdistributedc_11// "SPDistributedCachePointerWrapper::Initi"...
0x65fbc5  newobj   instance void [mscorlib]System.InvalidOperationException::.ctor(string)
0x65fbca  throw
0x65fbcb  newobj   instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::.ctor()
0x65fbd0  stloc.s  6
0x65fbd2  call     valuetype Microsoft.SharePoint.Administration.SPServerRole Microsoft.SharePoint.Administration.SPServer::get_LocalServerRole()
0x65fbd7  ldc.i4.3
0x65fbd8  bne.un.s loc_65FBFA
0x65fbda  ldc.i4   0x78A091
0x65fbdf  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_Topology()
0x65fbe4  ldc.i4.s 0xA
0x65fbe6  ldstr    aUnexpectedUsag// "Unexpected usage of SPServerRole.Single"...
0x65fbeb  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output)
0x65fbf0  ldloc.s  6
0x65fbf2  ldc.i4.0
0x65fbf3  callvirt instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::set_DataCacheServiceAccountType(valuetype [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheServiceAccountType)
0x65fbf8  br.s     loc_65FC02
0x65fbfa  ldloc.s  6
0x65fbfc  ldc.i4.1
0x65fbfd  callvirt instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::set_DataCacheServiceAccountType(valuetype [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheServiceAccountType)
0x65fc02  ldloc.s  6
0x65fc04  ldloc.s  4
0x65fc06  callvirt instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::set_Servers(class [mscorlib]System.Collections.Generic.IEnumerable`1<class [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheServerEndpoint>)
0x65fc0b  ldloc.s  6
0x65fc0d  ldarg.0
0x65fc0e  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fc13  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_ChannelOpenTimeOut()
0x65fc18  callvirt instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::set_ChannelOpenTimeout(valuetype [mscorlib]System.TimeSpan)
0x65fc1d  ldc.i4   0x1DC792
0x65fc22  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fc27  ldc.i4.s 0x64
0x65fc29  ldstr    aDistributedcac_12// "DistributedCacheClient ChannelOpenTimeo"...
0x65fc2e  ldc.i4.1
0x65fc2f  newarr   [mscorlib]System.Object
0x65fc34  stloc.s  0x13
0x65fc36  ldloc.s  0x13
0x65fc38  ldc.i4.0
0x65fc39  ldloc.s  6
0x65fc3b  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_ChannelOpenTimeout()
0x65fc40  box      [mscorlib]System.TimeSpan
0x65fc45  stelem.ref
0x65fc46  ldloc.s  0x13
0x65fc48  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x65fc4d  ldloc.s  6
0x65fc4f  ldarg.0
0x65fc50  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fc55  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_RequestTimeout()
0x65fc5a  callvirt instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::set_RequestTimeout(valuetype [mscorlib]System.TimeSpan)
0x65fc5f  ldc.i4   0x1DC793
0x65fc64  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fc69  ldc.i4.s 0x64
0x65fc6b  ldstr    aDistributedcac_13// "DistributedCacheClient RequestTimeout '"...
0x65fc70  ldc.i4.1
0x65fc71  newarr   [mscorlib]System.Object
0x65fc76  stloc.s  0x14
0x65fc78  ldloc.s  0x14
0x65fc7a  ldc.i4.0
0x65fc7b  ldloc.s  6
0x65fc7d  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_RequestTimeout()
0x65fc82  box      [mscorlib]System.TimeSpan
0x65fc87  stelem.ref
0x65fc88  ldloc.s  0x14
0x65fc8a  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x65fc8f  ldloc.s  6
0x65fc91  ldarg.0
0x65fc92  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fc97  callvirt instance int32 Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_MaxConnectionsToServer()
0x65fc9c  callvirt instance void [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::set_MaxConnectionsToServer(int32)
0x65fca1  ldc.i4   0x1DC794
0x65fca6  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fcab  ldc.i4.s 0x64
0x65fcad  ldstr    aDistributedcac_14// "DistributedCacheClient MaxConnectionsTo"...
0x65fcb2  ldc.i4.1
0x65fcb3  newarr   [mscorlib]System.Object
0x65fcb8  stloc.s  0x15
0x65fcba  ldloc.s  0x15
0x65fcbc  ldc.i4.0
0x65fcbd  ldloc.s  6
0x65fcbf  callvirt instance int32 [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_MaxConnectionsToServer()
0x65fcc4  box      [mscorlib]System.Int32
0x65fcc9  stelem.ref
0x65fcca  ldloc.s  0x15
0x65fccc  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x65fcd1  ldloc.s  6
0x65fcd3  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fcd8  ldarg.0
0x65fcd9  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fcde  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_ChannelInitializationTimeout()
0x65fce3  callvirt instance void [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::set_ChannelInitializationTimeout(valuetype [mscorlib]System.TimeSpan)
0x65fce8  ldloc.s  6
0x65fcea  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fcef  ldarg.0
0x65fcf0  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fcf5  callvirt instance int32 Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_ConnectionBufferSize()
0x65fcfa  callvirt instance void [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::set_ConnectionBufferSize(int32)
0x65fcff  ldloc.s  6
0x65fd01  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fd06  ldarg.0
0x65fd07  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fd0c  callvirt instance int64 Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_MaxBufferPoolSize()
0x65fd11  callvirt instance void [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::set_MaxBufferPoolSize(int64)
0x65fd16  ldloc.s  6
0x65fd18  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fd1d  ldarg.0
0x65fd1e  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fd23  callvirt instance int32 Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_MaxBufferSize()
0x65fd28  callvirt instance void [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::set_MaxBufferSize(int32)
0x65fd2d  ldloc.s  6
0x65fd2f  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fd34  ldarg.0
0x65fd35  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fd3a  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_MaxOutputDelay()
0x65fd3f  callvirt instance void [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::set_MaxOutputDelay(valuetype [mscorlib]System.TimeSpan)
0x65fd44  ldloc.s  6
0x65fd46  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fd4b  ldarg.0
0x65fd4c  ldfld    class Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings Microsoft.SharePoint.DistributedCaching.SPDistributedCachePointerWrapper::_settings
0x65fd51  callvirt instance valuetype [mscorlib]System.TimeSpan Microsoft.SharePoint.DistributedCaching.Utilities.SPDistributedCacheClientConfigurationSettings::get_ReceiveTimeout()
0x65fd56  callvirt instance void [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::set_ReceiveTimeout(valuetype [mscorlib]System.TimeSpan)
0x65fd5b  ldc.i4   0x1DC795
0x65fd60  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fd65  ldc.i4.s 0x64
0x65fd67  ldstr    aDistributedcac_15// "DistributedCacheClient TransportPropert"...
0x65fd6c  ldc.i4.6
0x65fd6d  newarr   [mscorlib]System.Object
0x65fd72  stloc.s  0x16
0x65fd74  ldloc.s  0x16
0x65fd76  ldc.i4.0
0x65fd77  ldloc.s  6
0x65fd79  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fd7e  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::get_ChannelInitializationTimeout()
0x65fd83  box      [mscorlib]System.TimeSpan
0x65fd88  stelem.ref
0x65fd89  ldloc.s  0x16
0x65fd8b  ldc.i4.1
0x65fd8c  ldloc.s  6
0x65fd8e  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fd93  callvirt instance int32 [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::get_ConnectionBufferSize()
0x65fd98  box      [mscorlib]System.Int32
0x65fd9d  stelem.ref
0x65fd9e  ldloc.s  0x16
0x65fda0  ldc.i4.2
0x65fda1  ldloc.s  6
0x65fda3  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fda8  callvirt instance int64 [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::get_MaxBufferPoolSize()
0x65fdad  box      [mscorlib]System.Int64
0x65fdb2  stelem.ref
0x65fdb3  ldloc.s  0x16
0x65fdb5  ldc.i4.3
0x65fdb6  ldloc.s  6
0x65fdb8  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fdbd  callvirt instance int32 [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::get_MaxBufferSize()
0x65fdc2  box      [mscorlib]System.Int32
0x65fdc7  stelem.ref
0x65fdc8  ldloc.s  0x16
0x65fdca  ldc.i4.4
0x65fdcb  ldloc.s  6
0x65fdcd  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fdd2  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::get_MaxOutputDelay()
0x65fdd7  box      [mscorlib]System.TimeSpan
0x65fddc  stelem.ref
0x65fddd  ldloc.s  0x16
0x65fddf  ldc.i4.5
0x65fde0  ldloc.s  6
0x65fde2  callvirt instance class [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties [Microsoft.ApplicationServer.Caching.Client]Microsoft.ApplicationServer.Caching.DataCacheFactoryConfiguration::get_TransportProperties()
0x65fde7  callvirt instance valuetype [mscorlib]System.TimeSpan [Microsoft.ApplicationServer.Caching.Core]Microsoft.ApplicationServer.Caching.DataCacheTransportProperties::get_ReceiveTimeout()
0x65fdec  box      [mscorlib]System.TimeSpan
0x65fdf1  stelem.ref
0x65fdf2  ldloc.s  0x16
0x65fdf4  call     void Microsoft.SharePoint.Diagnostics.ULS::SendTraceTag(unsigned int32 tagID, class Microsoft.SharePoint.Diagnostics.ULSCatBase categoryID, valuetype Microsoft.SharePoint.Diagnostics.ULSTraceLevel level, string output, object[] data)
0x65fdf9  ldc.i4   0x78A092
0x65fdfe  call     class Microsoft.SharePoint.Diagnostics.ULSCat Microsoft.SharePoint.Diagnostics.ULSCat::get_msoulscat_WSS_DistributedCache()
0x65fe03  ldc.i4.s 0x64
0x65fe05  ldstr    aIsdatacachesec// "IsDataCacheSecurityEnabled '{0}'."
0x65fe0a  ldc.i4.1
0x65fe0b  newarr   [mscorlib]System.Object
  ... truncated ...
```
