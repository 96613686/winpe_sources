# _AppServiceResourceHandler::GetResourceValFromResponseValueSet_::_1_::catch$7

- ea: `0x180060b5c`
- end: `0x180060bb0`
- name: `_AppServiceResourceHandler::GetResourceValFromResponseValueSet_::_1_::catch$7`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060b69`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060b69`

## string_xrefs

- `0x180060b8e`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to get the resource value from the response valueset."}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::GetResourceValFromResponseValueSet_::_1_::catch_7(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 64) = v3;
  *(_DWORD *)(a2 + 56) = 309;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 48,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to get the resource value from the response valueset.\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 56,
    a2 + 64);
}

```

## disassembly

```asm
0x180060b5c  mov     [rsp+arg_8], rdx
0x180060b61  push    rbp
0x180060b62  sub     rsp, 30h
0x180060b66  mov     rbp, rdx
0x180060b69  call    cs:__imp_GetCurrentThreadId
0x180060b6f  mov     [rbp+40h], rax
0x180060b73  mov     dword ptr [rbp+38h], 135h
0x180060b7a  lea     rax, [rbp+40h]
0x180060b7e  mov     [rsp+38h+var_18], rax
0x180060b83  lea     r9, [rbp+38h]
0x180060b87  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180060b8e  lea     rdx, aHr0x08xExcepti_13; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180060b95  lea     rcx, [rbp+30h]
0x180060b99  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180060b9f  mov     rax, 0
0x180060ba9  add     rsp, 30h
0x180060bad  pop     rbp
0x180060bae  retn
```
