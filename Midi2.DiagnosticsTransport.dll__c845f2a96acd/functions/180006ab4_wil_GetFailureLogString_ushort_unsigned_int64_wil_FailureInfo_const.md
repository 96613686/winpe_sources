# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006ab4`
- end: `0x180006d6a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800044a4`
- `0x180004714`
- `0x180007580`
- `0x18000a200`

## callees

- `0x1800033d0`
- `0x180004170`
- `0x180006ab4`
- `0x180007880`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c67`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006c67`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006be6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006be6`

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
          v7 = (const char *)&word_1800151EA;
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
0x180006ab4  mov     [rsp+arg_18], rbx
0x180006ab9  push    rbp
0x180006aba  push    rsi
0x180006abb  push    rdi
0x180006abc  push    r14
0x180006abe  push    r15
0x180006ac0  sub     rsp, 250h
0x180006ac7  mov     rax, cs:__security_cookie
0x180006ace  xor     rax, rsp
0x180006ad1  mov     [rsp+278h+var_38], rax
0x180006ad9  mov     rbx, r8
0x180006adc  mov     rsi, rdx
0x180006adf  mov     r14, rcx
0x180006ae2  xor     r15d, r15d
0x180006ae5  test    rdx, rdx
0x180006ae8  jz      loc_180006D41
0x180006aee  test    rcx, rcx
0x180006af1  jz      loc_180006D41
0x180006af7  mov     [rcx], r15w
0x180006afb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b02  test    rax, rax
0x180006b05  jz      short loc_180006B28
0x180006b07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006b0e  jz      short loc_180006B28
0x180006b10  mov     r8, rdx
0x180006b13  mov     rdx, rcx
0x180006b16  mov     rcx, rbx
0x180006b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b1e  cmp     [r14], r15w
0x180006b22  jnz     loc_180006D41
0x180006b28  mov     ecx, [rbx]
0x180006b2a  mov     bpl, 8
0x180006b2d  test    ecx, ecx
0x180006b2f  jz      short loc_180006B7A
0x180006b31  sub     ecx, 1
0x180006b34  jz      short loc_180006B62
0x180006b36  sub     ecx, 1
0x180006b39  jz      short loc_180006B52
0x180006b3b  cmp     ecx, 1
0x180006b3e  jz      short loc_180006B49
0x180006b40  lea     rdi, word_1800151EA
0x180006b47  jmp     short loc_180006B81
0x180006b49  lea     rdi, aFailfast; "FailFast"
0x180006b50  jmp     short loc_180006B81
0x180006b52  lea     rax, aLoghr; "LogHr"
0x180006b59  lea     rdi, aLognt; "LogNt"
0x180006b60  jmp     short loc_180006B70
0x180006b62  lea     rax, aReturnhr; "ReturnHr"
0x180006b69  lea     rdi, aReturnnt; "ReturnNt"
0x180006b70  test    [rbx+4], bpl
0x180006b74  cmovz   rdi, rax
0x180006b78  jmp     short loc_180006B81
0x180006b7a  lea     rdi, aException; "Exception"
0x180006b81  xor     edx, edx; Val
0x180006b83  mov     r8d, 200h; Size
0x180006b89  lea     rcx, [rsp+278h+Buffer]; void *
0x180006b8e  call    memset_0
0x180006b93  test    [rbx+4], bpl
0x180006b97  jz      short loc_180006BBC
0x180006b99  mov     ebp, [rbx+0Ch]
0x180006b9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006ba3  test    rax, rax
0x180006ba6  jz      short loc_180006BEC
0x180006ba8  mov     r8d, 100h
0x180006bae  lea     rdx, [rsp+278h+Buffer]
0x180006bb3  mov     ecx, ebp
0x180006bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bba  jmp     short loc_180006BEC
0x180006bbc  mov     ebp, [rbx+8]
0x180006bbf  mov     [rsp+278h+Arguments], r15; Arguments
0x180006bc4  mov     [rsp+278h+nSize], 100h; nSize
0x180006bcc  lea     rax, [rsp+278h+Buffer]
0x180006bd1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006bd6  mov     r9d, 400h; dwLanguageId
0x180006bdc  mov     r8d, ebp; dwMessageId
0x180006bdf  xor     edx, edx; lpSource
0x180006be1  mov     ecx, 1200h; dwFlags
0x180006be6  call    cs:__imp_FormatMessageW
0x180006bec  lea     rsi, [r14+rsi*2]
0x180006bf0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006bf4  mov     rax, [rbx+88h]
0x180006bfb  mov     rcx, [rbx+80h]
0x180006c02  mov     rdx, rsi; unsigned __int16 *
0x180006c05  test    r9, r9
0x180006c08  jz      short loc_180006C2C
0x180006c0a  mov     [rsp+278h+Arguments], rax
0x180006c0f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006c14  mov     eax, [rbx+40h]
0x180006c17  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006c1b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006c22  mov     rcx, r14; this
0x180006c25  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c2a  jmp     short loc_180006C43
0x180006c2c  mov     [rsp+278h+lpBuffer], rax
0x180006c31  mov     r9, rcx; unsigned __int16 *
0x180006c34  lea     r8, aHsP; "%hs!%p: "
0x180006c3b  mov     rcx, r14; this
0x180006c3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c43  mov     r14, rax
0x180006c46  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006c4d  test    r9, r9
0x180006c50  jz      short loc_180006C67
0x180006c52  lea     r8, aCallerP; "(caller: %p) "
0x180006c59  mov     rdx, rsi; unsigned __int16 *
0x180006c5c  mov     rcx, rax; this
0x180006c5f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c64  mov     r14, rax
0x180006c67  call    cs:__imp_GetCurrentThreadId
0x180006c6d  lea     rcx, [rsp+278h+Buffer]
0x180006c72  mov     [rsp+278h+var_240], rcx
0x180006c77  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006c7b  mov     [rsp+278h+nSize], eax
0x180006c7f  mov     eax, [rbx+44h]
0x180006c82  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006c86  mov     r9, rdi; unsigned __int16 *
0x180006c89  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006c90  mov     rdx, rsi; unsigned __int16 *
0x180006c93  mov     rcx, r14; this
0x180006c96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c9b  cmp     [rbx+18h], r15
0x180006c9f  jnz     short loc_180006CB1
0x180006ca1  cmp     [rbx+48h], r15
0x180006ca5  jnz     short loc_180006CB1
0x180006ca7  cmp     [rbx+30h], r15
0x180006cab  jz      loc_180006D41
0x180006cb1  lea     r8, asc_1800152F8; "    "
0x180006cb8  mov     rdx, rsi; unsigned __int16 *
0x180006cbb  mov     rcx, rax; this
0x180006cbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cc3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006cc7  test    r9, r9
0x180006cca  jz      short loc_180006CDE
0x180006ccc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006cd3  mov     rdx, rsi; unsigned __int16 *
0x180006cd6  mov     rcx, rax; this
0x180006cd9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cde  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006ce2  test    r9, r9
0x180006ce5  jz      short loc_180006CF9
0x180006ce7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006cee  mov     rdx, rsi; unsigned __int16 *
0x180006cf1  mov     rcx, rax; this
0x180006cf4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006cf9  mov     rcx, [rbx+28h]
0x180006cfd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006d01  mov     rdx, rsi; unsigned __int16 *
0x180006d04  test    rcx, rcx
0x180006d07  jz      short loc_180006D1F
0x180006d09  mov     [rsp+278h+lpBuffer], rcx
0x180006d0e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006d15  mov     rcx, rax; this
0x180006d18  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d1d  jmp     short loc_180006D41
0x180006d1f  mov     rcx, rax; this
0x180006d22  test    r9, r9
0x180006d25  jz      short loc_180006D35
0x180006d27  lea     r8, aHs; "[%hs]\n"
0x180006d2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d33  jmp     short loc_180006D41
0x180006d35  lea     r8, asc_180015370; "\n"
0x180006d3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d41  xor     eax, eax
0x180006d43  mov     rcx, [rsp+278h+var_38]
0x180006d4b  xor     rcx, rsp; StackCookie
0x180006d4e  call    __security_check_cookie
0x180006d53  mov     rbx, [rsp+278h+arg_18]
0x180006d5b  add     rsp, 250h
0x180006d62  pop     r15
0x180006d64  pop     r14
0x180006d66  pop     rdi
0x180006d67  pop     rsi
0x180006d68  pop     rbp
0x180006d69  retn
```
