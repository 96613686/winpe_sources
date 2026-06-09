# _AppServiceResourceHandler::GetResourceInternal_::_1_::catch$16

- ea: `0x18005f1fd`
- end: `0x18005f25d`
- name: `_AppServiceResourceHandler::GetResourceInternal_::_1_::catch$16`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `loader_planting, service_task`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f211`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005f211`

## string_xrefs

- `0x18005f236`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Error"}`

## pseudocode

```c
void __fastcall __noreturn AppServiceResourceHandler::GetResourceInternal_::_1_::catch_16(__int64 a1, __int64 a2)
{
  __int64 v3; // rax

  *(_DWORD *)(a2 + 64) = -2147418113;
  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 104) = v3;
  *(_DWORD *)(a2 + 72) = 209;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 64,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
    (__int64)"..\\appsvcresourcehandler.cpp",
    a2 + 72,
    a2 + 104);
}

```

## disassembly

```asm
0x18005f1fd  mov     [rsp+arg_8], rdx
0x18005f202  push    rbp
0x18005f203  sub     rsp, 40h
0x18005f207  mov     rbp, rdx
0x18005f20a  mov     dword ptr [rbp+40h], 8000FFFFh
0x18005f211  call    cs:__imp_GetCurrentThreadId
0x18005f217  mov     [rbp+68h], rax
0x18005f21b  mov     dword ptr [rbp+48h], 0D1h
0x18005f222  lea     rax, [rbp+68h]
0x18005f226  mov     [rsp+48h+var_28], rax
0x18005f22b  lea     r9, [rbp+48h]
0x18005f22f  lea     r8, aAppsvcresource; "..\\appsvcresourcehandler.cpp"
0x18005f236  lea     rdx, aHr0x08xExcepti_3; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18005f23d  lea     rcx, [rbp+40h]
0x18005f241  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x18005f246  mov     eax, [rbp+40h]
0x18005f249  mov     [rbp+48h], eax
0x18005f24c  mov     rax, 0
0x18005f256  add     rsp, 40h
0x18005f25a  pop     rbp
0x18005f25b  retn
```
