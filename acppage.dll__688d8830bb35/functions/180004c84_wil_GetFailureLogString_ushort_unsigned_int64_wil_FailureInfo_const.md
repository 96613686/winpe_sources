# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004c84`
- end: `0x180004f3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800028f4`
- `0x180002b5c`
- `0x180005794`

## callees

- `0x180004c84`
- `0x180005a94`
- `0x18001623a`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004e37`
- `KERNEL32!GetCurrentThreadId` at `0x180004e37`
- `KERNEL32!FormatMessageW` at `0x180004db6`
- `KERNEL32!FormatMessageW` at `0x180004db6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&word_1800196B6;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
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
0x180004ca9  xor     r15d, r15d
0x180004cac  mov     rbx, r8
0x180004caf  mov     rsi, rdx
0x180004cb2  mov     r14, rcx
0x180004cb5  test    rdx, rdx
0x180004cb8  jz      loc_180004F11
0x180004cbe  test    rcx, rcx
0x180004cc1  jz      loc_180004F11
0x180004cc7  mov     rax, cs:g_pfnResultLoggingCallback
0x180004cce  mov     [rcx], r15w
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
0x180004d10  lea     rdi, word_1800196B6
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
0x180004d53  lea     rcx, [rsp+278h+Buffer]; void *
0x180004d58  mov     r8d, 200h; Size
0x180004d5e  call    memset_0
0x180004d63  test    [rbx+4], bpl
0x180004d67  jz      short loc_180004D8C
0x180004d69  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004d70  mov     ebp, [rbx+0Ch]
0x180004d73  test    rax, rax
0x180004d76  jz      short loc_180004DBC
0x180004d78  mov     r8d, 100h
0x180004d7e  lea     rdx, [rsp+278h+Buffer]
0x180004d83  mov     ecx, ebp
0x180004d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8a  jmp     short loc_180004DBC
0x180004d8c  mov     ebp, [rbx+8]
0x180004d8f  lea     rax, [rsp+278h+Buffer]
0x180004d94  mov     [rsp+278h+Arguments], r15; Arguments
0x180004d99  mov     r8d, ebp; dwMessageId
0x180004d9c  mov     [rsp+278h+nSize], 100h; nSize
0x180004da4  mov     r9d, 400h; dwLanguageId
0x180004daa  xor     edx, edx; lpSource
0x180004dac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004db1  mov     ecx, 1200h; dwFlags
0x180004db6  call    cs:__imp_FormatMessageW
0x180004dbc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004dc0  lea     rsi, [r14+rsi*2]
0x180004dc4  mov     rax, [rbx+88h]
0x180004dcb  mov     rdx, rsi; unsigned __int16 *
0x180004dce  mov     rcx, [rbx+80h]
0x180004dd5  test    r9, r9
0x180004dd8  jz      short loc_180004DFC
0x180004dda  mov     [rsp+278h+Arguments], rax
0x180004ddf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004de6  mov     eax, [rbx+40h]
0x180004de9  mov     qword ptr [rsp+278h+nSize], rcx
0x180004dee  mov     rcx, r14; this
0x180004df1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004df5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dfa  jmp     short loc_180004E13
0x180004dfc  mov     r9, rcx; unsigned __int16 *
0x180004dff  mov     [rsp+278h+lpBuffer], rax
0x180004e04  mov     rcx, r14; this
0x180004e07  lea     r8, aHsP; "%hs!%p: "
0x180004e0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e13  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004e1a  mov     r14, rax
0x180004e1d  test    r9, r9
0x180004e20  jz      short loc_180004E37
0x180004e22  lea     r8, aCallerP; "(caller: %p) "
0x180004e29  mov     rdx, rsi; unsigned __int16 *
0x180004e2c  mov     rcx, rax; this
0x180004e2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e34  mov     r14, rax
0x180004e37  call    cs:__imp_GetCurrentThreadId
0x180004e3d  lea     rcx, [rsp+278h+Buffer]
0x180004e42  mov     r9, rdi; unsigned __int16 *
0x180004e45  mov     [rsp+278h+var_240], rcx
0x180004e4a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004e51  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004e55  mov     rdx, rsi; unsigned __int16 *
0x180004e58  mov     [rsp+278h+nSize], eax
0x180004e5c  mov     rcx, r14; this
0x180004e5f  mov     eax, [rbx+44h]
0x180004e62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004e66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e6b  cmp     [rbx+18h], r15
0x180004e6f  jnz     short loc_180004E81
0x180004e71  cmp     [rbx+48h], r15
0x180004e75  jnz     short loc_180004E81
0x180004e77  cmp     [rbx+30h], r15
0x180004e7b  jz      loc_180004F11
0x180004e81  lea     r8, asc_1800197B8; "    "
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
0x180004ecd  mov     rdx, rsi; unsigned __int16 *
0x180004ed0  mov     r9, [rbx+30h]; unsigned __int16 *
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
0x180004f05  lea     r8, asc_180019830; "\n"
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
