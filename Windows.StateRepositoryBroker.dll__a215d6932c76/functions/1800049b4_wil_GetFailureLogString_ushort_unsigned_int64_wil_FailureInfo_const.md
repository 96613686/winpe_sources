# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800049b4`
- end: `0x180004c6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003640`
- `0x1800053f8`
- `0x1800069a0`

## callees

- `0x180001d60`
- `0x180002900`
- `0x1800049b4`
- `0x1800056f8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ae6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ae6`

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
          v7 = (const char *)&byte_18000E6E1;
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
0x1800049b4  mov     [rsp+arg_18], rbx
0x1800049b9  push    rbp
0x1800049ba  push    rsi
0x1800049bb  push    rdi
0x1800049bc  push    r14
0x1800049be  push    r15
0x1800049c0  sub     rsp, 250h
0x1800049c7  mov     rax, cs:__security_cookie
0x1800049ce  xor     rax, rsp
0x1800049d1  mov     [rsp+278h+var_38], rax
0x1800049d9  mov     rbx, r8
0x1800049dc  mov     rsi, rdx
0x1800049df  mov     r14, rcx
0x1800049e2  xor     r15d, r15d
0x1800049e5  test    rdx, rdx
0x1800049e8  jz      loc_180004C41
0x1800049ee  test    rcx, rcx
0x1800049f1  jz      loc_180004C41
0x1800049f7  mov     [rcx], r15w
0x1800049fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a02  test    rax, rax
0x180004a05  jz      short loc_180004A28
0x180004a07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004a0e  jz      short loc_180004A28
0x180004a10  mov     r8, rdx
0x180004a13  mov     rdx, rcx
0x180004a16  mov     rcx, rbx
0x180004a19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a1e  cmp     [r14], r15w
0x180004a22  jnz     loc_180004C41
0x180004a28  mov     ecx, [rbx]
0x180004a2a  mov     bpl, 8
0x180004a2d  test    ecx, ecx
0x180004a2f  jz      short loc_180004A7A
0x180004a31  sub     ecx, 1
0x180004a34  jz      short loc_180004A62
0x180004a36  sub     ecx, 1
0x180004a39  jz      short loc_180004A52
0x180004a3b  cmp     ecx, 1
0x180004a3e  jz      short loc_180004A49
0x180004a40  lea     rdi, byte_18000E6E1
0x180004a47  jmp     short loc_180004A81
0x180004a49  lea     rdi, aFailfast; "FailFast"
0x180004a50  jmp     short loc_180004A81
0x180004a52  lea     rax, aLoghr; "LogHr"
0x180004a59  lea     rdi, aLognt; "LogNt"
0x180004a60  jmp     short loc_180004A70
0x180004a62  lea     rax, aReturnhr; "ReturnHr"
0x180004a69  lea     rdi, aReturnnt; "ReturnNt"
0x180004a70  test    [rbx+4], bpl
0x180004a74  cmovz   rdi, rax
0x180004a78  jmp     short loc_180004A81
0x180004a7a  lea     rdi, aException; "Exception"
0x180004a81  xor     edx, edx; Val
0x180004a83  mov     r8d, 200h; Size
0x180004a89  lea     rcx, [rsp+278h+Buffer]; void *
0x180004a8e  call    memset_0
0x180004a93  test    [rbx+4], bpl
0x180004a97  jz      short loc_180004ABC
0x180004a99  mov     ebp, [rbx+0Ch]
0x180004a9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004aa3  test    rax, rax
0x180004aa6  jz      short loc_180004AEC
0x180004aa8  mov     r8d, 100h
0x180004aae  lea     rdx, [rsp+278h+Buffer]
0x180004ab3  mov     ecx, ebp
0x180004ab5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aba  jmp     short loc_180004AEC
0x180004abc  mov     ebp, [rbx+8]
0x180004abf  mov     [rsp+278h+Arguments], r15; Arguments
0x180004ac4  mov     [rsp+278h+nSize], 100h; nSize
0x180004acc  lea     rax, [rsp+278h+Buffer]
0x180004ad1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004ad6  mov     r9d, 400h; dwLanguageId
0x180004adc  mov     r8d, ebp; dwMessageId
0x180004adf  xor     edx, edx; lpSource
0x180004ae1  mov     ecx, 1200h; dwFlags
0x180004ae6  call    cs:__imp_FormatMessageW
0x180004aec  lea     rsi, [r14+rsi*2]
0x180004af0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004af4  mov     rax, [rbx+88h]
0x180004afb  mov     rcx, [rbx+80h]
0x180004b02  mov     rdx, rsi; unsigned __int16 *
0x180004b05  test    r9, r9
0x180004b08  jz      short loc_180004B2C
0x180004b0a  mov     [rsp+278h+Arguments], rax
0x180004b0f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004b14  mov     eax, [rbx+40h]
0x180004b17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004b22  mov     rcx, r14; this
0x180004b25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b2a  jmp     short loc_180004B43
0x180004b2c  mov     [rsp+278h+lpBuffer], rax
0x180004b31  mov     r9, rcx; unsigned __int16 *
0x180004b34  lea     r8, aHsP; "%hs!%p: "
0x180004b3b  mov     rcx, r14; this
0x180004b3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b43  mov     r14, rax
0x180004b46  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004b4d  test    r9, r9
0x180004b50  jz      short loc_180004B67
0x180004b52  lea     r8, aCallerP; "(caller: %p) "
0x180004b59  mov     rdx, rsi; unsigned __int16 *
0x180004b5c  mov     rcx, rax; this
0x180004b5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b64  mov     r14, rax
0x180004b67  call    cs:__imp_GetCurrentThreadId
0x180004b6d  lea     rcx, [rsp+278h+Buffer]
0x180004b72  mov     [rsp+278h+var_240], rcx
0x180004b77  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004b7b  mov     [rsp+278h+nSize], eax
0x180004b7f  mov     eax, [rbx+44h]
0x180004b82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b86  mov     r9, rdi; unsigned __int16 *
0x180004b89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004b90  mov     rdx, rsi; unsigned __int16 *
0x180004b93  mov     rcx, r14; this
0x180004b96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b9b  cmp     [rbx+18h], r15
0x180004b9f  jnz     short loc_180004BB1
0x180004ba1  cmp     [rbx+48h], r15
0x180004ba5  jnz     short loc_180004BB1
0x180004ba7  cmp     [rbx+30h], r15
0x180004bab  jz      loc_180004C41
0x180004bb1  lea     r8, asc_18000E7E8; "    "
0x180004bb8  mov     rdx, rsi; unsigned __int16 *
0x180004bbb  mov     rcx, rax; this
0x180004bbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004bc7  test    r9, r9
0x180004bca  jz      short loc_180004BDE
0x180004bcc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004bd3  mov     rdx, rsi; unsigned __int16 *
0x180004bd6  mov     rcx, rax; this
0x180004bd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bde  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004be2  test    r9, r9
0x180004be5  jz      short loc_180004BF9
0x180004be7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004bee  mov     rdx, rsi; unsigned __int16 *
0x180004bf1  mov     rcx, rax; this
0x180004bf4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bf9  mov     rcx, [rbx+28h]
0x180004bfd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004c01  mov     rdx, rsi; unsigned __int16 *
0x180004c04  test    rcx, rcx
0x180004c07  jz      short loc_180004C1F
0x180004c09  mov     [rsp+278h+lpBuffer], rcx
0x180004c0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004c15  mov     rcx, rax; this
0x180004c18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c1d  jmp     short loc_180004C41
0x180004c1f  mov     rcx, rax; this
0x180004c22  test    r9, r9
0x180004c25  jz      short loc_180004C35
0x180004c27  lea     r8, aHs; "[%hs]\n"
0x180004c2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c33  jmp     short loc_180004C41
0x180004c35  lea     r8, asc_18000E860; "\n"
0x180004c3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c41  xor     eax, eax
0x180004c43  mov     rcx, [rsp+278h+var_38]
0x180004c4b  xor     rcx, rsp; StackCookie
0x180004c4e  call    __security_check_cookie
0x180004c53  mov     rbx, [rsp+278h+arg_18]
0x180004c5b  add     rsp, 250h
0x180004c62  pop     r15
0x180004c64  pop     r14
0x180004c66  pop     rdi
0x180004c67  pop     rsi
0x180004c68  pop     rbp
0x180004c69  retn
```
