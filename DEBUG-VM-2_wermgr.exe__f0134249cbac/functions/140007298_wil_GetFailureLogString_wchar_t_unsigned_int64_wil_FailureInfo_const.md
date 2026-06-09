# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140007298`
- end: `0x14000754e`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140003df4`
- `0x140004090`
- `0x14000fa90`
- `0x140014a20`

## callees

- `0x140002fbc`
- `0x140003200`
- `0x140007298`
- `0x140008b88`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000744b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000744b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400073ca`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400073ca`

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
          v7 = (const char *)&qword_140024070;
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
0x140007298  mov     [rsp+arg_18], rbx
0x14000729d  push    rbp
0x14000729e  push    rsi
0x14000729f  push    rdi
0x1400072a0  push    r14
0x1400072a2  push    r15
0x1400072a4  sub     rsp, 250h
0x1400072ab  mov     rax, cs:__security_cookie
0x1400072b2  xor     rax, rsp
0x1400072b5  mov     [rsp+278h+var_38], rax
0x1400072bd  mov     rbx, r8
0x1400072c0  mov     rsi, rdx
0x1400072c3  mov     r14, rcx
0x1400072c6  xor     r15d, r15d
0x1400072c9  test    rdx, rdx
0x1400072cc  jz      loc_140007525
0x1400072d2  test    rcx, rcx
0x1400072d5  jz      loc_140007525
0x1400072db  mov     [rcx], r15w
0x1400072df  mov     rax, cs:g_pfnResultLoggingCallback
0x1400072e6  test    rax, rax
0x1400072e9  jz      short loc_14000730C
0x1400072eb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400072f2  jz      short loc_14000730C
0x1400072f4  mov     r8, rdx
0x1400072f7  mov     rdx, rcx
0x1400072fa  mov     rcx, rbx
0x1400072fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007302  cmp     [r14], r15w
0x140007306  jnz     loc_140007525
0x14000730c  mov     ecx, [rbx]
0x14000730e  mov     bpl, 8
0x140007311  test    ecx, ecx
0x140007313  jz      short loc_14000735E
0x140007315  sub     ecx, 1
0x140007318  jz      short loc_140007346
0x14000731a  sub     ecx, 1
0x14000731d  jz      short loc_140007336
0x14000731f  cmp     ecx, 1
0x140007322  jz      short loc_14000732D
0x140007324  lea     rdi, qword_140024070
0x14000732b  jmp     short loc_140007365
0x14000732d  lea     rdi, aFailfast; "FailFast"
0x140007334  jmp     short loc_140007365
0x140007336  lea     rax, aLoghr; "LogHr"
0x14000733d  lea     rdi, aLognt; "LogNt"
0x140007344  jmp     short loc_140007354
0x140007346  lea     rax, aReturnhr; "ReturnHr"
0x14000734d  lea     rdi, aReturnnt; "ReturnNt"
0x140007354  test    [rbx+4], bpl
0x140007358  cmovz   rdi, rax
0x14000735c  jmp     short loc_140007365
0x14000735e  lea     rdi, aException; "Exception"
0x140007365  xor     edx, edx; Val
0x140007367  mov     r8d, 200h; Size
0x14000736d  lea     rcx, [rsp+278h+Buffer]; void *
0x140007372  call    memset_0
0x140007377  test    [rbx+4], bpl
0x14000737b  jz      short loc_1400073A0
0x14000737d  mov     ebp, [rbx+0Ch]
0x140007380  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140007387  test    rax, rax
0x14000738a  jz      short loc_1400073D0
0x14000738c  mov     r8d, 100h
0x140007392  lea     rdx, [rsp+278h+Buffer]
0x140007397  mov     ecx, ebp
0x140007399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000739e  jmp     short loc_1400073D0
0x1400073a0  mov     ebp, [rbx+8]
0x1400073a3  mov     [rsp+278h+Arguments], r15; Arguments
0x1400073a8  mov     [rsp+278h+nSize], 100h; nSize
0x1400073b0  lea     rax, [rsp+278h+Buffer]
0x1400073b5  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400073ba  mov     r9d, 400h; dwLanguageId
0x1400073c0  mov     r8d, ebp; dwMessageId
0x1400073c3  xor     edx, edx; lpSource
0x1400073c5  mov     ecx, 1200h; dwFlags
0x1400073ca  call    cs:__imp_FormatMessageW
0x1400073d0  lea     rsi, [r14+rsi*2]
0x1400073d4  mov     r9, [rbx+38h]; wchar_t *
0x1400073d8  mov     rax, [rbx+88h]
0x1400073df  mov     rcx, [rbx+80h]
0x1400073e6  mov     rdx, rsi; wchar_t *
0x1400073e9  test    r9, r9
0x1400073ec  jz      short loc_140007410
0x1400073ee  mov     [rsp+278h+Arguments], rax
0x1400073f3  mov     qword ptr [rsp+278h+nSize], rcx
0x1400073f8  mov     eax, [rbx+40h]
0x1400073fb  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400073ff  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140007406  mov     rcx, r14; this
0x140007409  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000740e  jmp     short loc_140007427
0x140007410  mov     [rsp+278h+lpBuffer], rax
0x140007415  mov     r9, rcx; wchar_t *
0x140007418  lea     r8, aHsP; "%hs!%p: "
0x14000741f  mov     rcx, r14; this
0x140007422  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007427  mov     r14, rax
0x14000742a  mov     r9, [rbx+90h]; wchar_t *
0x140007431  test    r9, r9
0x140007434  jz      short loc_14000744B
0x140007436  lea     r8, aCallerP; "(caller: %p) "
0x14000743d  mov     rdx, rsi; wchar_t *
0x140007440  mov     rcx, rax; this
0x140007443  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007448  mov     r14, rax
0x14000744b  call    cs:__imp_GetCurrentThreadId
0x140007451  lea     rcx, [rsp+278h+Buffer]
0x140007456  mov     [rsp+278h+var_240], rcx
0x14000745b  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000745f  mov     [rsp+278h+nSize], eax
0x140007463  mov     eax, [rbx+44h]
0x140007466  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000746a  mov     r9, rdi; wchar_t *
0x14000746d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140007474  mov     rdx, rsi; wchar_t *
0x140007477  mov     rcx, r14; this
0x14000747a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000747f  cmp     [rbx+18h], r15
0x140007483  jnz     short loc_140007495
0x140007485  cmp     [rbx+48h], r15
0x140007489  jnz     short loc_140007495
0x14000748b  cmp     [rbx+30h], r15
0x14000748f  jz      loc_140007525
0x140007495  lea     r8, asc_140024160; "    "
0x14000749c  mov     rdx, rsi; wchar_t *
0x14000749f  mov     rcx, rax; this
0x1400074a2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400074a7  mov     r9, [rbx+18h]; wchar_t *
0x1400074ab  test    r9, r9
0x1400074ae  jz      short loc_1400074C2
0x1400074b0  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400074b7  mov     rdx, rsi; wchar_t *
0x1400074ba  mov     rcx, rax; this
0x1400074bd  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400074c2  mov     r9, [rbx+48h]; wchar_t *
0x1400074c6  test    r9, r9
0x1400074c9  jz      short loc_1400074DD
0x1400074cb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400074d2  mov     rdx, rsi; wchar_t *
0x1400074d5  mov     rcx, rax; this
0x1400074d8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400074dd  mov     rcx, [rbx+28h]
0x1400074e1  mov     r9, [rbx+30h]; wchar_t *
0x1400074e5  mov     rdx, rsi; wchar_t *
0x1400074e8  test    rcx, rcx
0x1400074eb  jz      short loc_140007503
0x1400074ed  mov     [rsp+278h+lpBuffer], rcx
0x1400074f2  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400074f9  mov     rcx, rax; this
0x1400074fc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007501  jmp     short loc_140007525
0x140007503  mov     rcx, rax; this
0x140007506  test    r9, r9
0x140007509  jz      short loc_140007519
0x14000750b  lea     r8, aHs; "[%hs]\n"
0x140007512  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007517  jmp     short loc_140007525
0x140007519  lea     r8, asc_1400241D8; "\n"
0x140007520  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007525  xor     eax, eax
0x140007527  mov     rcx, [rsp+278h+var_38]
0x14000752f  xor     rcx, rsp; StackCookie
0x140007532  call    __security_check_cookie
0x140007537  mov     rbx, [rsp+278h+arg_18]
0x14000753f  add     rsp, 250h
0x140007546  pop     r15
0x140007548  pop     r14
0x14000754a  pop     rdi
0x14000754b  pop     rsi
0x14000754c  pop     rbp
0x14000754d  retn
```
