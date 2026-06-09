# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140010c3c`
- end: `0x140010eec`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000e318`
- `0x14000e5cc`
- `0x14000e864`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x14000be30`
- `0x140010c3c`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010de9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140010de9`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140010d65`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140010d65`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v6; // rdi
  const char *v7; // rax
  DWORD v8; // ebp
  unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // r9
  __int64 v11; // rax
  const unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rdx
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

  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, 2048);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v7 = "ReturnHr";
      v6 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v6 = "FailFast";
        else
          v6 = (const char *)&byte_14001C467;
        goto LABEL_17;
      }
      v7 = "LogHr";
      v6 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v6 = v7;
    goto LABEL_17;
  }
  v6 = "Exception";
LABEL_17:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v8 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v8, Buffer, 0x100u);
  }
  else
  {
    v8 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v8, 0x400u, Buffer, 0x100u, 0);
  }
  v9 = (unsigned __int16 *)((char *)this + 4096);
  v10 = *(const unsigned __int16 **)(a3 + 56);
  v11 = *(_QWORD *)(a3 + 136);
  v12 = *(const unsigned __int16 **)(a3 + 128);
  v13 = (unsigned __int16 *)((char *)this + 4096);
  if ( v10 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, v12, v11);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs!%p: ", v12, v11);
  }
  v15 = (wil::details *)v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v9, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v8;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v9,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v6,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v9, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v9, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v9, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v9, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v9, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v9, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140010c3c  mov     [rsp+arg_8], rbx
0x140010c41  push    rbp
0x140010c42  push    rsi
0x140010c43  push    rdi
0x140010c44  push    r14
0x140010c46  push    r15
0x140010c48  sub     rsp, 250h
0x140010c4f  mov     rax, cs:__security_cookie
0x140010c56  xor     rax, rsp
0x140010c59  mov     [rsp+278h+var_38], rax
0x140010c61  mov     rbx, r8
0x140010c64  mov     r14, rcx
0x140010c67  xor     r15d, r15d
0x140010c6a  test    rcx, rcx
0x140010c6d  jz      loc_140010EC3
0x140010c73  mov     [rcx], r15w
0x140010c77  mov     rax, cs:g_pfnResultLoggingCallback
0x140010c7e  test    rax, rax
0x140010c81  jz      short loc_140010CA7
0x140010c83  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140010c8a  jz      short loc_140010CA7
0x140010c8c  mov     r8d, 800h
0x140010c92  mov     rdx, rcx
0x140010c95  mov     rcx, rbx
0x140010c98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010c9d  cmp     [r14], r15w
0x140010ca1  jnz     loc_140010EC3
0x140010ca7  mov     ecx, [rbx]
0x140010ca9  mov     sil, 8
0x140010cac  test    ecx, ecx
0x140010cae  jz      short loc_140010CF9
0x140010cb0  sub     ecx, 1
0x140010cb3  jz      short loc_140010CE1
0x140010cb5  sub     ecx, 1
0x140010cb8  jz      short loc_140010CD1
0x140010cba  cmp     ecx, 1
0x140010cbd  jz      short loc_140010CC8
0x140010cbf  lea     rdi, byte_14001C467
0x140010cc6  jmp     short loc_140010D00
0x140010cc8  lea     rdi, aFailfast; "FailFast"
0x140010ccf  jmp     short loc_140010D00
0x140010cd1  lea     rax, aLoghr; "LogHr"
0x140010cd8  lea     rdi, aLognt; "LogNt"
0x140010cdf  jmp     short loc_140010CEF
0x140010ce1  lea     rax, aReturnhr; "ReturnHr"
0x140010ce8  lea     rdi, aReturnnt; "ReturnNt"
0x140010cef  test    [rbx+4], sil
0x140010cf3  cmovz   rdi, rax
0x140010cf7  jmp     short loc_140010D00
0x140010cf9  lea     rdi, aException; "Exception"
0x140010d00  xor     edx, edx; Val
0x140010d02  mov     r8d, 200h; Size
0x140010d08  lea     rcx, [rsp+278h+Buffer]; void *
0x140010d0d  call    memset_0
0x140010d12  test    [rbx+4], sil
0x140010d16  jz      short loc_140010D3B
0x140010d18  mov     ebp, [rbx+0Ch]
0x140010d1b  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140010d22  test    rax, rax
0x140010d25  jz      short loc_140010D6B
0x140010d27  mov     r8d, 100h
0x140010d2d  lea     rdx, [rsp+278h+Buffer]
0x140010d32  mov     ecx, ebp
0x140010d34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d39  jmp     short loc_140010D6B
0x140010d3b  mov     ebp, [rbx+8]
0x140010d3e  mov     [rsp+278h+Arguments], r15; Arguments
0x140010d43  mov     [rsp+278h+nSize], 100h; nSize
0x140010d4b  lea     rax, [rsp+278h+Buffer]
0x140010d50  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140010d55  mov     r9d, 400h; dwLanguageId
0x140010d5b  mov     r8d, ebp; dwMessageId
0x140010d5e  xor     edx, edx; lpSource
0x140010d60  mov     ecx, 1200h; dwFlags
0x140010d65  call    cs:__imp_FormatMessageW
0x140010d6b  lea     rsi, [r14+1000h]
0x140010d72  mov     r9, [rbx+38h]; unsigned __int16 *
0x140010d76  mov     rax, [rbx+88h]
0x140010d7d  mov     rcx, [rbx+80h]
0x140010d84  mov     rdx, rsi; unsigned __int16 *
0x140010d87  test    r9, r9
0x140010d8a  jz      short loc_140010DAE
0x140010d8c  mov     [rsp+278h+Arguments], rax
0x140010d91  mov     qword ptr [rsp+278h+nSize], rcx
0x140010d96  mov     eax, [rbx+40h]
0x140010d99  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140010d9d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140010da4  mov     rcx, r14; this
0x140010da7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010dac  jmp     short loc_140010DC5
0x140010dae  mov     [rsp+278h+lpBuffer], rax
0x140010db3  mov     r9, rcx; unsigned __int16 *
0x140010db6  lea     r8, aHsP; "%hs!%p: "
0x140010dbd  mov     rcx, r14; this
0x140010dc0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010dc5  mov     r14, rax
0x140010dc8  mov     r9, [rbx+90h]; unsigned __int16 *
0x140010dcf  test    r9, r9
0x140010dd2  jz      short loc_140010DE9
0x140010dd4  lea     r8, aCallerP; "(caller: %p) "
0x140010ddb  mov     rdx, rsi; unsigned __int16 *
0x140010dde  mov     rcx, rax; this
0x140010de1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010de6  mov     r14, rax
0x140010de9  call    cs:__imp_GetCurrentThreadId
0x140010def  lea     rcx, [rsp+278h+Buffer]
0x140010df4  mov     [rsp+278h+var_240], rcx
0x140010df9  mov     dword ptr [rsp+278h+Arguments], ebp
0x140010dfd  mov     [rsp+278h+nSize], eax
0x140010e01  mov     eax, [rbx+44h]
0x140010e04  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140010e08  mov     r9, rdi; unsigned __int16 *
0x140010e0b  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140010e12  mov     rdx, rsi; unsigned __int16 *
0x140010e15  mov     rcx, r14; this
0x140010e18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010e1d  cmp     [rbx+18h], r15
0x140010e21  jnz     short loc_140010E33
0x140010e23  cmp     [rbx+48h], r15
0x140010e27  jnz     short loc_140010E33
0x140010e29  cmp     [rbx+30h], r15
0x140010e2d  jz      loc_140010EC3
0x140010e33  lea     r8, asc_14001C558; "    "
0x140010e3a  mov     rdx, rsi; unsigned __int16 *
0x140010e3d  mov     rcx, rax; this
0x140010e40  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010e45  mov     r9, [rbx+18h]; unsigned __int16 *
0x140010e49  test    r9, r9
0x140010e4c  jz      short loc_140010E60
0x140010e4e  lea     r8, aMsgWs; "Msg:[%ws] "
0x140010e55  mov     rdx, rsi; unsigned __int16 *
0x140010e58  mov     rcx, rax; this
0x140010e5b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010e60  mov     r9, [rbx+48h]; unsigned __int16 *
0x140010e64  test    r9, r9
0x140010e67  jz      short loc_140010E7B
0x140010e69  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140010e70  mov     rdx, rsi; unsigned __int16 *
0x140010e73  mov     rcx, rax; this
0x140010e76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010e7b  mov     rcx, [rbx+28h]
0x140010e7f  mov     r9, [rbx+30h]; unsigned __int16 *
0x140010e83  mov     rdx, rsi; unsigned __int16 *
0x140010e86  test    rcx, rcx
0x140010e89  jz      short loc_140010EA1
0x140010e8b  mov     [rsp+278h+lpBuffer], rcx
0x140010e90  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140010e97  mov     rcx, rax; this
0x140010e9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010e9f  jmp     short loc_140010EC3
0x140010ea1  mov     rcx, rax; this
0x140010ea4  test    r9, r9
0x140010ea7  jz      short loc_140010EB7
0x140010ea9  lea     r8, aHs; "[%hs]\n"
0x140010eb0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010eb5  jmp     short loc_140010EC3
0x140010eb7  lea     r8, asc_14001C5D0; "\n"
0x140010ebe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140010ec3  xor     eax, eax
0x140010ec5  mov     rcx, [rsp+278h+var_38]
0x140010ecd  xor     rcx, rsp; StackCookie
0x140010ed0  call    __security_check_cookie
0x140010ed5  mov     rbx, [rsp+278h+arg_8]
0x140010edd  add     rsp, 250h
0x140010ee4  pop     r15
0x140010ee6  pop     r14
0x140010ee8  pop     rdi
0x140010ee9  pop     rsi
0x140010eea  pop     rbp
0x140010eeb  retn
```
