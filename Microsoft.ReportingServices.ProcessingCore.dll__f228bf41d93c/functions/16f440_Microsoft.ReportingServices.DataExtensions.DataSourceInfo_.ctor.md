# Microsoft.ReportingServices.DataExtensions.DataSourceInfo::.ctor

- ea: `0x16f440`
- end: `0x16f6b2`
- name: `Microsoft.ReportingServices.DataExtensions.DataSourceInfo::.ctor`
- size: `626`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `loader_planting, service_task, installer_update, broker_com_uri`

## string_xrefs

- `0x16f4d3`: `extension`
- `0x16f573`: `linkid`
- `0x16f673`: `modellastupdatedtime`

## pseudocode

```c

```

## disassembly

```asm
0x16f440  ldarg.0
0x16f441  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0x16f446  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_modelID
0x16f44b  ldarg.0
0x16f44c  call     instance void [mscorlib]System.Object::.ctor()
0x16f451  ldarg.0
0x16f452  ldarg.1
0x16f453  ldstr    aId_1// "id"
0x16f458  ldtoken  [mscorlib]System.Guid
0x16f45d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f462  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f467  unbox.any [mscorlib]System.Guid
0x16f46c  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_id
0x16f471  ldarg.0
0x16f472  ldarg.1
0x16f473  ldstr    aOriginalid// "originalid"
0x16f478  ldtoken  [mscorlib]System.Guid
0x16f47d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f482  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f487  unbox.any [mscorlib]System.Guid
0x16f48c  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_DataSourceWithCredentialsId
0x16f491  ldarg.0
0x16f492  ldarg.1
0x16f493  ldstr    aName// "name"
0x16f498  ldtoken  [mscorlib]System.String
0x16f49d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f4a2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f4a7  castclass [mscorlib]System.String
0x16f4ac  stfld    string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_name
0x16f4b1  ldarg.0
0x16f4b2  ldarg.1
0x16f4b3  ldstr    aOriginalname// "originalname"
0x16f4b8  ldtoken  [mscorlib]System.String
0x16f4bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f4c2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f4c7  castclass [mscorlib]System.String
0x16f4cc  stfld    string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_originalName
0x16f4d1  ldarg.0
0x16f4d2  ldarg.1
0x16f4d3  ldstr    aExtension// "extension"
0x16f4d8  ldtoken  [mscorlib]System.String
0x16f4dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f4e2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f4e7  castclass [mscorlib]System.String
0x16f4ec  stfld    string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_extension
0x16f4f1  ldarg.0
0x16f4f2  ldarg.1
0x16f4f3  ldstr    aConnectionstri// "connectionstringencrypted"
0x16f4f8  ldtoken  unsigned int8[]
0x16f4fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f502  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f507  castclass unsigned int8[]
0x16f50c  stfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_connectionStringEncrypted
0x16f511  ldarg.0
0x16f512  ldarg.1
0x16f513  ldstr    aOriginalconnec// "originalconnectionstringencrypted"
0x16f518  ldtoken  unsigned int8[]
0x16f51d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f522  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f527  castclass unsigned int8[]
0x16f52c  stfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_originalConnectionStringEncrypted
0x16f531  ldarg.0
0x16f532  ldarg.1
0x16f533  ldstr    aOriginalconnec_0// "originalConnectStringExpressionBased"
0x16f538  ldtoken  [mscorlib]System.Boolean
0x16f53d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f542  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f547  unbox.any [mscorlib]System.Boolean
0x16f54c  stfld    bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_originalConnectStringExpressionBased
0x16f551  ldarg.0
0x16f552  ldarg.1
0x16f553  ldstr    aDatasourcerefe_0// "datasourcereference"
0x16f558  ldtoken  [mscorlib]System.String
0x16f55d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f562  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f567  castclass [mscorlib]System.String
0x16f56c  stfld    string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_dataSourceReference
0x16f571  ldarg.0
0x16f572  ldarg.1
0x16f573  ldstr    aLinkid// "linkid"
0x16f578  ldtoken  [mscorlib]System.Guid
0x16f57d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f582  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f587  unbox.any [mscorlib]System.Guid
0x16f58c  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_linkID
0x16f591  ldarg.0
0x16f592  ldarg.1
0x16f593  ldstr    aSecdesc// "secdesc"
0x16f598  ldtoken  unsigned int8[]
0x16f59d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f5a2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f5a7  castclass unsigned int8[]
0x16f5ac  stfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_secDesc
0x16f5b1  ldarg.0
0x16f5b2  ldarg.1
0x16f5b3  ldstr    aCredentialsret// "credentialsretrieval"
0x16f5b8  ldtoken  CredentialsRetrievalOption
0x16f5bd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f5c2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f5c7  unbox.any CredentialsRetrievalOption
0x16f5cc  stfld    valuetype CredentialsRetrievalOption Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_credentialsRetrieval
0x16f5d1  ldarg.0
0x16f5d2  ldarg.1
0x16f5d3  ldstr    aPrompt_0// "prompt"
0x16f5d8  ldtoken  [mscorlib]System.String
0x16f5dd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f5e2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f5e7  castclass [mscorlib]System.String
0x16f5ec  stfld    string Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_prompt
0x16f5f1  ldarg.0
0x16f5f2  ldarg.1
0x16f5f3  ldstr    aUsernameencryp// "usernameencrypted"
0x16f5f8  ldtoken  unsigned int8[]
0x16f5fd  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f602  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f607  castclass unsigned int8[]
0x16f60c  stfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_userNameEncrypted
0x16f611  ldarg.0
0x16f612  ldarg.1
0x16f613  ldstr    aPasswordencryp// "passwordencrypted"
0x16f618  ldtoken  unsigned int8[]
0x16f61d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f622  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f627  castclass unsigned int8[]
0x16f62c  stfld    unsigned int8[] Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_passwordEncrypted
0x16f631  ldarg.0
0x16f632  ldarg.1
0x16f633  ldstr    aDatasourceflag// "datasourceflags"
0x16f638  ldtoken  DataSourceFlags
0x16f63d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f642  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f647  unbox.any DataSourceFlags
0x16f64c  stfld    valuetype DataSourceFlags Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_flags
0x16f651  ldarg.0
0x16f652  ldarg.1
0x16f653  ldstr    aModelid// "modelid"
0x16f658  ldtoken  [mscorlib]System.Guid
0x16f65d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f662  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f667  unbox.any [mscorlib]System.Guid
0x16f66c  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_modelID
0x16f671  ldarg.0
0x16f672  ldarg.1
0x16f673  ldstr    aModellastupdat// "modellastupdatedtime"
0x16f678  ldtoken  valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x16f67d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f682  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f687  unbox.any valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime>
0x16f68c  stfld    valuetype [mscorlib]System.Nullable`1<valuetype [mscorlib]System.DateTime> Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_modelLastUpdatedTime
0x16f691  ldarg.0
0x16f692  ldarg.1
0x16f693  ldstr    aIsembeddedinmo// "isembeddedinmodel"
0x16f698  ldtoken  [mscorlib]System.Boolean
0x16f69d  call     class [mscorlib]System.Type [mscorlib]System.Type::GetTypeFromHandle(valuetype [mscorlib]System.RuntimeTypeHandle)
0x16f6a2  callvirt instance object [mscorlib]System.Runtime.Serialization.SerializationInfo::GetValue(string, class [mscorlib]System.Type)
0x16f6a7  unbox.any [mscorlib]System.Boolean
0x16f6ac  stfld    bool Microsoft.ReportingServices.DataExtensions.DataSourceInfo::m_isEmbeddedInModel
0x16f6b1  ret
```
