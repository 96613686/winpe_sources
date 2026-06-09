# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800064b4`
- end: `0x18000676a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180003214`
- `0x180007120`
- `0x18000af80`

## callees

- `0x180001ed0`
- `0x180002878`
- `0x1800064b4`
- `0x180007420`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006667`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800065e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800065e6`

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
          v7 = (const char *)&word_180012E8A;
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
0x1800064b4  mov     [rsp+arg_18], rbx
0x1800064b9  push    rbp
0x1800064ba  push    rsi
0x1800064bb  push    rdi
0x1800064bc  push    r14
0x1800064be  push    r15
0x1800064c0  sub     rsp, 250h
0x1800064c7  mov     rax, cs:__security_cookie
0x1800064ce  xor     rax, rsp
0x1800064d1  mov     [rsp+278h+var_38], rax
0x1800064d9  mov     rbx, r8
0x1800064dc  mov     rsi, rdx
0x1800064df  mov     r14, rcx
0x1800064e2  xor     r15d, r15d
0x1800064e5  test    rdx, rdx
0x1800064e8  jz      loc_180006741
0x1800064ee  test    rcx, rcx
0x1800064f1  jz      loc_180006741
0x1800064f7  mov     [rcx], r15w
0x1800064fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006502  test    rax, rax
0x180006505  jz      short loc_180006528
0x180006507  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000650e  jz      short loc_180006528
0x180006510  mov     r8, rdx
0x180006513  mov     rdx, rcx
0x180006516  mov     rcx, rbx
0x180006519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000651e  cmp     [r14], r15w
0x180006522  jnz     loc_180006741
0x180006528  mov     ecx, [rbx]
0x18000652a  mov     bpl, 8
0x18000652d  test    ecx, ecx
0x18000652f  jz      short loc_18000657A
0x180006531  sub     ecx, 1
0x180006534  jz      short loc_180006562
0x180006536  sub     ecx, 1
0x180006539  jz      short loc_180006552
0x18000653b  cmp     ecx, 1
0x18000653e  jz      short loc_180006549
0x180006540  lea     rdi, word_180012E8A
0x180006547  jmp     short loc_180006581
0x180006549  lea     rdi, aFailfast; "FailFast"
0x180006550  jmp     short loc_180006581
0x180006552  lea     rax, aLoghr; "LogHr"
0x180006559  lea     rdi, aLognt; "LogNt"
0x180006560  jmp     short loc_180006570
0x180006562  lea     rax, aReturnhr; "ReturnHr"
0x180006569  lea     rdi, aReturnnt; "ReturnNt"
0x180006570  test    [rbx+4], bpl
0x180006574  cmovz   rdi, rax
0x180006578  jmp     short loc_180006581
0x18000657a  lea     rdi, aException; "Exception"
0x180006581  xor     edx, edx; Val
0x180006583  mov     r8d, 200h; Size
0x180006589  lea     rcx, [rsp+278h+Buffer]; void *
0x18000658e  call    memset_0
0x180006593  test    [rbx+4], bpl
0x180006597  jz      short loc_1800065BC
0x180006599  mov     ebp, [rbx+0Ch]
0x18000659c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800065a3  test    rax, rax
0x1800065a6  jz      short loc_1800065EC
0x1800065a8  mov     r8d, 100h
0x1800065ae  lea     rdx, [rsp+278h+Buffer]
0x1800065b3  mov     ecx, ebp
0x1800065b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ba  jmp     short loc_1800065EC
0x1800065bc  mov     ebp, [rbx+8]
0x1800065bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800065c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800065cc  lea     rax, [rsp+278h+Buffer]
0x1800065d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800065d6  mov     r9d, 400h; dwLanguageId
0x1800065dc  mov     r8d, ebp; dwMessageId
0x1800065df  xor     edx, edx; lpSource
0x1800065e1  mov     ecx, 1200h; dwFlags
0x1800065e6  call    cs:__imp_FormatMessageW
0x1800065ec  lea     rsi, [r14+rsi*2]
0x1800065f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800065f4  mov     rax, [rbx+88h]
0x1800065fb  mov     rcx, [rbx+80h]
0x180006602  mov     rdx, rsi; unsigned __int16 *
0x180006605  test    r9, r9
0x180006608  jz      short loc_18000662C
0x18000660a  mov     [rsp+278h+Arguments], rax
0x18000660f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006614  mov     eax, [rbx+40h]
0x180006617  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000661b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006622  mov     rcx, r14; this
0x180006625  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000662a  jmp     short loc_180006643
0x18000662c  mov     [rsp+278h+lpBuffer], rax
0x180006631  mov     r9, rcx; unsigned __int16 *
0x180006634  lea     r8, aHsP; "%hs!%p: "
0x18000663b  mov     rcx, r14; this
0x18000663e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006643  mov     r14, rax
0x180006646  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000664d  test    r9, r9
0x180006650  jz      short loc_180006667
0x180006652  lea     r8, aCallerP; "(caller: %p) "
0x180006659  mov     rdx, rsi; unsigned __int16 *
0x18000665c  mov     rcx, rax; this
0x18000665f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006664  mov     r14, rax
0x180006667  call    cs:__imp_GetCurrentThreadId
0x18000666d  lea     rcx, [rsp+278h+Buffer]
0x180006672  mov     [rsp+278h+var_240], rcx
0x180006677  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000667b  mov     [rsp+278h+nSize], eax
0x18000667f  mov     eax, [rbx+44h]
0x180006682  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006686  mov     r9, rdi; unsigned __int16 *
0x180006689  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006690  mov     rdx, rsi; unsigned __int16 *
0x180006693  mov     rcx, r14; this
0x180006696  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000669b  cmp     [rbx+18h], r15
0x18000669f  jnz     short loc_1800066B1
0x1800066a1  cmp     [rbx+48h], r15
0x1800066a5  jnz     short loc_1800066B1
0x1800066a7  cmp     [rbx+30h], r15
0x1800066ab  jz      loc_180006741
0x1800066b1  lea     r8, asc_180012F78; "    "
0x1800066b8  mov     rdx, rsi; unsigned __int16 *
0x1800066bb  mov     rcx, rax; this
0x1800066be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800066c7  test    r9, r9
0x1800066ca  jz      short loc_1800066DE
0x1800066cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800066d3  mov     rdx, rsi; unsigned __int16 *
0x1800066d6  mov     rcx, rax; this
0x1800066d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800066e2  test    r9, r9
0x1800066e5  jz      short loc_1800066F9
0x1800066e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800066ee  mov     rdx, rsi; unsigned __int16 *
0x1800066f1  mov     rcx, rax; this
0x1800066f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800066f9  mov     rcx, [rbx+28h]
0x1800066fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006701  mov     rdx, rsi; unsigned __int16 *
0x180006704  test    rcx, rcx
0x180006707  jz      short loc_18000671F
0x180006709  mov     [rsp+278h+lpBuffer], rcx
0x18000670e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006715  mov     rcx, rax; this
0x180006718  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000671d  jmp     short loc_180006741
0x18000671f  mov     rcx, rax; this
0x180006722  test    r9, r9
0x180006725  jz      short loc_180006735
0x180006727  lea     r8, aHs; "[%hs]\n"
0x18000672e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006733  jmp     short loc_180006741
0x180006735  lea     r8, asc_180012FF0; "\n"
0x18000673c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006741  xor     eax, eax
0x180006743  mov     rcx, [rsp+278h+var_38]
0x18000674b  xor     rcx, rsp; StackCookie
0x18000674e  call    __security_check_cookie
0x180006753  mov     rbx, [rsp+278h+arg_18]
0x18000675b  add     rsp, 250h
0x180006762  pop     r15
0x180006764  pop     r14
0x180006766  pop     rdi
0x180006767  pop     rsi
0x180006768  pop     rbp
0x180006769  retn
```
