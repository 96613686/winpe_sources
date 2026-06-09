# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009a74`
- end: `0x180009d37`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000822c`
- `0x18000a49c`
- `0x18000a9f8`
- `0x18000c560`

## callees

- `0x180006f60`
- `0x180007b38`
- `0x180009a74`
- `0x18000a7bc`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c2d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009ba6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009ba6`

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
          v7 = (const char *)&dword_180042334;
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
0x180009a74  mov     [rsp+arg_18], rbx
0x180009a79  push    rbp
0x180009a7a  push    rsi
0x180009a7b  push    rdi
0x180009a7c  push    r14
0x180009a7e  push    r15
0x180009a80  sub     rsp, 250h
0x180009a87  mov     rax, cs:__security_cookie
0x180009a8e  xor     rax, rsp
0x180009a91  mov     [rsp+278h+var_38], rax
0x180009a99  mov     rbx, r8
0x180009a9c  mov     rsi, rdx
0x180009a9f  mov     r14, rcx
0x180009aa2  xor     r15d, r15d
0x180009aa5  test    rdx, rdx
0x180009aa8  jz      loc_180009D0D
0x180009aae  test    rcx, rcx
0x180009ab1  jz      loc_180009D0D
0x180009ab7  mov     [rcx], r15w
0x180009abb  mov     rax, cs:g_pfnResultLoggingCallback
0x180009ac2  test    rax, rax
0x180009ac5  jz      short loc_180009AE8
0x180009ac7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009ace  jz      short loc_180009AE8
0x180009ad0  mov     r8, rdx
0x180009ad3  mov     rdx, rcx
0x180009ad6  mov     rcx, rbx
0x180009ad9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ade  cmp     [r14], r15w
0x180009ae2  jnz     loc_180009D0D
0x180009ae8  mov     ecx, [rbx]
0x180009aea  mov     bpl, 8
0x180009aed  test    ecx, ecx
0x180009aef  jz      short loc_180009B3A
0x180009af1  sub     ecx, 1
0x180009af4  jz      short loc_180009B22
0x180009af6  sub     ecx, 1
0x180009af9  jz      short loc_180009B12
0x180009afb  cmp     ecx, 1
0x180009afe  jz      short loc_180009B09
0x180009b00  lea     rdi, dword_180042334
0x180009b07  jmp     short loc_180009B41
0x180009b09  lea     rdi, aFailfast; "FailFast"
0x180009b10  jmp     short loc_180009B41
0x180009b12  lea     rax, aLoghr; "LogHr"
0x180009b19  lea     rdi, aLognt; "LogNt"
0x180009b20  jmp     short loc_180009B30
0x180009b22  lea     rax, aReturnhr; "ReturnHr"
0x180009b29  lea     rdi, aReturnnt; "ReturnNt"
0x180009b30  test    [rbx+4], bpl
0x180009b34  cmovz   rdi, rax
0x180009b38  jmp     short loc_180009B41
0x180009b3a  lea     rdi, aException; "Exception"
0x180009b41  xor     edx, edx; Val
0x180009b43  mov     r8d, 200h; Size
0x180009b49  lea     rcx, [rsp+278h+Buffer]; void *
0x180009b4e  call    memset_0
0x180009b53  test    [rbx+4], bpl
0x180009b57  jz      short loc_180009B7C
0x180009b59  mov     ebp, [rbx+0Ch]
0x180009b5c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009b63  test    rax, rax
0x180009b66  jz      short loc_180009BB2
0x180009b68  mov     r8d, 100h
0x180009b6e  lea     rdx, [rsp+278h+Buffer]
0x180009b73  mov     ecx, ebp
0x180009b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b7a  jmp     short loc_180009BB2
0x180009b7c  mov     ebp, [rbx+8]
0x180009b7f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009b84  mov     [rsp+278h+nSize], 100h; nSize
0x180009b8c  lea     rax, [rsp+278h+Buffer]
0x180009b91  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009b96  mov     r9d, 400h; dwLanguageId
0x180009b9c  mov     r8d, ebp; dwMessageId
0x180009b9f  xor     edx, edx; lpSource
0x180009ba1  mov     ecx, 1200h; dwFlags
0x180009ba6  call    cs:__imp_FormatMessageW
0x180009bad  nop     dword ptr [rax+rax+00h]
0x180009bb2  lea     rsi, [r14+rsi*2]
0x180009bb6  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009bba  mov     rax, [rbx+88h]
0x180009bc1  mov     rcx, [rbx+80h]
0x180009bc8  mov     rdx, rsi; unsigned __int16 *
0x180009bcb  test    r9, r9
0x180009bce  jz      short loc_180009BF2
0x180009bd0  mov     [rsp+278h+Arguments], rax
0x180009bd5  mov     qword ptr [rsp+278h+nSize], rcx
0x180009bda  mov     eax, [rbx+40h]
0x180009bdd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009be1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009be8  mov     rcx, r14; this
0x180009beb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009bf0  jmp     short loc_180009C09
0x180009bf2  mov     [rsp+278h+lpBuffer], rax
0x180009bf7  mov     r9, rcx; unsigned __int16 *
0x180009bfa  lea     r8, aHsP; "%hs!%p: "
0x180009c01  mov     rcx, r14; this
0x180009c04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c09  mov     r14, rax
0x180009c0c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009c13  test    r9, r9
0x180009c16  jz      short loc_180009C2D
0x180009c18  lea     r8, aCallerP; "(caller: %p) "
0x180009c1f  mov     rdx, rsi; unsigned __int16 *
0x180009c22  mov     rcx, rax; this
0x180009c25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c2a  mov     r14, rax
0x180009c2d  call    cs:__imp_GetCurrentThreadId
0x180009c34  nop     dword ptr [rax+rax+00h]
0x180009c39  lea     rcx, [rsp+278h+Buffer]
0x180009c3e  mov     [rsp+278h+var_240], rcx
0x180009c43  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009c47  mov     [rsp+278h+nSize], eax
0x180009c4b  mov     eax, [rbx+44h]
0x180009c4e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009c52  mov     r9, rdi; unsigned __int16 *
0x180009c55  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009c5c  mov     rdx, rsi; unsigned __int16 *
0x180009c5f  mov     rcx, r14; this
0x180009c62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c67  cmp     [rbx+18h], r15
0x180009c6b  jnz     short loc_180009C7D
0x180009c6d  cmp     [rbx+48h], r15
0x180009c71  jnz     short loc_180009C7D
0x180009c73  cmp     [rbx+30h], r15
0x180009c77  jz      loc_180009D0D
0x180009c7d  lea     r8, asc_180042468; "    "
0x180009c84  mov     rdx, rsi; unsigned __int16 *
0x180009c87  mov     rcx, rax; this
0x180009c8a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c8f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009c93  test    r9, r9
0x180009c96  jz      short loc_180009CAA
0x180009c98  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009c9f  mov     rdx, rsi; unsigned __int16 *
0x180009ca2  mov     rcx, rax; this
0x180009ca5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009caa  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009cae  test    r9, r9
0x180009cb1  jz      short loc_180009CC5
0x180009cb3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009cba  mov     rdx, rsi; unsigned __int16 *
0x180009cbd  mov     rcx, rax; this
0x180009cc0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cc5  mov     rcx, [rbx+28h]
0x180009cc9  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009ccd  mov     rdx, rsi; unsigned __int16 *
0x180009cd0  test    rcx, rcx
0x180009cd3  jz      short loc_180009CEB
0x180009cd5  mov     [rsp+278h+lpBuffer], rcx
0x180009cda  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009ce1  mov     rcx, rax; this
0x180009ce4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ce9  jmp     short loc_180009D0D
0x180009ceb  mov     rcx, rax; this
0x180009cee  test    r9, r9
0x180009cf1  jz      short loc_180009D01
0x180009cf3  lea     r8, aHs; "[%hs]\n"
0x180009cfa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cff  jmp     short loc_180009D0D
0x180009d01  lea     r8, asc_1800424E0; "\n"
0x180009d08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d0d  xor     eax, eax
0x180009d0f  mov     rcx, [rsp+278h+var_38]
0x180009d17  xor     rcx, rsp; StackCookie
0x180009d1a  call    __security_check_cookie
0x180009d1f  mov     rbx, [rsp+278h+arg_18]
0x180009d27  add     rsp, 250h
0x180009d2e  pop     r15
0x180009d30  pop     r14
0x180009d32  pop     rdi
0x180009d33  pop     rsi
0x180009d34  pop     rbp
0x180009d35  retn
```
