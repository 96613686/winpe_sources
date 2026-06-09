# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005374`
- end: `0x14000562a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140004254`
- `0x1400044c4`
- `0x140005cd4`

## callees

- `0x14000195f`
- `0x140005374`
- `0x140005fd4`
- `0x140006b90`
- `0x140007010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005527`
- `KERNEL32!GetCurrentThreadId` at `0x140005527`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400054a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400054a6`

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
          v8 = (const char *)&qword_140009AE8;
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
0x140005374  mov     [rsp+arg_18], rbx
0x140005379  push    rbp
0x14000537a  push    rsi
0x14000537b  push    rdi
0x14000537c  push    r14
0x14000537e  push    r15
0x140005380  sub     rsp, 250h
0x140005387  mov     rax, cs:__security_cookie
0x14000538e  xor     rax, rsp
0x140005391  mov     [rsp+278h+var_38], rax
0x140005399  xor     r15d, r15d
0x14000539c  mov     rbx, r8
0x14000539f  mov     rsi, rdx
0x1400053a2  mov     r14, rcx
0x1400053a5  test    rdx, rdx
0x1400053a8  jz      loc_140005601
0x1400053ae  test    rcx, rcx
0x1400053b1  jz      loc_140005601
0x1400053b7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400053be  mov     [rcx], r15w
0x1400053c2  test    rax, rax
0x1400053c5  jz      short loc_1400053E8
0x1400053c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400053ce  jz      short loc_1400053E8
0x1400053d0  mov     r8, rdx
0x1400053d3  mov     rdx, rcx
0x1400053d6  mov     rcx, rbx
0x1400053d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400053de  cmp     [r14], r15w
0x1400053e2  jnz     loc_140005601
0x1400053e8  mov     ecx, [rbx]
0x1400053ea  mov     bpl, 8
0x1400053ed  test    ecx, ecx
0x1400053ef  jz      short loc_14000543A
0x1400053f1  sub     ecx, 1
0x1400053f4  jz      short loc_140005422
0x1400053f6  sub     ecx, 1
0x1400053f9  jz      short loc_140005412
0x1400053fb  cmp     ecx, 1
0x1400053fe  jz      short loc_140005409
0x140005400  lea     rdi, qword_140009AE8
0x140005407  jmp     short loc_140005441
0x140005409  lea     rdi, aFailfast; "FailFast"
0x140005410  jmp     short loc_140005441
0x140005412  lea     rax, aLoghr; "LogHr"
0x140005419  lea     rdi, aLognt; "LogNt"
0x140005420  jmp     short loc_140005430
0x140005422  lea     rax, aReturnhr; "ReturnHr"
0x140005429  lea     rdi, aReturnnt; "ReturnNt"
0x140005430  test    [rbx+4], bpl
0x140005434  cmovz   rdi, rax
0x140005438  jmp     short loc_140005441
0x14000543a  lea     rdi, aException; "Exception"
0x140005441  xor     edx, edx; Val
0x140005443  lea     rcx, [rsp+278h+Buffer]; void *
0x140005448  mov     r8d, 200h; Size
0x14000544e  call    memset_0
0x140005453  test    [rbx+4], bpl
0x140005457  jz      short loc_14000547C
0x140005459  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005460  mov     ebp, [rbx+0Ch]
0x140005463  test    rax, rax
0x140005466  jz      short loc_1400054AC
0x140005468  mov     r8d, 100h
0x14000546e  lea     rdx, [rsp+278h+Buffer]
0x140005473  mov     ecx, ebp
0x140005475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000547a  jmp     short loc_1400054AC
0x14000547c  mov     ebp, [rbx+8]
0x14000547f  lea     rax, [rsp+278h+Buffer]
0x140005484  mov     [rsp+278h+Arguments], r15; Arguments
0x140005489  mov     r8d, ebp; dwMessageId
0x14000548c  mov     [rsp+278h+nSize], 100h; nSize
0x140005494  mov     r9d, 400h; dwLanguageId
0x14000549a  xor     edx, edx; lpSource
0x14000549c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400054a1  mov     ecx, 1200h; dwFlags
0x1400054a6  call    cs:__imp_FormatMessageW
0x1400054ac  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400054b0  lea     rsi, [r14+rsi*2]
0x1400054b4  mov     rax, [rbx+88h]
0x1400054bb  mov     rdx, rsi; unsigned __int16 *
0x1400054be  mov     rcx, [rbx+80h]
0x1400054c5  test    r9, r9
0x1400054c8  jz      short loc_1400054EC
0x1400054ca  mov     [rsp+278h+Arguments], rax
0x1400054cf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400054d6  mov     eax, [rbx+40h]
0x1400054d9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400054de  mov     rcx, r14; this
0x1400054e1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400054e5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400054ea  jmp     short loc_140005503
0x1400054ec  mov     r9, rcx; unsigned __int16 *
0x1400054ef  mov     [rsp+278h+lpBuffer], rax
0x1400054f4  mov     rcx, r14; this
0x1400054f7  lea     r8, aHsP; "%hs!%p: "
0x1400054fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005503  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000550a  mov     r14, rax
0x14000550d  test    r9, r9
0x140005510  jz      short loc_140005527
0x140005512  lea     r8, aCallerP; "(caller: %p) "
0x140005519  mov     rdx, rsi; unsigned __int16 *
0x14000551c  mov     rcx, rax; this
0x14000551f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005524  mov     r14, rax
0x140005527  call    cs:__imp_GetCurrentThreadId
0x14000552d  lea     rcx, [rsp+278h+Buffer]
0x140005532  mov     r9, rdi; unsigned __int16 *
0x140005535  mov     [rsp+278h+var_240], rcx
0x14000553a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005541  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005545  mov     rdx, rsi; unsigned __int16 *
0x140005548  mov     [rsp+278h+nSize], eax
0x14000554c  mov     rcx, r14; this
0x14000554f  mov     eax, [rbx+44h]
0x140005552  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005556  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000555b  cmp     [rbx+18h], r15
0x14000555f  jnz     short loc_140005571
0x140005561  cmp     [rbx+48h], r15
0x140005565  jnz     short loc_140005571
0x140005567  cmp     [rbx+30h], r15
0x14000556b  jz      loc_140005601
0x140005571  lea     r8, asc_140009BD8; "    "
0x140005578  mov     rdx, rsi; unsigned __int16 *
0x14000557b  mov     rcx, rax; this
0x14000557e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005583  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005587  test    r9, r9
0x14000558a  jz      short loc_14000559E
0x14000558c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005593  mov     rdx, rsi; unsigned __int16 *
0x140005596  mov     rcx, rax; this
0x140005599  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000559e  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400055a2  test    r9, r9
0x1400055a5  jz      short loc_1400055B9
0x1400055a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400055ae  mov     rdx, rsi; unsigned __int16 *
0x1400055b1  mov     rcx, rax; this
0x1400055b4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055b9  mov     rcx, [rbx+28h]
0x1400055bd  mov     rdx, rsi; unsigned __int16 *
0x1400055c0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400055c4  test    rcx, rcx
0x1400055c7  jz      short loc_1400055DF
0x1400055c9  mov     [rsp+278h+lpBuffer], rcx
0x1400055ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400055d5  mov     rcx, rax; this
0x1400055d8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055dd  jmp     short loc_140005601
0x1400055df  mov     rcx, rax; this
0x1400055e2  test    r9, r9
0x1400055e5  jz      short loc_1400055F5
0x1400055e7  lea     r8, aHs; "[%hs]\n"
0x1400055ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055f3  jmp     short loc_140005601
0x1400055f5  lea     r8, asc_140009C50; "\n"
0x1400055fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005601  xor     eax, eax
0x140005603  mov     rcx, [rsp+278h+var_38]
0x14000560b  xor     rcx, rsp; StackCookie
0x14000560e  call    __security_check_cookie
0x140005613  mov     rbx, [rsp+278h+arg_18]
0x14000561b  add     rsp, 250h
0x140005622  pop     r15
0x140005624  pop     r14
0x140005626  pop     rdi
0x140005627  pop     rsi
0x140005628  pop     rbp
0x140005629  retn
```
