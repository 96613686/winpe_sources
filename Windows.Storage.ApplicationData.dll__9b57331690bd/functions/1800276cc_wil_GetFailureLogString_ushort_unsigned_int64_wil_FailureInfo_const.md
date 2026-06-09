# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800276cc`
- end: `0x180027982`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `HRESULT __fastcall(wchar_t *pszDest, unsigned __int64 cchDest, const wil::FailureInfo *failure)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18002711c`
- `0x180027c20`

## callees

- `0x1800276cc`
- `0x180027f20`
- `0x1800415ee`
- `0x180041620`
- `0x180042010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002787f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002787f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800277fe`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800277fe`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wchar_t *pszDest, unsigned __int64 cchDest, wil::FailureInfo *failure)
{
  void (__fastcall *v6)(wil::FailureInfo *, wchar_t *, unsigned __int64); // rax
  const char *v7; // rdi
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
          v7 = (const char *)&qword_18004C9F0;
        goto LABEL_18;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (failure->flags[0] & 8) == 0 )
      v7 = v8;
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
0x1800276cc  mov     [rsp+arg_18], rbx
0x1800276d1  push    rbp
0x1800276d2  push    rsi
0x1800276d3  push    rdi
0x1800276d4  push    r14
0x1800276d6  push    r15
0x1800276d8  sub     rsp, 250h
0x1800276df  mov     rax, cs:__security_cookie
0x1800276e6  xor     rax, rsp
0x1800276e9  mov     [rsp+278h+var_38], rax
0x1800276f1  xor     r15d, r15d
0x1800276f4  mov     rbx, failure
0x1800276f7  mov     rsi, cchDest
0x1800276fa  mov     r14, pszDest
0x1800276fd  test    cchDest, cchDest
0x180027700  jz      loc_180027959
0x180027706  test    pszDest, pszDest
0x180027709  jz      loc_180027959
0x18002770f  mov     rax, cs:g_pfnResultLoggingCallback
0x180027716  mov     [pszDest], r15w
0x18002771a  test    rax, rax
0x18002771d  jz      short loc_180027740
0x18002771f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180027726  jz      short loc_180027740
0x180027728  mov     failure, cchDest
0x18002772b  mov     cchDest, pszDest
0x18002772e  mov     pszDest, rbx
0x180027731  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027736  cmp     [r14], r15w
0x18002773a  jnz     loc_180027959
0x180027740  mov     ecx, [rbx]
0x180027742  mov     bpl, 8
0x180027745  test    ecx, ecx
0x180027747  jz      short loc_180027792
0x180027749  sub     ecx, 1
0x18002774c  jz      short loc_18002777A
0x18002774e  sub     ecx, 1
0x180027751  jz      short loc_18002776A
0x180027753  cmp     ecx, 1
0x180027756  jz      short loc_180027761
0x180027758  lea     rdi, qword_18004C9F0
0x18002775f  jmp     short loc_180027799
0x180027761  lea     rdi, aFailfast; "FailFast"
0x180027768  jmp     short loc_180027799
0x18002776a  lea     rax, aLoghr; "LogHr"
0x180027771  lea     rdi, aLognt; "LogNt"
0x180027778  jmp     short loc_180027788
0x18002777a  lea     rax, aReturnhr; "ReturnHr"
0x180027781  lea     rdi, aReturnnt; "ReturnNt"
0x180027788  test    [rbx+4], bpl
0x18002778c  cmovz   rdi, rax
0x180027790  jmp     short loc_180027799
0x180027792  lea     rdi, aException; "Exception"
0x180027799  xor     edx, edx; Val
0x18002779b  lea     pszDest, [rsp+278h+szErrorText]; void *
0x1800277a0  mov     r8d, 200h; Size
0x1800277a6  call    memset_0
0x1800277ab  test    [rbx+4], bpl
0x1800277af  jz      short loc_1800277D4
0x1800277b1  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800277b8  mov     ebp, [rbx+0Ch]
0x1800277bb  test    rax, rax
0x1800277be  jz      short loc_180027804
0x1800277c0  mov     r8d, 100h
0x1800277c6  lea     cchDest, [rsp+278h+szErrorText]
0x1800277cb  mov     ecx, ebp
0x1800277cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277d2  jmp     short loc_180027804
0x1800277d4  mov     ebp, [rbx+8]
0x1800277d7  lea     rax, [rsp+278h+szErrorText]
0x1800277dc  mov     [rsp+278h+Arguments], r15; Arguments
0x1800277e1  mov     r8d, ebp; dwMessageId
0x1800277e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800277ec  mov     r9d, 400h; dwLanguageId
0x1800277f2  xor     edx, edx; lpSource
0x1800277f4  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800277f9  mov     ecx, 1200h; dwFlags
0x1800277fe  call    cs:__imp_FormatMessageW
0x180027804  mov     r9, [rbx+38h]
0x180027808  lea     rsi, [r14+rsi*2]
0x18002780c  mov     rax, [rbx+88h]
0x180027813  mov     cchDest, rsi; destEnd
0x180027816  mov     pszDest, [rbx+80h]
0x18002781d  test    r9, r9
0x180027820  jz      short loc_180027844
0x180027822  mov     [rsp+278h+Arguments], rax
0x180027827  lea     failure, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002782e  mov     eax, [rbx+40h]
0x180027831  mov     qword ptr [rsp+278h+nSize], pszDest
0x180027836  mov     pszDest, r14; dest
0x180027839  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002783d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027842  jmp     short loc_18002785B
0x180027844  mov     r9, pszDest
0x180027847  mov     [rsp+278h+lpBuffer], rax
0x18002784c  mov     pszDest, r14; dest
0x18002784f  lea     failure, aHsP; "%hs!%p: "
0x180027856  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002785b  mov     r9, [rbx+90h]
0x180027862  mov     r14, rax
0x180027865  test    r9, r9
0x180027868  jz      short loc_18002787F
0x18002786a  lea     failure, aCallerP; "(caller: %p) "
0x180027871  mov     cchDest, rsi; destEnd
0x180027874  mov     pszDest, rax; dest
0x180027877  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002787c  mov     r14, rax
0x18002787f  call    cs:__imp_GetCurrentThreadId
0x180027885  lea     pszDest, [rsp+278h+szErrorText]
0x18002788a  mov     r9, rdi
0x18002788d  mov     [rsp+278h+var_240], pszDest
0x180027892  lea     failure, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180027899  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002789d  mov     cchDest, rsi; destEnd
0x1800278a0  mov     [rsp+278h+nSize], eax
0x1800278a4  mov     pszDest, r14; dest
0x1800278a7  mov     eax, [rbx+44h]
0x1800278aa  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800278ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800278b3  cmp     [rbx+18h], r15
0x1800278b7  jnz     short loc_1800278C9
0x1800278b9  cmp     [rbx+48h], r15
0x1800278bd  jnz     short loc_1800278C9
0x1800278bf  cmp     [rbx+30h], r15
0x1800278c3  jz      loc_180027959
0x1800278c9  lea     failure, asc_18004DE98; "    "
0x1800278d0  mov     cchDest, rsi; destEnd
0x1800278d3  mov     pszDest, rax; dest
0x1800278d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800278db  mov     r9, [rbx+18h]
0x1800278df  test    r9, r9
0x1800278e2  jz      short loc_1800278F6
0x1800278e4  lea     failure, aMsgWs; "Msg:[%ws] "
0x1800278eb  mov     cchDest, rsi; destEnd
0x1800278ee  mov     pszDest, rax; dest
0x1800278f1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800278f6  mov     r9, [rbx+48h]
0x1800278fa  test    r9, r9
0x1800278fd  jz      short loc_180027911
0x1800278ff  lea     failure, aCallcontextHs; "CallContext:[%hs] "
0x180027906  mov     cchDest, rsi; destEnd
0x180027909  mov     pszDest, rax; dest
0x18002790c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027911  mov     pszDest, [rbx+28h]
0x180027915  mov     cchDest, rsi; destEnd
0x180027918  mov     r9, [rbx+30h]
0x18002791c  test    pszDest, pszDest
0x18002791f  jz      short loc_180027937
0x180027921  mov     [rsp+278h+lpBuffer], pszDest
0x180027926  lea     failure, aHsHs; "[%hs(%hs)]\n"
0x18002792d  mov     pszDest, rax; dest
0x180027930  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027935  jmp     short loc_180027959
0x180027937  mov     pszDest, rax; dest
0x18002793a  test    r9, r9
0x18002793d  jz      short loc_18002794D
0x18002793f  lea     failure, aHs; "[%hs]\n"
0x180027946  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002794b  jmp     short loc_180027959
0x18002794d  lea     failure, asc_18004DF10; "\n"
0x180027954  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027959  xor     eax, eax
0x18002795b  mov     pszDest, [rsp+278h+var_38]
0x180027963  xor     pszDest, rsp; StackCookie
0x180027966  call    __security_check_cookie
0x18002796b  mov     rbx, [rsp+278h+arg_18]
0x180027973  add     rsp, 250h
0x18002797a  pop     r15
0x18002797c  pop     r14
0x18002797e  pop     rdi
0x18002797f  pop     rsi
0x180027980  pop     rbp
0x180027981  retn
```
