# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180141464`
- end: `0x18014171a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18013fcb4`
- `0x180141e18`
- `0x180278790`

## callees

- `0x18013bad0`
- `0x18013c916`
- `0x180141464`
- `0x180142118`
- `0x18027a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180141617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180141617`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180141596`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180141596`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const unsigned __int16 *v15; // r9
  wchar_t *v16; // r14
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
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
  if ( !pszDest )
    return 0;
  v7 = (void (__fastcall *)(__int64, STRSAFE_LPWSTR, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *pszDest = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, pszDest, a2, a4);
      if ( *pszDest )
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
          v8 = &byte_1802A8987;
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
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = &pszDest[(_QWORD)a2];
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = v14;
  if ( v15 )
    v16 = wil::details::LogStringPrintf(v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
          v16,
          v12,
          L"%hs(%d) tid(%x) %08X %ws",
          (const unsigned __int16 *)v8,
          lpBuffera,
          *(_QWORD *)nSize,
          Arguments,
          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180141464  mov     [rsp+arg_18], rbx
0x180141469  push    rbp
0x18014146a  push    rsi
0x18014146b  push    rdi
0x18014146c  push    r14
0x18014146e  push    r15
0x180141470  sub     rsp, 250h
0x180141477  mov     rax, cs:__security_cookie
0x18014147e  xor     rax, rsp
0x180141481  mov     [rsp+278h+var_38], rax
0x180141489  xor     r15d, r15d
0x18014148c  mov     rbx, r8
0x18014148f  mov     rsi, rdx
0x180141492  mov     r14, rcx
0x180141495  test    rdx, rdx
0x180141498  jz      loc_1801416F1
0x18014149e  test    rcx, rcx
0x1801414a1  jz      loc_1801416F1
0x1801414a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1801414ae  mov     [rcx], r15w
0x1801414b2  test    rax, rax
0x1801414b5  jz      short loc_1801414D8
0x1801414b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1801414be  jz      short loc_1801414D8
0x1801414c0  mov     r8, rdx
0x1801414c3  mov     rdx, rcx
0x1801414c6  mov     rcx, rbx
0x1801414c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801414ce  cmp     [r14], r15w
0x1801414d2  jnz     loc_1801416F1
0x1801414d8  mov     ecx, [rbx]
0x1801414da  mov     bpl, 8
0x1801414dd  test    ecx, ecx
0x1801414df  jz      short loc_18014152A
0x1801414e1  sub     ecx, 1
0x1801414e4  jz      short loc_180141512
0x1801414e6  sub     ecx, 1
0x1801414e9  jz      short loc_180141502
0x1801414eb  cmp     ecx, 1
0x1801414ee  jz      short loc_1801414F9
0x1801414f0  lea     rdi, byte_1802A8987
0x1801414f7  jmp     short loc_180141531
0x1801414f9  lea     rdi, aFailfast; "FailFast"
0x180141500  jmp     short loc_180141531
0x180141502  lea     rax, aLoghr; "LogHr"
0x180141509  lea     rdi, aLognt; "LogNt"
0x180141510  jmp     short loc_180141520
0x180141512  lea     rax, aReturnhr; "ReturnHr"
0x180141519  lea     rdi, aReturnnt; "ReturnNt"
0x180141520  test    [rbx+4], bpl
0x180141524  cmovz   rdi, rax
0x180141528  jmp     short loc_180141531
0x18014152a  lea     rdi, aException; "Exception"
0x180141531  xor     edx, edx; Val
0x180141533  lea     rcx, [rsp+278h+Buffer]; void *
0x180141538  mov     r8d, 200h; Size
0x18014153e  call    memset_0
0x180141543  test    [rbx+4], bpl
0x180141547  jz      short loc_18014156C
0x180141549  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180141550  mov     ebp, [rbx+0Ch]
0x180141553  test    rax, rax
0x180141556  jz      short loc_18014159C
0x180141558  mov     r8d, 100h
0x18014155e  lea     rdx, [rsp+278h+Buffer]
0x180141563  mov     ecx, ebp
0x180141565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18014156a  jmp     short loc_18014159C
0x18014156c  mov     ebp, [rbx+8]
0x18014156f  lea     rax, [rsp+278h+Buffer]
0x180141574  mov     [rsp+278h+Arguments], r15; Arguments
0x180141579  mov     r8d, ebp; dwMessageId
0x18014157c  mov     [rsp+278h+nSize], 100h; nSize
0x180141584  mov     r9d, 400h; dwLanguageId
0x18014158a  xor     edx, edx; lpSource
0x18014158c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180141591  mov     ecx, 1200h; dwFlags
0x180141596  call    cs:__imp_FormatMessageW
0x18014159c  mov     r9, [rbx+38h]; unsigned __int16 *
0x1801415a0  lea     rsi, [r14+rsi*2]
0x1801415a4  mov     rax, [rbx+88h]
0x1801415ab  mov     rdx, rsi; unsigned __int16 *
0x1801415ae  mov     rcx, [rbx+80h]
0x1801415b5  test    r9, r9
0x1801415b8  jz      short loc_1801415DC
0x1801415ba  mov     [rsp+278h+Arguments], rax
0x1801415bf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1801415c6  mov     eax, [rbx+40h]
0x1801415c9  mov     qword ptr [rsp+278h+nSize], rcx
0x1801415ce  mov     rcx, r14; pszDest
0x1801415d1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1801415d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801415da  jmp     short loc_1801415F3
0x1801415dc  mov     r9, rcx; unsigned __int16 *
0x1801415df  mov     [rsp+278h+lpBuffer], rax
0x1801415e4  mov     rcx, r14; pszDest
0x1801415e7  lea     r8, aHsP; "%hs!%p: "
0x1801415ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801415f3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1801415fa  mov     r14, rax
0x1801415fd  test    r9, r9
0x180141600  jz      short loc_180141617
0x180141602  lea     r8, aCallerP; "(caller: %p) "
0x180141609  mov     rdx, rsi; unsigned __int16 *
0x18014160c  mov     rcx, rax; pszDest
0x18014160f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180141614  mov     r14, rax
0x180141617  call    cs:__imp_GetCurrentThreadId
0x18014161d  lea     rcx, [rsp+278h+Buffer]
0x180141622  mov     r9, rdi; unsigned __int16 *
0x180141625  mov     [rsp+278h+var_240], rcx
0x18014162a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180141631  mov     dword ptr [rsp+278h+Arguments], ebp
0x180141635  mov     rdx, rsi; unsigned __int16 *
0x180141638  mov     [rsp+278h+nSize], eax
0x18014163c  mov     rcx, r14; pszDest
0x18014163f  mov     eax, [rbx+44h]
0x180141642  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180141646  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18014164b  cmp     [rbx+18h], r15
0x18014164f  jnz     short loc_180141661
0x180141651  cmp     [rbx+48h], r15
0x180141655  jnz     short loc_180141661
0x180141657  cmp     [rbx+30h], r15
0x18014165b  jz      loc_1801416F1
0x180141661  lea     r8, asc_1802A8A70; "    "
0x180141668  mov     rdx, rsi; unsigned __int16 *
0x18014166b  mov     rcx, rax; pszDest
0x18014166e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180141673  mov     r9, [rbx+18h]; unsigned __int16 *
0x180141677  test    r9, r9
0x18014167a  jz      short loc_18014168E
0x18014167c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180141683  mov     rdx, rsi; unsigned __int16 *
0x180141686  mov     rcx, rax; pszDest
0x180141689  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18014168e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180141692  test    r9, r9
0x180141695  jz      short loc_1801416A9
0x180141697  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18014169e  mov     rdx, rsi; unsigned __int16 *
0x1801416a1  mov     rcx, rax; pszDest
0x1801416a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801416a9  mov     rcx, [rbx+28h]
0x1801416ad  mov     rdx, rsi; unsigned __int16 *
0x1801416b0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1801416b4  test    rcx, rcx
0x1801416b7  jz      short loc_1801416CF
0x1801416b9  mov     [rsp+278h+lpBuffer], rcx
0x1801416be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1801416c5  mov     rcx, rax; pszDest
0x1801416c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801416cd  jmp     short loc_1801416F1
0x1801416cf  mov     rcx, rax; pszDest
0x1801416d2  test    r9, r9
0x1801416d5  jz      short loc_1801416E5
0x1801416d7  lea     r8, aHs; "[%hs]\n"
0x1801416de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801416e3  jmp     short loc_1801416F1
0x1801416e5  lea     r8, asc_1802A8AE8; "\n"
0x1801416ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1801416f1  xor     eax, eax
0x1801416f3  mov     rcx, [rsp+278h+var_38]
0x1801416fb  xor     rcx, rsp; StackCookie
0x1801416fe  call    __security_check_cookie
0x180141703  mov     rbx, [rsp+278h+arg_18]
0x18014170b  add     rsp, 250h
0x180141712  pop     r15
0x180141714  pop     r14
0x180141716  pop     rdi
0x180141717  pop     rsi
0x180141718  pop     rbp
0x180141719  retn
```
