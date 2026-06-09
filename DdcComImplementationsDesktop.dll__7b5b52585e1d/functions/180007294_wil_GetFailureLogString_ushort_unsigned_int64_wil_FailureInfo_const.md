# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007294`
- end: `0x18000754a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005030`
- `0x180005298`
- `0x180007bf4`
- `0x18000ad30`

## callees

- `0x1800016b0`
- `0x180002134`
- `0x180007294`
- `0x180007ef4`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007447`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800073c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800073c6`

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
          v7 = (const char *)&qword_18000F6E8;
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
0x180007294  mov     [rsp+arg_18], rbx
0x180007299  push    rbp
0x18000729a  push    rsi
0x18000729b  push    rdi
0x18000729c  push    r14
0x18000729e  push    r15
0x1800072a0  sub     rsp, 250h
0x1800072a7  mov     rax, cs:__security_cookie
0x1800072ae  xor     rax, rsp
0x1800072b1  mov     [rsp+278h+var_38], rax
0x1800072b9  mov     rbx, r8
0x1800072bc  mov     rsi, rdx
0x1800072bf  mov     r14, rcx
0x1800072c2  xor     r15d, r15d
0x1800072c5  test    rdx, rdx
0x1800072c8  jz      loc_180007521
0x1800072ce  test    rcx, rcx
0x1800072d1  jz      loc_180007521
0x1800072d7  mov     [rcx], r15w
0x1800072db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800072e2  test    rax, rax
0x1800072e5  jz      short loc_180007308
0x1800072e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800072ee  jz      short loc_180007308
0x1800072f0  mov     r8, rdx
0x1800072f3  mov     rdx, rcx
0x1800072f6  mov     rcx, rbx
0x1800072f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072fe  cmp     [r14], r15w
0x180007302  jnz     loc_180007521
0x180007308  mov     ecx, [rbx]
0x18000730a  mov     bpl, 8
0x18000730d  test    ecx, ecx
0x18000730f  jz      short loc_18000735A
0x180007311  sub     ecx, 1
0x180007314  jz      short loc_180007342
0x180007316  sub     ecx, 1
0x180007319  jz      short loc_180007332
0x18000731b  cmp     ecx, 1
0x18000731e  jz      short loc_180007329
0x180007320  lea     rdi, qword_18000F6E8
0x180007327  jmp     short loc_180007361
0x180007329  lea     rdi, aFailfast; "FailFast"
0x180007330  jmp     short loc_180007361
0x180007332  lea     rax, aLoghr; "LogHr"
0x180007339  lea     rdi, aLognt; "LogNt"
0x180007340  jmp     short loc_180007350
0x180007342  lea     rax, aReturnhr; "ReturnHr"
0x180007349  lea     rdi, aReturnnt; "ReturnNt"
0x180007350  test    [rbx+4], bpl
0x180007354  cmovz   rdi, rax
0x180007358  jmp     short loc_180007361
0x18000735a  lea     rdi, aException; "Exception"
0x180007361  xor     edx, edx; Val
0x180007363  mov     r8d, 200h; Size
0x180007369  lea     rcx, [rsp+278h+Buffer]; void *
0x18000736e  call    memset_0
0x180007373  test    [rbx+4], bpl
0x180007377  jz      short loc_18000739C
0x180007379  mov     ebp, [rbx+0Ch]
0x18000737c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007383  test    rax, rax
0x180007386  jz      short loc_1800073CC
0x180007388  mov     r8d, 100h
0x18000738e  lea     rdx, [rsp+278h+Buffer]
0x180007393  mov     ecx, ebp
0x180007395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000739a  jmp     short loc_1800073CC
0x18000739c  mov     ebp, [rbx+8]
0x18000739f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800073a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800073ac  lea     rax, [rsp+278h+Buffer]
0x1800073b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800073b6  mov     r9d, 400h; dwLanguageId
0x1800073bc  mov     r8d, ebp; dwMessageId
0x1800073bf  xor     edx, edx; lpSource
0x1800073c1  mov     ecx, 1200h; dwFlags
0x1800073c6  call    cs:__imp_FormatMessageW
0x1800073cc  lea     rsi, [r14+rsi*2]
0x1800073d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800073d4  mov     rax, [rbx+88h]
0x1800073db  mov     rcx, [rbx+80h]
0x1800073e2  mov     rdx, rsi; unsigned __int16 *
0x1800073e5  test    r9, r9
0x1800073e8  jz      short loc_18000740C
0x1800073ea  mov     [rsp+278h+Arguments], rax
0x1800073ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800073f4  mov     eax, [rbx+40h]
0x1800073f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800073fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007402  mov     rcx, r14; this
0x180007405  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000740a  jmp     short loc_180007423
0x18000740c  mov     [rsp+278h+lpBuffer], rax
0x180007411  mov     r9, rcx; unsigned __int16 *
0x180007414  lea     r8, aHsP; "%hs!%p: "
0x18000741b  mov     rcx, r14; this
0x18000741e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007423  mov     r14, rax
0x180007426  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000742d  test    r9, r9
0x180007430  jz      short loc_180007447
0x180007432  lea     r8, aCallerP; "(caller: %p) "
0x180007439  mov     rdx, rsi; unsigned __int16 *
0x18000743c  mov     rcx, rax; this
0x18000743f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007444  mov     r14, rax
0x180007447  call    cs:__imp_GetCurrentThreadId
0x18000744d  lea     rcx, [rsp+278h+Buffer]
0x180007452  mov     [rsp+278h+var_240], rcx
0x180007457  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000745b  mov     [rsp+278h+nSize], eax
0x18000745f  mov     eax, [rbx+44h]
0x180007462  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007466  mov     r9, rdi; unsigned __int16 *
0x180007469  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007470  mov     rdx, rsi; unsigned __int16 *
0x180007473  mov     rcx, r14; this
0x180007476  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000747b  cmp     [rbx+18h], r15
0x18000747f  jnz     short loc_180007491
0x180007481  cmp     [rbx+48h], r15
0x180007485  jnz     short loc_180007491
0x180007487  cmp     [rbx+30h], r15
0x18000748b  jz      loc_180007521
0x180007491  lea     r8, asc_18000F340; "    "
0x180007498  mov     rdx, rsi; unsigned __int16 *
0x18000749b  mov     rcx, rax; this
0x18000749e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800074a7  test    r9, r9
0x1800074aa  jz      short loc_1800074BE
0x1800074ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800074b3  mov     rdx, rsi; unsigned __int16 *
0x1800074b6  mov     rcx, rax; this
0x1800074b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800074c2  test    r9, r9
0x1800074c5  jz      short loc_1800074D9
0x1800074c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800074ce  mov     rdx, rsi; unsigned __int16 *
0x1800074d1  mov     rcx, rax; this
0x1800074d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074d9  mov     rcx, [rbx+28h]
0x1800074dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800074e1  mov     rdx, rsi; unsigned __int16 *
0x1800074e4  test    rcx, rcx
0x1800074e7  jz      short loc_1800074FF
0x1800074e9  mov     [rsp+278h+lpBuffer], rcx
0x1800074ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800074f5  mov     rcx, rax; this
0x1800074f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074fd  jmp     short loc_180007521
0x1800074ff  mov     rcx, rax; this
0x180007502  test    r9, r9
0x180007505  jz      short loc_180007515
0x180007507  lea     r8, aHs; "[%hs]\n"
0x18000750e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007513  jmp     short loc_180007521
0x180007515  lea     r8, asc_18000F3B8; "\n"
0x18000751c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007521  xor     eax, eax
0x180007523  mov     rcx, [rsp+278h+var_38]
0x18000752b  xor     rcx, rsp; StackCookie
0x18000752e  call    __security_check_cookie
0x180007533  mov     rbx, [rsp+278h+arg_18]
0x18000753b  add     rsp, 250h
0x180007542  pop     r15
0x180007544  pop     r14
0x180007546  pop     rdi
0x180007547  pop     rsi
0x180007548  pop     rbp
0x180007549  retn
```
