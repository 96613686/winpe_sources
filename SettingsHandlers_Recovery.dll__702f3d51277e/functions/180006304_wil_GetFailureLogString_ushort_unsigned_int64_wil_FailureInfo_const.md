# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006304`
- end: `0x1800065ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b3c`
- `0x180003dbc`
- `0x180006d98`
- `0x18000a6c0`
- `0x1800242c4`
- `0x18002950c`
- `0x180029640`

## callees

- `0x180002350`
- `0x180002ed4`
- `0x180006304`
- `0x180007098`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006436`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006436`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
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
          v7 = (const char *)&word_18003240A;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180006304  mov     [rsp+arg_18], rbx
0x180006309  push    rbp
0x18000630a  push    rsi
0x18000630b  push    rdi
0x18000630c  push    r14
0x18000630e  push    r15
0x180006310  sub     rsp, 250h
0x180006317  mov     rax, cs:__security_cookie
0x18000631e  xor     rax, rsp
0x180006321  mov     [rsp+278h+var_38], rax
0x180006329  mov     rbx, r8
0x18000632c  mov     rsi, rdx
0x18000632f  mov     r14, rcx
0x180006332  xor     r15d, r15d
0x180006335  test    rdx, rdx
0x180006338  jz      loc_180006591
0x18000633e  test    rcx, rcx
0x180006341  jz      loc_180006591
0x180006347  mov     [rcx], r15w
0x18000634b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006352  test    rax, rax
0x180006355  jz      short loc_180006378
0x180006357  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000635e  jz      short loc_180006378
0x180006360  mov     r8, rdx
0x180006363  mov     rdx, rcx
0x180006366  mov     rcx, rbx
0x180006369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636e  cmp     [r14], r15w
0x180006372  jnz     loc_180006591
0x180006378  mov     ecx, [rbx]
0x18000637a  mov     bpl, 8
0x18000637d  test    ecx, ecx
0x18000637f  jz      short loc_1800063CA
0x180006381  sub     ecx, 1
0x180006384  jz      short loc_1800063B2
0x180006386  sub     ecx, 1
0x180006389  jz      short loc_1800063A2
0x18000638b  cmp     ecx, 1
0x18000638e  jz      short loc_180006399
0x180006390  lea     rdi, word_18003240A
0x180006397  jmp     short loc_1800063D1
0x180006399  lea     rdi, aFailfast; "FailFast"
0x1800063a0  jmp     short loc_1800063D1
0x1800063a2  lea     rax, aLoghr; "LogHr"
0x1800063a9  lea     rdi, aLognt; "LogNt"
0x1800063b0  jmp     short loc_1800063C0
0x1800063b2  lea     rax, aReturnhr; "ReturnHr"
0x1800063b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800063c0  test    [rbx+4], bpl
0x1800063c4  cmovz   rdi, rax
0x1800063c8  jmp     short loc_1800063D1
0x1800063ca  lea     rdi, aException; "Exception"
0x1800063d1  xor     edx, edx; Val
0x1800063d3  mov     r8d, 200h; Size
0x1800063d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800063de  call    memset_0
0x1800063e3  test    [rbx+4], bpl
0x1800063e7  jz      short loc_18000640C
0x1800063e9  mov     ebp, [rbx+0Ch]
0x1800063ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800063f3  test    rax, rax
0x1800063f6  jz      short loc_18000643C
0x1800063f8  mov     r8d, 100h
0x1800063fe  lea     rdx, [rsp+278h+Buffer]
0x180006403  mov     ecx, ebp
0x180006405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000640a  jmp     short loc_18000643C
0x18000640c  mov     ebp, [rbx+8]
0x18000640f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006414  mov     [rsp+278h+nSize], 100h; nSize
0x18000641c  lea     rax, [rsp+278h+Buffer]
0x180006421  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006426  mov     r9d, 400h; dwLanguageId
0x18000642c  mov     r8d, ebp; dwMessageId
0x18000642f  xor     edx, edx; lpSource
0x180006431  mov     ecx, 1200h; dwFlags
0x180006436  call    cs:__imp_FormatMessageW
0x18000643c  lea     rsi, [r14+rsi*2]
0x180006440  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006444  mov     rax, [rbx+88h]
0x18000644b  mov     rcx, [rbx+80h]
0x180006452  mov     rdx, rsi; unsigned __int16 *
0x180006455  test    r9, r9
0x180006458  jz      short loc_18000647C
0x18000645a  mov     [rsp+278h+Arguments], rax
0x18000645f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006464  mov     eax, [rbx+40h]
0x180006467  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000646b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006472  mov     rcx, r14; this
0x180006475  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000647a  jmp     short loc_180006493
0x18000647c  mov     [rsp+278h+lpBuffer], rax
0x180006481  mov     r9, rcx; unsigned __int16 *
0x180006484  lea     r8, aHsP; "%hs!%p: "
0x18000648b  mov     rcx, r14; this
0x18000648e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006493  mov     r14, rax
0x180006496  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000649d  test    r9, r9
0x1800064a0  jz      short loc_1800064B7
0x1800064a2  lea     r8, aCallerP; "(caller: %p) "
0x1800064a9  mov     rdx, rsi; unsigned __int16 *
0x1800064ac  mov     rcx, rax; this
0x1800064af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800064b4  mov     r14, rax
0x1800064b7  call    cs:__imp_GetCurrentThreadId
0x1800064bd  lea     rcx, [rsp+278h+Buffer]
0x1800064c2  mov     [rsp+278h+var_240], rcx
0x1800064c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800064cb  mov     [rsp+278h+nSize], eax
0x1800064cf  mov     eax, [rbx+44h]
0x1800064d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800064d6  mov     r9, rdi; unsigned __int16 *
0x1800064d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800064e0  mov     rdx, rsi; unsigned __int16 *
0x1800064e3  mov     rcx, r14; this
0x1800064e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800064eb  cmp     [rbx+18h], r15
0x1800064ef  jnz     short loc_180006501
0x1800064f1  cmp     [rbx+48h], r15
0x1800064f5  jnz     short loc_180006501
0x1800064f7  cmp     [rbx+30h], r15
0x1800064fb  jz      loc_180006591
0x180006501  lea     r8, asc_1800324F8; "    "
0x180006508  mov     rdx, rsi; unsigned __int16 *
0x18000650b  mov     rcx, rax; this
0x18000650e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006513  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006517  test    r9, r9
0x18000651a  jz      short loc_18000652E
0x18000651c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006523  mov     rdx, rsi; unsigned __int16 *
0x180006526  mov     rcx, rax; this
0x180006529  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000652e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006532  test    r9, r9
0x180006535  jz      short loc_180006549
0x180006537  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000653e  mov     rdx, rsi; unsigned __int16 *
0x180006541  mov     rcx, rax; this
0x180006544  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006549  mov     rcx, [rbx+28h]
0x18000654d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006551  mov     rdx, rsi; unsigned __int16 *
0x180006554  test    rcx, rcx
0x180006557  jz      short loc_18000656F
0x180006559  mov     [rsp+278h+lpBuffer], rcx
0x18000655e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006565  mov     rcx, rax; this
0x180006568  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000656d  jmp     short loc_180006591
0x18000656f  mov     rcx, rax; this
0x180006572  test    r9, r9
0x180006575  jz      short loc_180006585
0x180006577  lea     r8, aHs; "[%hs]\n"
0x18000657e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006583  jmp     short loc_180006591
0x180006585  lea     r8, asc_180032570; "\n"
0x18000658c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006591  xor     eax, eax
0x180006593  mov     rcx, [rsp+278h+var_38]
0x18000659b  xor     rcx, rsp; StackCookie
0x18000659e  call    __security_check_cookie
0x1800065a3  mov     rbx, [rsp+278h+arg_18]
0x1800065ab  add     rsp, 250h
0x1800065b2  pop     r15
0x1800065b4  pop     r14
0x1800065b6  pop     rdi
0x1800065b7  pop     rsi
0x1800065b8  pop     rbp
0x1800065b9  retn
```
