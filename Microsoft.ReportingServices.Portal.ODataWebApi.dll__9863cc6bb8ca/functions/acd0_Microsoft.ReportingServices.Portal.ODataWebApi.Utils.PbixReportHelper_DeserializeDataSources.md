# Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataSources

- ea: `0xacd0`
- end: `0xae47`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.Utils.PbixReportHelper::DeserializeDataSources`
- size: `375`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0xa670`
- `0xa900`

## callees

- `0xacd0`

## pseudocode

```c

```

## disassembly

```asm
0xacd0  ldarg.2
0xacd1  ldstr    aDatasources// "DataSources"
0xacd6  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xacdb  callvirt instance string [mscorlib]System.Object::ToString()
0xace0  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xace5  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray
0xacea  stloc.0
0xaceb  ldloc.0
0xacec  brfalse  loc_AE46
0xacf1  ldarg.1
0xacf2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::.ctor()
0xacf7  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::set_DataSources(class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>)
0xacfc  ldloc.0
0xacfd  callvirt instance class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken> [Newtonsoft.Json]Newtonsoft.Json.Linq.JArray::GetEnumerator()
0xad02  stloc.1
0xad03  br       loc_AE2F
0xad08  ldloc.1
0xad09  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IEnumerator`1<class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken>::get_Current()
0xad0e  dup
0xad0f  ldstr    aDatamodeldatas// "DataModelDataSource"
0xad14  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0xad19  callvirt instance string [mscorlib]System.Object::ToString()
0xad1e  call     object [Newtonsoft.Json]Newtonsoft.Json.JsonConvert::DeserializeObject(string)
0xad23  castclass [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject
0xad28  stloc.2
0xad29  ldloc.2
0xad2a  ldstr    aKind// "Kind"
0xad2f  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xad34  callvirt instance string [mscorlib]System.Object::ToString()
0xad39  ldloca.s 3
0xad3b  call     T0x2B0000E4
0xad40  brtrue.s loc_AD4D
0xad42  ldstr    aInvalidDataSou// "Invalid data source kind specified!"
0xad47  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xad4c  throw
0xad4d  ldloc.2
0xad4e  ldstr    aType_0// "Type"
0xad53  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xad58  callvirt instance string [mscorlib]System.Object::ToString()
0xad5d  ldloca.s 4
0xad5f  call     T0x2B0000E5
0xad64  brtrue.s loc_AD71
0xad66  ldstr    aInvalidDataSou_0// "Invalid data source type specified!"
0xad6b  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xad70  throw
0xad71  ldloc.2
0xad72  ldstr    aAuthtype// "AuthType"
0xad77  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xad7c  callvirt instance string [mscorlib]System.Object::ToString()
0xad81  ldloca.s 5
0xad83  call     T0x2B0000E6
0xad88  brtrue.s loc_AD95
0xad8a  ldstr    aInvalidDataSou_1// "Invalid data source authType specified!"
0xad8f  newobj   instance void [mscorlib]System.ArgumentOutOfRangeException::.ctor(string)
0xad94  throw
0xad95  ldloc.s  5
0xad97  brtrue.s loc_ADB6
0xad99  ldloc.3
0xad9a  ldloc.s  4
0xad9c  call     valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType[] [Microsoft.ReportingServices.Portal.Services]Microsoft.ReportingServices.Portal.Services.ODataExtensions.DataModelDataSourceExtensions::GetSupportedAuthKinds(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind, valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType)
0xada1  stloc.s  9
0xada3  ldloc.s  9
0xada5  call     T0x2B0000E7
0xadaa  ldc.i4.0
0xadab  ble.s    loc_ADB6
0xadad  ldloc.s  9
0xadaf  call     T0x2B0000E8
0xadb4  stloc.s  5
0xadb6  ldloc.2
0xadb7  ldstr    aModelconnectio// "ModelConnectionName"
0xadbc  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xadc1  brtrue.s loc_ADC6
0xadc3  ldnull
0xadc4  br.s     loc_ADD6
0xadc6  ldloc.2
0xadc7  ldstr    aModelconnectio// "ModelConnectionName"
0xadcc  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JObject::get_Item(string)
0xadd1  callvirt instance string [mscorlib]System.Object::ToString()
0xadd6  stloc.s  6
0xadd8  ldstr    aConnectionstri// "ConnectionString"
0xaddd  callvirt instance class [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken [Newtonsoft.Json]Newtonsoft.Json.Linq.JToken::get_Item(object)
0xade2  callvirt instance string [mscorlib]System.Object::ToString()
0xade7  stloc.s  7
0xade9  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::.ctor()
0xadee  dup
0xadef  ldloc.s  7
0xadf1  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_ConnectionString(string)
0xadf6  dup
0xadf7  newobj   instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::.ctor()
0xadfc  dup
0xadfd  ldloc.3
0xadfe  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Kind(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceKind)
0xae03  dup
0xae04  ldloc.s  4
0xae06  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_Type(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceType)
0xae0b  dup
0xae0c  ldloc.s  6
0xae0e  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_ModelConnectionName(string)
0xae13  dup
0xae14  ldloc.s  5
0xae16  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource::set_AuthType(valuetype [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSourceAuthType)
0xae1b  callvirt instance void [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource::set_DataModelDataSource(class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataModelDataSource)
0xae20  stloc.s  8
0xae22  ldarg.1
0xae23  callvirt instance class [mscorlib]System.Collections.Generic.IList`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource> [Microsoft.ReportingServices.Portal.Interfaces]Model.PowerBIReport::get_DataSources()
0xae28  ldloc.s  8
0xae2a  callvirt instance void class [mscorlib]System.Collections.Generic.ICollection`1<class [Microsoft.ReportingServices.Portal.Interfaces]Model.DataSource>::Add(var<u1>)
0xae2f  ldloc.1
0xae30  callvirt instance bool [mscorlib]System.Collections.IEnumerator::MoveNext()
0xae35  brtrue   loc_AD08
0xae3a  leave.s  loc_AE46
0xae3c  ldloc.1
0xae3d  brfalse.s loc_AE45
0xae3f  ldloc.1
0xae40  callvirt instance void [mscorlib]System.IDisposable::Dispose()
0xae45  endfinally
0xae46  ret
```
