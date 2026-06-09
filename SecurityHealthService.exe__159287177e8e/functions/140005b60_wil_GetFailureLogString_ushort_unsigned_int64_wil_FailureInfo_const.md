# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005b60`
- end: `0x140005e16`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140005778`
- `0x140006320`
- `0x1400079d0`
- `0x14000c770`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x140005b60`
- `0x140006620`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005d13`
- `KERNEL32!GetCurrentThreadId` at `0x140005d13`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005c92`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005c92`

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
          v7 = (const char *)&qword_140015AC0;
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
0x140005b60  mov     [rsp+arg_18], rbx
0x140005b65  push    rbp
0x140005b66  push    rsi
0x140005b67  push    rdi
0x140005b68  push    r14
0x140005b6a  push    r15
0x140005b6c  sub     rsp, 250h
0x140005b73  mov     rax, cs:__security_cookie
0x140005b7a  xor     rax, rsp
0x140005b7d  mov     [rsp+278h+var_38], rax
0x140005b85  mov     rbx, r8
0x140005b88  mov     rsi, rdx
0x140005b8b  mov     r14, rcx
0x140005b8e  xor     r15d, r15d
0x140005b91  test    rdx, rdx
0x140005b94  jz      loc_140005DED
0x140005b9a  test    rcx, rcx
0x140005b9d  jz      loc_140005DED
0x140005ba3  mov     [rcx], r15w
0x140005ba7  mov     rax, cs:g_pfnResultLoggingCallback
0x140005bae  test    rax, rax
0x140005bb1  jz      short loc_140005BD4
0x140005bb3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005bba  jz      short loc_140005BD4
0x140005bbc  mov     r8, rdx
0x140005bbf  mov     rdx, rcx
0x140005bc2  mov     rcx, rbx
0x140005bc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bca  cmp     [r14], r15w
0x140005bce  jnz     loc_140005DED
0x140005bd4  mov     ecx, [rbx]
0x140005bd6  mov     bpl, 8
0x140005bd9  test    ecx, ecx
0x140005bdb  jz      short loc_140005C26
0x140005bdd  sub     ecx, 1
0x140005be0  jz      short loc_140005C0E
0x140005be2  sub     ecx, 1
0x140005be5  jz      short loc_140005BFE
0x140005be7  cmp     ecx, 1
0x140005bea  jz      short loc_140005BF5
0x140005bec  lea     rdi, qword_140015AC0
0x140005bf3  jmp     short loc_140005C2D
0x140005bf5  lea     rdi, aFailfast; "FailFast"
0x140005bfc  jmp     short loc_140005C2D
0x140005bfe  lea     rax, aLoghr; "LogHr"
0x140005c05  lea     rdi, aLognt; "LogNt"
0x140005c0c  jmp     short loc_140005C1C
0x140005c0e  lea     rax, aReturnhr; "ReturnHr"
0x140005c15  lea     rdi, aReturnnt; "ReturnNt"
0x140005c1c  test    [rbx+4], bpl
0x140005c20  cmovz   rdi, rax
0x140005c24  jmp     short loc_140005C2D
0x140005c26  lea     rdi, aException; "Exception"
0x140005c2d  xor     edx, edx; Val
0x140005c2f  mov     r8d, 200h; Size
0x140005c35  lea     rcx, [rsp+278h+Buffer]; void *
0x140005c3a  call    memset_0
0x140005c3f  test    [rbx+4], bpl
0x140005c43  jz      short loc_140005C68
0x140005c45  mov     ebp, [rbx+0Ch]
0x140005c48  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005c4f  test    rax, rax
0x140005c52  jz      short loc_140005C98
0x140005c54  mov     r8d, 100h
0x140005c5a  lea     rdx, [rsp+278h+Buffer]
0x140005c5f  mov     ecx, ebp
0x140005c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c66  jmp     short loc_140005C98
0x140005c68  mov     ebp, [rbx+8]
0x140005c6b  mov     [rsp+278h+Arguments], r15; Arguments
0x140005c70  mov     [rsp+278h+nSize], 100h; nSize
0x140005c78  lea     rax, [rsp+278h+Buffer]
0x140005c7d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005c82  mov     r9d, 400h; dwLanguageId
0x140005c88  mov     r8d, ebp; dwMessageId
0x140005c8b  xor     edx, edx; lpSource
0x140005c8d  mov     ecx, 1200h; dwFlags
0x140005c92  call    cs:__imp_FormatMessageW
0x140005c98  lea     rsi, [r14+rsi*2]
0x140005c9c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005ca0  mov     rax, [rbx+88h]
0x140005ca7  mov     rcx, [rbx+80h]
0x140005cae  mov     rdx, rsi; unsigned __int16 *
0x140005cb1  test    r9, r9
0x140005cb4  jz      short loc_140005CD8
0x140005cb6  mov     [rsp+278h+Arguments], rax
0x140005cbb  mov     qword ptr [rsp+278h+nSize], rcx
0x140005cc0  mov     eax, [rbx+40h]
0x140005cc3  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005cc7  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005cce  mov     rcx, r14; this
0x140005cd1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005cd6  jmp     short loc_140005CEF
0x140005cd8  mov     [rsp+278h+lpBuffer], rax
0x140005cdd  mov     r9, rcx; unsigned __int16 *
0x140005ce0  lea     r8, aHsP; "%hs!%p: "
0x140005ce7  mov     rcx, r14; this
0x140005cea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005cef  mov     r14, rax
0x140005cf2  mov     r9, [rbx+90h]; unsigned __int16 *
0x140005cf9  test    r9, r9
0x140005cfc  jz      short loc_140005D13
0x140005cfe  lea     r8, aCallerP; "(caller: %p) "
0x140005d05  mov     rdx, rsi; unsigned __int16 *
0x140005d08  mov     rcx, rax; this
0x140005d0b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005d10  mov     r14, rax
0x140005d13  call    cs:__imp_GetCurrentThreadId
0x140005d19  lea     rcx, [rsp+278h+Buffer]
0x140005d1e  mov     [rsp+278h+var_240], rcx
0x140005d23  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005d27  mov     [rsp+278h+nSize], eax
0x140005d2b  mov     eax, [rbx+44h]
0x140005d2e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005d32  mov     r9, rdi; unsigned __int16 *
0x140005d35  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005d3c  mov     rdx, rsi; unsigned __int16 *
0x140005d3f  mov     rcx, r14; this
0x140005d42  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005d47  cmp     [rbx+18h], r15
0x140005d4b  jnz     short loc_140005D5D
0x140005d4d  cmp     [rbx+48h], r15
0x140005d51  jnz     short loc_140005D5D
0x140005d53  cmp     [rbx+30h], r15
0x140005d57  jz      loc_140005DED
0x140005d5d  lea     r8, asc_140015BB0; "    "
0x140005d64  mov     rdx, rsi; unsigned __int16 *
0x140005d67  mov     rcx, rax; this
0x140005d6a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005d6f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005d73  test    r9, r9
0x140005d76  jz      short loc_140005D8A
0x140005d78  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005d7f  mov     rdx, rsi; unsigned __int16 *
0x140005d82  mov     rcx, rax; this
0x140005d85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005d8a  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005d8e  test    r9, r9
0x140005d91  jz      short loc_140005DA5
0x140005d93  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140005d9a  mov     rdx, rsi; unsigned __int16 *
0x140005d9d  mov     rcx, rax; this
0x140005da0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005da5  mov     rcx, [rbx+28h]
0x140005da9  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005dad  mov     rdx, rsi; unsigned __int16 *
0x140005db0  test    rcx, rcx
0x140005db3  jz      short loc_140005DCB
0x140005db5  mov     [rsp+278h+lpBuffer], rcx
0x140005dba  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005dc1  mov     rcx, rax; this
0x140005dc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005dc9  jmp     short loc_140005DED
0x140005dcb  mov     rcx, rax; this
0x140005dce  test    r9, r9
0x140005dd1  jz      short loc_140005DE1
0x140005dd3  lea     r8, aHs; "[%hs]\n"
0x140005dda  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ddf  jmp     short loc_140005DED
0x140005de1  lea     r8, asc_140015C28; "\n"
0x140005de8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ded  xor     eax, eax
0x140005def  mov     rcx, [rsp+278h+var_38]
0x140005df7  xor     rcx, rsp; StackCookie
0x140005dfa  call    __security_check_cookie
0x140005dff  mov     rbx, [rsp+278h+arg_18]
0x140005e07  add     rsp, 250h
0x140005e0e  pop     r15
0x140005e10  pop     r14
0x140005e12  pop     rdi
0x140005e13  pop     rsi
0x140005e14  pop     rbp
0x140005e15  retn
```
