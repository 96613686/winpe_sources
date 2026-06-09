# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800a3be4`
- end: `0x1800a3e9a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800a2284`
- `0x1800a4288`
- `0x1800a45f0`
- `0x1800a53b0`
- `0x1800a5e84`

## callees

- `0x180003180`
- `0x180003cc4`
- `0x1800a3be4`
- `0x1800a4588`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3d97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a3d97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800a3d16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800a3d16`

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
          v7 = (const char *)&qword_1801135E8;
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
0x1800a3be4  mov     [rsp+arg_18], rbx
0x1800a3be9  push    rbp
0x1800a3bea  push    rsi
0x1800a3beb  push    rdi
0x1800a3bec  push    r14
0x1800a3bee  push    r15
0x1800a3bf0  sub     rsp, 250h
0x1800a3bf7  mov     rax, cs:__security_cookie
0x1800a3bfe  xor     rax, rsp
0x1800a3c01  mov     [rsp+278h+var_38], rax
0x1800a3c09  mov     rbx, r8
0x1800a3c0c  mov     rsi, rdx
0x1800a3c0f  mov     r14, rcx
0x1800a3c12  xor     r15d, r15d
0x1800a3c15  test    rdx, rdx
0x1800a3c18  jz      loc_1800A3E71
0x1800a3c1e  test    rcx, rcx
0x1800a3c21  jz      loc_1800A3E71
0x1800a3c27  mov     [rcx], r15w
0x1800a3c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a3c32  test    rax, rax
0x1800a3c35  jz      short loc_1800A3C58
0x1800a3c37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800a3c3e  jz      short loc_1800A3C58
0x1800a3c40  mov     r8, rdx
0x1800a3c43  mov     rdx, rcx
0x1800a3c46  mov     rcx, rbx
0x1800a3c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3c4e  cmp     [r14], r15w
0x1800a3c52  jnz     loc_1800A3E71
0x1800a3c58  mov     ecx, [rbx]
0x1800a3c5a  mov     bpl, 8
0x1800a3c5d  test    ecx, ecx
0x1800a3c5f  jz      short loc_1800A3CAA
0x1800a3c61  sub     ecx, 1
0x1800a3c64  jz      short loc_1800A3C92
0x1800a3c66  sub     ecx, 1
0x1800a3c69  jz      short loc_1800A3C82
0x1800a3c6b  cmp     ecx, 1
0x1800a3c6e  jz      short loc_1800A3C79
0x1800a3c70  lea     rdi, qword_1801135E8
0x1800a3c77  jmp     short loc_1800A3CB1
0x1800a3c79  lea     rdi, aFailfast; "FailFast"
0x1800a3c80  jmp     short loc_1800A3CB1
0x1800a3c82  lea     rax, aLoghr; "LogHr"
0x1800a3c89  lea     rdi, aLognt; "LogNt"
0x1800a3c90  jmp     short loc_1800A3CA0
0x1800a3c92  lea     rax, aReturnhr; "ReturnHr"
0x1800a3c99  lea     rdi, aReturnnt; "ReturnNt"
0x1800a3ca0  test    [rbx+4], bpl
0x1800a3ca4  cmovz   rdi, rax
0x1800a3ca8  jmp     short loc_1800A3CB1
0x1800a3caa  lea     rdi, aException; "Exception"
0x1800a3cb1  xor     edx, edx; Val
0x1800a3cb3  mov     r8d, 200h; Size
0x1800a3cb9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800a3cbe  call    memset_0
0x1800a3cc3  test    [rbx+4], bpl
0x1800a3cc7  jz      short loc_1800A3CEC
0x1800a3cc9  mov     ebp, [rbx+0Ch]
0x1800a3ccc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800a3cd3  test    rax, rax
0x1800a3cd6  jz      short loc_1800A3D1C
0x1800a3cd8  mov     r8d, 100h
0x1800a3cde  lea     rdx, [rsp+278h+Buffer]
0x1800a3ce3  mov     ecx, ebp
0x1800a3ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a3cea  jmp     short loc_1800A3D1C
0x1800a3cec  mov     ebp, [rbx+8]
0x1800a3cef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800a3cf4  mov     [rsp+278h+nSize], 100h; nSize
0x1800a3cfc  lea     rax, [rsp+278h+Buffer]
0x1800a3d01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800a3d06  mov     r9d, 400h; dwLanguageId
0x1800a3d0c  mov     r8d, ebp; dwMessageId
0x1800a3d0f  xor     edx, edx; lpSource
0x1800a3d11  mov     ecx, 1200h; dwFlags
0x1800a3d16  call    cs:__imp_FormatMessageW
0x1800a3d1c  lea     rsi, [r14+rsi*2]
0x1800a3d20  mov     r9, [rbx+38h]; wchar_t *
0x1800a3d24  mov     rax, [rbx+88h]
0x1800a3d2b  mov     rcx, [rbx+80h]
0x1800a3d32  mov     rdx, rsi; wchar_t *
0x1800a3d35  test    r9, r9
0x1800a3d38  jz      short loc_1800A3D5C
0x1800a3d3a  mov     [rsp+278h+Arguments], rax
0x1800a3d3f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800a3d44  mov     eax, [rbx+40h]
0x1800a3d47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800a3d4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800a3d52  mov     rcx, r14; this
0x1800a3d55  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3d5a  jmp     short loc_1800A3D73
0x1800a3d5c  mov     [rsp+278h+lpBuffer], rax
0x1800a3d61  mov     r9, rcx; wchar_t *
0x1800a3d64  lea     r8, aHsP; "%hs!%p: "
0x1800a3d6b  mov     rcx, r14; this
0x1800a3d6e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3d73  mov     r14, rax
0x1800a3d76  mov     r9, [rbx+90h]; wchar_t *
0x1800a3d7d  test    r9, r9
0x1800a3d80  jz      short loc_1800A3D97
0x1800a3d82  lea     r8, aCallerP; "(caller: %p) "
0x1800a3d89  mov     rdx, rsi; wchar_t *
0x1800a3d8c  mov     rcx, rax; this
0x1800a3d8f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3d94  mov     r14, rax
0x1800a3d97  call    cs:__imp_GetCurrentThreadId
0x1800a3d9d  lea     rcx, [rsp+278h+Buffer]
0x1800a3da2  mov     [rsp+278h+var_240], rcx
0x1800a3da7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800a3dab  mov     [rsp+278h+nSize], eax
0x1800a3daf  mov     eax, [rbx+44h]
0x1800a3db2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800a3db6  mov     r9, rdi; wchar_t *
0x1800a3db9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800a3dc0  mov     rdx, rsi; wchar_t *
0x1800a3dc3  mov     rcx, r14; this
0x1800a3dc6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3dcb  cmp     [rbx+18h], r15
0x1800a3dcf  jnz     short loc_1800A3DE1
0x1800a3dd1  cmp     [rbx+48h], r15
0x1800a3dd5  jnz     short loc_1800A3DE1
0x1800a3dd7  cmp     [rbx+30h], r15
0x1800a3ddb  jz      loc_1800A3E71
0x1800a3de1  lea     r8, asc_1801136F0; "    "
0x1800a3de8  mov     rdx, rsi; wchar_t *
0x1800a3deb  mov     rcx, rax; this
0x1800a3dee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3df3  mov     r9, [rbx+18h]; wchar_t *
0x1800a3df7  test    r9, r9
0x1800a3dfa  jz      short loc_1800A3E0E
0x1800a3dfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800a3e03  mov     rdx, rsi; wchar_t *
0x1800a3e06  mov     rcx, rax; this
0x1800a3e09  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3e0e  mov     r9, [rbx+48h]; wchar_t *
0x1800a3e12  test    r9, r9
0x1800a3e15  jz      short loc_1800A3E29
0x1800a3e17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800a3e1e  mov     rdx, rsi; wchar_t *
0x1800a3e21  mov     rcx, rax; this
0x1800a3e24  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3e29  mov     rcx, [rbx+28h]
0x1800a3e2d  mov     r9, [rbx+30h]; wchar_t *
0x1800a3e31  mov     rdx, rsi; wchar_t *
0x1800a3e34  test    rcx, rcx
0x1800a3e37  jz      short loc_1800A3E4F
0x1800a3e39  mov     [rsp+278h+lpBuffer], rcx
0x1800a3e3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800a3e45  mov     rcx, rax; this
0x1800a3e48  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3e4d  jmp     short loc_1800A3E71
0x1800a3e4f  mov     rcx, rax; this
0x1800a3e52  test    r9, r9
0x1800a3e55  jz      short loc_1800A3E65
0x1800a3e57  lea     r8, aHs; "[%hs]\n"
0x1800a3e5e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3e63  jmp     short loc_1800A3E71
0x1800a3e65  lea     r8, asc_180113768; "\n"
0x1800a3e6c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a3e71  xor     eax, eax
0x1800a3e73  mov     rcx, [rsp+278h+var_38]
0x1800a3e7b  xor     rcx, rsp; StackCookie
0x1800a3e7e  call    __security_check_cookie
0x1800a3e83  mov     rbx, [rsp+278h+arg_18]
0x1800a3e8b  add     rsp, 250h
0x1800a3e92  pop     r15
0x1800a3e94  pop     r14
0x1800a3e96  pop     rdi
0x1800a3e97  pop     rsi
0x1800a3e98  pop     rbp
0x1800a3e99  retn
```
