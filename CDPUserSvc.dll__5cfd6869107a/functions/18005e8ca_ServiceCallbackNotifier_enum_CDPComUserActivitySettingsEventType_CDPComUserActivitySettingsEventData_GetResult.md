# _ServiceCallbackNotifier_enum_CDPComUserActivitySettingsEventType_CDPComUserActivitySettingsEventData_::GetResult_::_1_::catch$6

- ea: `0x18005e8ca`
- end: `0x18005e91a`
- name: `_ServiceCallbackNotifier_enum_CDPComUserActivitySettingsEventType_CDPComUserActivitySettingsEventData_::GetResult_::_1_::catch$6`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180045320`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e8d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005e8d7`

## string_xrefs

- `0x18005e8f5`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to get result in service callback notifier."}`

## pseudocode

```c
void __fastcall __noreturn ServiceCallbackNotifier_enum_CDPComUserActivitySettingsEventType_CDPComUserActivitySettingsEventData_::GetResult_::_1_::catch_6(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax
  int v4; // r8d

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 56) = v3;
  *(_DWORD *)(a2 + 48) = 69;
  cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(
    a2 + 136,
    (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                  "Failed to get result in service callback notifier.\"}",
    v4,
    a2 + 48,
    a2 + 56);
}

```

## disassembly

```asm
0x18005e8ca  mov     [rsp+arg_8], rdx
0x18005e8cf  push    rbp
0x18005e8d0  sub     rsp, 30h
0x18005e8d4  mov     rbp, rdx
0x18005e8d7  call    cs:__imp_GetCurrentThreadId
0x18005e8dd  mov     [rbp+38h], rax
0x18005e8e1  mov     dword ptr [rbp+30h], 45h ; 'E'
0x18005e8e8  lea     rax, [rbp+38h]
0x18005e8ec  mov     [rsp+38h+var_18], rax
0x18005e8f1  lea     r9, [rbp+30h]
0x18005e8f5  lea     rdx, aHr0x08xExcepti_0; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005e8fc  lea     rcx, [rbp+88h]
0x18005e903  call    ??$CatchAllToHR@AEAY0EA@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0EA@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(long &,char const *,char const (&)[64],int &&,unsigned __int64 &&)
0x18005e909  mov     rax, 0
0x18005e913  add     rsp, 30h
0x18005e917  pop     rbp
0x18005e918  retn
```
