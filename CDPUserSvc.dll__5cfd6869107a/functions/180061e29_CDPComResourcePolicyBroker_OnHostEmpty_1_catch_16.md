# _CDPComResourcePolicyBroker::OnHostEmpty_::_1_::catch$16

- ea: `0x180061e29`
- end: `0x180061e7d`
- name: `_CDPComResourcePolicyBroker::OnHostEmpty_::_1_::catch$16`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061e36`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061e36`

## string_xrefs

- `0x180061e54`: `..\cdpcomresourcepolicybroker.cpp`
- `0x180061e5b`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to cancel app service controller."}`

## pseudocode

```c
void __fastcall __noreturn CDPComResourcePolicyBroker::OnHostEmpty_::_1_::catch_16(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 72) = v3;
  *(_DWORD *)(a2 + 52) = 78;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 64,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to cancel app service controller.\"}",
    (__int64)"..\\cdpcomresourcepolicybroker.cpp",
    a2 + 52,
    a2 + 72);
}

```

## disassembly

```asm
0x180061e29  mov     [rsp+arg_8], rdx
0x180061e2e  push    rbp
0x180061e2f  sub     rsp, 30h
0x180061e33  mov     rbp, rdx
0x180061e36  call    cs:__imp_GetCurrentThreadId
0x180061e3c  mov     [rbp+48h], rax
0x180061e40  mov     dword ptr [rbp+34h], 4Eh ; 'N'
0x180061e47  lea     rax, [rbp+48h]
0x180061e4b  mov     [rsp+38h+var_18], rax
0x180061e50  lea     r9, [rbp+34h]
0x180061e54  lea     r8, aCdpcomresource; "..\\cdpcomresourcepolicybroker.cpp"
0x180061e5b  lea     rdx, aHr0x08xExcepti_8; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180061e62  lea     rcx, [rbp+40h]
0x180061e66  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180061e6c  mov     rax, 0
0x180061e76  add     rsp, 30h
0x180061e7a  pop     rbp
0x180061e7b  retn
```
