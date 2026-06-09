# _ServiceCallbackNotifier_enum_CDPComUserActivitySettingsEventType_CDPComUserActivitySettingsEventData_::CreateCallbackNotifier_::_1_::catch$9

- ea: `0x18005d632`
- end: `0x18005d67f`
- name: `_ServiceCallbackNotifier_enum_CDPComUserActivitySettingsEventType_CDPComUserActivitySettingsEventData_::CreateCallbackNotifier_::_1_::catch$9`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x180045320`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d63f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005d63f`

## string_xrefs

- `0x18005d65d`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to start callback notifier!"}`

## pseudocode

```c
void __fastcall __noreturn ServiceCallbackNotifier_enum_CDPComUserActivitySettingsEventType_CDPComUserActivitySettingsEventData_::CreateCallbackNotifier_::_1_::catch_9(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax
  int v4; // r8d

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 56) = v3;
  *(_DWORD *)(a2 + 52) = 92;
  cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(
    a2 + 48,
    (unsigned int)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\""
                  "Failed to start callback notifier!\"}",
    v4,
    a2 + 52,
    a2 + 56);
}

```

## disassembly

```asm
0x18005d632  mov     [rsp+arg_8], rdx
0x18005d637  push    rbp
0x18005d638  sub     rsp, 30h
0x18005d63c  mov     rbp, rdx
0x18005d63f  call    cs:__imp_GetCurrentThreadId
0x18005d645  mov     [rbp+38h], rax
0x18005d649  mov     dword ptr [rbp+34h], 5Ch ; '\'
0x18005d650  lea     rax, [rbp+38h]
0x18005d654  mov     [rsp+38h+var_18], rax
0x18005d659  lea     r9, [rbp+34h]
0x18005d65d  lea     rdx, aHr0x08xExcepti_4; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005d664  lea     rcx, [rbp+30h]
0x18005d668  call    ??$CatchAllToHR@AEAY0EA@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0EA@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(long &,char const *,char const (&)[64],int &&,unsigned __int64 &&)
0x18005d66e  mov     rax, 0
0x18005d678  add     rsp, 30h
0x18005d67c  pop     rbp
0x18005d67d  retn
```
