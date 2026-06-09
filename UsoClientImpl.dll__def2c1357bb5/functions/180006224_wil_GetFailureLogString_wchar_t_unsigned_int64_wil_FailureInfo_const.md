# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006224`
- end: `0x1800064d8`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180007140`
- `0x180008e00`
- `0x180009504`
- `0x18000980c`
- `0x1800346c0`
- `0x18005d299`
- `0x18005d3d2`
- `0x1800614bd`
- `0x1800618c6`

## callees

- `0x1800061b8`
- `0x180006224`
- `0x180056500`
- `0x18005c5e0`
- `0x18005c660`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800063d5`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006354`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006354`

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
0x180006224  mov     [rsp+arg_18], rbx
0x180006229  push    rbp
0x18000622a  push    rsi
0x18000622b  push    rdi
0x18000622c  push    r14
0x18000622e  push    r15
0x180006230  sub     rsp, 250h
0x180006237  mov     rax, cs:__security_cookie
0x18000623e  xor     rax, rsp
0x180006241  mov     [rsp+278h+var_38], rax
0x180006249  mov     rbx, r8
0x18000624c  mov     rdi, rdx
0x18000624f  mov     r14, rcx
0x180006252  xor     r15d, r15d
0x180006255  test    rdx, rdx
0x180006258  jz      loc_1800064AF
0x18000625e  test    rcx, rcx
0x180006261  jz      loc_1800064AF
0x180006267  mov     [rcx], r15w
0x18000626b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006272  test    rax, rax
0x180006275  jz      short loc_180006298
0x180006277  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000627e  jz      short loc_180006298
0x180006280  mov     r8, rdx
0x180006283  mov     rdx, rcx
0x180006286  mov     rcx, rbx
0x180006289  call    _guard_dispatch_icall
0x18000628e  cmp     [r14], r15w
0x180006292  jnz     loc_1800064AF
0x180006298  lea     rsi, Src
0x18000629f  mov     ecx, [rbx]
0x1800062a1  mov     bpl, 8
0x1800062a4  test    ecx, ecx
0x1800062a6  jz      short loc_1800062E8
0x1800062a8  sub     ecx, 1
0x1800062ab  jz      short loc_1800062D0
0x1800062ad  sub     ecx, 1
0x1800062b0  jz      short loc_1800062C0
0x1800062b2  cmp     ecx, 1
0x1800062b5  jnz     short loc_1800062EF
0x1800062b7  lea     rsi, aFailfast; "FailFast"
0x1800062be  jmp     short loc_1800062EF
0x1800062c0  lea     rax, aLoghr; "LogHr"
0x1800062c7  lea     rsi, aLognt; "LogNt"
0x1800062ce  jmp     short loc_1800062DE
0x1800062d0  lea     rax, aReturnhr; "ReturnHr"
0x1800062d7  lea     rsi, aReturnnt; "ReturnNt"
0x1800062de  test    [rbx+4], bpl
0x1800062e2  cmovz   rsi, rax
0x1800062e6  jmp     short loc_1800062EF
0x1800062e8  lea     rsi, aException; "Exception"
0x1800062ef  xor     edx, edx; Val
0x1800062f1  mov     r8d, 200h; Size
0x1800062f7  lea     rcx, [rsp+278h+Buffer]; void *
0x1800062fc  call    memset
0x180006301  test    [rbx+4], bpl
0x180006305  jz      short loc_18000632A
0x180006307  mov     ebp, [rbx+0Ch]
0x18000630a  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180006311  test    rax, rax
0x180006314  jz      short loc_18000635A
0x180006316  mov     r8d, 100h
0x18000631c  lea     rdx, [rsp+278h+Buffer]
0x180006321  mov     ecx, ebp
0x180006323  call    _guard_dispatch_icall
0x180006328  jmp     short loc_18000635A
0x18000632a  mov     ebp, [rbx+8]
0x18000632d  mov     [rsp+278h+Arguments], r15; Arguments
0x180006332  mov     [rsp+278h+nSize], 100h; nSize
0x18000633a  lea     rax, [rsp+278h+Buffer]
0x18000633f  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006344  mov     r9d, 400h; dwLanguageId
0x18000634a  mov     r8d, ebp; dwMessageId
0x18000634d  xor     edx, edx; lpSource
0x18000634f  mov     ecx, 1200h; dwFlags
0x180006354  call    cs:__imp_FormatMessageW
0x18000635a  lea     rdi, [r14+rdi*2]
0x18000635e  mov     r9, [rbx+38h]; wchar_t *
0x180006362  mov     rax, [rbx+88h]
0x180006369  mov     rcx, [rbx+80h]
0x180006370  mov     rdx, rdi; wchar_t *
0x180006373  test    r9, r9
0x180006376  jz      short loc_18000639A
0x180006378  mov     [rsp+278h+Arguments], rax
0x18000637d  mov     qword ptr [rsp+278h+nSize], rcx
0x180006382  mov     eax, [rbx+40h]
0x180006385  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006389  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006390  mov     rcx, r14; this
0x180006393  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006398  jmp     short loc_1800063B1
0x18000639a  mov     [rsp+278h+lpBuffer], rax
0x18000639f  mov     r9, rcx; wchar_t *
0x1800063a2  lea     r8, aHsP; "%hs!%p: "
0x1800063a9  mov     rcx, r14; this
0x1800063ac  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800063b1  mov     r14, rax
0x1800063b4  mov     r9, [rbx+90h]; wchar_t *
0x1800063bb  test    r9, r9
0x1800063be  jz      short loc_1800063D5
0x1800063c0  lea     r8, aCallerP; "(caller: %p) "
0x1800063c7  mov     rdx, rdi; wchar_t *
0x1800063ca  mov     rcx, rax; this
0x1800063cd  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800063d2  mov     r14, rax
0x1800063d5  call    cs:__imp_GetCurrentThreadId
0x1800063db  lea     rcx, [rsp+278h+Buffer]
0x1800063e0  mov     [rsp+278h+var_240], rcx
0x1800063e5  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800063e9  mov     [rsp+278h+nSize], eax
0x1800063ed  mov     eax, [rbx+44h]
0x1800063f0  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800063f4  mov     r9, rsi; wchar_t *
0x1800063f7  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800063fe  mov     rdx, rdi; wchar_t *
0x180006401  mov     rcx, r14; this
0x180006404  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006409  cmp     [rbx+18h], r15
0x18000640d  jnz     short loc_18000641F
0x18000640f  cmp     [rbx+48h], r15
0x180006413  jnz     short loc_18000641F
0x180006415  cmp     [rbx+30h], r15
0x180006419  jz      loc_1800064AF
0x18000641f  lea     r8, asc_180065CD8; "    "
0x180006426  mov     rdx, rdi; wchar_t *
0x180006429  mov     rcx, rax; this
0x18000642c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006431  mov     r9, [rbx+18h]; wchar_t *
0x180006435  test    r9, r9
0x180006438  jz      short loc_18000644C
0x18000643a  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006441  mov     rdx, rdi; wchar_t *
0x180006444  mov     rcx, rax; this
0x180006447  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000644c  mov     r9, [rbx+48h]; wchar_t *
0x180006450  test    r9, r9
0x180006453  jz      short loc_180006467
0x180006455  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000645c  mov     rdx, rdi; wchar_t *
0x18000645f  mov     rcx, rax; this
0x180006462  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006467  mov     rcx, [rbx+28h]
0x18000646b  mov     r9, [rbx+30h]; wchar_t *
0x18000646f  mov     rdx, rdi; wchar_t *
0x180006472  test    rcx, rcx
0x180006475  jz      short loc_18000648D
0x180006477  mov     [rsp+278h+lpBuffer], rcx
0x18000647c  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006483  mov     rcx, rax; this
0x180006486  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000648b  jmp     short loc_1800064AF
0x18000648d  mov     rcx, rax; this
0x180006490  test    r9, r9
0x180006493  jz      short loc_1800064A3
0x180006495  lea     r8, aHs; "[%hs]\n"
0x18000649c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800064a1  jmp     short loc_1800064AF
0x1800064a3  lea     r8, asc_180065D50; "\n"
0x1800064aa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800064af  xor     eax, eax
0x1800064b1  mov     rcx, [rsp+278h+var_38]
0x1800064b9  xor     rcx, rsp; StackCookie
0x1800064bc  call    __security_check_cookie
0x1800064c1  mov     rbx, [rsp+278h+arg_18]
0x1800064c9  add     rsp, 250h
0x1800064d0  pop     r15
0x1800064d2  pop     r14
0x1800064d4  pop     rdi
0x1800064d5  pop     rsi
0x1800064d6  pop     rbp
0x1800064d7  retn
```
