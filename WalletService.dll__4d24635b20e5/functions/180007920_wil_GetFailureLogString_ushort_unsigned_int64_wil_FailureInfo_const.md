# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007920`
- end: `0x180007bd6`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e14`
- `0x180008544`
- `0x1800324f0`

## callees

- `0x180007920`
- `0x180008824`
- `0x180043052`
- `0x180043090`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007a52`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007a52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ad3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ad3`

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
          v8 = (const char *)&qword_18004A280;
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
0x180007920  mov     [rsp+arg_18], rbx
0x180007925  push    rbp
0x180007926  push    rsi
0x180007927  push    rdi
0x180007928  push    r14
0x18000792a  push    r15
0x18000792c  sub     rsp, 250h
0x180007933  mov     rax, cs:__security_cookie
0x18000793a  xor     rax, rsp
0x18000793d  mov     [rsp+278h+var_38], rax
0x180007945  xor     r15d, r15d
0x180007948  mov     rbx, r8
0x18000794b  mov     rsi, rdx
0x18000794e  mov     r14, rcx
0x180007951  test    rdx, rdx
0x180007954  jz      loc_180007BAD
0x18000795a  test    rcx, rcx
0x18000795d  jz      loc_180007BAD
0x180007963  mov     rax, cs:g_pfnResultLoggingCallback
0x18000796a  mov     [rcx], r15w
0x18000796e  test    rax, rax
0x180007971  jz      short loc_180007994
0x180007973  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000797a  jz      short loc_180007994
0x18000797c  mov     r8, rdx
0x18000797f  mov     rdx, rcx
0x180007982  mov     rcx, rbx
0x180007985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000798a  cmp     [r14], r15w
0x18000798e  jnz     loc_180007BAD
0x180007994  mov     ecx, [rbx]
0x180007996  mov     bpl, 8
0x180007999  test    ecx, ecx
0x18000799b  jz      short loc_1800079E6
0x18000799d  sub     ecx, 1
0x1800079a0  jz      short loc_1800079CE
0x1800079a2  sub     ecx, 1
0x1800079a5  jz      short loc_1800079BE
0x1800079a7  cmp     ecx, 1
0x1800079aa  jz      short loc_1800079B5
0x1800079ac  lea     rdi, qword_18004A280
0x1800079b3  jmp     short loc_1800079ED
0x1800079b5  lea     rdi, aFailfast; "FailFast"
0x1800079bc  jmp     short loc_1800079ED
0x1800079be  lea     rax, aLoghr; "LogHr"
0x1800079c5  lea     rdi, aLognt; "LogNt"
0x1800079cc  jmp     short loc_1800079DC
0x1800079ce  lea     rax, aReturnhr; "ReturnHr"
0x1800079d5  lea     rdi, aReturnnt; "ReturnNt"
0x1800079dc  test    [rbx+4], bpl
0x1800079e0  cmovz   rdi, rax
0x1800079e4  jmp     short loc_1800079ED
0x1800079e6  lea     rdi, aException; "Exception"
0x1800079ed  xor     edx, edx; Val
0x1800079ef  lea     rcx, [rsp+278h+Buffer]; void *
0x1800079f4  mov     r8d, 200h; Size
0x1800079fa  call    memset_0
0x1800079ff  test    [rbx+4], bpl
0x180007a03  jz      short loc_180007A28
0x180007a05  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007a0c  mov     ebp, [rbx+0Ch]
0x180007a0f  test    rax, rax
0x180007a12  jz      short loc_180007A58
0x180007a14  mov     r8d, 100h
0x180007a1a  lea     rdx, [rsp+278h+Buffer]
0x180007a1f  mov     ecx, ebp
0x180007a21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a26  jmp     short loc_180007A58
0x180007a28  mov     ebp, [rbx+8]
0x180007a2b  lea     rax, [rsp+278h+Buffer]
0x180007a30  mov     [rsp+278h+Arguments], r15; Arguments
0x180007a35  mov     r8d, ebp; dwMessageId
0x180007a38  mov     [rsp+278h+nSize], 100h; nSize
0x180007a40  mov     r9d, 400h; dwLanguageId
0x180007a46  xor     edx, edx; lpSource
0x180007a48  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007a4d  mov     ecx, 1200h; dwFlags
0x180007a52  call    cs:__imp_FormatMessageW
0x180007a58  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007a5c  lea     rsi, [r14+rsi*2]
0x180007a60  mov     rax, [rbx+88h]
0x180007a67  mov     rdx, rsi; unsigned __int16 *
0x180007a6a  mov     rcx, [rbx+80h]
0x180007a71  test    r9, r9
0x180007a74  jz      short loc_180007A98
0x180007a76  mov     [rsp+278h+Arguments], rax
0x180007a7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007a82  mov     eax, [rbx+40h]
0x180007a85  mov     qword ptr [rsp+278h+nSize], rcx
0x180007a8a  mov     rcx, r14; pszDest
0x180007a8d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007a91  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a96  jmp     short loc_180007AAF
0x180007a98  mov     r9, rcx; unsigned __int16 *
0x180007a9b  mov     [rsp+278h+lpBuffer], rax
0x180007aa0  mov     rcx, r14; pszDest
0x180007aa3  lea     r8, aHsP; "%hs!%p: "
0x180007aaa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007aaf  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007ab6  mov     r14, rax
0x180007ab9  test    r9, r9
0x180007abc  jz      short loc_180007AD3
0x180007abe  lea     r8, aCallerP; "(caller: %p) "
0x180007ac5  mov     rdx, rsi; unsigned __int16 *
0x180007ac8  mov     rcx, rax; pszDest
0x180007acb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ad0  mov     r14, rax
0x180007ad3  call    cs:__imp_GetCurrentThreadId
0x180007ad9  lea     rcx, [rsp+278h+Buffer]
0x180007ade  mov     r9, rdi; unsigned __int16 *
0x180007ae1  mov     [rsp+278h+var_240], rcx
0x180007ae6  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007aed  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007af1  mov     rdx, rsi; unsigned __int16 *
0x180007af4  mov     [rsp+278h+nSize], eax
0x180007af8  mov     rcx, r14; pszDest
0x180007afb  mov     eax, [rbx+44h]
0x180007afe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007b02  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b07  cmp     [rbx+18h], r15
0x180007b0b  jnz     short loc_180007B1D
0x180007b0d  cmp     [rbx+48h], r15
0x180007b11  jnz     short loc_180007B1D
0x180007b13  cmp     [rbx+30h], r15
0x180007b17  jz      loc_180007BAD
0x180007b1d  lea     r8, asc_180049FA0; "    "
0x180007b24  mov     rdx, rsi; unsigned __int16 *
0x180007b27  mov     rcx, rax; pszDest
0x180007b2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b2f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007b33  test    r9, r9
0x180007b36  jz      short loc_180007B4A
0x180007b38  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007b3f  mov     rdx, rsi; unsigned __int16 *
0x180007b42  mov     rcx, rax; pszDest
0x180007b45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b4a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007b4e  test    r9, r9
0x180007b51  jz      short loc_180007B65
0x180007b53  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007b5a  mov     rdx, rsi; unsigned __int16 *
0x180007b5d  mov     rcx, rax; pszDest
0x180007b60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b65  mov     rcx, [rbx+28h]
0x180007b69  mov     rdx, rsi; unsigned __int16 *
0x180007b6c  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007b70  test    rcx, rcx
0x180007b73  jz      short loc_180007B8B
0x180007b75  mov     [rsp+278h+lpBuffer], rcx
0x180007b7a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007b81  mov     rcx, rax; pszDest
0x180007b84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b89  jmp     short loc_180007BAD
0x180007b8b  mov     rcx, rax; pszDest
0x180007b8e  test    r9, r9
0x180007b91  jz      short loc_180007BA1
0x180007b93  lea     r8, aHs; "[%hs]\n"
0x180007b9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b9f  jmp     short loc_180007BAD
0x180007ba1  lea     r8, asc_18004A018; "\n"
0x180007ba8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007bad  xor     eax, eax
0x180007baf  mov     rcx, [rsp+278h+var_38]
0x180007bb7  xor     rcx, rsp; StackCookie
0x180007bba  call    __security_check_cookie
0x180007bbf  mov     rbx, [rsp+278h+arg_18]
0x180007bc7  add     rsp, 250h
0x180007bce  pop     r15
0x180007bd0  pop     r14
0x180007bd2  pop     rdi
0x180007bd3  pop     rsi
0x180007bd4  pop     rbp
0x180007bd5  retn
```
