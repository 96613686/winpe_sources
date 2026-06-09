# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18005cbf8`
- end: `0x18005ceb9`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18004b654`
- `0x18005cac0`

## callees

- `0x18005acc4`
- `0x18005cbf8`
- `0x1800810a2`
- `0x1800810d0`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cdb6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005cdb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005cd35`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18005cd35`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_1800A2F40;
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
                          Buffer,
                          -2);
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
0x18005cbf8  mov     rax, rsp
0x18005cbfb  push    rbp
0x18005cbfc  push    rsi
0x18005cbfd  push    rdi
0x18005cbfe  push    r14
0x18005cc00  push    r15
0x18005cc02  sub     rsp, 260h
0x18005cc09  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18005cc12  mov     [rax+20h], rbx
0x18005cc16  mov     rax, cs:__security_cookie
0x18005cc1d  xor     rax, rsp
0x18005cc20  mov     [rsp+288h+var_38], rax
0x18005cc28  mov     rbx, r8
0x18005cc2b  mov     rsi, rdx
0x18005cc2e  mov     r14, rcx
0x18005cc31  xor     r15d, r15d
0x18005cc34  test    rdx, rdx
0x18005cc37  jz      loc_18005CE90
0x18005cc3d  test    rcx, rcx
0x18005cc40  jz      loc_18005CE90
0x18005cc46  mov     [rcx], r15w
0x18005cc4a  mov     rax, cs:g_pfnResultLoggingCallback
0x18005cc51  test    rax, rax
0x18005cc54  jz      short loc_18005CC77
0x18005cc56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18005cc5d  jz      short loc_18005CC77
0x18005cc5f  mov     r8, rdx
0x18005cc62  mov     rdx, rcx
0x18005cc65  mov     rcx, rbx
0x18005cc68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cc6d  cmp     [r14], r15w
0x18005cc71  jnz     loc_18005CE90
0x18005cc77  mov     ecx, [rbx]
0x18005cc79  mov     bpl, 8
0x18005cc7c  test    ecx, ecx
0x18005cc7e  jz      short loc_18005CCC9
0x18005cc80  sub     ecx, 1
0x18005cc83  jz      short loc_18005CCB1
0x18005cc85  sub     ecx, 1
0x18005cc88  jz      short loc_18005CCA1
0x18005cc8a  cmp     ecx, 1
0x18005cc8d  jz      short loc_18005CC98
0x18005cc8f  lea     rdi, qword_1800A2F40
0x18005cc96  jmp     short loc_18005CCD0
0x18005cc98  lea     rdi, aFailfast; "FailFast"
0x18005cc9f  jmp     short loc_18005CCD0
0x18005cca1  lea     rax, aLoghr; "LogHr"
0x18005cca8  lea     rdi, aLognt; "LogNt"
0x18005ccaf  jmp     short loc_18005CCBF
0x18005ccb1  lea     rax, aReturnhr; "ReturnHr"
0x18005ccb8  lea     rdi, aReturnnt; "ReturnNt"
0x18005ccbf  test    [rbx+4], bpl
0x18005ccc3  cmovz   rdi, rax
0x18005ccc7  jmp     short loc_18005CCD0
0x18005ccc9  lea     rdi, aException; "Exception"
0x18005ccd0  xor     edx, edx; Val
0x18005ccd2  mov     r8d, 200h; Size
0x18005ccd8  lea     rcx, [rsp+288h+Buffer]; void *
0x18005ccdd  call    memset_0
0x18005cce2  test    [rbx+4], bpl
0x18005cce6  jz      short loc_18005CD0B
0x18005cce8  mov     ebp, [rbx+0Ch]
0x18005cceb  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18005ccf2  test    rax, rax
0x18005ccf5  jz      short loc_18005CD3B
0x18005ccf7  mov     r8d, 100h
0x18005ccfd  lea     rdx, [rsp+288h+Buffer]
0x18005cd02  mov     ecx, ebp
0x18005cd04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005cd09  jmp     short loc_18005CD3B
0x18005cd0b  mov     ebp, [rbx+8]
0x18005cd0e  mov     [rsp+288h+Arguments], r15; Arguments
0x18005cd13  mov     [rsp+288h+nSize], 100h; nSize
0x18005cd1b  lea     rax, [rsp+288h+Buffer]
0x18005cd20  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18005cd25  mov     r9d, 400h; dwLanguageId
0x18005cd2b  mov     r8d, ebp; dwMessageId
0x18005cd2e  xor     edx, edx; lpSource
0x18005cd30  mov     ecx, 1200h; dwFlags
0x18005cd35  call    cs:__imp_FormatMessageW
0x18005cd3b  lea     rsi, [r14+rsi*2]
0x18005cd3f  mov     r9, [rbx+38h]; wchar_t *
0x18005cd43  mov     rax, [rbx+88h]
0x18005cd4a  mov     rcx, [rbx+80h]
0x18005cd51  mov     rdx, rsi; wchar_t *
0x18005cd54  test    r9, r9
0x18005cd57  jz      short loc_18005CD7B
0x18005cd59  mov     [rsp+288h+Arguments], rax
0x18005cd5e  mov     qword ptr [rsp+288h+nSize], rcx
0x18005cd63  mov     eax, [rbx+40h]
0x18005cd66  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18005cd6a  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18005cd71  mov     rcx, r14; this
0x18005cd74  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005cd79  jmp     short loc_18005CD92
0x18005cd7b  mov     [rsp+288h+lpBuffer], rax
0x18005cd80  mov     r9, rcx; wchar_t *
0x18005cd83  lea     r8, aHsP; "%hs!%p: "
0x18005cd8a  mov     rcx, r14; this
0x18005cd8d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005cd92  mov     r14, rax
0x18005cd95  mov     r9, [rbx+90h]; wchar_t *
0x18005cd9c  test    r9, r9
0x18005cd9f  jz      short loc_18005CDB6
0x18005cda1  lea     r8, aCallerP; "(caller: %p) "
0x18005cda8  mov     rdx, rsi; wchar_t *
0x18005cdab  mov     rcx, rax; this
0x18005cdae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005cdb3  mov     r14, rax
0x18005cdb6  call    cs:__imp_GetCurrentThreadId
0x18005cdbc  lea     rcx, [rsp+288h+Buffer]
0x18005cdc1  mov     [rsp+288h+var_250], rcx
0x18005cdc6  mov     dword ptr [rsp+288h+Arguments], ebp
0x18005cdca  mov     [rsp+288h+nSize], eax
0x18005cdce  mov     eax, [rbx+44h]
0x18005cdd1  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18005cdd5  mov     r9, rdi; wchar_t *
0x18005cdd8  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005cddf  mov     rdx, rsi; wchar_t *
0x18005cde2  mov     rcx, r14; this
0x18005cde5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005cdea  cmp     [rbx+18h], r15
0x18005cdee  jnz     short loc_18005CE00
0x18005cdf0  cmp     [rbx+48h], r15
0x18005cdf4  jnz     short loc_18005CE00
0x18005cdf6  cmp     [rbx+30h], r15
0x18005cdfa  jz      loc_18005CE90
0x18005ce00  lea     r8, asc_1800A3078; "    "
0x18005ce07  mov     rdx, rsi; wchar_t *
0x18005ce0a  mov     rcx, rax; this
0x18005ce0d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005ce12  mov     r9, [rbx+18h]; wchar_t *
0x18005ce16  test    r9, r9
0x18005ce19  jz      short loc_18005CE2D
0x18005ce1b  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005ce22  mov     rdx, rsi; wchar_t *
0x18005ce25  mov     rcx, rax; this
0x18005ce28  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005ce2d  mov     r9, [rbx+48h]; wchar_t *
0x18005ce31  test    r9, r9
0x18005ce34  jz      short loc_18005CE48
0x18005ce36  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18005ce3d  mov     rdx, rsi; wchar_t *
0x18005ce40  mov     rcx, rax; this
0x18005ce43  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005ce48  mov     rcx, [rbx+28h]
0x18005ce4c  mov     r9, [rbx+30h]; wchar_t *
0x18005ce50  mov     rdx, rsi; wchar_t *
0x18005ce53  test    rcx, rcx
0x18005ce56  jz      short loc_18005CE6E
0x18005ce58  mov     [rsp+288h+lpBuffer], rcx
0x18005ce5d  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18005ce64  mov     rcx, rax; this
0x18005ce67  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005ce6c  jmp     short loc_18005CE90
0x18005ce6e  mov     rcx, rax; this
0x18005ce71  test    r9, r9
0x18005ce74  jz      short loc_18005CE84
0x18005ce76  lea     r8, aHs; "[%hs]\n"
0x18005ce7d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005ce82  jmp     short loc_18005CE90
0x18005ce84  lea     r8, asc_1800A30F0; "\n"
0x18005ce8b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18005ce90  xor     eax, eax
0x18005ce92  mov     rcx, [rsp+288h+var_38]
0x18005ce9a  xor     rcx, rsp; StackCookie
0x18005ce9d  call    __security_check_cookie
0x18005cea2  mov     rbx, [rsp+288h+arg_18]
0x18005ceaa  add     rsp, 260h
0x18005ceb1  pop     r15
0x18005ceb3  pop     r14
0x18005ceb5  pop     rdi
0x18005ceb6  pop     rsi
0x18005ceb7  pop     rbp
0x18005ceb8  retn
```
