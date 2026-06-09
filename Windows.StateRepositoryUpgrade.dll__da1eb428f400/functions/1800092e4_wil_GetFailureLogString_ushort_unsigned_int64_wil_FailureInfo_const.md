# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800092e4`
- end: `0x18000959a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180008664`
- `0x180009c8c`

## callees

- `0x180003980`
- `0x1800042f4`
- `0x1800092e4`
- `0x180009f8c`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009497`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009497`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009416`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009416`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
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
          v8 = (const char *)&dword_180034EEC;
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
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800092e4  mov     [rsp+arg_18], rbx
0x1800092e9  push    rbp
0x1800092ea  push    rsi
0x1800092eb  push    rdi
0x1800092ec  push    r14
0x1800092ee  push    r15
0x1800092f0  sub     rsp, 250h
0x1800092f7  mov     rax, cs:__security_cookie
0x1800092fe  xor     rax, rsp
0x180009301  mov     [rsp+278h+var_38], rax
0x180009309  xor     r15d, r15d
0x18000930c  mov     rbx, r8
0x18000930f  mov     rsi, rdx
0x180009312  mov     r14, rcx
0x180009315  test    rdx, rdx
0x180009318  jz      loc_180009571
0x18000931e  test    rcx, rcx
0x180009321  jz      loc_180009571
0x180009327  mov     rax, cs:g_pfnResultLoggingCallback
0x18000932e  mov     [rcx], r15w
0x180009332  test    rax, rax
0x180009335  jz      short loc_180009358
0x180009337  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000933e  jz      short loc_180009358
0x180009340  mov     r8, rdx
0x180009343  mov     rdx, rcx
0x180009346  mov     rcx, rbx
0x180009349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000934e  cmp     [r14], r15w
0x180009352  jnz     loc_180009571
0x180009358  mov     ecx, [rbx]
0x18000935a  mov     bpl, 8
0x18000935d  test    ecx, ecx
0x18000935f  jz      short loc_1800093AA
0x180009361  sub     ecx, 1
0x180009364  jz      short loc_180009392
0x180009366  sub     ecx, 1
0x180009369  jz      short loc_180009382
0x18000936b  cmp     ecx, 1
0x18000936e  jz      short loc_180009379
0x180009370  lea     rdi, dword_180034EEC
0x180009377  jmp     short loc_1800093B1
0x180009379  lea     rdi, aFailfast; "FailFast"
0x180009380  jmp     short loc_1800093B1
0x180009382  lea     rax, aLoghr; "LogHr"
0x180009389  lea     rdi, aLognt; "LogNt"
0x180009390  jmp     short loc_1800093A0
0x180009392  lea     rax, aReturnhr; "ReturnHr"
0x180009399  lea     rdi, aReturnnt; "ReturnNt"
0x1800093a0  test    [rbx+4], bpl
0x1800093a4  cmovz   rdi, rax
0x1800093a8  jmp     short loc_1800093B1
0x1800093aa  lea     rdi, aException; "Exception"
0x1800093b1  xor     edx, edx; Val
0x1800093b3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800093b8  mov     r8d, 200h; Size
0x1800093be  call    memset_0
0x1800093c3  test    [rbx+4], bpl
0x1800093c7  jz      short loc_1800093EC
0x1800093c9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800093d0  mov     ebp, [rbx+0Ch]
0x1800093d3  test    rax, rax
0x1800093d6  jz      short loc_18000941C
0x1800093d8  mov     r8d, 100h
0x1800093de  lea     rdx, [rsp+278h+Buffer]
0x1800093e3  mov     ecx, ebp
0x1800093e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093ea  jmp     short loc_18000941C
0x1800093ec  mov     ebp, [rbx+8]
0x1800093ef  lea     rax, [rsp+278h+Buffer]
0x1800093f4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800093f9  mov     r8d, ebp; dwMessageId
0x1800093fc  mov     [rsp+278h+nSize], 100h; nSize
0x180009404  mov     r9d, 400h; dwLanguageId
0x18000940a  xor     edx, edx; lpSource
0x18000940c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009411  mov     ecx, 1200h; dwFlags
0x180009416  call    cs:__imp_FormatMessageW
0x18000941c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009420  lea     rsi, [r14+rsi*2]
0x180009424  mov     rax, [rbx+88h]
0x18000942b  mov     rdx, rsi; unsigned __int16 *
0x18000942e  mov     rcx, [rbx+80h]
0x180009435  test    r9, r9
0x180009438  jz      short loc_18000945C
0x18000943a  mov     [rsp+278h+Arguments], rax
0x18000943f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009446  mov     eax, [rbx+40h]
0x180009449  mov     qword ptr [rsp+278h+nSize], rcx
0x18000944e  mov     rcx, r14; this
0x180009451  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009455  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000945a  jmp     short loc_180009473
0x18000945c  mov     r9, rcx; unsigned __int16 *
0x18000945f  mov     [rsp+278h+lpBuffer], rax
0x180009464  mov     rcx, r14; this
0x180009467  lea     r8, aHsP; "%hs!%p: "
0x18000946e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009473  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000947a  mov     r14, rax
0x18000947d  test    r9, r9
0x180009480  jz      short loc_180009497
0x180009482  lea     r8, aCallerP; "(caller: %p) "
0x180009489  mov     rdx, rsi; unsigned __int16 *
0x18000948c  mov     rcx, rax; this
0x18000948f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009494  mov     r14, rax
0x180009497  call    cs:__imp_GetCurrentThreadId
0x18000949d  lea     rcx, [rsp+278h+Buffer]
0x1800094a2  mov     r9, rdi; unsigned __int16 *
0x1800094a5  mov     [rsp+278h+var_240], rcx
0x1800094aa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800094b1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800094b5  mov     rdx, rsi; unsigned __int16 *
0x1800094b8  mov     [rsp+278h+nSize], eax
0x1800094bc  mov     rcx, r14; this
0x1800094bf  mov     eax, [rbx+44h]
0x1800094c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800094c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094cb  cmp     [rbx+18h], r15
0x1800094cf  jnz     short loc_1800094E1
0x1800094d1  cmp     [rbx+48h], r15
0x1800094d5  jnz     short loc_1800094E1
0x1800094d7  cmp     [rbx+30h], r15
0x1800094db  jz      loc_180009571
0x1800094e1  lea     r8, asc_180034FD8; "    "
0x1800094e8  mov     rdx, rsi; unsigned __int16 *
0x1800094eb  mov     rcx, rax; this
0x1800094ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800094f7  test    r9, r9
0x1800094fa  jz      short loc_18000950E
0x1800094fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009503  mov     rdx, rsi; unsigned __int16 *
0x180009506  mov     rcx, rax; this
0x180009509  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000950e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009512  test    r9, r9
0x180009515  jz      short loc_180009529
0x180009517  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000951e  mov     rdx, rsi; unsigned __int16 *
0x180009521  mov     rcx, rax; this
0x180009524  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009529  mov     rcx, [rbx+28h]
0x18000952d  mov     rdx, rsi; unsigned __int16 *
0x180009530  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009534  test    rcx, rcx
0x180009537  jz      short loc_18000954F
0x180009539  mov     [rsp+278h+lpBuffer], rcx
0x18000953e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009545  mov     rcx, rax; this
0x180009548  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000954d  jmp     short loc_180009571
0x18000954f  mov     rcx, rax; this
0x180009552  test    r9, r9
0x180009555  jz      short loc_180009565
0x180009557  lea     r8, aHs; "[%hs]\n"
0x18000955e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009563  jmp     short loc_180009571
0x180009565  lea     r8, asc_180035050; "\n"
0x18000956c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009571  xor     eax, eax
0x180009573  mov     rcx, [rsp+278h+var_38]
0x18000957b  xor     rcx, rsp; StackCookie
0x18000957e  call    __security_check_cookie
0x180009583  mov     rbx, [rsp+278h+arg_18]
0x18000958b  add     rsp, 250h
0x180009592  pop     r15
0x180009594  pop     r14
0x180009596  pop     rdi
0x180009597  pop     rsi
0x180009598  pop     rbp
0x180009599  retn
```
