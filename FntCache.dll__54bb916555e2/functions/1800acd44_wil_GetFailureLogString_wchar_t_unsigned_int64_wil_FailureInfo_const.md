# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800acd44`
- end: `0x1800acffa`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ad5b8`
- `0x1800adc50`
- `0x1800afb50`

## callees

- `0x1800aa650`
- `0x1800ab180`
- `0x1800acd44`
- `0x1800ad8b4`
- `0x1800e6010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ace76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800ace76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acef7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800acef7`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        wchar_t *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const wchar_t *v16; // r9
  wchar_t *v17; // rax
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
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
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
          v7 = (const char *)&dword_1800EC744;
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
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800acd44  mov     [rsp+arg_18], rbx
0x1800acd49  push    rbp
0x1800acd4a  push    rsi
0x1800acd4b  push    rdi
0x1800acd4c  push    r14
0x1800acd4e  push    r15
0x1800acd50  sub     rsp, 250h
0x1800acd57  mov     rax, cs:__security_cookie
0x1800acd5e  xor     rax, rsp
0x1800acd61  mov     [rsp+278h+var_38], rax
0x1800acd69  mov     rbx, r8
0x1800acd6c  mov     rsi, rdx
0x1800acd6f  mov     r14, rcx
0x1800acd72  xor     r15d, r15d
0x1800acd75  test    rdx, rdx
0x1800acd78  jz      loc_1800ACFD1
0x1800acd7e  test    rcx, rcx
0x1800acd81  jz      loc_1800ACFD1
0x1800acd87  mov     [rcx], r15w
0x1800acd8b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800acd92  test    rax, rax
0x1800acd95  jz      short loc_1800ACDB8
0x1800acd97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800acd9e  jz      short loc_1800ACDB8
0x1800acda0  mov     r8, rdx
0x1800acda3  mov     rdx, rcx
0x1800acda6  mov     rcx, rbx
0x1800acda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800acdae  cmp     [r14], r15w
0x1800acdb2  jnz     loc_1800ACFD1
0x1800acdb8  mov     ecx, [rbx]
0x1800acdba  mov     bpl, 8
0x1800acdbd  test    ecx, ecx
0x1800acdbf  jz      short loc_1800ACE0A
0x1800acdc1  sub     ecx, 1
0x1800acdc4  jz      short loc_1800ACDF2
0x1800acdc6  sub     ecx, 1
0x1800acdc9  jz      short loc_1800ACDE2
0x1800acdcb  cmp     ecx, 1
0x1800acdce  jz      short loc_1800ACDD9
0x1800acdd0  lea     rdi, dword_1800EC744
0x1800acdd7  jmp     short loc_1800ACE11
0x1800acdd9  lea     rdi, aFailfast; "FailFast"
0x1800acde0  jmp     short loc_1800ACE11
0x1800acde2  lea     rax, aLoghr; "LogHr"
0x1800acde9  lea     rdi, aLognt; "LogNt"
0x1800acdf0  jmp     short loc_1800ACE00
0x1800acdf2  lea     rax, aReturnhr; "ReturnHr"
0x1800acdf9  lea     rdi, aReturnnt; "ReturnNt"
0x1800ace00  test    [rbx+4], bpl
0x1800ace04  cmovz   rdi, rax
0x1800ace08  jmp     short loc_1800ACE11
0x1800ace0a  lea     rdi, aException; "Exception"
0x1800ace11  xor     edx, edx; Val
0x1800ace13  mov     r8d, 200h; Size
0x1800ace19  lea     rcx, [rsp+278h+Buffer]; void *
0x1800ace1e  call    memset_0
0x1800ace23  test    [rbx+4], bpl
0x1800ace27  jz      short loc_1800ACE4C
0x1800ace29  mov     ebp, [rbx+0Ch]
0x1800ace2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800ace33  test    rax, rax
0x1800ace36  jz      short loc_1800ACE7C
0x1800ace38  mov     r8d, 100h
0x1800ace3e  lea     rdx, [rsp+278h+Buffer]
0x1800ace43  mov     ecx, ebp
0x1800ace45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ace4a  jmp     short loc_1800ACE7C
0x1800ace4c  mov     ebp, [rbx+8]
0x1800ace4f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800ace54  mov     [rsp+278h+nSize], 100h; nSize
0x1800ace5c  lea     rax, [rsp+278h+Buffer]
0x1800ace61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800ace66  mov     r9d, 400h; dwLanguageId
0x1800ace6c  mov     r8d, ebp; dwMessageId
0x1800ace6f  xor     edx, edx; lpSource
0x1800ace71  mov     ecx, 1200h; dwFlags
0x1800ace76  call    cs:__imp_FormatMessageW
0x1800ace7c  lea     rsi, [r14+rsi*2]
0x1800ace80  mov     r9, [rbx+38h]; wchar_t *
0x1800ace84  mov     rax, [rbx+88h]
0x1800ace8b  mov     rcx, [rbx+80h]
0x1800ace92  mov     rdx, rsi; wchar_t *
0x1800ace95  test    r9, r9
0x1800ace98  jz      short loc_1800ACEBC
0x1800ace9a  mov     [rsp+278h+Arguments], rax
0x1800ace9f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800acea4  mov     eax, [rbx+40h]
0x1800acea7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800aceab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800aceb2  mov     rcx, r14; pszDest
0x1800aceb5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aceba  jmp     short loc_1800ACED3
0x1800acebc  mov     [rsp+278h+lpBuffer], rax
0x1800acec1  mov     r9, rcx; wchar_t *
0x1800acec4  lea     r8, aHsP; "%hs!%p: "
0x1800acecb  mov     rcx, r14; pszDest
0x1800acece  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aced3  mov     r14, rax
0x1800aced6  mov     r9, [rbx+90h]; wchar_t *
0x1800acedd  test    r9, r9
0x1800acee0  jz      short loc_1800ACEF7
0x1800acee2  lea     r8, aCallerP; "(caller: %p) "
0x1800acee9  mov     rdx, rsi; wchar_t *
0x1800aceec  mov     rcx, rax; pszDest
0x1800aceef  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acef4  mov     r14, rax
0x1800acef7  call    cs:__imp_GetCurrentThreadId
0x1800acefd  lea     rcx, [rsp+278h+Buffer]
0x1800acf02  mov     [rsp+278h+var_240], rcx
0x1800acf07  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800acf0b  mov     [rsp+278h+nSize], eax
0x1800acf0f  mov     eax, [rbx+44h]
0x1800acf12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800acf16  mov     r9, rdi; wchar_t *
0x1800acf19  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800acf20  mov     rdx, rsi; wchar_t *
0x1800acf23  mov     rcx, r14; pszDest
0x1800acf26  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acf2b  cmp     [rbx+18h], r15
0x1800acf2f  jnz     short loc_1800ACF41
0x1800acf31  cmp     [rbx+48h], r15
0x1800acf35  jnz     short loc_1800ACF41
0x1800acf37  cmp     [rbx+30h], r15
0x1800acf3b  jz      loc_1800ACFD1
0x1800acf41  lea     r8, asc_180100F78; "    "
0x1800acf48  mov     rdx, rsi; wchar_t *
0x1800acf4b  mov     rcx, rax; pszDest
0x1800acf4e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acf53  mov     r9, [rbx+18h]; wchar_t *
0x1800acf57  test    r9, r9
0x1800acf5a  jz      short loc_1800ACF6E
0x1800acf5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800acf63  mov     rdx, rsi; wchar_t *
0x1800acf66  mov     rcx, rax; pszDest
0x1800acf69  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acf6e  mov     r9, [rbx+48h]; wchar_t *
0x1800acf72  test    r9, r9
0x1800acf75  jz      short loc_1800ACF89
0x1800acf77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800acf7e  mov     rdx, rsi; wchar_t *
0x1800acf81  mov     rcx, rax; pszDest
0x1800acf84  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acf89  mov     rcx, [rbx+28h]
0x1800acf8d  mov     r9, [rbx+30h]; wchar_t *
0x1800acf91  mov     rdx, rsi; wchar_t *
0x1800acf94  test    rcx, rcx
0x1800acf97  jz      short loc_1800ACFAF
0x1800acf99  mov     [rsp+278h+lpBuffer], rcx
0x1800acf9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800acfa5  mov     rcx, rax; pszDest
0x1800acfa8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acfad  jmp     short loc_1800ACFD1
0x1800acfaf  mov     rcx, rax; pszDest
0x1800acfb2  test    r9, r9
0x1800acfb5  jz      short loc_1800ACFC5
0x1800acfb7  lea     r8, aHs; "[%hs]\n"
0x1800acfbe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acfc3  jmp     short loc_1800ACFD1
0x1800acfc5  lea     r8, asc_180100FF0; "\n"
0x1800acfcc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800acfd1  xor     eax, eax
0x1800acfd3  mov     rcx, [rsp+278h+var_38]
0x1800acfdb  xor     rcx, rsp; StackCookie
0x1800acfde  call    __security_check_cookie
0x1800acfe3  mov     rbx, [rsp+278h+arg_18]
0x1800acfeb  add     rsp, 250h
0x1800acff2  pop     r15
0x1800acff4  pop     r14
0x1800acff6  pop     rdi
0x1800acff7  pop     rsi
0x1800acff8  pop     rbp
0x1800acff9  retn
```
