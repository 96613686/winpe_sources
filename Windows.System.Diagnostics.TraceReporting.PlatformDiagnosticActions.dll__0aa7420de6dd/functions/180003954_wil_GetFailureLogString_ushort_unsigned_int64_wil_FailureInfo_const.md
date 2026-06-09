# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003954`
- end: `0x180003c0a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180002554`
- `0x1800027d4`
- `0x1800042b8`
- `0x180005ad0`
- `0x18000a171`
- `0x18000a2a5`

## callees

- `0x1800016a0`
- `0x180002058`
- `0x180003954`
- `0x1800045b8`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b07`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003a86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003a86`

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
          v7 = (const char *)&byte_18000F937;
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
0x180003954  mov     [rsp+arg_18], rbx
0x180003959  push    rbp
0x18000395a  push    rsi
0x18000395b  push    rdi
0x18000395c  push    r14
0x18000395e  push    r15
0x180003960  sub     rsp, 250h
0x180003967  mov     rax, cs:__security_cookie
0x18000396e  xor     rax, rsp
0x180003971  mov     [rsp+278h+var_38], rax
0x180003979  mov     rbx, r8
0x18000397c  mov     rsi, rdx
0x18000397f  mov     r14, rcx
0x180003982  xor     r15d, r15d
0x180003985  test    rdx, rdx
0x180003988  jz      loc_180003BE1
0x18000398e  test    rcx, rcx
0x180003991  jz      loc_180003BE1
0x180003997  mov     [rcx], r15w
0x18000399b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800039a2  test    rax, rax
0x1800039a5  jz      short loc_1800039C8
0x1800039a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800039ae  jz      short loc_1800039C8
0x1800039b0  mov     r8, rdx
0x1800039b3  mov     rdx, rcx
0x1800039b6  mov     rcx, rbx
0x1800039b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800039be  cmp     [r14], r15w
0x1800039c2  jnz     loc_180003BE1
0x1800039c8  mov     ecx, [rbx]
0x1800039ca  mov     bpl, 8
0x1800039cd  test    ecx, ecx
0x1800039cf  jz      short loc_180003A1A
0x1800039d1  sub     ecx, 1
0x1800039d4  jz      short loc_180003A02
0x1800039d6  sub     ecx, 1
0x1800039d9  jz      short loc_1800039F2
0x1800039db  cmp     ecx, 1
0x1800039de  jz      short loc_1800039E9
0x1800039e0  lea     rdi, byte_18000F937
0x1800039e7  jmp     short loc_180003A21
0x1800039e9  lea     rdi, aFailfast; "FailFast"
0x1800039f0  jmp     short loc_180003A21
0x1800039f2  lea     rax, aLoghr; "LogHr"
0x1800039f9  lea     rdi, aLognt; "LogNt"
0x180003a00  jmp     short loc_180003A10
0x180003a02  lea     rax, aReturnhr; "ReturnHr"
0x180003a09  lea     rdi, aReturnnt; "ReturnNt"
0x180003a10  test    [rbx+4], bpl
0x180003a14  cmovz   rdi, rax
0x180003a18  jmp     short loc_180003A21
0x180003a1a  lea     rdi, aException; "Exception"
0x180003a21  xor     edx, edx; Val
0x180003a23  mov     r8d, 200h; Size
0x180003a29  lea     rcx, [rsp+278h+Buffer]; void *
0x180003a2e  call    memset_0
0x180003a33  test    [rbx+4], bpl
0x180003a37  jz      short loc_180003A5C
0x180003a39  mov     ebp, [rbx+0Ch]
0x180003a3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003a43  test    rax, rax
0x180003a46  jz      short loc_180003A8C
0x180003a48  mov     r8d, 100h
0x180003a4e  lea     rdx, [rsp+278h+Buffer]
0x180003a53  mov     ecx, ebp
0x180003a55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a5a  jmp     short loc_180003A8C
0x180003a5c  mov     ebp, [rbx+8]
0x180003a5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003a64  mov     [rsp+278h+nSize], 100h; nSize
0x180003a6c  lea     rax, [rsp+278h+Buffer]
0x180003a71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003a76  mov     r9d, 400h; dwLanguageId
0x180003a7c  mov     r8d, ebp; dwMessageId
0x180003a7f  xor     edx, edx; lpSource
0x180003a81  mov     ecx, 1200h; dwFlags
0x180003a86  call    cs:__imp_FormatMessageW
0x180003a8c  lea     rsi, [r14+rsi*2]
0x180003a90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003a94  mov     rax, [rbx+88h]
0x180003a9b  mov     rcx, [rbx+80h]
0x180003aa2  mov     rdx, rsi; unsigned __int16 *
0x180003aa5  test    r9, r9
0x180003aa8  jz      short loc_180003ACC
0x180003aaa  mov     [rsp+278h+Arguments], rax
0x180003aaf  mov     qword ptr [rsp+278h+nSize], rcx
0x180003ab4  mov     eax, [rbx+40h]
0x180003ab7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003abb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003ac2  mov     rcx, r14; this
0x180003ac5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003aca  jmp     short loc_180003AE3
0x180003acc  mov     [rsp+278h+lpBuffer], rax
0x180003ad1  mov     r9, rcx; unsigned __int16 *
0x180003ad4  lea     r8, aHsP; "%hs!%p: "
0x180003adb  mov     rcx, r14; this
0x180003ade  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ae3  mov     r14, rax
0x180003ae6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003aed  test    r9, r9
0x180003af0  jz      short loc_180003B07
0x180003af2  lea     r8, aCallerP; "(caller: %p) "
0x180003af9  mov     rdx, rsi; unsigned __int16 *
0x180003afc  mov     rcx, rax; this
0x180003aff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b04  mov     r14, rax
0x180003b07  call    cs:__imp_GetCurrentThreadId
0x180003b0d  lea     rcx, [rsp+278h+Buffer]
0x180003b12  mov     [rsp+278h+var_240], rcx
0x180003b17  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003b1b  mov     [rsp+278h+nSize], eax
0x180003b1f  mov     eax, [rbx+44h]
0x180003b22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003b26  mov     r9, rdi; unsigned __int16 *
0x180003b29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003b30  mov     rdx, rsi; unsigned __int16 *
0x180003b33  mov     rcx, r14; this
0x180003b36  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b3b  cmp     [rbx+18h], r15
0x180003b3f  jnz     short loc_180003B51
0x180003b41  cmp     [rbx+48h], r15
0x180003b45  jnz     short loc_180003B51
0x180003b47  cmp     [rbx+30h], r15
0x180003b4b  jz      loc_180003BE1
0x180003b51  lea     r8, asc_18000FA38; "    "
0x180003b58  mov     rdx, rsi; unsigned __int16 *
0x180003b5b  mov     rcx, rax; this
0x180003b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b63  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003b67  test    r9, r9
0x180003b6a  jz      short loc_180003B7E
0x180003b6c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003b73  mov     rdx, rsi; unsigned __int16 *
0x180003b76  mov     rcx, rax; this
0x180003b79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b7e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003b82  test    r9, r9
0x180003b85  jz      short loc_180003B99
0x180003b87  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003b8e  mov     rdx, rsi; unsigned __int16 *
0x180003b91  mov     rcx, rax; this
0x180003b94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b99  mov     rcx, [rbx+28h]
0x180003b9d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003ba1  mov     rdx, rsi; unsigned __int16 *
0x180003ba4  test    rcx, rcx
0x180003ba7  jz      short loc_180003BBF
0x180003ba9  mov     [rsp+278h+lpBuffer], rcx
0x180003bae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003bb5  mov     rcx, rax; this
0x180003bb8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bbd  jmp     short loc_180003BE1
0x180003bbf  mov     rcx, rax; this
0x180003bc2  test    r9, r9
0x180003bc5  jz      short loc_180003BD5
0x180003bc7  lea     r8, aHs; "[%hs]\n"
0x180003bce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bd3  jmp     short loc_180003BE1
0x180003bd5  lea     r8, asc_18000FAB0; "\n"
0x180003bdc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003be1  xor     eax, eax
0x180003be3  mov     rcx, [rsp+278h+var_38]
0x180003beb  xor     rcx, rsp; StackCookie
0x180003bee  call    __security_check_cookie
0x180003bf3  mov     rbx, [rsp+278h+arg_18]
0x180003bfb  add     rsp, 250h
0x180003c02  pop     r15
0x180003c04  pop     r14
0x180003c06  pop     rdi
0x180003c07  pop     rsi
0x180003c08  pop     rbp
0x180003c09  retn
```
