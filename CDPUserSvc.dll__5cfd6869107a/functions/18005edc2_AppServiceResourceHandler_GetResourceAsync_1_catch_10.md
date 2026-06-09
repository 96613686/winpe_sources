# _AppServiceResourceHandler::GetResourceAsync_::_1_::catch$10

- ea: `0x18005edc2`
- end: `0x18005ee16`
- name: `_AppServiceResourceHandler::GetResourceAsync_::_1_::catch$10`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005edcf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005edcf`

## string_xrefs

- `0x18005edf4`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed in start async operation to get a resource."}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::GetResourceAsync_::_1_::catch_10(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 72) = v3;
  *(_DWORD *)(a2 + 56) = 112;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 48,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed in start async operation to get a resource.\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 56,
    a2 + 72);
}

```

## disassembly

```asm
0x18005edc2  mov     [rsp+arg_8], rdx
0x18005edc7  push    rbp
0x18005edc8  sub     rsp, 30h
0x18005edcc  mov     rbp, rdx
0x18005edcf  call    cs:__imp_GetCurrentThreadId
0x18005edd5  mov     [rbp+48h], rax
0x18005edd9  mov     dword ptr [rbp+38h], 70h ; 'p'
0x18005ede0  lea     rax, [rbp+48h]
0x18005ede4  mov     [rsp+38h+var_18], rax
0x18005ede9  lea     r9, [rbp+38h]
0x18005eded  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x18005edf4  lea     rdx, aHr0x08xExcepti_2; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005edfb  lea     rcx, [rbp+30h]
0x18005edff  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x18005ee05  mov     rax, 0
0x18005ee0f  add     rsp, 30h
0x18005ee13  pop     rbp
0x18005ee14  retn
```
