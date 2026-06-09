# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004cc4`
- end: `0x180004f7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003e64`
- `0x18000568c`
- `0x180005b58`
- `0x180006c00`

## callees

- `0x180002420`
- `0x180003088`
- `0x180004cc4`
- `0x18000598c`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004df6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004df6`

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
          v7 = (const char *)&dword_18014ADBC;
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
0x180004cc4  mov     [rsp+arg_18], rbx
0x180004cc9  push    rbp
0x180004cca  push    rsi
0x180004ccb  push    rdi
0x180004ccc  push    r14
0x180004cce  push    r15
0x180004cd0  sub     rsp, 250h
0x180004cd7  mov     rax, cs:__security_cookie
0x180004cde  xor     rax, rsp
0x180004ce1  mov     [rsp+278h+var_38], rax
0x180004ce9  mov     rbx, r8
0x180004cec  mov     rsi, rdx
0x180004cef  mov     r14, rcx
0x180004cf2  xor     r15d, r15d
0x180004cf5  test    rdx, rdx
0x180004cf8  jz      loc_180004F51
0x180004cfe  test    rcx, rcx
0x180004d01  jz      loc_180004F51
0x180004d07  mov     [rcx], r15w
0x180004d0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004d12  test    rax, rax
0x180004d15  jz      short loc_180004D38
0x180004d17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004d1e  jz      short loc_180004D38
0x180004d20  mov     r8, rdx
0x180004d23  mov     rdx, rcx
0x180004d26  mov     rcx, rbx
0x180004d29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d2e  cmp     [r14], r15w
0x180004d32  jnz     loc_180004F51
0x180004d38  mov     ecx, [rbx]
0x180004d3a  mov     bpl, 8
0x180004d3d  test    ecx, ecx
0x180004d3f  jz      short loc_180004D8A
0x180004d41  sub     ecx, 1
0x180004d44  jz      short loc_180004D72
0x180004d46  sub     ecx, 1
0x180004d49  jz      short loc_180004D62
0x180004d4b  cmp     ecx, 1
0x180004d4e  jz      short loc_180004D59
0x180004d50  lea     rdi, dword_18014ADBC
0x180004d57  jmp     short loc_180004D91
0x180004d59  lea     rdi, aFailfast; "FailFast"
0x180004d60  jmp     short loc_180004D91
0x180004d62  lea     rax, aLoghr; "LogHr"
0x180004d69  lea     rdi, aLognt; "LogNt"
0x180004d70  jmp     short loc_180004D80
0x180004d72  lea     rax, aReturnhr; "ReturnHr"
0x180004d79  lea     rdi, aReturnnt; "ReturnNt"
0x180004d80  test    [rbx+4], bpl
0x180004d84  cmovz   rdi, rax
0x180004d88  jmp     short loc_180004D91
0x180004d8a  lea     rdi, aException; "Exception"
0x180004d91  xor     edx, edx; Val
0x180004d93  mov     r8d, 200h; Size
0x180004d99  lea     rcx, [rsp+278h+Buffer]; void *
0x180004d9e  call    memset_0
0x180004da3  test    [rbx+4], bpl
0x180004da7  jz      short loc_180004DCC
0x180004da9  mov     ebp, [rbx+0Ch]
0x180004dac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004db3  test    rax, rax
0x180004db6  jz      short loc_180004DFC
0x180004db8  mov     r8d, 100h
0x180004dbe  lea     rdx, [rsp+278h+Buffer]
0x180004dc3  mov     ecx, ebp
0x180004dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dca  jmp     short loc_180004DFC
0x180004dcc  mov     ebp, [rbx+8]
0x180004dcf  mov     [rsp+278h+Arguments], r15; Arguments
0x180004dd4  mov     [rsp+278h+nSize], 100h; nSize
0x180004ddc  lea     rax, [rsp+278h+Buffer]
0x180004de1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004de6  mov     r9d, 400h; dwLanguageId
0x180004dec  mov     r8d, ebp; dwMessageId
0x180004def  xor     edx, edx; lpSource
0x180004df1  mov     ecx, 1200h; dwFlags
0x180004df6  call    cs:__imp_FormatMessageW
0x180004dfc  lea     rsi, [r14+rsi*2]
0x180004e00  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004e04  mov     rax, [rbx+88h]
0x180004e0b  mov     rcx, [rbx+80h]
0x180004e12  mov     rdx, rsi; unsigned __int16 *
0x180004e15  test    r9, r9
0x180004e18  jz      short loc_180004E3C
0x180004e1a  mov     [rsp+278h+Arguments], rax
0x180004e1f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004e24  mov     eax, [rbx+40h]
0x180004e27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004e2b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004e32  mov     rcx, r14; this
0x180004e35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e3a  jmp     short loc_180004E53
0x180004e3c  mov     [rsp+278h+lpBuffer], rax
0x180004e41  mov     r9, rcx; unsigned __int16 *
0x180004e44  lea     r8, aHsP; "%hs!%p: "
0x180004e4b  mov     rcx, r14; this
0x180004e4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e53  mov     r14, rax
0x180004e56  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004e5d  test    r9, r9
0x180004e60  jz      short loc_180004E77
0x180004e62  lea     r8, aCallerP; "(caller: %p) "
0x180004e69  mov     rdx, rsi; unsigned __int16 *
0x180004e6c  mov     rcx, rax; this
0x180004e6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e74  mov     r14, rax
0x180004e77  call    cs:__imp_GetCurrentThreadId
0x180004e7d  lea     rcx, [rsp+278h+Buffer]
0x180004e82  mov     [rsp+278h+var_240], rcx
0x180004e87  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004e8b  mov     [rsp+278h+nSize], eax
0x180004e8f  mov     eax, [rbx+44h]
0x180004e92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004e96  mov     r9, rdi; unsigned __int16 *
0x180004e99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004ea0  mov     rdx, rsi; unsigned __int16 *
0x180004ea3  mov     rcx, r14; this
0x180004ea6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eab  cmp     [rbx+18h], r15
0x180004eaf  jnz     short loc_180004EC1
0x180004eb1  cmp     [rbx+48h], r15
0x180004eb5  jnz     short loc_180004EC1
0x180004eb7  cmp     [rbx+30h], r15
0x180004ebb  jz      loc_180004F51
0x180004ec1  lea     r8, asc_18014AEE0; "    "
0x180004ec8  mov     rdx, rsi; unsigned __int16 *
0x180004ecb  mov     rcx, rax; this
0x180004ece  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ed3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004ed7  test    r9, r9
0x180004eda  jz      short loc_180004EEE
0x180004edc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004ee3  mov     rdx, rsi; unsigned __int16 *
0x180004ee6  mov     rcx, rax; this
0x180004ee9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004ef2  test    r9, r9
0x180004ef5  jz      short loc_180004F09
0x180004ef7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004efe  mov     rdx, rsi; unsigned __int16 *
0x180004f01  mov     rcx, rax; this
0x180004f04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f09  mov     rcx, [rbx+28h]
0x180004f0d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004f11  mov     rdx, rsi; unsigned __int16 *
0x180004f14  test    rcx, rcx
0x180004f17  jz      short loc_180004F2F
0x180004f19  mov     [rsp+278h+lpBuffer], rcx
0x180004f1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004f25  mov     rcx, rax; this
0x180004f28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f2d  jmp     short loc_180004F51
0x180004f2f  mov     rcx, rax; this
0x180004f32  test    r9, r9
0x180004f35  jz      short loc_180004F45
0x180004f37  lea     r8, aHs; "[%hs]\n"
0x180004f3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f43  jmp     short loc_180004F51
0x180004f45  lea     r8, asc_18014AF58; "\n"
0x180004f4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f51  xor     eax, eax
0x180004f53  mov     rcx, [rsp+278h+var_38]
0x180004f5b  xor     rcx, rsp; StackCookie
0x180004f5e  call    __security_check_cookie
0x180004f63  mov     rbx, [rsp+278h+arg_18]
0x180004f6b  add     rsp, 250h
0x180004f72  pop     r15
0x180004f74  pop     r14
0x180004f76  pop     rdi
0x180004f77  pop     rsi
0x180004f78  pop     rbp
0x180004f79  retn
```
