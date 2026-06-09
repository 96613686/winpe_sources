# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000f4b4`
- end: `0x18000f76a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e3d8`
- `0x18000fe6c`
- `0x1800114e0`

## callees

- `0x18000ca90`
- `0x18000d678`
- `0x18000f4b4`
- `0x18001016c`
- `0x1800e7010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f667`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f5e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f5e6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        wchar_t *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
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
          v7 = (const char *)&qword_1801687B8;
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
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x18000f4b4  mov     [rsp+arg_18], rbx
0x18000f4b9  push    rbp
0x18000f4ba  push    rsi
0x18000f4bb  push    rdi
0x18000f4bc  push    r14
0x18000f4be  push    r15
0x18000f4c0  sub     rsp, 250h
0x18000f4c7  mov     rax, cs:__security_cookie
0x18000f4ce  xor     rax, rsp
0x18000f4d1  mov     [rsp+278h+var_38], rax
0x18000f4d9  mov     rbx, r8
0x18000f4dc  mov     rsi, rdx
0x18000f4df  mov     r14, rcx
0x18000f4e2  xor     r15d, r15d
0x18000f4e5  test    rdx, rdx
0x18000f4e8  jz      loc_18000F741
0x18000f4ee  test    rcx, rcx
0x18000f4f1  jz      loc_18000F741
0x18000f4f7  mov     [rcx], r15w
0x18000f4fb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f502  test    rax, rax
0x18000f505  jz      short loc_18000F528
0x18000f507  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f50e  jz      short loc_18000F528
0x18000f510  mov     r8, rdx
0x18000f513  mov     rdx, rcx
0x18000f516  mov     rcx, rbx
0x18000f519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f51e  cmp     [r14], r15w
0x18000f522  jnz     loc_18000F741
0x18000f528  mov     ecx, [rbx]
0x18000f52a  mov     bpl, 8
0x18000f52d  test    ecx, ecx
0x18000f52f  jz      short loc_18000F57A
0x18000f531  sub     ecx, 1
0x18000f534  jz      short loc_18000F562
0x18000f536  sub     ecx, 1
0x18000f539  jz      short loc_18000F552
0x18000f53b  cmp     ecx, 1
0x18000f53e  jz      short loc_18000F549
0x18000f540  lea     rdi, qword_1801687B8
0x18000f547  jmp     short loc_18000F581
0x18000f549  lea     rdi, aFailfast; "FailFast"
0x18000f550  jmp     short loc_18000F581
0x18000f552  lea     rax, aLoghr; "LogHr"
0x18000f559  lea     rdi, aLognt; "LogNt"
0x18000f560  jmp     short loc_18000F570
0x18000f562  lea     rax, aReturnhr; "ReturnHr"
0x18000f569  lea     rdi, aReturnnt; "ReturnNt"
0x18000f570  test    [rbx+4], bpl
0x18000f574  cmovz   rdi, rax
0x18000f578  jmp     short loc_18000F581
0x18000f57a  lea     rdi, aException; "Exception"
0x18000f581  xor     edx, edx; Val
0x18000f583  mov     r8d, 200h; Size
0x18000f589  lea     rcx, [rsp+278h+Buffer]; void *
0x18000f58e  call    memset_0
0x18000f593  test    [rbx+4], bpl
0x18000f597  jz      short loc_18000F5BC
0x18000f599  mov     ebp, [rbx+0Ch]
0x18000f59c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000f5a3  test    rax, rax
0x18000f5a6  jz      short loc_18000F5EC
0x18000f5a8  mov     r8d, 100h
0x18000f5ae  lea     rdx, [rsp+278h+Buffer]
0x18000f5b3  mov     ecx, ebp
0x18000f5b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f5ba  jmp     short loc_18000F5EC
0x18000f5bc  mov     ebp, [rbx+8]
0x18000f5bf  mov     [rsp+278h+Arguments], r15; Arguments
0x18000f5c4  mov     [rsp+278h+nSize], 100h; nSize
0x18000f5cc  lea     rax, [rsp+278h+Buffer]
0x18000f5d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000f5d6  mov     r9d, 400h; dwLanguageId
0x18000f5dc  mov     r8d, ebp; dwMessageId
0x18000f5df  xor     edx, edx; lpSource
0x18000f5e1  mov     ecx, 1200h; dwFlags
0x18000f5e6  call    cs:__imp_FormatMessageW
0x18000f5ec  lea     rsi, [r14+rsi*2]
0x18000f5f0  mov     r9, [rbx+38h]; wchar_t *
0x18000f5f4  mov     rax, [rbx+88h]
0x18000f5fb  mov     rcx, [rbx+80h]
0x18000f602  mov     rdx, rsi; wchar_t *
0x18000f605  test    r9, r9
0x18000f608  jz      short loc_18000F62C
0x18000f60a  mov     [rsp+278h+Arguments], rax
0x18000f60f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000f614  mov     eax, [rbx+40h]
0x18000f617  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f61b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000f622  mov     rcx, r14; pszDest
0x18000f625  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f62a  jmp     short loc_18000F643
0x18000f62c  mov     [rsp+278h+lpBuffer], rax
0x18000f631  mov     r9, rcx; wchar_t *
0x18000f634  lea     r8, aHsP; "%hs!%p: "
0x18000f63b  mov     rcx, r14; pszDest
0x18000f63e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f643  mov     r14, rax
0x18000f646  mov     r9, [rbx+90h]; wchar_t *
0x18000f64d  test    r9, r9
0x18000f650  jz      short loc_18000F667
0x18000f652  lea     r8, aCallerP; "(caller: %p) "
0x18000f659  mov     rdx, rsi; wchar_t *
0x18000f65c  mov     rcx, rax; pszDest
0x18000f65f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f664  mov     r14, rax
0x18000f667  call    cs:__imp_GetCurrentThreadId
0x18000f66d  lea     rcx, [rsp+278h+Buffer]
0x18000f672  mov     [rsp+278h+var_240], rcx
0x18000f677  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f67b  mov     [rsp+278h+nSize], eax
0x18000f67f  mov     eax, [rbx+44h]
0x18000f682  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f686  mov     r9, rdi; wchar_t *
0x18000f689  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f690  mov     rdx, rsi; wchar_t *
0x18000f693  mov     rcx, r14; pszDest
0x18000f696  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f69b  cmp     [rbx+18h], r15
0x18000f69f  jnz     short loc_18000F6B1
0x18000f6a1  cmp     [rbx+48h], r15
0x18000f6a5  jnz     short loc_18000F6B1
0x18000f6a7  cmp     [rbx+30h], r15
0x18000f6ab  jz      loc_18000F741
0x18000f6b1  lea     r8, asc_1801688A8; "    "
0x18000f6b8  mov     rdx, rsi; wchar_t *
0x18000f6bb  mov     rcx, rax; pszDest
0x18000f6be  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f6c3  mov     r9, [rbx+18h]; wchar_t *
0x18000f6c7  test    r9, r9
0x18000f6ca  jz      short loc_18000F6DE
0x18000f6cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f6d3  mov     rdx, rsi; wchar_t *
0x18000f6d6  mov     rcx, rax; pszDest
0x18000f6d9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f6de  mov     r9, [rbx+48h]; wchar_t *
0x18000f6e2  test    r9, r9
0x18000f6e5  jz      short loc_18000F6F9
0x18000f6e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f6ee  mov     rdx, rsi; wchar_t *
0x18000f6f1  mov     rcx, rax; pszDest
0x18000f6f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f6f9  mov     rcx, [rbx+28h]
0x18000f6fd  mov     r9, [rbx+30h]; wchar_t *
0x18000f701  mov     rdx, rsi; wchar_t *
0x18000f704  test    rcx, rcx
0x18000f707  jz      short loc_18000F71F
0x18000f709  mov     [rsp+278h+lpBuffer], rcx
0x18000f70e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f715  mov     rcx, rax; pszDest
0x18000f718  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f71d  jmp     short loc_18000F741
0x18000f71f  mov     rcx, rax; pszDest
0x18000f722  test    r9, r9
0x18000f725  jz      short loc_18000F735
0x18000f727  lea     r8, aHs; "[%hs]\n"
0x18000f72e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f733  jmp     short loc_18000F741
0x18000f735  lea     r8, asc_180168920; "\n"
0x18000f73c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000f741  xor     eax, eax
0x18000f743  mov     rcx, [rsp+278h+var_38]
0x18000f74b  xor     rcx, rsp; StackCookie
0x18000f74e  call    __security_check_cookie
0x18000f753  mov     rbx, [rsp+278h+arg_18]
0x18000f75b  add     rsp, 250h
0x18000f762  pop     r15
0x18000f764  pop     r14
0x18000f766  pop     rdi
0x18000f767  pop     rsi
0x18000f768  pop     rbp
0x18000f769  retn
```
