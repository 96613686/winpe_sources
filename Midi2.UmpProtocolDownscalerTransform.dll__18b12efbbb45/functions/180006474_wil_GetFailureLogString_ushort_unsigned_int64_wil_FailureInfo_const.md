# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006474`
- end: `0x18000672a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003e68`
- `0x1800040d8`
- `0x180006f40`
- `0x180009bc0`

## callees

- `0x180002e70`
- `0x180003a20`
- `0x180006474`
- `0x180007240`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006627`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006627`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800065a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800065a6`

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
          v7 = (const char *)&word_1800152BA;
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
0x180006474  mov     [rsp+arg_18], rbx
0x180006479  push    rbp
0x18000647a  push    rsi
0x18000647b  push    rdi
0x18000647c  push    r14
0x18000647e  push    r15
0x180006480  sub     rsp, 250h
0x180006487  mov     rax, cs:__security_cookie
0x18000648e  xor     rax, rsp
0x180006491  mov     [rsp+278h+var_38], rax
0x180006499  mov     rbx, r8
0x18000649c  mov     rsi, rdx
0x18000649f  mov     r14, rcx
0x1800064a2  xor     r15d, r15d
0x1800064a5  test    rdx, rdx
0x1800064a8  jz      loc_180006701
0x1800064ae  test    rcx, rcx
0x1800064b1  jz      loc_180006701
0x1800064b7  mov     [rcx], r15w
0x1800064bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800064c2  test    rax, rax
0x1800064c5  jz      short loc_1800064E8
0x1800064c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800064ce  jz      short loc_1800064E8
0x1800064d0  mov     r8, rdx
0x1800064d3  mov     rdx, rcx
0x1800064d6  mov     rcx, rbx
0x1800064d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064de  cmp     [r14], r15w
0x1800064e2  jnz     loc_180006701
0x1800064e8  mov     ecx, [rbx]
0x1800064ea  mov     bpl, 8
0x1800064ed  test    ecx, ecx
0x1800064ef  jz      short loc_18000653A
0x1800064f1  sub     ecx, 1
0x1800064f4  jz      short loc_180006522
0x1800064f6  sub     ecx, 1
0x1800064f9  jz      short loc_180006512
0x1800064fb  cmp     ecx, 1
0x1800064fe  jz      short loc_180006509
0x180006500  lea     rdi, word_1800152BA
0x180006507  jmp     short loc_180006541
0x180006509  lea     rdi, aFailfast; "FailFast"
0x180006510  jmp     short loc_180006541
0x180006512  lea     rax, aLoghr; "LogHr"
0x180006519  lea     rdi, aLognt; "LogNt"
0x180006520  jmp     short loc_180006530
0x180006522  lea     rax, aReturnhr; "ReturnHr"
0x180006529  lea     rdi, aReturnnt; "ReturnNt"
0x180006530  test    [rbx+4], bpl
0x180006534  cmovz   rdi, rax
0x180006538  jmp     short loc_180006541
0x18000653a  lea     rdi, aException; "Exception"
0x180006541  xor     edx, edx; Val
0x180006543  mov     r8d, 200h; Size
0x180006549  lea     rcx, [rsp+278h+Buffer]; void *
0x18000654e  call    memset_0
0x180006553  test    [rbx+4], bpl
0x180006557  jz      short loc_18000657C
0x180006559  mov     ebp, [rbx+0Ch]
0x18000655c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006563  test    rax, rax
0x180006566  jz      short loc_1800065AC
0x180006568  mov     r8d, 100h
0x18000656e  lea     rdx, [rsp+278h+Buffer]
0x180006573  mov     ecx, ebp
0x180006575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000657a  jmp     short loc_1800065AC
0x18000657c  mov     ebp, [rbx+8]
0x18000657f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006584  mov     [rsp+278h+nSize], 100h; nSize
0x18000658c  lea     rax, [rsp+278h+Buffer]
0x180006591  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006596  mov     r9d, 400h; dwLanguageId
0x18000659c  mov     r8d, ebp; dwMessageId
0x18000659f  xor     edx, edx; lpSource
0x1800065a1  mov     ecx, 1200h; dwFlags
0x1800065a6  call    cs:__imp_FormatMessageW
0x1800065ac  lea     rsi, [r14+rsi*2]
0x1800065b0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800065b4  mov     rax, [rbx+88h]
0x1800065bb  mov     rcx, [rbx+80h]
0x1800065c2  mov     rdx, rsi; unsigned __int16 *
0x1800065c5  test    r9, r9
0x1800065c8  jz      short loc_1800065EC
0x1800065ca  mov     [rsp+278h+Arguments], rax
0x1800065cf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800065d4  mov     eax, [rbx+40h]
0x1800065d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800065db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800065e2  mov     rcx, r14; this
0x1800065e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800065ea  jmp     short loc_180006603
0x1800065ec  mov     [rsp+278h+lpBuffer], rax
0x1800065f1  mov     r9, rcx; unsigned __int16 *
0x1800065f4  lea     r8, aHsP; "%hs!%p: "
0x1800065fb  mov     rcx, r14; this
0x1800065fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006603  mov     r14, rax
0x180006606  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000660d  test    r9, r9
0x180006610  jz      short loc_180006627
0x180006612  lea     r8, aCallerP; "(caller: %p) "
0x180006619  mov     rdx, rsi; unsigned __int16 *
0x18000661c  mov     rcx, rax; this
0x18000661f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006624  mov     r14, rax
0x180006627  call    cs:__imp_GetCurrentThreadId
0x18000662d  lea     rcx, [rsp+278h+Buffer]
0x180006632  mov     [rsp+278h+var_240], rcx
0x180006637  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000663b  mov     [rsp+278h+nSize], eax
0x18000663f  mov     eax, [rbx+44h]
0x180006642  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006646  mov     r9, rdi; unsigned __int16 *
0x180006649  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006650  mov     rdx, rsi; unsigned __int16 *
0x180006653  mov     rcx, r14; this
0x180006656  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000665b  cmp     [rbx+18h], r15
0x18000665f  jnz     short loc_180006671
0x180006661  cmp     [rbx+48h], r15
0x180006665  jnz     short loc_180006671
0x180006667  cmp     [rbx+30h], r15
0x18000666b  jz      loc_180006701
0x180006671  lea     r8, asc_1800153C8; "    "
0x180006678  mov     rdx, rsi; unsigned __int16 *
0x18000667b  mov     rcx, rax; this
0x18000667e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006683  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006687  test    r9, r9
0x18000668a  jz      short loc_18000669E
0x18000668c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006693  mov     rdx, rsi; unsigned __int16 *
0x180006696  mov     rcx, rax; this
0x180006699  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000669e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800066a2  test    r9, r9
0x1800066a5  jz      short loc_1800066B9
0x1800066a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800066ae  mov     rdx, rsi; unsigned __int16 *
0x1800066b1  mov     rcx, rax; this
0x1800066b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066b9  mov     rcx, [rbx+28h]
0x1800066bd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800066c1  mov     rdx, rsi; unsigned __int16 *
0x1800066c4  test    rcx, rcx
0x1800066c7  jz      short loc_1800066DF
0x1800066c9  mov     [rsp+278h+lpBuffer], rcx
0x1800066ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800066d5  mov     rcx, rax; this
0x1800066d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066dd  jmp     short loc_180006701
0x1800066df  mov     rcx, rax; this
0x1800066e2  test    r9, r9
0x1800066e5  jz      short loc_1800066F5
0x1800066e7  lea     r8, aHs; "[%hs]\n"
0x1800066ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066f3  jmp     short loc_180006701
0x1800066f5  lea     r8, asc_180015440; "\n"
0x1800066fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006701  xor     eax, eax
0x180006703  mov     rcx, [rsp+278h+var_38]
0x18000670b  xor     rcx, rsp; StackCookie
0x18000670e  call    __security_check_cookie
0x180006713  mov     rbx, [rsp+278h+arg_18]
0x18000671b  add     rsp, 250h
0x180006722  pop     r15
0x180006724  pop     r14
0x180006726  pop     rdi
0x180006727  pop     rsi
0x180006728  pop     rbp
0x180006729  retn
```
