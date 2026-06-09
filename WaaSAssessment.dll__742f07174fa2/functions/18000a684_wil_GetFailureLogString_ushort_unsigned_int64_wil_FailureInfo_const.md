# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a684`
- end: `0x18000a93a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000b810`
- `0x18000bbe0`
- `0x18000be48`
- `0x18000eac0`
- `0x180010a28`

## callees

- `0x18000a684`
- `0x18000ac30`
- `0x18001972e`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a837`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a837`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a7b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a7b6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
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
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
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
          v7 = (const char *)&word_18001F07E;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x18000a684  mov     [rsp+arg_18], rbx
0x18000a689  push    rbp
0x18000a68a  push    rsi
0x18000a68b  push    rdi
0x18000a68c  push    r14
0x18000a68e  push    r15
0x18000a690  sub     rsp, 250h
0x18000a697  mov     rax, cs:__security_cookie
0x18000a69e  xor     rax, rsp
0x18000a6a1  mov     [rsp+278h+var_38], rax
0x18000a6a9  mov     rbx, r8
0x18000a6ac  mov     rsi, rdx
0x18000a6af  mov     r14, rcx
0x18000a6b2  xor     r15d, r15d
0x18000a6b5  test    rdx, rdx
0x18000a6b8  jz      loc_18000A911
0x18000a6be  test    rcx, rcx
0x18000a6c1  jz      loc_18000A911
0x18000a6c7  mov     [rcx], r15w
0x18000a6cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a6d2  test    rax, rax
0x18000a6d5  jz      short loc_18000A6F8
0x18000a6d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a6de  jz      short loc_18000A6F8
0x18000a6e0  mov     r8, rdx
0x18000a6e3  mov     rdx, rcx
0x18000a6e6  mov     rcx, rbx
0x18000a6e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6ee  cmp     [r14], r15w
0x18000a6f2  jnz     loc_18000A911
0x18000a6f8  mov     ecx, [rbx]
0x18000a6fa  mov     bpl, 8
0x18000a6fd  test    ecx, ecx
0x18000a6ff  jz      short loc_18000A74A
0x18000a701  sub     ecx, 1
0x18000a704  jz      short loc_18000A732
0x18000a706  sub     ecx, 1
0x18000a709  jz      short loc_18000A722
0x18000a70b  cmp     ecx, 1
0x18000a70e  jz      short loc_18000A719
0x18000a710  lea     rdi, word_18001F07E
0x18000a717  jmp     short loc_18000A751
0x18000a719  lea     rdi, aFailfast; "FailFast"
0x18000a720  jmp     short loc_18000A751
0x18000a722  lea     rax, aLoghr; "LogHr"
0x18000a729  lea     rdi, aLognt; "LogNt"
0x18000a730  jmp     short loc_18000A740
0x18000a732  lea     rax, aReturnhr; "ReturnHr"
0x18000a739  lea     rdi, aReturnnt; "ReturnNt"
0x18000a740  test    [rbx+4], bpl
0x18000a744  cmovz   rdi, rax
0x18000a748  jmp     short loc_18000A751
0x18000a74a  lea     rdi, aException; "Exception"
0x18000a751  xor     edx, edx; Val
0x18000a753  mov     r8d, 200h; Size
0x18000a759  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a75e  call    memset_0
0x18000a763  test    [rbx+4], bpl
0x18000a767  jz      short loc_18000A78C
0x18000a769  mov     ebp, [rbx+0Ch]
0x18000a76c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a773  test    rax, rax
0x18000a776  jz      short loc_18000A7BC
0x18000a778  mov     r8d, 100h
0x18000a77e  lea     rdx, [rsp+278h+Buffer]
0x18000a783  mov     ecx, ebp
0x18000a785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a78a  jmp     short loc_18000A7BC
0x18000a78c  mov     ebp, [rbx+8]
0x18000a78f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a794  mov     [rsp+278h+nSize], 100h; nSize
0x18000a79c  lea     rax, [rsp+278h+Buffer]
0x18000a7a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a7a6  mov     r9d, 400h; dwLanguageId
0x18000a7ac  mov     r8d, ebp; dwMessageId
0x18000a7af  xor     edx, edx; lpSource
0x18000a7b1  mov     ecx, 1200h; dwFlags
0x18000a7b6  call    cs:__imp_FormatMessageW
0x18000a7bc  lea     rsi, [r14+rsi*2]
0x18000a7c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a7c4  mov     rax, [rbx+88h]
0x18000a7cb  mov     rcx, [rbx+80h]
0x18000a7d2  mov     rdx, rsi; unsigned __int16 *
0x18000a7d5  test    r9, r9
0x18000a7d8  jz      short loc_18000A7FC
0x18000a7da  mov     [rsp+278h+Arguments], rax
0x18000a7df  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a7e4  mov     eax, [rbx+40h]
0x18000a7e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a7eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a7f2  mov     rcx, r14; this
0x18000a7f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a7fa  jmp     short loc_18000A813
0x18000a7fc  mov     [rsp+278h+lpBuffer], rax
0x18000a801  mov     r9, rcx; unsigned __int16 *
0x18000a804  lea     r8, aHsP; "%hs!%p: "
0x18000a80b  mov     rcx, r14; this
0x18000a80e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a813  mov     r14, rax
0x18000a816  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a81d  test    r9, r9
0x18000a820  jz      short loc_18000A837
0x18000a822  lea     r8, aCallerP; "(caller: %p) "
0x18000a829  mov     rdx, rsi; unsigned __int16 *
0x18000a82c  mov     rcx, rax; this
0x18000a82f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a834  mov     r14, rax
0x18000a837  call    cs:__imp_GetCurrentThreadId
0x18000a83d  lea     rcx, [rsp+278h+Buffer]
0x18000a842  mov     [rsp+278h+var_240], rcx
0x18000a847  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a84b  mov     [rsp+278h+nSize], eax
0x18000a84f  mov     eax, [rbx+44h]
0x18000a852  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a856  mov     r9, rdi; unsigned __int16 *
0x18000a859  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a860  mov     rdx, rsi; unsigned __int16 *
0x18000a863  mov     rcx, r14; this
0x18000a866  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a86b  cmp     [rbx+18h], r15
0x18000a86f  jnz     short loc_18000A881
0x18000a871  cmp     [rbx+48h], r15
0x18000a875  jnz     short loc_18000A881
0x18000a877  cmp     [rbx+30h], r15
0x18000a87b  jz      loc_18000A911
0x18000a881  lea     r8, asc_18001F168; "    "
0x18000a888  mov     rdx, rsi; unsigned __int16 *
0x18000a88b  mov     rcx, rax; this
0x18000a88e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a893  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a897  test    r9, r9
0x18000a89a  jz      short loc_18000A8AE
0x18000a89c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a8a3  mov     rdx, rsi; unsigned __int16 *
0x18000a8a6  mov     rcx, rax; this
0x18000a8a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a8ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a8b2  test    r9, r9
0x18000a8b5  jz      short loc_18000A8C9
0x18000a8b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a8be  mov     rdx, rsi; unsigned __int16 *
0x18000a8c1  mov     rcx, rax; this
0x18000a8c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a8c9  mov     rcx, [rbx+28h]
0x18000a8cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a8d1  mov     rdx, rsi; unsigned __int16 *
0x18000a8d4  test    rcx, rcx
0x18000a8d7  jz      short loc_18000A8EF
0x18000a8d9  mov     [rsp+278h+lpBuffer], rcx
0x18000a8de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000a8e5  mov     rcx, rax; this
0x18000a8e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a8ed  jmp     short loc_18000A911
0x18000a8ef  mov     rcx, rax; this
0x18000a8f2  test    r9, r9
0x18000a8f5  jz      short loc_18000A905
0x18000a8f7  lea     r8, aHs; "[%hs]\n"
0x18000a8fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a903  jmp     short loc_18000A911
0x18000a905  lea     r8, asc_18001F1E0; "\n"
0x18000a90c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a911  xor     eax, eax
0x18000a913  mov     rcx, [rsp+278h+var_38]
0x18000a91b  xor     rcx, rsp; StackCookie
0x18000a91e  call    __security_check_cookie
0x18000a923  mov     rbx, [rsp+278h+arg_18]
0x18000a92b  add     rsp, 250h
0x18000a932  pop     r15
0x18000a934  pop     r14
0x18000a936  pop     rdi
0x18000a937  pop     rsi
0x18000a938  pop     rbp
0x18000a939  retn
```
