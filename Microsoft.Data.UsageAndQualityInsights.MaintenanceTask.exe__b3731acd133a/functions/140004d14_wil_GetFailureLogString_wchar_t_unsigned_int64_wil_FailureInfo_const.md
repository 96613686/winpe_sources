# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004d14`
- end: `0x140004fca`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000280c`
- `0x140002a74`
- `0x14000575c`
- `0x140008d20`

## callees

- `0x1400016f0`
- `0x14000221c`
- `0x140004d14`
- `0x140005a5c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ec7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004ec7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004e46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140004e46`

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
          v7 = (const char *)&qword_14000D7D0;
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
0x140004d14  mov     [rsp+arg_18], rbx
0x140004d19  push    rbp
0x140004d1a  push    rsi
0x140004d1b  push    rdi
0x140004d1c  push    r14
0x140004d1e  push    r15
0x140004d20  sub     rsp, 250h
0x140004d27  mov     rax, cs:__security_cookie
0x140004d2e  xor     rax, rsp
0x140004d31  mov     [rsp+278h+var_38], rax
0x140004d39  mov     rbx, r8
0x140004d3c  mov     rsi, rdx
0x140004d3f  mov     r14, rcx
0x140004d42  xor     r15d, r15d
0x140004d45  test    rdx, rdx
0x140004d48  jz      loc_140004FA1
0x140004d4e  test    rcx, rcx
0x140004d51  jz      loc_140004FA1
0x140004d57  mov     [rcx], r15w
0x140004d5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004d62  test    rax, rax
0x140004d65  jz      short loc_140004D88
0x140004d67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140004d6e  jz      short loc_140004D88
0x140004d70  mov     r8, rdx
0x140004d73  mov     rdx, rcx
0x140004d76  mov     rcx, rbx
0x140004d79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d7e  cmp     [r14], r15w
0x140004d82  jnz     loc_140004FA1
0x140004d88  mov     ecx, [rbx]
0x140004d8a  mov     bpl, 8
0x140004d8d  test    ecx, ecx
0x140004d8f  jz      short loc_140004DDA
0x140004d91  sub     ecx, 1
0x140004d94  jz      short loc_140004DC2
0x140004d96  sub     ecx, 1
0x140004d99  jz      short loc_140004DB2
0x140004d9b  cmp     ecx, 1
0x140004d9e  jz      short loc_140004DA9
0x140004da0  lea     rdi, qword_14000D7D0
0x140004da7  jmp     short loc_140004DE1
0x140004da9  lea     rdi, aFailfast; "FailFast"
0x140004db0  jmp     short loc_140004DE1
0x140004db2  lea     rax, aLoghr; "LogHr"
0x140004db9  lea     rdi, aLognt; "LogNt"
0x140004dc0  jmp     short loc_140004DD0
0x140004dc2  lea     rax, aReturnhr; "ReturnHr"
0x140004dc9  lea     rdi, aReturnnt; "ReturnNt"
0x140004dd0  test    [rbx+4], bpl
0x140004dd4  cmovz   rdi, rax
0x140004dd8  jmp     short loc_140004DE1
0x140004dda  lea     rdi, aException; "Exception"
0x140004de1  xor     edx, edx; Val
0x140004de3  mov     r8d, 200h; Size
0x140004de9  lea     rcx, [rsp+278h+Buffer]; void *
0x140004dee  call    memset_0
0x140004df3  test    [rbx+4], bpl
0x140004df7  jz      short loc_140004E1C
0x140004df9  mov     ebp, [rbx+0Ch]
0x140004dfc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140004e03  test    rax, rax
0x140004e06  jz      short loc_140004E4C
0x140004e08  mov     r8d, 100h
0x140004e0e  lea     rdx, [rsp+278h+Buffer]
0x140004e13  mov     ecx, ebp
0x140004e15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e1a  jmp     short loc_140004E4C
0x140004e1c  mov     ebp, [rbx+8]
0x140004e1f  mov     [rsp+278h+Arguments], r15; Arguments
0x140004e24  mov     [rsp+278h+nSize], 100h; nSize
0x140004e2c  lea     rax, [rsp+278h+Buffer]
0x140004e31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140004e36  mov     r9d, 400h; dwLanguageId
0x140004e3c  mov     r8d, ebp; dwMessageId
0x140004e3f  xor     edx, edx; lpSource
0x140004e41  mov     ecx, 1200h; dwFlags
0x140004e46  call    cs:__imp_FormatMessageW
0x140004e4c  lea     rsi, [r14+rsi*2]
0x140004e50  mov     r9, [rbx+38h]; wchar_t *
0x140004e54  mov     rax, [rbx+88h]
0x140004e5b  mov     rcx, [rbx+80h]
0x140004e62  mov     rdx, rsi; wchar_t *
0x140004e65  test    r9, r9
0x140004e68  jz      short loc_140004E8C
0x140004e6a  mov     [rsp+278h+Arguments], rax
0x140004e6f  mov     qword ptr [rsp+278h+nSize], rcx
0x140004e74  mov     eax, [rbx+40h]
0x140004e77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004e7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004e82  mov     rcx, r14; this
0x140004e85  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004e8a  jmp     short loc_140004EA3
0x140004e8c  mov     [rsp+278h+lpBuffer], rax
0x140004e91  mov     r9, rcx; wchar_t *
0x140004e94  lea     r8, aHsP; "%hs!%p: "
0x140004e9b  mov     rcx, r14; this
0x140004e9e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004ea3  mov     r14, rax
0x140004ea6  mov     r9, [rbx+90h]; wchar_t *
0x140004ead  test    r9, r9
0x140004eb0  jz      short loc_140004EC7
0x140004eb2  lea     r8, aCallerP; "(caller: %p) "
0x140004eb9  mov     rdx, rsi; wchar_t *
0x140004ebc  mov     rcx, rax; this
0x140004ebf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004ec4  mov     r14, rax
0x140004ec7  call    cs:__imp_GetCurrentThreadId
0x140004ecd  lea     rcx, [rsp+278h+Buffer]
0x140004ed2  mov     [rsp+278h+var_240], rcx
0x140004ed7  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004edb  mov     [rsp+278h+nSize], eax
0x140004edf  mov     eax, [rbx+44h]
0x140004ee2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004ee6  mov     r9, rdi; wchar_t *
0x140004ee9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004ef0  mov     rdx, rsi; wchar_t *
0x140004ef3  mov     rcx, r14; this
0x140004ef6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004efb  cmp     [rbx+18h], r15
0x140004eff  jnz     short loc_140004F11
0x140004f01  cmp     [rbx+48h], r15
0x140004f05  jnz     short loc_140004F11
0x140004f07  cmp     [rbx+30h], r15
0x140004f0b  jz      loc_140004FA1
0x140004f11  lea     r8, asc_14000D8D8; "    "
0x140004f18  mov     rdx, rsi; wchar_t *
0x140004f1b  mov     rcx, rax; this
0x140004f1e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004f23  mov     r9, [rbx+18h]; wchar_t *
0x140004f27  test    r9, r9
0x140004f2a  jz      short loc_140004F3E
0x140004f2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004f33  mov     rdx, rsi; wchar_t *
0x140004f36  mov     rcx, rax; this
0x140004f39  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004f3e  mov     r9, [rbx+48h]; wchar_t *
0x140004f42  test    r9, r9
0x140004f45  jz      short loc_140004F59
0x140004f47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004f4e  mov     rdx, rsi; wchar_t *
0x140004f51  mov     rcx, rax; this
0x140004f54  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004f59  mov     rcx, [rbx+28h]
0x140004f5d  mov     r9, [rbx+30h]; wchar_t *
0x140004f61  mov     rdx, rsi; wchar_t *
0x140004f64  test    rcx, rcx
0x140004f67  jz      short loc_140004F7F
0x140004f69  mov     [rsp+278h+lpBuffer], rcx
0x140004f6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004f75  mov     rcx, rax; this
0x140004f78  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004f7d  jmp     short loc_140004FA1
0x140004f7f  mov     rcx, rax; this
0x140004f82  test    r9, r9
0x140004f85  jz      short loc_140004F95
0x140004f87  lea     r8, aHs; "[%hs]\n"
0x140004f8e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004f93  jmp     short loc_140004FA1
0x140004f95  lea     r8, asc_14000D950; "\n"
0x140004f9c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004fa1  xor     eax, eax
0x140004fa3  mov     rcx, [rsp+278h+var_38]
0x140004fab  xor     rcx, rsp; StackCookie
0x140004fae  call    __security_check_cookie
0x140004fb3  mov     rbx, [rsp+278h+arg_18]
0x140004fbb  add     rsp, 250h
0x140004fc2  pop     r15
0x140004fc4  pop     r14
0x140004fc6  pop     rdi
0x140004fc7  pop     rsi
0x140004fc8  pop     rbp
0x140004fc9  retn
```
