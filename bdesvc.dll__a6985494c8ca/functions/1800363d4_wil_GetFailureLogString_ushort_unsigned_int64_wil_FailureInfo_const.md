# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800363d4`
- end: `0x180036697`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180025a9c`
- `0x180036e14`
- `0x180038510`

## callees

- `0x180034070`
- `0x180034d28`
- `0x1800363d4`
- `0x180036b2c`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003658d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003658d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180036506`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180036506`

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
          v7 = (const char *)&dword_180086DE4;
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
0x1800363d4  mov     [rsp+arg_18], rbx
0x1800363d9  push    rbp
0x1800363da  push    rsi
0x1800363db  push    rdi
0x1800363dc  push    r14
0x1800363de  push    r15
0x1800363e0  sub     rsp, 250h
0x1800363e7  mov     rax, cs:__security_cookie
0x1800363ee  xor     rax, rsp
0x1800363f1  mov     [rsp+278h+var_38], rax
0x1800363f9  mov     rbx, r8
0x1800363fc  mov     rsi, rdx
0x1800363ff  mov     r14, rcx
0x180036402  xor     r15d, r15d
0x180036405  test    rdx, rdx
0x180036408  jz      loc_18003666D
0x18003640e  test    rcx, rcx
0x180036411  jz      loc_18003666D
0x180036417  mov     [rcx], r15w
0x18003641b  mov     rax, cs:g_pfnResultLoggingCallback
0x180036422  test    rax, rax
0x180036425  jz      short loc_180036448
0x180036427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003642e  jz      short loc_180036448
0x180036430  mov     r8, rdx
0x180036433  mov     rdx, rcx
0x180036436  mov     rcx, rbx
0x180036439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003643e  cmp     [r14], r15w
0x180036442  jnz     loc_18003666D
0x180036448  mov     ecx, [rbx]
0x18003644a  mov     bpl, 8
0x18003644d  test    ecx, ecx
0x18003644f  jz      short loc_18003649A
0x180036451  sub     ecx, 1
0x180036454  jz      short loc_180036482
0x180036456  sub     ecx, 1
0x180036459  jz      short loc_180036472
0x18003645b  cmp     ecx, 1
0x18003645e  jz      short loc_180036469
0x180036460  lea     rdi, dword_180086DE4
0x180036467  jmp     short loc_1800364A1
0x180036469  lea     rdi, aFailfast; "FailFast"
0x180036470  jmp     short loc_1800364A1
0x180036472  lea     rax, aLoghr; "LogHr"
0x180036479  lea     rdi, aLognt; "LogNt"
0x180036480  jmp     short loc_180036490
0x180036482  lea     rax, aReturnhr; "ReturnHr"
0x180036489  lea     rdi, aReturnnt; "ReturnNt"
0x180036490  test    [rbx+4], bpl
0x180036494  cmovz   rdi, rax
0x180036498  jmp     short loc_1800364A1
0x18003649a  lea     rdi, aException; "Exception"
0x1800364a1  xor     edx, edx; Val
0x1800364a3  mov     r8d, 200h; Size
0x1800364a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800364ae  call    memset_0
0x1800364b3  test    [rbx+4], bpl
0x1800364b7  jz      short loc_1800364DC
0x1800364b9  mov     ebp, [rbx+0Ch]
0x1800364bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800364c3  test    rax, rax
0x1800364c6  jz      short loc_180036512
0x1800364c8  mov     r8d, 100h
0x1800364ce  lea     rdx, [rsp+278h+Buffer]
0x1800364d3  mov     ecx, ebp
0x1800364d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800364da  jmp     short loc_180036512
0x1800364dc  mov     ebp, [rbx+8]
0x1800364df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800364e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800364ec  lea     rax, [rsp+278h+Buffer]
0x1800364f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800364f6  mov     r9d, 400h; dwLanguageId
0x1800364fc  mov     r8d, ebp; dwMessageId
0x1800364ff  xor     edx, edx; lpSource
0x180036501  mov     ecx, 1200h; dwFlags
0x180036506  call    cs:__imp_FormatMessageW
0x18003650d  nop     dword ptr [rax+rax+00h]
0x180036512  lea     rsi, [r14+rsi*2]
0x180036516  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003651a  mov     rax, [rbx+88h]
0x180036521  mov     rcx, [rbx+80h]
0x180036528  mov     rdx, rsi; unsigned __int16 *
0x18003652b  test    r9, r9
0x18003652e  jz      short loc_180036552
0x180036530  mov     [rsp+278h+Arguments], rax
0x180036535  mov     qword ptr [rsp+278h+nSize], rcx
0x18003653a  mov     eax, [rbx+40h]
0x18003653d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180036541  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180036548  mov     rcx, r14; this
0x18003654b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036550  jmp     short loc_180036569
0x180036552  mov     [rsp+278h+lpBuffer], rax
0x180036557  mov     r9, rcx; unsigned __int16 *
0x18003655a  lea     r8, aHsP; "%hs!%p: "
0x180036561  mov     rcx, r14; this
0x180036564  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036569  mov     r14, rax
0x18003656c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180036573  test    r9, r9
0x180036576  jz      short loc_18003658D
0x180036578  lea     r8, aCallerP; "(caller: %p) "
0x18003657f  mov     rdx, rsi; unsigned __int16 *
0x180036582  mov     rcx, rax; this
0x180036585  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003658a  mov     r14, rax
0x18003658d  call    cs:__imp_GetCurrentThreadId
0x180036594  nop     dword ptr [rax+rax+00h]
0x180036599  lea     rcx, [rsp+278h+Buffer]
0x18003659e  mov     [rsp+278h+var_240], rcx
0x1800365a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800365a7  mov     [rsp+278h+nSize], eax
0x1800365ab  mov     eax, [rbx+44h]
0x1800365ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800365b2  mov     r9, rdi; unsigned __int16 *
0x1800365b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800365bc  mov     rdx, rsi; unsigned __int16 *
0x1800365bf  mov     rcx, r14; this
0x1800365c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800365c7  cmp     [rbx+18h], r15
0x1800365cb  jnz     short loc_1800365DD
0x1800365cd  cmp     [rbx+48h], r15
0x1800365d1  jnz     short loc_1800365DD
0x1800365d3  cmp     [rbx+30h], r15
0x1800365d7  jz      loc_18003666D
0x1800365dd  lea     r8, asc_180086EE8; "    "
0x1800365e4  mov     rdx, rsi; unsigned __int16 *
0x1800365e7  mov     rcx, rax; this
0x1800365ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800365ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800365f3  test    r9, r9
0x1800365f6  jz      short loc_18003660A
0x1800365f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800365ff  mov     rdx, rsi; unsigned __int16 *
0x180036602  mov     rcx, rax; this
0x180036605  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003660a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003660e  test    r9, r9
0x180036611  jz      short loc_180036625
0x180036613  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003661a  mov     rdx, rsi; unsigned __int16 *
0x18003661d  mov     rcx, rax; this
0x180036620  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036625  mov     rcx, [rbx+28h]
0x180036629  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003662d  mov     rdx, rsi; unsigned __int16 *
0x180036630  test    rcx, rcx
0x180036633  jz      short loc_18003664B
0x180036635  mov     [rsp+278h+lpBuffer], rcx
0x18003663a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180036641  mov     rcx, rax; this
0x180036644  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180036649  jmp     short loc_18003666D
0x18003664b  mov     rcx, rax; this
0x18003664e  test    r9, r9
0x180036651  jz      short loc_180036661
0x180036653  lea     r8, aHs; "[%hs]\n"
0x18003665a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003665f  jmp     short loc_18003666D
0x180036661  lea     r8, asc_180086F60; "\n"
0x180036668  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003666d  xor     eax, eax
0x18003666f  mov     rcx, [rsp+278h+var_38]
0x180036677  xor     rcx, rsp; StackCookie
0x18003667a  call    __security_check_cookie
0x18003667f  mov     rbx, [rsp+278h+arg_18]
0x180036687  add     rsp, 250h
0x18003668e  pop     r15
0x180036690  pop     r14
0x180036692  pop     rdi
0x180036693  pop     rsi
0x180036694  pop     rbp
0x180036695  retn
```
