# _CDPComStrongAuthenticationHelper::RuntimeClassInitialize_::_1_::catch$3

- ea: `0x180062310`
- end: `0x18006237c`
- name: `_CDPComStrongAuthenticationHelper::RuntimeClassInitialize_::_1_::catch$3`
- size: `108`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062324`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062324`

## string_xrefs

- `0x180062355`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Error"}`
- `0x18006234e`: `..\cdpcomstrongauthenticationhelper.cpp`

## pseudocode

```c
void __fastcall __noreturn CDPComStrongAuthenticationHelper::RuntimeClassInitialize_::_1_::catch_3(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax

  *(_DWORD *)(a2 + 120) = -2147418113;
  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 136) = v3;
  *(_DWORD *)(a2 + 128) = 68;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 120,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
    (__int64)"..\\cdpcomstrongauthenticationhelper.cpp",
    a2 + 128,
    a2 + 136);
}

```

## disassembly

```asm
0x180062310  mov     [rsp+arg_8], rdx
0x180062315  push    rbp
0x180062316  sub     rsp, 30h
0x18006231a  mov     rbp, rdx
0x18006231d  mov     dword ptr [rbp+78h], 8000FFFFh
0x180062324  call    cs:__imp_GetCurrentThreadId
0x18006232a  mov     [rbp+88h], rax
0x180062331  mov     dword ptr [rbp+80h], 44h ; 'D'
0x18006233b  lea     rax, [rbp+88h]
0x180062342  mov     [rsp+38h+var_18], rax
0x180062347  lea     r9, [rbp+80h]
0x18006234e  lea     r8, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x180062355  lea     rdx, aHr0x08xExcepti_3; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x18006235c  lea     rcx, [rbp+78h]
0x180062360  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x180062365  mov     eax, [rbp+78h]
0x180062368  mov     [rbp+78h], eax
0x18006236b  mov     rax, 0
0x180062375  add     rsp, 30h
0x180062379  pop     rbp
0x18006237a  retn
```
