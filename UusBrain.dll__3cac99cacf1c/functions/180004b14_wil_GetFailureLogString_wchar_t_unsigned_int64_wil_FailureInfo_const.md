# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004b14`
- end: `0x180004dc8`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x180005a30`
- `0x180005f20`
- `0x180007230`
- `0x180007820`
- `0x1800087f0`
- `0x180026d90`
- `0x1800486e9`
- `0x180048822`
- `0x18004be49`
- `0x18004c25b`

## callees

- `0x180004aa8`
- `0x180004b14`
- `0x1800427d0`
- `0x180047a30`
- `0x180047ab0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004cc5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c44`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004c44`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&Src;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
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
0x180004b14  mov     [rsp+arg_18], rbx
0x180004b19  push    rbp
0x180004b1a  push    rsi
0x180004b1b  push    rdi
0x180004b1c  push    r14
0x180004b1e  push    r15
0x180004b20  sub     rsp, 250h
0x180004b27  mov     rax, cs:__security_cookie
0x180004b2e  xor     rax, rsp
0x180004b31  mov     [rsp+278h+var_38], rax
0x180004b39  mov     rbx, r8
0x180004b3c  mov     rdi, rdx
0x180004b3f  mov     r14, rcx
0x180004b42  xor     r15d, r15d
0x180004b45  test    rdx, rdx
0x180004b48  jz      loc_180004D9F
0x180004b4e  test    rcx, rcx
0x180004b51  jz      loc_180004D9F
0x180004b57  mov     [rcx], r15w
0x180004b5b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004b62  test    rax, rax
0x180004b65  jz      short loc_180004B88
0x180004b67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004b6e  jz      short loc_180004B88
0x180004b70  mov     r8, rdx
0x180004b73  mov     rdx, rcx
0x180004b76  mov     rcx, rbx
0x180004b79  call    _guard_dispatch_icall
0x180004b7e  cmp     [r14], r15w
0x180004b82  jnz     loc_180004D9F
0x180004b88  lea     rsi, Src
0x180004b8f  mov     ecx, [rbx]
0x180004b91  mov     bpl, 8
0x180004b94  test    ecx, ecx
0x180004b96  jz      short loc_180004BD8
0x180004b98  sub     ecx, 1
0x180004b9b  jz      short loc_180004BC0
0x180004b9d  sub     ecx, 1
0x180004ba0  jz      short loc_180004BB0
0x180004ba2  cmp     ecx, 1
0x180004ba5  jnz     short loc_180004BDF
0x180004ba7  lea     rsi, aFailfast; "FailFast"
0x180004bae  jmp     short loc_180004BDF
0x180004bb0  lea     rax, aLoghr; "LogHr"
0x180004bb7  lea     rsi, aLognt; "LogNt"
0x180004bbe  jmp     short loc_180004BCE
0x180004bc0  lea     rax, aReturnhr; "ReturnHr"
0x180004bc7  lea     rsi, aReturnnt; "ReturnNt"
0x180004bce  test    [rbx+4], bpl
0x180004bd2  cmovz   rsi, rax
0x180004bd6  jmp     short loc_180004BDF
0x180004bd8  lea     rsi, aException; "Exception"
0x180004bdf  xor     edx, edx; Val
0x180004be1  mov     r8d, 200h; Size
0x180004be7  lea     rcx, [rsp+278h+Buffer]; void *
0x180004bec  call    memset
0x180004bf1  test    [rbx+4], bpl
0x180004bf5  jz      short loc_180004C1A
0x180004bf7  mov     ebp, [rbx+0Ch]
0x180004bfa  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180004c01  test    rax, rax
0x180004c04  jz      short loc_180004C4A
0x180004c06  mov     r8d, 100h
0x180004c0c  lea     rdx, [rsp+278h+Buffer]
0x180004c11  mov     ecx, ebp
0x180004c13  call    _guard_dispatch_icall
0x180004c18  jmp     short loc_180004C4A
0x180004c1a  mov     ebp, [rbx+8]
0x180004c1d  mov     [rsp+278h+Arguments], r15; Arguments
0x180004c22  mov     [rsp+278h+nSize], 100h; nSize
0x180004c2a  lea     rax, [rsp+278h+Buffer]
0x180004c2f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004c34  mov     r9d, 400h; dwLanguageId
0x180004c3a  mov     r8d, ebp; dwMessageId
0x180004c3d  xor     edx, edx; lpSource
0x180004c3f  mov     ecx, 1200h; dwFlags
0x180004c44  call    cs:__imp_FormatMessageW
0x180004c4a  lea     rdi, [r14+rdi*2]
0x180004c4e  mov     r9, [rbx+38h]; wchar_t *
0x180004c52  mov     rax, [rbx+88h]
0x180004c59  mov     rcx, [rbx+80h]
0x180004c60  mov     rdx, rdi; wchar_t *
0x180004c63  test    r9, r9
0x180004c66  jz      short loc_180004C8A
0x180004c68  mov     [rsp+278h+Arguments], rax
0x180004c6d  mov     qword ptr [rsp+278h+nSize], rcx
0x180004c72  mov     eax, [rbx+40h]
0x180004c75  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004c79  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004c80  mov     rcx, r14; this
0x180004c83  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004c88  jmp     short loc_180004CA1
0x180004c8a  mov     [rsp+278h+lpBuffer], rax
0x180004c8f  mov     r9, rcx; wchar_t *
0x180004c92  lea     r8, aHsP; "%hs!%p: "
0x180004c99  mov     rcx, r14; this
0x180004c9c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004ca1  mov     r14, rax
0x180004ca4  mov     r9, [rbx+90h]; wchar_t *
0x180004cab  test    r9, r9
0x180004cae  jz      short loc_180004CC5
0x180004cb0  lea     r8, aCallerP; "(caller: %p) "
0x180004cb7  mov     rdx, rdi; wchar_t *
0x180004cba  mov     rcx, rax; this
0x180004cbd  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004cc2  mov     r14, rax
0x180004cc5  call    cs:__imp_GetCurrentThreadId
0x180004ccb  lea     rcx, [rsp+278h+Buffer]
0x180004cd0  mov     [rsp+278h+var_240], rcx
0x180004cd5  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004cd9  mov     [rsp+278h+nSize], eax
0x180004cdd  mov     eax, [rbx+44h]
0x180004ce0  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004ce4  mov     r9, rsi; wchar_t *
0x180004ce7  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004cee  mov     rdx, rdi; wchar_t *
0x180004cf1  mov     rcx, r14; this
0x180004cf4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004cf9  cmp     [rbx+18h], r15
0x180004cfd  jnz     short loc_180004D0F
0x180004cff  cmp     [rbx+48h], r15
0x180004d03  jnz     short loc_180004D0F
0x180004d05  cmp     [rbx+30h], r15
0x180004d09  jz      loc_180004D9F
0x180004d0f  lea     r8, asc_18004F920; "    "
0x180004d16  mov     rdx, rdi; wchar_t *
0x180004d19  mov     rcx, rax; this
0x180004d1c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004d21  mov     r9, [rbx+18h]; wchar_t *
0x180004d25  test    r9, r9
0x180004d28  jz      short loc_180004D3C
0x180004d2a  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004d31  mov     rdx, rdi; wchar_t *
0x180004d34  mov     rcx, rax; this
0x180004d37  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004d3c  mov     r9, [rbx+48h]; wchar_t *
0x180004d40  test    r9, r9
0x180004d43  jz      short loc_180004D57
0x180004d45  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004d4c  mov     rdx, rdi; wchar_t *
0x180004d4f  mov     rcx, rax; this
0x180004d52  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004d57  mov     rcx, [rbx+28h]
0x180004d5b  mov     r9, [rbx+30h]; wchar_t *
0x180004d5f  mov     rdx, rdi; wchar_t *
0x180004d62  test    rcx, rcx
0x180004d65  jz      short loc_180004D7D
0x180004d67  mov     [rsp+278h+lpBuffer], rcx
0x180004d6c  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004d73  mov     rcx, rax; this
0x180004d76  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004d7b  jmp     short loc_180004D9F
0x180004d7d  mov     rcx, rax; this
0x180004d80  test    r9, r9
0x180004d83  jz      short loc_180004D93
0x180004d85  lea     r8, aHs; "[%hs]\n"
0x180004d8c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004d91  jmp     short loc_180004D9F
0x180004d93  lea     r8, asc_18004F998; "\n"
0x180004d9a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180004d9f  xor     eax, eax
0x180004da1  mov     rcx, [rsp+278h+var_38]
0x180004da9  xor     rcx, rsp; StackCookie
0x180004dac  call    __security_check_cookie
0x180004db1  mov     rbx, [rsp+278h+arg_18]
0x180004db9  add     rsp, 250h
0x180004dc0  pop     r15
0x180004dc2  pop     r14
0x180004dc4  pop     rdi
0x180004dc5  pop     rsi
0x180004dc6  pop     rbp
0x180004dc7  retn
```
