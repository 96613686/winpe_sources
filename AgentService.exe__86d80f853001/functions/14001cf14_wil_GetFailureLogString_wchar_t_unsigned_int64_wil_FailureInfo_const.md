# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14001cf14`
- end: `0x14001d1ca`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14001bbd0`
- `0x14001be40`
- `0x14001d880`
- `0x14001ef60`

## callees

- `0x140003e50`
- `0x140004a78`
- `0x14001cf14`
- `0x14001db80`
- `0x14009b010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x14001d046`
- `KERNEL32!FormatMessageW` at `0x14001d046`
- `KERNEL32!GetCurrentThreadId` at `0x14001d0c7`
- `KERNEL32!GetCurrentThreadId` at `0x14001d0c7`

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
          v7 = (const char *)&byte_1400A7530;
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
0x14001cf14  mov     [rsp+arg_18], rbx
0x14001cf19  push    rbp
0x14001cf1a  push    rsi
0x14001cf1b  push    rdi
0x14001cf1c  push    r14
0x14001cf1e  push    r15
0x14001cf20  sub     rsp, 250h
0x14001cf27  mov     rax, cs:__security_cookie
0x14001cf2e  xor     rax, rsp
0x14001cf31  mov     [rsp+278h+var_38], rax
0x14001cf39  mov     rbx, r8
0x14001cf3c  mov     rsi, rdx
0x14001cf3f  mov     r14, rcx
0x14001cf42  xor     r15d, r15d
0x14001cf45  test    rdx, rdx
0x14001cf48  jz      loc_14001D1A1
0x14001cf4e  test    rcx, rcx
0x14001cf51  jz      loc_14001D1A1
0x14001cf57  mov     [rcx], r15w
0x14001cf5b  mov     rax, cs:g_pfnResultLoggingCallback
0x14001cf62  test    rax, rax
0x14001cf65  jz      short loc_14001CF88
0x14001cf67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14001cf6e  jz      short loc_14001CF88
0x14001cf70  mov     r8, rdx
0x14001cf73  mov     rdx, rcx
0x14001cf76  mov     rcx, rbx
0x14001cf79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001cf7e  cmp     [r14], r15w
0x14001cf82  jnz     loc_14001D1A1
0x14001cf88  mov     ecx, [rbx]
0x14001cf8a  mov     bpl, 8
0x14001cf8d  test    ecx, ecx
0x14001cf8f  jz      short loc_14001CFDA
0x14001cf91  sub     ecx, 1
0x14001cf94  jz      short loc_14001CFC2
0x14001cf96  sub     ecx, 1
0x14001cf99  jz      short loc_14001CFB2
0x14001cf9b  cmp     ecx, 1
0x14001cf9e  jz      short loc_14001CFA9
0x14001cfa0  lea     rdi, byte_1400A7530
0x14001cfa7  jmp     short loc_14001CFE1
0x14001cfa9  lea     rdi, aFailfast; "FailFast"
0x14001cfb0  jmp     short loc_14001CFE1
0x14001cfb2  lea     rax, aLoghr; "LogHr"
0x14001cfb9  lea     rdi, aLognt; "LogNt"
0x14001cfc0  jmp     short loc_14001CFD0
0x14001cfc2  lea     rax, aReturnhr; "ReturnHr"
0x14001cfc9  lea     rdi, aReturnnt; "ReturnNt"
0x14001cfd0  test    [rbx+4], bpl
0x14001cfd4  cmovz   rdi, rax
0x14001cfd8  jmp     short loc_14001CFE1
0x14001cfda  lea     rdi, aException; "Exception"
0x14001cfe1  xor     edx, edx; Val
0x14001cfe3  mov     r8d, 200h; Size
0x14001cfe9  lea     rcx, [rsp+278h+Buffer]; void *
0x14001cfee  call    memset_0
0x14001cff3  test    [rbx+4], bpl
0x14001cff7  jz      short loc_14001D01C
0x14001cff9  mov     ebp, [rbx+0Ch]
0x14001cffc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x14001d003  test    rax, rax
0x14001d006  jz      short loc_14001D04C
0x14001d008  mov     r8d, 100h
0x14001d00e  lea     rdx, [rsp+278h+Buffer]
0x14001d013  mov     ecx, ebp
0x14001d015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001d01a  jmp     short loc_14001D04C
0x14001d01c  mov     ebp, [rbx+8]
0x14001d01f  mov     [rsp+278h+Arguments], r15; Arguments
0x14001d024  mov     [rsp+278h+nSize], 100h; nSize
0x14001d02c  lea     rax, [rsp+278h+Buffer]
0x14001d031  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14001d036  mov     r9d, 400h; dwLanguageId
0x14001d03c  mov     r8d, ebp; dwMessageId
0x14001d03f  xor     edx, edx; lpSource
0x14001d041  mov     ecx, 1200h; dwFlags
0x14001d046  call    cs:__imp_FormatMessageW
0x14001d04c  lea     rsi, [r14+rsi*2]
0x14001d050  mov     r9, [rbx+38h]; wchar_t *
0x14001d054  mov     rax, [rbx+88h]
0x14001d05b  mov     rcx, [rbx+80h]
0x14001d062  mov     rdx, rsi; wchar_t *
0x14001d065  test    r9, r9
0x14001d068  jz      short loc_14001D08C
0x14001d06a  mov     [rsp+278h+Arguments], rax
0x14001d06f  mov     qword ptr [rsp+278h+nSize], rcx
0x14001d074  mov     eax, [rbx+40h]
0x14001d077  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14001d07b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14001d082  mov     rcx, r14; this
0x14001d085  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d08a  jmp     short loc_14001D0A3
0x14001d08c  mov     [rsp+278h+lpBuffer], rax
0x14001d091  mov     r9, rcx; wchar_t *
0x14001d094  lea     r8, aHsP; "%hs!%p: "
0x14001d09b  mov     rcx, r14; this
0x14001d09e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d0a3  mov     r14, rax
0x14001d0a6  mov     r9, [rbx+90h]; wchar_t *
0x14001d0ad  test    r9, r9
0x14001d0b0  jz      short loc_14001D0C7
0x14001d0b2  lea     r8, aCallerP; "(caller: %p) "
0x14001d0b9  mov     rdx, rsi; wchar_t *
0x14001d0bc  mov     rcx, rax; this
0x14001d0bf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d0c4  mov     r14, rax
0x14001d0c7  call    cs:__imp_GetCurrentThreadId
0x14001d0cd  lea     rcx, [rsp+278h+Buffer]
0x14001d0d2  mov     [rsp+278h+var_240], rcx
0x14001d0d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x14001d0db  mov     [rsp+278h+nSize], eax
0x14001d0df  mov     eax, [rbx+44h]
0x14001d0e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14001d0e6  mov     r9, rdi; wchar_t *
0x14001d0e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14001d0f0  mov     rdx, rsi; wchar_t *
0x14001d0f3  mov     rcx, r14; this
0x14001d0f6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d0fb  cmp     [rbx+18h], r15
0x14001d0ff  jnz     short loc_14001D111
0x14001d101  cmp     [rbx+48h], r15
0x14001d105  jnz     short loc_14001D111
0x14001d107  cmp     [rbx+30h], r15
0x14001d10b  jz      loc_14001D1A1
0x14001d111  lea     r8, asc_1400A7620; "    "
0x14001d118  mov     rdx, rsi; wchar_t *
0x14001d11b  mov     rcx, rax; this
0x14001d11e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d123  mov     r9, [rbx+18h]; wchar_t *
0x14001d127  test    r9, r9
0x14001d12a  jz      short loc_14001D13E
0x14001d12c  lea     r8, aMsgWs; "Msg:[%ws] "
0x14001d133  mov     rdx, rsi; wchar_t *
0x14001d136  mov     rcx, rax; this
0x14001d139  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d13e  mov     r9, [rbx+48h]; wchar_t *
0x14001d142  test    r9, r9
0x14001d145  jz      short loc_14001D159
0x14001d147  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14001d14e  mov     rdx, rsi; wchar_t *
0x14001d151  mov     rcx, rax; this
0x14001d154  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d159  mov     rcx, [rbx+28h]
0x14001d15d  mov     r9, [rbx+30h]; wchar_t *
0x14001d161  mov     rdx, rsi; wchar_t *
0x14001d164  test    rcx, rcx
0x14001d167  jz      short loc_14001D17F
0x14001d169  mov     [rsp+278h+lpBuffer], rcx
0x14001d16e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14001d175  mov     rcx, rax; this
0x14001d178  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d17d  jmp     short loc_14001D1A1
0x14001d17f  mov     rcx, rax; this
0x14001d182  test    r9, r9
0x14001d185  jz      short loc_14001D195
0x14001d187  lea     r8, aHs; "[%hs]\n"
0x14001d18e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d193  jmp     short loc_14001D1A1
0x14001d195  lea     r8, asc_1400A7698; "\n"
0x14001d19c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14001d1a1  xor     eax, eax
0x14001d1a3  mov     rcx, [rsp+278h+var_38]
0x14001d1ab  xor     rcx, rsp; StackCookie
0x14001d1ae  call    __security_check_cookie
0x14001d1b3  mov     rbx, [rsp+278h+arg_18]
0x14001d1bb  add     rsp, 250h
0x14001d1c2  pop     r15
0x14001d1c4  pop     r14
0x14001d1c6  pop     rdi
0x14001d1c7  pop     rsi
0x14001d1c8  pop     rbp
0x14001d1c9  retn
```
