# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005cd4`
- end: `0x180005f8a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003e30`
- `0x18000691c`
- `0x180007014`
- `0x18000a0a0`

## callees

- `0x180002300`
- `0x18000306c`
- `0x180005cd4`
- `0x180006c1c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005e06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005e06`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&byte_1800444C0;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180005cd4  mov     [rsp+arg_18], rbx
0x180005cd9  push    rbp
0x180005cda  push    rsi
0x180005cdb  push    rdi
0x180005cdc  push    r14
0x180005cde  push    r15
0x180005ce0  sub     rsp, 250h
0x180005ce7  mov     rax, cs:__security_cookie
0x180005cee  xor     rax, rsp
0x180005cf1  mov     [rsp+278h+var_38], rax
0x180005cf9  mov     rbx, r8
0x180005cfc  mov     rsi, rdx
0x180005cff  mov     r14, rcx
0x180005d02  xor     r15d, r15d
0x180005d05  test    rdx, rdx
0x180005d08  jz      loc_180005F61
0x180005d0e  test    rcx, rcx
0x180005d11  jz      loc_180005F61
0x180005d17  mov     [rcx], r15w
0x180005d1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005d22  test    rax, rax
0x180005d25  jz      short loc_180005D48
0x180005d27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005d2e  jz      short loc_180005D48
0x180005d30  mov     r8, rdx
0x180005d33  mov     rdx, rcx
0x180005d36  mov     rcx, rbx
0x180005d39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3e  cmp     [r14], r15w
0x180005d42  jnz     loc_180005F61
0x180005d48  mov     ecx, [rbx]
0x180005d4a  mov     bpl, 8
0x180005d4d  test    ecx, ecx
0x180005d4f  jz      short loc_180005D9A
0x180005d51  sub     ecx, 1
0x180005d54  jz      short loc_180005D82
0x180005d56  sub     ecx, 1
0x180005d59  jz      short loc_180005D72
0x180005d5b  cmp     ecx, 1
0x180005d5e  jz      short loc_180005D69
0x180005d60  lea     rdi, byte_1800444C0
0x180005d67  jmp     short loc_180005DA1
0x180005d69  lea     rdi, aFailfast; "FailFast"
0x180005d70  jmp     short loc_180005DA1
0x180005d72  lea     rax, aLoghr; "LogHr"
0x180005d79  lea     rdi, aLognt; "LogNt"
0x180005d80  jmp     short loc_180005D90
0x180005d82  lea     rax, aReturnhr; "ReturnHr"
0x180005d89  lea     rdi, aReturnnt; "ReturnNt"
0x180005d90  test    [rbx+4], bpl
0x180005d94  cmovz   rdi, rax
0x180005d98  jmp     short loc_180005DA1
0x180005d9a  lea     rdi, aException; "Exception"
0x180005da1  xor     edx, edx; Val
0x180005da3  mov     r8d, 200h; Size
0x180005da9  lea     rcx, [rsp+278h+Buffer]; void *
0x180005dae  call    memset_0
0x180005db3  test    [rbx+4], bpl
0x180005db7  jz      short loc_180005DDC
0x180005db9  mov     ebp, [rbx+0Ch]
0x180005dbc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180005dc3  test    rax, rax
0x180005dc6  jz      short loc_180005E0C
0x180005dc8  mov     r8d, 100h
0x180005dce  lea     rdx, [rsp+278h+Buffer]
0x180005dd3  mov     ecx, ebp
0x180005dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dda  jmp     short loc_180005E0C
0x180005ddc  mov     ebp, [rbx+8]
0x180005ddf  mov     [rsp+278h+Arguments], r15; Arguments
0x180005de4  mov     [rsp+278h+nSize], 100h; nSize
0x180005dec  lea     rax, [rsp+278h+Buffer]
0x180005df1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005df6  mov     r9d, 400h; dwLanguageId
0x180005dfc  mov     r8d, ebp; dwMessageId
0x180005dff  xor     edx, edx; lpSource
0x180005e01  mov     ecx, 1200h; dwFlags
0x180005e06  call    cs:__imp_FormatMessageW
0x180005e0c  lea     rsi, [r14+rsi*2]
0x180005e10  mov     r9, [rbx+38h]; wchar_t *
0x180005e14  mov     rax, [rbx+88h]
0x180005e1b  mov     rcx, [rbx+80h]
0x180005e22  mov     rdx, rsi; wchar_t *
0x180005e25  test    r9, r9
0x180005e28  jz      short loc_180005E4C
0x180005e2a  mov     [rsp+278h+Arguments], rax
0x180005e2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005e34  mov     eax, [rbx+40h]
0x180005e37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005e3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005e42  mov     rcx, r14; this
0x180005e45  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005e4a  jmp     short loc_180005E63
0x180005e4c  mov     [rsp+278h+lpBuffer], rax
0x180005e51  mov     r9, rcx; wchar_t *
0x180005e54  lea     r8, aHsP; "%hs!%p: "
0x180005e5b  mov     rcx, r14; this
0x180005e5e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005e63  mov     r14, rax
0x180005e66  mov     r9, [rbx+90h]; wchar_t *
0x180005e6d  test    r9, r9
0x180005e70  jz      short loc_180005E87
0x180005e72  lea     r8, aCallerP; "(caller: %p) "
0x180005e79  mov     rdx, rsi; wchar_t *
0x180005e7c  mov     rcx, rax; this
0x180005e7f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005e84  mov     r14, rax
0x180005e87  call    cs:__imp_GetCurrentThreadId
0x180005e8d  lea     rcx, [rsp+278h+Buffer]
0x180005e92  mov     [rsp+278h+var_240], rcx
0x180005e97  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005e9b  mov     [rsp+278h+nSize], eax
0x180005e9f  mov     eax, [rbx+44h]
0x180005ea2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005ea6  mov     r9, rdi; wchar_t *
0x180005ea9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005eb0  mov     rdx, rsi; wchar_t *
0x180005eb3  mov     rcx, r14; this
0x180005eb6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005ebb  cmp     [rbx+18h], r15
0x180005ebf  jnz     short loc_180005ED1
0x180005ec1  cmp     [rbx+48h], r15
0x180005ec5  jnz     short loc_180005ED1
0x180005ec7  cmp     [rbx+30h], r15
0x180005ecb  jz      loc_180005F61
0x180005ed1  lea     r8, asc_1800445F0; "    "
0x180005ed8  mov     rdx, rsi; wchar_t *
0x180005edb  mov     rcx, rax; this
0x180005ede  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005ee3  mov     r9, [rbx+18h]; wchar_t *
0x180005ee7  test    r9, r9
0x180005eea  jz      short loc_180005EFE
0x180005eec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005ef3  mov     rdx, rsi; wchar_t *
0x180005ef6  mov     rcx, rax; this
0x180005ef9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005efe  mov     r9, [rbx+48h]; wchar_t *
0x180005f02  test    r9, r9
0x180005f05  jz      short loc_180005F19
0x180005f07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005f0e  mov     rdx, rsi; wchar_t *
0x180005f11  mov     rcx, rax; this
0x180005f14  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005f19  mov     rcx, [rbx+28h]
0x180005f1d  mov     r9, [rbx+30h]; wchar_t *
0x180005f21  mov     rdx, rsi; wchar_t *
0x180005f24  test    rcx, rcx
0x180005f27  jz      short loc_180005F3F
0x180005f29  mov     [rsp+278h+lpBuffer], rcx
0x180005f2e  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180005f35  mov     rcx, rax; this
0x180005f38  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005f3d  jmp     short loc_180005F61
0x180005f3f  mov     rcx, rax; this
0x180005f42  test    r9, r9
0x180005f45  jz      short loc_180005F55
0x180005f47  lea     r8, aHs; "[%hs]\n"
0x180005f4e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005f53  jmp     short loc_180005F61
0x180005f55  lea     r8, asc_180044668; "\n"
0x180005f5c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005f61  xor     eax, eax
0x180005f63  mov     rcx, [rsp+278h+var_38]
0x180005f6b  xor     rcx, rsp; StackCookie
0x180005f6e  call    __security_check_cookie
0x180005f73  mov     rbx, [rsp+278h+arg_18]
0x180005f7b  add     rsp, 250h
0x180005f82  pop     r15
0x180005f84  pop     r14
0x180005f86  pop     rdi
0x180005f87  pop     rsi
0x180005f88  pop     rbp
0x180005f89  retn
```
