# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180077a80`
- end: `0x180077d36`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800763d4`
- `0x18007832c`

## callees

- `0x180015190`
- `0x180015ea8`
- `0x180077a80`
- `0x18007862c`
- `0x180086010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077c33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180077c33`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180077bb2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180077bb2`

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
          v8 = (const char *)&qword_1801AFCA0;
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
0x180077a80  mov     [rsp+arg_18], rbx
0x180077a85  push    rbp
0x180077a86  push    rsi
0x180077a87  push    rdi
0x180077a88  push    r14
0x180077a8a  push    r15
0x180077a8c  sub     rsp, 250h
0x180077a93  mov     rax, cs:__security_cookie
0x180077a9a  xor     rax, rsp
0x180077a9d  mov     [rsp+278h+var_38], rax
0x180077aa5  xor     r15d, r15d
0x180077aa8  mov     rbx, r8
0x180077aab  mov     rsi, rdx
0x180077aae  mov     r14, rcx
0x180077ab1  test    rdx, rdx
0x180077ab4  jz      loc_180077D0D
0x180077aba  test    rcx, rcx
0x180077abd  jz      loc_180077D0D
0x180077ac3  mov     rax, cs:g_pfnResultLoggingCallback
0x180077aca  mov     [rcx], r15w
0x180077ace  test    rax, rax
0x180077ad1  jz      short loc_180077AF4
0x180077ad3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180077ada  jz      short loc_180077AF4
0x180077adc  mov     r8, rdx
0x180077adf  mov     rdx, rcx
0x180077ae2  mov     rcx, rbx
0x180077ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077aea  cmp     [r14], r15w
0x180077aee  jnz     loc_180077D0D
0x180077af4  mov     ecx, [rbx]
0x180077af6  mov     bpl, 8
0x180077af9  test    ecx, ecx
0x180077afb  jz      short loc_180077B46
0x180077afd  sub     ecx, 1
0x180077b00  jz      short loc_180077B2E
0x180077b02  sub     ecx, 1
0x180077b05  jz      short loc_180077B1E
0x180077b07  cmp     ecx, 1
0x180077b0a  jz      short loc_180077B15
0x180077b0c  lea     rdi, qword_1801AFCA0
0x180077b13  jmp     short loc_180077B4D
0x180077b15  lea     rdi, aFailfast; "FailFast"
0x180077b1c  jmp     short loc_180077B4D
0x180077b1e  lea     rax, aLoghr; "LogHr"
0x180077b25  lea     rdi, aLognt; "LogNt"
0x180077b2c  jmp     short loc_180077B3C
0x180077b2e  lea     rax, aReturnhr; "ReturnHr"
0x180077b35  lea     rdi, aReturnnt; "ReturnNt"
0x180077b3c  test    [rbx+4], bpl
0x180077b40  cmovz   rdi, rax
0x180077b44  jmp     short loc_180077B4D
0x180077b46  lea     rdi, aException; "Exception"
0x180077b4d  xor     edx, edx; Val
0x180077b4f  lea     rcx, [rsp+278h+Buffer]; void *
0x180077b54  mov     r8d, 200h; Size
0x180077b5a  call    memset_0
0x180077b5f  test    [rbx+4], bpl
0x180077b63  jz      short loc_180077B88
0x180077b65  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180077b6c  mov     ebp, [rbx+0Ch]
0x180077b6f  test    rax, rax
0x180077b72  jz      short loc_180077BB8
0x180077b74  mov     r8d, 100h
0x180077b7a  lea     rdx, [rsp+278h+Buffer]
0x180077b7f  mov     ecx, ebp
0x180077b81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180077b86  jmp     short loc_180077BB8
0x180077b88  mov     ebp, [rbx+8]
0x180077b8b  lea     rax, [rsp+278h+Buffer]
0x180077b90  mov     [rsp+278h+Arguments], r15; Arguments
0x180077b95  mov     r8d, ebp; dwMessageId
0x180077b98  mov     [rsp+278h+nSize], 100h; nSize
0x180077ba0  mov     r9d, 400h; dwLanguageId
0x180077ba6  xor     edx, edx; lpSource
0x180077ba8  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180077bad  mov     ecx, 1200h; dwFlags
0x180077bb2  call    cs:__imp_FormatMessageW
0x180077bb8  mov     r9, [rbx+38h]; unsigned __int16 *
0x180077bbc  lea     rsi, [r14+rsi*2]
0x180077bc0  mov     rax, [rbx+88h]
0x180077bc7  mov     rdx, rsi; unsigned __int16 *
0x180077bca  mov     rcx, [rbx+80h]
0x180077bd1  test    r9, r9
0x180077bd4  jz      short loc_180077BF8
0x180077bd6  mov     [rsp+278h+Arguments], rax
0x180077bdb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180077be2  mov     eax, [rbx+40h]
0x180077be5  mov     qword ptr [rsp+278h+nSize], rcx
0x180077bea  mov     rcx, r14; this
0x180077bed  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180077bf1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077bf6  jmp     short loc_180077C0F
0x180077bf8  mov     r9, rcx; unsigned __int16 *
0x180077bfb  mov     [rsp+278h+lpBuffer], rax
0x180077c00  mov     rcx, r14; this
0x180077c03  lea     r8, aHsP; "%hs!%p: "
0x180077c0a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077c0f  mov     r9, [rbx+90h]; unsigned __int16 *
0x180077c16  mov     r14, rax
0x180077c19  test    r9, r9
0x180077c1c  jz      short loc_180077C33
0x180077c1e  lea     r8, aCallerP; "(caller: %p) "
0x180077c25  mov     rdx, rsi; unsigned __int16 *
0x180077c28  mov     rcx, rax; this
0x180077c2b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077c30  mov     r14, rax
0x180077c33  call    cs:__imp_GetCurrentThreadId
0x180077c39  lea     rcx, [rsp+278h+Buffer]
0x180077c3e  mov     r9, rdi; unsigned __int16 *
0x180077c41  mov     [rsp+278h+var_240], rcx
0x180077c46  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180077c4d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180077c51  mov     rdx, rsi; unsigned __int16 *
0x180077c54  mov     [rsp+278h+nSize], eax
0x180077c58  mov     rcx, r14; this
0x180077c5b  mov     eax, [rbx+44h]
0x180077c5e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180077c62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077c67  cmp     [rbx+18h], r15
0x180077c6b  jnz     short loc_180077C7D
0x180077c6d  cmp     [rbx+48h], r15
0x180077c71  jnz     short loc_180077C7D
0x180077c73  cmp     [rbx+30h], r15
0x180077c77  jz      loc_180077D0D
0x180077c7d  lea     r8, asc_1801AFD90; "    "
0x180077c84  mov     rdx, rsi; unsigned __int16 *
0x180077c87  mov     rcx, rax; this
0x180077c8a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077c8f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180077c93  test    r9, r9
0x180077c96  jz      short loc_180077CAA
0x180077c98  lea     r8, aMsgWs; "Msg:[%ws] "
0x180077c9f  mov     rdx, rsi; unsigned __int16 *
0x180077ca2  mov     rcx, rax; this
0x180077ca5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077caa  mov     r9, [rbx+48h]; unsigned __int16 *
0x180077cae  test    r9, r9
0x180077cb1  jz      short loc_180077CC5
0x180077cb3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180077cba  mov     rdx, rsi; unsigned __int16 *
0x180077cbd  mov     rcx, rax; this
0x180077cc0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077cc5  mov     rcx, [rbx+28h]
0x180077cc9  mov     rdx, rsi; unsigned __int16 *
0x180077ccc  mov     r9, [rbx+30h]; unsigned __int16 *
0x180077cd0  test    rcx, rcx
0x180077cd3  jz      short loc_180077CEB
0x180077cd5  mov     [rsp+278h+lpBuffer], rcx
0x180077cda  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180077ce1  mov     rcx, rax; this
0x180077ce4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077ce9  jmp     short loc_180077D0D
0x180077ceb  mov     rcx, rax; this
0x180077cee  test    r9, r9
0x180077cf1  jz      short loc_180077D01
0x180077cf3  lea     r8, aHs; "[%hs]\n"
0x180077cfa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077cff  jmp     short loc_180077D0D
0x180077d01  lea     r8, asc_1801AFC9C; "\n"
0x180077d08  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077d0d  xor     eax, eax
0x180077d0f  mov     rcx, [rsp+278h+var_38]
0x180077d17  xor     rcx, rsp; StackCookie
0x180077d1a  call    __security_check_cookie
0x180077d1f  mov     rbx, [rsp+278h+arg_18]
0x180077d27  add     rsp, 250h
0x180077d2e  pop     r15
0x180077d30  pop     r14
0x180077d32  pop     rdi
0x180077d33  pop     rsi
0x180077d34  pop     rbp
0x180077d35  retn
```
