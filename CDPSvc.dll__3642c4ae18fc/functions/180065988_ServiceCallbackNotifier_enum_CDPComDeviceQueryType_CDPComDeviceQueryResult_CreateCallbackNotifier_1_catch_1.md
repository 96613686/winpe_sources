# _ServiceCallbackNotifier_enum_CDPComDeviceQueryType_CDPComDeviceQueryResult_::CreateCallbackNotifier_::_1_::catch$1

- ea: `0x180065988`
- end: `0x1800659d5`
- name: `_ServiceCallbackNotifier_enum_CDPComDeviceQueryType_CDPComDeviceQueryResult_::CreateCallbackNotifier_::_1_::catch$1`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002781c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065995`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180065995`

## string_xrefs

- `0x1800659b3`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to start callback notifier!"}`

## pseudocode

```c
void __fastcall __noreturn ServiceCallbackNotifier_enum_CDPComDeviceQueryType_CDPComDeviceQueryResult_::CreateCallbackNotifier_::_1_::catch_1(
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
0x180065988  mov     [rsp+arg_8], rdx
0x18006598d  push    rbp
0x18006598e  sub     rsp, 30h
0x180065992  mov     rbp, rdx
0x180065995  call    cs:__imp_GetCurrentThreadId
0x18006599b  mov     [rbp+38h], rax
0x18006599f  mov     dword ptr [rbp+34h], 5Ch ; '\'
0x1800659a6  lea     rax, [rbp+38h]
0x1800659aa  mov     [rsp+38h+var_18], rax
0x1800659af  lea     r9, [rbp+34h]
0x1800659b3  lea     rdx, aHr0x08xExcepti_4; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x1800659ba  lea     rcx, [rbp+30h]
0x1800659be  call    ??$CatchAllToHR@AEAY0EA@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0EA@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(long &,char const *,char const (&)[64],int &&,unsigned __int64 &&)
0x1800659c4  mov     rax, 0
0x1800659ce  add     rsp, 30h
0x1800659d2  pop     rbp
0x1800659d3  retn
```
