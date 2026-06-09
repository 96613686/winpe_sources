# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180024c04`
- end: `0x180024ed0`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `716`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180025ab4`
- `0x18002b7e0`

## callees

- `0x180013e69`
- `0x180024c04`
- `0x180025dc8`
- `0x18002fb50`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024dc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024dc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024d3f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180024d3f`

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
  v7 = (const char *)&word_180039250;
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
0x180024c04  mov     rax, rsp
0x180024c07  push    rbp
0x180024c08  push    rsi
0x180024c09  push    rdi
0x180024c0a  push    r14
0x180024c0c  push    r15
0x180024c0e  sub     rsp, 260h
0x180024c15  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180024c1e  mov     [rax+20h], rbx
0x180024c22  mov     rax, cs:__security_cookie
0x180024c29  xor     rax, rsp
0x180024c2c  mov     [rsp+288h+var_38], rax
0x180024c34  mov     rbx, r8
0x180024c37  mov     rdi, rdx
0x180024c3a  mov     r14, rcx
0x180024c3d  xor     r15d, r15d
0x180024c40  test    rdx, rdx
0x180024c43  jz      loc_180024EA6
0x180024c49  test    rcx, rcx
0x180024c4c  jz      loc_180024EA6
0x180024c52  mov     [rcx], r15w
0x180024c56  mov     rax, cs:g_pfnResultLoggingCallback
0x180024c5d  test    rax, rax
0x180024c60  jz      short loc_180024C83
0x180024c62  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180024c69  jz      short loc_180024C83
0x180024c6b  mov     r8, rdx
0x180024c6e  mov     rdx, rcx
0x180024c71  mov     rcx, rbx
0x180024c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c79  cmp     [r14], r15w
0x180024c7d  jnz     loc_180024EA6
0x180024c83  lea     rsi, word_180039250
0x180024c8a  mov     ecx, [rbx]
0x180024c8c  mov     bpl, 8
0x180024c8f  test    ecx, ecx
0x180024c91  jz      short loc_180024CD3
0x180024c93  sub     ecx, 1
0x180024c96  jz      short loc_180024CBB
0x180024c98  sub     ecx, 1
0x180024c9b  jz      short loc_180024CAB
0x180024c9d  cmp     ecx, 1
0x180024ca0  jnz     short loc_180024CDA
0x180024ca2  lea     rsi, aFailfast; "FailFast"
0x180024ca9  jmp     short loc_180024CDA
0x180024cab  lea     rax, aLoghr; "LogHr"
0x180024cb2  lea     rsi, aLognt; "LogNt"
0x180024cb9  jmp     short loc_180024CC9
0x180024cbb  lea     rax, aReturnhr; "ReturnHr"
0x180024cc2  lea     rsi, aReturnnt; "ReturnNt"
0x180024cc9  test    [rbx+4], bpl
0x180024ccd  cmovz   rsi, rax
0x180024cd1  jmp     short loc_180024CDA
0x180024cd3  lea     rsi, aException; "Exception"
0x180024cda  xor     edx, edx; Val
0x180024cdc  mov     r8d, 200h; Size
0x180024ce2  lea     rcx, [rsp+288h+Buffer]; void *
0x180024ce7  call    memset_0
0x180024cec  test    [rbx+4], bpl
0x180024cf0  jz      short loc_180024D15
0x180024cf2  mov     ebp, [rbx+0Ch]
0x180024cf5  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180024cfc  test    rax, rax
0x180024cff  jz      short loc_180024D4B
0x180024d01  mov     r8d, 100h
0x180024d07  lea     rdx, [rsp+288h+Buffer]
0x180024d0c  mov     ecx, ebp
0x180024d0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024d13  jmp     short loc_180024D4B
0x180024d15  mov     ebp, [rbx+8]
0x180024d18  mov     [rsp+288h+Arguments], r15; Arguments
0x180024d1d  mov     [rsp+288h+nSize], 100h; nSize
0x180024d25  lea     rax, [rsp+288h+Buffer]
0x180024d2a  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180024d2f  mov     r9d, 400h; dwLanguageId
0x180024d35  mov     r8d, ebp; dwMessageId
0x180024d38  xor     edx, edx; lpSource
0x180024d3a  mov     ecx, 1200h; dwFlags
0x180024d3f  call    cs:__imp_FormatMessageW
0x180024d46  nop     dword ptr [rax+rax+00h]
0x180024d4b  lea     rdi, [r14+rdi*2]
0x180024d4f  mov     r9, [rbx+38h]; unsigned __int16 *
0x180024d53  mov     rax, [rbx+88h]
0x180024d5a  mov     rcx, [rbx+80h]
0x180024d61  mov     rdx, rdi; unsigned __int16 *
0x180024d64  test    r9, r9
0x180024d67  jz      short loc_180024D8B
0x180024d69  mov     [rsp+288h+Arguments], rax
0x180024d6e  mov     qword ptr [rsp+288h+nSize], rcx
0x180024d73  mov     eax, [rbx+40h]
0x180024d76  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180024d7a  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180024d81  mov     rcx, r14; this
0x180024d84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024d89  jmp     short loc_180024DA2
0x180024d8b  mov     [rsp+288h+lpBuffer], rax
0x180024d90  mov     r9, rcx; unsigned __int16 *
0x180024d93  lea     r8, aHsP; "%hs!%p: "
0x180024d9a  mov     rcx, r14; this
0x180024d9d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024da2  mov     r14, rax
0x180024da5  mov     r9, [rbx+90h]; unsigned __int16 *
0x180024dac  test    r9, r9
0x180024daf  jz      short loc_180024DC6
0x180024db1  lea     r8, aCallerP; "(caller: %p) "
0x180024db8  mov     rdx, rdi; unsigned __int16 *
0x180024dbb  mov     rcx, rax; this
0x180024dbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024dc3  mov     r14, rax
0x180024dc6  call    cs:__imp_GetCurrentThreadId
0x180024dcd  nop     dword ptr [rax+rax+00h]
0x180024dd2  mov     ecx, [rbx+44h]
0x180024dd5  lea     rdx, [rsp+288h+Buffer]
0x180024dda  mov     [rsp+288h+var_250], rdx
0x180024ddf  mov     dword ptr [rsp+288h+Arguments], ebp
0x180024de3  mov     [rsp+288h+nSize], eax
0x180024de7  mov     dword ptr [rsp+288h+lpBuffer], ecx
0x180024deb  mov     r9, rsi; unsigned __int16 *
0x180024dee  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180024df5  mov     rdx, rdi; unsigned __int16 *
0x180024df8  mov     rcx, r14; this
0x180024dfb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e00  cmp     [rbx+18h], r15
0x180024e04  jnz     short loc_180024E16
0x180024e06  cmp     [rbx+48h], r15
0x180024e0a  jnz     short loc_180024E16
0x180024e0c  cmp     [rbx+30h], r15
0x180024e10  jz      loc_180024EA6
0x180024e16  lea     r8, asc_18003AD08; "    "
0x180024e1d  mov     rdx, rdi; unsigned __int16 *
0x180024e20  mov     rcx, rax; this
0x180024e23  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e28  mov     r9, [rbx+18h]; unsigned __int16 *
0x180024e2c  test    r9, r9
0x180024e2f  jz      short loc_180024E43
0x180024e31  lea     r8, aMsgWs; "Msg:[%ws] "
0x180024e38  mov     rdx, rdi; unsigned __int16 *
0x180024e3b  mov     rcx, rax; this
0x180024e3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e43  mov     r9, [rbx+48h]; unsigned __int16 *
0x180024e47  test    r9, r9
0x180024e4a  jz      short loc_180024E5E
0x180024e4c  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180024e53  mov     rdx, rdi; unsigned __int16 *
0x180024e56  mov     rcx, rax; this
0x180024e59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e5e  mov     rcx, [rbx+28h]
0x180024e62  mov     r9, [rbx+30h]; unsigned __int16 *
0x180024e66  mov     rdx, rdi; unsigned __int16 *
0x180024e69  test    rcx, rcx
0x180024e6c  jz      short loc_180024E84
0x180024e6e  mov     [rsp+288h+lpBuffer], rcx
0x180024e73  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180024e7a  mov     rcx, rax; this
0x180024e7d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e82  jmp     short loc_180024EA6
0x180024e84  mov     rcx, rax; this
0x180024e87  test    r9, r9
0x180024e8a  jz      short loc_180024E9A
0x180024e8c  lea     r8, aHs; "[%hs]\n"
0x180024e93  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e98  jmp     short loc_180024EA6
0x180024e9a  lea     r8, asc_18003AD80; "\n"
0x180024ea1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024ea6  xor     eax, eax
0x180024ea8  mov     rcx, [rsp+288h+var_38]
0x180024eb0  xor     rcx, rsp; StackCookie
0x180024eb3  call    __security_check_cookie
0x180024eb8  mov     rbx, [rsp+288h+arg_18]
0x180024ec0  add     rsp, 260h
0x180024ec7  pop     r15
0x180024ec9  pop     r14
0x180024ecb  pop     rdi
0x180024ecc  pop     rsi
0x180024ecd  pop     rbp
0x180024ece  retn
```
