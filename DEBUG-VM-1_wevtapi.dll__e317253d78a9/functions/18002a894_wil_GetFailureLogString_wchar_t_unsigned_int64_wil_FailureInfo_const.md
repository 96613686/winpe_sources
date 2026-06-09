# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002a894`
- end: `0x18002ab4a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18002b1b8`

## callees

- `0x1800249f0`
- `0x1800254b4`
- `0x18002a894`
- `0x18002b4b4`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a9c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002a9c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002aa47`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
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
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *(_WORD *)this )
        return 0;
    }
  }
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
        else
          v7 = (const char *)&word_18004024A;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
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
0x18002a894  mov     [rsp+arg_18], rbx
0x18002a899  push    rbp
0x18002a89a  push    rsi
0x18002a89b  push    rdi
0x18002a89c  push    r14
0x18002a89e  push    r15
0x18002a8a0  sub     rsp, 250h
0x18002a8a7  mov     rax, cs:__security_cookie
0x18002a8ae  xor     rax, rsp
0x18002a8b1  mov     [rsp+278h+var_38], rax
0x18002a8b9  mov     rbx, r8
0x18002a8bc  mov     rsi, rdx
0x18002a8bf  mov     r14, rcx
0x18002a8c2  xor     r15d, r15d
0x18002a8c5  test    rdx, rdx
0x18002a8c8  jz      loc_18002AB21
0x18002a8ce  test    rcx, rcx
0x18002a8d1  jz      loc_18002AB21
0x18002a8d7  mov     [rcx], r15w
0x18002a8db  mov     rax, cs:g_pfnResultLoggingCallback
0x18002a8e2  test    rax, rax
0x18002a8e5  jz      short loc_18002A908
0x18002a8e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002a8ee  jz      short loc_18002A908
0x18002a8f0  mov     r8, rdx
0x18002a8f3  mov     rdx, rcx
0x18002a8f6  mov     rcx, rbx
0x18002a8f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a8fe  cmp     [r14], r15w
0x18002a902  jnz     loc_18002AB21
0x18002a908  mov     ecx, [rbx]
0x18002a90a  mov     bpl, 8
0x18002a90d  test    ecx, ecx
0x18002a90f  jz      short loc_18002A95A
0x18002a911  sub     ecx, 1
0x18002a914  jz      short loc_18002A942
0x18002a916  sub     ecx, 1
0x18002a919  jz      short loc_18002A932
0x18002a91b  cmp     ecx, 1
0x18002a91e  jz      short loc_18002A929
0x18002a920  lea     rdi, word_18004024A
0x18002a927  jmp     short loc_18002A961
0x18002a929  lea     rdi, aFailfast; "FailFast"
0x18002a930  jmp     short loc_18002A961
0x18002a932  lea     rax, aLoghr; "LogHr"
0x18002a939  lea     rdi, aLognt; "LogNt"
0x18002a940  jmp     short loc_18002A950
0x18002a942  lea     rax, aReturnhr; "ReturnHr"
0x18002a949  lea     rdi, aReturnnt; "ReturnNt"
0x18002a950  test    [rbx+4], bpl
0x18002a954  cmovz   rdi, rax
0x18002a958  jmp     short loc_18002A961
0x18002a95a  lea     rdi, aException; "Exception"
0x18002a961  xor     edx, edx; Val
0x18002a963  mov     r8d, 200h; Size
0x18002a969  lea     rcx, [rsp+278h+Buffer]; void *
0x18002a96e  call    memset_0
0x18002a973  test    [rbx+4], bpl
0x18002a977  jz      short loc_18002A99C
0x18002a979  mov     ebp, [rbx+0Ch]
0x18002a97c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18002a983  test    rax, rax
0x18002a986  jz      short loc_18002A9CC
0x18002a988  mov     r8d, 100h
0x18002a98e  lea     rdx, [rsp+278h+Buffer]
0x18002a993  mov     ecx, ebp
0x18002a995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a99a  jmp     short loc_18002A9CC
0x18002a99c  mov     ebp, [rbx+8]
0x18002a99f  mov     [rsp+278h+Arguments], r15; Arguments
0x18002a9a4  mov     [rsp+278h+nSize], 100h; nSize
0x18002a9ac  lea     rax, [rsp+278h+Buffer]
0x18002a9b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002a9b6  mov     r9d, 400h; dwLanguageId
0x18002a9bc  mov     r8d, ebp; dwMessageId
0x18002a9bf  xor     edx, edx; lpSource
0x18002a9c1  mov     ecx, 1200h; dwFlags
0x18002a9c6  call    cs:__imp_FormatMessageW
0x18002a9cc  lea     rsi, [r14+rsi*2]
0x18002a9d0  mov     r9, [rbx+38h]; wchar_t *
0x18002a9d4  mov     rax, [rbx+88h]
0x18002a9db  mov     rcx, [rbx+80h]
0x18002a9e2  mov     rdx, rsi; wchar_t *
0x18002a9e5  test    r9, r9
0x18002a9e8  jz      short loc_18002AA0C
0x18002a9ea  mov     [rsp+278h+Arguments], rax
0x18002a9ef  mov     qword ptr [rsp+278h+nSize], rcx
0x18002a9f4  mov     eax, [rbx+40h]
0x18002a9f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002a9fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002aa02  mov     rcx, r14; this
0x18002aa05  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aa0a  jmp     short loc_18002AA23
0x18002aa0c  mov     [rsp+278h+lpBuffer], rax
0x18002aa11  mov     r9, rcx; wchar_t *
0x18002aa14  lea     r8, aHsP; "%hs!%p: "
0x18002aa1b  mov     rcx, r14; this
0x18002aa1e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aa23  mov     r14, rax
0x18002aa26  mov     r9, [rbx+90h]; wchar_t *
0x18002aa2d  test    r9, r9
0x18002aa30  jz      short loc_18002AA47
0x18002aa32  lea     r8, aCallerP; "(caller: %p) "
0x18002aa39  mov     rdx, rsi; wchar_t *
0x18002aa3c  mov     rcx, rax; this
0x18002aa3f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aa44  mov     r14, rax
0x18002aa47  call    cs:__imp_GetCurrentThreadId
0x18002aa4d  lea     rcx, [rsp+278h+Buffer]
0x18002aa52  mov     [rsp+278h+var_240], rcx
0x18002aa57  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002aa5b  mov     [rsp+278h+nSize], eax
0x18002aa5f  mov     eax, [rbx+44h]
0x18002aa62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002aa66  mov     r9, rdi; wchar_t *
0x18002aa69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002aa70  mov     rdx, rsi; wchar_t *
0x18002aa73  mov     rcx, r14; this
0x18002aa76  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aa7b  cmp     [rbx+18h], r15
0x18002aa7f  jnz     short loc_18002AA91
0x18002aa81  cmp     [rbx+48h], r15
0x18002aa85  jnz     short loc_18002AA91
0x18002aa87  cmp     [rbx+30h], r15
0x18002aa8b  jz      loc_18002AB21
0x18002aa91  lea     r8, asc_180041648; "    "
0x18002aa98  mov     rdx, rsi; wchar_t *
0x18002aa9b  mov     rcx, rax; this
0x18002aa9e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aaa3  mov     r9, [rbx+18h]; wchar_t *
0x18002aaa7  test    r9, r9
0x18002aaaa  jz      short loc_18002AABE
0x18002aaac  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002aab3  mov     rdx, rsi; wchar_t *
0x18002aab6  mov     rcx, rax; this
0x18002aab9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aabe  mov     r9, [rbx+48h]; wchar_t *
0x18002aac2  test    r9, r9
0x18002aac5  jz      short loc_18002AAD9
0x18002aac7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002aace  mov     rdx, rsi; wchar_t *
0x18002aad1  mov     rcx, rax; this
0x18002aad4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aad9  mov     rcx, [rbx+28h]
0x18002aadd  mov     r9, [rbx+30h]; wchar_t *
0x18002aae1  mov     rdx, rsi; wchar_t *
0x18002aae4  test    rcx, rcx
0x18002aae7  jz      short loc_18002AAFF
0x18002aae9  mov     [rsp+278h+lpBuffer], rcx
0x18002aaee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002aaf5  mov     rcx, rax; this
0x18002aaf8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002aafd  jmp     short loc_18002AB21
0x18002aaff  mov     rcx, rax; this
0x18002ab02  test    r9, r9
0x18002ab05  jz      short loc_18002AB15
0x18002ab07  lea     r8, aHs; "[%hs]\n"
0x18002ab0e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab13  jmp     short loc_18002AB21
0x18002ab15  lea     r8, asc_1800416C0; "\n"
0x18002ab1c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18002ab21  xor     eax, eax
0x18002ab23  mov     rcx, [rsp+278h+var_38]
0x18002ab2b  xor     rcx, rsp; StackCookie
0x18002ab2e  call    __security_check_cookie
0x18002ab33  mov     rbx, [rsp+278h+arg_18]
0x18002ab3b  add     rsp, 250h
0x18002ab42  pop     r15
0x18002ab44  pop     r14
0x18002ab46  pop     rdi
0x18002ab47  pop     rsi
0x18002ab48  pop     rbp
0x18002ab49  retn
```
