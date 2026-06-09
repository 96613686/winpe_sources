# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180024be8`
- end: `0x180024e9e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180022ac8`
- `0x180022d30`
- `0x1800255c4`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180024be8`
- `0x1800258c4`
- `0x18005d010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180024d1a`
- `KERNEL32!FormatMessageW` at `0x180024d1a`
- `KERNEL32!GetCurrentThreadId` at `0x180024d9b`
- `KERNEL32!GetCurrentThreadId` at `0x180024d9b`

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
          v8 = (const char *)&dword_1800624DC;
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
0x180024be8  mov     [rsp+arg_18], rbx
0x180024bed  push    rbp
0x180024bee  push    rsi
0x180024bef  push    rdi
0x180024bf0  push    r14
0x180024bf2  push    r15
0x180024bf4  sub     rsp, 250h
0x180024bfb  mov     rax, cs:__security_cookie
0x180024c02  xor     rax, rsp
0x180024c05  mov     [rsp+278h+var_38], rax
0x180024c0d  xor     r15d, r15d
0x180024c10  mov     rbx, r8
0x180024c13  mov     rsi, rdx
0x180024c16  mov     r14, rcx
0x180024c19  test    rdx, rdx
0x180024c1c  jz      loc_180024E75
0x180024c22  test    rcx, rcx
0x180024c25  jz      loc_180024E75
0x180024c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180024c32  mov     [rcx], r15w
0x180024c36  test    rax, rax
0x180024c39  jz      short loc_180024C5C
0x180024c3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180024c42  jz      short loc_180024C5C
0x180024c44  mov     r8, rdx
0x180024c47  mov     rdx, rcx
0x180024c4a  mov     rcx, rbx
0x180024c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024c52  cmp     [r14], r15w
0x180024c56  jnz     loc_180024E75
0x180024c5c  mov     ecx, [rbx]
0x180024c5e  mov     bpl, 8
0x180024c61  test    ecx, ecx
0x180024c63  jz      short loc_180024CAE
0x180024c65  sub     ecx, 1
0x180024c68  jz      short loc_180024C96
0x180024c6a  sub     ecx, 1
0x180024c6d  jz      short loc_180024C86
0x180024c6f  cmp     ecx, 1
0x180024c72  jz      short loc_180024C7D
0x180024c74  lea     rdi, dword_1800624DC
0x180024c7b  jmp     short loc_180024CB5
0x180024c7d  lea     rdi, aFailfast; "FailFast"
0x180024c84  jmp     short loc_180024CB5
0x180024c86  lea     rax, aLoghr; "LogHr"
0x180024c8d  lea     rdi, aLognt; "LogNt"
0x180024c94  jmp     short loc_180024CA4
0x180024c96  lea     rax, aReturnhr; "ReturnHr"
0x180024c9d  lea     rdi, aReturnnt; "ReturnNt"
0x180024ca4  test    [rbx+4], bpl
0x180024ca8  cmovz   rdi, rax
0x180024cac  jmp     short loc_180024CB5
0x180024cae  lea     rdi, aException; "Exception"
0x180024cb5  xor     edx, edx; Val
0x180024cb7  lea     rcx, [rsp+278h+Buffer]; void *
0x180024cbc  mov     r8d, 200h; Size
0x180024cc2  call    memset_0
0x180024cc7  test    [rbx+4], bpl
0x180024ccb  jz      short loc_180024CF0
0x180024ccd  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180024cd4  mov     ebp, [rbx+0Ch]
0x180024cd7  test    rax, rax
0x180024cda  jz      short loc_180024D20
0x180024cdc  mov     r8d, 100h
0x180024ce2  lea     rdx, [rsp+278h+Buffer]
0x180024ce7  mov     ecx, ebp
0x180024ce9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024cee  jmp     short loc_180024D20
0x180024cf0  mov     ebp, [rbx+8]
0x180024cf3  lea     rax, [rsp+278h+Buffer]
0x180024cf8  mov     [rsp+278h+Arguments], r15; Arguments
0x180024cfd  mov     r8d, ebp; dwMessageId
0x180024d00  mov     [rsp+278h+nSize], 100h; nSize
0x180024d08  mov     r9d, 400h; dwLanguageId
0x180024d0e  xor     edx, edx; lpSource
0x180024d10  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180024d15  mov     ecx, 1200h; dwFlags
0x180024d1a  call    cs:__imp_FormatMessageW
0x180024d20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180024d24  lea     rsi, [r14+rsi*2]
0x180024d28  mov     rax, [rbx+88h]
0x180024d2f  mov     rdx, rsi; unsigned __int16 *
0x180024d32  mov     rcx, [rbx+80h]
0x180024d39  test    r9, r9
0x180024d3c  jz      short loc_180024D60
0x180024d3e  mov     [rsp+278h+Arguments], rax
0x180024d43  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180024d4a  mov     eax, [rbx+40h]
0x180024d4d  mov     qword ptr [rsp+278h+nSize], rcx
0x180024d52  mov     rcx, r14; this
0x180024d55  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180024d59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024d5e  jmp     short loc_180024D77
0x180024d60  mov     r9, rcx; unsigned __int16 *
0x180024d63  mov     [rsp+278h+lpBuffer], rax
0x180024d68  mov     rcx, r14; this
0x180024d6b  lea     r8, aHsP; "%hs!%p: "
0x180024d72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024d77  mov     r9, [rbx+90h]; unsigned __int16 *
0x180024d7e  mov     r14, rax
0x180024d81  test    r9, r9
0x180024d84  jz      short loc_180024D9B
0x180024d86  lea     r8, aCallerP; "(caller: %p) "
0x180024d8d  mov     rdx, rsi; unsigned __int16 *
0x180024d90  mov     rcx, rax; this
0x180024d93  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024d98  mov     r14, rax
0x180024d9b  call    cs:__imp_GetCurrentThreadId
0x180024da1  lea     rcx, [rsp+278h+Buffer]
0x180024da6  mov     r9, rdi; unsigned __int16 *
0x180024da9  mov     [rsp+278h+var_240], rcx
0x180024dae  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180024db5  mov     dword ptr [rsp+278h+Arguments], ebp
0x180024db9  mov     rdx, rsi; unsigned __int16 *
0x180024dbc  mov     [rsp+278h+nSize], eax
0x180024dc0  mov     rcx, r14; this
0x180024dc3  mov     eax, [rbx+44h]
0x180024dc6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180024dca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024dcf  cmp     [rbx+18h], r15
0x180024dd3  jnz     short loc_180024DE5
0x180024dd5  cmp     [rbx+48h], r15
0x180024dd9  jnz     short loc_180024DE5
0x180024ddb  cmp     [rbx+30h], r15
0x180024ddf  jz      loc_180024E75
0x180024de5  lea     r8, asc_180064BA8; "    "
0x180024dec  mov     rdx, rsi; unsigned __int16 *
0x180024def  mov     rcx, rax; this
0x180024df2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024df7  mov     r9, [rbx+18h]; unsigned __int16 *
0x180024dfb  test    r9, r9
0x180024dfe  jz      short loc_180024E12
0x180024e00  lea     r8, aMsgWs; "Msg:[%ws] "
0x180024e07  mov     rdx, rsi; unsigned __int16 *
0x180024e0a  mov     rcx, rax; this
0x180024e0d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e12  mov     r9, [rbx+48h]; unsigned __int16 *
0x180024e16  test    r9, r9
0x180024e19  jz      short loc_180024E2D
0x180024e1b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180024e22  mov     rdx, rsi; unsigned __int16 *
0x180024e25  mov     rcx, rax; this
0x180024e28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e2d  mov     rcx, [rbx+28h]
0x180024e31  mov     rdx, rsi; unsigned __int16 *
0x180024e34  mov     r9, [rbx+30h]; unsigned __int16 *
0x180024e38  test    rcx, rcx
0x180024e3b  jz      short loc_180024E53
0x180024e3d  mov     [rsp+278h+lpBuffer], rcx
0x180024e42  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180024e49  mov     rcx, rax; this
0x180024e4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e51  jmp     short loc_180024E75
0x180024e53  mov     rcx, rax; this
0x180024e56  test    r9, r9
0x180024e59  jz      short loc_180024E69
0x180024e5b  lea     r8, aHs; "[%hs]\n"
0x180024e62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e67  jmp     short loc_180024E75
0x180024e69  lea     r8, asc_180064C20; "\n"
0x180024e70  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180024e75  xor     eax, eax
0x180024e77  mov     rcx, [rsp+278h+var_38]
0x180024e7f  xor     rcx, rsp; StackCookie
0x180024e82  call    __security_check_cookie
0x180024e87  mov     rbx, [rsp+278h+arg_18]
0x180024e8f  add     rsp, 250h
0x180024e96  pop     r15
0x180024e98  pop     r14
0x180024e9a  pop     rdi
0x180024e9b  pop     rsi
0x180024e9c  pop     rbp
0x180024e9d  retn
```
