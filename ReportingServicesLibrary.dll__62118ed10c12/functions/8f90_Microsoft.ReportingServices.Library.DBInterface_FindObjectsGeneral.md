# Microsoft.ReportingServices.Library.DBInterface::FindObjectsGeneral

- ea: `0x8f90`
- end: `0x9423`
- name: `Microsoft.ReportingServices.Library.DBInterface::FindObjectsGeneral`
- size: `1171`
- prototype: ``
- caller_count: `0`
- callee_count: `10`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callees

- `0x4630`
- `0x8f90`
- `0x9430`
- `0x9470`
- `0x9480`
- `0x94b0`
- `0x9660`
- `0x137a0`
- `0x137e0`
- `0x87790`

## string_xrefs

- `0x9058`: `@Path`
- `0x8fed`: `\nSELECT\n   C.Type,\n   C.PolicyID,\n   SD.NtSecDescPrimary,\n   C.Name,\n   C.Path,\n   C.ItemID,\n   C.ContentSize AS [Size],\n   C.Description,\n   C.CreationDate,\n   C.ModifiedDate,\n   SUSER_SNAME(CU.Sid),\n   CU.UserName,\n   SUSER_SNAME(MU.Sid),\n   MU.UserName,\n   C.MimeType,\n   C.ExecutionTime,\n   C.Hidden,\n   C.SubType,\n   C.ComponentID\nFROM\n   Catalog AS C\n   INNER JOIN Users AS CU ON C.CreatedByID = CU.UserID\n   INNER JOIN Users AS MU ON C.ModifiedB`
- `0x9021`: `C.Path like @Prefix escape '*'`
- `0x9050`: `P.Path = @Path`
- `0x9182`: `CreatedBy`
- `0x9206`: `ComponentID`
- `0x92a5`: `ISNULL(SUSER_SNAME(CU.Sid), CU.UserName)`
- `0x92d0`: `ISNULL(SUSER_SNAME(MU.Sid), MU.UserName)`
- `0x9320`: `C.ComponentID`
- `0x9369`: `C.Path NOT LIKE '/68f0607b-9378-4bbb-9e70-4da3d7d66838%'`

## pseudocode

```c

```

## disassembly

```asm
0x8f90  ldc.i4.0
0x8f91  stloc.0
0x8f92  ldarg.3
0x8f93  callvirt instance bool Microsoft.ReportingServices.Library.ItemSearchOptions::get_ComponentLookup()
0x8f98  brfalse.s loc_8F9E
0x8f9a  ldloc.0
0x8f9b  ldc.i4.1
0x8f9c  or
0x8f9d  stloc.0
0x8f9e  ldarg.0
0x8f9f  ldarg.s  7
0x8fa1  ldarg.s  6
0x8fa3  ldloc.0
0x8fa4  callvirt instance class Microsoft.ReportingServices.Library.ICatalogItemDescriptorFactory Microsoft.ReportingServices.Library.DBInterface::CreateDescriptorFactory(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator pathTranslator, class Microsoft.ReportingServices.Library.Security secMgr, valuetype Microsoft.ReportingServices.Library.ItemDescriptorOptions options)
0x8fa9  stloc.1
0x8faa  ldarga.s 2
0x8fac  constrained. Microsoft.ReportingServices.Library.Soap.BooleanOperatorEnum
0x8fb2  callvirt instance string [mscorlib]System.Object::ToString()
0x8fb7  stloc.2
0x8fb8  ldarg.0
0x8fb9  ldstr    asc_90EAC// ""
0x8fbe  ldnull
0x8fbf  callvirt instance class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::NewStandardSqlCommand(string, class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlConnection)
0x8fc4  stloc.3
0x8fc5  ldloc.3
0x8fc6  ldc.i4.1
0x8fc7  callvirt instance void [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::set_CommandType(valuetype [System.Data]System.Data.CommandType)
0x8fcc  ldloc.3
0x8fcd  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::get_Parameters()
0x8fd2  ldstr    aAuthtype// "@AuthType"
0x8fd7  ldarg.0
0x8fd8  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Library.DBInterface::get_UserContext()
0x8fdd  callvirt instance valuetype [Microsoft.ReportingServices.Interfaces]Microsoft.ReportingServices.Interfaces.AuthenticationType [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_AuthenticationType()
0x8fe2  box      [mscorlib]System.Int32
0x8fe7  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameterCollection::AddWithValue(string, object)
0x8fec  pop
0x8fed  ldstr    aSelectCTypeCPo// "\r\nSELECT\r\n   C.Type,\r\n   C.Policy"...
0x8ff2  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor(string)
0x8ff7  stloc.s  4
0x8ff9  ldnull
0x8ffa  stloc.s  5
0x8ffc  ldarg.s  7
0x8ffe  ldarg.1
0x8fff  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.ItemPathBase::get_Value()
0x9004  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.IPathTranslator::ExternalToCatalog(string)
0x9009  stloc.s  6
0x900b  ldarg.3
0x900c  callvirt instance bool Microsoft.ReportingServices.Library.ItemSearchOptions::get_Recursive()
0x9011  brfalse.s loc_9043
0x9013  ldloc.s  6
0x9015  ldsfld   string [mscorlib]System.String::Empty
0x901a  call     bool [mscorlib]System.String::op_Inequality(string, string)
0x901f  brfalse.s loc_9067
0x9021  ldstr    aCPathLikePrefi// "C.Path like @Prefix escape '*'"
0x9026  stloc.s  5
0x9028  ldloc.s  6
0x902a  call     string Microsoft.ReportingServices.Library.DBInterface::BuildRecursivePathPrefix(string catalogPrefix)
0x902f  stloc.s  6
0x9031  ldloc.3
0x9032  ldstr    aPrefix// "@Prefix"
0x9037  ldc.i4.s 0xC
0x9039  ldloc.s  6
0x903b  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x9040  pop
0x9041  br.s     loc_9067
0x9043  ldloc.s  4
0x9045  ldstr    aInnerJoinCatal// " INNER JOIN Catalog AS P ON C.ParentID "...
0x904a  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x904f  pop
0x9050  ldstr    aPPathPath// "P.Path = @Path"
0x9055  stloc.s  5
0x9057  ldloc.3
0x9058  ldstr    aPath// "@Path"
0x905d  ldc.i4.s 0xC
0x905f  ldloc.s  6
0x9061  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x9066  pop
0x9067  newobj   instance void [mscorlib]System.Text.StringBuilder::.ctor()
0x906c  stloc.s  7
0x906e  ldarg.s  4
0x9070  callvirt instance valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<var<u1>, !!T0> class [mscorlib]System.Collections.Generic.Dictionary`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::GetEnumerator()
0x9075  stloc.s  9
0x9077  br       loc_9340
0x907c  ldloca.s 9
0x907e  call     instance valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<var<u1>, !!T0> valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::get_Current()
0x9083  stloc.s  0xA
0x9085  ldloca.s 0xA
0x9087  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::get_Key()
0x908c  stloc.s  0xB
0x908e  ldloca.s 0xA
0x9090  call     instance var<u1> valuetype [mscorlib]System.Collections.Generic.KeyValuePair`2<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::get_Value()
0x9095  stloc.s  0xC
0x9097  ldloc.s  0xB
0x9099  call     unsigned int32 <PrivateImplementationDetails>::ComputeStringHash(string s)
0x909e  stloc.s  0xD
0x90a0  ldloc.s  0xD
0x90a2  ldc.i4   0x84616586
0x90a7  bgt.un.s loc_90F5
0x90a9  ldloc.s  0xD
0x90ab  ldc.i4   0x4C8DA3F6
0x90b0  bgt.un.s loc_90CF
0x90b2  ldloc.s  0xD
0x90b4  ldc.i4   0xFE07306
0x90b9  beq      loc_9154
0x90be  ldloc.s  0xD
0x90c0  ldc.i4   0x4C8DA3F6
0x90c5  beq      loc_91C2
0x90ca  br       loc_9330
0x90cf  ldloc.s  0xD
0x90d1  ldc.i4   0x66DE7A09
0x90d6  beq      loc_916A
0x90db  ldloc.s  0xD
0x90dd  ldc.i4   0x75AFE364
0x90e2  beq.s    loc_913E
0x90e4  ldloc.s  0xD
0x90e6  ldc.i4   0x84616586
0x90eb  beq      loc_9180
0x90f0  br       loc_9330
0x90f5  ldloc.s  0xD
0x90f7  ldc.i4   0xABC51FDD
0x90fc  bgt.un.s loc_911B
0x90fe  ldloc.s  0xD
0x9100  ldc.i4   0x8EA11CFD
0x9105  beq      loc_9204
0x910a  ldloc.s  0xD
0x910c  ldc.i4   0xABC51FDD
0x9111  beq      loc_91EE
0x9116  br       loc_9330
0x911b  ldloc.s  0xD
0x911d  ldc.i4   0xB12DEC60
0x9122  beq.s    loc_9196
0x9124  ldloc.s  0xD
0x9126  ldc.i4   0xD155D06D
0x912b  beq      loc_91D8
0x9130  ldloc.s  0xD
0x9132  ldc.i4   0xD17D9B0B
0x9137  beq.s    loc_91AC
0x9139  br       loc_9330
0x913e  ldloc.s  0xB
0x9140  ldstr    aAll// "All"
0x9145  call     bool [mscorlib]System.String::op_Equality(string, string)
0x914a  brtrue   loc_921A
0x914f  br       loc_9330
0x9154  ldloc.s  0xB
0x9156  ldstr    aName// "Name"
0x915b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9160  brtrue   loc_9273
0x9165  br       loc_9330
0x916a  ldloc.s  0xB
0x916c  ldstr    aDescription_0// "Description"
0x9171  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9176  brtrue   loc_928A
0x917b  br       loc_9330
0x9180  ldloc.s  0xB
0x9182  ldstr    aCreatedby// "CreatedBy"
0x9187  call     bool [mscorlib]System.String::op_Equality(string, string)
0x918c  brtrue   loc_92A1
0x9191  br       loc_9330
0x9196  ldloc.s  0xB
0x9198  ldstr    aCreationdate_0// "CreationDate"
0x919d  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91a2  brtrue   loc_92B8
0x91a7  br       loc_9330
0x91ac  ldloc.s  0xB
0x91ae  ldstr    aModifiedby// "ModifiedBy"
0x91b3  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91b8  brtrue   loc_92CC
0x91bd  br       loc_9330
0x91c2  ldloc.s  0xB
0x91c4  ldstr    aModifieddate_0// "ModifiedDate"
0x91c9  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91ce  brtrue   loc_92E0
0x91d3  br       loc_9330
0x91d8  ldloc.s  0xB
0x91da  ldstr    aType_0// "Type"
0x91df  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91e4  brtrue   loc_92F4
0x91e9  br       loc_9330
0x91ee  ldloc.s  0xB
0x91f0  ldstr    aSubtype_0// "Subtype"
0x91f5  call     bool [mscorlib]System.String::op_Equality(string, string)
0x91fa  brtrue   loc_9308
0x91ff  br       loc_9330
0x9204  ldloc.s  0xB
0x9206  ldstr    aComponentid_0// "ComponentID"
0x920b  call     bool [mscorlib]System.String::op_Equality(string, string)
0x9210  brtrue   loc_931C
0x9215  br       loc_9330
0x921a  ldloc.s  7
0x921c  callvirt instance int32 [mscorlib]System.Text.StringBuilder::get_Length()
0x9221  ldc.i4.0
0x9222  ble.s    loc_923C
0x9224  ldloc.s  7
0x9226  ldstr    asc_9657E// " "
0x922b  ldloc.2
0x922c  ldstr    asc_9657E// " "
0x9231  call     string [mscorlib]System.String::Concat(string, string, string)
0x9236  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x923b  pop
0x923c  ldloc.s  0xC
0x923e  ldfld    class [mscorlib]System.Collections.Generic.IList`1<string> Microsoft.ReportingServices.Library.ItemSearchCondition::Values
0x9243  ldc.i4.0
0x9244  callvirt instance var<u1> class [mscorlib]System.Collections.Generic.IList`1<string>::get_Item(!!T0)
0x9249  ldc.i4.1
0x924a  call     string [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.Storage::EncodeForSearch(string, bool)
0x924f  stloc.s  0xE
0x9251  ldloc.s  7
0x9253  ldstr    aCNameLikeTextE// "(C.Name like @Text escape '*' or C.Desc"...
0x9258  callvirt instance class [mscorlib]System.Text.StringBuilder [mscorlib]System.Text.StringBuilder::Append(string)
0x925d  pop
0x925e  ldloc.3
0x925f  ldstr    aText_0// "@Text"
0x9264  ldc.i4.s 0xC
0x9266  ldloc.s  0xE
0x9268  callvirt instance class [Microsoft.Data.SqlClient]Microsoft.Data.SqlClient.SqlParameter [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand::AddParameter(string, valuetype [System.Data]System.Data.SqlDbType, object)
0x926d  pop
0x926e  br       loc_9340
0x9273  ldloc.s  0xB
0x9275  ldloc.s  0xC
0x9277  ldstr    aCName// "C.Name"
0x927c  ldloc.2
0x927d  ldloc.s  7
0x927f  ldloc.3
0x9280  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x9285  br       loc_9340
0x928a  ldloc.s  0xB
0x928c  ldloc.s  0xC
0x928e  ldstr    aCDescription// "C.Description"
0x9293  ldloc.2
0x9294  ldloc.s  7
0x9296  ldloc.3
0x9297  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x929c  br       loc_9340
0x92a1  ldloc.s  0xB
0x92a3  ldloc.s  0xC
0x92a5  ldstr    aIsnullSuserSna// "ISNULL(SUSER_SNAME(CU.Sid), CU.UserName"...
0x92aa  ldloc.2
0x92ab  ldloc.s  7
0x92ad  ldloc.3
0x92ae  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x92b3  br       loc_9340
0x92b8  ldloc.s  0xB
0x92ba  ldloc.s  0xC
0x92bc  ldstr    aCCreationdate// "C.CreationDate"
0x92c1  ldloc.2
0x92c2  ldloc.s  7
0x92c4  ldloc.3
0x92c5  call     void Microsoft.ReportingServices.Library.DBInterface::AddDateTimeSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x92ca  br.s     loc_9340
0x92cc  ldloc.s  0xB
0x92ce  ldloc.s  0xC
0x92d0  ldstr    aIsnullSuserSna_0// "ISNULL(SUSER_SNAME(MU.Sid), MU.UserName"...
0x92d5  ldloc.2
0x92d6  ldloc.s  7
0x92d8  ldloc.3
0x92d9  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x92de  br.s     loc_9340
0x92e0  ldloc.s  0xB
0x92e2  ldloc.s  0xC
0x92e4  ldstr    aCModifieddate// "C.ModifiedDate"
0x92e9  ldloc.2
0x92ea  ldloc.s  7
0x92ec  ldloc.3
0x92ed  call     void Microsoft.ReportingServices.Library.DBInterface::AddDateTimeSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x92f2  br.s     loc_9340
0x92f4  ldloc.s  0xB
0x92f6  ldloc.s  0xC
0x92f8  ldstr    aCType// "C.Type"
0x92fd  ldloc.2
0x92fe  ldloc.s  7
0x9300  ldloc.3
0x9301  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x9306  br.s     loc_9340
0x9308  ldloc.s  0xB
0x930a  ldloc.s  0xC
0x930c  ldstr    aCSubtype// "C.SubType"
0x9311  ldloc.2
0x9312  ldloc.s  7
0x9314  ldloc.3
0x9315  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x931a  br.s     loc_9340
0x931c  ldloc.s  0xB
0x931e  ldloc.s  0xC
0x9320  ldstr    aCComponentid// "C.ComponentID"
0x9325  ldloc.2
0x9326  ldloc.s  7
0x9328  ldloc.3
0x9329  call     void Microsoft.ReportingServices.Library.DBInterface::AddSearchCondition(string property, class Microsoft.ReportingServices.Library.ItemSearchCondition condition, string field, string operation, class [mscorlib]System.Text.StringBuilder query, class [Microsoft.ReportingServices.Storage]Microsoft.ReportingServices.Library.InstrumentedSqlCommand command)
0x932e  br.s     loc_9340
0x9330  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_CatalogTrace()
0x9335  ldc.i4.0
0x9336  ldstr    aInvalidFindite// "Invalid FindItems search condition"
0x933b  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Assert(bool, string)
0x9340  ldloca.s 9
0x9342  call     instance bool valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>::MoveNext()
0x9347  brtrue   loc_907C
0x934c  leave.s  loc_935C
0x934e  ldloca.s 9
0x9350  constrained. valuetype [mscorlib]System.Collections.Generic.Dictionary`2/Enumerator<string, class Microsoft.ReportingServices.Library.ItemSearchCondition>
0x9356  callvirt instance void [mscorlib]System.IDisposable::Dispose()
  ... truncated ...
```
