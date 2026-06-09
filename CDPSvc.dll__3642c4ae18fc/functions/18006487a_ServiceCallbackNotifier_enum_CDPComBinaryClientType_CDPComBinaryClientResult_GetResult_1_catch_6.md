# _ServiceCallbackNotifier_enum_CDPComBinaryClientType_CDPComBinaryClientResult_::GetResult_::_1_::catch$6

- ea: `0x18006487a`
- end: `0x1800648ca`
- name: `_ServiceCallbackNotifier_enum_CDPComBinaryClientType_CDPComBinaryClientResult_::GetResult_::_1_::catch$6`
- size: `80`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002781c`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180064887`

## string_xrefs

- `0x1800648a5`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to get result in service callback notifier."}`

## pseudocode

```c
void __fastcall __noreturn ServiceCallbackNotifier_enum_CDPComBinaryClientType_CDPComBinaryClientResult_::GetResult_::_1_::catch_6(
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
0x18006487a  mov     [rsp+arg_8], rdx
0x18006487f  push    rbp
0x180064880  sub     rsp, 30h
0x180064884  mov     rbp, rdx
0x180064887  call    cs:__imp_GetCurrentThreadId
0x18006488d  mov     [rbp+38h], rax
0x180064891  mov     dword ptr [rbp+30h], 45h ; 'E'
0x180064898  lea     rax, [rbp+38h]
0x18006489c  mov     [rsp+38h+var_18], rax
0x1800648a1  lea     r9, [rbp+30h]
0x1800648a5  lea     rdx, aHr0x08xExcepti_0; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x1800648ac  lea     rcx, [rbp+88h]
0x1800648b3  call    ??$CatchAllToHR@AEAY0EA@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0EA@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[64],int,unsigned __int64>(long &,char const *,char const (&)[64],int &&,unsigned __int64 &&)
0x1800648b9  mov     rax, 0
0x1800648c3  add     rsp, 30h
0x1800648c7  pop     rbp
0x1800648c8  retn
```
