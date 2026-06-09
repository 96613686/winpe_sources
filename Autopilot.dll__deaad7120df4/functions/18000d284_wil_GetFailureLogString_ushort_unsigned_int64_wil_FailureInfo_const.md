# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000d284`
- end: `0x18000d547`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180009f8c`
- `0x18000a220`
- `0x18000e000`
- `0x180012640`
- `0x18001da0c`
- `0x18002971b`
- `0x18002984f`
- `0x18002a712`
- `0x18002a91f`

## callees

- `0x1800045d0`
- `0x1800053c4`
- `0x18000d284`
- `0x18000e314`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d43d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d43d`
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
          v7 = (const char *)&byte_180037110;
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
0x18000d2b8  jz      loc_18000D51D
0x18000d2be  test    rcx, rcx
0x18000d2c1  jz      loc_18000D51D
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
0x18000d2f2  jnz     loc_18000D51D
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
0x18000d310  lea     rdi, byte_180037110
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
0x18000d376  jz      short loc_18000D3C2
0x18000d378  mov     r8d, 100h
0x18000d37e  lea     rdx, [rsp+278h+Buffer]
0x18000d383  mov     ecx, ebp
0x18000d385  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d38a  jmp     short loc_18000D3C2
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
0x18000d3bd  nop     dword ptr [rax+rax+00h]
0x18000d3c2  lea     rsi, [r14+rsi*2]
0x18000d3c6  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000d3ca  mov     rax, [rbx+88h]
0x18000d3d1  mov     rcx, [rbx+80h]
0x18000d3d8  mov     rdx, rsi; unsigned __int16 *
0x18000d3db  test    r9, r9
0x18000d3de  jz      short loc_18000D402
0x18000d3e0  mov     [rsp+278h+Arguments], rax
0x18000d3e5  mov     qword ptr [rsp+278h+nSize], rcx
0x18000d3ea  mov     eax, [rbx+40h]
0x18000d3ed  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d3f1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000d3f8  mov     rcx, r14; this
0x18000d3fb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d400  jmp     short loc_18000D419
0x18000d402  mov     [rsp+278h+lpBuffer], rax
0x18000d407  mov     r9, rcx; unsigned __int16 *
0x18000d40a  lea     r8, aHsP; "%hs!%p: "
0x18000d411  mov     rcx, r14; this
0x18000d414  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d419  mov     r14, rax
0x18000d41c  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000d423  test    r9, r9
0x18000d426  jz      short loc_18000D43D
0x18000d428  lea     r8, aCallerP; "(caller: %p) "
0x18000d42f  mov     rdx, rsi; unsigned __int16 *
0x18000d432  mov     rcx, rax; this
0x18000d435  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d43a  mov     r14, rax
0x18000d43d  call    cs:__imp_GetCurrentThreadId
0x18000d444  nop     dword ptr [rax+rax+00h]
0x18000d449  lea     rcx, [rsp+278h+Buffer]
0x18000d44e  mov     [rsp+278h+var_240], rcx
0x18000d453  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000d457  mov     [rsp+278h+nSize], eax
0x18000d45b  mov     eax, [rbx+44h]
0x18000d45e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000d462  mov     r9, rdi; unsigned __int16 *
0x18000d465  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000d46c  mov     rdx, rsi; unsigned __int16 *
0x18000d46f  mov     rcx, r14; this
0x18000d472  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d477  cmp     [rbx+18h], r15
0x18000d47b  jnz     short loc_18000D48D
0x18000d47d  cmp     [rbx+48h], r15
0x18000d481  jnz     short loc_18000D48D
0x18000d483  cmp     [rbx+30h], r15
0x18000d487  jz      loc_18000D51D
0x18000d48d  lea     r8, asc_180037218; "    "
0x18000d494  mov     rdx, rsi; unsigned __int16 *
0x18000d497  mov     rcx, rax; this
0x18000d49a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d49f  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000d4a3  test    r9, r9
0x18000d4a6  jz      short loc_18000D4BA
0x18000d4a8  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000d4af  mov     rdx, rsi; unsigned __int16 *
0x18000d4b2  mov     rcx, rax; this
0x18000d4b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d4ba  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000d4be  test    r9, r9
0x18000d4c1  jz      short loc_18000D4D5
0x18000d4c3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000d4ca  mov     rdx, rsi; unsigned __int16 *
0x18000d4cd  mov     rcx, rax; this
0x18000d4d0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d4d5  mov     rcx, [rbx+28h]
0x18000d4d9  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000d4dd  mov     rdx, rsi; unsigned __int16 *
0x18000d4e0  test    rcx, rcx
0x18000d4e3  jz      short loc_18000D4FB
0x18000d4e5  mov     [rsp+278h+lpBuffer], rcx
0x18000d4ea  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000d4f1  mov     rcx, rax; this
0x18000d4f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d4f9  jmp     short loc_18000D51D
0x18000d4fb  mov     rcx, rax; this
0x18000d4fe  test    r9, r9
0x18000d501  jz      short loc_18000D511
0x18000d503  lea     r8, aHs; "[%hs]\n"
0x18000d50a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d50f  jmp     short loc_18000D51D
0x18000d511  lea     r8, asc_180037290; "\n"
0x18000d518  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000d51d  xor     eax, eax
0x18000d51f  mov     rcx, [rsp+278h+var_38]
0x18000d527  xor     rcx, rsp; StackCookie
0x18000d52a  call    __security_check_cookie
0x18000d52f  mov     rbx, [rsp+278h+arg_18]
0x18000d537  add     rsp, 250h
0x18000d53e  pop     r15
0x18000d540  pop     r14
0x18000d542  pop     rdi
0x18000d543  pop     rsi
0x18000d544  pop     rbp
0x18000d545  retn
```
