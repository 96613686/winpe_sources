# Microsoft.ReportingServices.Diagnostics.Task::WriteScheduleXml

- ea: `0xe8d0`
- end: `0xe9ff`
- name: `Microsoft.ReportingServices.Diagnostics.Task::WriteScheduleXml`
- size: `303`
- prototype: ``
- caller_count: `0`
- callee_count: `12`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0xac70`
- `0xd830`
- `0xd8d0`
- `0xd8f0`
- `0xd910`
- `0xd9b0`
- `0xd9c0`
- `0xda10`
- `0xda90`
- `0xe800`
- `0xe8d0`
- `0xf480`

## string_xrefs

- `0xe902`: `ScheduleDescription`

## pseudocode

```c

```

## disassembly

```asm
0xe8d0  ldarg.1
0xe8d1  ldstr    aSchedule// "Schedule"
0xe8d6  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteStartElement(string)
0xe8db  ldarg.1
0xe8dc  ldstr    aScheduleid// "ScheduleID"
0xe8e1  ldarg.0
0xe8e2  call     instance valuetype [mscorlib]System.Guid Microsoft.ReportingServices.Diagnostics.Task::get_ID()
0xe8e7  stloc.2
0xe8e8  ldloca.s 2
0xe8ea  constrained. [mscorlib]System.Guid
0xe8f0  callvirt instance string [mscorlib]System.Object::ToString()
0xe8f5  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xe8fa  ldarg.0
0xe8fb  ldarg.1
0xe8fc  call     instance void Microsoft.ReportingServices.Diagnostics.Task::WriteDefinitionXml(class [System.Xml]System.Xml.XmlTextWriter writer)
0xe901  ldarg.1
0xe902  ldstr    aScheduledescri// "ScheduleDescription"
0xe907  ldarg.0
0xe908  call     instance class Microsoft.ReportingServices.Diagnostics.TaskTrigger Microsoft.ReportingServices.Diagnostics.Task::get_Trigger()
0xe90d  callvirt instance string Microsoft.ReportingServices.Diagnostics.TaskTrigger::get_ScheduleDescription()
0xe912  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xe917  ldarg.1
0xe918  ldstr    aCreator// "Creator"
0xe91d  ldarg.0
0xe91e  call     instance class [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext Microsoft.ReportingServices.Diagnostics.Task::get_Creator()
0xe923  callvirt instance string [Microsoft.ReportingServices.ProcessingRenderingCommon]Microsoft.ReportingServices.Diagnostics.UserContext::get_UserName()
0xe928  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xe92d  ldstr    asc_126C2// ""
0xe932  stloc.0
0xe933  ldarg.0
0xe934  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::get_NextRunTime()
0xe939  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xe93e  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe943  brfalse.s loc_E94D
0xe945  ldstr    aNever// "Never"
0xe94a  stloc.0
0xe94b  br.s     loc_E959
0xe94d  ldarg.0
0xe94e  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::get_NextRunTime()
0xe953  call     string Microsoft.ReportingServices.Diagnostics.Globals::ToPublicDateTimeFormat(valuetype [mscorlib]System.DateTime date)
0xe958  stloc.0
0xe959  ldarg.1
0xe95a  ldstr    aNextruntime// "NextRunTime"
0xe95f  ldloc.0
0xe960  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xe965  ldarg.0
0xe966  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::get_LastRunTime()
0xe96b  ldsfld   valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::MinValue
0xe970  call     bool [mscorlib]System.DateTime::op_Equality(valuetype [mscorlib]System.DateTime, valuetype [mscorlib]System.DateTime)
0xe975  brfalse.s loc_E97F
0xe977  ldstr    aNever// "Never"
0xe97c  stloc.0
0xe97d  br.s     loc_E98B
0xe97f  ldarg.0
0xe980  call     instance valuetype [mscorlib]System.DateTime Microsoft.ReportingServices.Diagnostics.Task::get_LastRunTime()
0xe985  call     string Microsoft.ReportingServices.Diagnostics.Globals::ToPublicDateTimeFormat(valuetype [mscorlib]System.DateTime date)
0xe98a  stloc.0
0xe98b  ldarg.1
0xe98c  ldstr    aLastruntime// "LastRunTime"
0xe991  ldloc.0
0xe992  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xe997  ldstr    asc_126C2// ""
0xe99c  stloc.1
0xe99d  ldarg.0
0xe99e  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::get_IsFailing()
0xe9a3  brfalse.s loc_E9B3
0xe9a5  ldloc.1
0xe9a6  ldstr    aFailing// "Failing"
0xe9ab  call     string [mscorlib]System.String::Concat(string, string)
0xe9b0  stloc.1
0xe9b1  br.s     loc_E9EC
0xe9b3  ldarg.0
0xe9b4  call     instance bool Microsoft.ReportingServices.Diagnostics.Task::get_IsRunning()
0xe9b9  brfalse.s loc_E9D7
0xe9bb  ldloc.1
0xe9bc  ldc.i4   0x10000000
0xe9c1  stloc.3
0xe9c2  ldloca.s 3
0xe9c4  constrained. Microsoft.ReportingServices.Diagnostics.TaskState
0xe9ca  callvirt instance string [mscorlib]System.Object::ToString()
0xe9cf  call     string [mscorlib]System.String::Concat(string, string)
0xe9d4  stloc.1
0xe9d5  br.s     loc_E9EC
0xe9d7  ldarg.0
0xe9d8  call     instance valuetype Microsoft.ReportingServices.Diagnostics.TaskState Microsoft.ReportingServices.Diagnostics.Task::get_ScheduleState()
0xe9dd  stloc.3
0xe9de  ldloca.s 3
0xe9e0  constrained. Microsoft.ReportingServices.Diagnostics.TaskState
0xe9e6  callvirt instance string [mscorlib]System.Object::ToString()
0xe9eb  stloc.1
0xe9ec  ldarg.1
0xe9ed  ldstr    aState// "State"
0xe9f2  ldloc.1
0xe9f3  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteElementString(string, string)
0xe9f8  ldarg.1
0xe9f9  callvirt instance void [System.Xml]System.Xml.XmlWriter::WriteEndElement()
0xe9fe  ret
```
