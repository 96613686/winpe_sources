# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006b44`
- end: `0x180006dfa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180004c30`
- `0x180004e98`
- `0x1800074a0`

## callees

- `0x180006b44`
- `0x1800077a0`
- `0x18000a19e`
- `0x18000a1d0`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cf7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006c76`

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
          v8 = (const char *)&qword_18000E4C0;
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
0x180006b44  mov     [rsp+arg_18], rbx
0x180006b49  push    rbp
0x180006b4a  push    rsi
0x180006b4b  push    rdi
0x180006b4c  push    r14
0x180006b4e  push    r15
0x180006b50  sub     rsp, 250h
0x180006b57  mov     rax, cs:__security_cookie
0x180006b5e  xor     rax, rsp
0x180006b61  mov     [rsp+278h+var_38], rax
0x180006b69  xor     r15d, r15d
0x180006b6c  mov     rbx, r8
0x180006b6f  mov     rsi, rdx
0x180006b72  mov     r14, rcx
0x180006b75  test    rdx, rdx
0x180006b78  jz      loc_180006DD1
0x180006b7e  test    rcx, rcx
0x180006b81  jz      loc_180006DD1
0x180006b87  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b8e  mov     [rcx], r15w
0x180006b92  test    rax, rax
0x180006b95  jz      short loc_180006BB8
0x180006b97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006b9e  jz      short loc_180006BB8
0x180006ba0  mov     r8, rdx
0x180006ba3  mov     rdx, rcx
0x180006ba6  mov     rcx, rbx
0x180006ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bae  cmp     [r14], r15w
0x180006bb2  jnz     loc_180006DD1
0x180006bb8  mov     ecx, [rbx]
0x180006bba  mov     bpl, 8
0x180006bbd  test    ecx, ecx
0x180006bbf  jz      short loc_180006C0A
0x180006bc1  sub     ecx, 1
0x180006bc4  jz      short loc_180006BF2
0x180006bc6  sub     ecx, 1
0x180006bc9  jz      short loc_180006BE2
0x180006bcb  cmp     ecx, 1
0x180006bce  jz      short loc_180006BD9
0x180006bd0  lea     rdi, qword_18000E4C0
0x180006bd7  jmp     short loc_180006C11
0x180006bd9  lea     rdi, aFailfast; "FailFast"
0x180006be0  jmp     short loc_180006C11
0x180006be2  lea     rax, aLoghr; "LogHr"
0x180006be9  lea     rdi, aLognt; "LogNt"
0x180006bf0  jmp     short loc_180006C00
0x180006bf2  lea     rax, aReturnhr; "ReturnHr"
0x180006bf9  lea     rdi, aReturnnt; "ReturnNt"
0x180006c00  test    [rbx+4], bpl
0x180006c04  cmovz   rdi, rax
0x180006c08  jmp     short loc_180006C11
0x180006c0a  lea     rdi, aException; "Exception"
0x180006c11  xor     edx, edx; Val
0x180006c13  lea     rcx, [rsp+278h+Buffer]; void *
0x180006c18  mov     r8d, 200h; Size
0x180006c1e  call    memset_0
0x180006c23  test    [rbx+4], bpl
0x180006c27  jz      short loc_180006C4C
0x180006c29  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006c30  mov     ebp, [rbx+0Ch]
0x180006c33  test    rax, rax
0x180006c36  jz      short loc_180006C7C
0x180006c38  mov     r8d, 100h
0x180006c3e  lea     rdx, [rsp+278h+Buffer]
0x180006c43  mov     ecx, ebp
0x180006c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4a  jmp     short loc_180006C7C
0x180006c4c  mov     ebp, [rbx+8]
0x180006c4f  lea     rax, [rsp+278h+Buffer]
0x180006c54  mov     [rsp+278h+Arguments], r15; Arguments
0x180006c59  mov     r8d, ebp; dwMessageId
0x180006c5c  mov     [rsp+278h+nSize], 100h; nSize
0x180006c64  mov     r9d, 400h; dwLanguageId
0x180006c6a  xor     edx, edx; lpSource
0x180006c6c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006c71  mov     ecx, 1200h; dwFlags
0x180006c76  call    cs:__imp_FormatMessageW
0x180006c7c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006c80  lea     rsi, [r14+rsi*2]
0x180006c84  mov     rax, [rbx+88h]
0x180006c8b  mov     rdx, rsi; unsigned __int16 *
0x180006c8e  mov     rcx, [rbx+80h]
0x180006c95  test    r9, r9
0x180006c98  jz      short loc_180006CBC
0x180006c9a  mov     [rsp+278h+Arguments], rax
0x180006c9f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006ca6  mov     eax, [rbx+40h]
0x180006ca9  mov     qword ptr [rsp+278h+nSize], rcx
0x180006cae  mov     rcx, r14; this
0x180006cb1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006cb5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cba  jmp     short loc_180006CD3
0x180006cbc  mov     r9, rcx; unsigned __int16 *
0x180006cbf  mov     [rsp+278h+lpBuffer], rax
0x180006cc4  mov     rcx, r14; this
0x180006cc7  lea     r8, aHsP; "%hs!%p: "
0x180006cce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cd3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006cda  mov     r14, rax
0x180006cdd  test    r9, r9
0x180006ce0  jz      short loc_180006CF7
0x180006ce2  lea     r8, aCallerP; "(caller: %p) "
0x180006ce9  mov     rdx, rsi; unsigned __int16 *
0x180006cec  mov     rcx, rax; this
0x180006cef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cf4  mov     r14, rax
0x180006cf7  call    cs:__imp_GetCurrentThreadId
0x180006cfd  lea     rcx, [rsp+278h+Buffer]
0x180006d02  mov     r9, rdi; unsigned __int16 *
0x180006d05  mov     [rsp+278h+var_240], rcx
0x180006d0a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006d11  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006d15  mov     rdx, rsi; unsigned __int16 *
0x180006d18  mov     [rsp+278h+nSize], eax
0x180006d1c  mov     rcx, r14; this
0x180006d1f  mov     eax, [rbx+44h]
0x180006d22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d2b  cmp     [rbx+18h], r15
0x180006d2f  jnz     short loc_180006D41
0x180006d31  cmp     [rbx+48h], r15
0x180006d35  jnz     short loc_180006D41
0x180006d37  cmp     [rbx+30h], r15
0x180006d3b  jz      loc_180006DD1
0x180006d41  lea     r8, asc_18000E5B0; "    "
0x180006d48  mov     rdx, rsi; unsigned __int16 *
0x180006d4b  mov     rcx, rax; this
0x180006d4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d53  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006d57  test    r9, r9
0x180006d5a  jz      short loc_180006D6E
0x180006d5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006d63  mov     rdx, rsi; unsigned __int16 *
0x180006d66  mov     rcx, rax; this
0x180006d69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006d72  test    r9, r9
0x180006d75  jz      short loc_180006D89
0x180006d77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006d7e  mov     rdx, rsi; unsigned __int16 *
0x180006d81  mov     rcx, rax; this
0x180006d84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d89  mov     rcx, [rbx+28h]
0x180006d8d  mov     rdx, rsi; unsigned __int16 *
0x180006d90  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006d94  test    rcx, rcx
0x180006d97  jz      short loc_180006DAF
0x180006d99  mov     [rsp+278h+lpBuffer], rcx
0x180006d9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006da5  mov     rcx, rax; this
0x180006da8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dad  jmp     short loc_180006DD1
0x180006daf  mov     rcx, rax; this
0x180006db2  test    r9, r9
0x180006db5  jz      short loc_180006DC5
0x180006db7  lea     r8, aHs; "[%hs]\n"
0x180006dbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dc3  jmp     short loc_180006DD1
0x180006dc5  lea     r8, asc_18000E628; "\n"
0x180006dcc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dd1  xor     eax, eax
0x180006dd3  mov     rcx, [rsp+278h+var_38]
0x180006ddb  xor     rcx, rsp; StackCookie
0x180006dde  call    __security_check_cookie
0x180006de3  mov     rbx, [rsp+278h+arg_18]
0x180006deb  add     rsp, 250h
0x180006df2  pop     r15
0x180006df4  pop     r14
0x180006df6  pop     rdi
0x180006df7  pop     rsi
0x180006df8  pop     rbp
0x180006df9  retn
```
