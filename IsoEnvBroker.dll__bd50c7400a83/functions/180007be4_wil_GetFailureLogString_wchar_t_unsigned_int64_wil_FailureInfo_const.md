# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007be4`
- end: `0x180007e9a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180005624`
- `0x1800058a4`
- `0x1800086dc`
- `0x18000bfa0`
- `0x18000cee8`
- `0x18005f660`
- `0x18006469c`
- `0x1800647d0`

## callees

- `0x180002520`
- `0x1800030d0`
- `0x180007be4`
- `0x1800089dc`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007d16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007d16`

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
          v7 = (const char *)&byte_18009568A;
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
0x180007be4  mov     [rsp+arg_18], rbx
0x180007be9  push    rbp
0x180007bea  push    rsi
0x180007beb  push    rdi
0x180007bec  push    r14
0x180007bee  push    r15
0x180007bf0  sub     rsp, 250h
0x180007bf7  mov     rax, cs:__security_cookie
0x180007bfe  xor     rax, rsp
0x180007c01  mov     [rsp+278h+var_38], rax
0x180007c09  mov     rbx, r8
0x180007c0c  mov     rsi, rdx
0x180007c0f  mov     r14, rcx
0x180007c12  xor     r15d, r15d
0x180007c15  test    rdx, rdx
0x180007c18  jz      loc_180007E71
0x180007c1e  test    rcx, rcx
0x180007c21  jz      loc_180007E71
0x180007c27  mov     [rcx], r15w
0x180007c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c32  test    rax, rax
0x180007c35  jz      short loc_180007C58
0x180007c37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007c3e  jz      short loc_180007C58
0x180007c40  mov     r8, rdx
0x180007c43  mov     rdx, rcx
0x180007c46  mov     rcx, rbx
0x180007c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c4e  cmp     [r14], r15w
0x180007c52  jnz     loc_180007E71
0x180007c58  mov     ecx, [rbx]
0x180007c5a  mov     bpl, 8
0x180007c5d  test    ecx, ecx
0x180007c5f  jz      short loc_180007CAA
0x180007c61  sub     ecx, 1
0x180007c64  jz      short loc_180007C92
0x180007c66  sub     ecx, 1
0x180007c69  jz      short loc_180007C82
0x180007c6b  cmp     ecx, 1
0x180007c6e  jz      short loc_180007C79
0x180007c70  lea     rdi, byte_18009568A
0x180007c77  jmp     short loc_180007CB1
0x180007c79  lea     rdi, aFailfast; "FailFast"
0x180007c80  jmp     short loc_180007CB1
0x180007c82  lea     rax, aLoghr; "LogHr"
0x180007c89  lea     rdi, aLognt; "LogNt"
0x180007c90  jmp     short loc_180007CA0
0x180007c92  lea     rax, aReturnhr; "ReturnHr"
0x180007c99  lea     rdi, aReturnnt; "ReturnNt"
0x180007ca0  test    [rbx+4], bpl
0x180007ca4  cmovz   rdi, rax
0x180007ca8  jmp     short loc_180007CB1
0x180007caa  lea     rdi, aException; "Exception"
0x180007cb1  xor     edx, edx; Val
0x180007cb3  mov     r8d, 200h; Size
0x180007cb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180007cbe  call    memset_0
0x180007cc3  test    [rbx+4], bpl
0x180007cc7  jz      short loc_180007CEC
0x180007cc9  mov     ebp, [rbx+0Ch]
0x180007ccc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180007cd3  test    rax, rax
0x180007cd6  jz      short loc_180007D1C
0x180007cd8  mov     r8d, 100h
0x180007cde  lea     rdx, [rsp+278h+Buffer]
0x180007ce3  mov     ecx, ebp
0x180007ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cea  jmp     short loc_180007D1C
0x180007cec  mov     ebp, [rbx+8]
0x180007cef  mov     [rsp+278h+Arguments], r15; Arguments
0x180007cf4  mov     [rsp+278h+nSize], 100h; nSize
0x180007cfc  lea     rax, [rsp+278h+Buffer]
0x180007d01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007d06  mov     r9d, 400h; dwLanguageId
0x180007d0c  mov     r8d, ebp; dwMessageId
0x180007d0f  xor     edx, edx; lpSource
0x180007d11  mov     ecx, 1200h; dwFlags
0x180007d16  call    cs:__imp_FormatMessageW
0x180007d1c  lea     rsi, [r14+rsi*2]
0x180007d20  mov     r9, [rbx+38h]; wchar_t *
0x180007d24  mov     rax, [rbx+88h]
0x180007d2b  mov     rcx, [rbx+80h]
0x180007d32  mov     rdx, rsi; wchar_t *
0x180007d35  test    r9, r9
0x180007d38  jz      short loc_180007D5C
0x180007d3a  mov     [rsp+278h+Arguments], rax
0x180007d3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007d44  mov     eax, [rbx+40h]
0x180007d47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007d4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007d52  mov     rcx, r14; this
0x180007d55  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007d5a  jmp     short loc_180007D73
0x180007d5c  mov     [rsp+278h+lpBuffer], rax
0x180007d61  mov     r9, rcx; wchar_t *
0x180007d64  lea     r8, aHsP; "%hs!%p: "
0x180007d6b  mov     rcx, r14; this
0x180007d6e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007d73  mov     r14, rax
0x180007d76  mov     r9, [rbx+90h]; wchar_t *
0x180007d7d  test    r9, r9
0x180007d80  jz      short loc_180007D97
0x180007d82  lea     r8, aCallerP; "(caller: %p) "
0x180007d89  mov     rdx, rsi; wchar_t *
0x180007d8c  mov     rcx, rax; this
0x180007d8f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007d94  mov     r14, rax
0x180007d97  call    cs:__imp_GetCurrentThreadId
0x180007d9d  lea     rcx, [rsp+278h+Buffer]
0x180007da2  mov     [rsp+278h+var_240], rcx
0x180007da7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007dab  mov     [rsp+278h+nSize], eax
0x180007daf  mov     eax, [rbx+44h]
0x180007db2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007db6  mov     r9, rdi; wchar_t *
0x180007db9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007dc0  mov     rdx, rsi; wchar_t *
0x180007dc3  mov     rcx, r14; this
0x180007dc6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007dcb  cmp     [rbx+18h], r15
0x180007dcf  jnz     short loc_180007DE1
0x180007dd1  cmp     [rbx+48h], r15
0x180007dd5  jnz     short loc_180007DE1
0x180007dd7  cmp     [rbx+30h], r15
0x180007ddb  jz      loc_180007E71
0x180007de1  lea     r8, asc_180095778; "    "
0x180007de8  mov     rdx, rsi; wchar_t *
0x180007deb  mov     rcx, rax; this
0x180007dee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007df3  mov     r9, [rbx+18h]; wchar_t *
0x180007df7  test    r9, r9
0x180007dfa  jz      short loc_180007E0E
0x180007dfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007e03  mov     rdx, rsi; wchar_t *
0x180007e06  mov     rcx, rax; this
0x180007e09  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007e0e  mov     r9, [rbx+48h]; wchar_t *
0x180007e12  test    r9, r9
0x180007e15  jz      short loc_180007E29
0x180007e17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007e1e  mov     rdx, rsi; wchar_t *
0x180007e21  mov     rcx, rax; this
0x180007e24  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007e29  mov     rcx, [rbx+28h]
0x180007e2d  mov     r9, [rbx+30h]; wchar_t *
0x180007e31  mov     rdx, rsi; wchar_t *
0x180007e34  test    rcx, rcx
0x180007e37  jz      short loc_180007E4F
0x180007e39  mov     [rsp+278h+lpBuffer], rcx
0x180007e3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007e45  mov     rcx, rax; this
0x180007e48  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007e4d  jmp     short loc_180007E71
0x180007e4f  mov     rcx, rax; this
0x180007e52  test    r9, r9
0x180007e55  jz      short loc_180007E65
0x180007e57  lea     r8, aHs; "[%hs]\n"
0x180007e5e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007e63  jmp     short loc_180007E71
0x180007e65  lea     r8, asc_1800957F0; "\n"
0x180007e6c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007e71  xor     eax, eax
0x180007e73  mov     rcx, [rsp+278h+var_38]
0x180007e7b  xor     rcx, rsp; StackCookie
0x180007e7e  call    __security_check_cookie
0x180007e83  mov     rbx, [rsp+278h+arg_18]
0x180007e8b  add     rsp, 250h
0x180007e92  pop     r15
0x180007e94  pop     r14
0x180007e96  pop     rdi
0x180007e97  pop     rsi
0x180007e98  pop     rbp
0x180007e99  retn
```
