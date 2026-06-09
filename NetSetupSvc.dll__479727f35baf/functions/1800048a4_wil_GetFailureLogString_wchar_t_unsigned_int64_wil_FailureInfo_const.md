# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800048a4`
- end: `0x180004b5a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003990`
- `0x1800052a4`
- `0x18000577c`
- `0x180006a70`

## callees

- `0x1800027c0`
- `0x1800032d8`
- `0x1800048a4`
- `0x1800055a4`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a57`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a57`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049d6`

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
          v7 = (const char *)&word_18003647A;
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
0x1800048a4  mov     [rsp+arg_18], rbx
0x1800048a9  push    rbp
0x1800048aa  push    rsi
0x1800048ab  push    rdi
0x1800048ac  push    r14
0x1800048ae  push    r15
0x1800048b0  sub     rsp, 250h
0x1800048b7  mov     rax, cs:__security_cookie
0x1800048be  xor     rax, rsp
0x1800048c1  mov     [rsp+278h+var_38], rax
0x1800048c9  mov     rbx, r8
0x1800048cc  mov     rsi, rdx
0x1800048cf  mov     r14, rcx
0x1800048d2  xor     r15d, r15d
0x1800048d5  test    rdx, rdx
0x1800048d8  jz      loc_180004B31
0x1800048de  test    rcx, rcx
0x1800048e1  jz      loc_180004B31
0x1800048e7  mov     [rcx], r15w
0x1800048eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048f2  test    rax, rax
0x1800048f5  jz      short loc_180004918
0x1800048f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800048fe  jz      short loc_180004918
0x180004900  mov     r8, rdx
0x180004903  mov     rdx, rcx
0x180004906  mov     rcx, rbx
0x180004909  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000490e  cmp     [r14], r15w
0x180004912  jnz     loc_180004B31
0x180004918  mov     ecx, [rbx]
0x18000491a  mov     bpl, 8
0x18000491d  test    ecx, ecx
0x18000491f  jz      short loc_18000496A
0x180004921  sub     ecx, 1
0x180004924  jz      short loc_180004952
0x180004926  sub     ecx, 1
0x180004929  jz      short loc_180004942
0x18000492b  cmp     ecx, 1
0x18000492e  jz      short loc_180004939
0x180004930  lea     rdi, word_18003647A
0x180004937  jmp     short loc_180004971
0x180004939  lea     rdi, aFailfast; "FailFast"
0x180004940  jmp     short loc_180004971
0x180004942  lea     rax, aLoghr; "LogHr"
0x180004949  lea     rdi, aLognt; "LogNt"
0x180004950  jmp     short loc_180004960
0x180004952  lea     rax, aReturnhr; "ReturnHr"
0x180004959  lea     rdi, aReturnnt; "ReturnNt"
0x180004960  test    [rbx+4], bpl
0x180004964  cmovz   rdi, rax
0x180004968  jmp     short loc_180004971
0x18000496a  lea     rdi, aException; "Exception"
0x180004971  xor     edx, edx; Val
0x180004973  mov     r8d, 200h; Size
0x180004979  lea     rcx, [rsp+278h+Buffer]; void *
0x18000497e  call    memset_0
0x180004983  test    [rbx+4], bpl
0x180004987  jz      short loc_1800049AC
0x180004989  mov     ebp, [rbx+0Ch]
0x18000498c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180004993  test    rax, rax
0x180004996  jz      short loc_1800049DC
0x180004998  mov     r8d, 100h
0x18000499e  lea     rdx, [rsp+278h+Buffer]
0x1800049a3  mov     ecx, ebp
0x1800049a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049aa  jmp     short loc_1800049DC
0x1800049ac  mov     ebp, [rbx+8]
0x1800049af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800049b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800049bc  lea     rax, [rsp+278h+Buffer]
0x1800049c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800049c6  mov     r9d, 400h; dwLanguageId
0x1800049cc  mov     r8d, ebp; dwMessageId
0x1800049cf  xor     edx, edx; lpSource
0x1800049d1  mov     ecx, 1200h; dwFlags
0x1800049d6  call    cs:__imp_FormatMessageW
0x1800049dc  lea     rsi, [r14+rsi*2]
0x1800049e0  mov     r9, [rbx+38h]; wchar_t *
0x1800049e4  mov     rax, [rbx+88h]
0x1800049eb  mov     rcx, [rbx+80h]
0x1800049f2  mov     rdx, rsi; wchar_t *
0x1800049f5  test    r9, r9
0x1800049f8  jz      short loc_180004A1C
0x1800049fa  mov     [rsp+278h+Arguments], rax
0x1800049ff  mov     qword ptr [rsp+278h+nSize], rcx
0x180004a04  mov     eax, [rbx+40h]
0x180004a07  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a0b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004a12  mov     rcx, r14; this
0x180004a15  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a1a  jmp     short loc_180004A33
0x180004a1c  mov     [rsp+278h+lpBuffer], rax
0x180004a21  mov     r9, rcx; wchar_t *
0x180004a24  lea     r8, aHsP; "%hs!%p: "
0x180004a2b  mov     rcx, r14; this
0x180004a2e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a33  mov     r14, rax
0x180004a36  mov     r9, [rbx+90h]; wchar_t *
0x180004a3d  test    r9, r9
0x180004a40  jz      short loc_180004A57
0x180004a42  lea     r8, aCallerP; "(caller: %p) "
0x180004a49  mov     rdx, rsi; wchar_t *
0x180004a4c  mov     rcx, rax; this
0x180004a4f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a54  mov     r14, rax
0x180004a57  call    cs:__imp_GetCurrentThreadId
0x180004a5d  lea     rcx, [rsp+278h+Buffer]
0x180004a62  mov     [rsp+278h+var_240], rcx
0x180004a67  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004a6b  mov     [rsp+278h+nSize], eax
0x180004a6f  mov     eax, [rbx+44h]
0x180004a72  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a76  mov     r9, rdi; wchar_t *
0x180004a79  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004a80  mov     rdx, rsi; wchar_t *
0x180004a83  mov     rcx, r14; this
0x180004a86  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004a8b  cmp     [rbx+18h], r15
0x180004a8f  jnz     short loc_180004AA1
0x180004a91  cmp     [rbx+48h], r15
0x180004a95  jnz     short loc_180004AA1
0x180004a97  cmp     [rbx+30h], r15
0x180004a9b  jz      loc_180004B31
0x180004aa1  lea     r8, asc_180036568; "    "
0x180004aa8  mov     rdx, rsi; wchar_t *
0x180004aab  mov     rcx, rax; this
0x180004aae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004ab3  mov     r9, [rbx+18h]; wchar_t *
0x180004ab7  test    r9, r9
0x180004aba  jz      short loc_180004ACE
0x180004abc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004ac3  mov     rdx, rsi; wchar_t *
0x180004ac6  mov     rcx, rax; this
0x180004ac9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004ace  mov     r9, [rbx+48h]; wchar_t *
0x180004ad2  test    r9, r9
0x180004ad5  jz      short loc_180004AE9
0x180004ad7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004ade  mov     rdx, rsi; wchar_t *
0x180004ae1  mov     rcx, rax; this
0x180004ae4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004ae9  mov     rcx, [rbx+28h]
0x180004aed  mov     r9, [rbx+30h]; wchar_t *
0x180004af1  mov     rdx, rsi; wchar_t *
0x180004af4  test    rcx, rcx
0x180004af7  jz      short loc_180004B0F
0x180004af9  mov     [rsp+278h+lpBuffer], rcx
0x180004afe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004b05  mov     rcx, rax; this
0x180004b08  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004b0d  jmp     short loc_180004B31
0x180004b0f  mov     rcx, rax; this
0x180004b12  test    r9, r9
0x180004b15  jz      short loc_180004B25
0x180004b17  lea     r8, aHs; "[%hs]\n"
0x180004b1e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004b23  jmp     short loc_180004B31
0x180004b25  lea     r8, asc_1800365E0; "\n"
0x180004b2c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004b31  xor     eax, eax
0x180004b33  mov     rcx, [rsp+278h+var_38]
0x180004b3b  xor     rcx, rsp; StackCookie
0x180004b3e  call    __security_check_cookie
0x180004b43  mov     rbx, [rsp+278h+arg_18]
0x180004b4b  add     rsp, 250h
0x180004b52  pop     r15
0x180004b54  pop     r14
0x180004b56  pop     rdi
0x180004b57  pop     rsi
0x180004b58  pop     rbp
0x180004b59  retn
```
