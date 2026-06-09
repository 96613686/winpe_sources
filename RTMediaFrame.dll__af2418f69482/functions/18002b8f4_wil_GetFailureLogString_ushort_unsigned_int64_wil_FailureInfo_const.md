# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002b8f4`
- end: `0x18002bbaa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800285fc`
- `0x18002c8c8`
- `0x180030a20`

## callees

- `0x180026920`
- `0x180027490`
- `0x18002b8f4`
- `0x18002cbc8`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002ba26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002ba26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002baa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002baa7`

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
          v7 = (const char *)&dword_180060FE4;
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
0x18002b8f4  mov     [rsp+arg_18], rbx
0x18002b8f9  push    rbp
0x18002b8fa  push    rsi
0x18002b8fb  push    rdi
0x18002b8fc  push    r14
0x18002b8fe  push    r15
0x18002b900  sub     rsp, 250h
0x18002b907  mov     rax, cs:__security_cookie
0x18002b90e  xor     rax, rsp
0x18002b911  mov     [rsp+278h+var_38], rax
0x18002b919  mov     rbx, r8
0x18002b91c  mov     rsi, rdx
0x18002b91f  mov     r14, rcx
0x18002b922  xor     r15d, r15d
0x18002b925  test    rdx, rdx
0x18002b928  jz      loc_18002BB81
0x18002b92e  test    rcx, rcx
0x18002b931  jz      loc_18002BB81
0x18002b937  mov     [rcx], r15w
0x18002b93b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b942  test    rax, rax
0x18002b945  jz      short loc_18002B968
0x18002b947  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002b94e  jz      short loc_18002B968
0x18002b950  mov     r8, rdx
0x18002b953  mov     rdx, rcx
0x18002b956  mov     rcx, rbx
0x18002b959  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b95e  cmp     [r14], r15w
0x18002b962  jnz     loc_18002BB81
0x18002b968  mov     ecx, [rbx]
0x18002b96a  mov     bpl, 8
0x18002b96d  test    ecx, ecx
0x18002b96f  jz      short loc_18002B9BA
0x18002b971  sub     ecx, 1
0x18002b974  jz      short loc_18002B9A2
0x18002b976  sub     ecx, 1
0x18002b979  jz      short loc_18002B992
0x18002b97b  cmp     ecx, 1
0x18002b97e  jz      short loc_18002B989
0x18002b980  lea     rdi, dword_180060FE4
0x18002b987  jmp     short loc_18002B9C1
0x18002b989  lea     rdi, aFailfast; "FailFast"
0x18002b990  jmp     short loc_18002B9C1
0x18002b992  lea     rax, aLoghr; "LogHr"
0x18002b999  lea     rdi, aLognt; "LogNt"
0x18002b9a0  jmp     short loc_18002B9B0
0x18002b9a2  lea     rax, aReturnhr; "ReturnHr"
0x18002b9a9  lea     rdi, aReturnnt; "ReturnNt"
0x18002b9b0  test    [rbx+4], bpl
0x18002b9b4  cmovz   rdi, rax
0x18002b9b8  jmp     short loc_18002B9C1
0x18002b9ba  lea     rdi, aException; "Exception"
0x18002b9c1  xor     edx, edx; Val
0x18002b9c3  mov     r8d, 200h; Size
0x18002b9c9  lea     rcx, [rsp+278h+Buffer]; void *
0x18002b9ce  call    memset_0
0x18002b9d3  test    [rbx+4], bpl
0x18002b9d7  jz      short loc_18002B9FC
0x18002b9d9  mov     ebp, [rbx+0Ch]
0x18002b9dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002b9e3  test    rax, rax
0x18002b9e6  jz      short loc_18002BA2C
0x18002b9e8  mov     r8d, 100h
0x18002b9ee  lea     rdx, [rsp+278h+Buffer]
0x18002b9f3  mov     ecx, ebp
0x18002b9f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b9fa  jmp     short loc_18002BA2C
0x18002b9fc  mov     ebp, [rbx+8]
0x18002b9ff  mov     [rsp+278h+Arguments], r15; Arguments
0x18002ba04  mov     [rsp+278h+nSize], 100h; nSize
0x18002ba0c  lea     rax, [rsp+278h+Buffer]
0x18002ba11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002ba16  mov     r9d, 400h; dwLanguageId
0x18002ba1c  mov     r8d, ebp; dwMessageId
0x18002ba1f  xor     edx, edx; lpSource
0x18002ba21  mov     ecx, 1200h; dwFlags
0x18002ba26  call    cs:__imp_FormatMessageW
0x18002ba2c  lea     rsi, [r14+rsi*2]
0x18002ba30  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002ba34  mov     rax, [rbx+88h]
0x18002ba3b  mov     rcx, [rbx+80h]
0x18002ba42  mov     rdx, rsi; unsigned __int16 *
0x18002ba45  test    r9, r9
0x18002ba48  jz      short loc_18002BA6C
0x18002ba4a  mov     [rsp+278h+Arguments], rax
0x18002ba4f  mov     qword ptr [rsp+278h+nSize], rcx
0x18002ba54  mov     eax, [rbx+40h]
0x18002ba57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002ba5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002ba62  mov     rcx, r14; pszDest
0x18002ba65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002ba6a  jmp     short loc_18002BA83
0x18002ba6c  mov     [rsp+278h+lpBuffer], rax
0x18002ba71  mov     r9, rcx; unsigned __int16 *
0x18002ba74  lea     r8, aHsP; "%hs!%p: "
0x18002ba7b  mov     rcx, r14; pszDest
0x18002ba7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002ba83  mov     r14, rax
0x18002ba86  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002ba8d  test    r9, r9
0x18002ba90  jz      short loc_18002BAA7
0x18002ba92  lea     r8, aCallerP; "(caller: %p) "
0x18002ba99  mov     rdx, rsi; unsigned __int16 *
0x18002ba9c  mov     rcx, rax; pszDest
0x18002ba9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002baa4  mov     r14, rax
0x18002baa7  call    cs:__imp_GetCurrentThreadId
0x18002baad  lea     rcx, [rsp+278h+Buffer]
0x18002bab2  mov     [rsp+278h+var_240], rcx
0x18002bab7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002babb  mov     [rsp+278h+nSize], eax
0x18002babf  mov     eax, [rbx+44h]
0x18002bac2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002bac6  mov     r9, rdi; unsigned __int16 *
0x18002bac9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002bad0  mov     rdx, rsi; unsigned __int16 *
0x18002bad3  mov     rcx, r14; pszDest
0x18002bad6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002badb  cmp     [rbx+18h], r15
0x18002badf  jnz     short loc_18002BAF1
0x18002bae1  cmp     [rbx+48h], r15
0x18002bae5  jnz     short loc_18002BAF1
0x18002bae7  cmp     [rbx+30h], r15
0x18002baeb  jz      loc_18002BB81
0x18002baf1  lea     r8, asc_1800610D0; "    "
0x18002baf8  mov     rdx, rsi; unsigned __int16 *
0x18002bafb  mov     rcx, rax; pszDest
0x18002bafe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bb03  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002bb07  test    r9, r9
0x18002bb0a  jz      short loc_18002BB1E
0x18002bb0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002bb13  mov     rdx, rsi; unsigned __int16 *
0x18002bb16  mov     rcx, rax; pszDest
0x18002bb19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bb1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002bb22  test    r9, r9
0x18002bb25  jz      short loc_18002BB39
0x18002bb27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002bb2e  mov     rdx, rsi; unsigned __int16 *
0x18002bb31  mov     rcx, rax; pszDest
0x18002bb34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bb39  mov     rcx, [rbx+28h]
0x18002bb3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002bb41  mov     rdx, rsi; unsigned __int16 *
0x18002bb44  test    rcx, rcx
0x18002bb47  jz      short loc_18002BB5F
0x18002bb49  mov     [rsp+278h+lpBuffer], rcx
0x18002bb4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002bb55  mov     rcx, rax; pszDest
0x18002bb58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bb5d  jmp     short loc_18002BB81
0x18002bb5f  mov     rcx, rax; pszDest
0x18002bb62  test    r9, r9
0x18002bb65  jz      short loc_18002BB75
0x18002bb67  lea     r8, aHs; "[%hs]\n"
0x18002bb6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bb73  jmp     short loc_18002BB81
0x18002bb75  lea     r8, asc_180061148; "\n"
0x18002bb7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002bb81  xor     eax, eax
0x18002bb83  mov     rcx, [rsp+278h+var_38]
0x18002bb8b  xor     rcx, rsp; StackCookie
0x18002bb8e  call    __security_check_cookie
0x18002bb93  mov     rbx, [rsp+278h+arg_18]
0x18002bb9b  add     rsp, 250h
0x18002bba2  pop     r15
0x18002bba4  pop     r14
0x18002bba6  pop     rdi
0x18002bba7  pop     rsi
0x18002bba8  pop     rbp
0x18002bba9  retn
```
