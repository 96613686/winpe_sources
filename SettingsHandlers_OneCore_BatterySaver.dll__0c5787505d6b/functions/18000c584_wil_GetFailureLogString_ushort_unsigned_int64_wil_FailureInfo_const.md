# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000c584`
- end: `0x18000c83a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a9a4`
- `0x18000d1e8`
- `0x18000d868`
- `0x1800104d0`

## callees

- `0x180009190`
- `0x180009cf0`
- `0x18000c584`
- `0x18000d4ec`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c737`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c737`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c6b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000c6b6`

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
          v7 = (const char *)&word_180054492;
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
0x18000c584  mov     [rsp+arg_18], rbx
0x18000c589  push    rbp
0x18000c58a  push    rsi
0x18000c58b  push    rdi
0x18000c58c  push    r14
0x18000c58e  push    r15
0x18000c590  sub     rsp, 250h
0x18000c597  mov     rax, cs:__security_cookie
0x18000c59e  xor     rax, rsp
0x18000c5a1  mov     [rsp+278h+var_38], rax
0x18000c5a9  mov     rbx, r8
0x18000c5ac  mov     rsi, rdx
0x18000c5af  mov     r14, rcx
0x18000c5b2  xor     r15d, r15d
0x18000c5b5  test    rdx, rdx
0x18000c5b8  jz      loc_18000C811
0x18000c5be  test    rcx, rcx
0x18000c5c1  jz      loc_18000C811
0x18000c5c7  mov     [rcx], r15w
0x18000c5cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c5d2  test    rax, rax
0x18000c5d5  jz      short loc_18000C5F8
0x18000c5d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000c5de  jz      short loc_18000C5F8
0x18000c5e0  mov     r8, rdx
0x18000c5e3  mov     rdx, rcx
0x18000c5e6  mov     rcx, rbx
0x18000c5e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c5ee  cmp     [r14], r15w
0x18000c5f2  jnz     loc_18000C811
0x18000c5f8  mov     ecx, [rbx]
0x18000c5fa  mov     bpl, 8
0x18000c5fd  test    ecx, ecx
0x18000c5ff  jz      short loc_18000C64A
0x18000c601  sub     ecx, 1
0x18000c604  jz      short loc_18000C632
0x18000c606  sub     ecx, 1
0x18000c609  jz      short loc_18000C622
0x18000c60b  cmp     ecx, 1
0x18000c60e  jz      short loc_18000C619
0x18000c610  lea     rdi, word_180054492
0x18000c617  jmp     short loc_18000C651
0x18000c619  lea     rdi, aFailfast; "FailFast"
0x18000c620  jmp     short loc_18000C651
0x18000c622  lea     rax, aLoghr; "LogHr"
0x18000c629  lea     rdi, aLognt; "LogNt"
0x18000c630  jmp     short loc_18000C640
0x18000c632  lea     rax, aReturnhr; "ReturnHr"
0x18000c639  lea     rdi, aReturnnt; "ReturnNt"
0x18000c640  test    [rbx+4], bpl
0x18000c644  cmovz   rdi, rax
0x18000c648  jmp     short loc_18000C651
0x18000c64a  lea     rdi, aException; "Exception"
0x18000c651  xor     edx, edx; Val
0x18000c653  mov     r8d, 200h; Size
0x18000c659  lea     rcx, [rsp+278h+Buffer]; void *
0x18000c65e  call    memset_0
0x18000c663  test    [rbx+4], bpl
0x18000c667  jz      short loc_18000C68C
0x18000c669  mov     ebp, [rbx+0Ch]
0x18000c66c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000c673  test    rax, rax
0x18000c676  jz      short loc_18000C6BC
0x18000c678  mov     r8d, 100h
0x18000c67e  lea     rdx, [rsp+278h+Buffer]
0x18000c683  mov     ecx, ebp
0x18000c685  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68a  jmp     short loc_18000C6BC
0x18000c68c  mov     ebp, [rbx+8]
0x18000c68f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000c694  mov     [rsp+278h+nSize], 100h; nSize
0x18000c69c  lea     rax, [rsp+278h+Buffer]
0x18000c6a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000c6a6  mov     r9d, 400h; dwLanguageId
0x18000c6ac  mov     r8d, ebp; dwMessageId
0x18000c6af  xor     edx, edx; lpSource
0x18000c6b1  mov     ecx, 1200h; dwFlags
0x18000c6b6  call    cs:__imp_FormatMessageW
0x18000c6bc  lea     rsi, [r14+rsi*2]
0x18000c6c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000c6c4  mov     rax, [rbx+88h]
0x18000c6cb  mov     rcx, [rbx+80h]
0x18000c6d2  mov     rdx, rsi; unsigned __int16 *
0x18000c6d5  test    r9, r9
0x18000c6d8  jz      short loc_18000C6FC
0x18000c6da  mov     [rsp+278h+Arguments], rax
0x18000c6df  mov     qword ptr [rsp+278h+nSize], rcx
0x18000c6e4  mov     eax, [rbx+40h]
0x18000c6e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000c6eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000c6f2  mov     rcx, r14; this
0x18000c6f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c6fa  jmp     short loc_18000C713
0x18000c6fc  mov     [rsp+278h+lpBuffer], rax
0x18000c701  mov     r9, rcx; unsigned __int16 *
0x18000c704  lea     r8, aHsP; "%hs!%p: "
0x18000c70b  mov     rcx, r14; this
0x18000c70e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c713  mov     r14, rax
0x18000c716  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000c71d  test    r9, r9
0x18000c720  jz      short loc_18000C737
0x18000c722  lea     r8, aCallerP; "(caller: %p) "
0x18000c729  mov     rdx, rsi; unsigned __int16 *
0x18000c72c  mov     rcx, rax; this
0x18000c72f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c734  mov     r14, rax
0x18000c737  call    cs:__imp_GetCurrentThreadId
0x18000c73d  lea     rcx, [rsp+278h+Buffer]
0x18000c742  mov     [rsp+278h+var_240], rcx
0x18000c747  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000c74b  mov     [rsp+278h+nSize], eax
0x18000c74f  mov     eax, [rbx+44h]
0x18000c752  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000c756  mov     r9, rdi; unsigned __int16 *
0x18000c759  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000c760  mov     rdx, rsi; unsigned __int16 *
0x18000c763  mov     rcx, r14; this
0x18000c766  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c76b  cmp     [rbx+18h], r15
0x18000c76f  jnz     short loc_18000C781
0x18000c771  cmp     [rbx+48h], r15
0x18000c775  jnz     short loc_18000C781
0x18000c777  cmp     [rbx+30h], r15
0x18000c77b  jz      loc_18000C811
0x18000c781  lea     r8, asc_180054580; "    "
0x18000c788  mov     rdx, rsi; unsigned __int16 *
0x18000c78b  mov     rcx, rax; this
0x18000c78e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c793  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000c797  test    r9, r9
0x18000c79a  jz      short loc_18000C7AE
0x18000c79c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000c7a3  mov     rdx, rsi; unsigned __int16 *
0x18000c7a6  mov     rcx, rax; this
0x18000c7a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c7ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000c7b2  test    r9, r9
0x18000c7b5  jz      short loc_18000C7C9
0x18000c7b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000c7be  mov     rdx, rsi; unsigned __int16 *
0x18000c7c1  mov     rcx, rax; this
0x18000c7c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c7c9  mov     rcx, [rbx+28h]
0x18000c7cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000c7d1  mov     rdx, rsi; unsigned __int16 *
0x18000c7d4  test    rcx, rcx
0x18000c7d7  jz      short loc_18000C7EF
0x18000c7d9  mov     [rsp+278h+lpBuffer], rcx
0x18000c7de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000c7e5  mov     rcx, rax; this
0x18000c7e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c7ed  jmp     short loc_18000C811
0x18000c7ef  mov     rcx, rax; this
0x18000c7f2  test    r9, r9
0x18000c7f5  jz      short loc_18000C805
0x18000c7f7  lea     r8, aHs; "[%hs]\n"
0x18000c7fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c803  jmp     short loc_18000C811
0x18000c805  lea     r8, asc_1800545F8; "\n"
0x18000c80c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000c811  xor     eax, eax
0x18000c813  mov     rcx, [rsp+278h+var_38]
0x18000c81b  xor     rcx, rsp; StackCookie
0x18000c81e  call    __security_check_cookie
0x18000c823  mov     rbx, [rsp+278h+arg_18]
0x18000c82b  add     rsp, 250h
0x18000c832  pop     r15
0x18000c834  pop     r14
0x18000c836  pop     rdi
0x18000c837  pop     rsi
0x18000c838  pop     rbp
0x18000c839  retn
```
