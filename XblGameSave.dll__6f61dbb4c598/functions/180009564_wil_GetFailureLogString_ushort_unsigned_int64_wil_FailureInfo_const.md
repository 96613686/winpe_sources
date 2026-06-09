# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009564`
- end: `0x18000981a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800073e4`
- `0x18000a148`
- `0x18000c640`

## callees

- `0x180003c70`
- `0x180004754`
- `0x180009564`
- `0x18000a448`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009696`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009696`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009717`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009717`

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
          v7 = (const char *)&word_18009722A;
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
0x180009564  mov     [rsp+arg_18], rbx
0x180009569  push    rbp
0x18000956a  push    rsi
0x18000956b  push    rdi
0x18000956c  push    r14
0x18000956e  push    r15
0x180009570  sub     rsp, 250h
0x180009577  mov     rax, cs:__security_cookie
0x18000957e  xor     rax, rsp
0x180009581  mov     [rsp+278h+var_38], rax
0x180009589  mov     rbx, r8
0x18000958c  mov     rsi, rdx
0x18000958f  mov     r14, rcx
0x180009592  xor     r15d, r15d
0x180009595  test    rdx, rdx
0x180009598  jz      loc_1800097F1
0x18000959e  test    rcx, rcx
0x1800095a1  jz      loc_1800097F1
0x1800095a7  mov     [rcx], r15w
0x1800095ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095b2  test    rax, rax
0x1800095b5  jz      short loc_1800095D8
0x1800095b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800095be  jz      short loc_1800095D8
0x1800095c0  mov     r8, rdx
0x1800095c3  mov     rdx, rcx
0x1800095c6  mov     rcx, rbx
0x1800095c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095ce  cmp     [r14], r15w
0x1800095d2  jnz     loc_1800097F1
0x1800095d8  mov     ecx, [rbx]
0x1800095da  mov     bpl, 8
0x1800095dd  test    ecx, ecx
0x1800095df  jz      short loc_18000962A
0x1800095e1  sub     ecx, 1
0x1800095e4  jz      short loc_180009612
0x1800095e6  sub     ecx, 1
0x1800095e9  jz      short loc_180009602
0x1800095eb  cmp     ecx, 1
0x1800095ee  jz      short loc_1800095F9
0x1800095f0  lea     rdi, word_18009722A
0x1800095f7  jmp     short loc_180009631
0x1800095f9  lea     rdi, aFailfast; "FailFast"
0x180009600  jmp     short loc_180009631
0x180009602  lea     rax, aLoghr; "LogHr"
0x180009609  lea     rdi, aLognt; "LogNt"
0x180009610  jmp     short loc_180009620
0x180009612  lea     rax, aReturnhr; "ReturnHr"
0x180009619  lea     rdi, aReturnnt; "ReturnNt"
0x180009620  test    [rbx+4], bpl
0x180009624  cmovz   rdi, rax
0x180009628  jmp     short loc_180009631
0x18000962a  lea     rdi, aException; "Exception"
0x180009631  xor     edx, edx; Val
0x180009633  mov     r8d, 200h; Size
0x180009639  lea     rcx, [rsp+278h+Buffer]; void *
0x18000963e  call    memset_0
0x180009643  test    [rbx+4], bpl
0x180009647  jz      short loc_18000966C
0x180009649  mov     ebp, [rbx+0Ch]
0x18000964c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009653  test    rax, rax
0x180009656  jz      short loc_18000969C
0x180009658  mov     r8d, 100h
0x18000965e  lea     rdx, [rsp+278h+Buffer]
0x180009663  mov     ecx, ebp
0x180009665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000966a  jmp     short loc_18000969C
0x18000966c  mov     ebp, [rbx+8]
0x18000966f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009674  mov     [rsp+278h+nSize], 100h; nSize
0x18000967c  lea     rax, [rsp+278h+Buffer]
0x180009681  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009686  mov     r9d, 400h; dwLanguageId
0x18000968c  mov     r8d, ebp; dwMessageId
0x18000968f  xor     edx, edx; lpSource
0x180009691  mov     ecx, 1200h; dwFlags
0x180009696  call    cs:__imp_FormatMessageW
0x18000969c  lea     rsi, [r14+rsi*2]
0x1800096a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800096a4  mov     rax, [rbx+88h]
0x1800096ab  mov     rcx, [rbx+80h]
0x1800096b2  mov     rdx, rsi; unsigned __int16 *
0x1800096b5  test    r9, r9
0x1800096b8  jz      short loc_1800096DC
0x1800096ba  mov     [rsp+278h+Arguments], rax
0x1800096bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800096c4  mov     eax, [rbx+40h]
0x1800096c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800096cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800096d2  mov     rcx, r14; this
0x1800096d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800096da  jmp     short loc_1800096F3
0x1800096dc  mov     [rsp+278h+lpBuffer], rax
0x1800096e1  mov     r9, rcx; unsigned __int16 *
0x1800096e4  lea     r8, aHsP; "%hs!%p: "
0x1800096eb  mov     rcx, r14; this
0x1800096ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800096f3  mov     r14, rax
0x1800096f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800096fd  test    r9, r9
0x180009700  jz      short loc_180009717
0x180009702  lea     r8, aCallerP; "(caller: %p) "
0x180009709  mov     rdx, rsi; unsigned __int16 *
0x18000970c  mov     rcx, rax; this
0x18000970f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009714  mov     r14, rax
0x180009717  call    cs:__imp_GetCurrentThreadId
0x18000971d  lea     rcx, [rsp+278h+Buffer]
0x180009722  mov     [rsp+278h+var_240], rcx
0x180009727  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000972b  mov     [rsp+278h+nSize], eax
0x18000972f  mov     eax, [rbx+44h]
0x180009732  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009736  mov     r9, rdi; unsigned __int16 *
0x180009739  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009740  mov     rdx, rsi; unsigned __int16 *
0x180009743  mov     rcx, r14; this
0x180009746  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000974b  cmp     [rbx+18h], r15
0x18000974f  jnz     short loc_180009761
0x180009751  cmp     [rbx+48h], r15
0x180009755  jnz     short loc_180009761
0x180009757  cmp     [rbx+30h], r15
0x18000975b  jz      loc_1800097F1
0x180009761  lea     r8, asc_180096A70; "    "
0x180009768  mov     rdx, rsi; unsigned __int16 *
0x18000976b  mov     rcx, rax; this
0x18000976e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009773  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009777  test    r9, r9
0x18000977a  jz      short loc_18000978E
0x18000977c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009783  mov     rdx, rsi; unsigned __int16 *
0x180009786  mov     rcx, rax; this
0x180009789  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000978e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009792  test    r9, r9
0x180009795  jz      short loc_1800097A9
0x180009797  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000979e  mov     rdx, rsi; unsigned __int16 *
0x1800097a1  mov     rcx, rax; this
0x1800097a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097a9  mov     rcx, [rbx+28h]
0x1800097ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800097b1  mov     rdx, rsi; unsigned __int16 *
0x1800097b4  test    rcx, rcx
0x1800097b7  jz      short loc_1800097CF
0x1800097b9  mov     [rsp+278h+lpBuffer], rcx
0x1800097be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800097c5  mov     rcx, rax; this
0x1800097c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097cd  jmp     short loc_1800097F1
0x1800097cf  mov     rcx, rax; this
0x1800097d2  test    r9, r9
0x1800097d5  jz      short loc_1800097E5
0x1800097d7  lea     r8, aHs; "[%hs]\n"
0x1800097de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097e3  jmp     short loc_1800097F1
0x1800097e5  lea     r8, asc_180096AE8; "\n"
0x1800097ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097f1  xor     eax, eax
0x1800097f3  mov     rcx, [rsp+278h+var_38]
0x1800097fb  xor     rcx, rsp; StackCookie
0x1800097fe  call    __security_check_cookie
0x180009803  mov     rbx, [rsp+278h+arg_18]
0x18000980b  add     rsp, 250h
0x180009812  pop     r15
0x180009814  pop     r14
0x180009816  pop     rdi
0x180009817  pop     rsi
0x180009818  pop     rbp
0x180009819  retn
```
