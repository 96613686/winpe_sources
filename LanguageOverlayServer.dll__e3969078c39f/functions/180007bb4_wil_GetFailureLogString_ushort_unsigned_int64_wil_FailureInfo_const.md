# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007bb4`
- end: `0x180007e6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180006360`
- `0x1800065e0`
- `0x18000688c`
- `0x18000a120`
- `0x18000b48c`
- `0x1800636b4`
- `0x1800637e8`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x180007bb4`
- `0x180008698`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007ce6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007ce6`

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
          v7 = (const char *)&byte_1800700FD;
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
0x180007bb4  mov     [rsp+arg_18], rbx
0x180007bb9  push    rbp
0x180007bba  push    rsi
0x180007bbb  push    rdi
0x180007bbc  push    r14
0x180007bbe  push    r15
0x180007bc0  sub     rsp, 250h
0x180007bc7  mov     rax, cs:__security_cookie
0x180007bce  xor     rax, rsp
0x180007bd1  mov     [rsp+278h+var_38], rax
0x180007bd9  mov     rbx, r8
0x180007bdc  mov     rsi, rdx
0x180007bdf  mov     r14, rcx
0x180007be2  xor     r15d, r15d
0x180007be5  test    rdx, rdx
0x180007be8  jz      loc_180007E41
0x180007bee  test    rcx, rcx
0x180007bf1  jz      loc_180007E41
0x180007bf7  mov     [rcx], r15w
0x180007bfb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c02  test    rax, rax
0x180007c05  jz      short loc_180007C28
0x180007c07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007c0e  jz      short loc_180007C28
0x180007c10  mov     r8, rdx
0x180007c13  mov     rdx, rcx
0x180007c16  mov     rcx, rbx
0x180007c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c1e  cmp     [r14], r15w
0x180007c22  jnz     loc_180007E41
0x180007c28  mov     ecx, [rbx]
0x180007c2a  mov     bpl, 8
0x180007c2d  test    ecx, ecx
0x180007c2f  jz      short loc_180007C7A
0x180007c31  sub     ecx, 1
0x180007c34  jz      short loc_180007C62
0x180007c36  sub     ecx, 1
0x180007c39  jz      short loc_180007C52
0x180007c3b  cmp     ecx, 1
0x180007c3e  jz      short loc_180007C49
0x180007c40  lea     rdi, byte_1800700FD
0x180007c47  jmp     short loc_180007C81
0x180007c49  lea     rdi, aFailfast; "FailFast"
0x180007c50  jmp     short loc_180007C81
0x180007c52  lea     rax, aLoghr; "LogHr"
0x180007c59  lea     rdi, aLognt; "LogNt"
0x180007c60  jmp     short loc_180007C70
0x180007c62  lea     rax, aReturnhr; "ReturnHr"
0x180007c69  lea     rdi, aReturnnt; "ReturnNt"
0x180007c70  test    [rbx+4], bpl
0x180007c74  cmovz   rdi, rax
0x180007c78  jmp     short loc_180007C81
0x180007c7a  lea     rdi, aException; "Exception"
0x180007c81  xor     edx, edx; Val
0x180007c83  mov     r8d, 200h; Size
0x180007c89  lea     rcx, [rsp+278h+Buffer]; void *
0x180007c8e  call    memset_0
0x180007c93  test    [rbx+4], bpl
0x180007c97  jz      short loc_180007CBC
0x180007c99  mov     ebp, [rbx+0Ch]
0x180007c9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007ca3  test    rax, rax
0x180007ca6  jz      short loc_180007CEC
0x180007ca8  mov     r8d, 100h
0x180007cae  lea     rdx, [rsp+278h+Buffer]
0x180007cb3  mov     ecx, ebp
0x180007cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cba  jmp     short loc_180007CEC
0x180007cbc  mov     ebp, [rbx+8]
0x180007cbf  mov     [rsp+278h+Arguments], r15; Arguments
0x180007cc4  mov     [rsp+278h+nSize], 100h; nSize
0x180007ccc  lea     rax, [rsp+278h+Buffer]
0x180007cd1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007cd6  mov     r9d, 400h; dwLanguageId
0x180007cdc  mov     r8d, ebp; dwMessageId
0x180007cdf  xor     edx, edx; lpSource
0x180007ce1  mov     ecx, 1200h; dwFlags
0x180007ce6  call    cs:__imp_FormatMessageW
0x180007cec  lea     rsi, [r14+rsi*2]
0x180007cf0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007cf4  mov     rax, [rbx+88h]
0x180007cfb  mov     rcx, [rbx+80h]
0x180007d02  mov     rdx, rsi; unsigned __int16 *
0x180007d05  test    r9, r9
0x180007d08  jz      short loc_180007D2C
0x180007d0a  mov     [rsp+278h+Arguments], rax
0x180007d0f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007d14  mov     eax, [rbx+40h]
0x180007d17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007d1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007d22  mov     rcx, r14; this
0x180007d25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d2a  jmp     short loc_180007D43
0x180007d2c  mov     [rsp+278h+lpBuffer], rax
0x180007d31  mov     r9, rcx; unsigned __int16 *
0x180007d34  lea     r8, aHsP; "%hs!%p: "
0x180007d3b  mov     rcx, r14; this
0x180007d3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d43  mov     r14, rax
0x180007d46  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007d4d  test    r9, r9
0x180007d50  jz      short loc_180007D67
0x180007d52  lea     r8, aCallerP; "(caller: %p) "
0x180007d59  mov     rdx, rsi; unsigned __int16 *
0x180007d5c  mov     rcx, rax; this
0x180007d5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d64  mov     r14, rax
0x180007d67  call    cs:__imp_GetCurrentThreadId
0x180007d6d  lea     rcx, [rsp+278h+Buffer]
0x180007d72  mov     [rsp+278h+var_240], rcx
0x180007d77  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007d7b  mov     [rsp+278h+nSize], eax
0x180007d7f  mov     eax, [rbx+44h]
0x180007d82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007d86  mov     r9, rdi; unsigned __int16 *
0x180007d89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007d90  mov     rdx, rsi; unsigned __int16 *
0x180007d93  mov     rcx, r14; this
0x180007d96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d9b  cmp     [rbx+18h], r15
0x180007d9f  jnz     short loc_180007DB1
0x180007da1  cmp     [rbx+48h], r15
0x180007da5  jnz     short loc_180007DB1
0x180007da7  cmp     [rbx+30h], r15
0x180007dab  jz      loc_180007E41
0x180007db1  lea     r8, asc_180070208; "    "
0x180007db8  mov     rdx, rsi; unsigned __int16 *
0x180007dbb  mov     rcx, rax; this
0x180007dbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007dc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007dc7  test    r9, r9
0x180007dca  jz      short loc_180007DDE
0x180007dcc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007dd3  mov     rdx, rsi; unsigned __int16 *
0x180007dd6  mov     rcx, rax; this
0x180007dd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007dde  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007de2  test    r9, r9
0x180007de5  jz      short loc_180007DF9
0x180007de7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007dee  mov     rdx, rsi; unsigned __int16 *
0x180007df1  mov     rcx, rax; this
0x180007df4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007df9  mov     rcx, [rbx+28h]
0x180007dfd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007e01  mov     rdx, rsi; unsigned __int16 *
0x180007e04  test    rcx, rcx
0x180007e07  jz      short loc_180007E1F
0x180007e09  mov     [rsp+278h+lpBuffer], rcx
0x180007e0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007e15  mov     rcx, rax; this
0x180007e18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e1d  jmp     short loc_180007E41
0x180007e1f  mov     rcx, rax; this
0x180007e22  test    r9, r9
0x180007e25  jz      short loc_180007E35
0x180007e27  lea     r8, aHs; "[%hs]\n"
0x180007e2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e33  jmp     short loc_180007E41
0x180007e35  lea     r8, asc_180070280; "\n"
0x180007e3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e41  xor     eax, eax
0x180007e43  mov     rcx, [rsp+278h+var_38]
0x180007e4b  xor     rcx, rsp; StackCookie
0x180007e4e  call    __security_check_cookie
0x180007e53  mov     rbx, [rsp+278h+arg_18]
0x180007e5b  add     rsp, 250h
0x180007e62  pop     r15
0x180007e64  pop     r14
0x180007e66  pop     rdi
0x180007e67  pop     rsi
0x180007e68  pop     rbp
0x180007e69  retn
```
