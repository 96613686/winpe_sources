# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007b74`
- end: `0x180007e2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800054f0`
- `0x180005760`
- `0x180008640`
- `0x18000b2c0`

## callees

- `0x180004180`
- `0x18000500c`
- `0x180007b74`
- `0x180008940`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007ca6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007ca6`

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
          v7 = (const char *)&Src;
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
0x180007b74  mov     [rsp+arg_18], rbx
0x180007b79  push    rbp
0x180007b7a  push    rsi
0x180007b7b  push    rdi
0x180007b7c  push    r14
0x180007b7e  push    r15
0x180007b80  sub     rsp, 250h
0x180007b87  mov     rax, cs:__security_cookie
0x180007b8e  xor     rax, rsp
0x180007b91  mov     [rsp+278h+var_38], rax
0x180007b99  mov     rbx, r8
0x180007b9c  mov     rsi, rdx
0x180007b9f  mov     r14, rcx
0x180007ba2  xor     r15d, r15d
0x180007ba5  test    rdx, rdx
0x180007ba8  jz      loc_180007E01
0x180007bae  test    rcx, rcx
0x180007bb1  jz      loc_180007E01
0x180007bb7  mov     [rcx], r15w
0x180007bbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007bc2  test    rax, rax
0x180007bc5  jz      short loc_180007BE8
0x180007bc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007bce  jz      short loc_180007BE8
0x180007bd0  mov     r8, rdx
0x180007bd3  mov     rdx, rcx
0x180007bd6  mov     rcx, rbx
0x180007bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bde  cmp     [r14], r15w
0x180007be2  jnz     loc_180007E01
0x180007be8  mov     ecx, [rbx]
0x180007bea  mov     bpl, 8
0x180007bed  test    ecx, ecx
0x180007bef  jz      short loc_180007C3A
0x180007bf1  sub     ecx, 1
0x180007bf4  jz      short loc_180007C22
0x180007bf6  sub     ecx, 1
0x180007bf9  jz      short loc_180007C12
0x180007bfb  cmp     ecx, 1
0x180007bfe  jz      short loc_180007C09
0x180007c00  lea     rdi, Src
0x180007c07  jmp     short loc_180007C41
0x180007c09  lea     rdi, aFailfast; "FailFast"
0x180007c10  jmp     short loc_180007C41
0x180007c12  lea     rax, aLoghr; "LogHr"
0x180007c19  lea     rdi, aLognt; "LogNt"
0x180007c20  jmp     short loc_180007C30
0x180007c22  lea     rax, aReturnhr; "ReturnHr"
0x180007c29  lea     rdi, aReturnnt; "ReturnNt"
0x180007c30  test    [rbx+4], bpl
0x180007c34  cmovz   rdi, rax
0x180007c38  jmp     short loc_180007C41
0x180007c3a  lea     rdi, aException; "Exception"
0x180007c41  xor     edx, edx; Val
0x180007c43  mov     r8d, 200h; Size
0x180007c49  lea     rcx, [rsp+278h+Buffer]; void *
0x180007c4e  call    memset_0
0x180007c53  test    [rbx+4], bpl
0x180007c57  jz      short loc_180007C7C
0x180007c59  mov     ebp, [rbx+0Ch]
0x180007c5c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007c63  test    rax, rax
0x180007c66  jz      short loc_180007CAC
0x180007c68  mov     r8d, 100h
0x180007c6e  lea     rdx, [rsp+278h+Buffer]
0x180007c73  mov     ecx, ebp
0x180007c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c7a  jmp     short loc_180007CAC
0x180007c7c  mov     ebp, [rbx+8]
0x180007c7f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007c84  mov     [rsp+278h+nSize], 100h; nSize
0x180007c8c  lea     rax, [rsp+278h+Buffer]
0x180007c91  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007c96  mov     r9d, 400h; dwLanguageId
0x180007c9c  mov     r8d, ebp; dwMessageId
0x180007c9f  xor     edx, edx; lpSource
0x180007ca1  mov     ecx, 1200h; dwFlags
0x180007ca6  call    cs:__imp_FormatMessageW
0x180007cac  lea     rsi, [r14+rsi*2]
0x180007cb0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007cb4  mov     rax, [rbx+88h]
0x180007cbb  mov     rcx, [rbx+80h]
0x180007cc2  mov     rdx, rsi; unsigned __int16 *
0x180007cc5  test    r9, r9
0x180007cc8  jz      short loc_180007CEC
0x180007cca  mov     [rsp+278h+Arguments], rax
0x180007ccf  mov     qword ptr [rsp+278h+nSize], rcx
0x180007cd4  mov     eax, [rbx+40h]
0x180007cd7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007cdb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007ce2  mov     rcx, r14; this
0x180007ce5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007cea  jmp     short loc_180007D03
0x180007cec  mov     [rsp+278h+lpBuffer], rax
0x180007cf1  mov     r9, rcx; unsigned __int16 *
0x180007cf4  lea     r8, aHsP; "%hs!%p: "
0x180007cfb  mov     rcx, r14; this
0x180007cfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d03  mov     r14, rax
0x180007d06  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007d0d  test    r9, r9
0x180007d10  jz      short loc_180007D27
0x180007d12  lea     r8, aCallerP; "(caller: %p) "
0x180007d19  mov     rdx, rsi; unsigned __int16 *
0x180007d1c  mov     rcx, rax; this
0x180007d1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d24  mov     r14, rax
0x180007d27  call    cs:__imp_GetCurrentThreadId
0x180007d2d  lea     rcx, [rsp+278h+Buffer]
0x180007d32  mov     [rsp+278h+var_240], rcx
0x180007d37  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007d3b  mov     [rsp+278h+nSize], eax
0x180007d3f  mov     eax, [rbx+44h]
0x180007d42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007d46  mov     r9, rdi; unsigned __int16 *
0x180007d49  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007d50  mov     rdx, rsi; unsigned __int16 *
0x180007d53  mov     rcx, r14; this
0x180007d56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d5b  cmp     [rbx+18h], r15
0x180007d5f  jnz     short loc_180007D71
0x180007d61  cmp     [rbx+48h], r15
0x180007d65  jnz     short loc_180007D71
0x180007d67  cmp     [rbx+30h], r15
0x180007d6b  jz      loc_180007E01
0x180007d71  lea     r8, asc_180051AD0; "    "
0x180007d78  mov     rdx, rsi; unsigned __int16 *
0x180007d7b  mov     rcx, rax; this
0x180007d7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d83  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007d87  test    r9, r9
0x180007d8a  jz      short loc_180007D9E
0x180007d8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007d93  mov     rdx, rsi; unsigned __int16 *
0x180007d96  mov     rcx, rax; this
0x180007d99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007da2  test    r9, r9
0x180007da5  jz      short loc_180007DB9
0x180007da7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007dae  mov     rdx, rsi; unsigned __int16 *
0x180007db1  mov     rcx, rax; this
0x180007db4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007db9  mov     rcx, [rbx+28h]
0x180007dbd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007dc1  mov     rdx, rsi; unsigned __int16 *
0x180007dc4  test    rcx, rcx
0x180007dc7  jz      short loc_180007DDF
0x180007dc9  mov     [rsp+278h+lpBuffer], rcx
0x180007dce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007dd5  mov     rcx, rax; this
0x180007dd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ddd  jmp     short loc_180007E01
0x180007ddf  mov     rcx, rax; this
0x180007de2  test    r9, r9
0x180007de5  jz      short loc_180007DF5
0x180007de7  lea     r8, aHs; "[%hs]\n"
0x180007dee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007df3  jmp     short loc_180007E01
0x180007df5  lea     r8, asc_180051B48; "\n"
0x180007dfc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e01  xor     eax, eax
0x180007e03  mov     rcx, [rsp+278h+var_38]
0x180007e0b  xor     rcx, rsp; StackCookie
0x180007e0e  call    __security_check_cookie
0x180007e13  mov     rbx, [rsp+278h+arg_18]
0x180007e1b  add     rsp, 250h
0x180007e22  pop     r15
0x180007e24  pop     r14
0x180007e26  pop     rdi
0x180007e27  pop     rsi
0x180007e28  pop     rbp
0x180007e29  retn
```
