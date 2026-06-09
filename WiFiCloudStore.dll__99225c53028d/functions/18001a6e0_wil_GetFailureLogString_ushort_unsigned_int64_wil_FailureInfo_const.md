# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001a6e0`
- end: `0x18001a996`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001f0d8`
- `0x180024900`
- `0x18002cad0`

## callees

- `0x18001a6e0`
- `0x18001a99c`
- `0x18002a030`
- `0x18002aad0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a893`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001a893`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a812`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001a812`

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
          v7 = (const char *)&dword_180043B4C;
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
0x18001a6e0  mov     [rsp+arg_18], rbx
0x18001a6e5  push    rbp
0x18001a6e6  push    rsi
0x18001a6e7  push    rdi
0x18001a6e8  push    r14
0x18001a6ea  push    r15
0x18001a6ec  sub     rsp, 250h
0x18001a6f3  mov     rax, cs:__security_cookie
0x18001a6fa  xor     rax, rsp
0x18001a6fd  mov     [rsp+278h+var_38], rax
0x18001a705  mov     rbx, r8
0x18001a708  mov     rsi, rdx
0x18001a70b  mov     r14, rcx
0x18001a70e  xor     r15d, r15d
0x18001a711  test    rdx, rdx
0x18001a714  jz      loc_18001A96D
0x18001a71a  test    rcx, rcx
0x18001a71d  jz      loc_18001A96D
0x18001a723  mov     [rcx], r15w
0x18001a727  mov     rax, cs:g_pfnResultLoggingCallback
0x18001a72e  test    rax, rax
0x18001a731  jz      short loc_18001A754
0x18001a733  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001a73a  jz      short loc_18001A754
0x18001a73c  mov     r8, rdx
0x18001a73f  mov     rdx, rcx
0x18001a742  mov     rcx, rbx
0x18001a745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a74a  cmp     [r14], r15w
0x18001a74e  jnz     loc_18001A96D
0x18001a754  mov     ecx, [rbx]
0x18001a756  mov     bpl, 8
0x18001a759  test    ecx, ecx
0x18001a75b  jz      short loc_18001A7A6
0x18001a75d  sub     ecx, 1
0x18001a760  jz      short loc_18001A78E
0x18001a762  sub     ecx, 1
0x18001a765  jz      short loc_18001A77E
0x18001a767  cmp     ecx, 1
0x18001a76a  jz      short loc_18001A775
0x18001a76c  lea     rdi, dword_180043B4C
0x18001a773  jmp     short loc_18001A7AD
0x18001a775  lea     rdi, aFailfast; "FailFast"
0x18001a77c  jmp     short loc_18001A7AD
0x18001a77e  lea     rax, aLoghr; "LogHr"
0x18001a785  lea     rdi, aLognt; "LogNt"
0x18001a78c  jmp     short loc_18001A79C
0x18001a78e  lea     rax, aReturnhr; "ReturnHr"
0x18001a795  lea     rdi, aReturnnt; "ReturnNt"
0x18001a79c  test    [rbx+4], bpl
0x18001a7a0  cmovz   rdi, rax
0x18001a7a4  jmp     short loc_18001A7AD
0x18001a7a6  lea     rdi, aException; "Exception"
0x18001a7ad  xor     edx, edx; Val
0x18001a7af  mov     r8d, 200h; Size
0x18001a7b5  lea     rcx, [rsp+278h+Buffer]; void *
0x18001a7ba  call    memset_0
0x18001a7bf  test    [rbx+4], bpl
0x18001a7c3  jz      short loc_18001A7E8
0x18001a7c5  mov     ebp, [rbx+0Ch]
0x18001a7c8  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001a7cf  test    rax, rax
0x18001a7d2  jz      short loc_18001A818
0x18001a7d4  mov     r8d, 100h
0x18001a7da  lea     rdx, [rsp+278h+Buffer]
0x18001a7df  mov     ecx, ebp
0x18001a7e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a7e6  jmp     short loc_18001A818
0x18001a7e8  mov     ebp, [rbx+8]
0x18001a7eb  mov     [rsp+278h+Arguments], r15; Arguments
0x18001a7f0  mov     [rsp+278h+nSize], 100h; nSize
0x18001a7f8  lea     rax, [rsp+278h+Buffer]
0x18001a7fd  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001a802  mov     r9d, 400h; dwLanguageId
0x18001a808  mov     r8d, ebp; dwMessageId
0x18001a80b  xor     edx, edx; lpSource
0x18001a80d  mov     ecx, 1200h; dwFlags
0x18001a812  call    cs:__imp_FormatMessageW
0x18001a818  lea     rsi, [r14+rsi*2]
0x18001a81c  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001a820  mov     rax, [rbx+88h]
0x18001a827  mov     rcx, [rbx+80h]
0x18001a82e  mov     rdx, rsi; unsigned __int16 *
0x18001a831  test    r9, r9
0x18001a834  jz      short loc_18001A858
0x18001a836  mov     [rsp+278h+Arguments], rax
0x18001a83b  mov     qword ptr [rsp+278h+nSize], rcx
0x18001a840  mov     eax, [rbx+40h]
0x18001a843  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001a847  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001a84e  mov     rcx, r14; this
0x18001a851  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a856  jmp     short loc_18001A86F
0x18001a858  mov     [rsp+278h+lpBuffer], rax
0x18001a85d  mov     r9, rcx; unsigned __int16 *
0x18001a860  lea     r8, aHsP; "%hs!%p: "
0x18001a867  mov     rcx, r14; this
0x18001a86a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a86f  mov     r14, rax
0x18001a872  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001a879  test    r9, r9
0x18001a87c  jz      short loc_18001A893
0x18001a87e  lea     r8, aCallerP; "(caller: %p) "
0x18001a885  mov     rdx, rsi; unsigned __int16 *
0x18001a888  mov     rcx, rax; this
0x18001a88b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a890  mov     r14, rax
0x18001a893  call    cs:__imp_GetCurrentThreadId
0x18001a899  lea     rcx, [rsp+278h+Buffer]
0x18001a89e  mov     [rsp+278h+var_240], rcx
0x18001a8a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001a8a7  mov     [rsp+278h+nSize], eax
0x18001a8ab  mov     eax, [rbx+44h]
0x18001a8ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001a8b2  mov     r9, rdi; unsigned __int16 *
0x18001a8b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001a8bc  mov     rdx, rsi; unsigned __int16 *
0x18001a8bf  mov     rcx, r14; this
0x18001a8c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a8c7  cmp     [rbx+18h], r15
0x18001a8cb  jnz     short loc_18001A8DD
0x18001a8cd  cmp     [rbx+48h], r15
0x18001a8d1  jnz     short loc_18001A8DD
0x18001a8d3  cmp     [rbx+30h], r15
0x18001a8d7  jz      loc_18001A96D
0x18001a8dd  lea     r8, asc_180044988; "    "
0x18001a8e4  mov     rdx, rsi; unsigned __int16 *
0x18001a8e7  mov     rcx, rax; this
0x18001a8ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a8ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001a8f3  test    r9, r9
0x18001a8f6  jz      short loc_18001A90A
0x18001a8f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001a8ff  mov     rdx, rsi; unsigned __int16 *
0x18001a902  mov     rcx, rax; this
0x18001a905  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a90a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001a90e  test    r9, r9
0x18001a911  jz      short loc_18001A925
0x18001a913  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001a91a  mov     rdx, rsi; unsigned __int16 *
0x18001a91d  mov     rcx, rax; this
0x18001a920  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a925  mov     rcx, [rbx+28h]
0x18001a929  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001a92d  mov     rdx, rsi; unsigned __int16 *
0x18001a930  test    rcx, rcx
0x18001a933  jz      short loc_18001A94B
0x18001a935  mov     [rsp+278h+lpBuffer], rcx
0x18001a93a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001a941  mov     rcx, rax; this
0x18001a944  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a949  jmp     short loc_18001A96D
0x18001a94b  mov     rcx, rax; this
0x18001a94e  test    r9, r9
0x18001a951  jz      short loc_18001A961
0x18001a953  lea     r8, aHs; "[%hs]\n"
0x18001a95a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a95f  jmp     short loc_18001A96D
0x18001a961  lea     r8, asc_180044A00; "\n"
0x18001a968  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a96d  xor     eax, eax
0x18001a96f  mov     rcx, [rsp+278h+var_38]
0x18001a977  xor     rcx, rsp; StackCookie
0x18001a97a  call    __security_check_cookie
0x18001a97f  mov     rbx, [rsp+278h+arg_18]
0x18001a987  add     rsp, 250h
0x18001a98e  pop     r15
0x18001a990  pop     r14
0x18001a992  pop     rdi
0x18001a993  pop     rsi
0x18001a994  pop     rbp
0x18001a995  retn
```
