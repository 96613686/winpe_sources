# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006bec`
- end: `0x180006ea0`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800061d0`
- `0x180006560`
- `0x180006ea8`
- `0x1800072b0`
- `0x1800086a0`
- `0x180016347`
- `0x180016480`

## callees

- `0x180006b80`
- `0x180006bec`
- `0x18000ed40`
- `0x180015430`
- `0x1800154b0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d9d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d9d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006d1c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006d1c`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&word_180018322;
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v7 = "FailFast";
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v9 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v9, Buffer, 0x100u);
  }
  else
  {
    v9 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v9, 0x400u, Buffer, 0x100u, 0);
  }
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = (wil::details *)v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180006bec  mov     [rsp+arg_18], rbx
0x180006bf1  push    rbp
0x180006bf2  push    rsi
0x180006bf3  push    rdi
0x180006bf4  push    r14
0x180006bf6  push    r15
0x180006bf8  sub     rsp, 250h
0x180006bff  mov     rax, cs:__security_cookie
0x180006c06  xor     rax, rsp
0x180006c09  mov     [rsp+278h+var_38], rax
0x180006c11  mov     rbx, r8
0x180006c14  mov     rdi, rdx
0x180006c17  mov     r14, rcx
0x180006c1a  xor     r15d, r15d
0x180006c1d  test    rdx, rdx
0x180006c20  jz      loc_180006E77
0x180006c26  test    rcx, rcx
0x180006c29  jz      loc_180006E77
0x180006c2f  mov     [rcx], r15w
0x180006c33  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c3a  test    rax, rax
0x180006c3d  jz      short loc_180006C60
0x180006c3f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006c46  jz      short loc_180006C60
0x180006c48  mov     r8, rdx
0x180006c4b  mov     rdx, rcx
0x180006c4e  mov     rcx, rbx
0x180006c51  call    _guard_dispatch_icall
0x180006c56  cmp     [r14], r15w
0x180006c5a  jnz     loc_180006E77
0x180006c60  lea     rsi, word_180018322
0x180006c67  mov     ecx, [rbx]
0x180006c69  mov     bpl, 8
0x180006c6c  test    ecx, ecx
0x180006c6e  jz      short loc_180006CB0
0x180006c70  sub     ecx, 1
0x180006c73  jz      short loc_180006C98
0x180006c75  sub     ecx, 1
0x180006c78  jz      short loc_180006C88
0x180006c7a  cmp     ecx, 1
0x180006c7d  jnz     short loc_180006CB7
0x180006c7f  lea     rsi, aFailfast; "FailFast"
0x180006c86  jmp     short loc_180006CB7
0x180006c88  lea     rax, aLoghr; "LogHr"
0x180006c8f  lea     rsi, aLognt; "LogNt"
0x180006c96  jmp     short loc_180006CA6
0x180006c98  lea     rax, aReturnhr; "ReturnHr"
0x180006c9f  lea     rsi, aReturnnt; "ReturnNt"
0x180006ca6  test    [rbx+4], bpl
0x180006caa  cmovz   rsi, rax
0x180006cae  jmp     short loc_180006CB7
0x180006cb0  lea     rsi, aException; "Exception"
0x180006cb7  xor     edx, edx; Val
0x180006cb9  mov     r8d, 200h; Size
0x180006cbf  lea     rcx, [rsp+278h+Buffer]; void *
0x180006cc4  call    memset
0x180006cc9  test    [rbx+4], bpl
0x180006ccd  jz      short loc_180006CF2
0x180006ccf  mov     ebp, [rbx+0Ch]
0x180006cd2  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180006cd9  test    rax, rax
0x180006cdc  jz      short loc_180006D22
0x180006cde  mov     r8d, 100h
0x180006ce4  lea     rdx, [rsp+278h+Buffer]
0x180006ce9  mov     ecx, ebp
0x180006ceb  call    _guard_dispatch_icall
0x180006cf0  jmp     short loc_180006D22
0x180006cf2  mov     ebp, [rbx+8]
0x180006cf5  mov     [rsp+278h+Arguments], r15; Arguments
0x180006cfa  mov     [rsp+278h+nSize], 100h; nSize
0x180006d02  lea     rax, [rsp+278h+Buffer]
0x180006d07  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006d0c  mov     r9d, 400h; dwLanguageId
0x180006d12  mov     r8d, ebp; dwMessageId
0x180006d15  xor     edx, edx; lpSource
0x180006d17  mov     ecx, 1200h; dwFlags
0x180006d1c  call    cs:__imp_FormatMessageW
0x180006d22  lea     rdi, [r14+rdi*2]
0x180006d26  mov     r9, [rbx+38h]; wchar_t *
0x180006d2a  mov     rax, [rbx+88h]
0x180006d31  mov     rcx, [rbx+80h]
0x180006d38  mov     rdx, rdi; wchar_t *
0x180006d3b  test    r9, r9
0x180006d3e  jz      short loc_180006D62
0x180006d40  mov     [rsp+278h+Arguments], rax
0x180006d45  mov     qword ptr [rsp+278h+nSize], rcx
0x180006d4a  mov     eax, [rbx+40h]
0x180006d4d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d51  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006d58  mov     rcx, r14; this
0x180006d5b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d60  jmp     short loc_180006D79
0x180006d62  mov     [rsp+278h+lpBuffer], rax
0x180006d67  mov     r9, rcx; wchar_t *
0x180006d6a  lea     r8, aHsP; "%hs!%p: "
0x180006d71  mov     rcx, r14; this
0x180006d74  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d79  mov     r14, rax
0x180006d7c  mov     r9, [rbx+90h]; wchar_t *
0x180006d83  test    r9, r9
0x180006d86  jz      short loc_180006D9D
0x180006d88  lea     r8, aCallerP; "(caller: %p) "
0x180006d8f  mov     rdx, rdi; wchar_t *
0x180006d92  mov     rcx, rax; this
0x180006d95  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006d9a  mov     r14, rax
0x180006d9d  call    cs:__imp_GetCurrentThreadId
0x180006da3  lea     rcx, [rsp+278h+Buffer]
0x180006da8  mov     [rsp+278h+var_240], rcx
0x180006dad  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006db1  mov     [rsp+278h+nSize], eax
0x180006db5  mov     eax, [rbx+44h]
0x180006db8  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006dbc  mov     r9, rsi; wchar_t *
0x180006dbf  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006dc6  mov     rdx, rdi; wchar_t *
0x180006dc9  mov     rcx, r14; this
0x180006dcc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006dd1  cmp     [rbx+18h], r15
0x180006dd5  jnz     short loc_180006DE7
0x180006dd7  cmp     [rbx+48h], r15
0x180006ddb  jnz     short loc_180006DE7
0x180006ddd  cmp     [rbx+30h], r15
0x180006de1  jz      loc_180006E77
0x180006de7  lea     r8, asc_1800181D8; "    "
0x180006dee  mov     rdx, rdi; wchar_t *
0x180006df1  mov     rcx, rax; this
0x180006df4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006df9  mov     r9, [rbx+18h]; wchar_t *
0x180006dfd  test    r9, r9
0x180006e00  jz      short loc_180006E14
0x180006e02  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006e09  mov     rdx, rdi; wchar_t *
0x180006e0c  mov     rcx, rax; this
0x180006e0f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006e14  mov     r9, [rbx+48h]; wchar_t *
0x180006e18  test    r9, r9
0x180006e1b  jz      short loc_180006E2F
0x180006e1d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006e24  mov     rdx, rdi; wchar_t *
0x180006e27  mov     rcx, rax; this
0x180006e2a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006e2f  mov     rcx, [rbx+28h]
0x180006e33  mov     r9, [rbx+30h]; wchar_t *
0x180006e37  mov     rdx, rdi; wchar_t *
0x180006e3a  test    rcx, rcx
0x180006e3d  jz      short loc_180006E55
0x180006e3f  mov     [rsp+278h+lpBuffer], rcx
0x180006e44  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006e4b  mov     rcx, rax; this
0x180006e4e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006e53  jmp     short loc_180006E77
0x180006e55  mov     rcx, rax; this
0x180006e58  test    r9, r9
0x180006e5b  jz      short loc_180006E6B
0x180006e5d  lea     r8, aHs; "[%hs]\n"
0x180006e64  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006e69  jmp     short loc_180006E77
0x180006e6b  lea     r8, asc_180018250; "\n"
0x180006e72  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006e77  xor     eax, eax
0x180006e79  mov     rcx, [rsp+278h+var_38]
0x180006e81  xor     rcx, rsp; StackCookie
0x180006e84  call    __security_check_cookie
0x180006e89  mov     rbx, [rsp+278h+arg_18]
0x180006e91  add     rsp, 250h
0x180006e98  pop     r15
0x180006e9a  pop     r14
0x180006e9c  pop     rdi
0x180006e9d  pop     rsi
0x180006e9e  pop     rbp
0x180006e9f  retn
```
