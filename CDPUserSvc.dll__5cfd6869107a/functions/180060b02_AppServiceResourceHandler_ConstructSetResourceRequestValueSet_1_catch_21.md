# _AppServiceResourceHandler::ConstructSetResourceRequestValueSet_::_1_::catch$21

- ea: `0x180060b02`
- end: `0x180060b56`
- name: `_AppServiceResourceHandler::ConstructSetResourceRequestValueSet_::_1_::catch$21`
- size: `84`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060b0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060b0f`

## string_xrefs

- `0x180060b34`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to construct valueset for set-resource request or storing it in the out param."}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::ConstructSetResourceRequestValueSet_::_1_::catch_21(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 56) = v3;
  *(_DWORD *)(a2 + 48) = 293;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 64,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to construct valueset for set-resource request or storing it in the out param.\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 48,
    a2 + 56);
}

```

## disassembly

```asm
0x180060b02  mov     [rsp+arg_8], rdx
0x180060b07  push    rbp
0x180060b08  sub     rsp, 30h
0x180060b0c  mov     rbp, rdx
0x180060b0f  call    cs:__imp_GetCurrentThreadId
0x180060b15  mov     [rbp+38h], rax
0x180060b19  mov     dword ptr [rbp+30h], 125h
0x180060b20  lea     rax, [rbp+38h]
0x180060b24  mov     [rsp+38h+var_18], rax
0x180060b29  lea     r9, [rbp+30h]
0x180060b2d  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180060b34  lea     rdx, aHr0x08xExcepti_11; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180060b3b  lea     rcx, [rbp+40h]
0x180060b3f  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180060b45  mov     rax, 0
0x180060b4f  add     rsp, 30h
0x180060b53  pop     rbp
0x180060b54  retn
```
