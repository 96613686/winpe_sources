# Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch107

- ea: `0xcf740`
- end: `0xd018b`
- name: `Microsoft.SharePoint.SPStoredProceduresContent::GetStoredProceduresBatch107`
- size: `2635`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0xd24c0`

## callees

- `0x17e710`

## string_xrefs

- `0xcf76d`: `proc_UpdateStatisticsForProjectServer`
- `0xcf793`: `proc_UpdateStatisticsInternal`
- `0xcfbeb`: `@TimeCreated`
- `0xcfbac`: `@TemplateVersion`
- `0xcfac4`: `@ExternalSecurityProvider`
- `0xcf8ec`: `@WebTemplate`
- `0xcf747`: `proc_UpdateStatisticsForContent`
- `0xcf7b9`: `proc_UpdateStreamHash`
- `0xcf860`: `proc_UpdateTpWebMetaData`
- `0xcf9f9`: `@Config`
- `0xcfb98`: `@OverwriteMUICultures`
- `0xcfc57`: `proc_UpdateUncustomizedFeatureVersion`
- `0xcfcbc`: `proc_UpdateUserInfoInTableFromRowUpdater`
- `0xcfe8d`: `proc_UpdateUserResource`
- `0xcff89`: `proc_UpdateVersionVirusInfo`
- `0xd0044`: `proc_UpdateView`
- `0xd0163`: `@bUpdateAllPersonalViews`

## pseudocode

```c

```

## disassembly

```asm
0xcf740  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcf745  stloc.0
0xcf746  ldarg.0
0xcf747  ldstr    aProcUpdatestat_2// "proc_UpdateStatisticsForContent"
0xcf74c  ldloc.0
0xcf74d  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcf752  ldloc.0
0xcf753  ldstr    aReturnValue// "@RETURN_VALUE"
0xcf758  ldc.i4.8
0xcf759  ldc.i4.0
0xcf75a  ldc.i4.1
0xcf75b  ldc.i4.0
0xcf75c  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf761  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf766  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcf76b  stloc.0
0xcf76c  ldarg.0
0xcf76d  ldstr    aProcUpdatestat_0// "proc_UpdateStatisticsForProjectServer"
0xcf772  ldloc.0
0xcf773  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcf778  ldloc.0
0xcf779  ldstr    aReturnValue// "@RETURN_VALUE"
0xcf77e  ldc.i4.8
0xcf77f  ldc.i4.0
0xcf780  ldc.i4.1
0xcf781  ldc.i4.0
0xcf782  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf787  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf78c  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcf791  stloc.0
0xcf792  ldarg.0
0xcf793  ldstr    aProcUpdatestat_1// "proc_UpdateStatisticsInternal"
0xcf798  ldloc.0
0xcf799  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcf79e  ldloc.0
0xcf79f  ldstr    aReturnValue// "@RETURN_VALUE"
0xcf7a4  ldc.i4.8
0xcf7a5  ldc.i4.0
0xcf7a6  ldc.i4.1
0xcf7a7  ldc.i4.0
0xcf7a8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf7ad  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf7b2  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcf7b7  stloc.0
0xcf7b8  ldarg.0
0xcf7b9  ldstr    aProcUpdatestre// "proc_UpdateStreamHash"
0xcf7be  ldloc.0
0xcf7bf  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcf7c4  ldloc.0
0xcf7c5  ldstr    aReturnValue// "@RETURN_VALUE"
0xcf7ca  ldc.i4.8
0xcf7cb  ldc.i4.0
0xcf7cc  ldc.i4.1
0xcf7cd  ldc.i4.0
0xcf7ce  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf7d3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf7d8  ldloc.0
0xcf7d9  ldstr    aSiteid_1// "@SiteId"
0xcf7de  ldc.i4.s 0xE
0xcf7e0  ldc.i4.0
0xcf7e1  ldc.i4.0
0xcf7e2  ldc.i4.0
0xcf7e3  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf7e8  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf7ed  ldloc.0
0xcf7ee  ldstr    aParentid_1// "@ParentId"
0xcf7f3  ldc.i4.s 0xE
0xcf7f5  ldc.i4.0
0xcf7f6  ldc.i4.0
0xcf7f7  ldc.i4.0
0xcf7f8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf7fd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf802  ldloc.0
0xcf803  ldstr    aDocid_1// "@DocId"
0xcf808  ldc.i4.s 0xE
0xcf80a  ldc.i4.0
0xcf80b  ldc.i4.0
0xcf80c  ldc.i4.0
0xcf80d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf812  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf817  ldloc.0
0xcf818  ldstr    aLevel_1// "@Level"
0xcf81d  ldc.i4.s 0x14
0xcf81f  ldc.i4.0
0xcf820  ldc.i4.0
0xcf821  ldc.i4.0
0xcf822  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf827  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf82c  ldloc.0
0xcf82d  ldstr    aContentversion// "@ContentVersion"
0xcf832  ldc.i4.8
0xcf833  ldc.i4.0
0xcf834  ldc.i4.0
0xcf835  ldc.i4.0
0xcf836  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf83b  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf840  ldloc.0
0xcf841  ldstr    aStreamhash// "@StreamHash"
0xcf846  ldc.i4.s 0x15
0xcf848  ldc.i4   0x400
0xcf84d  ldc.i4.0
0xcf84e  ldc.i4.0
0xcf84f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf854  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf859  newobj   instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::.ctor()
0xcf85e  stloc.0
0xcf85f  ldarg.0
0xcf860  ldstr    aProcUpdatetpwe// "proc_UpdateTpWebMetaData"
0xcf865  ldloc.0
0xcf866  callvirt instance void class [mscorlib]System.Collections.Generic.Dictionary`2<string, class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>>::Add(var<u1>, !!T0)
0xcf86b  ldloc.0
0xcf86c  ldstr    aReturnValue// "@RETURN_VALUE"
0xcf871  ldc.i4.8
0xcf872  ldc.i4.0
0xcf873  ldc.i4.1
0xcf874  ldc.i4.0
0xcf875  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf87a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf87f  ldloc.0
0xcf880  ldstr    aSiteid_1// "@SiteId"
0xcf885  ldc.i4.s 0xE
0xcf887  ldc.i4.0
0xcf888  ldc.i4.0
0xcf889  ldc.i4.0
0xcf88a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf88f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf894  ldloc.0
0xcf895  ldstr    aWebid_0// "@WebId"
0xcf89a  ldc.i4.s 0xE
0xcf89c  ldc.i4.0
0xcf89d  ldc.i4.0
0xcf89e  ldc.i4.0
0xcf89f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf8a4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf8a9  ldloc.0
0xcf8aa  ldstr    aTitle// "@Title"
0xcf8af  ldc.i4.s 0xC
0xcf8b1  ldc.i4   0xFF
0xcf8b6  ldc.i4.0
0xcf8b7  ldc.i4.0
0xcf8b8  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf8bd  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf8c2  ldloc.0
0xcf8c3  ldstr    aDescription_0// "@Description"
0xcf8c8  ldc.i4.s 0xC
0xcf8ca  ldc.i4.m1
0xcf8cb  ldc.i4.0
0xcf8cc  ldc.i4.0
0xcf8cd  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf8d2  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf8d7  ldloc.0
0xcf8d8  ldstr    aVersion_3// "@Version"
0xcf8dd  ldc.i4.8
0xcf8de  ldc.i4.0
0xcf8df  ldc.i4.0
0xcf8e0  ldc.i4.0
0xcf8e1  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf8e6  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf8eb  ldloc.0
0xcf8ec  ldstr    aWebtemplate_0// "@WebTemplate"
0xcf8f1  ldc.i4.8
0xcf8f2  ldc.i4.0
0xcf8f3  ldc.i4.0
0xcf8f4  ldc.i4.0
0xcf8f5  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf8fa  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf8ff  ldloc.0
0xcf900  ldstr    aLanguage_0// "@Language"
0xcf905  ldc.i4.8
0xcf906  ldc.i4.0
0xcf907  ldc.i4.0
0xcf908  ldc.i4.0
0xcf909  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf90e  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf913  ldloc.0
0xcf914  ldstr    aLocale// "@Locale"
0xcf919  ldc.i4.8
0xcf91a  ldc.i4.0
0xcf91b  ldc.i4.0
0xcf91c  ldc.i4.0
0xcf91d  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf922  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf927  ldloc.0
0xcf928  ldstr    aCollation// "@Collation"
0xcf92d  ldc.i4.s 0x10
0xcf92f  ldc.i4.0
0xcf930  ldc.i4.0
0xcf931  ldc.i4.0
0xcf932  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf937  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf93c  ldloc.0
0xcf93d  ldstr    aTimezone// "@TimeZone"
0xcf942  ldc.i4.s 0x10
0xcf944  ldc.i4.0
0xcf945  ldc.i4.0
0xcf946  ldc.i4.0
0xcf947  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf94c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf951  ldloc.0
0xcf952  ldstr    aTime24// "@Time24"
0xcf957  ldc.i4.2
0xcf958  ldc.i4.0
0xcf959  ldc.i4.0
0xcf95a  ldc.i4.0
0xcf95b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf960  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf965  ldloc.0
0xcf966  ldstr    aCalendartype// "@CalendarType"
0xcf96b  ldc.i4.s 0x10
0xcf96d  ldc.i4.0
0xcf96e  ldc.i4.0
0xcf96f  ldc.i4.0
0xcf970  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf975  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf97a  ldloc.0
0xcf97b  ldstr    aAdjusthijriday// "@AdjustHijriDays"
0xcf980  ldc.i4.s 0x10
0xcf982  ldc.i4.0
0xcf983  ldc.i4.0
0xcf984  ldc.i4.0
0xcf985  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf98a  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf98f  ldloc.0
0xcf990  ldstr    aAltcalendartyp// "@AltCalendarType"
0xcf995  ldc.i4.s 0x14
0xcf997  ldc.i4.0
0xcf998  ldc.i4.0
0xcf999  ldc.i4.0
0xcf99a  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf99f  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf9a4  ldloc.0
0xcf9a5  ldstr    aCalendarviewop// "@CalendarViewOptions"
0xcf9aa  ldc.i4.s 0x14
0xcf9ac  ldc.i4.0
0xcf9ad  ldc.i4.0
0xcf9ae  ldc.i4.0
0xcf9af  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf9b4  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf9b9  ldloc.0
0xcf9ba  ldstr    aWorkdays// "@WorkDays"
0xcf9bf  ldc.i4.s 0x10
0xcf9c1  ldc.i4.0
0xcf9c2  ldc.i4.0
0xcf9c3  ldc.i4.0
0xcf9c4  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf9c9  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf9ce  ldloc.0
0xcf9cf  ldstr    aWorkdaystartho// "@WorkDayStartHour"
0xcf9d4  ldc.i4.s 0x10
0xcf9d6  ldc.i4.0
0xcf9d7  ldc.i4.0
0xcf9d8  ldc.i4.0
0xcf9d9  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf9de  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf9e3  ldloc.0
0xcf9e4  ldstr    aWorkdayendhour// "@WorkDayEndHour"
0xcf9e9  ldc.i4.s 0x10
0xcf9eb  ldc.i4.0
0xcf9ec  ldc.i4.0
0xcf9ed  ldc.i4.0
0xcf9ee  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcf9f3  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcf9f8  ldloc.0
0xcf9f9  ldstr    aConfig_1// "@Config"
0xcf9fe  ldc.i4.s 0x10
0xcfa00  ldc.i4.0
0xcfa01  ldc.i4.0
0xcfa02  ldc.i4.0
0xcfa03  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcfa08  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcfa0d  ldloc.0
0xcfa0e  ldstr    aFlags_0// "@Flags"
0xcfa13  ldc.i4.8
0xcfa14  ldc.i4.0
0xcfa15  ldc.i4.0
0xcfa16  ldc.i4.0
0xcfa17  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcfa1c  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcfa21  ldloc.0
0xcfa22  ldstr    aIgnoredflagsma// "@IgnoredFlagsMask"
0xcfa27  ldc.i4.8
0xcfa28  ldc.i4.0
0xcfa29  ldc.i4.0
0xcfa2a  ldc.i4.0
0xcfa2b  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcfa30  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcfa35  ldloc.0
0xcfa36  ldstr    aAuthor// "@Author"
0xcfa3b  ldc.i4.8
0xcfa3c  ldc.i4.0
0xcfa3d  ldc.i4.0
0xcfa3e  ldc.i4.0
0xcfa3f  newobj   instance void Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo::.ctor(string name, valuetype [System.Data]System.Data.SqlDbType dbType, int32 size, bool output, bool hasDefault)
0xcfa44  callvirt instance void class [mscorlib]System.Collections.Generic.List`1<class Microsoft.SharePoint.Utilities.Sql.StoredProcedureParameterInfo>::Add(var<u1>)
0xcfa49  ldloc.0
0xcfa4a  ldstr    aDeftheme// "@DefTheme"
0xcfa4f  ldc.i4.s 0xC
0xcfa51  ldc.i4.s 0x40
0xcfa53  ldc.i4.0
0xcfa54  ldc.i4.0
  ... truncated ...
```
