# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400053b4`
- end: `0x14000566a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140003628`
- `0x140005f48`
- `0x14000642c`
- `0x140007f10`

## callees

- `0x140002210`
- `0x140002d50`
- `0x1400053b4`
- `0x140006248`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005567`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400054e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400054e6`

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
          v7 = (const char *)&byte_1400140E0;
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
0x1400053b4  mov     [rsp+arg_18], rbx
0x1400053b9  push    rbp
0x1400053ba  push    rsi
0x1400053bb  push    rdi
0x1400053bc  push    r14
0x1400053be  push    r15
0x1400053c0  sub     rsp, 250h
0x1400053c7  mov     rax, cs:__security_cookie
0x1400053ce  xor     rax, rsp
0x1400053d1  mov     [rsp+278h+var_38], rax
0x1400053d9  mov     rbx, r8
0x1400053dc  mov     rsi, rdx
0x1400053df  mov     r14, rcx
0x1400053e2  xor     r15d, r15d
0x1400053e5  test    rdx, rdx
0x1400053e8  jz      loc_140005641
0x1400053ee  test    rcx, rcx
0x1400053f1  jz      loc_140005641
0x1400053f7  mov     [rcx], r15w
0x1400053fb  mov     rax, cs:g_pfnResultLoggingCallback
0x140005402  test    rax, rax
0x140005405  jz      short loc_140005428
0x140005407  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000540e  jz      short loc_140005428
0x140005410  mov     r8, rdx
0x140005413  mov     rdx, rcx
0x140005416  mov     rcx, rbx
0x140005419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000541e  cmp     [r14], r15w
0x140005422  jnz     loc_140005641
0x140005428  mov     ecx, [rbx]
0x14000542a  mov     bpl, 8
0x14000542d  test    ecx, ecx
0x14000542f  jz      short loc_14000547A
0x140005431  sub     ecx, 1
0x140005434  jz      short loc_140005462
0x140005436  sub     ecx, 1
0x140005439  jz      short loc_140005452
0x14000543b  cmp     ecx, 1
0x14000543e  jz      short loc_140005449
0x140005440  lea     rdi, byte_1400140E0
0x140005447  jmp     short loc_140005481
0x140005449  lea     rdi, aFailfast; "FailFast"
0x140005450  jmp     short loc_140005481
0x140005452  lea     rax, aLoghr; "LogHr"
0x140005459  lea     rdi, aLognt; "LogNt"
0x140005460  jmp     short loc_140005470
0x140005462  lea     rax, aReturnhr; "ReturnHr"
0x140005469  lea     rdi, aReturnnt; "ReturnNt"
0x140005470  test    [rbx+4], bpl
0x140005474  cmovz   rdi, rax
0x140005478  jmp     short loc_140005481
0x14000547a  lea     rdi, aException; "Exception"
0x140005481  xor     edx, edx; Val
0x140005483  mov     r8d, 200h; Size
0x140005489  lea     rcx, [rsp+278h+Buffer]; void *
0x14000548e  call    memset_0
0x140005493  test    [rbx+4], bpl
0x140005497  jz      short loc_1400054BC
0x140005499  mov     ebp, [rbx+0Ch]
0x14000549c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400054a3  test    rax, rax
0x1400054a6  jz      short loc_1400054EC
0x1400054a8  mov     r8d, 100h
0x1400054ae  lea     rdx, [rsp+278h+Buffer]
0x1400054b3  mov     ecx, ebp
0x1400054b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054ba  jmp     short loc_1400054EC
0x1400054bc  mov     ebp, [rbx+8]
0x1400054bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1400054c4  mov     [rsp+278h+nSize], 100h; nSize
0x1400054cc  lea     rax, [rsp+278h+Buffer]
0x1400054d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400054d6  mov     r9d, 400h; dwLanguageId
0x1400054dc  mov     r8d, ebp; dwMessageId
0x1400054df  xor     edx, edx; lpSource
0x1400054e1  mov     ecx, 1200h; dwFlags
0x1400054e6  call    cs:__imp_FormatMessageW
0x1400054ec  lea     rsi, [r14+rsi*2]
0x1400054f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400054f4  mov     rax, [rbx+88h]
0x1400054fb  mov     rcx, [rbx+80h]
0x140005502  mov     rdx, rsi; unsigned __int16 *
0x140005505  test    r9, r9
0x140005508  jz      short loc_14000552C
0x14000550a  mov     [rsp+278h+Arguments], rax
0x14000550f  mov     qword ptr [rsp+278h+nSize], rcx
0x140005514  mov     eax, [rbx+40h]
0x140005517  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000551b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005522  mov     rcx, r14; this
0x140005525  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000552a  jmp     short loc_140005543
0x14000552c  mov     [rsp+278h+lpBuffer], rax
0x140005531  mov     r9, rcx; unsigned __int16 *
0x140005534  lea     r8, aHsP; "%hs!%p: "
0x14000553b  mov     rcx, r14; this
0x14000553e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005543  mov     r14, rax
0x140005546  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000554d  test    r9, r9
0x140005550  jz      short loc_140005567
0x140005552  lea     r8, aCallerP; "(caller: %p) "
0x140005559  mov     rdx, rsi; unsigned __int16 *
0x14000555c  mov     rcx, rax; this
0x14000555f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005564  mov     r14, rax
0x140005567  call    cs:__imp_GetCurrentThreadId
0x14000556d  lea     rcx, [rsp+278h+Buffer]
0x140005572  mov     [rsp+278h+var_240], rcx
0x140005577  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000557b  mov     [rsp+278h+nSize], eax
0x14000557f  mov     eax, [rbx+44h]
0x140005582  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005586  mov     r9, rdi; unsigned __int16 *
0x140005589  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005590  mov     rdx, rsi; unsigned __int16 *
0x140005593  mov     rcx, r14; this
0x140005596  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000559b  cmp     [rbx+18h], r15
0x14000559f  jnz     short loc_1400055B1
0x1400055a1  cmp     [rbx+48h], r15
0x1400055a5  jnz     short loc_1400055B1
0x1400055a7  cmp     [rbx+30h], r15
0x1400055ab  jz      loc_140005641
0x1400055b1  lea     r8, asc_140014210; "    "
0x1400055b8  mov     rdx, rsi; unsigned __int16 *
0x1400055bb  mov     rcx, rax; this
0x1400055be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400055c7  test    r9, r9
0x1400055ca  jz      short loc_1400055DE
0x1400055cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400055d3  mov     rdx, rsi; unsigned __int16 *
0x1400055d6  mov     rcx, rax; this
0x1400055d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400055e2  test    r9, r9
0x1400055e5  jz      short loc_1400055F9
0x1400055e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400055ee  mov     rdx, rsi; unsigned __int16 *
0x1400055f1  mov     rcx, rax; this
0x1400055f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055f9  mov     rcx, [rbx+28h]
0x1400055fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005601  mov     rdx, rsi; unsigned __int16 *
0x140005604  test    rcx, rcx
0x140005607  jz      short loc_14000561F
0x140005609  mov     [rsp+278h+lpBuffer], rcx
0x14000560e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005615  mov     rcx, rax; this
0x140005618  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000561d  jmp     short loc_140005641
0x14000561f  mov     rcx, rax; this
0x140005622  test    r9, r9
0x140005625  jz      short loc_140005635
0x140005627  lea     r8, aHs; "[%hs]\n"
0x14000562e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005633  jmp     short loc_140005641
0x140005635  lea     r8, asc_140014288; "\n"
0x14000563c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005641  xor     eax, eax
0x140005643  mov     rcx, [rsp+278h+var_38]
0x14000564b  xor     rcx, rsp; StackCookie
0x14000564e  call    __security_check_cookie
0x140005653  mov     rbx, [rsp+278h+arg_18]
0x14000565b  add     rsp, 250h
0x140005662  pop     r15
0x140005664  pop     r14
0x140005666  pop     rdi
0x140005667  pop     rsi
0x140005668  pop     rbp
0x140005669  retn
```
