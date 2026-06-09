# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800072bc`
- end: `0x180007572`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180004380`
- `0x180004600`
- `0x1800048ac`
- `0x18000b620`
- `0x18000c130`
- `0x180029b04`
- `0x180029c38`
- `0x180029da1`
- `0x18002a01e`

## callees

- `0x1800021c0`
- `0x180002c04`
- `0x1800072bc`
- `0x180008200`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000746f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000746f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800073ee`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800073ee`

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
          v7 = (const char *)&word_18002FDC8;
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
0x1800072bc  mov     [rsp+arg_18], rbx
0x1800072c1  push    rbp
0x1800072c2  push    rsi
0x1800072c3  push    rdi
0x1800072c4  push    r14
0x1800072c6  push    r15
0x1800072c8  sub     rsp, 250h
0x1800072cf  mov     rax, cs:__security_cookie
0x1800072d6  xor     rax, rsp
0x1800072d9  mov     [rsp+278h+var_38], rax
0x1800072e1  mov     rbx, r8
0x1800072e4  mov     rsi, rdx
0x1800072e7  mov     r14, rcx
0x1800072ea  xor     r15d, r15d
0x1800072ed  test    rdx, rdx
0x1800072f0  jz      loc_180007549
0x1800072f6  test    rcx, rcx
0x1800072f9  jz      loc_180007549
0x1800072ff  mov     [rcx], r15w
0x180007303  mov     rax, cs:g_pfnResultLoggingCallback
0x18000730a  test    rax, rax
0x18000730d  jz      short loc_180007330
0x18000730f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007316  jz      short loc_180007330
0x180007318  mov     r8, rdx
0x18000731b  mov     rdx, rcx
0x18000731e  mov     rcx, rbx
0x180007321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007326  cmp     [r14], r15w
0x18000732a  jnz     loc_180007549
0x180007330  mov     ecx, [rbx]
0x180007332  mov     bpl, 8
0x180007335  test    ecx, ecx
0x180007337  jz      short loc_180007382
0x180007339  sub     ecx, 1
0x18000733c  jz      short loc_18000736A
0x18000733e  sub     ecx, 1
0x180007341  jz      short loc_18000735A
0x180007343  cmp     ecx, 1
0x180007346  jz      short loc_180007351
0x180007348  lea     rdi, word_18002FDC8
0x18000734f  jmp     short loc_180007389
0x180007351  lea     rdi, aFailfast; "FailFast"
0x180007358  jmp     short loc_180007389
0x18000735a  lea     rax, aLoghr; "LogHr"
0x180007361  lea     rdi, aLognt; "LogNt"
0x180007368  jmp     short loc_180007378
0x18000736a  lea     rax, aReturnhr; "ReturnHr"
0x180007371  lea     rdi, aReturnnt; "ReturnNt"
0x180007378  test    [rbx+4], bpl
0x18000737c  cmovz   rdi, rax
0x180007380  jmp     short loc_180007389
0x180007382  lea     rdi, aException; "Exception"
0x180007389  xor     edx, edx; Val
0x18000738b  mov     r8d, 200h; Size
0x180007391  lea     rcx, [rsp+278h+Buffer]; void *
0x180007396  call    memset_0
0x18000739b  test    [rbx+4], bpl
0x18000739f  jz      short loc_1800073C4
0x1800073a1  mov     ebp, [rbx+0Ch]
0x1800073a4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800073ab  test    rax, rax
0x1800073ae  jz      short loc_1800073F4
0x1800073b0  mov     r8d, 100h
0x1800073b6  lea     rdx, [rsp+278h+Buffer]
0x1800073bb  mov     ecx, ebp
0x1800073bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c2  jmp     short loc_1800073F4
0x1800073c4  mov     ebp, [rbx+8]
0x1800073c7  mov     [rsp+278h+Arguments], r15; Arguments
0x1800073cc  mov     [rsp+278h+nSize], 100h; nSize
0x1800073d4  lea     rax, [rsp+278h+Buffer]
0x1800073d9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800073de  mov     r9d, 400h; dwLanguageId
0x1800073e4  mov     r8d, ebp; dwMessageId
0x1800073e7  xor     edx, edx; lpSource
0x1800073e9  mov     ecx, 1200h; dwFlags
0x1800073ee  call    cs:__imp_FormatMessageW
0x1800073f4  lea     rsi, [r14+rsi*2]
0x1800073f8  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800073fc  mov     rax, [rbx+88h]
0x180007403  mov     rcx, [rbx+80h]
0x18000740a  mov     rdx, rsi; unsigned __int16 *
0x18000740d  test    r9, r9
0x180007410  jz      short loc_180007434
0x180007412  mov     [rsp+278h+Arguments], rax
0x180007417  mov     qword ptr [rsp+278h+nSize], rcx
0x18000741c  mov     eax, [rbx+40h]
0x18000741f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007423  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000742a  mov     rcx, r14; this
0x18000742d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007432  jmp     short loc_18000744B
0x180007434  mov     [rsp+278h+lpBuffer], rax
0x180007439  mov     r9, rcx; unsigned __int16 *
0x18000743c  lea     r8, aHsP; "%hs!%p: "
0x180007443  mov     rcx, r14; this
0x180007446  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000744b  mov     r14, rax
0x18000744e  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007455  test    r9, r9
0x180007458  jz      short loc_18000746F
0x18000745a  lea     r8, aCallerP; "(caller: %p) "
0x180007461  mov     rdx, rsi; unsigned __int16 *
0x180007464  mov     rcx, rax; this
0x180007467  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000746c  mov     r14, rax
0x18000746f  call    cs:__imp_GetCurrentThreadId
0x180007475  lea     rcx, [rsp+278h+Buffer]
0x18000747a  mov     [rsp+278h+var_240], rcx
0x18000747f  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007483  mov     [rsp+278h+nSize], eax
0x180007487  mov     eax, [rbx+44h]
0x18000748a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000748e  mov     r9, rdi; unsigned __int16 *
0x180007491  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007498  mov     rdx, rsi; unsigned __int16 *
0x18000749b  mov     rcx, r14; this
0x18000749e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074a3  cmp     [rbx+18h], r15
0x1800074a7  jnz     short loc_1800074B9
0x1800074a9  cmp     [rbx+48h], r15
0x1800074ad  jnz     short loc_1800074B9
0x1800074af  cmp     [rbx+30h], r15
0x1800074b3  jz      loc_180007549
0x1800074b9  lea     r8, asc_18002FEE0; "    "
0x1800074c0  mov     rdx, rsi; unsigned __int16 *
0x1800074c3  mov     rcx, rax; this
0x1800074c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074cb  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800074cf  test    r9, r9
0x1800074d2  jz      short loc_1800074E6
0x1800074d4  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800074db  mov     rdx, rsi; unsigned __int16 *
0x1800074de  mov     rcx, rax; this
0x1800074e1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800074e6  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800074ea  test    r9, r9
0x1800074ed  jz      short loc_180007501
0x1800074ef  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800074f6  mov     rdx, rsi; unsigned __int16 *
0x1800074f9  mov     rcx, rax; this
0x1800074fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007501  mov     rcx, [rbx+28h]
0x180007505  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007509  mov     rdx, rsi; unsigned __int16 *
0x18000750c  test    rcx, rcx
0x18000750f  jz      short loc_180007527
0x180007511  mov     [rsp+278h+lpBuffer], rcx
0x180007516  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000751d  mov     rcx, rax; this
0x180007520  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007525  jmp     short loc_180007549
0x180007527  mov     rcx, rax; this
0x18000752a  test    r9, r9
0x18000752d  jz      short loc_18000753D
0x18000752f  lea     r8, aHs; "[%hs]\n"
0x180007536  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000753b  jmp     short loc_180007549
0x18000753d  lea     r8, asc_18002FF58; "\n"
0x180007544  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007549  xor     eax, eax
0x18000754b  mov     rcx, [rsp+278h+var_38]
0x180007553  xor     rcx, rsp; StackCookie
0x180007556  call    __security_check_cookie
0x18000755b  mov     rbx, [rsp+278h+arg_18]
0x180007563  add     rsp, 250h
0x18000756a  pop     r15
0x18000756c  pop     r14
0x18000756e  pop     rdi
0x18000756f  pop     rsi
0x180007570  pop     rbp
0x180007571  retn
```
