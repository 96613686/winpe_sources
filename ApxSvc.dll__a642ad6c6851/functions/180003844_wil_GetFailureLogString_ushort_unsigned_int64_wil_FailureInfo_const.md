# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003844`
- end: `0x180003afa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002464`
- `0x1800026d4`
- `0x1800041a8`
- `0x180005830`

## callees

- `0x180001560`
- `0x180001ef2`
- `0x180003844`
- `0x1800044a8`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003976`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003976`

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
          v7 = (const char *)&byte_18000AC95;
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
0x180003844  mov     [rsp+arg_18], rbx
0x180003849  push    rbp
0x18000384a  push    rsi
0x18000384b  push    rdi
0x18000384c  push    r14
0x18000384e  push    r15
0x180003850  sub     rsp, 250h
0x180003857  mov     rax, cs:__security_cookie
0x18000385e  xor     rax, rsp
0x180003861  mov     [rsp+278h+var_38], rax
0x180003869  mov     rbx, r8
0x18000386c  mov     rsi, rdx
0x18000386f  mov     r14, rcx
0x180003872  xor     r15d, r15d
0x180003875  test    rdx, rdx
0x180003878  jz      loc_180003AD1
0x18000387e  test    rcx, rcx
0x180003881  jz      loc_180003AD1
0x180003887  mov     [rcx], r15w
0x18000388b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003892  test    rax, rax
0x180003895  jz      short loc_1800038B8
0x180003897  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000389e  jz      short loc_1800038B8
0x1800038a0  mov     r8, rdx
0x1800038a3  mov     rdx, rcx
0x1800038a6  mov     rcx, rbx
0x1800038a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800038ae  cmp     [r14], r15w
0x1800038b2  jnz     loc_180003AD1
0x1800038b8  mov     ecx, [rbx]
0x1800038ba  mov     bpl, 8
0x1800038bd  test    ecx, ecx
0x1800038bf  jz      short loc_18000390A
0x1800038c1  sub     ecx, 1
0x1800038c4  jz      short loc_1800038F2
0x1800038c6  sub     ecx, 1
0x1800038c9  jz      short loc_1800038E2
0x1800038cb  cmp     ecx, 1
0x1800038ce  jz      short loc_1800038D9
0x1800038d0  lea     rdi, byte_18000AC95
0x1800038d7  jmp     short loc_180003911
0x1800038d9  lea     rdi, aFailfast; "FailFast"
0x1800038e0  jmp     short loc_180003911
0x1800038e2  lea     rax, aLoghr; "LogHr"
0x1800038e9  lea     rdi, aLognt; "LogNt"
0x1800038f0  jmp     short loc_180003900
0x1800038f2  lea     rax, aReturnhr; "ReturnHr"
0x1800038f9  lea     rdi, aReturnnt; "ReturnNt"
0x180003900  test    [rbx+4], bpl
0x180003904  cmovz   rdi, rax
0x180003908  jmp     short loc_180003911
0x18000390a  lea     rdi, aException; "Exception"
0x180003911  xor     edx, edx; Val
0x180003913  mov     r8d, 200h; Size
0x180003919  lea     rcx, [rsp+278h+Buffer]; void *
0x18000391e  call    memset_0
0x180003923  test    [rbx+4], bpl
0x180003927  jz      short loc_18000394C
0x180003929  mov     ebp, [rbx+0Ch]
0x18000392c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003933  test    rax, rax
0x180003936  jz      short loc_18000397C
0x180003938  mov     r8d, 100h
0x18000393e  lea     rdx, [rsp+278h+Buffer]
0x180003943  mov     ecx, ebp
0x180003945  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000394a  jmp     short loc_18000397C
0x18000394c  mov     ebp, [rbx+8]
0x18000394f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003954  mov     [rsp+278h+nSize], 100h; nSize
0x18000395c  lea     rax, [rsp+278h+Buffer]
0x180003961  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003966  mov     r9d, 400h; dwLanguageId
0x18000396c  mov     r8d, ebp; dwMessageId
0x18000396f  xor     edx, edx; lpSource
0x180003971  mov     ecx, 1200h; dwFlags
0x180003976  call    cs:__imp_FormatMessageW
0x18000397c  lea     rsi, [r14+rsi*2]
0x180003980  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003984  mov     rax, [rbx+88h]
0x18000398b  mov     rcx, [rbx+80h]
0x180003992  mov     rdx, rsi; unsigned __int16 *
0x180003995  test    r9, r9
0x180003998  jz      short loc_1800039BC
0x18000399a  mov     [rsp+278h+Arguments], rax
0x18000399f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800039a4  mov     eax, [rbx+40h]
0x1800039a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800039ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800039b2  mov     rcx, r14; this
0x1800039b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039ba  jmp     short loc_1800039D3
0x1800039bc  mov     [rsp+278h+lpBuffer], rax
0x1800039c1  mov     r9, rcx; unsigned __int16 *
0x1800039c4  lea     r8, aHsP; "%hs!%p: "
0x1800039cb  mov     rcx, r14; this
0x1800039ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039d3  mov     r14, rax
0x1800039d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800039dd  test    r9, r9
0x1800039e0  jz      short loc_1800039F7
0x1800039e2  lea     r8, aCallerP; "(caller: %p) "
0x1800039e9  mov     rdx, rsi; unsigned __int16 *
0x1800039ec  mov     rcx, rax; this
0x1800039ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039f4  mov     r14, rax
0x1800039f7  call    cs:__imp_GetCurrentThreadId
0x1800039fd  lea     rcx, [rsp+278h+Buffer]
0x180003a02  mov     [rsp+278h+var_240], rcx
0x180003a07  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003a0b  mov     [rsp+278h+nSize], eax
0x180003a0f  mov     eax, [rbx+44h]
0x180003a12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003a16  mov     r9, rdi; unsigned __int16 *
0x180003a19  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003a20  mov     rdx, rsi; unsigned __int16 *
0x180003a23  mov     rcx, r14; this
0x180003a26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a2b  cmp     [rbx+18h], r15
0x180003a2f  jnz     short loc_180003A41
0x180003a31  cmp     [rbx+48h], r15
0x180003a35  jnz     short loc_180003A41
0x180003a37  cmp     [rbx+30h], r15
0x180003a3b  jz      loc_180003AD1
0x180003a41  lea     r8, asc_18000AD98; "    "
0x180003a48  mov     rdx, rsi; unsigned __int16 *
0x180003a4b  mov     rcx, rax; this
0x180003a4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a53  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003a57  test    r9, r9
0x180003a5a  jz      short loc_180003A6E
0x180003a5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003a63  mov     rdx, rsi; unsigned __int16 *
0x180003a66  mov     rcx, rax; this
0x180003a69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003a72  test    r9, r9
0x180003a75  jz      short loc_180003A89
0x180003a77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003a7e  mov     rdx, rsi; unsigned __int16 *
0x180003a81  mov     rcx, rax; this
0x180003a84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a89  mov     rcx, [rbx+28h]
0x180003a8d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003a91  mov     rdx, rsi; unsigned __int16 *
0x180003a94  test    rcx, rcx
0x180003a97  jz      short loc_180003AAF
0x180003a99  mov     [rsp+278h+lpBuffer], rcx
0x180003a9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003aa5  mov     rcx, rax; this
0x180003aa8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aad  jmp     short loc_180003AD1
0x180003aaf  mov     rcx, rax; this
0x180003ab2  test    r9, r9
0x180003ab5  jz      short loc_180003AC5
0x180003ab7  lea     r8, aHs; "[%hs]\n"
0x180003abe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ac3  jmp     short loc_180003AD1
0x180003ac5  lea     r8, asc_18000AE10; "\n"
0x180003acc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ad1  xor     eax, eax
0x180003ad3  mov     rcx, [rsp+278h+var_38]
0x180003adb  xor     rcx, rsp; StackCookie
0x180003ade  call    __security_check_cookie
0x180003ae3  mov     rbx, [rsp+278h+arg_18]
0x180003aeb  add     rsp, 250h
0x180003af2  pop     r15
0x180003af4  pop     r14
0x180003af6  pop     rdi
0x180003af7  pop     rsi
0x180003af8  pop     rbp
0x180003af9  retn
```
