# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400063d4`
- end: `0x14000668a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002abc`
- `0x140007960`
- `0x14000c470`

## callees

- `0x1400022d3`
- `0x1400063d4`
- `0x140007c60`
- `0x140015aa0`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006587`
- `KERNEL32!GetCurrentThreadId` at `0x140006587`
- `KERNEL32!FormatMessageW` at `0x140006506`
- `KERNEL32!FormatMessageW` at `0x140006506`

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
          v7 = (const char *)&word_14001AD4A;
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
0x1400063d4  mov     [rsp+arg_18], rbx
0x1400063d9  push    rbp
0x1400063da  push    rsi
0x1400063db  push    rdi
0x1400063dc  push    r14
0x1400063de  push    r15
0x1400063e0  sub     rsp, 250h
0x1400063e7  mov     rax, cs:__security_cookie
0x1400063ee  xor     rax, rsp
0x1400063f1  mov     [rsp+278h+var_38], rax
0x1400063f9  mov     rbx, r8
0x1400063fc  mov     rsi, rdx
0x1400063ff  mov     r14, rcx
0x140006402  xor     r15d, r15d
0x140006405  test    rdx, rdx
0x140006408  jz      loc_140006661
0x14000640e  test    rcx, rcx
0x140006411  jz      loc_140006661
0x140006417  mov     [rcx], r15w
0x14000641b  mov     rax, cs:g_pfnResultLoggingCallback
0x140006422  test    rax, rax
0x140006425  jz      short loc_140006448
0x140006427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000642e  jz      short loc_140006448
0x140006430  mov     r8, rdx
0x140006433  mov     rdx, rcx
0x140006436  mov     rcx, rbx
0x140006439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000643e  cmp     [r14], r15w
0x140006442  jnz     loc_140006661
0x140006448  mov     ecx, [rbx]
0x14000644a  mov     bpl, 8
0x14000644d  test    ecx, ecx
0x14000644f  jz      short loc_14000649A
0x140006451  sub     ecx, 1
0x140006454  jz      short loc_140006482
0x140006456  sub     ecx, 1
0x140006459  jz      short loc_140006472
0x14000645b  cmp     ecx, 1
0x14000645e  jz      short loc_140006469
0x140006460  lea     rdi, word_14001AD4A
0x140006467  jmp     short loc_1400064A1
0x140006469  lea     rdi, aFailfast; "FailFast"
0x140006470  jmp     short loc_1400064A1
0x140006472  lea     rax, aLoghr; "LogHr"
0x140006479  lea     rdi, aLognt; "LogNt"
0x140006480  jmp     short loc_140006490
0x140006482  lea     rax, aReturnhr; "ReturnHr"
0x140006489  lea     rdi, aReturnnt; "ReturnNt"
0x140006490  test    [rbx+4], bpl
0x140006494  cmovz   rdi, rax
0x140006498  jmp     short loc_1400064A1
0x14000649a  lea     rdi, aException; "Exception"
0x1400064a1  xor     edx, edx; Val
0x1400064a3  mov     r8d, 200h; Size
0x1400064a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400064ae  call    memset_0
0x1400064b3  test    [rbx+4], bpl
0x1400064b7  jz      short loc_1400064DC
0x1400064b9  mov     ebp, [rbx+0Ch]
0x1400064bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400064c3  test    rax, rax
0x1400064c6  jz      short loc_14000650C
0x1400064c8  mov     r8d, 100h
0x1400064ce  lea     rdx, [rsp+278h+Buffer]
0x1400064d3  mov     ecx, ebp
0x1400064d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064da  jmp     short loc_14000650C
0x1400064dc  mov     ebp, [rbx+8]
0x1400064df  mov     [rsp+278h+Arguments], r15; Arguments
0x1400064e4  mov     [rsp+278h+nSize], 100h; nSize
0x1400064ec  lea     rax, [rsp+278h+Buffer]
0x1400064f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400064f6  mov     r9d, 400h; dwLanguageId
0x1400064fc  mov     r8d, ebp; dwMessageId
0x1400064ff  xor     edx, edx; lpSource
0x140006501  mov     ecx, 1200h; dwFlags
0x140006506  call    cs:__imp_FormatMessageW
0x14000650c  lea     rsi, [r14+rsi*2]
0x140006510  mov     r9, [rbx+38h]; unsigned __int16 *
0x140006514  mov     rax, [rbx+88h]
0x14000651b  mov     rcx, [rbx+80h]
0x140006522  mov     rdx, rsi; unsigned __int16 *
0x140006525  test    r9, r9
0x140006528  jz      short loc_14000654C
0x14000652a  mov     [rsp+278h+Arguments], rax
0x14000652f  mov     qword ptr [rsp+278h+nSize], rcx
0x140006534  mov     eax, [rbx+40h]
0x140006537  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000653b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140006542  mov     rcx, r14; this
0x140006545  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000654a  jmp     short loc_140006563
0x14000654c  mov     [rsp+278h+lpBuffer], rax
0x140006551  mov     r9, rcx; unsigned __int16 *
0x140006554  lea     r8, aHsP; "%hs!%p: "
0x14000655b  mov     rcx, r14; this
0x14000655e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006563  mov     r14, rax
0x140006566  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000656d  test    r9, r9
0x140006570  jz      short loc_140006587
0x140006572  lea     r8, aCallerP; "(caller: %p) "
0x140006579  mov     rdx, rsi; unsigned __int16 *
0x14000657c  mov     rcx, rax; this
0x14000657f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006584  mov     r14, rax
0x140006587  call    cs:__imp_GetCurrentThreadId
0x14000658d  lea     rcx, [rsp+278h+Buffer]
0x140006592  mov     [rsp+278h+var_240], rcx
0x140006597  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000659b  mov     [rsp+278h+nSize], eax
0x14000659f  mov     eax, [rbx+44h]
0x1400065a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400065a6  mov     r9, rdi; unsigned __int16 *
0x1400065a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400065b0  mov     rdx, rsi; unsigned __int16 *
0x1400065b3  mov     rcx, r14; this
0x1400065b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400065bb  cmp     [rbx+18h], r15
0x1400065bf  jnz     short loc_1400065D1
0x1400065c1  cmp     [rbx+48h], r15
0x1400065c5  jnz     short loc_1400065D1
0x1400065c7  cmp     [rbx+30h], r15
0x1400065cb  jz      loc_140006661
0x1400065d1  lea     r8, asc_14001AE38; "    "
0x1400065d8  mov     rdx, rsi; unsigned __int16 *
0x1400065db  mov     rcx, rax; this
0x1400065de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400065e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400065e7  test    r9, r9
0x1400065ea  jz      short loc_1400065FE
0x1400065ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400065f3  mov     rdx, rsi; unsigned __int16 *
0x1400065f6  mov     rcx, rax; this
0x1400065f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400065fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x140006602  test    r9, r9
0x140006605  jz      short loc_140006619
0x140006607  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000660e  mov     rdx, rsi; unsigned __int16 *
0x140006611  mov     rcx, rax; this
0x140006614  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006619  mov     rcx, [rbx+28h]
0x14000661d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140006621  mov     rdx, rsi; unsigned __int16 *
0x140006624  test    rcx, rcx
0x140006627  jz      short loc_14000663F
0x140006629  mov     [rsp+278h+lpBuffer], rcx
0x14000662e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140006635  mov     rcx, rax; this
0x140006638  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000663d  jmp     short loc_140006661
0x14000663f  mov     rcx, rax; this
0x140006642  test    r9, r9
0x140006645  jz      short loc_140006655
0x140006647  lea     r8, aHs; "[%hs]\n"
0x14000664e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006653  jmp     short loc_140006661
0x140006655  lea     r8, asc_14001AEB0; "\n"
0x14000665c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140006661  xor     eax, eax
0x140006663  mov     rcx, [rsp+278h+var_38]
0x14000666b  xor     rcx, rsp; StackCookie
0x14000666e  call    __security_check_cookie
0x140006673  mov     rbx, [rsp+278h+arg_18]
0x14000667b  add     rsp, 250h
0x140006682  pop     r15
0x140006684  pop     r14
0x140006686  pop     rdi
0x140006687  pop     rsi
0x140006688  pop     rbp
0x140006689  retn
```
