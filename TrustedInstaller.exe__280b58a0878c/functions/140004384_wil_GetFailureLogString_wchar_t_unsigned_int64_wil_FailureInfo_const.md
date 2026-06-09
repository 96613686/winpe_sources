# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004384`
- end: `0x14000463a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140003760`
- `0x140004d3c`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x140004384`
- `0x14000503c`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004537`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004537`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400044b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400044b6`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const wchar_t *v11; // r9
  wchar_t *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const wchar_t *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&qword_14002F388;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const wchar_t **)(a3 + 128), v13);
  }
  v15 = *(const wchar_t **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x140004384  mov     [rsp+arg_18], rbx
0x140004389  push    rbp
0x14000438a  push    rsi
0x14000438b  push    rdi
0x14000438c  push    r14
0x14000438e  push    r15
0x140004390  sub     rsp, 250h
0x140004397  mov     rax, cs:__security_cookie
0x14000439e  xor     rax, rsp
0x1400043a1  mov     [rsp+278h+var_38], rax
0x1400043a9  xor     r15d, r15d
0x1400043ac  mov     rbx, r8
0x1400043af  mov     rsi, rdx
0x1400043b2  mov     r14, rcx
0x1400043b5  test    rdx, rdx
0x1400043b8  jz      loc_140004611
0x1400043be  test    rcx, rcx
0x1400043c1  jz      loc_140004611
0x1400043c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400043ce  mov     [rcx], r15w
0x1400043d2  test    rax, rax
0x1400043d5  jz      short loc_1400043F8
0x1400043d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400043de  jz      short loc_1400043F8
0x1400043e0  mov     r8, rdx
0x1400043e3  mov     rdx, rcx
0x1400043e6  mov     rcx, rbx
0x1400043e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400043ee  cmp     [r14], r15w
0x1400043f2  jnz     loc_140004611
0x1400043f8  mov     ecx, [rbx]
0x1400043fa  mov     bpl, 8
0x1400043fd  test    ecx, ecx
0x1400043ff  jz      short loc_14000444A
0x140004401  sub     ecx, 1
0x140004404  jz      short loc_140004432
0x140004406  sub     ecx, 1
0x140004409  jz      short loc_140004422
0x14000440b  cmp     ecx, 1
0x14000440e  jz      short loc_140004419
0x140004410  lea     rdi, qword_14002F388
0x140004417  jmp     short loc_140004451
0x140004419  lea     rdi, aFailfast; "FailFast"
0x140004420  jmp     short loc_140004451
0x140004422  lea     rax, aLoghr; "LogHr"
0x140004429  lea     rdi, aLognt; "LogNt"
0x140004430  jmp     short loc_140004440
0x140004432  lea     rax, aReturnhr; "ReturnHr"
0x140004439  lea     rdi, aReturnnt; "ReturnNt"
0x140004440  test    [rbx+4], bpl
0x140004444  cmovz   rdi, rax
0x140004448  jmp     short loc_140004451
0x14000444a  lea     rdi, aException; "Exception"
0x140004451  xor     edx, edx; Val
0x140004453  lea     rcx, [rsp+278h+Buffer]; void *
0x140004458  mov     r8d, 200h; Size
0x14000445e  call    memset_0
0x140004463  test    [rbx+4], bpl
0x140004467  jz      short loc_14000448C
0x140004469  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140004470  mov     ebp, [rbx+0Ch]
0x140004473  test    rax, rax
0x140004476  jz      short loc_1400044BC
0x140004478  mov     r8d, 100h
0x14000447e  lea     rdx, [rsp+278h+Buffer]
0x140004483  mov     ecx, ebp
0x140004485  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000448a  jmp     short loc_1400044BC
0x14000448c  mov     ebp, [rbx+8]
0x14000448f  lea     rax, [rsp+278h+Buffer]
0x140004494  mov     [rsp+278h+Arguments], r15; Arguments
0x140004499  mov     r8d, ebp; dwMessageId
0x14000449c  mov     [rsp+278h+nSize], 100h; nSize
0x1400044a4  mov     r9d, 400h; dwLanguageId
0x1400044aa  xor     edx, edx; lpSource
0x1400044ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400044b1  mov     ecx, 1200h; dwFlags
0x1400044b6  call    cs:__imp_FormatMessageW
0x1400044bc  mov     r9, [rbx+38h]; wchar_t *
0x1400044c0  lea     rsi, [r14+rsi*2]
0x1400044c4  mov     rax, [rbx+88h]
0x1400044cb  mov     rdx, rsi; wchar_t *
0x1400044ce  mov     rcx, [rbx+80h]
0x1400044d5  test    r9, r9
0x1400044d8  jz      short loc_1400044FC
0x1400044da  mov     [rsp+278h+Arguments], rax
0x1400044df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400044e6  mov     eax, [rbx+40h]
0x1400044e9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400044ee  mov     rcx, r14; this
0x1400044f1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400044f5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400044fa  jmp     short loc_140004513
0x1400044fc  mov     r9, rcx; wchar_t *
0x1400044ff  mov     [rsp+278h+lpBuffer], rax
0x140004504  mov     rcx, r14; this
0x140004507  lea     r8, aHsP; "%hs!%p: "
0x14000450e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004513  mov     r9, [rbx+90h]; wchar_t *
0x14000451a  mov     r14, rax
0x14000451d  test    r9, r9
0x140004520  jz      short loc_140004537
0x140004522  lea     r8, aCallerP; "(caller: %p) "
0x140004529  mov     rdx, rsi; wchar_t *
0x14000452c  mov     rcx, rax; this
0x14000452f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004534  mov     r14, rax
0x140004537  call    cs:__imp_GetCurrentThreadId
0x14000453d  lea     rcx, [rsp+278h+Buffer]
0x140004542  mov     r9, rdi; wchar_t *
0x140004545  mov     [rsp+278h+var_240], rcx
0x14000454a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004551  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004555  mov     rdx, rsi; wchar_t *
0x140004558  mov     [rsp+278h+nSize], eax
0x14000455c  mov     rcx, r14; this
0x14000455f  mov     eax, [rbx+44h]
0x140004562  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004566  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000456b  cmp     [rbx+18h], r15
0x14000456f  jnz     short loc_140004581
0x140004571  cmp     [rbx+48h], r15
0x140004575  jnz     short loc_140004581
0x140004577  cmp     [rbx+30h], r15
0x14000457b  jz      loc_140004611
0x140004581  lea     r8, asc_14002F478; "    "
0x140004588  mov     rdx, rsi; wchar_t *
0x14000458b  mov     rcx, rax; this
0x14000458e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004593  mov     r9, [rbx+18h]; wchar_t *
0x140004597  test    r9, r9
0x14000459a  jz      short loc_1400045AE
0x14000459c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400045a3  mov     rdx, rsi; wchar_t *
0x1400045a6  mov     rcx, rax; this
0x1400045a9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400045ae  mov     r9, [rbx+48h]; wchar_t *
0x1400045b2  test    r9, r9
0x1400045b5  jz      short loc_1400045C9
0x1400045b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400045be  mov     rdx, rsi; wchar_t *
0x1400045c1  mov     rcx, rax; this
0x1400045c4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400045c9  mov     rcx, [rbx+28h]
0x1400045cd  mov     rdx, rsi; wchar_t *
0x1400045d0  mov     r9, [rbx+30h]; wchar_t *
0x1400045d4  test    rcx, rcx
0x1400045d7  jz      short loc_1400045EF
0x1400045d9  mov     [rsp+278h+lpBuffer], rcx
0x1400045de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400045e5  mov     rcx, rax; this
0x1400045e8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400045ed  jmp     short loc_140004611
0x1400045ef  mov     rcx, rax; this
0x1400045f2  test    r9, r9
0x1400045f5  jz      short loc_140004605
0x1400045f7  lea     r8, aHs; "[%hs]\n"
0x1400045fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004603  jmp     short loc_140004611
0x140004605  lea     r8, asc_14002F4F0; "\n"
0x14000460c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004611  xor     eax, eax
0x140004613  mov     rcx, [rsp+278h+var_38]
0x14000461b  xor     rcx, rsp; StackCookie
0x14000461e  call    __security_check_cookie
0x140004623  mov     rbx, [rsp+278h+arg_18]
0x14000462b  add     rsp, 250h
0x140004632  pop     r15
0x140004634  pop     r14
0x140004636  pop     rdi
0x140004637  pop     rsi
0x140004638  pop     rbp
0x140004639  retn
```
