# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005a74`
- end: `0x140005d2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140004be4`
- `0x140006460`
- `0x140007990`

## callees

- `0x1400033b0`
- `0x140003f8c`
- `0x140005a74`
- `0x140006760`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005c27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005ba6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005ba6`

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
          v7 = (const char *)&dword_140010DA4;
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
0x140005a74  mov     [rsp+arg_18], rbx
0x140005a79  push    rbp
0x140005a7a  push    rsi
0x140005a7b  push    rdi
0x140005a7c  push    r14
0x140005a7e  push    r15
0x140005a80  sub     rsp, 250h
0x140005a87  mov     rax, cs:__security_cookie
0x140005a8e  xor     rax, rsp
0x140005a91  mov     [rsp+278h+var_38], rax
0x140005a99  mov     rbx, r8
0x140005a9c  mov     rsi, rdx
0x140005a9f  mov     r14, rcx
0x140005aa2  xor     r15d, r15d
0x140005aa5  test    rdx, rdx
0x140005aa8  jz      loc_140005D01
0x140005aae  test    rcx, rcx
0x140005ab1  jz      loc_140005D01
0x140005ab7  mov     [rcx], r15w
0x140005abb  mov     rax, cs:g_pfnResultLoggingCallback
0x140005ac2  test    rax, rax
0x140005ac5  jz      short loc_140005AE8
0x140005ac7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005ace  jz      short loc_140005AE8
0x140005ad0  mov     r8, rdx
0x140005ad3  mov     rdx, rcx
0x140005ad6  mov     rcx, rbx
0x140005ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ade  cmp     [r14], r15w
0x140005ae2  jnz     loc_140005D01
0x140005ae8  mov     ecx, [rbx]
0x140005aea  mov     bpl, 8
0x140005aed  test    ecx, ecx
0x140005aef  jz      short loc_140005B3A
0x140005af1  sub     ecx, 1
0x140005af4  jz      short loc_140005B22
0x140005af6  sub     ecx, 1
0x140005af9  jz      short loc_140005B12
0x140005afb  cmp     ecx, 1
0x140005afe  jz      short loc_140005B09
0x140005b00  lea     rdi, dword_140010DA4
0x140005b07  jmp     short loc_140005B41
0x140005b09  lea     rdi, aFailfast; "FailFast"
0x140005b10  jmp     short loc_140005B41
0x140005b12  lea     rax, aLoghr; "LogHr"
0x140005b19  lea     rdi, aLognt; "LogNt"
0x140005b20  jmp     short loc_140005B30
0x140005b22  lea     rax, aReturnhr; "ReturnHr"
0x140005b29  lea     rdi, aReturnnt; "ReturnNt"
0x140005b30  test    [rbx+4], bpl
0x140005b34  cmovz   rdi, rax
0x140005b38  jmp     short loc_140005B41
0x140005b3a  lea     rdi, aException; "Exception"
0x140005b41  xor     edx, edx; Val
0x140005b43  mov     r8d, 200h; Size
0x140005b49  lea     rcx, [rsp+278h+Buffer]; void *
0x140005b4e  call    memset_0
0x140005b53  test    [rbx+4], bpl
0x140005b57  jz      short loc_140005B7C
0x140005b59  mov     ebp, [rbx+0Ch]
0x140005b5c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005b63  test    rax, rax
0x140005b66  jz      short loc_140005BAC
0x140005b68  mov     r8d, 100h
0x140005b6e  lea     rdx, [rsp+278h+Buffer]
0x140005b73  mov     ecx, ebp
0x140005b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b7a  jmp     short loc_140005BAC
0x140005b7c  mov     ebp, [rbx+8]
0x140005b7f  mov     [rsp+278h+Arguments], r15; Arguments
0x140005b84  mov     [rsp+278h+nSize], 100h; nSize
0x140005b8c  lea     rax, [rsp+278h+Buffer]
0x140005b91  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005b96  mov     r9d, 400h; dwLanguageId
0x140005b9c  mov     r8d, ebp; dwMessageId
0x140005b9f  xor     edx, edx; lpSource
0x140005ba1  mov     ecx, 1200h; dwFlags
0x140005ba6  call    cs:__imp_FormatMessageW
0x140005bac  lea     rsi, [r14+rsi*2]
0x140005bb0  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005bb4  mov     rax, [rbx+88h]
0x140005bbb  mov     rcx, [rbx+80h]
0x140005bc2  mov     rdx, rsi; unsigned __int16 *
0x140005bc5  test    r9, r9
0x140005bc8  jz      short loc_140005BEC
0x140005bca  mov     [rsp+278h+Arguments], rax
0x140005bcf  mov     qword ptr [rsp+278h+nSize], rcx
0x140005bd4  mov     eax, [rbx+40h]
0x140005bd7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005bdb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005be2  mov     rcx, r14; this
0x140005be5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005bea  jmp     short loc_140005C03
0x140005bec  mov     [rsp+278h+lpBuffer], rax
0x140005bf1  mov     r9, rcx; unsigned __int16 *
0x140005bf4  lea     r8, aHsP; "%hs!%p: "
0x140005bfb  mov     rcx, r14; this
0x140005bfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005c03  mov     r14, rax
0x140005c06  mov     r9, [rbx+90h]; unsigned __int16 *
0x140005c0d  test    r9, r9
0x140005c10  jz      short loc_140005C27
0x140005c12  lea     r8, aCallerP; "(caller: %p) "
0x140005c19  mov     rdx, rsi; unsigned __int16 *
0x140005c1c  mov     rcx, rax; this
0x140005c1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005c24  mov     r14, rax
0x140005c27  call    cs:__imp_GetCurrentThreadId
0x140005c2d  lea     rcx, [rsp+278h+Buffer]
0x140005c32  mov     [rsp+278h+var_240], rcx
0x140005c37  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005c3b  mov     [rsp+278h+nSize], eax
0x140005c3f  mov     eax, [rbx+44h]
0x140005c42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005c46  mov     r9, rdi; unsigned __int16 *
0x140005c49  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005c50  mov     rdx, rsi; unsigned __int16 *
0x140005c53  mov     rcx, r14; this
0x140005c56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005c5b  cmp     [rbx+18h], r15
0x140005c5f  jnz     short loc_140005C71
0x140005c61  cmp     [rbx+48h], r15
0x140005c65  jnz     short loc_140005C71
0x140005c67  cmp     [rbx+30h], r15
0x140005c6b  jz      loc_140005D01
0x140005c71  lea     r8, asc_140010EB0; "    "
0x140005c78  mov     rdx, rsi; unsigned __int16 *
0x140005c7b  mov     rcx, rax; this
0x140005c7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005c83  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005c87  test    r9, r9
0x140005c8a  jz      short loc_140005C9E
0x140005c8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005c93  mov     rdx, rsi; unsigned __int16 *
0x140005c96  mov     rcx, rax; this
0x140005c99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005c9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005ca2  test    r9, r9
0x140005ca5  jz      short loc_140005CB9
0x140005ca7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140005cae  mov     rdx, rsi; unsigned __int16 *
0x140005cb1  mov     rcx, rax; this
0x140005cb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005cb9  mov     rcx, [rbx+28h]
0x140005cbd  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005cc1  mov     rdx, rsi; unsigned __int16 *
0x140005cc4  test    rcx, rcx
0x140005cc7  jz      short loc_140005CDF
0x140005cc9  mov     [rsp+278h+lpBuffer], rcx
0x140005cce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005cd5  mov     rcx, rax; this
0x140005cd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005cdd  jmp     short loc_140005D01
0x140005cdf  mov     rcx, rax; this
0x140005ce2  test    r9, r9
0x140005ce5  jz      short loc_140005CF5
0x140005ce7  lea     r8, aHs; "[%hs]\n"
0x140005cee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005cf3  jmp     short loc_140005D01
0x140005cf5  lea     r8, asc_140010F28; "\n"
0x140005cfc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005d01  xor     eax, eax
0x140005d03  mov     rcx, [rsp+278h+var_38]
0x140005d0b  xor     rcx, rsp; StackCookie
0x140005d0e  call    __security_check_cookie
0x140005d13  mov     rbx, [rsp+278h+arg_18]
0x140005d1b  add     rsp, 250h
0x140005d22  pop     r15
0x140005d24  pop     r14
0x140005d26  pop     rdi
0x140005d27  pop     rsi
0x140005d28  pop     rbp
0x140005d29  retn
```
