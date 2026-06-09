# Microsoft.ReportingServices.Diagnostics.Task::.ctor_0

- ea: `0xd1b0`
- end: `0xd52e`
- name: `Microsoft.ReportingServices.Diagnostics.Task::.ctor_0`
- size: `894`
- prototype: ``
- caller_count: `0`
- callee_count: `22`
- tags: `service_task, broker_com_uri`

## callees

- `0xd1b0`
- `0xd830`
- `0xd860`
- `0xd880`
- `0xd8a0`
- `0xd8c0`
- `0xd900`
- `0xd920`
- `0xd940`
- `0xd960`
- `0xd980`
- `0xda80`
- `0xdaa0`
- `0xdb20`
- `0xf350`
- `0xf3a0`
- `0xf3f0`
- `0xf5f0`
- `0xf610`
- `0xf630`
- `0xf660`
- `0xf680`

## pseudocode

```c

```

## disassembly

```asm
0xd1b0  ldarg.0
0xd1b1  newobj   instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::.ctor()
0xd1b6  stfld    class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::m_trigger
0xd1bb  ldarg.0
0xd1bc  ldc.i4.1
0xd1bd  stfld    valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::m_state
0xd1c2  ldarg.0
0xd1c3  ldstr    asc_126C2// ""
0xd1c8  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_name
0xd1cd  ldarg.0
0xd1ce  ldstr    asc_126C2// ""
0xd1d3  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_lastRunStatus
0xd1d8  ldarg.0
0xd1d9  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xd1de  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::m_lastRunTime
0xd1e3  ldarg.0
0xd1e4  ldstr    asc_126C2// ""
0xd1e9  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_eventType
0xd1ee  ldarg.0
0xd1ef  ldstr    asc_126C2// ""
0xd1f4  stfld    string Microsoft.ReportingServices.Diagnostics.Task::m_eventData
0xd1f9  ldarg.0
0xd1fa  ldc.i4.1
0xd1fb  stfld    valuetype Microsoft.ReportingServices.Diagnostics.ScheduleType Microsoft.ReportingServices.Diagnostics.Task::m_type
0xd200  ldarg.0
0xd201  ldsfld   valuetype [mscorlib]System.Guid [mscorlib]System.Guid::Empty
0xd206  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.Task::m_id
0xd20b  ldarg.0
0xd20c  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xd211  stfld    valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::m_nextRunTime
0xd216  ldarg.0
0xd217  call     instance void [mscorlib]System.Object::.ctor()
0xd21c  ldarg.2
0xd21d  stloc.0
0xd21e  ldc.i4.1
0xd21f  ldarg.2
0xd220  add.ovf
0xd221  stloc.1
0xd222  ldc.i4.2
0xd223  ldarg.2
0xd224  add.ovf
0xd225  stloc.2
0xd226  ldc.i4.3
0xd227  ldarg.2
0xd228  add.ovf
0xd229  stloc.3
0xd22a  ldc.i4.4
0xd22b  ldarg.2
0xd22c  add.ovf
0xd22d  stloc.s  4
0xd22f  ldc.i4.5
0xd230  ldarg.2
0xd231  add.ovf
0xd232  stloc.s  5
0xd234  ldc.i4.6
0xd235  ldarg.2
0xd236  add.ovf
0xd237  stloc.s  6
0xd239  ldc.i4.7
0xd23a  ldarg.2
0xd23b  add.ovf
0xd23c  stloc.s  7
0xd23e  ldc.i4.8
0xd23f  ldarg.2
0xd240  add.ovf
0xd241  stloc.s  8
0xd243  ldc.i4.s 9
0xd245  ldarg.2
0xd246  add.ovf
0xd247  stloc.s  9
0xd249  ldc.i4.s 0xA
0xd24b  ldarg.2
0xd24c  add.ovf
0xd24d  stloc.s  0xA
0xd24f  ldc.i4.s 0xB
0xd251  ldarg.2
0xd252  add.ovf
0xd253  stloc.s  0xB
0xd255  ldc.i4.s 0xC
0xd257  ldarg.2
0xd258  add.ovf
0xd259  stloc.s  0xC
0xd25b  ldc.i4.s 0xD
0xd25d  ldarg.2
0xd25e  add.ovf
0xd25f  stloc.s  0xD
0xd261  ldc.i4.s 0xE
0xd263  ldarg.2
0xd264  add.ovf
0xd265  stloc.s  0xE
0xd267  ldc.i4.s 0xF
0xd269  ldarg.2
0xd26a  add.ovf
0xd26b  stloc.s  0xF
0xd26d  ldc.i4.s 0x10
0xd26f  ldarg.2
0xd270  add.ovf
0xd271  stloc.s  0x10
0xd273  ldc.i4.s 0x11
0xd275  ldarg.2
0xd276  add.ovf
0xd277  stloc.s  0x11
0xd279  ldc.i4.s 0x12
0xd27b  ldarg.2
0xd27c  add.ovf
0xd27d  stloc.s  0x12
0xd27f  ldc.i4.s 0x13
0xd281  ldarg.2
0xd282  add.ovf
0xd283  stloc.s  0x13
0xd285  ldc.i4.s 0x14
0xd287  ldarg.2
0xd288  add.ovf
0xd289  stloc.s  0x14
0xd28b  ldc.i4.s 0x15
0xd28d  ldarg.2
0xd28e  add.ovf
0xd28f  stloc.s  0x15
0xd291  ldc.i4.s 0x16
0xd293  ldarg.2
0xd294  add.ovf
0xd295  stloc.s  0x16
0xd297  ldc.i4.s 0x17
0xd299  ldarg.2
0xd29a  add.ovf
0xd29b  stloc.s  0x17
0xd29d  ldc.i4.s 0x18
0xd29f  ldarg.2
0xd2a0  add.ovf
0xd2a1  stloc.s  0x18
0xd2a3  ldarg.0
0xd2a4  ldarg.1
0xd2a5  ldloc.0
0xd2a6  callvirt instance valuetype [mscorlib]System.Guid [System.Data]System.Data.IDataRecord::GetGuid(int32)
0xd2ab  stfld    valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.Task::m_id
0xd2b0  ldarg.0
0xd2b1  ldarg.1
0xd2b2  ldloc.1
0xd2b3  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd2b8  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_Name(string value)
0xd2bd  ldarg.0
0xd2be  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xd2c3  stloc.s  0x19
0xd2c5  ldloc.s  0x19
0xd2c7  ldarg.1
0xd2c8  ldloc.2
0xd2c9  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0xd2ce  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_StartDate(valuetype [mscorlib]System.DateTime value)
0xd2d3  ldarg.0
0xd2d4  ldarg.1
0xd2d5  ldloc.3
0xd2d6  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd2db  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_Flags(valuetype Microsoft.ReportingServices.Diagnostics.TaskFlags value)
0xd2e0  ldarg.1
0xd2e1  ldloc.s  6
0xd2e3  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd2e8  brtrue.s loc_D2F9
0xd2ea  ldloc.s  0x19
0xd2ec  ldarg.1
0xd2ed  ldloc.s  6
0xd2ef  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0xd2f4  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::set_EndDate(valuetype [mscorlib]System.DateTime value)
0xd2f9  ldarg.1
0xd2fa  ldloc.s  0xF
0xd2fc  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd301  brtrue.s loc_D311
0xd303  ldarg.0
0xd304  ldarg.1
0xd305  ldloc.s  0xF
0xd307  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd30c  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_DatabaseState(valuetype Microsoft.ReportingServices.Diagnostics.TaskState value)
0xd311  ldarg.1
0xd312  ldloc.s  0x10
0xd314  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd319  brtrue.s loc_D329
0xd31b  ldarg.0
0xd31c  ldarg.1
0xd31d  ldloc.s  0x10
0xd31f  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd324  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_LastRunStatus(string value)
0xd329  ldarg.1
0xd32a  ldloc.s  4
0xd32c  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd331  brtrue.s loc_D341
0xd333  ldarg.0
0xd334  ldarg.1
0xd335  ldloc.s  4
0xd337  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0xd33c  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_NextRunTime(valuetype [mscorlib]System.DateTime value)
0xd341  ldarg.1
0xd342  ldloc.s  5
0xd344  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd349  brtrue.s loc_D359
0xd34b  ldarg.0
0xd34c  ldarg.1
0xd34d  ldloc.s  5
0xd34f  callvirt instance valuetype [mscorlib]System.DateTime [System.Data]System.Data.IDataRecord::GetDateTime(int32)
0xd354  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_LastRunTime(valuetype [mscorlib]System.DateTime value)
0xd359  ldarg.1
0xd35a  ldloc.s  0x11
0xd35c  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd361  brtrue.s loc_D372
0xd363  ldarg.0
0xd364  ldarg.1
0xd365  ldloc.s  0x11
0xd367  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd36c  conv.i8
0xd36d  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_MaxRunTime(int64 value)
0xd372  ldarg.0
0xd373  ldarg.1
0xd374  ldloc.s  0x12
0xd376  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd37b  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_EventType(string value)
0xd380  ldarg.1
0xd381  ldloc.s  0x13
0xd383  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd388  brtrue.s loc_D398
0xd38a  ldarg.0
0xd38b  ldarg.1
0xd38c  ldloc.s  0x13
0xd38e  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd393  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_EventData(string value)
0xd398  ldarg.1
0xd399  ldloc.s  0x15
0xd39b  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd3a0  brtrue.s loc_D3B5
0xd3a2  ldarg.0
0xd3a3  ldarg.1
0xd3a4  ldloc.s  0x15
0xd3a6  callvirt instance string [System.Data]System.Data.IDataRecord::GetString(int32)
0xd3ab  newobj   instance void [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath::.ctor(string)
0xd3b0  call     instance void Microsoft.ReportingServices.Diagnostics.Task::set_Path(class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.CatalogItemPath value)
0xd3b5  ldc.i4.1
0xd3b6  stloc.s  0x1A
0xd3b8  ldarg.1
0xd3b9  ldloc.s  7
0xd3bb  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd3c0  brtrue.s loc_D3CC
0xd3c2  ldarg.1
0xd3c3  ldloc.s  7
0xd3c5  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd3ca  stloc.s  0x1A
0xd3cc  ldc.i4.0
0xd3cd  conv.i8
0xd3ce  stloc.s  0x1B
0xd3d0  ldc.i4.0
0xd3d1  stloc.s  0x1C
0xd3d3  ldc.i4.0
0xd3d4  stloc.s  0x1D
0xd3d6  ldc.i4.0
0xd3d7  stloc.s  0x1E
0xd3d9  ldloc.s  0x1A
0xd3db  ldc.i4.2
0xd3dc  sub
0xd3dd  switch   loc_D41D, loc_D3FB, loc_D442, loc_D478, loc_D4AD
0xd3f6  br       loc_D4F6
0xd3fb  ldarg.1
0xd3fc  ldloc.s  9
0xd3fe  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd403  brtrue   loc_D4F6
0xd408  ldloc.s  0x19
0xd40a  ldarg.1
0xd40b  ldloc.s  9
0xd40d  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd412  conv.i8
0xd413  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToDaily(int64 daysInterval)
0xd418  br       loc_D4F6
0xd41d  ldc.i4.0
0xd41e  stloc.s  0x1F
0xd420  ldarg.1
0xd421  ldloc.s  8
0xd423  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd428  brtrue.s loc_D434
0xd42a  ldarg.1
0xd42b  ldloc.s  8
0xd42d  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd432  stloc.s  0x1F
0xd434  ldloc.s  0x19
0xd436  ldloc.s  0x1F
0xd438  callvirt instance void Microsoft.ReportingServices.Diagnostics.TaskTrigger::SetToMinutes(int32 minutesInterval)
0xd43d  br       loc_D4F6
0xd442  ldarg.1
0xd443  ldloc.s  0xA
0xd445  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd44a  brtrue.s loc_D457
0xd44c  ldarg.1
0xd44d  ldloc.s  0xA
0xd44f  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd454  conv.i8
0xd455  stloc.s  0x1B
0xd457  ldarg.1
0xd458  ldloc.s  0xB
0xd45a  callvirt instance bool [System.Data]System.Data.IDataRecord::IsDBNull(int32)
0xd45f  brtrue.s loc_D46B
0xd461  ldarg.1
0xd462  ldloc.s  0xB
0xd464  callvirt instance int32 [System.Data]System.Data.IDataRecord::GetInt32(int32)
0xd469  stloc.s  0x1C
0xd46b  ldloc.s  0x19
0xd46d  ldloc.s  0x1B
  ... truncated ...
```
