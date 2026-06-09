# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800a02e4`
- end: `0x1800a059a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18009f568`
- `0x1800a0a20`
- `0x1800a1d00`

## callees

- `0x18009d670`
- `0x18009e054`
- `0x1800a02e4`
- `0x1800a0d20`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0497`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800a0416`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800a0416`

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
          v7 = (const char *)&word_1800E61F2;
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
0x1800a02e4  mov     [rsp+arg_18], rbx
0x1800a02e9  push    rbp
0x1800a02ea  push    rsi
0x1800a02eb  push    rdi
0x1800a02ec  push    r14
0x1800a02ee  push    r15
0x1800a02f0  sub     rsp, 250h
0x1800a02f7  mov     rax, cs:__security_cookie
0x1800a02fe  xor     rax, rsp
0x1800a0301  mov     [rsp+278h+var_38], rax
0x1800a0309  mov     rbx, r8
0x1800a030c  mov     rsi, rdx
0x1800a030f  mov     r14, rcx
0x1800a0312  xor     r15d, r15d
0x1800a0315  test    rdx, rdx
0x1800a0318  jz      loc_1800A0571
0x1800a031e  test    rcx, rcx
0x1800a0321  jz      loc_1800A0571
0x1800a0327  mov     [rcx], r15w
0x1800a032b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a0332  test    rax, rax
0x1800a0335  jz      short loc_1800A0358
0x1800a0337  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800a033e  jz      short loc_1800A0358
0x1800a0340  mov     r8, rdx
0x1800a0343  mov     rdx, rcx
0x1800a0346  mov     rcx, rbx
0x1800a0349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a034e  cmp     [r14], r15w
0x1800a0352  jnz     loc_1800A0571
0x1800a0358  mov     ecx, [rbx]
0x1800a035a  mov     bpl, 8
0x1800a035d  test    ecx, ecx
0x1800a035f  jz      short loc_1800A03AA
0x1800a0361  sub     ecx, 1
0x1800a0364  jz      short loc_1800A0392
0x1800a0366  sub     ecx, 1
0x1800a0369  jz      short loc_1800A0382
0x1800a036b  cmp     ecx, 1
0x1800a036e  jz      short loc_1800A0379
0x1800a0370  lea     rdi, word_1800E61F2
0x1800a0377  jmp     short loc_1800A03B1
0x1800a0379  lea     rdi, aFailfast; "FailFast"
0x1800a0380  jmp     short loc_1800A03B1
0x1800a0382  lea     rax, aLoghr; "LogHr"
0x1800a0389  lea     rdi, aLognt; "LogNt"
0x1800a0390  jmp     short loc_1800A03A0
0x1800a0392  lea     rax, aReturnhr; "ReturnHr"
0x1800a0399  lea     rdi, aReturnnt; "ReturnNt"
0x1800a03a0  test    [rbx+4], bpl
0x1800a03a4  cmovz   rdi, rax
0x1800a03a8  jmp     short loc_1800A03B1
0x1800a03aa  lea     rdi, aException; "Exception"
0x1800a03b1  xor     edx, edx; Val
0x1800a03b3  mov     r8d, 200h; Size
0x1800a03b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800a03be  call    memset_0
0x1800a03c3  test    [rbx+4], bpl
0x1800a03c7  jz      short loc_1800A03EC
0x1800a03c9  mov     ebp, [rbx+0Ch]
0x1800a03cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800a03d3  test    rax, rax
0x1800a03d6  jz      short loc_1800A041C
0x1800a03d8  mov     r8d, 100h
0x1800a03de  lea     rdx, [rsp+278h+Buffer]
0x1800a03e3  mov     ecx, ebp
0x1800a03e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a03ea  jmp     short loc_1800A041C
0x1800a03ec  mov     ebp, [rbx+8]
0x1800a03ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800a03f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800a03fc  lea     rax, [rsp+278h+Buffer]
0x1800a0401  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800a0406  mov     r9d, 400h; dwLanguageId
0x1800a040c  mov     r8d, ebp; dwMessageId
0x1800a040f  xor     edx, edx; lpSource
0x1800a0411  mov     ecx, 1200h; dwFlags
0x1800a0416  call    cs:__imp_FormatMessageW
0x1800a041c  lea     rsi, [r14+rsi*2]
0x1800a0420  mov     r9, [rbx+38h]; wchar_t *
0x1800a0424  mov     rax, [rbx+88h]
0x1800a042b  mov     rcx, [rbx+80h]
0x1800a0432  mov     rdx, rsi; wchar_t *
0x1800a0435  test    r9, r9
0x1800a0438  jz      short loc_1800A045C
0x1800a043a  mov     [rsp+278h+Arguments], rax
0x1800a043f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800a0444  mov     eax, [rbx+40h]
0x1800a0447  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800a044b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800a0452  mov     rcx, r14; this
0x1800a0455  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a045a  jmp     short loc_1800A0473
0x1800a045c  mov     [rsp+278h+lpBuffer], rax
0x1800a0461  mov     r9, rcx; wchar_t *
0x1800a0464  lea     r8, aHsP; "%hs!%p: "
0x1800a046b  mov     rcx, r14; this
0x1800a046e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a0473  mov     r14, rax
0x1800a0476  mov     r9, [rbx+90h]; wchar_t *
0x1800a047d  test    r9, r9
0x1800a0480  jz      short loc_1800A0497
0x1800a0482  lea     r8, aCallerP; "(caller: %p) "
0x1800a0489  mov     rdx, rsi; wchar_t *
0x1800a048c  mov     rcx, rax; this
0x1800a048f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a0494  mov     r14, rax
0x1800a0497  call    cs:__imp_GetCurrentThreadId
0x1800a049d  lea     rcx, [rsp+278h+Buffer]
0x1800a04a2  mov     [rsp+278h+var_240], rcx
0x1800a04a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800a04ab  mov     [rsp+278h+nSize], eax
0x1800a04af  mov     eax, [rbx+44h]
0x1800a04b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800a04b6  mov     r9, rdi; wchar_t *
0x1800a04b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800a04c0  mov     rdx, rsi; wchar_t *
0x1800a04c3  mov     rcx, r14; this
0x1800a04c6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a04cb  cmp     [rbx+18h], r15
0x1800a04cf  jnz     short loc_1800A04E1
0x1800a04d1  cmp     [rbx+48h], r15
0x1800a04d5  jnz     short loc_1800A04E1
0x1800a04d7  cmp     [rbx+30h], r15
0x1800a04db  jz      loc_1800A0571
0x1800a04e1  lea     r8, asc_1800E62D0; "    "
0x1800a04e8  mov     rdx, rsi; wchar_t *
0x1800a04eb  mov     rcx, rax; this
0x1800a04ee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a04f3  mov     r9, [rbx+18h]; wchar_t *
0x1800a04f7  test    r9, r9
0x1800a04fa  jz      short loc_1800A050E
0x1800a04fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800a0503  mov     rdx, rsi; wchar_t *
0x1800a0506  mov     rcx, rax; this
0x1800a0509  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a050e  mov     r9, [rbx+48h]; wchar_t *
0x1800a0512  test    r9, r9
0x1800a0515  jz      short loc_1800A0529
0x1800a0517  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800a051e  mov     rdx, rsi; wchar_t *
0x1800a0521  mov     rcx, rax; this
0x1800a0524  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a0529  mov     rcx, [rbx+28h]
0x1800a052d  mov     r9, [rbx+30h]; wchar_t *
0x1800a0531  mov     rdx, rsi; wchar_t *
0x1800a0534  test    rcx, rcx
0x1800a0537  jz      short loc_1800A054F
0x1800a0539  mov     [rsp+278h+lpBuffer], rcx
0x1800a053e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800a0545  mov     rcx, rax; this
0x1800a0548  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a054d  jmp     short loc_1800A0571
0x1800a054f  mov     rcx, rax; this
0x1800a0552  test    r9, r9
0x1800a0555  jz      short loc_1800A0565
0x1800a0557  lea     r8, aHs; "[%hs]\n"
0x1800a055e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a0563  jmp     short loc_1800A0571
0x1800a0565  lea     r8, asc_1800E6348; "\n"
0x1800a056c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800a0571  xor     eax, eax
0x1800a0573  mov     rcx, [rsp+278h+var_38]
0x1800a057b  xor     rcx, rsp; StackCookie
0x1800a057e  call    __security_check_cookie
0x1800a0583  mov     rbx, [rsp+278h+arg_18]
0x1800a058b  add     rsp, 250h
0x1800a0592  pop     r15
0x1800a0594  pop     r14
0x1800a0596  pop     rdi
0x1800a0597  pop     rsi
0x1800a0598  pop     rbp
0x1800a0599  retn
```
