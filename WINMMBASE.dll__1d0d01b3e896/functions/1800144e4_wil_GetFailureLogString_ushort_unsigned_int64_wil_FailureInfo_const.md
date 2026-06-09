# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800144e4`
- end: `0x18001479a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001334c`
- `0x180014e9c`
- `0x1800168a0`

## callees

- `0x1800106c0`
- `0x18001102a`
- `0x1800144e4`
- `0x1800151ac`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014697`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014616`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180014616`

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
          v7 = (const char *)&qword_180025898;
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
0x1800144e4  mov     [rsp+arg_18], rbx
0x1800144e9  push    rbp
0x1800144ea  push    rsi
0x1800144eb  push    rdi
0x1800144ec  push    r14
0x1800144ee  push    r15
0x1800144f0  sub     rsp, 250h
0x1800144f7  mov     rax, cs:__security_cookie
0x1800144fe  xor     rax, rsp
0x180014501  mov     [rsp+278h+var_38], rax
0x180014509  mov     rbx, r8
0x18001450c  mov     rsi, rdx
0x18001450f  mov     r14, rcx
0x180014512  xor     r15d, r15d
0x180014515  test    rdx, rdx
0x180014518  jz      loc_180014771
0x18001451e  test    rcx, rcx
0x180014521  jz      loc_180014771
0x180014527  mov     [rcx], r15w
0x18001452b  mov     rax, cs:g_pfnResultLoggingCallback
0x180014532  test    rax, rax
0x180014535  jz      short loc_180014558
0x180014537  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001453e  jz      short loc_180014558
0x180014540  mov     r8, rdx
0x180014543  mov     rdx, rcx
0x180014546  mov     rcx, rbx
0x180014549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001454e  cmp     [r14], r15w
0x180014552  jnz     loc_180014771
0x180014558  mov     ecx, [rbx]
0x18001455a  mov     bpl, 8
0x18001455d  test    ecx, ecx
0x18001455f  jz      short loc_1800145AA
0x180014561  sub     ecx, 1
0x180014564  jz      short loc_180014592
0x180014566  sub     ecx, 1
0x180014569  jz      short loc_180014582
0x18001456b  cmp     ecx, 1
0x18001456e  jz      short loc_180014579
0x180014570  lea     rdi, qword_180025898
0x180014577  jmp     short loc_1800145B1
0x180014579  lea     rdi, aFailfast; "FailFast"
0x180014580  jmp     short loc_1800145B1
0x180014582  lea     rax, aLoghr; "LogHr"
0x180014589  lea     rdi, aLognt; "LogNt"
0x180014590  jmp     short loc_1800145A0
0x180014592  lea     rax, aReturnhr; "ReturnHr"
0x180014599  lea     rdi, aReturnnt; "ReturnNt"
0x1800145a0  test    [rbx+4], bpl
0x1800145a4  cmovz   rdi, rax
0x1800145a8  jmp     short loc_1800145B1
0x1800145aa  lea     rdi, aException; "Exception"
0x1800145b1  xor     edx, edx; Val
0x1800145b3  mov     r8d, 200h; Size
0x1800145b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800145be  call    memset_0
0x1800145c3  test    [rbx+4], bpl
0x1800145c7  jz      short loc_1800145EC
0x1800145c9  mov     ebp, [rbx+0Ch]
0x1800145cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800145d3  test    rax, rax
0x1800145d6  jz      short loc_18001461C
0x1800145d8  mov     r8d, 100h
0x1800145de  lea     rdx, [rsp+278h+Buffer]
0x1800145e3  mov     ecx, ebp
0x1800145e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145ea  jmp     short loc_18001461C
0x1800145ec  mov     ebp, [rbx+8]
0x1800145ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800145f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800145fc  lea     rax, [rsp+278h+Buffer]
0x180014601  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180014606  mov     r9d, 400h; dwLanguageId
0x18001460c  mov     r8d, ebp; dwMessageId
0x18001460f  xor     edx, edx; lpSource
0x180014611  mov     ecx, 1200h; dwFlags
0x180014616  call    cs:__imp_FormatMessageW
0x18001461c  lea     rsi, [r14+rsi*2]
0x180014620  mov     r9, [rbx+38h]; unsigned __int16 *
0x180014624  mov     rax, [rbx+88h]
0x18001462b  mov     rcx, [rbx+80h]
0x180014632  mov     rdx, rsi; unsigned __int16 *
0x180014635  test    r9, r9
0x180014638  jz      short loc_18001465C
0x18001463a  mov     [rsp+278h+Arguments], rax
0x18001463f  mov     qword ptr [rsp+278h+nSize], rcx
0x180014644  mov     eax, [rbx+40h]
0x180014647  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001464b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180014652  mov     rcx, r14; this
0x180014655  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001465a  jmp     short loc_180014673
0x18001465c  mov     [rsp+278h+lpBuffer], rax
0x180014661  mov     r9, rcx; unsigned __int16 *
0x180014664  lea     r8, aHsP; "%hs!%p: "
0x18001466b  mov     rcx, r14; this
0x18001466e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014673  mov     r14, rax
0x180014676  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001467d  test    r9, r9
0x180014680  jz      short loc_180014697
0x180014682  lea     r8, aCallerP; "(caller: %p) "
0x180014689  mov     rdx, rsi; unsigned __int16 *
0x18001468c  mov     rcx, rax; this
0x18001468f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014694  mov     r14, rax
0x180014697  call    cs:__imp_GetCurrentThreadId
0x18001469d  lea     rcx, [rsp+278h+Buffer]
0x1800146a2  mov     [rsp+278h+var_240], rcx
0x1800146a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800146ab  mov     [rsp+278h+nSize], eax
0x1800146af  mov     eax, [rbx+44h]
0x1800146b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800146b6  mov     r9, rdi; unsigned __int16 *
0x1800146b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800146c0  mov     rdx, rsi; unsigned __int16 *
0x1800146c3  mov     rcx, r14; this
0x1800146c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800146cb  cmp     [rbx+18h], r15
0x1800146cf  jnz     short loc_1800146E1
0x1800146d1  cmp     [rbx+48h], r15
0x1800146d5  jnz     short loc_1800146E1
0x1800146d7  cmp     [rbx+30h], r15
0x1800146db  jz      loc_180014771
0x1800146e1  lea     r8, asc_1800259A0; "    "
0x1800146e8  mov     rdx, rsi; unsigned __int16 *
0x1800146eb  mov     rcx, rax; this
0x1800146ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800146f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800146f7  test    r9, r9
0x1800146fa  jz      short loc_18001470E
0x1800146fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180014703  mov     rdx, rsi; unsigned __int16 *
0x180014706  mov     rcx, rax; this
0x180014709  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001470e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180014712  test    r9, r9
0x180014715  jz      short loc_180014729
0x180014717  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001471e  mov     rdx, rsi; unsigned __int16 *
0x180014721  mov     rcx, rax; this
0x180014724  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014729  mov     rcx, [rbx+28h]
0x18001472d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180014731  mov     rdx, rsi; unsigned __int16 *
0x180014734  test    rcx, rcx
0x180014737  jz      short loc_18001474F
0x180014739  mov     [rsp+278h+lpBuffer], rcx
0x18001473e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180014745  mov     rcx, rax; this
0x180014748  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001474d  jmp     short loc_180014771
0x18001474f  mov     rcx, rax; this
0x180014752  test    r9, r9
0x180014755  jz      short loc_180014765
0x180014757  lea     r8, aHs; "[%hs]\n"
0x18001475e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014763  jmp     short loc_180014771
0x180014765  lea     r8, asc_180025A18; "\n"
0x18001476c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180014771  xor     eax, eax
0x180014773  mov     rcx, [rsp+278h+var_38]
0x18001477b  xor     rcx, rsp; StackCookie
0x18001477e  call    __security_check_cookie
0x180014783  mov     rbx, [rsp+278h+arg_18]
0x18001478b  add     rsp, 250h
0x180014792  pop     r15
0x180014794  pop     r14
0x180014796  pop     rdi
0x180014797  pop     rsi
0x180014798  pop     rbp
0x180014799  retn
```
