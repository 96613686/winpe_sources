# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000d284`
- end: `0x18000d53a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180009fc0`
- `0x18000a240`
- `0x18000df90`
- `0x1800123b0`
- `0x18001d288`
- `0x18002844b`
- `0x18002857f`
- `0x180029428`
- `0x18002983b`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x18000d284`
- `0x18000e290`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d437`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d437`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d3b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000d3b6`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&byte_1800360F0;
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
0x18000d284  mov     [rsp+arg_18], rbx
0x18000d289  push    rbp
0x18000d28a  push    rsi
0x18000d28b  push    rdi
0x18000d28c  push    r14
0x18000d28e  push    r15
0x18000d290  sub     rsp, 250h
0x18000d297  mov     rax, cs:__security_cookie
0x18000d29e  xor     rax, rsp
0x18000d2a1  mov     [rsp+278h+var_38], rax
0x18000d2a9  mov     rbx, r8
0x18000d2ac  mov     rsi, rdx
0x18000d2af  mov     r14, rcx
0x18000d2b2  xor     r15d, r15d
0x18000d2b5  test    rdx, rdx
0x18000d2b8  jz      loc_18000D511
0x18000d2be  test    rcx, rcx
0x18000d2c1  jz      loc_18000D511
0x18000d2c7  mov     [rcx], r15w
0x18000d2cb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000d2d2  test    rax, rax
0x18000d2d5  jz      short loc_18000D2F8
0x18000d2d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000d2de  jz      short loc_18000D2F8
0x18000d2e0  mov     r8, rdx
0x18000d2e3  mov     rdx, rcx
0x18000d2e6  mov     rcx, rbx
0x18000d2e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d2ee  cmp     [r14], r15w
0x18000d2f2  jnz     loc_18000D511
0x18000d2f8  mov     ecx, [rbx]
0x18000d2fa  mov     bpl, 8
0x18000d2fd  test    ecx, ecx
0x18000d2ff  jz      short loc_18000D34A
0x18000d301  sub     ecx, 1
0x18000d304  jz      short loc_18000D332
0x18000d306  sub     ecx, 1
0x18000d309  jz      short loc_18000D322
0x18000d30b  cmp     ecx, 1
0x18000d30e  jz      short loc_18000D319
0x18000d310  lea     rdi, byte_1800360F0
0x18000d317  jmp     short loc_18000D351
0x18000d319  lea     rdi, aFailfast; "FailFast"
0x18000d320  jmp     short loc_18000D351
0x18000d322  lea     rax, aLoghr; "LogHr"
0x18000d329  lea     rdi, aLognt; "LogNt"
0x18000d330  jmp     short loc_18000D340
0x18000d332  lea     rax, aReturnhr; "ReturnHr"
0x18000d339  lea     rdi, aReturnnt; "ReturnNt"
0x18000d340  test    [rbx+4], bpl
0x18000d344  cmovz   rdi, rax
0x18000d348  jmp     short loc_18000D351
0x18000d34a  lea     rdi, aException; "Exception"
0x18000d351  xor     edx, edx; Val
0x18000d353  mov     r8d, 200h; Size
0x18000d359  lea     rcx, [rsp+278h+Buffer]; void *
0x18000d35e  call    memset_0
0x18000d363  test    [rbx+4], bpl
0x18000d367  jz      short loc_18000D38C
0x18000d369  mov     ebp, [rbx+0Ch]
0x18000d36c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000d373  test    rax, rax
0x18000d376  jz      short loc_18000D3BC
0x18000d378  mov     r8d, 100h
0x18000d37e  lea     rdx, [rsp+278h+Buffer]
0x18000d383  mov     ecx, ebp
0x18000d385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d38a  jmp     short loc_18000D3BC
0x18000d38c  mov     ebp, [rbx+8]
0x18000d38f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000d394  mov     [rsp+278h+nSize], 100h; nSize
0x18000d39c  lea     rax, [rsp+278h+Buffer]
0x18000d3a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000d3a6  mov     r9d, 400h; dwLanguageId
0x18000d3ac  mov     r8d, ebp; dwMessageId
0x18000d3af  xor     edx, edx; lpSource
0x18000d3b1  mov     ecx, 1200h; dwFlags
0x18000d3b6  call    cs:__imp_FormatMessageW
0x18000d3bc  lea     rsi, [r14+rsi*2]
0x18000d3c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000d3c4  mov     rax, [rbx+88h]
0x18000d3cb  mov     rcx, [rbx+80h]
0x18000d3d2  mov     rdx, rsi; unsigned __int16 *
0x18000d3d5  test    r9, r9
0x18000d3d8  jz      short loc_18000D3FC
0x18000d3da  mov     [rsp+278h+Arguments], rax
0x18000d3df  mov     qword ptr [rsp+278h+nSize], rcx
0x18000d3e4  mov     eax, [rbx+40h]
0x18000d3e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d3eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000d3f2  mov     rcx, r14; this
0x18000d3f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d3fa  jmp     short loc_18000D413
0x18000d3fc  mov     [rsp+278h+lpBuffer], rax
0x18000d401  mov     r9, rcx; unsigned __int16 *
0x18000d404  lea     r8, aHsP; "%hs!%p: "
0x18000d40b  mov     rcx, r14; this
0x18000d40e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d413  mov     r14, rax
0x18000d416  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000d41d  test    r9, r9
0x18000d420  jz      short loc_18000D437
0x18000d422  lea     r8, aCallerP; "(caller: %p) "
0x18000d429  mov     rdx, rsi; unsigned __int16 *
0x18000d42c  mov     rcx, rax; this
0x18000d42f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d434  mov     r14, rax
0x18000d437  call    cs:__imp_GetCurrentThreadId
0x18000d43d  lea     rcx, [rsp+278h+Buffer]
0x18000d442  mov     [rsp+278h+var_240], rcx
0x18000d447  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000d44b  mov     [rsp+278h+nSize], eax
0x18000d44f  mov     eax, [rbx+44h]
0x18000d452  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d456  mov     r9, rdi; unsigned __int16 *
0x18000d459  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000d460  mov     rdx, rsi; unsigned __int16 *
0x18000d463  mov     rcx, r14; this
0x18000d466  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d46b  cmp     [rbx+18h], r15
0x18000d46f  jnz     short loc_18000D481
0x18000d471  cmp     [rbx+48h], r15
0x18000d475  jnz     short loc_18000D481
0x18000d477  cmp     [rbx+30h], r15
0x18000d47b  jz      loc_18000D511
0x18000d481  lea     r8, asc_1800361F8; "    "
0x18000d488  mov     rdx, rsi; unsigned __int16 *
0x18000d48b  mov     rcx, rax; this
0x18000d48e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d493  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000d497  test    r9, r9
0x18000d49a  jz      short loc_18000D4AE
0x18000d49c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000d4a3  mov     rdx, rsi; unsigned __int16 *
0x18000d4a6  mov     rcx, rax; this
0x18000d4a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d4ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000d4b2  test    r9, r9
0x18000d4b5  jz      short loc_18000D4C9
0x18000d4b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000d4be  mov     rdx, rsi; unsigned __int16 *
0x18000d4c1  mov     rcx, rax; this
0x18000d4c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d4c9  mov     rcx, [rbx+28h]
0x18000d4cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000d4d1  mov     rdx, rsi; unsigned __int16 *
0x18000d4d4  test    rcx, rcx
0x18000d4d7  jz      short loc_18000D4EF
0x18000d4d9  mov     [rsp+278h+lpBuffer], rcx
0x18000d4de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000d4e5  mov     rcx, rax; this
0x18000d4e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d4ed  jmp     short loc_18000D511
0x18000d4ef  mov     rcx, rax; this
0x18000d4f2  test    r9, r9
0x18000d4f5  jz      short loc_18000D505
0x18000d4f7  lea     r8, aHs; "[%hs]\n"
0x18000d4fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d503  jmp     short loc_18000D511
0x18000d505  lea     r8, asc_180036270; "\n"
0x18000d50c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d511  xor     eax, eax
0x18000d513  mov     rcx, [rsp+278h+var_38]
0x18000d51b  xor     rcx, rsp; StackCookie
0x18000d51e  call    __security_check_cookie
0x18000d523  mov     rbx, [rsp+278h+arg_18]
0x18000d52b  add     rsp, 250h
0x18000d532  pop     r15
0x18000d534  pop     r14
0x18000d536  pop     rdi
0x18000d537  pop     rsi
0x18000d538  pop     rbp
0x18000d539  retn
```
