# System.Web.Management.WebThreadInformation::FormatToString

- ea: `0x48d50`
- end: `0x48dca`
- name: `System.Web.Management.WebThreadInformation::FormatToString`
- size: `122`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: ``

## callers

- `0x47990`
- `0x47cb0`

## callees

- `0x47000`
- `0x47060`
- `0x471d0`
- `0x48d10`
- `0x48d20`
- `0x48d30`
- `0x48d40`
- `0x48d50`

## string_xrefs

- `0x48d74`: `Webevent_event_thread_account_name`
- `0x48d51`: `Webevent_event_thread_id`
- `0x48d92`: `Webevent_event_is_impersonating`
- `0x48da4`: `Webevent_event_is_not_impersonating`

## pseudocode

```c

```

## disassembly

```asm
0x48d50  ldarg.1
0x48d51  ldstr    aWebeventEventT_5// "Webevent_event_thread_id"
0x48d56  ldarg.0
0x48d57  call     instance int32 System.Web.Management.WebThreadInformation::get_ThreadID()
0x48d5c  stloc.0
0x48d5d  ldloca.s 0
0x48d5f  call     class [mscorlib]System.Globalization.CultureInfo [mscorlib]System.Globalization.CultureInfo::get_InstalledUICulture()
0x48d64  call     instance string [mscorlib]System.Int32::ToString(class [mscorlib]System.IFormatProvider)
0x48d69  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key, string arg0)
0x48d6e  callvirt instance void System.Web.Management.WebEventFormatter::AppendLine(string s)
0x48d73  ldarg.1
0x48d74  ldstr    aWebeventEventT_3// "Webevent_event_thread_account_name"
0x48d79  ldarg.0
0x48d7a  call     instance string System.Web.Management.WebThreadInformation::get_ThreadAccountName()
0x48d7f  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key, string arg0)
0x48d84  callvirt instance void System.Web.Management.WebEventFormatter::AppendLine(string s)
0x48d89  ldarg.0
0x48d8a  call     instance bool System.Web.Management.WebThreadInformation::get_IsImpersonating()
0x48d8f  brfalse.s loc_48DA3
0x48d91  ldarg.1
0x48d92  ldstr    aWebeventEventI_3// "Webevent_event_is_impersonating"
0x48d97  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x48d9c  callvirt instance void System.Web.Management.WebEventFormatter::AppendLine(string s)
0x48da1  br.s     loc_48DB3
0x48da3  ldarg.1
0x48da4  ldstr    aWebeventEventI_4// "Webevent_event_is_not_impersonating"
0x48da9  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key)
0x48dae  callvirt instance void System.Web.Management.WebEventFormatter::AppendLine(string s)
0x48db3  ldarg.1
0x48db4  ldstr    aWebeventEventS_0// "Webevent_event_stack_trace"
0x48db9  ldarg.0
0x48dba  call     instance string System.Web.Management.WebThreadInformation::get_StackTrace()
0x48dbf  call     string System.Web.Management.WebBaseEvent::FormatResourceStringWithCache(string key, string arg0)
0x48dc4  callvirt instance void System.Web.Management.WebEventFormatter::AppendLine(string s)
0x48dc9  ret
```
