# Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetTimeZoneFullName

- ea: `0x9a10`
- end: `0x9a6c`
- name: `Microsoft.ReportingServices.Portal.ODataWebApi.V1.Controllers.UnboundFunctionController::GetTimeZoneFullName`
- size: `92`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callers

- `0x6130`
- `0x97a0`

## callees

- `0x9a10`

## pseudocode

```c

```

## disassembly

```asm
0x9a10  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::get_Local()
0x9a15  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x9a1a  callvirt instance bool [mscorlib]System.TimeZoneInfo::IsDaylightSavingTime(valuetype [mscorlib]System.DateTime)
0x9a1f  brtrue.s loc_9A2D
0x9a21  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::get_Local()
0x9a26  callvirt instance string [mscorlib]System.TimeZoneInfo::get_StandardName()
0x9a2b  br.s     loc_9A37
0x9a2d  call     class [mscorlib]System.TimeZoneInfo [mscorlib]System.TimeZoneInfo::get_Local()
0x9a32  callvirt instance string [mscorlib]System.TimeZoneInfo::get_DaylightName()
0x9a37  stloc.0
0x9a38  call     class [mscorlib]System.TimeZone [mscorlib]System.TimeZone::get_CurrentTimeZone()
0x9a3d  call     valuetype [mscorlib]System.DateTime [mscorlib]System.DateTime::get_Now()
0x9a42  callvirt instance valuetype [mscorlib]System.TimeSpan [mscorlib]System.TimeZone::GetUtcOffset(valuetype [mscorlib]System.DateTime)
0x9a47  stloc.1
0x9a48  ldstr    aUtc00000001002// "(UTC{0:+00;-00;+00}:{1:00}) {2}"
0x9a4d  ldloca.s 1
0x9a4f  call     instance int32 [mscorlib]System.TimeSpan::get_Hours()
0x9a54  box      [mscorlib]System.Int32
0x9a59  ldloca.s 1
0x9a5b  call     instance int32 [mscorlib]System.TimeSpan::get_Minutes()
0x9a60  box      [mscorlib]System.Int32
0x9a65  ldloc.0
0x9a66  call     string [mscorlib]System.String::Format(string, object, object, object)
0x9a6b  ret
```
