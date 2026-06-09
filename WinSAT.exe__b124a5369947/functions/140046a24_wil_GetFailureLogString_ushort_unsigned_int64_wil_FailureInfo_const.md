# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140046a24`
- end: `0x140046cda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14004469c`
- `0x1400484b4`
- `0x14004b590`

## callees

- `0x140003611`
- `0x140046a24`
- `0x1400487b4`
- `0x140113220`
- `0x14011a010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140046bd7`
- `KERNEL32!GetCurrentThreadId` at `0x140046bd7`
- `KERNEL32!FormatMessageW` at `0x140046b56`
- `KERNEL32!FormatMessageW` at `0x140046b56`

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
          v7 = (const char *)&dword_14012B314;
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
0x140046a24  mov     [rsp+arg_18], rbx
0x140046a29  push    rbp
0x140046a2a  push    rsi
0x140046a2b  push    rdi
0x140046a2c  push    r14
0x140046a2e  push    r15
0x140046a30  sub     rsp, 250h
0x140046a37  mov     rax, cs:__security_cookie
0x140046a3e  xor     rax, rsp
0x140046a41  mov     [rsp+278h+var_38], rax
0x140046a49  mov     rbx, r8
0x140046a4c  mov     rsi, rdx
0x140046a4f  mov     r14, rcx
0x140046a52  xor     r15d, r15d
0x140046a55  test    rdx, rdx
0x140046a58  jz      loc_140046CB1
0x140046a5e  test    rcx, rcx
0x140046a61  jz      loc_140046CB1
0x140046a67  mov     [rcx], r15w
0x140046a6b  mov     rax, cs:g_pfnResultLoggingCallback
0x140046a72  test    rax, rax
0x140046a75  jz      short loc_140046A98
0x140046a77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140046a7e  jz      short loc_140046A98
0x140046a80  mov     r8, rdx
0x140046a83  mov     rdx, rcx
0x140046a86  mov     rcx, rbx
0x140046a89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046a8e  cmp     [r14], r15w
0x140046a92  jnz     loc_140046CB1
0x140046a98  mov     ecx, [rbx]
0x140046a9a  mov     bpl, 8
0x140046a9d  test    ecx, ecx
0x140046a9f  jz      short loc_140046AEA
0x140046aa1  sub     ecx, 1
0x140046aa4  jz      short loc_140046AD2
0x140046aa6  sub     ecx, 1
0x140046aa9  jz      short loc_140046AC2
0x140046aab  cmp     ecx, 1
0x140046aae  jz      short loc_140046AB9
0x140046ab0  lea     rdi, dword_14012B314
0x140046ab7  jmp     short loc_140046AF1
0x140046ab9  lea     rdi, aFailfast; "FailFast"
0x140046ac0  jmp     short loc_140046AF1
0x140046ac2  lea     rax, aLoghr; "LogHr"
0x140046ac9  lea     rdi, aLognt; "LogNt"
0x140046ad0  jmp     short loc_140046AE0
0x140046ad2  lea     rax, aReturnhr; "ReturnHr"
0x140046ad9  lea     rdi, aReturnnt; "ReturnNt"
0x140046ae0  test    [rbx+4], bpl
0x140046ae4  cmovz   rdi, rax
0x140046ae8  jmp     short loc_140046AF1
0x140046aea  lea     rdi, aException; "Exception"
0x140046af1  xor     edx, edx; Val
0x140046af3  mov     r8d, 200h; Size
0x140046af9  lea     rcx, [rsp+278h+Buffer]; void *
0x140046afe  call    memset_0
0x140046b03  test    [rbx+4], bpl
0x140046b07  jz      short loc_140046B2C
0x140046b09  mov     ebp, [rbx+0Ch]
0x140046b0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140046b13  test    rax, rax
0x140046b16  jz      short loc_140046B5C
0x140046b18  mov     r8d, 100h
0x140046b1e  lea     rdx, [rsp+278h+Buffer]
0x140046b23  mov     ecx, ebp
0x140046b25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140046b2a  jmp     short loc_140046B5C
0x140046b2c  mov     ebp, [rbx+8]
0x140046b2f  mov     [rsp+278h+Arguments], r15; Arguments
0x140046b34  mov     [rsp+278h+nSize], 100h; nSize
0x140046b3c  lea     rax, [rsp+278h+Buffer]
0x140046b41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140046b46  mov     r9d, 400h; dwLanguageId
0x140046b4c  mov     r8d, ebp; dwMessageId
0x140046b4f  xor     edx, edx; lpSource
0x140046b51  mov     ecx, 1200h; dwFlags
0x140046b56  call    cs:__imp_FormatMessageW
0x140046b5c  lea     rsi, [r14+rsi*2]
0x140046b60  mov     r9, [rbx+38h]; unsigned __int16 *
0x140046b64  mov     rax, [rbx+88h]
0x140046b6b  mov     rcx, [rbx+80h]
0x140046b72  mov     rdx, rsi; unsigned __int16 *
0x140046b75  test    r9, r9
0x140046b78  jz      short loc_140046B9C
0x140046b7a  mov     [rsp+278h+Arguments], rax
0x140046b7f  mov     qword ptr [rsp+278h+nSize], rcx
0x140046b84  mov     eax, [rbx+40h]
0x140046b87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140046b8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140046b92  mov     rcx, r14; this
0x140046b95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046b9a  jmp     short loc_140046BB3
0x140046b9c  mov     [rsp+278h+lpBuffer], rax
0x140046ba1  mov     r9, rcx; unsigned __int16 *
0x140046ba4  lea     r8, aHsP; "%hs!%p: "
0x140046bab  mov     rcx, r14; this
0x140046bae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046bb3  mov     r14, rax
0x140046bb6  mov     r9, [rbx+90h]; unsigned __int16 *
0x140046bbd  test    r9, r9
0x140046bc0  jz      short loc_140046BD7
0x140046bc2  lea     r8, aCallerP; "(caller: %p) "
0x140046bc9  mov     rdx, rsi; unsigned __int16 *
0x140046bcc  mov     rcx, rax; this
0x140046bcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046bd4  mov     r14, rax
0x140046bd7  call    cs:__imp_GetCurrentThreadId
0x140046bdd  lea     rcx, [rsp+278h+Buffer]
0x140046be2  mov     [rsp+278h+var_240], rcx
0x140046be7  mov     dword ptr [rsp+278h+Arguments], ebp
0x140046beb  mov     [rsp+278h+nSize], eax
0x140046bef  mov     eax, [rbx+44h]
0x140046bf2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140046bf6  mov     r9, rdi; unsigned __int16 *
0x140046bf9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140046c00  mov     rdx, rsi; unsigned __int16 *
0x140046c03  mov     rcx, r14; this
0x140046c06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046c0b  cmp     [rbx+18h], r15
0x140046c0f  jnz     short loc_140046C21
0x140046c11  cmp     [rbx+48h], r15
0x140046c15  jnz     short loc_140046C21
0x140046c17  cmp     [rbx+30h], r15
0x140046c1b  jz      loc_140046CB1
0x140046c21  lea     r8, asc_140136C68; "    "
0x140046c28  mov     rdx, rsi; unsigned __int16 *
0x140046c2b  mov     rcx, rax; this
0x140046c2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046c33  mov     r9, [rbx+18h]; unsigned __int16 *
0x140046c37  test    r9, r9
0x140046c3a  jz      short loc_140046C4E
0x140046c3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140046c43  mov     rdx, rsi; unsigned __int16 *
0x140046c46  mov     rcx, rax; this
0x140046c49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046c4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140046c52  test    r9, r9
0x140046c55  jz      short loc_140046C69
0x140046c57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140046c5e  mov     rdx, rsi; unsigned __int16 *
0x140046c61  mov     rcx, rax; this
0x140046c64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046c69  mov     rcx, [rbx+28h]
0x140046c6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140046c71  mov     rdx, rsi; unsigned __int16 *
0x140046c74  test    rcx, rcx
0x140046c77  jz      short loc_140046C8F
0x140046c79  mov     [rsp+278h+lpBuffer], rcx
0x140046c7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140046c85  mov     rcx, rax; this
0x140046c88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046c8d  jmp     short loc_140046CB1
0x140046c8f  mov     rcx, rax; this
0x140046c92  test    r9, r9
0x140046c95  jz      short loc_140046CA5
0x140046c97  lea     r8, aHs; "[%hs]\n"
0x140046c9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046ca3  jmp     short loc_140046CB1
0x140046ca5  lea     r8, asc_14012B970; "\n"
0x140046cac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140046cb1  xor     eax, eax
0x140046cb3  mov     rcx, [rsp+278h+var_38]
0x140046cbb  xor     rcx, rsp; StackCookie
0x140046cbe  call    __security_check_cookie
0x140046cc3  mov     rbx, [rsp+278h+arg_18]
0x140046ccb  add     rsp, 250h
0x140046cd2  pop     r15
0x140046cd4  pop     r14
0x140046cd6  pop     rdi
0x140046cd7  pop     rsi
0x140046cd8  pop     rbp
0x140046cd9  retn
```
