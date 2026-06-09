# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800039d4`
- end: `0x180003c8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800025ec`
- `0x180002854`
- `0x180004338`
- `0x180005e70`

## callees

- `0x1800039d4`
- `0x180004638`
- `0x18001143a`
- `0x180011460`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003b87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003b06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003b06`

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
          v7 = (const char *)&qword_18001B630;
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
0x1800039d4  mov     [rsp+arg_18], rbx
0x1800039d9  push    rbp
0x1800039da  push    rsi
0x1800039db  push    rdi
0x1800039dc  push    r14
0x1800039de  push    r15
0x1800039e0  sub     rsp, 250h
0x1800039e7  mov     rax, cs:__security_cookie
0x1800039ee  xor     rax, rsp
0x1800039f1  mov     [rsp+278h+var_38], rax
0x1800039f9  mov     rbx, r8
0x1800039fc  mov     rsi, rdx
0x1800039ff  mov     r14, rcx
0x180003a02  xor     r15d, r15d
0x180003a05  test    rdx, rdx
0x180003a08  jz      loc_180003C61
0x180003a0e  test    rcx, rcx
0x180003a11  jz      loc_180003C61
0x180003a17  mov     [rcx], r15w
0x180003a1b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003a22  test    rax, rax
0x180003a25  jz      short loc_180003A48
0x180003a27  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003a2e  jz      short loc_180003A48
0x180003a30  mov     r8, rdx
0x180003a33  mov     rdx, rcx
0x180003a36  mov     rcx, rbx
0x180003a39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a3e  cmp     [r14], r15w
0x180003a42  jnz     loc_180003C61
0x180003a48  mov     ecx, [rbx]
0x180003a4a  mov     bpl, 8
0x180003a4d  test    ecx, ecx
0x180003a4f  jz      short loc_180003A9A
0x180003a51  sub     ecx, 1
0x180003a54  jz      short loc_180003A82
0x180003a56  sub     ecx, 1
0x180003a59  jz      short loc_180003A72
0x180003a5b  cmp     ecx, 1
0x180003a5e  jz      short loc_180003A69
0x180003a60  lea     rdi, qword_18001B630
0x180003a67  jmp     short loc_180003AA1
0x180003a69  lea     rdi, aFailfast; "FailFast"
0x180003a70  jmp     short loc_180003AA1
0x180003a72  lea     rax, aLoghr; "LogHr"
0x180003a79  lea     rdi, aLognt; "LogNt"
0x180003a80  jmp     short loc_180003A90
0x180003a82  lea     rax, aReturnhr; "ReturnHr"
0x180003a89  lea     rdi, aReturnnt; "ReturnNt"
0x180003a90  test    [rbx+4], bpl
0x180003a94  cmovz   rdi, rax
0x180003a98  jmp     short loc_180003AA1
0x180003a9a  lea     rdi, aException; "Exception"
0x180003aa1  xor     edx, edx; Val
0x180003aa3  mov     r8d, 200h; Size
0x180003aa9  lea     rcx, [rsp+278h+Buffer]; void *
0x180003aae  call    memset_0
0x180003ab3  test    [rbx+4], bpl
0x180003ab7  jz      short loc_180003ADC
0x180003ab9  mov     ebp, [rbx+0Ch]
0x180003abc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003ac3  test    rax, rax
0x180003ac6  jz      short loc_180003B0C
0x180003ac8  mov     r8d, 100h
0x180003ace  lea     rdx, [rsp+278h+Buffer]
0x180003ad3  mov     ecx, ebp
0x180003ad5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ada  jmp     short loc_180003B0C
0x180003adc  mov     ebp, [rbx+8]
0x180003adf  mov     [rsp+278h+Arguments], r15; Arguments
0x180003ae4  mov     [rsp+278h+nSize], 100h; nSize
0x180003aec  lea     rax, [rsp+278h+Buffer]
0x180003af1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003af6  mov     r9d, 400h; dwLanguageId
0x180003afc  mov     r8d, ebp; dwMessageId
0x180003aff  xor     edx, edx; lpSource
0x180003b01  mov     ecx, 1200h; dwFlags
0x180003b06  call    cs:__imp_FormatMessageW
0x180003b0c  lea     rsi, [r14+rsi*2]
0x180003b10  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003b14  mov     rax, [rbx+88h]
0x180003b1b  mov     rcx, [rbx+80h]
0x180003b22  mov     rdx, rsi; unsigned __int16 *
0x180003b25  test    r9, r9
0x180003b28  jz      short loc_180003B4C
0x180003b2a  mov     [rsp+278h+Arguments], rax
0x180003b2f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003b34  mov     eax, [rbx+40h]
0x180003b37  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003b3b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003b42  mov     rcx, r14; this
0x180003b45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b4a  jmp     short loc_180003B63
0x180003b4c  mov     [rsp+278h+lpBuffer], rax
0x180003b51  mov     r9, rcx; unsigned __int16 *
0x180003b54  lea     r8, aHsP; "%hs!%p: "
0x180003b5b  mov     rcx, r14; this
0x180003b5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b63  mov     r14, rax
0x180003b66  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003b6d  test    r9, r9
0x180003b70  jz      short loc_180003B87
0x180003b72  lea     r8, aCallerP; "(caller: %p) "
0x180003b79  mov     rdx, rsi; unsigned __int16 *
0x180003b7c  mov     rcx, rax; this
0x180003b7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b84  mov     r14, rax
0x180003b87  call    cs:__imp_GetCurrentThreadId
0x180003b8d  lea     rcx, [rsp+278h+Buffer]
0x180003b92  mov     [rsp+278h+var_240], rcx
0x180003b97  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003b9b  mov     [rsp+278h+nSize], eax
0x180003b9f  mov     eax, [rbx+44h]
0x180003ba2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003ba6  mov     r9, rdi; unsigned __int16 *
0x180003ba9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003bb0  mov     rdx, rsi; unsigned __int16 *
0x180003bb3  mov     rcx, r14; this
0x180003bb6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bbb  cmp     [rbx+18h], r15
0x180003bbf  jnz     short loc_180003BD1
0x180003bc1  cmp     [rbx+48h], r15
0x180003bc5  jnz     short loc_180003BD1
0x180003bc7  cmp     [rbx+30h], r15
0x180003bcb  jz      loc_180003C61
0x180003bd1  lea     r8, asc_18001B720; "    "
0x180003bd8  mov     rdx, rsi; unsigned __int16 *
0x180003bdb  mov     rcx, rax; this
0x180003bde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003be3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003be7  test    r9, r9
0x180003bea  jz      short loc_180003BFE
0x180003bec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003bf3  mov     rdx, rsi; unsigned __int16 *
0x180003bf6  mov     rcx, rax; this
0x180003bf9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bfe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003c02  test    r9, r9
0x180003c05  jz      short loc_180003C19
0x180003c07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003c0e  mov     rdx, rsi; unsigned __int16 *
0x180003c11  mov     rcx, rax; this
0x180003c14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c19  mov     rcx, [rbx+28h]
0x180003c1d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003c21  mov     rdx, rsi; unsigned __int16 *
0x180003c24  test    rcx, rcx
0x180003c27  jz      short loc_180003C3F
0x180003c29  mov     [rsp+278h+lpBuffer], rcx
0x180003c2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003c35  mov     rcx, rax; this
0x180003c38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c3d  jmp     short loc_180003C61
0x180003c3f  mov     rcx, rax; this
0x180003c42  test    r9, r9
0x180003c45  jz      short loc_180003C55
0x180003c47  lea     r8, aHs; "[%hs]\n"
0x180003c4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c53  jmp     short loc_180003C61
0x180003c55  lea     r8, asc_18001B798; "\n"
0x180003c5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c61  xor     eax, eax
0x180003c63  mov     rcx, [rsp+278h+var_38]
0x180003c6b  xor     rcx, rsp; StackCookie
0x180003c6e  call    __security_check_cookie
0x180003c73  mov     rbx, [rsp+278h+arg_18]
0x180003c7b  add     rsp, 250h
0x180003c82  pop     r15
0x180003c84  pop     r14
0x180003c86  pop     rdi
0x180003c87  pop     rsi
0x180003c88  pop     rbp
0x180003c89  retn
```
