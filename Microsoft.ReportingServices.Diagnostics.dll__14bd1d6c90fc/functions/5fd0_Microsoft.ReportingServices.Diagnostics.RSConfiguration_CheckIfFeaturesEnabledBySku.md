# Microsoft.ReportingServices.Diagnostics.RSConfiguration::CheckIfFeaturesEnabledBySku

- ea: `0x5fd0`
- end: `0x6162`
- name: `Microsoft.ReportingServices.Diagnostics.RSConfiguration::CheckIfFeaturesEnabledBySku`
- size: `402`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x4170`

## callees

- `0x33c0`
- `0x5fd0`
- `0xc810`

## string_xrefs

- `0x6122`: `RDCE is not supported on this edition of Reporting Services and has been disabled.`
- `0x6150`: `Pinning report items to PowerBI is not supported on this edition of Reporting Services and has been disabled.`

## pseudocode

```c

```

## disassembly

```asm
0x5fd0  ldarg.0
0x5fd1  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isSchedulingService
0x5fd6  brfalse.s loc_601D
0x5fd8  ldarg.0
0x5fd9  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x5fde  ldc.i4.7
0x5fdf  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0x5fe4  brtrue.s loc_601D
0x5fe6  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5feb  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x5ff0  brfalse.s loc_6016
0x5ff2  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x5ff7  ldc.i4.2
0x5ff8  ldstr    aRestrictedFeat// "Restricted feature: "
0x5ffd  ldc.i4.7
0x5ffe  stloc.0
0x5fff  ldloca.s 0
0x6001  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0x6007  callvirt instance string [mscorlib]System.Object::ToString()
0x600c  call     string [mscorlib]System.String::Concat(string, string)
0x6011  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6016  ldarg.0
0x6017  ldc.i4.0
0x6018  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isSchedulingService
0x601d  ldarg.0
0x601e  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isAlertingService
0x6023  brfalse.s loc_606C
0x6025  ldarg.0
0x6026  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x602b  ldc.i4.s 0x17
0x602d  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0x6032  brtrue.s loc_606C
0x6034  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6039  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x603e  brfalse.s loc_6065
0x6040  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6045  ldc.i4.2
0x6046  ldstr    aRestrictedFeat// "Restricted feature: "
0x604b  ldc.i4.s 0x17
0x604d  stloc.0
0x604e  ldloca.s 0
0x6050  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0x6056  callvirt instance string [mscorlib]System.Object::ToString()
0x605b  call     string [mscorlib]System.String::Concat(string, string)
0x6060  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x6065  ldarg.0
0x6066  ldc.i4.0
0x6067  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isAlertingService
0x606c  ldarg.0
0x606d  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isNotificationService
0x6072  brfalse.s loc_60B9
0x6074  ldarg.0
0x6075  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x607a  ldc.i4.6
0x607b  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0x6080  brtrue.s loc_60B9
0x6082  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6087  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x608c  brfalse.s loc_60B2
0x608e  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6093  ldc.i4.2
0x6094  ldstr    aRestrictedFeat// "Restricted feature: "
0x6099  ldc.i4.6
0x609a  stloc.0
0x609b  ldloca.s 0
0x609d  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0x60a3  callvirt instance string [mscorlib]System.Object::ToString()
0x60a8  call     string [mscorlib]System.String::Concat(string, string)
0x60ad  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x60b2  ldarg.0
0x60b3  ldc.i4.0
0x60b4  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isNotificationService
0x60b9  ldarg.0
0x60ba  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isEventService
0x60bf  brfalse.s loc_6106
0x60c1  ldarg.0
0x60c2  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x60c7  ldc.i4.7
0x60c8  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0x60cd  brtrue.s loc_6106
0x60cf  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x60d4  callvirt instance bool [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_TraceWarning()
0x60d9  brfalse.s loc_60FF
0x60db  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x60e0  ldc.i4.2
0x60e1  ldstr    aRestrictedFeat// "Restricted feature: "
0x60e6  ldc.i4.7
0x60e7  stloc.0
0x60e8  ldloca.s 0
0x60ea  constrained. [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures
0x60f0  callvirt instance string [mscorlib]System.Object::ToString()
0x60f5  call     string [mscorlib]System.String::Concat(string, string)
0x60fa  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x60ff  ldarg.0
0x6100  ldc.i4.0
0x6101  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isEventService
0x6106  ldarg.0
0x6107  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isRdceEnabled
0x610c  brfalse.s loc_6133
0x610e  ldarg.0
0x610f  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x6114  ldc.i4.8
0x6115  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0x611a  brtrue.s loc_6133
0x611c  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x6121  ldc.i4.2
0x6122  ldstr    aRdceIsNotSuppo// "RDCE is not supported on this edition o"...
0x6127  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x612c  ldarg.0
0x612d  ldc.i4.0
0x612e  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_isRdceEnabled
0x6133  ldarg.0
0x6134  ldfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_enablePowerBIFeatures
0x6139  brfalse.s loc_6161
0x613b  ldarg.0
0x613c  callvirt instance string Microsoft.ReportingServices.Diagnostics.RSBaseConfiguration::get_InstanceID()
0x6141  ldc.i4.s 0x1B
0x6143  call     bool Microsoft.ReportingServices.Diagnostics.Sku::IsFeatureEnabled(string instanceId, valuetype [Microsoft.ReportingServices.Editions]Microsoft.ReportingServices.Diagnostics.RestrictedFeatures feature)
0x6148  brtrue.s loc_6161
0x614a  call     class [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::get_ConfigManagerTracer()
0x614f  ldc.i4.2
0x6150  ldstr    aPinningReportI// "Pinning report items to PowerBI is not "...
0x6155  callvirt instance void [Microsoft.ReportingServices.Exceptions]Microsoft.ReportingServices.Diagnostics.Utilities.RSTrace::Trace(valuetype [System]System.Diagnostics.TraceLevel, string)
0x615a  ldarg.0
0x615b  ldc.i4.0
0x615c  stfld    bool Microsoft.ReportingServices.Diagnostics.RSConfiguration::m_enablePowerBIFeatures
0x6161  ret
```
