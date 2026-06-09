# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004b54`
- end: `0x180004e0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d38`
- `0x180002fa8`
- `0x1800054e0`
- `0x180006f30`

## callees

- `0x180001c00`
- `0x180002648`
- `0x180004b54`
- `0x1800057e0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c86`

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
          v7 = (const char *)&word_180016E72;
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
0x180004b54  mov     [rsp+arg_18], rbx
0x180004b59  push    rbp
0x180004b5a  push    rsi
0x180004b5b  push    rdi
0x180004b5c  push    r14
0x180004b5e  push    r15
0x180004b60  sub     rsp, 250h
0x180004b67  mov     rax, cs:__security_cookie
0x180004b6e  xor     rax, rsp
0x180004b71  mov     [rsp+278h+var_38], rax
0x180004b79  mov     rbx, r8
0x180004b7c  mov     rsi, rdx
0x180004b7f  mov     r14, rcx
0x180004b82  xor     r15d, r15d
0x180004b85  test    rdx, rdx
0x180004b88  jz      loc_180004DE1
0x180004b8e  test    rcx, rcx
0x180004b91  jz      loc_180004DE1
0x180004b97  mov     [rcx], r15w
0x180004b9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ba2  test    rax, rax
0x180004ba5  jz      short loc_180004BC8
0x180004ba7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004bae  jz      short loc_180004BC8
0x180004bb0  mov     r8, rdx
0x180004bb3  mov     rdx, rcx
0x180004bb6  mov     rcx, rbx
0x180004bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bbe  cmp     [r14], r15w
0x180004bc2  jnz     loc_180004DE1
0x180004bc8  mov     ecx, [rbx]
0x180004bca  mov     bpl, 8
0x180004bcd  test    ecx, ecx
0x180004bcf  jz      short loc_180004C1A
0x180004bd1  sub     ecx, 1
0x180004bd4  jz      short loc_180004C02
0x180004bd6  sub     ecx, 1
0x180004bd9  jz      short loc_180004BF2
0x180004bdb  cmp     ecx, 1
0x180004bde  jz      short loc_180004BE9
0x180004be0  lea     rdi, word_180016E72
0x180004be7  jmp     short loc_180004C21
0x180004be9  lea     rdi, aFailfast; "FailFast"
0x180004bf0  jmp     short loc_180004C21
0x180004bf2  lea     rax, aLoghr; "LogHr"
0x180004bf9  lea     rdi, aLognt; "LogNt"
0x180004c00  jmp     short loc_180004C10
0x180004c02  lea     rax, aReturnhr; "ReturnHr"
0x180004c09  lea     rdi, aReturnnt; "ReturnNt"
0x180004c10  test    [rbx+4], bpl
0x180004c14  cmovz   rdi, rax
0x180004c18  jmp     short loc_180004C21
0x180004c1a  lea     rdi, aException; "Exception"
0x180004c21  xor     edx, edx; Val
0x180004c23  mov     r8d, 200h; Size
0x180004c29  lea     rcx, [rsp+278h+Buffer]; void *
0x180004c2e  call    memset_0
0x180004c33  test    [rbx+4], bpl
0x180004c37  jz      short loc_180004C5C
0x180004c39  mov     ebp, [rbx+0Ch]
0x180004c3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004c43  test    rax, rax
0x180004c46  jz      short loc_180004C8C
0x180004c48  mov     r8d, 100h
0x180004c4e  lea     rdx, [rsp+278h+Buffer]
0x180004c53  mov     ecx, ebp
0x180004c55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c5a  jmp     short loc_180004C8C
0x180004c5c  mov     ebp, [rbx+8]
0x180004c5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004c64  mov     [rsp+278h+nSize], 100h; nSize
0x180004c6c  lea     rax, [rsp+278h+Buffer]
0x180004c71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004c76  mov     r9d, 400h; dwLanguageId
0x180004c7c  mov     r8d, ebp; dwMessageId
0x180004c7f  xor     edx, edx; lpSource
0x180004c81  mov     ecx, 1200h; dwFlags
0x180004c86  call    cs:__imp_FormatMessageW
0x180004c8c  lea     rsi, [r14+rsi*2]
0x180004c90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004c94  mov     rax, [rbx+88h]
0x180004c9b  mov     rcx, [rbx+80h]
0x180004ca2  mov     rdx, rsi; unsigned __int16 *
0x180004ca5  test    r9, r9
0x180004ca8  jz      short loc_180004CCC
0x180004caa  mov     [rsp+278h+Arguments], rax
0x180004caf  mov     qword ptr [rsp+278h+nSize], rcx
0x180004cb4  mov     eax, [rbx+40h]
0x180004cb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004cbb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004cc2  mov     rcx, r14; this
0x180004cc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004cca  jmp     short loc_180004CE3
0x180004ccc  mov     [rsp+278h+lpBuffer], rax
0x180004cd1  mov     r9, rcx; unsigned __int16 *
0x180004cd4  lea     r8, aHsP; "%hs!%p: "
0x180004cdb  mov     rcx, r14; this
0x180004cde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ce3  mov     r14, rax
0x180004ce6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004ced  test    r9, r9
0x180004cf0  jz      short loc_180004D07
0x180004cf2  lea     r8, aCallerP; "(caller: %p) "
0x180004cf9  mov     rdx, rsi; unsigned __int16 *
0x180004cfc  mov     rcx, rax; this
0x180004cff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d04  mov     r14, rax
0x180004d07  call    cs:__imp_GetCurrentThreadId
0x180004d0d  lea     rcx, [rsp+278h+Buffer]
0x180004d12  mov     [rsp+278h+var_240], rcx
0x180004d17  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004d1b  mov     [rsp+278h+nSize], eax
0x180004d1f  mov     eax, [rbx+44h]
0x180004d22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004d26  mov     r9, rdi; unsigned __int16 *
0x180004d29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004d30  mov     rdx, rsi; unsigned __int16 *
0x180004d33  mov     rcx, r14; this
0x180004d36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d3b  cmp     [rbx+18h], r15
0x180004d3f  jnz     short loc_180004D51
0x180004d41  cmp     [rbx+48h], r15
0x180004d45  jnz     short loc_180004D51
0x180004d47  cmp     [rbx+30h], r15
0x180004d4b  jz      loc_180004DE1
0x180004d51  lea     r8, asc_180016F78; "    "
0x180004d58  mov     rdx, rsi; unsigned __int16 *
0x180004d5b  mov     rcx, rax; this
0x180004d5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d63  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004d67  test    r9, r9
0x180004d6a  jz      short loc_180004D7E
0x180004d6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004d73  mov     rdx, rsi; unsigned __int16 *
0x180004d76  mov     rcx, rax; this
0x180004d79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004d82  test    r9, r9
0x180004d85  jz      short loc_180004D99
0x180004d87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004d8e  mov     rdx, rsi; unsigned __int16 *
0x180004d91  mov     rcx, rax; this
0x180004d94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d99  mov     rcx, [rbx+28h]
0x180004d9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004da1  mov     rdx, rsi; unsigned __int16 *
0x180004da4  test    rcx, rcx
0x180004da7  jz      short loc_180004DBF
0x180004da9  mov     [rsp+278h+lpBuffer], rcx
0x180004dae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004db5  mov     rcx, rax; this
0x180004db8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dbd  jmp     short loc_180004DE1
0x180004dbf  mov     rcx, rax; this
0x180004dc2  test    r9, r9
0x180004dc5  jz      short loc_180004DD5
0x180004dc7  lea     r8, aHs; "[%hs]\n"
0x180004dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dd3  jmp     short loc_180004DE1
0x180004dd5  lea     r8, asc_180016FF0; "\n"
0x180004ddc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004de1  xor     eax, eax
0x180004de3  mov     rcx, [rsp+278h+var_38]
0x180004deb  xor     rcx, rsp; StackCookie
0x180004dee  call    __security_check_cookie
0x180004df3  mov     rbx, [rsp+278h+arg_18]
0x180004dfb  add     rsp, 250h
0x180004e02  pop     r15
0x180004e04  pop     r14
0x180004e06  pop     rdi
0x180004e07  pop     rsi
0x180004e08  pop     rbp
0x180004e09  retn
```
