# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004c84`
- end: `0x180004f3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180002780`
- `0x180002a00`
- `0x1800055e4`
- `0x180008b60`
- `0x1800091c8`
- `0x18000cd66`
- `0x18000ce9a`
- `0x18000d003`
- `0x18000d2d3`

## callees

- `0x1800016a0`
- `0x1800020e4`
- `0x180004c84`
- `0x1800058e4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004e37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004db6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004db6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&byte_18000FBC8;
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
0x180004c84  mov     [rsp+arg_18], rbx
0x180004c89  push    rbp
0x180004c8a  push    rsi
0x180004c8b  push    rdi
0x180004c8c  push    r14
0x180004c8e  push    r15
0x180004c90  sub     rsp, 250h
0x180004c97  mov     rax, cs:__security_cookie
0x180004c9e  xor     rax, rsp
0x180004ca1  mov     [rsp+278h+var_38], rax
0x180004ca9  mov     rbx, r8
0x180004cac  mov     rsi, rdx
0x180004caf  mov     r14, rcx
0x180004cb2  xor     r15d, r15d
0x180004cb5  test    rdx, rdx
0x180004cb8  jz      loc_180004F11
0x180004cbe  test    rcx, rcx
0x180004cc1  jz      loc_180004F11
0x180004cc7  mov     [rcx], r15w
0x180004ccb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004cd2  test    rax, rax
0x180004cd5  jz      short loc_180004CF8
0x180004cd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004cde  jz      short loc_180004CF8
0x180004ce0  mov     r8, rdx
0x180004ce3  mov     rdx, rcx
0x180004ce6  mov     rcx, rbx
0x180004ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cee  cmp     [r14], r15w
0x180004cf2  jnz     loc_180004F11
0x180004cf8  mov     ecx, [rbx]
0x180004cfa  mov     bpl, 8
0x180004cfd  test    ecx, ecx
0x180004cff  jz      short loc_180004D4A
0x180004d01  sub     ecx, 1
0x180004d04  jz      short loc_180004D32
0x180004d06  sub     ecx, 1
0x180004d09  jz      short loc_180004D22
0x180004d0b  cmp     ecx, 1
0x180004d0e  jz      short loc_180004D19
0x180004d10  lea     rdi, byte_18000FBC8
0x180004d17  jmp     short loc_180004D51
0x180004d19  lea     rdi, aFailfast; "FailFast"
0x180004d20  jmp     short loc_180004D51
0x180004d22  lea     rax, aLoghr; "LogHr"
0x180004d29  lea     rdi, aLognt; "LogNt"
0x180004d30  jmp     short loc_180004D40
0x180004d32  lea     rax, aReturnhr; "ReturnHr"
0x180004d39  lea     rdi, aReturnnt; "ReturnNt"
0x180004d40  test    [rbx+4], bpl
0x180004d44  cmovz   rdi, rax
0x180004d48  jmp     short loc_180004D51
0x180004d4a  lea     rdi, aException; "Exception"
0x180004d51  xor     edx, edx; Val
0x180004d53  mov     r8d, 200h; Size
0x180004d59  lea     rcx, [rsp+278h+Buffer]; void *
0x180004d5e  call    memset_0
0x180004d63  test    [rbx+4], bpl
0x180004d67  jz      short loc_180004D8C
0x180004d69  mov     ebp, [rbx+0Ch]
0x180004d6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004d73  test    rax, rax
0x180004d76  jz      short loc_180004DBC
0x180004d78  mov     r8d, 100h
0x180004d7e  lea     rdx, [rsp+278h+Buffer]
0x180004d83  mov     ecx, ebp
0x180004d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8a  jmp     short loc_180004DBC
0x180004d8c  mov     ebp, [rbx+8]
0x180004d8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004d94  mov     [rsp+278h+nSize], 100h; nSize
0x180004d9c  lea     rax, [rsp+278h+Buffer]
0x180004da1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004da6  mov     r9d, 400h; dwLanguageId
0x180004dac  mov     r8d, ebp; dwMessageId
0x180004daf  xor     edx, edx; lpSource
0x180004db1  mov     ecx, 1200h; dwFlags
0x180004db6  call    cs:__imp_FormatMessageW
0x180004dbc  lea     rsi, [r14+rsi*2]
0x180004dc0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004dc4  mov     rax, [rbx+88h]
0x180004dcb  mov     rcx, [rbx+80h]
0x180004dd2  mov     rdx, rsi; unsigned __int16 *
0x180004dd5  test    r9, r9
0x180004dd8  jz      short loc_180004DFC
0x180004dda  mov     [rsp+278h+Arguments], rax
0x180004ddf  mov     qword ptr [rsp+278h+nSize], rcx
0x180004de4  mov     eax, [rbx+40h]
0x180004de7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004deb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004df2  mov     rcx, r14; this
0x180004df5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dfa  jmp     short loc_180004E13
0x180004dfc  mov     [rsp+278h+lpBuffer], rax
0x180004e01  mov     r9, rcx; unsigned __int16 *
0x180004e04  lea     r8, aHsP; "%hs!%p: "
0x180004e0b  mov     rcx, r14; this
0x180004e0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e13  mov     r14, rax
0x180004e16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004e1d  test    r9, r9
0x180004e20  jz      short loc_180004E37
0x180004e22  lea     r8, aCallerP; "(caller: %p) "
0x180004e29  mov     rdx, rsi; unsigned __int16 *
0x180004e2c  mov     rcx, rax; this
0x180004e2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e34  mov     r14, rax
0x180004e37  call    cs:__imp_GetCurrentThreadId
0x180004e3d  lea     rcx, [rsp+278h+Buffer]
0x180004e42  mov     [rsp+278h+var_240], rcx
0x180004e47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004e4b  mov     [rsp+278h+nSize], eax
0x180004e4f  mov     eax, [rbx+44h]
0x180004e52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004e56  mov     r9, rdi; unsigned __int16 *
0x180004e59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004e60  mov     rdx, rsi; unsigned __int16 *
0x180004e63  mov     rcx, r14; this
0x180004e66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e6b  cmp     [rbx+18h], r15
0x180004e6f  jnz     short loc_180004E81
0x180004e71  cmp     [rbx+48h], r15
0x180004e75  jnz     short loc_180004E81
0x180004e77  cmp     [rbx+30h], r15
0x180004e7b  jz      loc_180004F11
0x180004e81  lea     r8, asc_18000FCE0; "    "
0x180004e88  mov     rdx, rsi; unsigned __int16 *
0x180004e8b  mov     rcx, rax; this
0x180004e8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004e97  test    r9, r9
0x180004e9a  jz      short loc_180004EAE
0x180004e9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004ea3  mov     rdx, rsi; unsigned __int16 *
0x180004ea6  mov     rcx, rax; this
0x180004ea9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004eb2  test    r9, r9
0x180004eb5  jz      short loc_180004EC9
0x180004eb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004ebe  mov     rdx, rsi; unsigned __int16 *
0x180004ec1  mov     rcx, rax; this
0x180004ec4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ec9  mov     rcx, [rbx+28h]
0x180004ecd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004ed1  mov     rdx, rsi; unsigned __int16 *
0x180004ed4  test    rcx, rcx
0x180004ed7  jz      short loc_180004EEF
0x180004ed9  mov     [rsp+278h+lpBuffer], rcx
0x180004ede  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004ee5  mov     rcx, rax; this
0x180004ee8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eed  jmp     short loc_180004F11
0x180004eef  mov     rcx, rax; this
0x180004ef2  test    r9, r9
0x180004ef5  jz      short loc_180004F05
0x180004ef7  lea     r8, aHs; "[%hs]\n"
0x180004efe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f03  jmp     short loc_180004F11
0x180004f05  lea     r8, asc_18000FD58; "\n"
0x180004f0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f11  xor     eax, eax
0x180004f13  mov     rcx, [rsp+278h+var_38]
0x180004f1b  xor     rcx, rsp; StackCookie
0x180004f1e  call    __security_check_cookie
0x180004f23  mov     rbx, [rsp+278h+arg_18]
0x180004f2b  add     rsp, 250h
0x180004f32  pop     r15
0x180004f34  pop     r14
0x180004f36  pop     rdi
0x180004f37  pop     rsi
0x180004f38  pop     rbp
0x180004f39  retn
```
