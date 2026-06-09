# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800024c4`
- end: `0x18000277a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180001d60`
- `0x180001fc4`

## callees

- `0x1800024c4`
- `0x180002a70`
- `0x1800040f6`
- `0x180004130`
- `0x180005010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800025f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800025f6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002677`

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
          v8 = (const char *)&qword_180006C80;
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
0x1800024c4  mov     [rsp+arg_18], rbx
0x1800024c9  push    rbp
0x1800024ca  push    rsi
0x1800024cb  push    rdi
0x1800024cc  push    r14
0x1800024ce  push    r15
0x1800024d0  sub     rsp, 250h
0x1800024d7  mov     rax, cs:__security_cookie
0x1800024de  xor     rax, rsp
0x1800024e1  mov     [rsp+278h+var_38], rax
0x1800024e9  xor     r15d, r15d
0x1800024ec  mov     rbx, r8
0x1800024ef  mov     rsi, rdx
0x1800024f2  mov     r14, rcx
0x1800024f5  test    rdx, rdx
0x1800024f8  jz      loc_180002751
0x1800024fe  test    rcx, rcx
0x180002501  jz      loc_180002751
0x180002507  mov     rax, cs:g_pfnResultLoggingCallback
0x18000250e  mov     [rcx], r15w
0x180002512  test    rax, rax
0x180002515  jz      short loc_180002538
0x180002517  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000251e  jz      short loc_180002538
0x180002520  mov     r8, rdx
0x180002523  mov     rdx, rcx
0x180002526  mov     rcx, rbx
0x180002529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000252e  cmp     [r14], r15w
0x180002532  jnz     loc_180002751
0x180002538  mov     ecx, [rbx]
0x18000253a  mov     bpl, 8
0x18000253d  test    ecx, ecx
0x18000253f  jz      short loc_18000258A
0x180002541  sub     ecx, 1
0x180002544  jz      short loc_180002572
0x180002546  sub     ecx, 1
0x180002549  jz      short loc_180002562
0x18000254b  cmp     ecx, 1
0x18000254e  jz      short loc_180002559
0x180002550  lea     rdi, qword_180006C80
0x180002557  jmp     short loc_180002591
0x180002559  lea     rdi, aFailfast; "FailFast"
0x180002560  jmp     short loc_180002591
0x180002562  lea     rax, aLoghr; "LogHr"
0x180002569  lea     rdi, aLognt; "LogNt"
0x180002570  jmp     short loc_180002580
0x180002572  lea     rax, aReturnhr; "ReturnHr"
0x180002579  lea     rdi, aReturnnt; "ReturnNt"
0x180002580  test    [rbx+4], bpl
0x180002584  cmovz   rdi, rax
0x180002588  jmp     short loc_180002591
0x18000258a  lea     rdi, aException; "Exception"
0x180002591  xor     edx, edx; Val
0x180002593  lea     rcx, [rsp+278h+Buffer]; void *
0x180002598  mov     r8d, 200h; Size
0x18000259e  call    memset_0
0x1800025a3  test    [rbx+4], bpl
0x1800025a7  jz      short loc_1800025CC
0x1800025a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800025b0  mov     ebp, [rbx+0Ch]
0x1800025b3  test    rax, rax
0x1800025b6  jz      short loc_1800025FC
0x1800025b8  mov     r8d, 100h
0x1800025be  lea     rdx, [rsp+278h+Buffer]
0x1800025c3  mov     ecx, ebp
0x1800025c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ca  jmp     short loc_1800025FC
0x1800025cc  mov     ebp, [rbx+8]
0x1800025cf  lea     rax, [rsp+278h+Buffer]
0x1800025d4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800025d9  mov     r8d, ebp; dwMessageId
0x1800025dc  mov     [rsp+278h+nSize], 100h; nSize
0x1800025e4  mov     r9d, 400h; dwLanguageId
0x1800025ea  xor     edx, edx; lpSource
0x1800025ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800025f1  mov     ecx, 1200h; dwFlags
0x1800025f6  call    cs:__imp_FormatMessageW
0x1800025fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180002600  lea     rsi, [r14+rsi*2]
0x180002604  mov     rax, [rbx+88h]
0x18000260b  mov     rdx, rsi; unsigned __int16 *
0x18000260e  mov     rcx, [rbx+80h]
0x180002615  test    r9, r9
0x180002618  jz      short loc_18000263C
0x18000261a  mov     [rsp+278h+Arguments], rax
0x18000261f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002626  mov     eax, [rbx+40h]
0x180002629  mov     qword ptr [rsp+278h+nSize], rcx
0x18000262e  mov     rcx, r14; this
0x180002631  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002635  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000263a  jmp     short loc_180002653
0x18000263c  mov     r9, rcx; unsigned __int16 *
0x18000263f  mov     [rsp+278h+lpBuffer], rax
0x180002644  mov     rcx, r14; this
0x180002647  lea     r8, aHsP; "%hs!%p: "
0x18000264e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002653  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000265a  mov     r14, rax
0x18000265d  test    r9, r9
0x180002660  jz      short loc_180002677
0x180002662  lea     r8, aCallerP; "(caller: %p) "
0x180002669  mov     rdx, rsi; unsigned __int16 *
0x18000266c  mov     rcx, rax; this
0x18000266f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002674  mov     r14, rax
0x180002677  call    cs:__imp_GetCurrentThreadId
0x18000267d  lea     rcx, [rsp+278h+Buffer]
0x180002682  mov     r9, rdi; unsigned __int16 *
0x180002685  mov     [rsp+278h+var_240], rcx
0x18000268a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002691  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002695  mov     rdx, rsi; unsigned __int16 *
0x180002698  mov     [rsp+278h+nSize], eax
0x18000269c  mov     rcx, r14; this
0x18000269f  mov     eax, [rbx+44h]
0x1800026a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800026a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800026ab  cmp     [rbx+18h], r15
0x1800026af  jnz     short loc_1800026C1
0x1800026b1  cmp     [rbx+48h], r15
0x1800026b5  jnz     short loc_1800026C1
0x1800026b7  cmp     [rbx+30h], r15
0x1800026bb  jz      loc_180002751
0x1800026c1  lea     r8, asc_180006628; "    "
0x1800026c8  mov     rdx, rsi; unsigned __int16 *
0x1800026cb  mov     rcx, rax; this
0x1800026ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800026d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800026d7  test    r9, r9
0x1800026da  jz      short loc_1800026EE
0x1800026dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800026e3  mov     rdx, rsi; unsigned __int16 *
0x1800026e6  mov     rcx, rax; this
0x1800026e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800026ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800026f2  test    r9, r9
0x1800026f5  jz      short loc_180002709
0x1800026f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800026fe  mov     rdx, rsi; unsigned __int16 *
0x180002701  mov     rcx, rax; this
0x180002704  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002709  mov     rcx, [rbx+28h]
0x18000270d  mov     rdx, rsi; unsigned __int16 *
0x180002710  mov     r9, [rbx+30h]; unsigned __int16 *
0x180002714  test    rcx, rcx
0x180002717  jz      short loc_18000272F
0x180002719  mov     [rsp+278h+lpBuffer], rcx
0x18000271e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180002725  mov     rcx, rax; this
0x180002728  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000272d  jmp     short loc_180002751
0x18000272f  mov     rcx, rax; this
0x180002732  test    r9, r9
0x180002735  jz      short loc_180002745
0x180002737  lea     r8, aHs; "[%hs]\n"
0x18000273e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002743  jmp     short loc_180002751
0x180002745  lea     r8, asc_1800066A0; "\n"
0x18000274c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180002751  xor     eax, eax
0x180002753  mov     rcx, [rsp+278h+var_38]
0x18000275b  xor     rcx, rsp; StackCookie
0x18000275e  call    __security_check_cookie
0x180002763  mov     rbx, [rsp+278h+arg_18]
0x18000276b  add     rsp, 250h
0x180002772  pop     r15
0x180002774  pop     r14
0x180002776  pop     rdi
0x180002777  pop     rsi
0x180002778  pop     rbp
0x180002779  retn
```
