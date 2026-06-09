# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180099228`
- end: `0x1800994d8`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180099dd0`

## callees

- `0x180061320`
- `0x180062314`
- `0x180099228`
- `0x18009a080`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180099351`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180099351`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800993d5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800993d5`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v6; // rdi
  const char *v7; // rax
  DWORD v8; // ebp
  wchar_t *v9; // rsi
  const wchar_t *v10; // r9
  __int64 v11; // rax
  const wchar_t *v12; // rcx
  wchar_t *v13; // rdx
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
          v6 = (const char *)&word_1800E0132;
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
  v9 = (wchar_t *)((char *)this + 4096);
  v10 = *(const wchar_t **)(a3 + 56);
  v11 = *(_QWORD *)(a3 + 136);
  v12 = *(const wchar_t **)(a3 + 128);
  v13 = (wchar_t *)((char *)this + 4096);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v9, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v8;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v9,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v6,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v9, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v9, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v9, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x180099228  mov     [rsp+arg_8], rbx
0x18009922d  push    rbp
0x18009922e  push    rsi
0x18009922f  push    rdi
0x180099230  push    r14
0x180099232  push    r15
0x180099234  sub     rsp, 250h
0x18009923b  mov     rax, cs:__security_cookie
0x180099242  xor     rax, rsp
0x180099245  mov     [rsp+278h+var_38], rax
0x18009924d  mov     rbx, r8
0x180099250  mov     r14, rcx
0x180099253  xor     r15d, r15d
0x180099256  test    rcx, rcx
0x180099259  jz      loc_1800994AF
0x18009925f  mov     [rcx], r15w
0x180099263  mov     rax, cs:g_pfnResultLoggingCallback
0x18009926a  test    rax, rax
0x18009926d  jz      short loc_180099293
0x18009926f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180099276  jz      short loc_180099293
0x180099278  mov     r8d, 800h
0x18009927e  mov     rdx, rcx
0x180099281  mov     rcx, rbx
0x180099284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099289  cmp     [r14], r15w
0x18009928d  jnz     loc_1800994AF
0x180099293  mov     ecx, [rbx]
0x180099295  mov     sil, 8
0x180099298  test    ecx, ecx
0x18009929a  jz      short loc_1800992E5
0x18009929c  sub     ecx, 1
0x18009929f  jz      short loc_1800992CD
0x1800992a1  sub     ecx, 1
0x1800992a4  jz      short loc_1800992BD
0x1800992a6  cmp     ecx, 1
0x1800992a9  jz      short loc_1800992B4
0x1800992ab  lea     rdi, word_1800E0132
0x1800992b2  jmp     short loc_1800992EC
0x1800992b4  lea     rdi, aFailfast; "FailFast"
0x1800992bb  jmp     short loc_1800992EC
0x1800992bd  lea     rax, aLoghr; "LogHr"
0x1800992c4  lea     rdi, aLognt; "LogNt"
0x1800992cb  jmp     short loc_1800992DB
0x1800992cd  lea     rax, aReturnhr; "ReturnHr"
0x1800992d4  lea     rdi, aReturnnt; "ReturnNt"
0x1800992db  test    [rbx+4], sil
0x1800992df  cmovz   rdi, rax
0x1800992e3  jmp     short loc_1800992EC
0x1800992e5  lea     rdi, aException; "Exception"
0x1800992ec  xor     edx, edx; Val
0x1800992ee  mov     r8d, 200h; Size
0x1800992f4  lea     rcx, [rsp+278h+Buffer]; void *
0x1800992f9  call    memset_0
0x1800992fe  test    [rbx+4], sil
0x180099302  jz      short loc_180099327
0x180099304  mov     ebp, [rbx+0Ch]
0x180099307  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18009930e  test    rax, rax
0x180099311  jz      short loc_180099357
0x180099313  mov     r8d, 100h
0x180099319  lea     rdx, [rsp+278h+Buffer]
0x18009931e  mov     ecx, ebp
0x180099320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099325  jmp     short loc_180099357
0x180099327  mov     ebp, [rbx+8]
0x18009932a  mov     [rsp+278h+Arguments], r15; Arguments
0x18009932f  mov     [rsp+278h+nSize], 100h; nSize
0x180099337  lea     rax, [rsp+278h+Buffer]
0x18009933c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180099341  mov     r9d, 400h; dwLanguageId
0x180099347  mov     r8d, ebp; dwMessageId
0x18009934a  xor     edx, edx; lpSource
0x18009934c  mov     ecx, 1200h; dwFlags
0x180099351  call    cs:__imp_FormatMessageW
0x180099357  lea     rsi, [r14+1000h]
0x18009935e  mov     r9, [rbx+38h]; wchar_t *
0x180099362  mov     rax, [rbx+88h]
0x180099369  mov     rcx, [rbx+80h]
0x180099370  mov     rdx, rsi; wchar_t *
0x180099373  test    r9, r9
0x180099376  jz      short loc_18009939A
0x180099378  mov     [rsp+278h+Arguments], rax
0x18009937d  mov     qword ptr [rsp+278h+nSize], rcx
0x180099382  mov     eax, [rbx+40h]
0x180099385  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180099389  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180099390  mov     rcx, r14; this
0x180099393  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180099398  jmp     short loc_1800993B1
0x18009939a  mov     [rsp+278h+lpBuffer], rax
0x18009939f  mov     r9, rcx; wchar_t *
0x1800993a2  lea     r8, aHsP; "%hs!%p: "
0x1800993a9  mov     rcx, r14; this
0x1800993ac  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800993b1  mov     r14, rax
0x1800993b4  mov     r9, [rbx+90h]; wchar_t *
0x1800993bb  test    r9, r9
0x1800993be  jz      short loc_1800993D5
0x1800993c0  lea     r8, aCallerP; "(caller: %p) "
0x1800993c7  mov     rdx, rsi; wchar_t *
0x1800993ca  mov     rcx, rax; this
0x1800993cd  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800993d2  mov     r14, rax
0x1800993d5  call    cs:__imp_GetCurrentThreadId
0x1800993db  lea     rcx, [rsp+278h+Buffer]
0x1800993e0  mov     [rsp+278h+var_240], rcx
0x1800993e5  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800993e9  mov     [rsp+278h+nSize], eax
0x1800993ed  mov     eax, [rbx+44h]
0x1800993f0  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800993f4  mov     r9, rdi; wchar_t *
0x1800993f7  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800993fe  mov     rdx, rsi; wchar_t *
0x180099401  mov     rcx, r14; this
0x180099404  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180099409  cmp     [rbx+18h], r15
0x18009940d  jnz     short loc_18009941F
0x18009940f  cmp     [rbx+48h], r15
0x180099413  jnz     short loc_18009941F
0x180099415  cmp     [rbx+30h], r15
0x180099419  jz      loc_1800994AF
0x18009941f  lea     r8, asc_1800E0220; "    "
0x180099426  mov     rdx, rsi; wchar_t *
0x180099429  mov     rcx, rax; this
0x18009942c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180099431  mov     r9, [rbx+18h]; wchar_t *
0x180099435  test    r9, r9
0x180099438  jz      short loc_18009944C
0x18009943a  lea     r8, aMsgWs; "Msg:[%ws] "
0x180099441  mov     rdx, rsi; wchar_t *
0x180099444  mov     rcx, rax; this
0x180099447  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18009944c  mov     r9, [rbx+48h]; wchar_t *
0x180099450  test    r9, r9
0x180099453  jz      short loc_180099467
0x180099455  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18009945c  mov     rdx, rsi; wchar_t *
0x18009945f  mov     rcx, rax; this
0x180099462  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180099467  mov     rcx, [rbx+28h]
0x18009946b  mov     r9, [rbx+30h]; wchar_t *
0x18009946f  mov     rdx, rsi; wchar_t *
0x180099472  test    rcx, rcx
0x180099475  jz      short loc_18009948D
0x180099477  mov     [rsp+278h+lpBuffer], rcx
0x18009947c  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180099483  mov     rcx, rax; this
0x180099486  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18009948b  jmp     short loc_1800994AF
0x18009948d  mov     rcx, rax; this
0x180099490  test    r9, r9
0x180099493  jz      short loc_1800994A3
0x180099495  lea     r8, aHs; "[%hs]\n"
0x18009949c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800994a1  jmp     short loc_1800994AF
0x1800994a3  lea     r8, asc_1800E0298; "\n"
0x1800994aa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800994af  xor     eax, eax
0x1800994b1  mov     rcx, [rsp+278h+var_38]
0x1800994b9  xor     rcx, rsp; StackCookie
0x1800994bc  call    __security_check_cookie
0x1800994c1  mov     rbx, [rsp+278h+arg_8]
0x1800994c9  add     rsp, 250h
0x1800994d0  pop     r15
0x1800994d2  pop     r14
0x1800994d4  pop     rdi
0x1800994d5  pop     rsi
0x1800994d6  pop     rbp
0x1800994d7  retn
```
