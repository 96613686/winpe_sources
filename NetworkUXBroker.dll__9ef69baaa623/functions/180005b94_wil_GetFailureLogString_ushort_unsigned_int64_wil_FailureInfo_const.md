# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005b94`
- end: `0x180005e4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180006190`
- `0x180006af0`
- `0x180007db4`
- `0x18000b068`
- `0x18000e19c`

## callees

- `0x180002520`
- `0x1800030a0`
- `0x180005b94`
- `0x180006140`
- `0x180047010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005cc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005cc6`

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
          v7 = (const char *)&qword_180067038;
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
0x180005b94  mov     [rsp+arg_18], rbx
0x180005b99  push    rbp
0x180005b9a  push    rsi
0x180005b9b  push    rdi
0x180005b9c  push    r14
0x180005b9e  push    r15
0x180005ba0  sub     rsp, 250h
0x180005ba7  mov     rax, cs:__security_cookie
0x180005bae  xor     rax, rsp
0x180005bb1  mov     [rsp+278h+var_38], rax
0x180005bb9  mov     rbx, r8
0x180005bbc  mov     rsi, rdx
0x180005bbf  mov     r14, rcx
0x180005bc2  xor     r15d, r15d
0x180005bc5  test    rdx, rdx
0x180005bc8  jz      loc_180005E21
0x180005bce  test    rcx, rcx
0x180005bd1  jz      loc_180005E21
0x180005bd7  mov     [rcx], r15w
0x180005bdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005be2  test    rax, rax
0x180005be5  jz      short loc_180005C08
0x180005be7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005bee  jz      short loc_180005C08
0x180005bf0  mov     r8, rdx
0x180005bf3  mov     rdx, rcx
0x180005bf6  mov     rcx, rbx
0x180005bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bfe  cmp     [r14], r15w
0x180005c02  jnz     loc_180005E21
0x180005c08  mov     ecx, [rbx]
0x180005c0a  mov     bpl, 8
0x180005c0d  test    ecx, ecx
0x180005c0f  jz      short loc_180005C5A
0x180005c11  sub     ecx, 1
0x180005c14  jz      short loc_180005C42
0x180005c16  sub     ecx, 1
0x180005c19  jz      short loc_180005C32
0x180005c1b  cmp     ecx, 1
0x180005c1e  jz      short loc_180005C29
0x180005c20  lea     rdi, qword_180067038
0x180005c27  jmp     short loc_180005C61
0x180005c29  lea     rdi, aFailfast; "FailFast"
0x180005c30  jmp     short loc_180005C61
0x180005c32  lea     rax, aLoghr; "LogHr"
0x180005c39  lea     rdi, aLognt; "LogNt"
0x180005c40  jmp     short loc_180005C50
0x180005c42  lea     rax, aReturnhr; "ReturnHr"
0x180005c49  lea     rdi, aReturnnt; "ReturnNt"
0x180005c50  test    [rbx+4], bpl
0x180005c54  cmovz   rdi, rax
0x180005c58  jmp     short loc_180005C61
0x180005c5a  lea     rdi, aException; "Exception"
0x180005c61  xor     edx, edx; Val
0x180005c63  mov     r8d, 200h; Size
0x180005c69  lea     rcx, [rsp+278h+Buffer]; void *
0x180005c6e  call    memset_0
0x180005c73  test    [rbx+4], bpl
0x180005c77  jz      short loc_180005C9C
0x180005c79  mov     ebp, [rbx+0Ch]
0x180005c7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005c83  test    rax, rax
0x180005c86  jz      short loc_180005CCC
0x180005c88  mov     r8d, 100h
0x180005c8e  lea     rdx, [rsp+278h+Buffer]
0x180005c93  mov     ecx, ebp
0x180005c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c9a  jmp     short loc_180005CCC
0x180005c9c  mov     ebp, [rbx+8]
0x180005c9f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005ca4  mov     [rsp+278h+nSize], 100h; nSize
0x180005cac  lea     rax, [rsp+278h+Buffer]
0x180005cb1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005cb6  mov     r9d, 400h; dwLanguageId
0x180005cbc  mov     r8d, ebp; dwMessageId
0x180005cbf  xor     edx, edx; lpSource
0x180005cc1  mov     ecx, 1200h; dwFlags
0x180005cc6  call    cs:__imp_FormatMessageW
0x180005ccc  lea     rsi, [r14+rsi*2]
0x180005cd0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005cd4  mov     rax, [rbx+88h]
0x180005cdb  mov     rcx, [rbx+80h]
0x180005ce2  mov     rdx, rsi; unsigned __int16 *
0x180005ce5  test    r9, r9
0x180005ce8  jz      short loc_180005D0C
0x180005cea  mov     [rsp+278h+Arguments], rax
0x180005cef  mov     qword ptr [rsp+278h+nSize], rcx
0x180005cf4  mov     eax, [rbx+40h]
0x180005cf7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005cfb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005d02  mov     rcx, r14; this
0x180005d05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005d0a  jmp     short loc_180005D23
0x180005d0c  mov     [rsp+278h+lpBuffer], rax
0x180005d11  mov     r9, rcx; unsigned __int16 *
0x180005d14  lea     r8, aHsP; "%hs!%p: "
0x180005d1b  mov     rcx, r14; this
0x180005d1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005d23  mov     r14, rax
0x180005d26  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005d2d  test    r9, r9
0x180005d30  jz      short loc_180005D47
0x180005d32  lea     r8, aCallerP; "(caller: %p) "
0x180005d39  mov     rdx, rsi; unsigned __int16 *
0x180005d3c  mov     rcx, rax; this
0x180005d3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005d44  mov     r14, rax
0x180005d47  call    cs:__imp_GetCurrentThreadId
0x180005d4d  lea     rcx, [rsp+278h+Buffer]
0x180005d52  mov     [rsp+278h+var_240], rcx
0x180005d57  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005d5b  mov     [rsp+278h+nSize], eax
0x180005d5f  mov     eax, [rbx+44h]
0x180005d62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005d66  mov     r9, rdi; unsigned __int16 *
0x180005d69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005d70  mov     rdx, rsi; unsigned __int16 *
0x180005d73  mov     rcx, r14; this
0x180005d76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005d7b  cmp     [rbx+18h], r15
0x180005d7f  jnz     short loc_180005D91
0x180005d81  cmp     [rbx+48h], r15
0x180005d85  jnz     short loc_180005D91
0x180005d87  cmp     [rbx+30h], r15
0x180005d8b  jz      loc_180005E21
0x180005d91  lea     r8, asc_180067140; "    "
0x180005d98  mov     rdx, rsi; unsigned __int16 *
0x180005d9b  mov     rcx, rax; this
0x180005d9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005da3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005da7  test    r9, r9
0x180005daa  jz      short loc_180005DBE
0x180005dac  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005db3  mov     rdx, rsi; unsigned __int16 *
0x180005db6  mov     rcx, rax; this
0x180005db9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005dbe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005dc2  test    r9, r9
0x180005dc5  jz      short loc_180005DD9
0x180005dc7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005dce  mov     rdx, rsi; unsigned __int16 *
0x180005dd1  mov     rcx, rax; this
0x180005dd4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005dd9  mov     rcx, [rbx+28h]
0x180005ddd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005de1  mov     rdx, rsi; unsigned __int16 *
0x180005de4  test    rcx, rcx
0x180005de7  jz      short loc_180005DFF
0x180005de9  mov     [rsp+278h+lpBuffer], rcx
0x180005dee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005df5  mov     rcx, rax; this
0x180005df8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005dfd  jmp     short loc_180005E21
0x180005dff  mov     rcx, rax; this
0x180005e02  test    r9, r9
0x180005e05  jz      short loc_180005E15
0x180005e07  lea     r8, aHs; "[%hs]\n"
0x180005e0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e13  jmp     short loc_180005E21
0x180005e15  lea     r8, asc_1800671B8; "\n"
0x180005e1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e21  xor     eax, eax
0x180005e23  mov     rcx, [rsp+278h+var_38]
0x180005e2b  xor     rcx, rsp; StackCookie
0x180005e2e  call    __security_check_cookie
0x180005e33  mov     rbx, [rsp+278h+arg_18]
0x180005e3b  add     rsp, 250h
0x180005e42  pop     r15
0x180005e44  pop     r14
0x180005e46  pop     rdi
0x180005e47  pop     rsi
0x180005e48  pop     rbp
0x180005e49  retn
```
