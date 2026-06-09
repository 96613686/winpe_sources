# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b104`
- end: `0x18000b3ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wchar_t *pszDest, unsigned __int64 cchDest, const wil::FailureInfo *failure)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18000be84`

## callees

- `0x180007acc`
- `0x18000b104`
- `0x1800204ee`
- `0x180020520`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b2b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b236`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b236`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wchar_t *pszDest,
        unsigned __int64 cchDest,
        const wil::FailureInfo *failure)
{
  void (__fastcall *v6)(wil::FailureInfo *, wchar_t *, unsigned __int64); // rax
  char *v7; // rdi
  const char *v8; // rax
  int status; // ebp
  const wchar_t *v10; // rsi
  wchar_t *v11; // rax
  wchar_t *v12; // r14
  wchar_t *v13; // rax
  wchar_t *v14; // rax
  const char *pszFunction; // r9
  LPWSTR lpBuffer; // [rsp+20h] [rbp-258h]
  DWORD nSize[2]; // [rsp+28h] [rbp-250h]
  va_list *Arguments; // [rsp+30h] [rbp-248h]
  wchar_t szErrorText[256]; // [rsp+40h] [rbp-238h] BYREF

  if ( !cchDest )
    return 0;
  if ( !pszDest )
    return 0;
  v6 = g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v6 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v6(failure, pszDest, cchDest);
      if ( *pszDest )
        return 0;
    }
  }
  if ( failure->type )
  {
    if ( failure->type == Return )
    {
      v8 = "ReturnHr";
      v7 = "ReturnNt";
    }
    else
    {
      if ( failure->type != Log )
      {
        if ( failure->type == FailFast )
          v7 = "FailFast";
        else
          v7 = byte_180026F30;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (failure->flags[0] & 8) == 0 )
      v7 = (char *)v8;
    goto LABEL_18;
  }
  v7 = "Exception";
LABEL_18:
  memset_0(szErrorText, 0, sizeof(szErrorText));
  if ( (failure->flags[0] & 8) != 0 )
  {
    status = failure->status;
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(status, szErrorText, 0x100u);
  }
  else
  {
    status = failure->hr;
    FormatMessageW(0x1200u, 0, status, 0x400u, szErrorText, 0x100u, 0);
  }
  v10 = &pszDest[cchDest];
  if ( failure->pszFile )
  {
    HIDWORD(Arguments) = HIDWORD(failure->returnAddress);
    nSize[1] = HIDWORD(failure->pszModule);
    v11 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ");
  }
  else
  {
    v11 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", failure->pszModule, failure->returnAddress);
  }
  v12 = v11;
  if ( failure->callerReturnAddress )
    v12 = wil::details::LogStringPrintf(v11, v10, L"(caller: %p) ");
  LODWORD(Arguments) = status;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffer) = failure->cFailureCount;
  v13 = wil::details::LogStringPrintf(
          v12,
          v10,
          L"%hs(%d) tid(%x) %08X %ws",
          v7,
          lpBuffer,
          *(_QWORD *)nSize,
          Arguments,
          szErrorText);
  if ( failure->pszMessage || failure->pszCallContext || failure->pszFunction )
  {
    v14 = wil::details::LogStringPrintf(v13, v10, L"    ");
    if ( failure->pszMessage )
      v14 = wil::details::LogStringPrintf(v14, v10, L"Msg:[%ws] ");
    if ( failure->pszCallContext )
      v14 = wil::details::LogStringPrintf(v14, v10, L"CallContext:[%hs] ");
    pszFunction = failure->pszFunction;
    if ( failure->pszCode )
    {
      wil::details::LogStringPrintf(v14, v10, L"[%hs(%hs)]\n", pszFunction, failure->pszCode);
    }
    else if ( pszFunction )
    {
      wil::details::LogStringPrintf(v14, v10, L"[%hs]\n");
    }
    else
    {
      wil::details::LogStringPrintf(v14, v10, L"\n");
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18000b104  mov     [rsp+arg_18], rbx
0x18000b109  push    rbp
0x18000b10a  push    rsi
0x18000b10b  push    rdi
0x18000b10c  push    r14
0x18000b10e  push    r15
0x18000b110  sub     rsp, 250h
0x18000b117  mov     rax, cs:__security_cookie
0x18000b11e  xor     rax, rsp
0x18000b121  mov     [rsp+278h+var_38], rax
0x18000b129  xor     r15d, r15d
0x18000b12c  mov     rbx, failure
0x18000b12f  mov     rsi, cchDest
0x18000b132  mov     r14, pszDest
0x18000b135  test    cchDest, cchDest
0x18000b138  jz      loc_18000B391
0x18000b13e  test    pszDest, pszDest
0x18000b141  jz      loc_18000B391
0x18000b147  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b14e  mov     [pszDest], r15w
0x18000b152  test    rax, rax
0x18000b155  jz      short loc_18000B178
0x18000b157  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b15e  jz      short loc_18000B178
0x18000b160  mov     failure, cchDest
0x18000b163  mov     cchDest, pszDest
0x18000b166  mov     pszDest, rbx
0x18000b169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b16e  cmp     [r14], r15w
0x18000b172  jnz     loc_18000B391
0x18000b178  mov     ecx, [rbx]
0x18000b17a  mov     bpl, 8
0x18000b17d  test    ecx, ecx
0x18000b17f  jz      short loc_18000B1CA
0x18000b181  sub     ecx, 1
0x18000b184  jz      short loc_18000B1B2
0x18000b186  sub     ecx, 1
0x18000b189  jz      short loc_18000B1A2
0x18000b18b  cmp     ecx, 1
0x18000b18e  jz      short loc_18000B199
0x18000b190  lea     rdi, byte_180026F30
0x18000b197  jmp     short loc_18000B1D1
0x18000b199  lea     rdi, aFailfast; "FailFast"
0x18000b1a0  jmp     short loc_18000B1D1
0x18000b1a2  lea     rax, aLoghr; "LogHr"
0x18000b1a9  lea     rdi, aLognt; "LogNt"
0x18000b1b0  jmp     short loc_18000B1C0
0x18000b1b2  lea     rax, aReturnhr; "ReturnHr"
0x18000b1b9  lea     rdi, aReturnnt; "ReturnNt"
0x18000b1c0  test    [rbx+4], bpl
0x18000b1c4  cmovz   rdi, rax
0x18000b1c8  jmp     short loc_18000B1D1
0x18000b1ca  lea     rdi, aException; "Exception"
0x18000b1d1  xor     edx, edx; Val
0x18000b1d3  lea     pszDest, [rsp+278h+szErrorText]; void *
0x18000b1d8  mov     r8d, 200h; Size
0x18000b1de  call    memset_0
0x18000b1e3  test    [rbx+4], bpl
0x18000b1e7  jz      short loc_18000B20C
0x18000b1e9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b1f0  mov     ebp, [rbx+0Ch]
0x18000b1f3  test    rax, rax
0x18000b1f6  jz      short loc_18000B23C
0x18000b1f8  mov     r8d, 100h
0x18000b1fe  lea     cchDest, [rsp+278h+szErrorText]
0x18000b203  mov     ecx, ebp
0x18000b205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b20a  jmp     short loc_18000B23C
0x18000b20c  mov     ebp, [rbx+8]
0x18000b20f  lea     rax, [rsp+278h+szErrorText]
0x18000b214  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b219  mov     r8d, ebp; dwMessageId
0x18000b21c  mov     [rsp+278h+nSize], 100h; nSize
0x18000b224  mov     r9d, 400h; dwLanguageId
0x18000b22a  xor     edx, edx; lpSource
0x18000b22c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b231  mov     ecx, 1200h; dwFlags
0x18000b236  call    cs:__imp_FormatMessageW
0x18000b23c  mov     r9, [rbx+38h]
0x18000b240  lea     rsi, [r14+rsi*2]
0x18000b244  mov     rax, [rbx+88h]
0x18000b24b  mov     cchDest, rsi; destEnd
0x18000b24e  mov     pszDest, [rbx+80h]
0x18000b255  test    r9, r9
0x18000b258  jz      short loc_18000B27C
0x18000b25a  mov     [rsp+278h+Arguments], rax
0x18000b25f  lea     failure, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b266  mov     eax, [rbx+40h]
0x18000b269  mov     qword ptr [rsp+278h+nSize], pszDest
0x18000b26e  mov     pszDest, r14; dest
0x18000b271  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b275  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b27a  jmp     short loc_18000B293
0x18000b27c  mov     r9, pszDest
0x18000b27f  mov     [rsp+278h+lpBuffer], rax
0x18000b284  mov     pszDest, r14; dest
0x18000b287  lea     failure, aHsP; "%hs!%p: "
0x18000b28e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b293  mov     r9, [rbx+90h]
0x18000b29a  mov     r14, rax
0x18000b29d  test    r9, r9
0x18000b2a0  jz      short loc_18000B2B7
0x18000b2a2  lea     failure, aCallerP; "(caller: %p) "
0x18000b2a9  mov     cchDest, rsi; destEnd
0x18000b2ac  mov     pszDest, rax; dest
0x18000b2af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2b4  mov     r14, rax
0x18000b2b7  call    cs:__imp_GetCurrentThreadId
0x18000b2bd  lea     pszDest, [rsp+278h+szErrorText]
0x18000b2c2  mov     r9, rdi
0x18000b2c5  mov     [rsp+278h+var_240], pszDest
0x18000b2ca  lea     failure, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b2d1  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b2d5  mov     cchDest, rsi; destEnd
0x18000b2d8  mov     [rsp+278h+nSize], eax
0x18000b2dc  mov     pszDest, r14; dest
0x18000b2df  mov     eax, [rbx+44h]
0x18000b2e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b2e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2eb  cmp     [rbx+18h], r15
0x18000b2ef  jnz     short loc_18000B301
0x18000b2f1  cmp     [rbx+48h], r15
0x18000b2f5  jnz     short loc_18000B301
0x18000b2f7  cmp     [rbx+30h], r15
0x18000b2fb  jz      loc_18000B391
0x18000b301  lea     failure, asc_180027020; "    "
0x18000b308  mov     cchDest, rsi; destEnd
0x18000b30b  mov     pszDest, rax; dest
0x18000b30e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b313  mov     r9, [rbx+18h]
0x18000b317  test    r9, r9
0x18000b31a  jz      short loc_18000B32E
0x18000b31c  lea     failure, aMsgWs; "Msg:[%ws] "
0x18000b323  mov     cchDest, rsi; destEnd
0x18000b326  mov     pszDest, rax; dest
0x18000b329  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b32e  mov     r9, [rbx+48h]
0x18000b332  test    r9, r9
0x18000b335  jz      short loc_18000B349
0x18000b337  lea     failure, aCallcontextHs; "CallContext:[%hs] "
0x18000b33e  mov     cchDest, rsi; destEnd
0x18000b341  mov     pszDest, rax; dest
0x18000b344  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b349  mov     pszDest, [rbx+28h]
0x18000b34d  mov     cchDest, rsi; destEnd
0x18000b350  mov     r9, [rbx+30h]
0x18000b354  test    pszDest, pszDest
0x18000b357  jz      short loc_18000B36F
0x18000b359  mov     [rsp+278h+lpBuffer], pszDest
0x18000b35e  lea     failure, aHsHs; "[%hs(%hs)]\n"
0x18000b365  mov     pszDest, rax; dest
0x18000b368  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b36d  jmp     short loc_18000B391
0x18000b36f  mov     pszDest, rax; dest
0x18000b372  test    r9, r9
0x18000b375  jz      short loc_18000B385
0x18000b377  lea     failure, aHs; "[%hs]\n"
0x18000b37e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b383  jmp     short loc_18000B391
0x18000b385  lea     failure, asc_180026F34; "\n"
0x18000b38c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b391  xor     eax, eax
0x18000b393  mov     pszDest, [rsp+278h+var_38]
0x18000b39b  xor     pszDest, rsp; StackCookie
0x18000b39e  call    __security_check_cookie
0x18000b3a3  mov     rbx, [rsp+278h+arg_18]
0x18000b3ab  add     rsp, 250h
0x18000b3b2  pop     r15
0x18000b3b4  pop     r14
0x18000b3b6  pop     rdi
0x18000b3b7  pop     rsi
0x18000b3b8  pop     rbp
0x18000b3b9  retn
```
