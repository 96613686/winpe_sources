# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003b54`
- end: `0x140003e0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x140002798`
- `0x140002a18`
- `0x1400044b4`
- `0x140005cb0`
- `0x140011698`
- `0x1400117cc`

## callees

- `0x1400016a0`
- `0x140002456`
- `0x140003b54`
- `0x1400047b4`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003d07`
- `KERNEL32!GetCurrentThreadId` at `0x140003d07`
- `KERNEL32!FormatMessageW` at `0x140003c86`
- `KERNEL32!FormatMessageW` at `0x140003c86`

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
          v7 = (const char *)&qword_140014C28;
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
0x140003b54  mov     [rsp+arg_18], rbx
0x140003b59  push    rbp
0x140003b5a  push    rsi
0x140003b5b  push    rdi
0x140003b5c  push    r14
0x140003b5e  push    r15
0x140003b60  sub     rsp, 250h
0x140003b67  mov     rax, cs:__security_cookie
0x140003b6e  xor     rax, rsp
0x140003b71  mov     [rsp+278h+var_38], rax
0x140003b79  mov     rbx, r8
0x140003b7c  mov     rsi, rdx
0x140003b7f  mov     r14, rcx
0x140003b82  xor     r15d, r15d
0x140003b85  test    rdx, rdx
0x140003b88  jz      loc_140003DE1
0x140003b8e  test    rcx, rcx
0x140003b91  jz      loc_140003DE1
0x140003b97  mov     [rcx], r15w
0x140003b9b  mov     rax, cs:g_pfnResultLoggingCallback
0x140003ba2  test    rax, rax
0x140003ba5  jz      short loc_140003BC8
0x140003ba7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003bae  jz      short loc_140003BC8
0x140003bb0  mov     r8, rdx
0x140003bb3  mov     rdx, rcx
0x140003bb6  mov     rcx, rbx
0x140003bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bbe  cmp     [r14], r15w
0x140003bc2  jnz     loc_140003DE1
0x140003bc8  mov     ecx, [rbx]
0x140003bca  mov     bpl, 8
0x140003bcd  test    ecx, ecx
0x140003bcf  jz      short loc_140003C1A
0x140003bd1  sub     ecx, 1
0x140003bd4  jz      short loc_140003C02
0x140003bd6  sub     ecx, 1
0x140003bd9  jz      short loc_140003BF2
0x140003bdb  cmp     ecx, 1
0x140003bde  jz      short loc_140003BE9
0x140003be0  lea     rdi, qword_140014C28
0x140003be7  jmp     short loc_140003C21
0x140003be9  lea     rdi, aFailfast; "FailFast"
0x140003bf0  jmp     short loc_140003C21
0x140003bf2  lea     rax, aLoghr; "LogHr"
0x140003bf9  lea     rdi, aLognt; "LogNt"
0x140003c00  jmp     short loc_140003C10
0x140003c02  lea     rax, aReturnhr; "ReturnHr"
0x140003c09  lea     rdi, aReturnnt; "ReturnNt"
0x140003c10  test    [rbx+4], bpl
0x140003c14  cmovz   rdi, rax
0x140003c18  jmp     short loc_140003C21
0x140003c1a  lea     rdi, aException; "Exception"
0x140003c21  xor     edx, edx; Val
0x140003c23  mov     r8d, 200h; Size
0x140003c29  lea     rcx, [rsp+278h+Buffer]; void *
0x140003c2e  call    memset_0
0x140003c33  test    [rbx+4], bpl
0x140003c37  jz      short loc_140003C5C
0x140003c39  mov     ebp, [rbx+0Ch]
0x140003c3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003c43  test    rax, rax
0x140003c46  jz      short loc_140003C8C
0x140003c48  mov     r8d, 100h
0x140003c4e  lea     rdx, [rsp+278h+Buffer]
0x140003c53  mov     ecx, ebp
0x140003c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c5a  jmp     short loc_140003C8C
0x140003c5c  mov     ebp, [rbx+8]
0x140003c5f  mov     [rsp+278h+Arguments], r15; Arguments
0x140003c64  mov     [rsp+278h+nSize], 100h; nSize
0x140003c6c  lea     rax, [rsp+278h+Buffer]
0x140003c71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003c76  mov     r9d, 400h; dwLanguageId
0x140003c7c  mov     r8d, ebp; dwMessageId
0x140003c7f  xor     edx, edx; lpSource
0x140003c81  mov     ecx, 1200h; dwFlags
0x140003c86  call    cs:__imp_FormatMessageW
0x140003c8c  lea     rsi, [r14+rsi*2]
0x140003c90  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003c94  mov     rax, [rbx+88h]
0x140003c9b  mov     rcx, [rbx+80h]
0x140003ca2  mov     rdx, rsi; unsigned __int16 *
0x140003ca5  test    r9, r9
0x140003ca8  jz      short loc_140003CCC
0x140003caa  mov     [rsp+278h+Arguments], rax
0x140003caf  mov     qword ptr [rsp+278h+nSize], rcx
0x140003cb4  mov     eax, [rbx+40h]
0x140003cb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003cbb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003cc2  mov     rcx, r14; this
0x140003cc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003cca  jmp     short loc_140003CE3
0x140003ccc  mov     [rsp+278h+lpBuffer], rax
0x140003cd1  mov     r9, rcx; unsigned __int16 *
0x140003cd4  lea     r8, aHsP; "%hs!%p: "
0x140003cdb  mov     rcx, r14; this
0x140003cde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003ce3  mov     r14, rax
0x140003ce6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140003ced  test    r9, r9
0x140003cf0  jz      short loc_140003D07
0x140003cf2  lea     r8, aCallerP; "(caller: %p) "
0x140003cf9  mov     rdx, rsi; unsigned __int16 *
0x140003cfc  mov     rcx, rax; this
0x140003cff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d04  mov     r14, rax
0x140003d07  call    cs:__imp_GetCurrentThreadId
0x140003d0d  lea     rcx, [rsp+278h+Buffer]
0x140003d12  mov     [rsp+278h+var_240], rcx
0x140003d17  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003d1b  mov     [rsp+278h+nSize], eax
0x140003d1f  mov     eax, [rbx+44h]
0x140003d22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003d26  mov     r9, rdi; unsigned __int16 *
0x140003d29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003d30  mov     rdx, rsi; unsigned __int16 *
0x140003d33  mov     rcx, r14; this
0x140003d36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d3b  cmp     [rbx+18h], r15
0x140003d3f  jnz     short loc_140003D51
0x140003d41  cmp     [rbx+48h], r15
0x140003d45  jnz     short loc_140003D51
0x140003d47  cmp     [rbx+30h], r15
0x140003d4b  jz      loc_140003DE1
0x140003d51  lea     r8, asc_140014D30; "    "
0x140003d58  mov     rdx, rsi; unsigned __int16 *
0x140003d5b  mov     rcx, rax; this
0x140003d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d63  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003d67  test    r9, r9
0x140003d6a  jz      short loc_140003D7E
0x140003d6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003d73  mov     rdx, rsi; unsigned __int16 *
0x140003d76  mov     rcx, rax; this
0x140003d79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003d82  test    r9, r9
0x140003d85  jz      short loc_140003D99
0x140003d87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140003d8e  mov     rdx, rsi; unsigned __int16 *
0x140003d91  mov     rcx, rax; this
0x140003d94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d99  mov     rcx, [rbx+28h]
0x140003d9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003da1  mov     rdx, rsi; unsigned __int16 *
0x140003da4  test    rcx, rcx
0x140003da7  jz      short loc_140003DBF
0x140003da9  mov     [rsp+278h+lpBuffer], rcx
0x140003dae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003db5  mov     rcx, rax; this
0x140003db8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003dbd  jmp     short loc_140003DE1
0x140003dbf  mov     rcx, rax; this
0x140003dc2  test    r9, r9
0x140003dc5  jz      short loc_140003DD5
0x140003dc7  lea     r8, aHs; "[%hs]\n"
0x140003dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003dd3  jmp     short loc_140003DE1
0x140003dd5  lea     r8, asc_140014DA8; "\n"
0x140003ddc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003de1  xor     eax, eax
0x140003de3  mov     rcx, [rsp+278h+var_38]
0x140003deb  xor     rcx, rsp; StackCookie
0x140003dee  call    __security_check_cookie
0x140003df3  mov     rbx, [rsp+278h+arg_18]
0x140003dfb  add     rsp, 250h
0x140003e02  pop     r15
0x140003e04  pop     r14
0x140003e06  pop     rdi
0x140003e07  pop     rsi
0x140003e08  pop     rbp
0x140003e09  retn
```
