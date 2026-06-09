# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006bb4`
- end: `0x180006e77`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004ac0`
- `0x180007900`
- `0x180007ffc`
- `0x18000b1a0`

## callees

- `0x180002a60`
- `0x180003534`
- `0x180006bb4`
- `0x180007c14`
- `0x180052010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d6d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d6d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006ce6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006ce6`

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
          v7 = (const char *)&word_18005A08A;
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
0x180006bb4  mov     [rsp+arg_18], rbx
0x180006bb9  push    rbp
0x180006bba  push    rsi
0x180006bbb  push    rdi
0x180006bbc  push    r14
0x180006bbe  push    r15
0x180006bc0  sub     rsp, 250h
0x180006bc7  mov     rax, cs:__security_cookie
0x180006bce  xor     rax, rsp
0x180006bd1  mov     [rsp+278h+var_38], rax
0x180006bd9  mov     rbx, r8
0x180006bdc  mov     rsi, rdx
0x180006bdf  mov     r14, rcx
0x180006be2  xor     r15d, r15d
0x180006be5  test    rdx, rdx
0x180006be8  jz      loc_180006E4D
0x180006bee  test    rcx, rcx
0x180006bf1  jz      loc_180006E4D
0x180006bf7  mov     [rcx], r15w
0x180006bfb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c02  test    rax, rax
0x180006c05  jz      short loc_180006C28
0x180006c07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006c0e  jz      short loc_180006C28
0x180006c10  mov     r8, rdx
0x180006c13  mov     rdx, rcx
0x180006c16  mov     rcx, rbx
0x180006c19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c1e  cmp     [r14], r15w
0x180006c22  jnz     loc_180006E4D
0x180006c28  mov     ecx, [rbx]
0x180006c2a  mov     bpl, 8
0x180006c2d  test    ecx, ecx
0x180006c2f  jz      short loc_180006C7A
0x180006c31  sub     ecx, 1
0x180006c34  jz      short loc_180006C62
0x180006c36  sub     ecx, 1
0x180006c39  jz      short loc_180006C52
0x180006c3b  cmp     ecx, 1
0x180006c3e  jz      short loc_180006C49
0x180006c40  lea     rdi, word_18005A08A
0x180006c47  jmp     short loc_180006C81
0x180006c49  lea     rdi, aFailfast; "FailFast"
0x180006c50  jmp     short loc_180006C81
0x180006c52  lea     rax, aLoghr; "LogHr"
0x180006c59  lea     rdi, aLognt; "LogNt"
0x180006c60  jmp     short loc_180006C70
0x180006c62  lea     rax, aReturnhr; "ReturnHr"
0x180006c69  lea     rdi, aReturnnt; "ReturnNt"
0x180006c70  test    [rbx+4], bpl
0x180006c74  cmovz   rdi, rax
0x180006c78  jmp     short loc_180006C81
0x180006c7a  lea     rdi, aException; "Exception"
0x180006c81  xor     edx, edx; Val
0x180006c83  mov     r8d, 200h; Size
0x180006c89  lea     rcx, [rsp+278h+Buffer]; void *
0x180006c8e  call    memset_0
0x180006c93  test    [rbx+4], bpl
0x180006c97  jz      short loc_180006CBC
0x180006c99  mov     ebp, [rbx+0Ch]
0x180006c9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006ca3  test    rax, rax
0x180006ca6  jz      short loc_180006CF2
0x180006ca8  mov     r8d, 100h
0x180006cae  lea     rdx, [rsp+278h+Buffer]
0x180006cb3  mov     ecx, ebp
0x180006cb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cba  jmp     short loc_180006CF2
0x180006cbc  mov     ebp, [rbx+8]
0x180006cbf  mov     [rsp+278h+Arguments], r15; Arguments
0x180006cc4  mov     [rsp+278h+nSize], 100h; nSize
0x180006ccc  lea     rax, [rsp+278h+Buffer]
0x180006cd1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006cd6  mov     r9d, 400h; dwLanguageId
0x180006cdc  mov     r8d, ebp; dwMessageId
0x180006cdf  xor     edx, edx; lpSource
0x180006ce1  mov     ecx, 1200h; dwFlags
0x180006ce6  call    cs:__imp_FormatMessageW
0x180006ced  nop     dword ptr [rax+rax+00h]
0x180006cf2  lea     rsi, [r14+rsi*2]
0x180006cf6  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006cfa  mov     rax, [rbx+88h]
0x180006d01  mov     rcx, [rbx+80h]
0x180006d08  mov     rdx, rsi; unsigned __int16 *
0x180006d0b  test    r9, r9
0x180006d0e  jz      short loc_180006D32
0x180006d10  mov     [rsp+278h+Arguments], rax
0x180006d15  mov     qword ptr [rsp+278h+nSize], rcx
0x180006d1a  mov     eax, [rbx+40h]
0x180006d1d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d21  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006d28  mov     rcx, r14; this
0x180006d2b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d30  jmp     short loc_180006D49
0x180006d32  mov     [rsp+278h+lpBuffer], rax
0x180006d37  mov     r9, rcx; unsigned __int16 *
0x180006d3a  lea     r8, aHsP; "%hs!%p: "
0x180006d41  mov     rcx, r14; this
0x180006d44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d49  mov     r14, rax
0x180006d4c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006d53  test    r9, r9
0x180006d56  jz      short loc_180006D6D
0x180006d58  lea     r8, aCallerP; "(caller: %p) "
0x180006d5f  mov     rdx, rsi; unsigned __int16 *
0x180006d62  mov     rcx, rax; this
0x180006d65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d6a  mov     r14, rax
0x180006d6d  call    cs:__imp_GetCurrentThreadId
0x180006d74  nop     dword ptr [rax+rax+00h]
0x180006d79  lea     rcx, [rsp+278h+Buffer]
0x180006d7e  mov     [rsp+278h+var_240], rcx
0x180006d83  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006d87  mov     [rsp+278h+nSize], eax
0x180006d8b  mov     eax, [rbx+44h]
0x180006d8e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d92  mov     r9, rdi; unsigned __int16 *
0x180006d95  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006d9c  mov     rdx, rsi; unsigned __int16 *
0x180006d9f  mov     rcx, r14; this
0x180006da2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006da7  cmp     [rbx+18h], r15
0x180006dab  jnz     short loc_180006DBD
0x180006dad  cmp     [rbx+48h], r15
0x180006db1  jnz     short loc_180006DBD
0x180006db3  cmp     [rbx+30h], r15
0x180006db7  jz      loc_180006E4D
0x180006dbd  lea     r8, asc_18005A178; "    "
0x180006dc4  mov     rdx, rsi; unsigned __int16 *
0x180006dc7  mov     rcx, rax; this
0x180006dca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dcf  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006dd3  test    r9, r9
0x180006dd6  jz      short loc_180006DEA
0x180006dd8  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006ddf  mov     rdx, rsi; unsigned __int16 *
0x180006de2  mov     rcx, rax; this
0x180006de5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dea  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006dee  test    r9, r9
0x180006df1  jz      short loc_180006E05
0x180006df3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006dfa  mov     rdx, rsi; unsigned __int16 *
0x180006dfd  mov     rcx, rax; this
0x180006e00  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e05  mov     rcx, [rbx+28h]
0x180006e09  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006e0d  mov     rdx, rsi; unsigned __int16 *
0x180006e10  test    rcx, rcx
0x180006e13  jz      short loc_180006E2B
0x180006e15  mov     [rsp+278h+lpBuffer], rcx
0x180006e1a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006e21  mov     rcx, rax; this
0x180006e24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e29  jmp     short loc_180006E4D
0x180006e2b  mov     rcx, rax; this
0x180006e2e  test    r9, r9
0x180006e31  jz      short loc_180006E41
0x180006e33  lea     r8, aHs; "[%hs]\n"
0x180006e3a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e3f  jmp     short loc_180006E4D
0x180006e41  lea     r8, asc_18005A1F0; "\n"
0x180006e48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e4d  xor     eax, eax
0x180006e4f  mov     rcx, [rsp+278h+var_38]
0x180006e57  xor     rcx, rsp; StackCookie
0x180006e5a  call    __security_check_cookie
0x180006e5f  mov     rbx, [rsp+278h+arg_18]
0x180006e67  add     rsp, 250h
0x180006e6e  pop     r15
0x180006e70  pop     r14
0x180006e72  pop     rdi
0x180006e73  pop     rsi
0x180006e74  pop     rbp
0x180006e75  retn
```
