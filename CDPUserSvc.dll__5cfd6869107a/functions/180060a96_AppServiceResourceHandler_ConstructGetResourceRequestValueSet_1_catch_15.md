# _AppServiceResourceHandler::ConstructGetResourceRequestValueSet_::_1_::catch$15

- ea: `0x180060a96`
- end: `0x180060aea`
- name: `_AppServiceResourceHandler::ConstructGetResourceRequestValueSet_::_1_::catch$15`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060aa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060aa3`

## string_xrefs

- `0x180060ac8`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to construct valueset for get-resource request or storing it in the out param."}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::ConstructGetResourceRequestValueSet_::_1_::catch_15(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 64) = v3;
  *(_DWORD *)(a2 + 48) = 269;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 56,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to construct valueset for get-resource request or storing it in the out param.\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 48,
    a2 + 64);
}

```

## disassembly

```asm
0x180060a96  mov     [rsp+arg_8], rdx
0x180060a9b  push    rbp
0x180060a9c  sub     rsp, 30h
0x180060aa0  mov     rbp, rdx
0x180060aa3  call    cs:__imp_GetCurrentThreadId
0x180060aa9  mov     [rbp+40h], rax
0x180060aad  mov     dword ptr [rbp+30h], 10Dh
0x180060ab4  lea     rax, [rbp+40h]
0x180060ab8  mov     [rsp+38h+var_18], rax
0x180060abd  lea     r9, [rbp+30h]
0x180060ac1  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180060ac8  lea     rdx, aHr0x08xExcepti; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180060acf  lea     rcx, [rbp+38h]
0x180060ad3  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180060ad9  mov     rax, 0
0x180060ae3  add     rsp, 30h
0x180060ae7  pop     rbp
0x180060ae8  retn
```
