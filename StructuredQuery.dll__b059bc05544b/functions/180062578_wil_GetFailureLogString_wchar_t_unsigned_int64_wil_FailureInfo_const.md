# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180062578`
- end: `0x18006282e`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18005ff34`
- `0x1800636e4`
- `0x180063afc`
- `0x180067780`

## callees

- `0x18005daf0`
- `0x18005e740`
- `0x180062578`
- `0x1800639e8`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800626aa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800626aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006272b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006272b`

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
          v7 = (const char *)&qword_18009CA68;
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
0x180062578  mov     [rsp+arg_18], rbx
0x18006257d  push    rbp
0x18006257e  push    rsi
0x18006257f  push    rdi
0x180062580  push    r14
0x180062582  push    r15
0x180062584  sub     rsp, 250h
0x18006258b  mov     rax, cs:__security_cookie
0x180062592  xor     rax, rsp
0x180062595  mov     [rsp+278h+var_38], rax
0x18006259d  mov     rbx, r8
0x1800625a0  mov     rsi, rdx
0x1800625a3  mov     r14, rcx
0x1800625a6  xor     r15d, r15d
0x1800625a9  test    rdx, rdx
0x1800625ac  jz      loc_180062805
0x1800625b2  test    rcx, rcx
0x1800625b5  jz      loc_180062805
0x1800625bb  mov     [rcx], r15w
0x1800625bf  mov     rax, cs:g_pfnResultLoggingCallback
0x1800625c6  test    rax, rax
0x1800625c9  jz      short loc_1800625EC
0x1800625cb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800625d2  jz      short loc_1800625EC
0x1800625d4  mov     r8, rdx
0x1800625d7  mov     rdx, rcx
0x1800625da  mov     rcx, rbx
0x1800625dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800625e2  cmp     [r14], r15w
0x1800625e6  jnz     loc_180062805
0x1800625ec  mov     ecx, [rbx]
0x1800625ee  mov     bpl, 8
0x1800625f1  test    ecx, ecx
0x1800625f3  jz      short loc_18006263E
0x1800625f5  sub     ecx, 1
0x1800625f8  jz      short loc_180062626
0x1800625fa  sub     ecx, 1
0x1800625fd  jz      short loc_180062616
0x1800625ff  cmp     ecx, 1
0x180062602  jz      short loc_18006260D
0x180062604  lea     rdi, qword_18009CA68
0x18006260b  jmp     short loc_180062645
0x18006260d  lea     rdi, aFailfast; "FailFast"
0x180062614  jmp     short loc_180062645
0x180062616  lea     rax, aLoghr; "LogHr"
0x18006261d  lea     rdi, aLognt; "LogNt"
0x180062624  jmp     short loc_180062634
0x180062626  lea     rax, aReturnhr; "ReturnHr"
0x18006262d  lea     rdi, aReturnnt; "ReturnNt"
0x180062634  test    [rbx+4], bpl
0x180062638  cmovz   rdi, rax
0x18006263c  jmp     short loc_180062645
0x18006263e  lea     rdi, aException; "Exception"
0x180062645  xor     edx, edx; Val
0x180062647  mov     r8d, 200h; Size
0x18006264d  lea     rcx, [rsp+278h+Buffer]; void *
0x180062652  call    memset_0
0x180062657  test    [rbx+4], bpl
0x18006265b  jz      short loc_180062680
0x18006265d  mov     ebp, [rbx+0Ch]
0x180062660  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180062667  test    rax, rax
0x18006266a  jz      short loc_1800626B0
0x18006266c  mov     r8d, 100h
0x180062672  lea     rdx, [rsp+278h+Buffer]
0x180062677  mov     ecx, ebp
0x180062679  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006267e  jmp     short loc_1800626B0
0x180062680  mov     ebp, [rbx+8]
0x180062683  mov     [rsp+278h+Arguments], r15; Arguments
0x180062688  mov     [rsp+278h+nSize], 100h; nSize
0x180062690  lea     rax, [rsp+278h+Buffer]
0x180062695  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18006269a  mov     r9d, 400h; dwLanguageId
0x1800626a0  mov     r8d, ebp; dwMessageId
0x1800626a3  xor     edx, edx; lpSource
0x1800626a5  mov     ecx, 1200h; dwFlags
0x1800626aa  call    cs:__imp_FormatMessageW
0x1800626b0  lea     rsi, [r14+rsi*2]
0x1800626b4  mov     r9, [rbx+38h]; wchar_t *
0x1800626b8  mov     rax, [rbx+88h]
0x1800626bf  mov     rcx, [rbx+80h]
0x1800626c6  mov     rdx, rsi; wchar_t *
0x1800626c9  test    r9, r9
0x1800626cc  jz      short loc_1800626F0
0x1800626ce  mov     [rsp+278h+Arguments], rax
0x1800626d3  mov     qword ptr [rsp+278h+nSize], rcx
0x1800626d8  mov     eax, [rbx+40h]
0x1800626db  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800626df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800626e6  mov     rcx, r14; this
0x1800626e9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800626ee  jmp     short loc_180062707
0x1800626f0  mov     [rsp+278h+lpBuffer], rax
0x1800626f5  mov     r9, rcx; wchar_t *
0x1800626f8  lea     r8, aHsP; "%hs!%p: "
0x1800626ff  mov     rcx, r14; this
0x180062702  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180062707  mov     r14, rax
0x18006270a  mov     r9, [rbx+90h]; wchar_t *
0x180062711  test    r9, r9
0x180062714  jz      short loc_18006272B
0x180062716  lea     r8, aCallerP; "(caller: %p) "
0x18006271d  mov     rdx, rsi; wchar_t *
0x180062720  mov     rcx, rax; this
0x180062723  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180062728  mov     r14, rax
0x18006272b  call    cs:__imp_GetCurrentThreadId
0x180062731  lea     rcx, [rsp+278h+Buffer]
0x180062736  mov     [rsp+278h+var_240], rcx
0x18006273b  mov     dword ptr [rsp+278h+Arguments], ebp
0x18006273f  mov     [rsp+278h+nSize], eax
0x180062743  mov     eax, [rbx+44h]
0x180062746  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18006274a  mov     r9, rdi; wchar_t *
0x18006274d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180062754  mov     rdx, rsi; wchar_t *
0x180062757  mov     rcx, r14; this
0x18006275a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18006275f  cmp     [rbx+18h], r15
0x180062763  jnz     short loc_180062775
0x180062765  cmp     [rbx+48h], r15
0x180062769  jnz     short loc_180062775
0x18006276b  cmp     [rbx+30h], r15
0x18006276f  jz      loc_180062805
0x180062775  lea     r8, asc_18009F6C8; "    "
0x18006277c  mov     rdx, rsi; wchar_t *
0x18006277f  mov     rcx, rax; this
0x180062782  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180062787  mov     r9, [rbx+18h]; wchar_t *
0x18006278b  test    r9, r9
0x18006278e  jz      short loc_1800627A2
0x180062790  lea     r8, aMsgWs; "Msg:[%ws] "
0x180062797  mov     rdx, rsi; wchar_t *
0x18006279a  mov     rcx, rax; this
0x18006279d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800627a2  mov     r9, [rbx+48h]; wchar_t *
0x1800627a6  test    r9, r9
0x1800627a9  jz      short loc_1800627BD
0x1800627ab  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800627b2  mov     rdx, rsi; wchar_t *
0x1800627b5  mov     rcx, rax; this
0x1800627b8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800627bd  mov     rcx, [rbx+28h]
0x1800627c1  mov     r9, [rbx+30h]; wchar_t *
0x1800627c5  mov     rdx, rsi; wchar_t *
0x1800627c8  test    rcx, rcx
0x1800627cb  jz      short loc_1800627E3
0x1800627cd  mov     [rsp+278h+lpBuffer], rcx
0x1800627d2  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x1800627d9  mov     rcx, rax; this
0x1800627dc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800627e1  jmp     short loc_180062805
0x1800627e3  mov     rcx, rax; this
0x1800627e6  test    r9, r9
0x1800627e9  jz      short loc_1800627F9
0x1800627eb  lea     r8, aHs; "[%hs]\n"
0x1800627f2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800627f7  jmp     short loc_180062805
0x1800627f9  lea     r8, asc_18009F740; "\n"
0x180062800  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180062805  xor     eax, eax
0x180062807  mov     rcx, [rsp+278h+var_38]
0x18006280f  xor     rcx, rsp; StackCookie
0x180062812  call    __security_check_cookie
0x180062817  mov     rbx, [rsp+278h+arg_18]
0x18006281f  add     rsp, 250h
0x180062826  pop     r15
0x180062828  pop     r14
0x18006282a  pop     rdi
0x18006282b  pop     rsi
0x18006282c  pop     rbp
0x18006282d  retn
```
