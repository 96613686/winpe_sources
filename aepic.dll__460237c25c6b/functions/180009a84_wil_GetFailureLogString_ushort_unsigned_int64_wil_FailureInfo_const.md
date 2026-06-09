# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009a84`
- end: `0x180009d3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `10`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a5fc`
- `0x18000ac74`
- `0x18000ddc0`
- `0x1800e5d49`
- `0x1800e60ae`
- `0x1800e70ee`
- `0x1800e74bc`
- `0x1800e7a7f`
- `0x1800e81de`
- `0x1800e83ce`

## callees

- `0x180005890`
- `0x180006938`
- `0x180009a84`
- `0x18000a8f8`
- `0x1800eb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009c37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009bb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009bb6`

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
          v7 = (const char *)&qword_1800F3280;
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
0x180009a84  mov     [rsp+arg_18], rbx
0x180009a89  push    rbp
0x180009a8a  push    rsi
0x180009a8b  push    rdi
0x180009a8c  push    r14
0x180009a8e  push    r15
0x180009a90  sub     rsp, 250h
0x180009a97  mov     rax, cs:__security_cookie
0x180009a9e  xor     rax, rsp
0x180009aa1  mov     [rsp+278h+var_38], rax
0x180009aa9  mov     rbx, r8
0x180009aac  mov     rsi, rdx
0x180009aaf  mov     r14, rcx
0x180009ab2  xor     r15d, r15d
0x180009ab5  test    rdx, rdx
0x180009ab8  jz      loc_180009D11
0x180009abe  test    rcx, rcx
0x180009ac1  jz      loc_180009D11
0x180009ac7  mov     [rcx], r15w
0x180009acb  mov     rax, cs:g_pfnResultLoggingCallback
0x180009ad2  test    rax, rax
0x180009ad5  jz      short loc_180009AF8
0x180009ad7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009ade  jz      short loc_180009AF8
0x180009ae0  mov     r8, rdx
0x180009ae3  mov     rdx, rcx
0x180009ae6  mov     rcx, rbx
0x180009ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aee  cmp     [r14], r15w
0x180009af2  jnz     loc_180009D11
0x180009af8  mov     ecx, [rbx]
0x180009afa  mov     bpl, 8
0x180009afd  test    ecx, ecx
0x180009aff  jz      short loc_180009B4A
0x180009b01  sub     ecx, 1
0x180009b04  jz      short loc_180009B32
0x180009b06  sub     ecx, 1
0x180009b09  jz      short loc_180009B22
0x180009b0b  cmp     ecx, 1
0x180009b0e  jz      short loc_180009B19
0x180009b10  lea     rdi, qword_1800F3280
0x180009b17  jmp     short loc_180009B51
0x180009b19  lea     rdi, aFailfast; "FailFast"
0x180009b20  jmp     short loc_180009B51
0x180009b22  lea     rax, aLoghr; "LogHr"
0x180009b29  lea     rdi, aLognt; "LogNt"
0x180009b30  jmp     short loc_180009B40
0x180009b32  lea     rax, aReturnhr; "ReturnHr"
0x180009b39  lea     rdi, aReturnnt; "ReturnNt"
0x180009b40  test    [rbx+4], bpl
0x180009b44  cmovz   rdi, rax
0x180009b48  jmp     short loc_180009B51
0x180009b4a  lea     rdi, aException; "Exception"
0x180009b51  xor     edx, edx; Val
0x180009b53  mov     r8d, 200h; Size
0x180009b59  lea     rcx, [rsp+278h+Buffer]; void *
0x180009b5e  call    memset_0
0x180009b63  test    [rbx+4], bpl
0x180009b67  jz      short loc_180009B8C
0x180009b69  mov     ebp, [rbx+0Ch]
0x180009b6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009b73  test    rax, rax
0x180009b76  jz      short loc_180009BBC
0x180009b78  mov     r8d, 100h
0x180009b7e  lea     rdx, [rsp+278h+Buffer]
0x180009b83  mov     ecx, ebp
0x180009b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009b8a  jmp     short loc_180009BBC
0x180009b8c  mov     ebp, [rbx+8]
0x180009b8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009b94  mov     [rsp+278h+nSize], 100h; nSize
0x180009b9c  lea     rax, [rsp+278h+Buffer]
0x180009ba1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009ba6  mov     r9d, 400h; dwLanguageId
0x180009bac  mov     r8d, ebp; dwMessageId
0x180009baf  xor     edx, edx; lpSource
0x180009bb1  mov     ecx, 1200h; dwFlags
0x180009bb6  call    cs:__imp_FormatMessageW
0x180009bbc  lea     rsi, [r14+rsi*2]
0x180009bc0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009bc4  mov     rax, [rbx+88h]
0x180009bcb  mov     rcx, [rbx+80h]
0x180009bd2  mov     rdx, rsi; unsigned __int16 *
0x180009bd5  test    r9, r9
0x180009bd8  jz      short loc_180009BFC
0x180009bda  mov     [rsp+278h+Arguments], rax
0x180009bdf  mov     qword ptr [rsp+278h+nSize], rcx
0x180009be4  mov     eax, [rbx+40h]
0x180009be7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009beb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009bf2  mov     rcx, r14; this
0x180009bf5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009bfa  jmp     short loc_180009C13
0x180009bfc  mov     [rsp+278h+lpBuffer], rax
0x180009c01  mov     r9, rcx; unsigned __int16 *
0x180009c04  lea     r8, aHsP; "%hs!%p: "
0x180009c0b  mov     rcx, r14; this
0x180009c0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c13  mov     r14, rax
0x180009c16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009c1d  test    r9, r9
0x180009c20  jz      short loc_180009C37
0x180009c22  lea     r8, aCallerP; "(caller: %p) "
0x180009c29  mov     rdx, rsi; unsigned __int16 *
0x180009c2c  mov     rcx, rax; this
0x180009c2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c34  mov     r14, rax
0x180009c37  call    cs:__imp_GetCurrentThreadId
0x180009c3d  lea     rcx, [rsp+278h+Buffer]
0x180009c42  mov     [rsp+278h+var_240], rcx
0x180009c47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009c4b  mov     [rsp+278h+nSize], eax
0x180009c4f  mov     eax, [rbx+44h]
0x180009c52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009c56  mov     r9, rdi; unsigned __int16 *
0x180009c59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009c60  mov     rdx, rsi; unsigned __int16 *
0x180009c63  mov     rcx, r14; this
0x180009c66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c6b  cmp     [rbx+18h], r15
0x180009c6f  jnz     short loc_180009C81
0x180009c71  cmp     [rbx+48h], r15
0x180009c75  jnz     short loc_180009C81
0x180009c77  cmp     [rbx+30h], r15
0x180009c7b  jz      loc_180009D11
0x180009c81  lea     r8, asc_1800F33A0; "    "
0x180009c88  mov     rdx, rsi; unsigned __int16 *
0x180009c8b  mov     rcx, rax; this
0x180009c8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009c93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009c97  test    r9, r9
0x180009c9a  jz      short loc_180009CAE
0x180009c9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009ca3  mov     rdx, rsi; unsigned __int16 *
0x180009ca6  mov     rcx, rax; this
0x180009ca9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009cb2  test    r9, r9
0x180009cb5  jz      short loc_180009CC9
0x180009cb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009cbe  mov     rdx, rsi; unsigned __int16 *
0x180009cc1  mov     rcx, rax; this
0x180009cc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009cc9  mov     rcx, [rbx+28h]
0x180009ccd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009cd1  mov     rdx, rsi; unsigned __int16 *
0x180009cd4  test    rcx, rcx
0x180009cd7  jz      short loc_180009CEF
0x180009cd9  mov     [rsp+278h+lpBuffer], rcx
0x180009cde  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180009ce5  mov     rcx, rax; this
0x180009ce8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009ced  jmp     short loc_180009D11
0x180009cef  mov     rcx, rax; this
0x180009cf2  test    r9, r9
0x180009cf5  jz      short loc_180009D05
0x180009cf7  lea     r8, aHs_0; "[%hs]\n"
0x180009cfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d03  jmp     short loc_180009D11
0x180009d05  lea     r8, asc_1800F3418; "\n"
0x180009d0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009d11  xor     eax, eax
0x180009d13  mov     rcx, [rsp+278h+var_38]
0x180009d1b  xor     rcx, rsp; StackCookie
0x180009d1e  call    __security_check_cookie
0x180009d23  mov     rbx, [rsp+278h+arg_18]
0x180009d2b  add     rsp, 250h
0x180009d32  pop     r15
0x180009d34  pop     r14
0x180009d36  pop     rdi
0x180009d37  pop     rsi
0x180009d38  pop     rbp
0x180009d39  retn
```
