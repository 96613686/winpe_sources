# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007cc4`
- end: `0x180007f7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800064d0`
- `0x180008470`
- `0x180008928`
- `0x180009f40`

## callees

- `0x180003c80`
- `0x1800045ba`
- `0x180007cc4`
- `0x180008770`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007e77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007df6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007df6`

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
          v7 = (const char *)&word_1804F782A;
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
0x180007cc4  mov     [rsp+arg_18], rbx
0x180007cc9  push    rbp
0x180007cca  push    rsi
0x180007ccb  push    rdi
0x180007ccc  push    r14
0x180007cce  push    r15
0x180007cd0  sub     rsp, 250h
0x180007cd7  mov     rax, cs:__security_cookie
0x180007cde  xor     rax, rsp
0x180007ce1  mov     [rsp+278h+var_38], rax
0x180007ce9  mov     rbx, r8
0x180007cec  mov     rsi, rdx
0x180007cef  mov     r14, rcx
0x180007cf2  xor     r15d, r15d
0x180007cf5  test    rdx, rdx
0x180007cf8  jz      loc_180007F51
0x180007cfe  test    rcx, rcx
0x180007d01  jz      loc_180007F51
0x180007d07  mov     [rcx], r15w
0x180007d0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d12  test    rax, rax
0x180007d15  jz      short loc_180007D38
0x180007d17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007d1e  jz      short loc_180007D38
0x180007d20  mov     r8, rdx
0x180007d23  mov     rdx, rcx
0x180007d26  mov     rcx, rbx
0x180007d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2e  cmp     [r14], r15w
0x180007d32  jnz     loc_180007F51
0x180007d38  mov     ecx, [rbx]
0x180007d3a  mov     bpl, 8
0x180007d3d  test    ecx, ecx
0x180007d3f  jz      short loc_180007D8A
0x180007d41  sub     ecx, 1
0x180007d44  jz      short loc_180007D72
0x180007d46  sub     ecx, 1
0x180007d49  jz      short loc_180007D62
0x180007d4b  cmp     ecx, 1
0x180007d4e  jz      short loc_180007D59
0x180007d50  lea     rdi, word_1804F782A
0x180007d57  jmp     short loc_180007D91
0x180007d59  lea     rdi, aFailfast; "FailFast"
0x180007d60  jmp     short loc_180007D91
0x180007d62  lea     rax, aLoghr; "LogHr"
0x180007d69  lea     rdi, aLognt; "LogNt"
0x180007d70  jmp     short loc_180007D80
0x180007d72  lea     rax, aReturnhr; "ReturnHr"
0x180007d79  lea     rdi, aReturnnt; "ReturnNt"
0x180007d80  test    [rbx+4], bpl
0x180007d84  cmovz   rdi, rax
0x180007d88  jmp     short loc_180007D91
0x180007d8a  lea     rdi, aException; "Exception"
0x180007d91  xor     edx, edx; Val
0x180007d93  mov     r8d, 200h; Size
0x180007d99  lea     rcx, [rsp+278h+Buffer]; void *
0x180007d9e  call    memset_0
0x180007da3  test    [rbx+4], bpl
0x180007da7  jz      short loc_180007DCC
0x180007da9  mov     ebp, [rbx+0Ch]
0x180007dac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007db3  test    rax, rax
0x180007db6  jz      short loc_180007DFC
0x180007db8  mov     r8d, 100h
0x180007dbe  lea     rdx, [rsp+278h+Buffer]
0x180007dc3  mov     ecx, ebp
0x180007dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dca  jmp     short loc_180007DFC
0x180007dcc  mov     ebp, [rbx+8]
0x180007dcf  mov     [rsp+278h+Arguments], r15; Arguments
0x180007dd4  mov     [rsp+278h+nSize], 100h; nSize
0x180007ddc  lea     rax, [rsp+278h+Buffer]
0x180007de1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007de6  mov     r9d, 400h; dwLanguageId
0x180007dec  mov     r8d, ebp; dwMessageId
0x180007def  xor     edx, edx; lpSource
0x180007df1  mov     ecx, 1200h; dwFlags
0x180007df6  call    cs:__imp_FormatMessageW
0x180007dfc  lea     rsi, [r14+rsi*2]
0x180007e00  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007e04  mov     rax, [rbx+88h]
0x180007e0b  mov     rcx, [rbx+80h]
0x180007e12  mov     rdx, rsi; unsigned __int16 *
0x180007e15  test    r9, r9
0x180007e18  jz      short loc_180007E3C
0x180007e1a  mov     [rsp+278h+Arguments], rax
0x180007e1f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007e24  mov     eax, [rbx+40h]
0x180007e27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007e2b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007e32  mov     rcx, r14; this
0x180007e35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e3a  jmp     short loc_180007E53
0x180007e3c  mov     [rsp+278h+lpBuffer], rax
0x180007e41  mov     r9, rcx; unsigned __int16 *
0x180007e44  lea     r8, aHsP; "%hs!%p: "
0x180007e4b  mov     rcx, r14; this
0x180007e4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e53  mov     r14, rax
0x180007e56  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007e5d  test    r9, r9
0x180007e60  jz      short loc_180007E77
0x180007e62  lea     r8, aCallerP; "(caller: %p) "
0x180007e69  mov     rdx, rsi; unsigned __int16 *
0x180007e6c  mov     rcx, rax; this
0x180007e6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e74  mov     r14, rax
0x180007e77  call    cs:__imp_GetCurrentThreadId
0x180007e7d  lea     rcx, [rsp+278h+Buffer]
0x180007e82  mov     [rsp+278h+var_240], rcx
0x180007e87  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007e8b  mov     [rsp+278h+nSize], eax
0x180007e8f  mov     eax, [rbx+44h]
0x180007e92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007e96  mov     r9, rdi; unsigned __int16 *
0x180007e99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007ea0  mov     rdx, rsi; unsigned __int16 *
0x180007ea3  mov     rcx, r14; this
0x180007ea6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007eab  cmp     [rbx+18h], r15
0x180007eaf  jnz     short loc_180007EC1
0x180007eb1  cmp     [rbx+48h], r15
0x180007eb5  jnz     short loc_180007EC1
0x180007eb7  cmp     [rbx+30h], r15
0x180007ebb  jz      loc_180007F51
0x180007ec1  lea     r8, asc_1804F7930; "    "
0x180007ec8  mov     rdx, rsi; unsigned __int16 *
0x180007ecb  mov     rcx, rax; this
0x180007ece  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ed3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007ed7  test    r9, r9
0x180007eda  jz      short loc_180007EEE
0x180007edc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007ee3  mov     rdx, rsi; unsigned __int16 *
0x180007ee6  mov     rcx, rax; this
0x180007ee9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007eee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007ef2  test    r9, r9
0x180007ef5  jz      short loc_180007F09
0x180007ef7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007efe  mov     rdx, rsi; unsigned __int16 *
0x180007f01  mov     rcx, rax; this
0x180007f04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f09  mov     rcx, [rbx+28h]
0x180007f0d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007f11  mov     rdx, rsi; unsigned __int16 *
0x180007f14  test    rcx, rcx
0x180007f17  jz      short loc_180007F2F
0x180007f19  mov     [rsp+278h+lpBuffer], rcx
0x180007f1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007f25  mov     rcx, rax; this
0x180007f28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f2d  jmp     short loc_180007F51
0x180007f2f  mov     rcx, rax; this
0x180007f32  test    r9, r9
0x180007f35  jz      short loc_180007F45
0x180007f37  lea     r8, aHs; "[%hs]\n"
0x180007f3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f43  jmp     short loc_180007F51
0x180007f45  lea     r8, asc_1804F7980; "\n"
0x180007f4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007f51  xor     eax, eax
0x180007f53  mov     rcx, [rsp+278h+var_38]
0x180007f5b  xor     rcx, rsp; StackCookie
0x180007f5e  call    __security_check_cookie
0x180007f63  mov     rbx, [rsp+278h+arg_18]
0x180007f6b  add     rsp, 250h
0x180007f72  pop     r15
0x180007f74  pop     r14
0x180007f76  pop     rdi
0x180007f77  pop     rsi
0x180007f78  pop     rbp
0x180007f79  retn
```
