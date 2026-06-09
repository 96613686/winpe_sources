# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180027604`
- end: `0x1800278ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800246d0`
- `0x180027ee0`
- `0x180029e00`

## callees

- `0x18001f650`
- `0x18001ffd4`
- `0x180027604`
- `0x1800281e4`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180027736`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180027736`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800277b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800277b7`

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
          v7 = (const char *)&word_18003DB96;
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
0x180027604  mov     [rsp+arg_18], rbx
0x180027609  push    rbp
0x18002760a  push    rsi
0x18002760b  push    rdi
0x18002760c  push    r14
0x18002760e  push    r15
0x180027610  sub     rsp, 250h
0x180027617  mov     rax, cs:__security_cookie
0x18002761e  xor     rax, rsp
0x180027621  mov     [rsp+278h+var_38], rax
0x180027629  mov     rbx, r8
0x18002762c  mov     rsi, rdx
0x18002762f  mov     r14, rcx
0x180027632  xor     r15d, r15d
0x180027635  test    rdx, rdx
0x180027638  jz      loc_180027891
0x18002763e  test    rcx, rcx
0x180027641  jz      loc_180027891
0x180027647  mov     [rcx], r15w
0x18002764b  mov     rax, cs:g_pfnResultLoggingCallback
0x180027652  test    rax, rax
0x180027655  jz      short loc_180027678
0x180027657  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002765e  jz      short loc_180027678
0x180027660  mov     r8, rdx
0x180027663  mov     rdx, rcx
0x180027666  mov     rcx, rbx
0x180027669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002766e  cmp     [r14], r15w
0x180027672  jnz     loc_180027891
0x180027678  mov     ecx, [rbx]
0x18002767a  mov     bpl, 8
0x18002767d  test    ecx, ecx
0x18002767f  jz      short loc_1800276CA
0x180027681  sub     ecx, 1
0x180027684  jz      short loc_1800276B2
0x180027686  sub     ecx, 1
0x180027689  jz      short loc_1800276A2
0x18002768b  cmp     ecx, 1
0x18002768e  jz      short loc_180027699
0x180027690  lea     rdi, word_18003DB96
0x180027697  jmp     short loc_1800276D1
0x180027699  lea     rdi, aFailfast; "FailFast"
0x1800276a0  jmp     short loc_1800276D1
0x1800276a2  lea     rax, aLoghr; "LogHr"
0x1800276a9  lea     rdi, aLognt; "LogNt"
0x1800276b0  jmp     short loc_1800276C0
0x1800276b2  lea     rax, aReturnhr; "ReturnHr"
0x1800276b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800276c0  test    [rbx+4], bpl
0x1800276c4  cmovz   rdi, rax
0x1800276c8  jmp     short loc_1800276D1
0x1800276ca  lea     rdi, aException; "Exception"
0x1800276d1  xor     edx, edx; Val
0x1800276d3  mov     r8d, 200h; Size
0x1800276d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800276de  call    memset_0
0x1800276e3  test    [rbx+4], bpl
0x1800276e7  jz      short loc_18002770C
0x1800276e9  mov     ebp, [rbx+0Ch]
0x1800276ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800276f3  test    rax, rax
0x1800276f6  jz      short loc_18002773C
0x1800276f8  mov     r8d, 100h
0x1800276fe  lea     rdx, [rsp+278h+Buffer]
0x180027703  mov     ecx, ebp
0x180027705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002770a  jmp     short loc_18002773C
0x18002770c  mov     ebp, [rbx+8]
0x18002770f  mov     [rsp+278h+Arguments], r15; Arguments
0x180027714  mov     [rsp+278h+nSize], 100h; nSize
0x18002771c  lea     rax, [rsp+278h+Buffer]
0x180027721  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180027726  mov     r9d, 400h; dwLanguageId
0x18002772c  mov     r8d, ebp; dwMessageId
0x18002772f  xor     edx, edx; lpSource
0x180027731  mov     ecx, 1200h; dwFlags
0x180027736  call    cs:__imp_FormatMessageW
0x18002773c  lea     rsi, [r14+rsi*2]
0x180027740  mov     r9, [rbx+38h]; unsigned __int16 *
0x180027744  mov     rax, [rbx+88h]
0x18002774b  mov     rcx, [rbx+80h]
0x180027752  mov     rdx, rsi; unsigned __int16 *
0x180027755  test    r9, r9
0x180027758  jz      short loc_18002777C
0x18002775a  mov     [rsp+278h+Arguments], rax
0x18002775f  mov     qword ptr [rsp+278h+nSize], rcx
0x180027764  mov     eax, [rbx+40h]
0x180027767  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002776b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180027772  mov     rcx, r14; pszDest
0x180027775  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002777a  jmp     short loc_180027793
0x18002777c  mov     [rsp+278h+lpBuffer], rax
0x180027781  mov     r9, rcx; unsigned __int16 *
0x180027784  lea     r8, aHsP; "%hs!%p: "
0x18002778b  mov     rcx, r14; pszDest
0x18002778e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027793  mov     r14, rax
0x180027796  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002779d  test    r9, r9
0x1800277a0  jz      short loc_1800277B7
0x1800277a2  lea     r8, aCallerP; "(caller: %p) "
0x1800277a9  mov     rdx, rsi; unsigned __int16 *
0x1800277ac  mov     rcx, rax; pszDest
0x1800277af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800277b4  mov     r14, rax
0x1800277b7  call    cs:__imp_GetCurrentThreadId
0x1800277bd  lea     rcx, [rsp+278h+Buffer]
0x1800277c2  mov     [rsp+278h+var_240], rcx
0x1800277c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800277cb  mov     [rsp+278h+nSize], eax
0x1800277cf  mov     eax, [rbx+44h]
0x1800277d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800277d6  mov     r9, rdi; unsigned __int16 *
0x1800277d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800277e0  mov     rdx, rsi; unsigned __int16 *
0x1800277e3  mov     rcx, r14; pszDest
0x1800277e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800277eb  cmp     [rbx+18h], r15
0x1800277ef  jnz     short loc_180027801
0x1800277f1  cmp     [rbx+48h], r15
0x1800277f5  jnz     short loc_180027801
0x1800277f7  cmp     [rbx+30h], r15
0x1800277fb  jz      loc_180027891
0x180027801  lea     r8, asc_18003DE80; "    "
0x180027808  mov     rdx, rsi; unsigned __int16 *
0x18002780b  mov     rcx, rax; pszDest
0x18002780e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027813  mov     r9, [rbx+18h]; unsigned __int16 *
0x180027817  test    r9, r9
0x18002781a  jz      short loc_18002782E
0x18002781c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180027823  mov     rdx, rsi; unsigned __int16 *
0x180027826  mov     rcx, rax; pszDest
0x180027829  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002782e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180027832  test    r9, r9
0x180027835  jz      short loc_180027849
0x180027837  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002783e  mov     rdx, rsi; unsigned __int16 *
0x180027841  mov     rcx, rax; pszDest
0x180027844  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027849  mov     rcx, [rbx+28h]
0x18002784d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180027851  mov     rdx, rsi; unsigned __int16 *
0x180027854  test    rcx, rcx
0x180027857  jz      short loc_18002786F
0x180027859  mov     [rsp+278h+lpBuffer], rcx
0x18002785e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180027865  mov     rcx, rax; pszDest
0x180027868  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002786d  jmp     short loc_180027891
0x18002786f  mov     rcx, rax; pszDest
0x180027872  test    r9, r9
0x180027875  jz      short loc_180027885
0x180027877  lea     r8, aHs; "[%hs]\n"
0x18002787e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027883  jmp     short loc_180027891
0x180027885  lea     r8, asc_18003DEF8; "\n"
0x18002788c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180027891  xor     eax, eax
0x180027893  mov     rcx, [rsp+278h+var_38]
0x18002789b  xor     rcx, rsp; StackCookie
0x18002789e  call    __security_check_cookie
0x1800278a3  mov     rbx, [rsp+278h+arg_18]
0x1800278ab  add     rsp, 250h
0x1800278b2  pop     r15
0x1800278b4  pop     r14
0x1800278b6  pop     rdi
0x1800278b7  pop     rsi
0x1800278b8  pop     rbp
0x1800278b9  retn
```
