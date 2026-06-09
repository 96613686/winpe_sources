# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180046884`
- end: `0x180046b3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003da3c`

## callees

- `0x180044f30`
- `0x180045900`
- `0x180046884`
- `0x180046fa8`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180046a37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800469b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800469b6`

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
          v8 = pszFormat;
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
0x180046884  mov     [rsp+arg_18], rbx
0x180046889  push    rbp
0x18004688a  push    rsi
0x18004688b  push    rdi
0x18004688c  push    r14
0x18004688e  push    r15
0x180046890  sub     rsp, 250h
0x180046897  mov     rax, cs:__security_cookie
0x18004689e  xor     rax, rsp
0x1800468a1  mov     [rsp+278h+var_38], rax
0x1800468a9  xor     r15d, r15d
0x1800468ac  mov     rbx, r8
0x1800468af  mov     rsi, rdx
0x1800468b2  mov     r14, rcx
0x1800468b5  test    rdx, rdx
0x1800468b8  jz      loc_180046B11
0x1800468be  test    rcx, rcx
0x1800468c1  jz      loc_180046B11
0x1800468c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800468ce  mov     [rcx], r15w
0x1800468d2  test    rax, rax
0x1800468d5  jz      short loc_1800468F8
0x1800468d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800468de  jz      short loc_1800468F8
0x1800468e0  mov     r8, rdx
0x1800468e3  mov     rdx, rcx
0x1800468e6  mov     rcx, rbx
0x1800468e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800468ee  cmp     [r14], r15w
0x1800468f2  jnz     loc_180046B11
0x1800468f8  mov     ecx, [rbx]
0x1800468fa  mov     bpl, 8
0x1800468fd  test    ecx, ecx
0x1800468ff  jz      short loc_18004694A
0x180046901  sub     ecx, 1
0x180046904  jz      short loc_180046932
0x180046906  sub     ecx, 1
0x180046909  jz      short loc_180046922
0x18004690b  cmp     ecx, 1
0x18004690e  jz      short loc_180046919
0x180046910  lea     rdi, pszFormat
0x180046917  jmp     short loc_180046951
0x180046919  lea     rdi, aFailfast; "FailFast"
0x180046920  jmp     short loc_180046951
0x180046922  lea     rax, aLoghr; "LogHr"
0x180046929  lea     rdi, aLognt; "LogNt"
0x180046930  jmp     short loc_180046940
0x180046932  lea     rax, aReturnhr; "ReturnHr"
0x180046939  lea     rdi, aReturnnt; "ReturnNt"
0x180046940  test    [rbx+4], bpl
0x180046944  cmovz   rdi, rax
0x180046948  jmp     short loc_180046951
0x18004694a  lea     rdi, aException; "Exception"
0x180046951  xor     edx, edx; Val
0x180046953  lea     rcx, [rsp+278h+Buffer]; void *
0x180046958  mov     r8d, 200h; Size
0x18004695e  call    memset_0
0x180046963  test    [rbx+4], bpl
0x180046967  jz      short loc_18004698C
0x180046969  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180046970  mov     ebp, [rbx+0Ch]
0x180046973  test    rax, rax
0x180046976  jz      short loc_1800469BC
0x180046978  mov     r8d, 100h
0x18004697e  lea     rdx, [rsp+278h+Buffer]
0x180046983  mov     ecx, ebp
0x180046985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004698a  jmp     short loc_1800469BC
0x18004698c  mov     ebp, [rbx+8]
0x18004698f  lea     rax, [rsp+278h+Buffer]
0x180046994  mov     [rsp+278h+Arguments], r15; Arguments
0x180046999  mov     r8d, ebp; dwMessageId
0x18004699c  mov     [rsp+278h+nSize], 100h; nSize
0x1800469a4  mov     r9d, 400h; dwLanguageId
0x1800469aa  xor     edx, edx; lpSource
0x1800469ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800469b1  mov     ecx, 1200h; dwFlags
0x1800469b6  call    cs:__imp_FormatMessageW
0x1800469bc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800469c0  lea     rsi, [r14+rsi*2]
0x1800469c4  mov     rax, [rbx+88h]
0x1800469cb  mov     rdx, rsi; unsigned __int16 *
0x1800469ce  mov     rcx, [rbx+80h]
0x1800469d5  test    r9, r9
0x1800469d8  jz      short loc_1800469FC
0x1800469da  mov     [rsp+278h+Arguments], rax
0x1800469df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800469e6  mov     eax, [rbx+40h]
0x1800469e9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800469ee  mov     rcx, r14; this
0x1800469f1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800469f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800469fa  jmp     short loc_180046A13
0x1800469fc  mov     r9, rcx; unsigned __int16 *
0x1800469ff  mov     [rsp+278h+lpBuffer], rax
0x180046a04  mov     rcx, r14; this
0x180046a07  lea     r8, aHsP; "%hs!%p: "
0x180046a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046a13  mov     r9, [rbx+90h]; unsigned __int16 *
0x180046a1a  mov     r14, rax
0x180046a1d  test    r9, r9
0x180046a20  jz      short loc_180046A37
0x180046a22  lea     r8, aCallerP; "(caller: %p) "
0x180046a29  mov     rdx, rsi; unsigned __int16 *
0x180046a2c  mov     rcx, rax; this
0x180046a2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046a34  mov     r14, rax
0x180046a37  call    cs:__imp_GetCurrentThreadId
0x180046a3d  lea     rcx, [rsp+278h+Buffer]
0x180046a42  mov     r9, rdi; unsigned __int16 *
0x180046a45  mov     [rsp+278h+var_240], rcx
0x180046a4a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180046a51  mov     dword ptr [rsp+278h+Arguments], ebp
0x180046a55  mov     rdx, rsi; unsigned __int16 *
0x180046a58  mov     [rsp+278h+nSize], eax
0x180046a5c  mov     rcx, r14; this
0x180046a5f  mov     eax, [rbx+44h]
0x180046a62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180046a66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046a6b  cmp     [rbx+18h], r15
0x180046a6f  jnz     short loc_180046A81
0x180046a71  cmp     [rbx+48h], r15
0x180046a75  jnz     short loc_180046A81
0x180046a77  cmp     [rbx+30h], r15
0x180046a7b  jz      loc_180046B11
0x180046a81  lea     r8, asc_18007E1A0; "    "
0x180046a88  mov     rdx, rsi; unsigned __int16 *
0x180046a8b  mov     rcx, rax; this
0x180046a8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046a93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180046a97  test    r9, r9
0x180046a9a  jz      short loc_180046AAE
0x180046a9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180046aa3  mov     rdx, rsi; unsigned __int16 *
0x180046aa6  mov     rcx, rax; this
0x180046aa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046aae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180046ab2  test    r9, r9
0x180046ab5  jz      short loc_180046AC9
0x180046ab7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180046abe  mov     rdx, rsi; unsigned __int16 *
0x180046ac1  mov     rcx, rax; this
0x180046ac4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046ac9  mov     rcx, [rbx+28h]
0x180046acd  mov     rdx, rsi; unsigned __int16 *
0x180046ad0  mov     r9, [rbx+30h]; unsigned __int16 *
0x180046ad4  test    rcx, rcx
0x180046ad7  jz      short loc_180046AEF
0x180046ad9  mov     [rsp+278h+lpBuffer], rcx
0x180046ade  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180046ae5  mov     rcx, rax; this
0x180046ae8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046aed  jmp     short loc_180046B11
0x180046aef  mov     rcx, rax; this
0x180046af2  test    r9, r9
0x180046af5  jz      short loc_180046B05
0x180046af7  lea     r8, aHs; "[%hs]\n"
0x180046afe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046b03  jmp     short loc_180046B11
0x180046b05  lea     r8, asc_18007E218; "\n"
0x180046b0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046b11  xor     eax, eax
0x180046b13  mov     rcx, [rsp+278h+var_38]
0x180046b1b  xor     rcx, rsp; StackCookie
0x180046b1e  call    __security_check_cookie
0x180046b23  mov     rbx, [rsp+278h+arg_18]
0x180046b2b  add     rsp, 250h
0x180046b32  pop     r15
0x180046b34  pop     r14
0x180046b36  pop     rdi
0x180046b37  pop     rsi
0x180046b38  pop     rbp
0x180046b39  retn
```
