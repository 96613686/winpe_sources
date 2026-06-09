# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180025284`
- end: `0x18002553a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180023810`
- `0x180025c6c`
- `0x1800260a0`
- `0x1800286e0`

## callees

- `0x180023282`
- `0x180025284`
- `0x180025f6c`
- `0x1800326d0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025437`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800253b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800253b6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  WCHAR Buffer[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
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
          v7 = (const char *)&byte_1800400D0;
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
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v15,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v7,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180025284  mov     [rsp+arg_18], rbx
0x180025289  push    rbp
0x18002528a  push    rsi
0x18002528b  push    rdi
0x18002528c  push    r14
0x18002528e  push    r15
0x180025290  sub     rsp, 250h
0x180025297  mov     rax, cs:__security_cookie
0x18002529e  xor     rax, rsp
0x1800252a1  mov     [rsp+278h+var_38], rax
0x1800252a9  mov     rbx, r8
0x1800252ac  mov     rsi, rdx
0x1800252af  mov     r14, rcx
0x1800252b2  xor     r15d, r15d
0x1800252b5  test    rdx, rdx
0x1800252b8  jz      loc_180025511
0x1800252be  test    rcx, rcx
0x1800252c1  jz      loc_180025511
0x1800252c7  mov     [rcx], r15w
0x1800252cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800252d2  test    rax, rax
0x1800252d5  jz      short loc_1800252F8
0x1800252d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800252de  jz      short loc_1800252F8
0x1800252e0  mov     r8, rdx
0x1800252e3  mov     rdx, rcx
0x1800252e6  mov     rcx, rbx
0x1800252e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800252ee  cmp     [r14], r15w
0x1800252f2  jnz     loc_180025511
0x1800252f8  mov     ecx, [rbx]
0x1800252fa  mov     bpl, 8
0x1800252fd  test    ecx, ecx
0x1800252ff  jz      short loc_18002534A
0x180025301  sub     ecx, 1
0x180025304  jz      short loc_180025332
0x180025306  sub     ecx, 1
0x180025309  jz      short loc_180025322
0x18002530b  cmp     ecx, 1
0x18002530e  jz      short loc_180025319
0x180025310  lea     rdi, byte_1800400D0
0x180025317  jmp     short loc_180025351
0x180025319  lea     rdi, aFailfast; "FailFast"
0x180025320  jmp     short loc_180025351
0x180025322  lea     rax, aLoghr; "LogHr"
0x180025329  lea     rdi, aLognt; "LogNt"
0x180025330  jmp     short loc_180025340
0x180025332  lea     rax, aReturnhr; "ReturnHr"
0x180025339  lea     rdi, aReturnnt; "ReturnNt"
0x180025340  test    [rbx+4], bpl
0x180025344  cmovz   rdi, rax
0x180025348  jmp     short loc_180025351
0x18002534a  lea     rdi, aException; "Exception"
0x180025351  xor     edx, edx; Val
0x180025353  mov     r8d, 200h; Size
0x180025359  lea     rcx, [rsp+278h+Buffer]; void *
0x18002535e  call    memset_0
0x180025363  test    [rbx+4], bpl
0x180025367  jz      short loc_18002538C
0x180025369  mov     ebp, [rbx+0Ch]
0x18002536c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180025373  test    rax, rax
0x180025376  jz      short loc_1800253BC
0x180025378  mov     r8d, 100h
0x18002537e  lea     rdx, [rsp+278h+Buffer]
0x180025383  mov     ecx, ebp
0x180025385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002538a  jmp     short loc_1800253BC
0x18002538c  mov     ebp, [rbx+8]
0x18002538f  mov     [rsp+278h+Arguments], r15; Arguments
0x180025394  mov     [rsp+278h+nSize], 100h; nSize
0x18002539c  lea     rax, [rsp+278h+Buffer]
0x1800253a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800253a6  mov     r9d, 400h; dwLanguageId
0x1800253ac  mov     r8d, ebp; dwMessageId
0x1800253af  xor     edx, edx; lpSource
0x1800253b1  mov     ecx, 1200h; dwFlags
0x1800253b6  call    cs:__imp_FormatMessageW
0x1800253bc  lea     rsi, [r14+rsi*2]
0x1800253c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800253c4  mov     rax, [rbx+88h]
0x1800253cb  mov     rcx, [rbx+80h]
0x1800253d2  mov     rdx, rsi; unsigned __int16 *
0x1800253d5  test    r9, r9
0x1800253d8  jz      short loc_1800253FC
0x1800253da  mov     [rsp+278h+Arguments], rax
0x1800253df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800253e4  mov     eax, [rbx+40h]
0x1800253e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800253eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800253f2  mov     rcx, r14; pszDest
0x1800253f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800253fa  jmp     short loc_180025413
0x1800253fc  mov     [rsp+278h+lpBuffer], rax
0x180025401  mov     r9, rcx; unsigned __int16 *
0x180025404  lea     r8, aHsP; "%hs!%p: "
0x18002540b  mov     rcx, r14; pszDest
0x18002540e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025413  mov     r14, rax
0x180025416  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002541d  test    r9, r9
0x180025420  jz      short loc_180025437
0x180025422  lea     r8, aCallerP; "(caller: %p) "
0x180025429  mov     rdx, rsi; unsigned __int16 *
0x18002542c  mov     rcx, rax; pszDest
0x18002542f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025434  mov     r14, rax
0x180025437  call    cs:__imp_GetCurrentThreadId
0x18002543d  lea     rcx, [rsp+278h+Buffer]
0x180025442  mov     [rsp+278h+var_240], rcx
0x180025447  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002544b  mov     [rsp+278h+nSize], eax
0x18002544f  mov     eax, [rbx+44h]
0x180025452  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025456  mov     r9, rdi; unsigned __int16 *
0x180025459  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025460  mov     rdx, rsi; unsigned __int16 *
0x180025463  mov     rcx, r14; pszDest
0x180025466  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002546b  cmp     [rbx+18h], r15
0x18002546f  jnz     short loc_180025481
0x180025471  cmp     [rbx+48h], r15
0x180025475  jnz     short loc_180025481
0x180025477  cmp     [rbx+30h], r15
0x18002547b  jz      loc_180025511
0x180025481  lea     r8, asc_1800401C0; "    "
0x180025488  mov     rdx, rsi; unsigned __int16 *
0x18002548b  mov     rcx, rax; pszDest
0x18002548e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025493  mov     r9, [rbx+18h]; unsigned __int16 *
0x180025497  test    r9, r9
0x18002549a  jz      short loc_1800254AE
0x18002549c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800254a3  mov     rdx, rsi; unsigned __int16 *
0x1800254a6  mov     rcx, rax; pszDest
0x1800254a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800254ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800254b2  test    r9, r9
0x1800254b5  jz      short loc_1800254C9
0x1800254b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800254be  mov     rdx, rsi; unsigned __int16 *
0x1800254c1  mov     rcx, rax; pszDest
0x1800254c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800254c9  mov     rcx, [rbx+28h]
0x1800254cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800254d1  mov     rdx, rsi; unsigned __int16 *
0x1800254d4  test    rcx, rcx
0x1800254d7  jz      short loc_1800254EF
0x1800254d9  mov     [rsp+278h+lpBuffer], rcx
0x1800254de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800254e5  mov     rcx, rax; pszDest
0x1800254e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800254ed  jmp     short loc_180025511
0x1800254ef  mov     rcx, rax; pszDest
0x1800254f2  test    r9, r9
0x1800254f5  jz      short loc_180025505
0x1800254f7  lea     r8, aHs; "[%hs]\n"
0x1800254fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025503  jmp     short loc_180025511
0x180025505  lea     r8, asc_180040238; "\n"
0x18002550c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025511  xor     eax, eax
0x180025513  mov     rcx, [rsp+278h+var_38]
0x18002551b  xor     rcx, rsp; StackCookie
0x18002551e  call    __security_check_cookie
0x180025523  mov     rbx, [rsp+278h+arg_18]
0x18002552b  add     rsp, 250h
0x180025532  pop     r15
0x180025534  pop     r14
0x180025536  pop     rdi
0x180025537  pop     rsi
0x180025538  pop     rbp
0x180025539  retn
```
