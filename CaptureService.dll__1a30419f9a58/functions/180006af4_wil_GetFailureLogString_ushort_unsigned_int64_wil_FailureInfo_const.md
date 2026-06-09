# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006af4`
- end: `0x180006daa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000492c`
- `0x1800078e4`
- `0x18000adb0`

## callees

- `0x180002e60`
- `0x180003bc8`
- `0x180006af4`
- `0x180007be4`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ca7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ca7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c26`

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
          v7 = (const char *)&word_18002642A;
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
0x180006af4  mov     [rsp+arg_18], rbx
0x180006af9  push    rbp
0x180006afa  push    rsi
0x180006afb  push    rdi
0x180006afc  push    r14
0x180006afe  push    r15
0x180006b00  sub     rsp, 250h
0x180006b07  mov     rax, cs:__security_cookie
0x180006b0e  xor     rax, rsp
0x180006b11  mov     [rsp+278h+var_38], rax
0x180006b19  mov     rbx, r8
0x180006b1c  mov     rsi, rdx
0x180006b1f  mov     r14, rcx
0x180006b22  xor     r15d, r15d
0x180006b25  test    rdx, rdx
0x180006b28  jz      loc_180006D81
0x180006b2e  test    rcx, rcx
0x180006b31  jz      loc_180006D81
0x180006b37  mov     [rcx], r15w
0x180006b3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b42  test    rax, rax
0x180006b45  jz      short loc_180006B68
0x180006b47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006b4e  jz      short loc_180006B68
0x180006b50  mov     r8, rdx
0x180006b53  mov     rdx, rcx
0x180006b56  mov     rcx, rbx
0x180006b59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b5e  cmp     [r14], r15w
0x180006b62  jnz     loc_180006D81
0x180006b68  mov     ecx, [rbx]
0x180006b6a  mov     bpl, 8
0x180006b6d  test    ecx, ecx
0x180006b6f  jz      short loc_180006BBA
0x180006b71  sub     ecx, 1
0x180006b74  jz      short loc_180006BA2
0x180006b76  sub     ecx, 1
0x180006b79  jz      short loc_180006B92
0x180006b7b  cmp     ecx, 1
0x180006b7e  jz      short loc_180006B89
0x180006b80  lea     rdi, word_18002642A
0x180006b87  jmp     short loc_180006BC1
0x180006b89  lea     rdi, aFailfast; "FailFast"
0x180006b90  jmp     short loc_180006BC1
0x180006b92  lea     rax, aLoghr; "LogHr"
0x180006b99  lea     rdi, aLognt; "LogNt"
0x180006ba0  jmp     short loc_180006BB0
0x180006ba2  lea     rax, aReturnhr; "ReturnHr"
0x180006ba9  lea     rdi, aReturnnt; "ReturnNt"
0x180006bb0  test    [rbx+4], bpl
0x180006bb4  cmovz   rdi, rax
0x180006bb8  jmp     short loc_180006BC1
0x180006bba  lea     rdi, aException; "Exception"
0x180006bc1  xor     edx, edx; Val
0x180006bc3  mov     r8d, 200h; Size
0x180006bc9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006bce  call    memset_0
0x180006bd3  test    [rbx+4], bpl
0x180006bd7  jz      short loc_180006BFC
0x180006bd9  mov     ebp, [rbx+0Ch]
0x180006bdc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006be3  test    rax, rax
0x180006be6  jz      short loc_180006C2C
0x180006be8  mov     r8d, 100h
0x180006bee  lea     rdx, [rsp+278h+Buffer]
0x180006bf3  mov     ecx, ebp
0x180006bf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bfa  jmp     short loc_180006C2C
0x180006bfc  mov     ebp, [rbx+8]
0x180006bff  mov     [rsp+278h+Arguments], r15; Arguments
0x180006c04  mov     [rsp+278h+nSize], 100h; nSize
0x180006c0c  lea     rax, [rsp+278h+Buffer]
0x180006c11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006c16  mov     r9d, 400h; dwLanguageId
0x180006c1c  mov     r8d, ebp; dwMessageId
0x180006c1f  xor     edx, edx; lpSource
0x180006c21  mov     ecx, 1200h; dwFlags
0x180006c26  call    cs:__imp_FormatMessageW
0x180006c2c  lea     rsi, [r14+rsi*2]
0x180006c30  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006c34  mov     rax, [rbx+88h]
0x180006c3b  mov     rcx, [rbx+80h]
0x180006c42  mov     rdx, rsi; unsigned __int16 *
0x180006c45  test    r9, r9
0x180006c48  jz      short loc_180006C6C
0x180006c4a  mov     [rsp+278h+Arguments], rax
0x180006c4f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006c54  mov     eax, [rbx+40h]
0x180006c57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006c5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006c62  mov     rcx, r14; this
0x180006c65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c6a  jmp     short loc_180006C83
0x180006c6c  mov     [rsp+278h+lpBuffer], rax
0x180006c71  mov     r9, rcx; unsigned __int16 *
0x180006c74  lea     r8, aHsP; "%hs!%p: "
0x180006c7b  mov     rcx, r14; this
0x180006c7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c83  mov     r14, rax
0x180006c86  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006c8d  test    r9, r9
0x180006c90  jz      short loc_180006CA7
0x180006c92  lea     r8, aCallerP; "(caller: %p) "
0x180006c99  mov     rdx, rsi; unsigned __int16 *
0x180006c9c  mov     rcx, rax; this
0x180006c9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006ca4  mov     r14, rax
0x180006ca7  call    cs:__imp_GetCurrentThreadId
0x180006cad  lea     rcx, [rsp+278h+Buffer]
0x180006cb2  mov     [rsp+278h+var_240], rcx
0x180006cb7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006cbb  mov     [rsp+278h+nSize], eax
0x180006cbf  mov     eax, [rbx+44h]
0x180006cc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006cc6  mov     r9, rdi; unsigned __int16 *
0x180006cc9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006cd0  mov     rdx, rsi; unsigned __int16 *
0x180006cd3  mov     rcx, r14; this
0x180006cd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cdb  cmp     [rbx+18h], r15
0x180006cdf  jnz     short loc_180006CF1
0x180006ce1  cmp     [rbx+48h], r15
0x180006ce5  jnz     short loc_180006CF1
0x180006ce7  cmp     [rbx+30h], r15
0x180006ceb  jz      loc_180006D81
0x180006cf1  lea     r8, asc_180026518; "    "
0x180006cf8  mov     rdx, rsi; unsigned __int16 *
0x180006cfb  mov     rcx, rax; this
0x180006cfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d03  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006d07  test    r9, r9
0x180006d0a  jz      short loc_180006D1E
0x180006d0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006d13  mov     rdx, rsi; unsigned __int16 *
0x180006d16  mov     rcx, rax; this
0x180006d19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006d22  test    r9, r9
0x180006d25  jz      short loc_180006D39
0x180006d27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006d2e  mov     rdx, rsi; unsigned __int16 *
0x180006d31  mov     rcx, rax; this
0x180006d34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d39  mov     rcx, [rbx+28h]
0x180006d3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006d41  mov     rdx, rsi; unsigned __int16 *
0x180006d44  test    rcx, rcx
0x180006d47  jz      short loc_180006D5F
0x180006d49  mov     [rsp+278h+lpBuffer], rcx
0x180006d4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006d55  mov     rcx, rax; this
0x180006d58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d5d  jmp     short loc_180006D81
0x180006d5f  mov     rcx, rax; this
0x180006d62  test    r9, r9
0x180006d65  jz      short loc_180006D75
0x180006d67  lea     r8, aHs; "[%hs]\n"
0x180006d6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d73  jmp     short loc_180006D81
0x180006d75  lea     r8, asc_180026590; "\n"
0x180006d7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d81  xor     eax, eax
0x180006d83  mov     rcx, [rsp+278h+var_38]
0x180006d8b  xor     rcx, rsp; StackCookie
0x180006d8e  call    __security_check_cookie
0x180006d93  mov     rbx, [rsp+278h+arg_18]
0x180006d9b  add     rsp, 250h
0x180006da2  pop     r15
0x180006da4  pop     r14
0x180006da6  pop     rdi
0x180006da7  pop     rsi
0x180006da8  pop     rbp
0x180006da9  retn
```
