# _ServiceCallbackNotifier_enum_CDPComDeviceQueryType_CDPComDeviceQueryResult_::GetResult_::_1_::catch$6

- ea: `0x180064130`
- end: `0x180064180`
- name: `_ServiceCallbackNotifier_enum_CDPComDeviceQueryType_CDPComDeviceQueryResult_::GetResult_::_1_::catch$6`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002781c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006413d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006413d`

## string_xrefs

- `0x18006415b`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to get result in service callback notifier."}`

## pseudocode

```c
void __fastcall __noreturn ServiceCallbackNotifier_enum_CDPComDeviceQueryType_CDPComDeviceQueryResult_::GetResult_::_1_::catch_6(
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
0x180064130  mov     [rsp+arg_8], rdx
0x180064135  push    rbp
0x180064136  sub     rsp, 30h
0x18006413a  mov     rbp, rdx
0x18006413d  call    cs:__imp_GetCurrentThreadId
0x180064143  mov     [rbp+38h], rax
0x180064147  mov     dword ptr [rbp+30h], 45h ; 'E'
0x18006414e  lea     rax, [rbp+38h]
0x180064152  mov     [rsp+38h+var_18], rax
0x180064157  lea     r9, [rbp+30h]
0x18006415b  lea     rdx, aHr0x08xExcepti_0; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180064162  lea     rcx, [rbp+88h]
0x180064169  call    ??$CatchAllToHR@AEAY0EA@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0EA@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(long &,char const *,char const (&)[64],int &&,unsigned __int64 &&)
0x18006416f  mov     rax, 0
0x180064179  add     rsp, 30h
0x18006417d  pop     rbp
0x18006417e  retn
```
