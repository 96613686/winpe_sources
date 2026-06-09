# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003b74`
- end: `0x140003e2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1400029f4`
- `0x140002c64`
- `0x140004598`

## callees

- `0x140001cd0`
- `0x140002690`
- `0x140003b74`
- `0x140004898`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003d27`
- `KERNEL32!GetCurrentThreadId` at `0x140003d27`
- `KERNEL32!FormatMessageW` at `0x140003ca6`
- `KERNEL32!FormatMessageW` at `0x140003ca6`

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
          v8 = (const char *)&byte_140009860;
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
0x140003b74  mov     [rsp+arg_18], rbx
0x140003b79  push    rbp
0x140003b7a  push    rsi
0x140003b7b  push    rdi
0x140003b7c  push    r14
0x140003b7e  push    r15
0x140003b80  sub     rsp, 250h
0x140003b87  mov     rax, cs:__security_cookie
0x140003b8e  xor     rax, rsp
0x140003b91  mov     [rsp+278h+var_38], rax
0x140003b99  xor     r15d, r15d
0x140003b9c  mov     rbx, r8
0x140003b9f  mov     rsi, rdx
0x140003ba2  mov     r14, rcx
0x140003ba5  test    rdx, rdx
0x140003ba8  jz      loc_140003E01
0x140003bae  test    rcx, rcx
0x140003bb1  jz      loc_140003E01
0x140003bb7  mov     rax, cs:g_pfnResultLoggingCallback
0x140003bbe  mov     [rcx], r15w
0x140003bc2  test    rax, rax
0x140003bc5  jz      short loc_140003BE8
0x140003bc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003bce  jz      short loc_140003BE8
0x140003bd0  mov     r8, rdx
0x140003bd3  mov     rdx, rcx
0x140003bd6  mov     rcx, rbx
0x140003bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bde  cmp     [r14], r15w
0x140003be2  jnz     loc_140003E01
0x140003be8  mov     ecx, [rbx]
0x140003bea  mov     bpl, 8
0x140003bed  test    ecx, ecx
0x140003bef  jz      short loc_140003C3A
0x140003bf1  sub     ecx, 1
0x140003bf4  jz      short loc_140003C22
0x140003bf6  sub     ecx, 1
0x140003bf9  jz      short loc_140003C12
0x140003bfb  cmp     ecx, 1
0x140003bfe  jz      short loc_140003C09
0x140003c00  lea     rdi, byte_140009860
0x140003c07  jmp     short loc_140003C41
0x140003c09  lea     rdi, aFailfast; "FailFast"
0x140003c10  jmp     short loc_140003C41
0x140003c12  lea     rax, aLoghr; "LogHr"
0x140003c19  lea     rdi, aLognt; "LogNt"
0x140003c20  jmp     short loc_140003C30
0x140003c22  lea     rax, aReturnhr; "ReturnHr"
0x140003c29  lea     rdi, aReturnnt; "ReturnNt"
0x140003c30  test    [rbx+4], bpl
0x140003c34  cmovz   rdi, rax
0x140003c38  jmp     short loc_140003C41
0x140003c3a  lea     rdi, aException; "Exception"
0x140003c41  xor     edx, edx; Val
0x140003c43  lea     rcx, [rsp+278h+Buffer]; void *
0x140003c48  mov     r8d, 200h; Size
0x140003c4e  call    memset_0
0x140003c53  test    [rbx+4], bpl
0x140003c57  jz      short loc_140003C7C
0x140003c59  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003c60  mov     ebp, [rbx+0Ch]
0x140003c63  test    rax, rax
0x140003c66  jz      short loc_140003CAC
0x140003c68  mov     r8d, 100h
0x140003c6e  lea     rdx, [rsp+278h+Buffer]
0x140003c73  mov     ecx, ebp
0x140003c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c7a  jmp     short loc_140003CAC
0x140003c7c  mov     ebp, [rbx+8]
0x140003c7f  lea     rax, [rsp+278h+Buffer]
0x140003c84  mov     [rsp+278h+Arguments], r15; Arguments
0x140003c89  mov     r8d, ebp; dwMessageId
0x140003c8c  mov     [rsp+278h+nSize], 100h; nSize
0x140003c94  mov     r9d, 400h; dwLanguageId
0x140003c9a  xor     edx, edx; lpSource
0x140003c9c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003ca1  mov     ecx, 1200h; dwFlags
0x140003ca6  call    cs:__imp_FormatMessageW
0x140003cac  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003cb0  lea     rsi, [r14+rsi*2]
0x140003cb4  mov     rax, [rbx+88h]
0x140003cbb  mov     rdx, rsi; unsigned __int16 *
0x140003cbe  mov     rcx, [rbx+80h]
0x140003cc5  test    r9, r9
0x140003cc8  jz      short loc_140003CEC
0x140003cca  mov     [rsp+278h+Arguments], rax
0x140003ccf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003cd6  mov     eax, [rbx+40h]
0x140003cd9  mov     qword ptr [rsp+278h+nSize], rcx
0x140003cde  mov     rcx, r14; this
0x140003ce1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003ce5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003cea  jmp     short loc_140003D03
0x140003cec  mov     r9, rcx; unsigned __int16 *
0x140003cef  mov     [rsp+278h+lpBuffer], rax
0x140003cf4  mov     rcx, r14; this
0x140003cf7  lea     r8, aHsP; "%hs!%p: "
0x140003cfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d03  mov     r9, [rbx+90h]; unsigned __int16 *
0x140003d0a  mov     r14, rax
0x140003d0d  test    r9, r9
0x140003d10  jz      short loc_140003D27
0x140003d12  lea     r8, aCallerP; "(caller: %p) "
0x140003d19  mov     rdx, rsi; unsigned __int16 *
0x140003d1c  mov     rcx, rax; this
0x140003d1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d24  mov     r14, rax
0x140003d27  call    cs:__imp_GetCurrentThreadId
0x140003d2d  lea     rcx, [rsp+278h+Buffer]
0x140003d32  mov     r9, rdi; unsigned __int16 *
0x140003d35  mov     [rsp+278h+var_240], rcx
0x140003d3a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003d41  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003d45  mov     rdx, rsi; unsigned __int16 *
0x140003d48  mov     [rsp+278h+nSize], eax
0x140003d4c  mov     rcx, r14; this
0x140003d4f  mov     eax, [rbx+44h]
0x140003d52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003d56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d5b  cmp     [rbx+18h], r15
0x140003d5f  jnz     short loc_140003D71
0x140003d61  cmp     [rbx+48h], r15
0x140003d65  jnz     short loc_140003D71
0x140003d67  cmp     [rbx+30h], r15
0x140003d6b  jz      loc_140003E01
0x140003d71  lea     r8, asc_140009950; "    "
0x140003d78  mov     rdx, rsi; unsigned __int16 *
0x140003d7b  mov     rcx, rax; this
0x140003d7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d83  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003d87  test    r9, r9
0x140003d8a  jz      short loc_140003D9E
0x140003d8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003d93  mov     rdx, rsi; unsigned __int16 *
0x140003d96  mov     rcx, rax; this
0x140003d99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003da2  test    r9, r9
0x140003da5  jz      short loc_140003DB9
0x140003da7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140003dae  mov     rdx, rsi; unsigned __int16 *
0x140003db1  mov     rcx, rax; this
0x140003db4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003db9  mov     rcx, [rbx+28h]
0x140003dbd  mov     rdx, rsi; unsigned __int16 *
0x140003dc0  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003dc4  test    rcx, rcx
0x140003dc7  jz      short loc_140003DDF
0x140003dc9  mov     [rsp+278h+lpBuffer], rcx
0x140003dce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003dd5  mov     rcx, rax; this
0x140003dd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003ddd  jmp     short loc_140003E01
0x140003ddf  mov     rcx, rax; this
0x140003de2  test    r9, r9
0x140003de5  jz      short loc_140003DF5
0x140003de7  lea     r8, aHs; "[%hs]\n"
0x140003dee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003df3  jmp     short loc_140003E01
0x140003df5  lea     r8, asc_1400099C8; "\n"
0x140003dfc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003e01  xor     eax, eax
0x140003e03  mov     rcx, [rsp+278h+var_38]
0x140003e0b  xor     rcx, rsp; StackCookie
0x140003e0e  call    __security_check_cookie
0x140003e13  mov     rbx, [rsp+278h+arg_18]
0x140003e1b  add     rsp, 250h
0x140003e22  pop     r15
0x140003e24  pop     r14
0x140003e26  pop     rdi
0x140003e27  pop     rsi
0x140003e28  pop     rbp
0x140003e29  retn
```
