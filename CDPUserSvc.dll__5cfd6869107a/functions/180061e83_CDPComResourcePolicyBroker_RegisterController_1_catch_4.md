# _CDPComResourcePolicyBroker::RegisterController_::_1_::catch$4

- ea: `0x180061e83`
- end: `0x180061ed7`
- name: `_CDPComResourcePolicyBroker::RegisterController_::_1_::catch$4`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061e90`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180061e90`

## string_xrefs

- `0x180061eae`: `..\cdpcomresourcepolicybroker.cpp`
- `0x180061eb5`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to register controller."}`

## pseudocode

```c
void __fastcall __noreturn CDPComResourcePolicyBroker::RegisterController_::_1_::catch_4(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 56) = v3;
  *(_DWORD *)(a2 + 64) = 37;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 48,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to register controller.\"}",
    (__int64)"..\\cdpcomresourcepolicybroker.cpp",
    a2 + 64,
    a2 + 56);
}

```

## disassembly

```asm
0x180061e83  mov     [rsp+arg_8], rdx
0x180061e88  push    rbp
0x180061e89  sub     rsp, 30h
0x180061e8d  mov     rbp, rdx
0x180061e90  call    cs:__imp_GetCurrentThreadId
0x180061e96  mov     [rbp+38h], rax
0x180061e9a  mov     dword ptr [rbp+40h], 25h ; '%'
0x180061ea1  lea     rax, [rbp+38h]
0x180061ea5  mov     [rsp+38h+var_18], rax
0x180061eaa  lea     r9, [rbp+40h]
0x180061eae  lea     r8, aCdpcomresource; "..\\cdpcomresourcepolicybroker.cpp"
0x180061eb5  lea     rdx, aHr0x08xExcepti_10; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180061ebc  lea     rcx, [rbp+30h]
0x180061ec0  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180061ec6  mov     rax, 0
0x180061ed0  add     rsp, 30h
0x180061ed4  pop     rbp
0x180061ed5  retn
```
