# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005954`
- end: `0x180005c0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180003344`
- `0x1800035b4`
- `0x180006430`
- `0x180009100`
- `0x18000cdac`

## callees

- `0x180002470`
- `0x180002ff8`
- `0x180005954`
- `0x180006730`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005b07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005a86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005a86`

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
          v7 = (const char *)&word_18001783A;
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
0x180005954  mov     [rsp+arg_18], rbx
0x180005959  push    rbp
0x18000595a  push    rsi
0x18000595b  push    rdi
0x18000595c  push    r14
0x18000595e  push    r15
0x180005960  sub     rsp, 250h
0x180005967  mov     rax, cs:__security_cookie
0x18000596e  xor     rax, rsp
0x180005971  mov     [rsp+278h+var_38], rax
0x180005979  mov     rbx, r8
0x18000597c  mov     rsi, rdx
0x18000597f  mov     r14, rcx
0x180005982  xor     r15d, r15d
0x180005985  test    rdx, rdx
0x180005988  jz      loc_180005BE1
0x18000598e  test    rcx, rcx
0x180005991  jz      loc_180005BE1
0x180005997  mov     [rcx], r15w
0x18000599b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059a2  test    rax, rax
0x1800059a5  jz      short loc_1800059C8
0x1800059a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800059ae  jz      short loc_1800059C8
0x1800059b0  mov     r8, rdx
0x1800059b3  mov     rdx, rcx
0x1800059b6  mov     rcx, rbx
0x1800059b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059be  cmp     [r14], r15w
0x1800059c2  jnz     loc_180005BE1
0x1800059c8  mov     ecx, [rbx]
0x1800059ca  mov     bpl, 8
0x1800059cd  test    ecx, ecx
0x1800059cf  jz      short loc_180005A1A
0x1800059d1  sub     ecx, 1
0x1800059d4  jz      short loc_180005A02
0x1800059d6  sub     ecx, 1
0x1800059d9  jz      short loc_1800059F2
0x1800059db  cmp     ecx, 1
0x1800059de  jz      short loc_1800059E9
0x1800059e0  lea     rdi, word_18001783A
0x1800059e7  jmp     short loc_180005A21
0x1800059e9  lea     rdi, aFailfast; "FailFast"
0x1800059f0  jmp     short loc_180005A21
0x1800059f2  lea     rax, aLoghr; "LogHr"
0x1800059f9  lea     rdi, aLognt; "LogNt"
0x180005a00  jmp     short loc_180005A10
0x180005a02  lea     rax, aReturnhr; "ReturnHr"
0x180005a09  lea     rdi, aReturnnt; "ReturnNt"
0x180005a10  test    [rbx+4], bpl
0x180005a14  cmovz   rdi, rax
0x180005a18  jmp     short loc_180005A21
0x180005a1a  lea     rdi, aException; "Exception"
0x180005a21  xor     edx, edx; Val
0x180005a23  mov     r8d, 200h; Size
0x180005a29  lea     rcx, [rsp+278h+Buffer]; void *
0x180005a2e  call    memset_0
0x180005a33  test    [rbx+4], bpl
0x180005a37  jz      short loc_180005A5C
0x180005a39  mov     ebp, [rbx+0Ch]
0x180005a3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005a43  test    rax, rax
0x180005a46  jz      short loc_180005A8C
0x180005a48  mov     r8d, 100h
0x180005a4e  lea     rdx, [rsp+278h+Buffer]
0x180005a53  mov     ecx, ebp
0x180005a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a5a  jmp     short loc_180005A8C
0x180005a5c  mov     ebp, [rbx+8]
0x180005a5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005a64  mov     [rsp+278h+nSize], 100h; nSize
0x180005a6c  lea     rax, [rsp+278h+Buffer]
0x180005a71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005a76  mov     r9d, 400h; dwLanguageId
0x180005a7c  mov     r8d, ebp; dwMessageId
0x180005a7f  xor     edx, edx; lpSource
0x180005a81  mov     ecx, 1200h; dwFlags
0x180005a86  call    cs:__imp_FormatMessageW
0x180005a8c  lea     rsi, [r14+rsi*2]
0x180005a90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005a94  mov     rax, [rbx+88h]
0x180005a9b  mov     rcx, [rbx+80h]
0x180005aa2  mov     rdx, rsi; unsigned __int16 *
0x180005aa5  test    r9, r9
0x180005aa8  jz      short loc_180005ACC
0x180005aaa  mov     [rsp+278h+Arguments], rax
0x180005aaf  mov     qword ptr [rsp+278h+nSize], rcx
0x180005ab4  mov     eax, [rbx+40h]
0x180005ab7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005abb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005ac2  mov     rcx, r14; this
0x180005ac5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005aca  jmp     short loc_180005AE3
0x180005acc  mov     [rsp+278h+lpBuffer], rax
0x180005ad1  mov     r9, rcx; unsigned __int16 *
0x180005ad4  lea     r8, aHsP; "%hs!%p: "
0x180005adb  mov     rcx, r14; this
0x180005ade  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ae3  mov     r14, rax
0x180005ae6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005aed  test    r9, r9
0x180005af0  jz      short loc_180005B07
0x180005af2  lea     r8, aCallerP; "(caller: %p) "
0x180005af9  mov     rdx, rsi; unsigned __int16 *
0x180005afc  mov     rcx, rax; this
0x180005aff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b04  mov     r14, rax
0x180005b07  call    cs:__imp_GetCurrentThreadId
0x180005b0d  lea     rcx, [rsp+278h+Buffer]
0x180005b12  mov     [rsp+278h+var_240], rcx
0x180005b17  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005b1b  mov     [rsp+278h+nSize], eax
0x180005b1f  mov     eax, [rbx+44h]
0x180005b22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005b26  mov     r9, rdi; unsigned __int16 *
0x180005b29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005b30  mov     rdx, rsi; unsigned __int16 *
0x180005b33  mov     rcx, r14; this
0x180005b36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b3b  cmp     [rbx+18h], r15
0x180005b3f  jnz     short loc_180005B51
0x180005b41  cmp     [rbx+48h], r15
0x180005b45  jnz     short loc_180005B51
0x180005b47  cmp     [rbx+30h], r15
0x180005b4b  jz      loc_180005BE1
0x180005b51  lea     r8, asc_180017948; "    "
0x180005b58  mov     rdx, rsi; unsigned __int16 *
0x180005b5b  mov     rcx, rax; this
0x180005b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b63  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005b67  test    r9, r9
0x180005b6a  jz      short loc_180005B7E
0x180005b6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005b73  mov     rdx, rsi; unsigned __int16 *
0x180005b76  mov     rcx, rax; this
0x180005b79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005b82  test    r9, r9
0x180005b85  jz      short loc_180005B99
0x180005b87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005b8e  mov     rdx, rsi; unsigned __int16 *
0x180005b91  mov     rcx, rax; this
0x180005b94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b99  mov     rcx, [rbx+28h]
0x180005b9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005ba1  mov     rdx, rsi; unsigned __int16 *
0x180005ba4  test    rcx, rcx
0x180005ba7  jz      short loc_180005BBF
0x180005ba9  mov     [rsp+278h+lpBuffer], rcx
0x180005bae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005bb5  mov     rcx, rax; this
0x180005bb8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005bbd  jmp     short loc_180005BE1
0x180005bbf  mov     rcx, rax; this
0x180005bc2  test    r9, r9
0x180005bc5  jz      short loc_180005BD5
0x180005bc7  lea     r8, aHs; "[%hs]\n"
0x180005bce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005bd3  jmp     short loc_180005BE1
0x180005bd5  lea     r8, asc_1800179C0; "\n"
0x180005bdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005be1  xor     eax, eax
0x180005be3  mov     rcx, [rsp+278h+var_38]
0x180005beb  xor     rcx, rsp; StackCookie
0x180005bee  call    __security_check_cookie
0x180005bf3  mov     rbx, [rsp+278h+arg_18]
0x180005bfb  add     rsp, 250h
0x180005c02  pop     r15
0x180005c04  pop     r14
0x180005c06  pop     rdi
0x180005c07  pop     rsi
0x180005c08  pop     rbp
0x180005c09  retn
```
