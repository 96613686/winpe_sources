# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005778`
- end: `0x180005a2e`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800035fc`
- `0x18000387c`
- `0x180003b30`
- `0x180006468`
- `0x18000a2c0`
- `0x18000f474`
- `0x18000f5a8`

## callees

- `0x180005778`
- `0x180006768`
- `0x18000e962`
- `0x18000e990`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000592b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000592b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800058aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800058aa`

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
          v7 = (const char *)&word_1800138F6;
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
0x180005778  mov     [rsp+arg_18], rbx
0x18000577d  push    rbp
0x18000577e  push    rsi
0x18000577f  push    rdi
0x180005780  push    r14
0x180005782  push    r15
0x180005784  sub     rsp, 250h
0x18000578b  mov     rax, cs:__security_cookie
0x180005792  xor     rax, rsp
0x180005795  mov     [rsp+278h+var_38], rax
0x18000579d  mov     rbx, r8
0x1800057a0  mov     rsi, rdx
0x1800057a3  mov     r14, rcx
0x1800057a6  xor     r15d, r15d
0x1800057a9  test    rdx, rdx
0x1800057ac  jz      loc_180005A05
0x1800057b2  test    rcx, rcx
0x1800057b5  jz      loc_180005A05
0x1800057bb  mov     [rcx], r15w
0x1800057bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800057c6  test    rax, rax
0x1800057c9  jz      short loc_1800057EC
0x1800057cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800057d2  jz      short loc_1800057EC
0x1800057d4  mov     r8, rdx
0x1800057d7  mov     rdx, rcx
0x1800057da  mov     rcx, rbx
0x1800057dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e2  cmp     [r14], r15w
0x1800057e6  jnz     loc_180005A05
0x1800057ec  mov     ecx, [rbx]
0x1800057ee  mov     bpl, 8
0x1800057f1  test    ecx, ecx
0x1800057f3  jz      short loc_18000583E
0x1800057f5  sub     ecx, 1
0x1800057f8  jz      short loc_180005826
0x1800057fa  sub     ecx, 1
0x1800057fd  jz      short loc_180005816
0x1800057ff  cmp     ecx, 1
0x180005802  jz      short loc_18000580D
0x180005804  lea     rdi, word_1800138F6
0x18000580b  jmp     short loc_180005845
0x18000580d  lea     rdi, aFailfast; "FailFast"
0x180005814  jmp     short loc_180005845
0x180005816  lea     rax, aLoghr; "LogHr"
0x18000581d  lea     rdi, aLognt; "LogNt"
0x180005824  jmp     short loc_180005834
0x180005826  lea     rax, aReturnhr; "ReturnHr"
0x18000582d  lea     rdi, aReturnnt; "ReturnNt"
0x180005834  test    [rbx+4], bpl
0x180005838  cmovz   rdi, rax
0x18000583c  jmp     short loc_180005845
0x18000583e  lea     rdi, aException; "Exception"
0x180005845  xor     edx, edx; Val
0x180005847  mov     r8d, 200h; Size
0x18000584d  lea     rcx, [rsp+278h+Buffer]; void *
0x180005852  call    memset_0
0x180005857  test    [rbx+4], bpl
0x18000585b  jz      short loc_180005880
0x18000585d  mov     ebp, [rbx+0Ch]
0x180005860  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180005867  test    rax, rax
0x18000586a  jz      short loc_1800058B0
0x18000586c  mov     r8d, 100h
0x180005872  lea     rdx, [rsp+278h+Buffer]
0x180005877  mov     ecx, ebp
0x180005879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000587e  jmp     short loc_1800058B0
0x180005880  mov     ebp, [rbx+8]
0x180005883  mov     [rsp+278h+Arguments], r15; Arguments
0x180005888  mov     [rsp+278h+nSize], 100h; nSize
0x180005890  lea     rax, [rsp+278h+Buffer]
0x180005895  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000589a  mov     r9d, 400h; dwLanguageId
0x1800058a0  mov     r8d, ebp; dwMessageId
0x1800058a3  xor     edx, edx; lpSource
0x1800058a5  mov     ecx, 1200h; dwFlags
0x1800058aa  call    cs:__imp_FormatMessageW
0x1800058b0  lea     rsi, [r14+rsi*2]
0x1800058b4  mov     r9, [rbx+38h]; wchar_t *
0x1800058b8  mov     rax, [rbx+88h]
0x1800058bf  mov     rcx, [rbx+80h]
0x1800058c6  mov     rdx, rsi; wchar_t *
0x1800058c9  test    r9, r9
0x1800058cc  jz      short loc_1800058F0
0x1800058ce  mov     [rsp+278h+Arguments], rax
0x1800058d3  mov     qword ptr [rsp+278h+nSize], rcx
0x1800058d8  mov     eax, [rbx+40h]
0x1800058db  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800058df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800058e6  mov     rcx, r14; this
0x1800058e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800058ee  jmp     short loc_180005907
0x1800058f0  mov     [rsp+278h+lpBuffer], rax
0x1800058f5  mov     r9, rcx; wchar_t *
0x1800058f8  lea     r8, aHsP; "%hs!%p: "
0x1800058ff  mov     rcx, r14; this
0x180005902  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005907  mov     r14, rax
0x18000590a  mov     r9, [rbx+90h]; wchar_t *
0x180005911  test    r9, r9
0x180005914  jz      short loc_18000592B
0x180005916  lea     r8, aCallerP; "(caller: %p) "
0x18000591d  mov     rdx, rsi; wchar_t *
0x180005920  mov     rcx, rax; this
0x180005923  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005928  mov     r14, rax
0x18000592b  call    cs:__imp_GetCurrentThreadId
0x180005931  lea     rcx, [rsp+278h+Buffer]
0x180005936  mov     [rsp+278h+var_240], rcx
0x18000593b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000593f  mov     [rsp+278h+nSize], eax
0x180005943  mov     eax, [rbx+44h]
0x180005946  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000594a  mov     r9, rdi; wchar_t *
0x18000594d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005954  mov     rdx, rsi; wchar_t *
0x180005957  mov     rcx, r14; this
0x18000595a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000595f  cmp     [rbx+18h], r15
0x180005963  jnz     short loc_180005975
0x180005965  cmp     [rbx+48h], r15
0x180005969  jnz     short loc_180005975
0x18000596b  cmp     [rbx+30h], r15
0x18000596f  jz      loc_180005A05
0x180005975  lea     r8, asc_180013820; "    "
0x18000597c  mov     rdx, rsi; wchar_t *
0x18000597f  mov     rcx, rax; this
0x180005982  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005987  mov     r9, [rbx+18h]; wchar_t *
0x18000598b  test    r9, r9
0x18000598e  jz      short loc_1800059A2
0x180005990  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005997  mov     rdx, rsi; wchar_t *
0x18000599a  mov     rcx, rax; this
0x18000599d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059a2  mov     r9, [rbx+48h]; wchar_t *
0x1800059a6  test    r9, r9
0x1800059a9  jz      short loc_1800059BD
0x1800059ab  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800059b2  mov     rdx, rsi; wchar_t *
0x1800059b5  mov     rcx, rax; this
0x1800059b8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059bd  mov     rcx, [rbx+28h]
0x1800059c1  mov     r9, [rbx+30h]; wchar_t *
0x1800059c5  mov     rdx, rsi; wchar_t *
0x1800059c8  test    rcx, rcx
0x1800059cb  jz      short loc_1800059E3
0x1800059cd  mov     [rsp+278h+lpBuffer], rcx
0x1800059d2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800059d9  mov     rcx, rax; this
0x1800059dc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059e1  jmp     short loc_180005A05
0x1800059e3  mov     rcx, rax; this
0x1800059e6  test    r9, r9
0x1800059e9  jz      short loc_1800059F9
0x1800059eb  lea     r8, aHs; "[%hs]\n"
0x1800059f2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800059f7  jmp     short loc_180005A05
0x1800059f9  lea     r8, asc_180013898; "\n"
0x180005a00  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005a05  xor     eax, eax
0x180005a07  mov     rcx, [rsp+278h+var_38]
0x180005a0f  xor     rcx, rsp; StackCookie
0x180005a12  call    __security_check_cookie
0x180005a17  mov     rbx, [rsp+278h+arg_18]
0x180005a1f  add     rsp, 250h
0x180005a26  pop     r15
0x180005a28  pop     r14
0x180005a2a  pop     rdi
0x180005a2b  pop     rsi
0x180005a2c  pop     rbp
0x180005a2d  retn
```
