# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800053f4`
- end: `0x1800056aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800045d4`
- `0x180005e30`

## callees

- `0x1800053f4`
- `0x180006130`
- `0x18000b6de`
- `0x18000b710`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005526`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005526`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // r9
  wchar_t *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, pszDest, a2, a4);
      if ( *pszDest )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&dword_18000ECFC;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = &pszDest[(_QWORD)a2];
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf(v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v16,
          v12,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v8,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800053f4  mov     [rsp+arg_18], rbx
0x1800053f9  push    rbp
0x1800053fa  push    rsi
0x1800053fb  push    rdi
0x1800053fc  push    r14
0x1800053fe  push    r15
0x180005400  sub     rsp, 250h
0x180005407  mov     rax, cs:__security_cookie
0x18000540e  xor     rax, rsp
0x180005411  mov     [rsp+278h+var_38], rax
0x180005419  xor     r15d, r15d
0x18000541c  mov     rbx, r8
0x18000541f  mov     rsi, rdx
0x180005422  mov     r14, rcx
0x180005425  test    rdx, rdx
0x180005428  jz      loc_180005681
0x18000542e  test    rcx, rcx
0x180005431  jz      loc_180005681
0x180005437  mov     rax, cs:g_pfnResultLoggingCallback
0x18000543e  mov     [rcx], r15w
0x180005442  test    rax, rax
0x180005445  jz      short loc_180005468
0x180005447  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000544e  jz      short loc_180005468
0x180005450  mov     r8, rdx
0x180005453  mov     rdx, rcx
0x180005456  mov     rcx, rbx
0x180005459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000545e  cmp     [r14], r15w
0x180005462  jnz     loc_180005681
0x180005468  mov     ecx, [rbx]
0x18000546a  mov     bpl, 8
0x18000546d  test    ecx, ecx
0x18000546f  jz      short loc_1800054BA
0x180005471  sub     ecx, 1
0x180005474  jz      short loc_1800054A2
0x180005476  sub     ecx, 1
0x180005479  jz      short loc_180005492
0x18000547b  cmp     ecx, 1
0x18000547e  jz      short loc_180005489
0x180005480  lea     rdi, dword_18000ECFC
0x180005487  jmp     short loc_1800054C1
0x180005489  lea     rdi, aFailfast; "FailFast"
0x180005490  jmp     short loc_1800054C1
0x180005492  lea     rax, aLoghr; "LogHr"
0x180005499  lea     rdi, aLognt; "LogNt"
0x1800054a0  jmp     short loc_1800054B0
0x1800054a2  lea     rax, aReturnhr; "ReturnHr"
0x1800054a9  lea     rdi, aReturnnt; "ReturnNt"
0x1800054b0  test    [rbx+4], bpl
0x1800054b4  cmovz   rdi, rax
0x1800054b8  jmp     short loc_1800054C1
0x1800054ba  lea     rdi, aException; "Exception"
0x1800054c1  xor     edx, edx; Val
0x1800054c3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800054c8  mov     r8d, 200h; Size
0x1800054ce  call    memset_0
0x1800054d3  test    [rbx+4], bpl
0x1800054d7  jz      short loc_1800054FC
0x1800054d9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800054e0  mov     ebp, [rbx+0Ch]
0x1800054e3  test    rax, rax
0x1800054e6  jz      short loc_18000552C
0x1800054e8  mov     r8d, 100h
0x1800054ee  lea     rdx, [rsp+278h+Buffer]
0x1800054f3  mov     ecx, ebp
0x1800054f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054fa  jmp     short loc_18000552C
0x1800054fc  mov     ebp, [rbx+8]
0x1800054ff  lea     rax, [rsp+278h+Buffer]
0x180005504  mov     [rsp+278h+Arguments], r15; Arguments
0x180005509  mov     r8d, ebp; dwMessageId
0x18000550c  mov     [rsp+278h+nSize], 100h; nSize
0x180005514  mov     r9d, 400h; dwLanguageId
0x18000551a  xor     edx, edx; lpSource
0x18000551c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005521  mov     ecx, 1200h; dwFlags
0x180005526  call    cs:__imp_FormatMessageW
0x18000552c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005530  lea     rsi, [r14+rsi*2]
0x180005534  mov     rax, [rbx+88h]
0x18000553b  mov     rdx, rsi; unsigned __int16 *
0x18000553e  mov     rcx, [rbx+80h]
0x180005545  test    r9, r9
0x180005548  jz      short loc_18000556C
0x18000554a  mov     [rsp+278h+Arguments], rax
0x18000554f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005556  mov     eax, [rbx+40h]
0x180005559  mov     qword ptr [rsp+278h+nSize], rcx
0x18000555e  mov     rcx, r14; pszDest
0x180005561  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005565  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000556a  jmp     short loc_180005583
0x18000556c  mov     r9, rcx; unsigned __int16 *
0x18000556f  mov     [rsp+278h+lpBuffer], rax
0x180005574  mov     rcx, r14; pszDest
0x180005577  lea     r8, aHsP; "%hs!%p: "
0x18000557e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005583  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000558a  mov     r14, rax
0x18000558d  test    r9, r9
0x180005590  jz      short loc_1800055A7
0x180005592  lea     r8, aCallerP; "(caller: %p) "
0x180005599  mov     rdx, rsi; unsigned __int16 *
0x18000559c  mov     rcx, rax; pszDest
0x18000559f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055a4  mov     r14, rax
0x1800055a7  call    cs:__imp_GetCurrentThreadId
0x1800055ad  lea     rcx, [rsp+278h+Buffer]
0x1800055b2  mov     r9, rdi; unsigned __int16 *
0x1800055b5  mov     [rsp+278h+var_240], rcx
0x1800055ba  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800055c1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800055c5  mov     rdx, rsi; unsigned __int16 *
0x1800055c8  mov     [rsp+278h+nSize], eax
0x1800055cc  mov     rcx, r14; pszDest
0x1800055cf  mov     eax, [rbx+44h]
0x1800055d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800055d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055db  cmp     [rbx+18h], r15
0x1800055df  jnz     short loc_1800055F1
0x1800055e1  cmp     [rbx+48h], r15
0x1800055e5  jnz     short loc_1800055F1
0x1800055e7  cmp     [rbx+30h], r15
0x1800055eb  jz      loc_180005681
0x1800055f1  lea     r8, asc_18000EB20; "    "
0x1800055f8  mov     rdx, rsi; unsigned __int16 *
0x1800055fb  mov     rcx, rax; pszDest
0x1800055fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005603  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005607  test    r9, r9
0x18000560a  jz      short loc_18000561E
0x18000560c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005613  mov     rdx, rsi; unsigned __int16 *
0x180005616  mov     rcx, rax; pszDest
0x180005619  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000561e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005622  test    r9, r9
0x180005625  jz      short loc_180005639
0x180005627  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000562e  mov     rdx, rsi; unsigned __int16 *
0x180005631  mov     rcx, rax; pszDest
0x180005634  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005639  mov     rcx, [rbx+28h]
0x18000563d  mov     rdx, rsi; unsigned __int16 *
0x180005640  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005644  test    rcx, rcx
0x180005647  jz      short loc_18000565F
0x180005649  mov     [rsp+278h+lpBuffer], rcx
0x18000564e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005655  mov     rcx, rax; pszDest
0x180005658  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000565d  jmp     short loc_180005681
0x18000565f  mov     rcx, rax; pszDest
0x180005662  test    r9, r9
0x180005665  jz      short loc_180005675
0x180005667  lea     r8, aHs; "[%hs]\n"
0x18000566e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005673  jmp     short loc_180005681
0x180005675  lea     r8, asc_18000EB98; "\n"
0x18000567c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005681  xor     eax, eax
0x180005683  mov     rcx, [rsp+278h+var_38]
0x18000568b  xor     rcx, rsp; StackCookie
0x18000568e  call    __security_check_cookie
0x180005693  mov     rbx, [rsp+278h+arg_18]
0x18000569b  add     rsp, 250h
0x1800056a2  pop     r15
0x1800056a4  pop     r14
0x1800056a6  pop     rdi
0x1800056a7  pop     rsi
0x1800056a8  pop     rbp
0x1800056a9  retn
```
