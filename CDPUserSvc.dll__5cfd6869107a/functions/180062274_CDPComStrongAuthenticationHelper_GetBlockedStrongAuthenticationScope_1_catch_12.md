# _CDPComStrongAuthenticationHelper::GetBlockedStrongAuthenticationScope_::_1_::catch$12

- ea: `0x180062274`
- end: `0x1800622d4`
- name: `_CDPComStrongAuthenticationHelper::GetBlockedStrongAuthenticationScope_::_1_::catch$12`
- size: `96`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `broker_com_uri`

## callees

- `0x18003ec20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062288`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180062288`

## string_xrefs

- `0x1800622ad`: `{"hr":"0x%08x","exception_text":"%s","file":"%s","line":%d,"thread":"%zu","text":"Error"}`
- `0x1800622a6`: `..\cdpcomstrongauthenticationhelper.cpp`

## pseudocode

```c
void __fastcall __noreturn CDPComStrongAuthenticationHelper::GetBlockedStrongAuthenticationScope_::_1_::catch_12(
        __int64 a1,
        __int64 a2)
{
  __int64 v3; // rax

  *(_DWORD *)(a2 + 48) = -2147418113;
  LODWORD(v3) = GetCurrentThreadId();
  *(_QWORD *)(a2 + 56) = v3;
  *(_DWORD *)(a2 + 52) = 109;
  cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(
    a2 + 48,
    (__int64)"{\"hr\":\"0x%08x\",\"exception_text\":\"%s\",\"file\":\"%s\",\"line\":%d,\"thread\":\"%zu\",\"text\":\"Error\"}",
    (__int64)"..\\cdpcomstrongauthenticationhelper.cpp",
    a2 + 52,
    a2 + 56);
}

```

## disassembly

```asm
0x180062274  mov     [rsp+arg_8], rdx
0x180062279  push    rbp
0x18006227a  sub     rsp, 30h
0x18006227e  mov     rbp, rdx
0x180062281  mov     dword ptr [rbp+30h], 8000FFFFh
0x180062288  call    cs:__imp_GetCurrentThreadId
0x18006228e  mov     [rbp+38h], rax
0x180062292  mov     dword ptr [rbp+34h], 6Dh ; 'm'
0x180062299  lea     rax, [rbp+38h]
0x18006229d  mov     [rsp+38h+var_18], rax
0x1800622a2  lea     r9, [rbp+34h]
0x1800622a6  lea     r8, aCdpcomstrongau; "..\\cdpcomstrongauthenticationhelper.cp"...
0x1800622ad  lea     rdx, aHr0x08xExcepti_3; "{\"hr\":\"0x%08x\",\"exception_text\":"...
0x1800622b4  lea     rcx, [rbp+30h]
0x1800622b8  call    ??$CatchAllToHR@AEAY0CC@$$CBDH_K@cdp@@YAXAEAJPEBDAEAY0CC@$$CBD$$QEAH$$QEA_K@Z; cdp::CatchAllToHR<char const (&)[34],int,unsigned __int64>(long &,char const *,char const (&)[34],int &&,unsigned __int64 &&)
0x1800622bd  mov     eax, [rbp+30h]
0x1800622c0  mov     [rbp+34h], eax
0x1800622c3  mov     rax, 0
0x1800622cd  add     rsp, 30h
0x1800622d1  pop     rbp
0x1800622d2  retn
```
