# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18009a62c`
- end: `0x18009a8f8`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `716`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180097c00`
- `0x180097ea0`
- `0x18009c4b4`
- `0x18009fd6c`
- `0x1800a0cd0`

## callees

- `0x180002a00`
- `0x18009a62c`
- `0x18009c8cc`
- `0x1800b0b00`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009a7ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18009a7ee`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18009a767`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18009a767`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rdi
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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
  v7 = (const char *)&word_1800D4828;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
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
                          Buffer,
                          -2);
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
0x18009a62c  mov     rax, rsp
0x18009a62f  push    rbp
0x18009a630  push    rsi
0x18009a631  push    rdi
0x18009a632  push    r14
0x18009a634  push    r15
0x18009a636  sub     rsp, 260h
0x18009a63d  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18009a646  mov     [rax+20h], rbx
0x18009a64a  mov     rax, cs:__security_cookie
0x18009a651  xor     rax, rsp
0x18009a654  mov     [rsp+288h+var_38], rax
0x18009a65c  mov     rbx, r8
0x18009a65f  mov     rdi, rdx
0x18009a662  mov     r14, rcx
0x18009a665  xor     r15d, r15d
0x18009a668  test    rdx, rdx
0x18009a66b  jz      loc_18009A8CE
0x18009a671  test    rcx, rcx
0x18009a674  jz      loc_18009A8CE
0x18009a67a  mov     [rcx], r15w
0x18009a67e  mov     rax, cs:g_pfnResultLoggingCallback
0x18009a685  test    rax, rax
0x18009a688  jz      short loc_18009A6AB
0x18009a68a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18009a691  jz      short loc_18009A6AB
0x18009a693  mov     r8, rdx
0x18009a696  mov     rdx, rcx
0x18009a699  mov     rcx, rbx
0x18009a69c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a6a1  cmp     [r14], r15w
0x18009a6a5  jnz     loc_18009A8CE
0x18009a6ab  lea     rsi, word_1800D4828
0x18009a6b2  mov     ecx, [rbx]
0x18009a6b4  mov     bpl, 8
0x18009a6b7  test    ecx, ecx
0x18009a6b9  jz      short loc_18009A6FB
0x18009a6bb  sub     ecx, 1
0x18009a6be  jz      short loc_18009A6E3
0x18009a6c0  sub     ecx, 1
0x18009a6c3  jz      short loc_18009A6D3
0x18009a6c5  cmp     ecx, 1
0x18009a6c8  jnz     short loc_18009A702
0x18009a6ca  lea     rsi, aFailfast; "FailFast"
0x18009a6d1  jmp     short loc_18009A702
0x18009a6d3  lea     rax, aLoghr; "LogHr"
0x18009a6da  lea     rsi, aLognt; "LogNt"
0x18009a6e1  jmp     short loc_18009A6F1
0x18009a6e3  lea     rax, aReturnhr; "ReturnHr"
0x18009a6ea  lea     rsi, aReturnnt; "ReturnNt"
0x18009a6f1  test    [rbx+4], bpl
0x18009a6f5  cmovz   rsi, rax
0x18009a6f9  jmp     short loc_18009A702
0x18009a6fb  lea     rsi, aException; "Exception"
0x18009a702  xor     edx, edx; Val
0x18009a704  mov     r8d, 200h; Size
0x18009a70a  lea     rcx, [rsp+288h+Buffer]; void *
0x18009a70f  call    memset
0x18009a714  test    [rbx+4], bpl
0x18009a718  jz      short loc_18009A73D
0x18009a71a  mov     ebp, [rbx+0Ch]
0x18009a71d  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18009a724  test    rax, rax
0x18009a727  jz      short loc_18009A773
0x18009a729  mov     r8d, 100h
0x18009a72f  lea     rdx, [rsp+288h+Buffer]
0x18009a734  mov     ecx, ebp
0x18009a736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a73b  jmp     short loc_18009A773
0x18009a73d  mov     ebp, [rbx+8]
0x18009a740  mov     [rsp+288h+Arguments], r15; Arguments
0x18009a745  mov     [rsp+288h+nSize], 100h; nSize
0x18009a74d  lea     rax, [rsp+288h+Buffer]
0x18009a752  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18009a757  mov     r9d, 400h; dwLanguageId
0x18009a75d  mov     r8d, ebp; dwMessageId
0x18009a760  xor     edx, edx; lpSource
0x18009a762  mov     ecx, 1200h; dwFlags
0x18009a767  call    cs:__imp_FormatMessageW
0x18009a76e  nop     dword ptr [rax+rax+00h]
0x18009a773  lea     rdi, [r14+rdi*2]
0x18009a777  mov     r9, [rbx+38h]; unsigned __int16 *
0x18009a77b  mov     rax, [rbx+88h]
0x18009a782  mov     rcx, [rbx+80h]
0x18009a789  mov     rdx, rdi; unsigned __int16 *
0x18009a78c  test    r9, r9
0x18009a78f  jz      short loc_18009A7B3
0x18009a791  mov     [rsp+288h+Arguments], rax
0x18009a796  mov     qword ptr [rsp+288h+nSize], rcx
0x18009a79b  mov     eax, [rbx+40h]
0x18009a79e  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18009a7a2  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18009a7a9  mov     rcx, r14; this
0x18009a7ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a7b1  jmp     short loc_18009A7CA
0x18009a7b3  mov     [rsp+288h+lpBuffer], rax
0x18009a7b8  mov     r9, rcx; unsigned __int16 *
0x18009a7bb  lea     r8, aHsP; "%hs!%p: "
0x18009a7c2  mov     rcx, r14; this
0x18009a7c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a7ca  mov     r14, rax
0x18009a7cd  mov     r9, [rbx+90h]; unsigned __int16 *
0x18009a7d4  test    r9, r9
0x18009a7d7  jz      short loc_18009A7EE
0x18009a7d9  lea     r8, aCallerP; "(caller: %p) "
0x18009a7e0  mov     rdx, rdi; unsigned __int16 *
0x18009a7e3  mov     rcx, rax; this
0x18009a7e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a7eb  mov     r14, rax
0x18009a7ee  call    cs:__imp_GetCurrentThreadId
0x18009a7f5  nop     dword ptr [rax+rax+00h]
0x18009a7fa  lea     rcx, [rsp+288h+Buffer]
0x18009a7ff  mov     [rsp+288h+var_250], rcx
0x18009a804  mov     dword ptr [rsp+288h+Arguments], ebp
0x18009a808  mov     [rsp+288h+nSize], eax
0x18009a80c  mov     eax, [rbx+44h]
0x18009a80f  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18009a813  mov     r9, rsi; unsigned __int16 *
0x18009a816  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18009a81d  mov     rdx, rdi; unsigned __int16 *
0x18009a820  mov     rcx, r14; this
0x18009a823  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a828  cmp     [rbx+18h], r15
0x18009a82c  jnz     short loc_18009A83E
0x18009a82e  cmp     [rbx+48h], r15
0x18009a832  jnz     short loc_18009A83E
0x18009a834  cmp     [rbx+30h], r15
0x18009a838  jz      loc_18009A8CE
0x18009a83e  lea     r8, asc_1800D4918; "    "
0x18009a845  mov     rdx, rdi; unsigned __int16 *
0x18009a848  mov     rcx, rax; this
0x18009a84b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a850  mov     r9, [rbx+18h]; unsigned __int16 *
0x18009a854  test    r9, r9
0x18009a857  jz      short loc_18009A86B
0x18009a859  lea     r8, aMsgWs; "Msg:[%ws] "
0x18009a860  mov     rdx, rdi; unsigned __int16 *
0x18009a863  mov     rcx, rax; this
0x18009a866  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a86b  mov     r9, [rbx+48h]; unsigned __int16 *
0x18009a86f  test    r9, r9
0x18009a872  jz      short loc_18009A886
0x18009a874  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18009a87b  mov     rdx, rdi; unsigned __int16 *
0x18009a87e  mov     rcx, rax; this
0x18009a881  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a886  mov     rcx, [rbx+28h]
0x18009a88a  mov     r9, [rbx+30h]; unsigned __int16 *
0x18009a88e  mov     rdx, rdi; unsigned __int16 *
0x18009a891  test    rcx, rcx
0x18009a894  jz      short loc_18009A8AC
0x18009a896  mov     [rsp+288h+lpBuffer], rcx
0x18009a89b  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18009a8a2  mov     rcx, rax; this
0x18009a8a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a8aa  jmp     short loc_18009A8CE
0x18009a8ac  mov     rcx, rax; this
0x18009a8af  test    r9, r9
0x18009a8b2  jz      short loc_18009A8C2
0x18009a8b4  lea     r8, aHs; "[%hs]\n"
0x18009a8bb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a8c0  jmp     short loc_18009A8CE
0x18009a8c2  lea     r8, asc_1800D4990; "\n"
0x18009a8c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18009a8ce  xor     eax, eax
0x18009a8d0  mov     rcx, [rsp+288h+var_38]
0x18009a8d8  xor     rcx, rsp; StackCookie
0x18009a8db  call    __security_check_cookie
0x18009a8e0  mov     rbx, [rsp+288h+arg_18]
0x18009a8e8  add     rsp, 260h
0x18009a8ef  pop     r15
0x18009a8f1  pop     r14
0x18009a8f3  pop     rdi
0x18009a8f4  pop     rsi
0x18009a8f5  pop     rbp
0x18009a8f6  retn
```
