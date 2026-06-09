# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800062b4`
- end: `0x18000656a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002564`
- `0x1800027cc`
- `0x1800075e0`
- `0x18000ccc0`

## callees

- `0x1800062b4`
- `0x1800078e0`
- `0x18000f5c2`
- `0x18000f5f0`
- `0x180011010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x1800063e6`
- `KERNEL32!FormatMessageW` at `0x1800063e6`
- `KERNEL32!GetCurrentThreadId` at `0x180006467`
- `KERNEL32!GetCurrentThreadId` at `0x180006467`

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
          v7 = (const char *)&byte_180012D0F;
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
0x1800062b4  mov     [rsp+arg_18], rbx
0x1800062b9  push    rbp
0x1800062ba  push    rsi
0x1800062bb  push    rdi
0x1800062bc  push    r14
0x1800062be  push    r15
0x1800062c0  sub     rsp, 250h
0x1800062c7  mov     rax, cs:__security_cookie
0x1800062ce  xor     rax, rsp
0x1800062d1  mov     [rsp+278h+var_38], rax
0x1800062d9  mov     rbx, r8
0x1800062dc  mov     rsi, rdx
0x1800062df  mov     r14, rcx
0x1800062e2  xor     r15d, r15d
0x1800062e5  test    rdx, rdx
0x1800062e8  jz      loc_180006541
0x1800062ee  test    rcx, rcx
0x1800062f1  jz      loc_180006541
0x1800062f7  mov     [rcx], r15w
0x1800062fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006302  test    rax, rax
0x180006305  jz      short loc_180006328
0x180006307  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000630e  jz      short loc_180006328
0x180006310  mov     r8, rdx
0x180006313  mov     rdx, rcx
0x180006316  mov     rcx, rbx
0x180006319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000631e  cmp     [r14], r15w
0x180006322  jnz     loc_180006541
0x180006328  mov     ecx, [rbx]
0x18000632a  mov     bpl, 8
0x18000632d  test    ecx, ecx
0x18000632f  jz      short loc_18000637A
0x180006331  sub     ecx, 1
0x180006334  jz      short loc_180006362
0x180006336  sub     ecx, 1
0x180006339  jz      short loc_180006352
0x18000633b  cmp     ecx, 1
0x18000633e  jz      short loc_180006349
0x180006340  lea     rdi, byte_180012D0F
0x180006347  jmp     short loc_180006381
0x180006349  lea     rdi, aFailfast; "FailFast"
0x180006350  jmp     short loc_180006381
0x180006352  lea     rax, aLoghr; "LogHr"
0x180006359  lea     rdi, aLognt; "LogNt"
0x180006360  jmp     short loc_180006370
0x180006362  lea     rax, aReturnhr; "ReturnHr"
0x180006369  lea     rdi, aReturnnt; "ReturnNt"
0x180006370  test    [rbx+4], bpl
0x180006374  cmovz   rdi, rax
0x180006378  jmp     short loc_180006381
0x18000637a  lea     rdi, aException; "Exception"
0x180006381  xor     edx, edx; Val
0x180006383  mov     r8d, 200h; Size
0x180006389  lea     rcx, [rsp+278h+Buffer]; void *
0x18000638e  call    memset_0
0x180006393  test    [rbx+4], bpl
0x180006397  jz      short loc_1800063BC
0x180006399  mov     ebp, [rbx+0Ch]
0x18000639c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800063a3  test    rax, rax
0x1800063a6  jz      short loc_1800063EC
0x1800063a8  mov     r8d, 100h
0x1800063ae  lea     rdx, [rsp+278h+Buffer]
0x1800063b3  mov     ecx, ebp
0x1800063b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ba  jmp     short loc_1800063EC
0x1800063bc  mov     ebp, [rbx+8]
0x1800063bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800063c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800063cc  lea     rax, [rsp+278h+Buffer]
0x1800063d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800063d6  mov     r9d, 400h; dwLanguageId
0x1800063dc  mov     r8d, ebp; dwMessageId
0x1800063df  xor     edx, edx; lpSource
0x1800063e1  mov     ecx, 1200h; dwFlags
0x1800063e6  call    cs:__imp_FormatMessageW
0x1800063ec  lea     rsi, [r14+rsi*2]
0x1800063f0  mov     r9, [rbx+38h]; wchar_t *
0x1800063f4  mov     rax, [rbx+88h]
0x1800063fb  mov     rcx, [rbx+80h]
0x180006402  mov     rdx, rsi; wchar_t *
0x180006405  test    r9, r9
0x180006408  jz      short loc_18000642C
0x18000640a  mov     [rsp+278h+Arguments], rax
0x18000640f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006414  mov     eax, [rbx+40h]
0x180006417  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000641b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006422  mov     rcx, r14; this
0x180006425  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000642a  jmp     short loc_180006443
0x18000642c  mov     [rsp+278h+lpBuffer], rax
0x180006431  mov     r9, rcx; wchar_t *
0x180006434  lea     r8, aHsP; "%hs!%p: "
0x18000643b  mov     rcx, r14; this
0x18000643e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006443  mov     r14, rax
0x180006446  mov     r9, [rbx+90h]; wchar_t *
0x18000644d  test    r9, r9
0x180006450  jz      short loc_180006467
0x180006452  lea     r8, aCallerP; "(caller: %p) "
0x180006459  mov     rdx, rsi; wchar_t *
0x18000645c  mov     rcx, rax; this
0x18000645f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006464  mov     r14, rax
0x180006467  call    cs:__imp_GetCurrentThreadId
0x18000646d  lea     rcx, [rsp+278h+Buffer]
0x180006472  mov     [rsp+278h+var_240], rcx
0x180006477  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000647b  mov     [rsp+278h+nSize], eax
0x18000647f  mov     eax, [rbx+44h]
0x180006482  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006486  mov     r9, rdi; wchar_t *
0x180006489  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006490  mov     rdx, rsi; wchar_t *
0x180006493  mov     rcx, r14; this
0x180006496  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000649b  cmp     [rbx+18h], r15
0x18000649f  jnz     short loc_1800064B1
0x1800064a1  cmp     [rbx+48h], r15
0x1800064a5  jnz     short loc_1800064B1
0x1800064a7  cmp     [rbx+30h], r15
0x1800064ab  jz      loc_180006541
0x1800064b1  lea     r8, asc_180012DF8; "    "
0x1800064b8  mov     rdx, rsi; wchar_t *
0x1800064bb  mov     rcx, rax; this
0x1800064be  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800064c3  mov     r9, [rbx+18h]; wchar_t *
0x1800064c7  test    r9, r9
0x1800064ca  jz      short loc_1800064DE
0x1800064cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800064d3  mov     rdx, rsi; wchar_t *
0x1800064d6  mov     rcx, rax; this
0x1800064d9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800064de  mov     r9, [rbx+48h]; wchar_t *
0x1800064e2  test    r9, r9
0x1800064e5  jz      short loc_1800064F9
0x1800064e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800064ee  mov     rdx, rsi; wchar_t *
0x1800064f1  mov     rcx, rax; this
0x1800064f4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800064f9  mov     rcx, [rbx+28h]
0x1800064fd  mov     r9, [rbx+30h]; wchar_t *
0x180006501  mov     rdx, rsi; wchar_t *
0x180006504  test    rcx, rcx
0x180006507  jz      short loc_18000651F
0x180006509  mov     [rsp+278h+lpBuffer], rcx
0x18000650e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006515  mov     rcx, rax; this
0x180006518  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000651d  jmp     short loc_180006541
0x18000651f  mov     rcx, rax; this
0x180006522  test    r9, r9
0x180006525  jz      short loc_180006535
0x180006527  lea     r8, aHs; "[%hs]\n"
0x18000652e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006533  jmp     short loc_180006541
0x180006535  lea     r8, asc_180012E70; "\n"
0x18000653c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006541  xor     eax, eax
0x180006543  mov     rcx, [rsp+278h+var_38]
0x18000654b  xor     rcx, rsp; StackCookie
0x18000654e  call    __security_check_cookie
0x180006553  mov     rbx, [rsp+278h+arg_18]
0x18000655b  add     rsp, 250h
0x180006562  pop     r15
0x180006564  pop     r14
0x180006566  pop     rdi
0x180006567  pop     rsi
0x180006568  pop     rbp
0x180006569  retn
```
