# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007914`
- end: `0x180007bca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x18000429c`
- `0x18000451c`
- `0x1800047c8`
- `0x18000c7c0`
- `0x18000ee78`
- `0x180030336`
- `0x18003046a`
- `0x180031ae0`
- `0x180031d5d`

## callees

- `0x180002590`
- `0x180002f98`
- `0x180007914`
- `0x1800084f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007a46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007a46`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ac7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007ac7`

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
          v7 = (const char *)&word_180035C12;
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
0x180007914  mov     [rsp+arg_18], rbx
0x180007919  push    rbp
0x18000791a  push    rsi
0x18000791b  push    rdi
0x18000791c  push    r14
0x18000791e  push    r15
0x180007920  sub     rsp, 250h
0x180007927  mov     rax, cs:__security_cookie
0x18000792e  xor     rax, rsp
0x180007931  mov     [rsp+278h+var_38], rax
0x180007939  mov     rbx, r8
0x18000793c  mov     rsi, rdx
0x18000793f  mov     r14, rcx
0x180007942  xor     r15d, r15d
0x180007945  test    rdx, rdx
0x180007948  jz      loc_180007BA1
0x18000794e  test    rcx, rcx
0x180007951  jz      loc_180007BA1
0x180007957  mov     [rcx], r15w
0x18000795b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007962  test    rax, rax
0x180007965  jz      short loc_180007988
0x180007967  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000796e  jz      short loc_180007988
0x180007970  mov     r8, rdx
0x180007973  mov     rdx, rcx
0x180007976  mov     rcx, rbx
0x180007979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000797e  cmp     [r14], r15w
0x180007982  jnz     loc_180007BA1
0x180007988  mov     ecx, [rbx]
0x18000798a  mov     bpl, 8
0x18000798d  test    ecx, ecx
0x18000798f  jz      short loc_1800079DA
0x180007991  sub     ecx, 1
0x180007994  jz      short loc_1800079C2
0x180007996  sub     ecx, 1
0x180007999  jz      short loc_1800079B2
0x18000799b  cmp     ecx, 1
0x18000799e  jz      short loc_1800079A9
0x1800079a0  lea     rdi, word_180035C12
0x1800079a7  jmp     short loc_1800079E1
0x1800079a9  lea     rdi, aFailfast; "FailFast"
0x1800079b0  jmp     short loc_1800079E1
0x1800079b2  lea     rax, aLoghr; "LogHr"
0x1800079b9  lea     rdi, aLognt; "LogNt"
0x1800079c0  jmp     short loc_1800079D0
0x1800079c2  lea     rax, aReturnhr; "ReturnHr"
0x1800079c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800079d0  test    [rbx+4], bpl
0x1800079d4  cmovz   rdi, rax
0x1800079d8  jmp     short loc_1800079E1
0x1800079da  lea     rdi, aException; "Exception"
0x1800079e1  xor     edx, edx; Val
0x1800079e3  mov     r8d, 200h; Size
0x1800079e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800079ee  call    memset_0
0x1800079f3  test    [rbx+4], bpl
0x1800079f7  jz      short loc_180007A1C
0x1800079f9  mov     ebp, [rbx+0Ch]
0x1800079fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007a03  test    rax, rax
0x180007a06  jz      short loc_180007A4C
0x180007a08  mov     r8d, 100h
0x180007a0e  lea     rdx, [rsp+278h+Buffer]
0x180007a13  mov     ecx, ebp
0x180007a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a1a  jmp     short loc_180007A4C
0x180007a1c  mov     ebp, [rbx+8]
0x180007a1f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007a24  mov     [rsp+278h+nSize], 100h; nSize
0x180007a2c  lea     rax, [rsp+278h+Buffer]
0x180007a31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007a36  mov     r9d, 400h; dwLanguageId
0x180007a3c  mov     r8d, ebp; dwMessageId
0x180007a3f  xor     edx, edx; lpSource
0x180007a41  mov     ecx, 1200h; dwFlags
0x180007a46  call    cs:__imp_FormatMessageW
0x180007a4c  lea     rsi, [r14+rsi*2]
0x180007a50  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007a54  mov     rax, [rbx+88h]
0x180007a5b  mov     rcx, [rbx+80h]
0x180007a62  mov     rdx, rsi; unsigned __int16 *
0x180007a65  test    r9, r9
0x180007a68  jz      short loc_180007A8C
0x180007a6a  mov     [rsp+278h+Arguments], rax
0x180007a6f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007a74  mov     eax, [rbx+40h]
0x180007a77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007a7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007a82  mov     rcx, r14; this
0x180007a85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007a8a  jmp     short loc_180007AA3
0x180007a8c  mov     [rsp+278h+lpBuffer], rax
0x180007a91  mov     r9, rcx; unsigned __int16 *
0x180007a94  lea     r8, aHsP; "%hs!%p: "
0x180007a9b  mov     rcx, r14; this
0x180007a9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007aa3  mov     r14, rax
0x180007aa6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007aad  test    r9, r9
0x180007ab0  jz      short loc_180007AC7
0x180007ab2  lea     r8, aCallerP; "(caller: %p) "
0x180007ab9  mov     rdx, rsi; unsigned __int16 *
0x180007abc  mov     rcx, rax; this
0x180007abf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ac4  mov     r14, rax
0x180007ac7  call    cs:__imp_GetCurrentThreadId
0x180007acd  lea     rcx, [rsp+278h+Buffer]
0x180007ad2  mov     [rsp+278h+var_240], rcx
0x180007ad7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007adb  mov     [rsp+278h+nSize], eax
0x180007adf  mov     eax, [rbx+44h]
0x180007ae2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007ae6  mov     r9, rdi; unsigned __int16 *
0x180007ae9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007af0  mov     rdx, rsi; unsigned __int16 *
0x180007af3  mov     rcx, r14; this
0x180007af6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007afb  cmp     [rbx+18h], r15
0x180007aff  jnz     short loc_180007B11
0x180007b01  cmp     [rbx+48h], r15
0x180007b05  jnz     short loc_180007B11
0x180007b07  cmp     [rbx+30h], r15
0x180007b0b  jz      loc_180007BA1
0x180007b11  lea     r8, asc_180035820; "    "
0x180007b18  mov     rdx, rsi; unsigned __int16 *
0x180007b1b  mov     rcx, rax; this
0x180007b1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b23  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007b27  test    r9, r9
0x180007b2a  jz      short loc_180007B3E
0x180007b2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007b33  mov     rdx, rsi; unsigned __int16 *
0x180007b36  mov     rcx, rax; this
0x180007b39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007b42  test    r9, r9
0x180007b45  jz      short loc_180007B59
0x180007b47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007b4e  mov     rdx, rsi; unsigned __int16 *
0x180007b51  mov     rcx, rax; this
0x180007b54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b59  mov     rcx, [rbx+28h]
0x180007b5d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007b61  mov     rdx, rsi; unsigned __int16 *
0x180007b64  test    rcx, rcx
0x180007b67  jz      short loc_180007B7F
0x180007b69  mov     [rsp+278h+lpBuffer], rcx
0x180007b6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007b75  mov     rcx, rax; this
0x180007b78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b7d  jmp     short loc_180007BA1
0x180007b7f  mov     rcx, rax; this
0x180007b82  test    r9, r9
0x180007b85  jz      short loc_180007B95
0x180007b87  lea     r8, aHs; "[%hs]\n"
0x180007b8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007b93  jmp     short loc_180007BA1
0x180007b95  lea     r8, asc_180035898; "\n"
0x180007b9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ba1  xor     eax, eax
0x180007ba3  mov     rcx, [rsp+278h+var_38]
0x180007bab  xor     rcx, rsp; StackCookie
0x180007bae  call    __security_check_cookie
0x180007bb3  mov     rbx, [rsp+278h+arg_18]
0x180007bbb  add     rsp, 250h
0x180007bc2  pop     r15
0x180007bc4  pop     r14
0x180007bc6  pop     rdi
0x180007bc7  pop     rsi
0x180007bc8  pop     rbp
0x180007bc9  retn
```
