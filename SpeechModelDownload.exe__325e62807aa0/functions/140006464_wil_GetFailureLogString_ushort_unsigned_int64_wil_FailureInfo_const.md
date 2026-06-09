# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140006464`
- end: `0x14000671a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140004124`
- `0x14000438c`
- `0x140006fb0`
- `0x1400094e0`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x140006464`
- `0x1400072b0`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006617`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006596`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140006596`

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
          v7 = (const char *)&word_14001EFBE;
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
0x140006464  mov     [rsp+arg_18], rbx
0x140006469  push    rbp
0x14000646a  push    rsi
0x14000646b  push    rdi
0x14000646c  push    r14
0x14000646e  push    r15
0x140006470  sub     rsp, 250h
0x140006477  mov     rax, cs:__security_cookie
0x14000647e  xor     rax, rsp
0x140006481  mov     [rsp+278h+var_38], rax
0x140006489  mov     rbx, r8
0x14000648c  mov     rsi, rdx
0x14000648f  mov     r14, rcx
0x140006492  xor     r15d, r15d
0x140006495  test    rdx, rdx
0x140006498  jz      loc_1400066F1
0x14000649e  test    rcx, rcx
0x1400064a1  jz      loc_1400066F1
0x1400064a7  mov     [rcx], r15w
0x1400064ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1400064b2  test    rax, rax
0x1400064b5  jz      short loc_1400064D8
0x1400064b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400064be  jz      short loc_1400064D8
0x1400064c0  mov     r8, rdx
0x1400064c3  mov     rdx, rcx
0x1400064c6  mov     rcx, rbx
0x1400064c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064ce  cmp     [r14], r15w
0x1400064d2  jnz     loc_1400066F1
0x1400064d8  mov     ecx, [rbx]
0x1400064da  mov     bpl, 8
0x1400064dd  test    ecx, ecx
0x1400064df  jz      short loc_14000652A
0x1400064e1  sub     ecx, 1
0x1400064e4  jz      short loc_140006512
0x1400064e6  sub     ecx, 1
0x1400064e9  jz      short loc_140006502
0x1400064eb  cmp     ecx, 1
0x1400064ee  jz      short loc_1400064F9
0x1400064f0  lea     rdi, word_14001EFBE
0x1400064f7  jmp     short loc_140006531
0x1400064f9  lea     rdi, aFailfast; "FailFast"
0x140006500  jmp     short loc_140006531
0x140006502  lea     rax, aLoghr; "LogHr"
0x140006509  lea     rdi, aLognt; "LogNt"
0x140006510  jmp     short loc_140006520
0x140006512  lea     rax, aReturnhr; "ReturnHr"
0x140006519  lea     rdi, aReturnnt; "ReturnNt"
0x140006520  test    [rbx+4], bpl
0x140006524  cmovz   rdi, rax
0x140006528  jmp     short loc_140006531
0x14000652a  lea     rdi, aException; "Exception"
0x140006531  xor     edx, edx; Val
0x140006533  mov     r8d, 200h; Size
0x140006539  lea     rcx, [rsp+278h+Buffer]; void *
0x14000653e  call    memset_0
0x140006543  test    [rbx+4], bpl
0x140006547  jz      short loc_14000656C
0x140006549  mov     ebp, [rbx+0Ch]
0x14000654c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140006553  test    rax, rax
0x140006556  jz      short loc_14000659C
0x140006558  mov     r8d, 100h
0x14000655e  lea     rdx, [rsp+278h+Buffer]
0x140006563  mov     ecx, ebp
0x140006565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000656a  jmp     short loc_14000659C
0x14000656c  mov     ebp, [rbx+8]
0x14000656f  mov     [rsp+278h+Arguments], r15; Arguments
0x140006574  mov     [rsp+278h+nSize], 100h; nSize
0x14000657c  lea     rax, [rsp+278h+Buffer]
0x140006581  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140006586  mov     r9d, 400h; dwLanguageId
0x14000658c  mov     r8d, ebp; dwMessageId
0x14000658f  xor     edx, edx; lpSource
0x140006591  mov     ecx, 1200h; dwFlags
0x140006596  call    cs:__imp_FormatMessageW
0x14000659c  lea     rsi, [r14+rsi*2]
0x1400065a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400065a4  mov     rax, [rbx+88h]
0x1400065ab  mov     rcx, [rbx+80h]
0x1400065b2  mov     rdx, rsi; unsigned __int16 *
0x1400065b5  test    r9, r9
0x1400065b8  jz      short loc_1400065DC
0x1400065ba  mov     [rsp+278h+Arguments], rax
0x1400065bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1400065c4  mov     eax, [rbx+40h]
0x1400065c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400065cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400065d2  mov     rcx, r14; this
0x1400065d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400065da  jmp     short loc_1400065F3
0x1400065dc  mov     [rsp+278h+lpBuffer], rax
0x1400065e1  mov     r9, rcx; unsigned __int16 *
0x1400065e4  lea     r8, aHsP; "%hs!%p: "
0x1400065eb  mov     rcx, r14; this
0x1400065ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400065f3  mov     r14, rax
0x1400065f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400065fd  test    r9, r9
0x140006600  jz      short loc_140006617
0x140006602  lea     r8, aCallerP; "(caller: %p) "
0x140006609  mov     rdx, rsi; unsigned __int16 *
0x14000660c  mov     rcx, rax; this
0x14000660f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006614  mov     r14, rax
0x140006617  call    cs:__imp_GetCurrentThreadId
0x14000661d  lea     rcx, [rsp+278h+Buffer]
0x140006622  mov     [rsp+278h+var_240], rcx
0x140006627  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000662b  mov     [rsp+278h+nSize], eax
0x14000662f  mov     eax, [rbx+44h]
0x140006632  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140006636  mov     r9, rdi; unsigned __int16 *
0x140006639  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140006640  mov     rdx, rsi; unsigned __int16 *
0x140006643  mov     rcx, r14; this
0x140006646  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000664b  cmp     [rbx+18h], r15
0x14000664f  jnz     short loc_140006661
0x140006651  cmp     [rbx+48h], r15
0x140006655  jnz     short loc_140006661
0x140006657  cmp     [rbx+30h], r15
0x14000665b  jz      loc_1400066F1
0x140006661  lea     r8, asc_14001F120; "    "
0x140006668  mov     rdx, rsi; unsigned __int16 *
0x14000666b  mov     rcx, rax; this
0x14000666e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006673  mov     r9, [rbx+18h]; unsigned __int16 *
0x140006677  test    r9, r9
0x14000667a  jz      short loc_14000668E
0x14000667c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140006683  mov     rdx, rsi; unsigned __int16 *
0x140006686  mov     rcx, rax; this
0x140006689  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000668e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140006692  test    r9, r9
0x140006695  jz      short loc_1400066A9
0x140006697  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000669e  mov     rdx, rsi; unsigned __int16 *
0x1400066a1  mov     rcx, rax; this
0x1400066a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400066a9  mov     rcx, [rbx+28h]
0x1400066ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400066b1  mov     rdx, rsi; unsigned __int16 *
0x1400066b4  test    rcx, rcx
0x1400066b7  jz      short loc_1400066CF
0x1400066b9  mov     [rsp+278h+lpBuffer], rcx
0x1400066be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400066c5  mov     rcx, rax; this
0x1400066c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400066cd  jmp     short loc_1400066F1
0x1400066cf  mov     rcx, rax; this
0x1400066d2  test    r9, r9
0x1400066d5  jz      short loc_1400066E5
0x1400066d7  lea     r8, aHs; "[%hs]\n"
0x1400066de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400066e3  jmp     short loc_1400066F1
0x1400066e5  lea     r8, asc_14001F198; "\n"
0x1400066ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400066f1  xor     eax, eax
0x1400066f3  mov     rcx, [rsp+278h+var_38]
0x1400066fb  xor     rcx, rsp; StackCookie
0x1400066fe  call    __security_check_cookie
0x140006703  mov     rbx, [rsp+278h+arg_18]
0x14000670b  add     rsp, 250h
0x140006712  pop     r15
0x140006714  pop     r14
0x140006716  pop     rdi
0x140006717  pop     rsi
0x140006718  pop     rbp
0x140006719  retn
```
