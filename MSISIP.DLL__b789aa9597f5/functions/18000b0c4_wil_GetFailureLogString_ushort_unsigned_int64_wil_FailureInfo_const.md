# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b0c4`
- end: `0x18000b385`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180007450`
- `0x180008aa0`
- `0x18000a780`

## callees

- `0x180007d70`
- `0x18000b0c4`
- `0x18000d2ce`
- `0x18000d300`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b282`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000b282`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b201`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000b201`

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
          v7 = (const char *)&dword_18000FAAC;
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
0x18000b0c4  mov     rax, rsp
0x18000b0c7  push    rbp
0x18000b0c8  push    rsi
0x18000b0c9  push    rdi
0x18000b0ca  push    r14
0x18000b0cc  push    r15
0x18000b0ce  sub     rsp, 260h
0x18000b0d5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18000b0de  mov     [rax+20h], rbx
0x18000b0e2  mov     rax, cs:__security_cookie
0x18000b0e9  xor     rax, rsp
0x18000b0ec  mov     [rsp+288h+var_38], rax
0x18000b0f4  mov     rbx, r8
0x18000b0f7  mov     rsi, rdx
0x18000b0fa  mov     r14, rcx
0x18000b0fd  xor     r15d, r15d
0x18000b100  test    rdx, rdx
0x18000b103  jz      loc_18000B35C
0x18000b109  test    rcx, rcx
0x18000b10c  jz      loc_18000B35C
0x18000b112  mov     [rcx], r15w
0x18000b116  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b11d  test    rax, rax
0x18000b120  jz      short loc_18000B143
0x18000b122  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b129  jz      short loc_18000B143
0x18000b12b  mov     r8, rdx
0x18000b12e  mov     rdx, rcx
0x18000b131  mov     rcx, rbx
0x18000b134  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b139  cmp     [r14], r15w
0x18000b13d  jnz     loc_18000B35C
0x18000b143  mov     ecx, [rbx]
0x18000b145  mov     bpl, 8
0x18000b148  test    ecx, ecx
0x18000b14a  jz      short loc_18000B195
0x18000b14c  sub     ecx, 1
0x18000b14f  jz      short loc_18000B17D
0x18000b151  sub     ecx, 1
0x18000b154  jz      short loc_18000B16D
0x18000b156  cmp     ecx, 1
0x18000b159  jz      short loc_18000B164
0x18000b15b  lea     rdi, dword_18000FAAC
0x18000b162  jmp     short loc_18000B19C
0x18000b164  lea     rdi, aFailfast; "FailFast"
0x18000b16b  jmp     short loc_18000B19C
0x18000b16d  lea     rax, aLoghr; "LogHr"
0x18000b174  lea     rdi, aLognt; "LogNt"
0x18000b17b  jmp     short loc_18000B18B
0x18000b17d  lea     rax, aReturnhr; "ReturnHr"
0x18000b184  lea     rdi, aReturnnt; "ReturnNt"
0x18000b18b  test    [rbx+4], bpl
0x18000b18f  cmovz   rdi, rax
0x18000b193  jmp     short loc_18000B19C
0x18000b195  lea     rdi, aException; "Exception"
0x18000b19c  xor     edx, edx; Val
0x18000b19e  mov     r8d, 200h; Size
0x18000b1a4  lea     rcx, [rsp+288h+Buffer]; void *
0x18000b1a9  call    memset_0
0x18000b1ae  test    [rbx+4], bpl
0x18000b1b2  jz      short loc_18000B1D7
0x18000b1b4  mov     ebp, [rbx+0Ch]
0x18000b1b7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000b1be  test    rax, rax
0x18000b1c1  jz      short loc_18000B207
0x18000b1c3  mov     r8d, 100h
0x18000b1c9  lea     rdx, [rsp+288h+Buffer]
0x18000b1ce  mov     ecx, ebp
0x18000b1d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1d5  jmp     short loc_18000B207
0x18000b1d7  mov     ebp, [rbx+8]
0x18000b1da  mov     [rsp+288h+Arguments], r15; Arguments
0x18000b1df  mov     [rsp+288h+nSize], 100h; nSize
0x18000b1e7  lea     rax, [rsp+288h+Buffer]
0x18000b1ec  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18000b1f1  mov     r9d, 400h; dwLanguageId
0x18000b1f7  mov     r8d, ebp; dwMessageId
0x18000b1fa  xor     edx, edx; lpSource
0x18000b1fc  mov     ecx, 1200h; dwFlags
0x18000b201  call    cs:__imp_FormatMessageW
0x18000b207  lea     rsi, [r14+rsi*2]
0x18000b20b  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000b20f  mov     rax, [rbx+88h]
0x18000b216  mov     rcx, [rbx+80h]
0x18000b21d  mov     rdx, rsi; unsigned __int16 *
0x18000b220  test    r9, r9
0x18000b223  jz      short loc_18000B247
0x18000b225  mov     [rsp+288h+Arguments], rax
0x18000b22a  mov     qword ptr [rsp+288h+nSize], rcx
0x18000b22f  mov     eax, [rbx+40h]
0x18000b232  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18000b236  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b23d  mov     rcx, r14; this
0x18000b240  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b245  jmp     short loc_18000B25E
0x18000b247  mov     [rsp+288h+lpBuffer], rax
0x18000b24c  mov     r9, rcx; unsigned __int16 *
0x18000b24f  lea     r8, aHsP; "%hs!%p: "
0x18000b256  mov     rcx, r14; this
0x18000b259  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b25e  mov     r14, rax
0x18000b261  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000b268  test    r9, r9
0x18000b26b  jz      short loc_18000B282
0x18000b26d  lea     r8, aCallerP; "(caller: %p) "
0x18000b274  mov     rdx, rsi; unsigned __int16 *
0x18000b277  mov     rcx, rax; this
0x18000b27a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b27f  mov     r14, rax
0x18000b282  call    cs:__imp_GetCurrentThreadId
0x18000b288  lea     rcx, [rsp+288h+Buffer]
0x18000b28d  mov     [rsp+288h+var_250], rcx
0x18000b292  mov     dword ptr [rsp+288h+Arguments], ebp
0x18000b296  mov     [rsp+288h+nSize], eax
0x18000b29a  mov     eax, [rbx+44h]
0x18000b29d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18000b2a1  mov     r9, rdi; unsigned __int16 *
0x18000b2a4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b2ab  mov     rdx, rsi; unsigned __int16 *
0x18000b2ae  mov     rcx, r14; this
0x18000b2b1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2b6  cmp     [rbx+18h], r15
0x18000b2ba  jnz     short loc_18000B2CC
0x18000b2bc  cmp     [rbx+48h], r15
0x18000b2c0  jnz     short loc_18000B2CC
0x18000b2c2  cmp     [rbx+30h], r15
0x18000b2c6  jz      loc_18000B35C
0x18000b2cc  lea     r8, asc_18000FBA0; "    "
0x18000b2d3  mov     rdx, rsi; unsigned __int16 *
0x18000b2d6  mov     rcx, rax; this
0x18000b2d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2de  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000b2e2  test    r9, r9
0x18000b2e5  jz      short loc_18000B2F9
0x18000b2e7  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b2ee  mov     rdx, rsi; unsigned __int16 *
0x18000b2f1  mov     rcx, rax; this
0x18000b2f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b2f9  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000b2fd  test    r9, r9
0x18000b300  jz      short loc_18000B314
0x18000b302  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b309  mov     rdx, rsi; unsigned __int16 *
0x18000b30c  mov     rcx, rax; this
0x18000b30f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b314  mov     rcx, [rbx+28h]
0x18000b318  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000b31c  mov     rdx, rsi; unsigned __int16 *
0x18000b31f  test    rcx, rcx
0x18000b322  jz      short loc_18000B33A
0x18000b324  mov     [rsp+288h+lpBuffer], rcx
0x18000b329  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b330  mov     rcx, rax; this
0x18000b333  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b338  jmp     short loc_18000B35C
0x18000b33a  mov     rcx, rax; this
0x18000b33d  test    r9, r9
0x18000b340  jz      short loc_18000B350
0x18000b342  lea     r8, aHs; "[%hs]\n"
0x18000b349  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b34e  jmp     short loc_18000B35C
0x18000b350  lea     r8, asc_18000FC18; "\n"
0x18000b357  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000b35c  xor     eax, eax
0x18000b35e  mov     rcx, [rsp+288h+var_38]
0x18000b366  xor     rcx, rsp; StackCookie
0x18000b369  call    __security_check_cookie
0x18000b36e  mov     rbx, [rsp+288h+arg_18]
0x18000b376  add     rsp, 260h
0x18000b37d  pop     r15
0x18000b37f  pop     r14
0x18000b381  pop     rdi
0x18000b382  pop     rsi
0x18000b383  pop     rbp
0x18000b384  retn
```
