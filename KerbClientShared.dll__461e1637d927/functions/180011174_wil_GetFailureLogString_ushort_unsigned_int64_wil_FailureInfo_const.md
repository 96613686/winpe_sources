# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180011174`
- end: `0x18001142a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000fde8`
- `0x180011e84`

## callees

- `0x18000eb70`
- `0x18000f4dc`
- `0x180011174`
- `0x180012184`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011327`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011327`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800112a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800112a6`

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
          v8 = (const char *)&byte_18002D071;
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
0x180011174  mov     [rsp+arg_18], rbx
0x180011179  push    rbp
0x18001117a  push    rsi
0x18001117b  push    rdi
0x18001117c  push    r14
0x18001117e  push    r15
0x180011180  sub     rsp, 250h
0x180011187  mov     rax, cs:__security_cookie
0x18001118e  xor     rax, rsp
0x180011191  mov     [rsp+278h+var_38], rax
0x180011199  xor     r15d, r15d
0x18001119c  mov     rbx, r8
0x18001119f  mov     rsi, rdx
0x1800111a2  mov     r14, rcx
0x1800111a5  test    rdx, rdx
0x1800111a8  jz      loc_180011401
0x1800111ae  test    rcx, rcx
0x1800111b1  jz      loc_180011401
0x1800111b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800111be  mov     [rcx], r15w
0x1800111c2  test    rax, rax
0x1800111c5  jz      short loc_1800111E8
0x1800111c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800111ce  jz      short loc_1800111E8
0x1800111d0  mov     r8, rdx
0x1800111d3  mov     rdx, rcx
0x1800111d6  mov     rcx, rbx
0x1800111d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800111de  cmp     [r14], r15w
0x1800111e2  jnz     loc_180011401
0x1800111e8  mov     ecx, [rbx]
0x1800111ea  mov     bpl, 8
0x1800111ed  test    ecx, ecx
0x1800111ef  jz      short loc_18001123A
0x1800111f1  sub     ecx, 1
0x1800111f4  jz      short loc_180011222
0x1800111f6  sub     ecx, 1
0x1800111f9  jz      short loc_180011212
0x1800111fb  cmp     ecx, 1
0x1800111fe  jz      short loc_180011209
0x180011200  lea     rdi, byte_18002D071
0x180011207  jmp     short loc_180011241
0x180011209  lea     rdi, aFailfast; "FailFast"
0x180011210  jmp     short loc_180011241
0x180011212  lea     rax, aLoghr; "LogHr"
0x180011219  lea     rdi, aLognt; "LogNt"
0x180011220  jmp     short loc_180011230
0x180011222  lea     rax, aReturnhr; "ReturnHr"
0x180011229  lea     rdi, aReturnnt; "ReturnNt"
0x180011230  test    [rbx+4], bpl
0x180011234  cmovz   rdi, rax
0x180011238  jmp     short loc_180011241
0x18001123a  lea     rdi, aException; "Exception"
0x180011241  xor     edx, edx; Val
0x180011243  lea     rcx, [rsp+278h+Buffer]; void *
0x180011248  mov     r8d, 200h; Size
0x18001124e  call    memset_0
0x180011253  test    [rbx+4], bpl
0x180011257  jz      short loc_18001127C
0x180011259  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011260  mov     ebp, [rbx+0Ch]
0x180011263  test    rax, rax
0x180011266  jz      short loc_1800112AC
0x180011268  mov     r8d, 100h
0x18001126e  lea     rdx, [rsp+278h+Buffer]
0x180011273  mov     ecx, ebp
0x180011275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001127a  jmp     short loc_1800112AC
0x18001127c  mov     ebp, [rbx+8]
0x18001127f  lea     rax, [rsp+278h+Buffer]
0x180011284  mov     [rsp+278h+Arguments], r15; Arguments
0x180011289  mov     r8d, ebp; dwMessageId
0x18001128c  mov     [rsp+278h+nSize], 100h; nSize
0x180011294  mov     r9d, 400h; dwLanguageId
0x18001129a  xor     edx, edx; lpSource
0x18001129c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800112a1  mov     ecx, 1200h; dwFlags
0x1800112a6  call    cs:__imp_FormatMessageW
0x1800112ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800112b0  lea     rsi, [r14+rsi*2]
0x1800112b4  mov     rax, [rbx+88h]
0x1800112bb  mov     rdx, rsi; unsigned __int16 *
0x1800112be  mov     rcx, [rbx+80h]
0x1800112c5  test    r9, r9
0x1800112c8  jz      short loc_1800112EC
0x1800112ca  mov     [rsp+278h+Arguments], rax
0x1800112cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800112d6  mov     eax, [rbx+40h]
0x1800112d9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800112de  mov     rcx, r14; pszDest
0x1800112e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800112e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800112ea  jmp     short loc_180011303
0x1800112ec  mov     r9, rcx; unsigned __int16 *
0x1800112ef  mov     [rsp+278h+lpBuffer], rax
0x1800112f4  mov     rcx, r14; pszDest
0x1800112f7  lea     r8, aHsP; "%hs!%p: "
0x1800112fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011303  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001130a  mov     r14, rax
0x18001130d  test    r9, r9
0x180011310  jz      short loc_180011327
0x180011312  lea     r8, aCallerP; "(caller: %p) "
0x180011319  mov     rdx, rsi; unsigned __int16 *
0x18001131c  mov     rcx, rax; pszDest
0x18001131f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011324  mov     r14, rax
0x180011327  call    cs:__imp_GetCurrentThreadId
0x18001132d  lea     rcx, [rsp+278h+Buffer]
0x180011332  mov     r9, rdi; unsigned __int16 *
0x180011335  mov     [rsp+278h+var_240], rcx
0x18001133a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011341  mov     dword ptr [rsp+278h+Arguments], ebp
0x180011345  mov     rdx, rsi; unsigned __int16 *
0x180011348  mov     [rsp+278h+nSize], eax
0x18001134c  mov     rcx, r14; pszDest
0x18001134f  mov     eax, [rbx+44h]
0x180011352  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011356  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001135b  cmp     [rbx+18h], r15
0x18001135f  jnz     short loc_180011371
0x180011361  cmp     [rbx+48h], r15
0x180011365  jnz     short loc_180011371
0x180011367  cmp     [rbx+30h], r15
0x18001136b  jz      loc_180011401
0x180011371  lea     r8, asc_18002D160; "    "
0x180011378  mov     rdx, rsi; unsigned __int16 *
0x18001137b  mov     rcx, rax; pszDest
0x18001137e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011383  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011387  test    r9, r9
0x18001138a  jz      short loc_18001139E
0x18001138c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011393  mov     rdx, rsi; unsigned __int16 *
0x180011396  mov     rcx, rax; pszDest
0x180011399  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001139e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800113a2  test    r9, r9
0x1800113a5  jz      short loc_1800113B9
0x1800113a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800113ae  mov     rdx, rsi; unsigned __int16 *
0x1800113b1  mov     rcx, rax; pszDest
0x1800113b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800113b9  mov     rcx, [rbx+28h]
0x1800113bd  mov     rdx, rsi; unsigned __int16 *
0x1800113c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800113c4  test    rcx, rcx
0x1800113c7  jz      short loc_1800113DF
0x1800113c9  mov     [rsp+278h+lpBuffer], rcx
0x1800113ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800113d5  mov     rcx, rax; pszDest
0x1800113d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800113dd  jmp     short loc_180011401
0x1800113df  mov     rcx, rax; pszDest
0x1800113e2  test    r9, r9
0x1800113e5  jz      short loc_1800113F5
0x1800113e7  lea     r8, aHs; "[%hs]\n"
0x1800113ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800113f3  jmp     short loc_180011401
0x1800113f5  lea     r8, asc_18002D1D8; "\n"
0x1800113fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011401  xor     eax, eax
0x180011403  mov     rcx, [rsp+278h+var_38]
0x18001140b  xor     rcx, rsp; StackCookie
0x18001140e  call    __security_check_cookie
0x180011413  mov     rbx, [rsp+278h+arg_18]
0x18001141b  add     rsp, 250h
0x180011422  pop     r15
0x180011424  pop     r14
0x180011426  pop     rdi
0x180011427  pop     rsi
0x180011428  pop     rbp
0x180011429  retn
```
