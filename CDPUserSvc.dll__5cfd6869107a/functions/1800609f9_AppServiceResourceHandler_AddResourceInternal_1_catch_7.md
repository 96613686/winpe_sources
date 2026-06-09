# _AppServiceResourceHandler::AddResourceInternal_::_1_::catch$7

- ea: `0x1800609f9`
- end: `0x180060a56`
- name: `_AppServiceResourceHandler::AddResourceInternal_::_1_::catch$7`
- size: `93`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060a06`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180060a06`

## string_xrefs

- `0x180060a31`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Failed to add a resource."}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::AddResourceInternal_::_1_::catch_7(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 48) = v3;
  *(_DWORD *)(a2 + 168) = 167;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 160,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Fail"
             "ed to add a resource.\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 168,
    a2 + 48);
}

```

## disassembly

```asm
0x1800609f9  mov     [rsp+arg_8], rdx
0x1800609fe  push    rbp
0x1800609ff  sub     rsp, 30h
0x180060a03  mov     rbp, rdx
0x180060a06  call    cs:__imp_GetCurrentThreadId
0x180060a0c  mov     [rbp+30h], rax
0x180060a10  mov     dword ptr [rbp+0A8h], 0A7h
0x180060a1a  lea     rax, [rbp+30h]
0x180060a1e  mov     [rsp+38h+var_18], rax
0x180060a23  lea     r9, [rbp+0A8h]
0x180060a2a  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x180060a31  lea     rdx, aHr0x08xExcepti_6; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x180060a38  lea     rcx, [rbp+0A0h]
0x180060a3f  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180060a45  mov     rax, 0
0x180060a4f  add     rsp, 30h
0x180060a53  pop     rbp
0x180060a54  retn
```
