# _AppServiceResourceHandler::RuntimeClassInitialize_::_1_::catch$13

- ea: `0x18005dfd8`
- end: `0x18005e02c`
- name: `_AppServiceResourceHandler::RuntimeClassInitialize_::_1_::catch$13`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config, loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dfe5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005dfe5`

## string_xrefs

- `0x18005e00a`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to load from config file"}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::RuntimeClassInitialize_::_1_::catch_13(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 96) = v3;
  *(_DWORD *)(a2 + 80) = 54;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 88,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to load from config file\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 80,
    a2 + 96);
}

```

## disassembly

```asm
0x18005dfd8  mov     [rsp+arg_8], rdx
0x18005dfdd  push    rbp
0x18005dfde  sub     rsp, 50h
0x18005dfe2  mov     rbp, rdx
0x18005dfe5  call    cs:__imp_GetCurrentThreadId
0x18005dfeb  mov     [rbp+60h], rax
0x18005dfef  mov     dword ptr [rbp+50h], 36h ; '6'
0x18005dff6  lea     rax, [rbp+60h]
0x18005dffa  mov     [rsp+58h+var_38], rax
0x18005dfff  lea     r9, [rbp+50h]
0x18005e003  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x18005e00a  lea     rdx, aHr0x08xExcepti_1; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005e011  lea     rcx, [rbp+58h]
0x18005e015  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x18005e01b  mov     rax, 0
0x18005e025  add     rsp, 50h
0x18005e029  pop     rbp
0x18005e02a  retn
```
