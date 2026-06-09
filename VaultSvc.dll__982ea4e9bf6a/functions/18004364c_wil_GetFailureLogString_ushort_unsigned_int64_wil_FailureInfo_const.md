# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18004364c`
- end: `0x180043902`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800420e0`
- `0x180043d78`
- `0x1800459c0`

## callees

- `0x18003a580`
- `0x18003af10`
- `0x18004364c`
- `0x180044078`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800437ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800437ff`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004377e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004377e`

## pseudocode

```c
// Hidden C++ exception states: #wind=6
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
          v7 = (const char *)&qword_180053138;
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
0x18004364c  mov     [rsp+arg_18], rbx
0x180043651  push    rbp
0x180043652  push    rsi
0x180043653  push    rdi
0x180043654  push    r14
0x180043656  push    r15
0x180043658  sub     rsp, 250h
0x18004365f  mov     rax, cs:__security_cookie
0x180043666  xor     rax, rsp
0x180043669  mov     [rsp+278h+var_38], rax
0x180043671  mov     rbx, r8
0x180043674  mov     rsi, rdx
0x180043677  mov     r14, rcx
0x18004367a  xor     r15d, r15d
0x18004367d  test    rdx, rdx
0x180043680  jz      loc_1800438D9
0x180043686  test    rcx, rcx
0x180043689  jz      loc_1800438D9
0x18004368f  mov     [rcx], r15w
0x180043693  mov     rax, cs:g_pfnResultLoggingCallback
0x18004369a  test    rax, rax
0x18004369d  jz      short loc_1800436C0
0x18004369f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800436a6  jz      short loc_1800436C0
0x1800436a8  mov     r8, rdx
0x1800436ab  mov     rdx, rcx
0x1800436ae  mov     rcx, rbx
0x1800436b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800436b6  cmp     [r14], r15w
0x1800436ba  jnz     loc_1800438D9
0x1800436c0  mov     ecx, [rbx]
0x1800436c2  mov     bpl, 8
0x1800436c5  test    ecx, ecx
0x1800436c7  jz      short loc_180043712
0x1800436c9  sub     ecx, 1
0x1800436cc  jz      short loc_1800436FA
0x1800436ce  sub     ecx, 1
0x1800436d1  jz      short loc_1800436EA
0x1800436d3  cmp     ecx, 1
0x1800436d6  jz      short loc_1800436E1
0x1800436d8  lea     rdi, qword_180053138
0x1800436df  jmp     short loc_180043719
0x1800436e1  lea     rdi, aFailfast; "FailFast"
0x1800436e8  jmp     short loc_180043719
0x1800436ea  lea     rax, aLoghr; "LogHr"
0x1800436f1  lea     rdi, aLognt; "LogNt"
0x1800436f8  jmp     short loc_180043708
0x1800436fa  lea     rax, aReturnhr; "ReturnHr"
0x180043701  lea     rdi, aReturnnt; "ReturnNt"
0x180043708  test    [rbx+4], bpl
0x18004370c  cmovz   rdi, rax
0x180043710  jmp     short loc_180043719
0x180043712  lea     rdi, aException; "Exception"
0x180043719  xor     edx, edx; Val
0x18004371b  mov     r8d, 200h; Size
0x180043721  lea     rcx, [rsp+278h+Buffer]; void *
0x180043726  call    memset_0
0x18004372b  test    [rbx+4], bpl
0x18004372f  jz      short loc_180043754
0x180043731  mov     ebp, [rbx+0Ch]
0x180043734  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18004373b  test    rax, rax
0x18004373e  jz      short loc_180043784
0x180043740  mov     r8d, 100h
0x180043746  lea     rdx, [rsp+278h+Buffer]
0x18004374b  mov     ecx, ebp
0x18004374d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180043752  jmp     short loc_180043784
0x180043754  mov     ebp, [rbx+8]
0x180043757  mov     [rsp+278h+Arguments], r15; Arguments
0x18004375c  mov     [rsp+278h+nSize], 100h; nSize
0x180043764  lea     rax, [rsp+278h+Buffer]
0x180043769  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18004376e  mov     r9d, 400h; dwLanguageId
0x180043774  mov     r8d, ebp; dwMessageId
0x180043777  xor     edx, edx; lpSource
0x180043779  mov     ecx, 1200h; dwFlags
0x18004377e  call    cs:__imp_FormatMessageW
0x180043784  lea     rsi, [r14+rsi*2]
0x180043788  mov     r9, [rbx+38h]; unsigned __int16 *
0x18004378c  mov     rax, [rbx+88h]
0x180043793  mov     rcx, [rbx+80h]
0x18004379a  mov     rdx, rsi; unsigned __int16 *
0x18004379d  test    r9, r9
0x1800437a0  jz      short loc_1800437C4
0x1800437a2  mov     [rsp+278h+Arguments], rax
0x1800437a7  mov     qword ptr [rsp+278h+nSize], rcx
0x1800437ac  mov     eax, [rbx+40h]
0x1800437af  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800437b3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800437ba  mov     rcx, r14; this
0x1800437bd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800437c2  jmp     short loc_1800437DB
0x1800437c4  mov     [rsp+278h+lpBuffer], rax
0x1800437c9  mov     r9, rcx; unsigned __int16 *
0x1800437cc  lea     r8, aHsP; "%hs!%p: "
0x1800437d3  mov     rcx, r14; this
0x1800437d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800437db  mov     r14, rax
0x1800437de  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800437e5  test    r9, r9
0x1800437e8  jz      short loc_1800437FF
0x1800437ea  lea     r8, aCallerP; "(caller: %p) "
0x1800437f1  mov     rdx, rsi; unsigned __int16 *
0x1800437f4  mov     rcx, rax; this
0x1800437f7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800437fc  mov     r14, rax
0x1800437ff  call    cs:__imp_GetCurrentThreadId
0x180043805  lea     rcx, [rsp+278h+Buffer]
0x18004380a  mov     [rsp+278h+var_240], rcx
0x18004380f  mov     dword ptr [rsp+278h+Arguments], ebp
0x180043813  mov     [rsp+278h+nSize], eax
0x180043817  mov     eax, [rbx+44h]
0x18004381a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18004381e  mov     r9, rdi; unsigned __int16 *
0x180043821  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180043828  mov     rdx, rsi; unsigned __int16 *
0x18004382b  mov     rcx, r14; this
0x18004382e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180043833  cmp     [rbx+18h], r15
0x180043837  jnz     short loc_180043849
0x180043839  cmp     [rbx+48h], r15
0x18004383d  jnz     short loc_180043849
0x18004383f  cmp     [rbx+30h], r15
0x180043843  jz      loc_1800438D9
0x180043849  lea     r8, asc_180052E80; "    "
0x180043850  mov     rdx, rsi; unsigned __int16 *
0x180043853  mov     rcx, rax; this
0x180043856  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004385b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18004385f  test    r9, r9
0x180043862  jz      short loc_180043876
0x180043864  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004386b  mov     rdx, rsi; unsigned __int16 *
0x18004386e  mov     rcx, rax; this
0x180043871  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180043876  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004387a  test    r9, r9
0x18004387d  jz      short loc_180043891
0x18004387f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180043886  mov     rdx, rsi; unsigned __int16 *
0x180043889  mov     rcx, rax; this
0x18004388c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180043891  mov     rcx, [rbx+28h]
0x180043895  mov     r9, [rbx+30h]; unsigned __int16 *
0x180043899  mov     rdx, rsi; unsigned __int16 *
0x18004389c  test    rcx, rcx
0x18004389f  jz      short loc_1800438B7
0x1800438a1  mov     [rsp+278h+lpBuffer], rcx
0x1800438a6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800438ad  mov     rcx, rax; this
0x1800438b0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800438b5  jmp     short loc_1800438D9
0x1800438b7  mov     rcx, rax; this
0x1800438ba  test    r9, r9
0x1800438bd  jz      short loc_1800438CD
0x1800438bf  lea     r8, aHs; "[%hs]\n"
0x1800438c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800438cb  jmp     short loc_1800438D9
0x1800438cd  lea     r8, asc_180052EF8; "\n"
0x1800438d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800438d9  xor     eax, eax
0x1800438db  mov     rcx, [rsp+278h+var_38]
0x1800438e3  xor     rcx, rsp; StackCookie
0x1800438e6  call    __security_check_cookie
0x1800438eb  mov     rbx, [rsp+278h+arg_18]
0x1800438f3  add     rsp, 250h
0x1800438fa  pop     r15
0x1800438fc  pop     r14
0x1800438fe  pop     rdi
0x1800438ff  pop     rsi
0x180043900  pop     rbp
0x180043901  retn
```
