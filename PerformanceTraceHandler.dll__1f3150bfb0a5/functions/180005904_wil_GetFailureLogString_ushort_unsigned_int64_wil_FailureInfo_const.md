# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005904`
- end: `0x180005bba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006564`
- `0x180006c58`
- `0x180009ca0`

## callees

- `0x180002c00`
- `0x180003710`
- `0x180005904`
- `0x180006860`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ab7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ab7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005a36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005a36`

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
          v7 = (const char *)&byte_18001E1D0;
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
0x180005904  mov     [rsp+arg_18], rbx
0x180005909  push    rbp
0x18000590a  push    rsi
0x18000590b  push    rdi
0x18000590c  push    r14
0x18000590e  push    r15
0x180005910  sub     rsp, 250h
0x180005917  mov     rax, cs:__security_cookie
0x18000591e  xor     rax, rsp
0x180005921  mov     [rsp+278h+var_38], rax
0x180005929  mov     rbx, r8
0x18000592c  mov     rsi, rdx
0x18000592f  mov     r14, rcx
0x180005932  xor     r15d, r15d
0x180005935  test    rdx, rdx
0x180005938  jz      loc_180005B91
0x18000593e  test    rcx, rcx
0x180005941  jz      loc_180005B91
0x180005947  mov     [rcx], r15w
0x18000594b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005952  test    rax, rax
0x180005955  jz      short loc_180005978
0x180005957  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000595e  jz      short loc_180005978
0x180005960  mov     r8, rdx
0x180005963  mov     rdx, rcx
0x180005966  mov     rcx, rbx
0x180005969  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000596e  cmp     [r14], r15w
0x180005972  jnz     loc_180005B91
0x180005978  mov     ecx, [rbx]
0x18000597a  mov     bpl, 8
0x18000597d  test    ecx, ecx
0x18000597f  jz      short loc_1800059CA
0x180005981  sub     ecx, 1
0x180005984  jz      short loc_1800059B2
0x180005986  sub     ecx, 1
0x180005989  jz      short loc_1800059A2
0x18000598b  cmp     ecx, 1
0x18000598e  jz      short loc_180005999
0x180005990  lea     rdi, byte_18001E1D0
0x180005997  jmp     short loc_1800059D1
0x180005999  lea     rdi, aFailfast; "FailFast"
0x1800059a0  jmp     short loc_1800059D1
0x1800059a2  lea     rax, aLoghr; "LogHr"
0x1800059a9  lea     rdi, aLognt; "LogNt"
0x1800059b0  jmp     short loc_1800059C0
0x1800059b2  lea     rax, aReturnhr; "ReturnHr"
0x1800059b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800059c0  test    [rbx+4], bpl
0x1800059c4  cmovz   rdi, rax
0x1800059c8  jmp     short loc_1800059D1
0x1800059ca  lea     rdi, aException; "Exception"
0x1800059d1  xor     edx, edx; Val
0x1800059d3  mov     r8d, 200h; Size
0x1800059d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800059de  call    memset_0
0x1800059e3  test    [rbx+4], bpl
0x1800059e7  jz      short loc_180005A0C
0x1800059e9  mov     ebp, [rbx+0Ch]
0x1800059ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800059f3  test    rax, rax
0x1800059f6  jz      short loc_180005A3C
0x1800059f8  mov     r8d, 100h
0x1800059fe  lea     rdx, [rsp+278h+Buffer]
0x180005a03  mov     ecx, ebp
0x180005a05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a0a  jmp     short loc_180005A3C
0x180005a0c  mov     ebp, [rbx+8]
0x180005a0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005a14  mov     [rsp+278h+nSize], 100h; nSize
0x180005a1c  lea     rax, [rsp+278h+Buffer]
0x180005a21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005a26  mov     r9d, 400h; dwLanguageId
0x180005a2c  mov     r8d, ebp; dwMessageId
0x180005a2f  xor     edx, edx; lpSource
0x180005a31  mov     ecx, 1200h; dwFlags
0x180005a36  call    cs:__imp_FormatMessageW
0x180005a3c  lea     rsi, [r14+rsi*2]
0x180005a40  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005a44  mov     rax, [rbx+88h]
0x180005a4b  mov     rcx, [rbx+80h]
0x180005a52  mov     rdx, rsi; unsigned __int16 *
0x180005a55  test    r9, r9
0x180005a58  jz      short loc_180005A7C
0x180005a5a  mov     [rsp+278h+Arguments], rax
0x180005a5f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005a64  mov     eax, [rbx+40h]
0x180005a67  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005a6b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005a72  mov     rcx, r14; this
0x180005a75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a7a  jmp     short loc_180005A93
0x180005a7c  mov     [rsp+278h+lpBuffer], rax
0x180005a81  mov     r9, rcx; unsigned __int16 *
0x180005a84  lea     r8, aHsP; "%hs!%p: "
0x180005a8b  mov     rcx, r14; this
0x180005a8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a93  mov     r14, rax
0x180005a96  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005a9d  test    r9, r9
0x180005aa0  jz      short loc_180005AB7
0x180005aa2  lea     r8, aCallerP; "(caller: %p) "
0x180005aa9  mov     rdx, rsi; unsigned __int16 *
0x180005aac  mov     rcx, rax; this
0x180005aaf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ab4  mov     r14, rax
0x180005ab7  call    cs:__imp_GetCurrentThreadId
0x180005abd  lea     rcx, [rsp+278h+Buffer]
0x180005ac2  mov     [rsp+278h+var_240], rcx
0x180005ac7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005acb  mov     [rsp+278h+nSize], eax
0x180005acf  mov     eax, [rbx+44h]
0x180005ad2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005ad6  mov     r9, rdi; unsigned __int16 *
0x180005ad9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005ae0  mov     rdx, rsi; unsigned __int16 *
0x180005ae3  mov     rcx, r14; this
0x180005ae6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005aeb  cmp     [rbx+18h], r15
0x180005aef  jnz     short loc_180005B01
0x180005af1  cmp     [rbx+48h], r15
0x180005af5  jnz     short loc_180005B01
0x180005af7  cmp     [rbx+30h], r15
0x180005afb  jz      loc_180005B91
0x180005b01  lea     r8, asc_18001E2E8; "    "
0x180005b08  mov     rdx, rsi; unsigned __int16 *
0x180005b0b  mov     rcx, rax; this
0x180005b0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b13  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005b17  test    r9, r9
0x180005b1a  jz      short loc_180005B2E
0x180005b1c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005b23  mov     rdx, rsi; unsigned __int16 *
0x180005b26  mov     rcx, rax; this
0x180005b29  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b2e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005b32  test    r9, r9
0x180005b35  jz      short loc_180005B49
0x180005b37  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005b3e  mov     rdx, rsi; unsigned __int16 *
0x180005b41  mov     rcx, rax; this
0x180005b44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b49  mov     rcx, [rbx+28h]
0x180005b4d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005b51  mov     rdx, rsi; unsigned __int16 *
0x180005b54  test    rcx, rcx
0x180005b57  jz      short loc_180005B6F
0x180005b59  mov     [rsp+278h+lpBuffer], rcx
0x180005b5e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005b65  mov     rcx, rax; this
0x180005b68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b6d  jmp     short loc_180005B91
0x180005b6f  mov     rcx, rax; this
0x180005b72  test    r9, r9
0x180005b75  jz      short loc_180005B85
0x180005b77  lea     r8, aHs; "[%hs]\n"
0x180005b7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b83  jmp     short loc_180005B91
0x180005b85  lea     r8, asc_18001E360; "\n"
0x180005b8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b91  xor     eax, eax
0x180005b93  mov     rcx, [rsp+278h+var_38]
0x180005b9b  xor     rcx, rsp; StackCookie
0x180005b9e  call    __security_check_cookie
0x180005ba3  mov     rbx, [rsp+278h+arg_18]
0x180005bab  add     rsp, 250h
0x180005bb2  pop     r15
0x180005bb4  pop     r14
0x180005bb6  pop     rdi
0x180005bb7  pop     rsi
0x180005bb8  pop     rbp
0x180005bb9  retn
```
