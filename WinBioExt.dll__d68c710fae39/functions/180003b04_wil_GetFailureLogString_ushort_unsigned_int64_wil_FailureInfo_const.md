# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003b04`
- end: `0x180003dba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x1800026a8`
- `0x180002928`
- `0x180004464`
- `0x180005c50`
- `0x18000a190`
- `0x18000a2c4`

## callees

- `0x180001610`
- `0x180002084`
- `0x180003b04`
- `0x180004764`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003cb7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003c36`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003c36`

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
          v7 = (const char *)&word_18000C9DA;
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
0x180003b04  mov     [rsp+arg_18], rbx
0x180003b09  push    rbp
0x180003b0a  push    rsi
0x180003b0b  push    rdi
0x180003b0c  push    r14
0x180003b0e  push    r15
0x180003b10  sub     rsp, 250h
0x180003b17  mov     rax, cs:__security_cookie
0x180003b1e  xor     rax, rsp
0x180003b21  mov     [rsp+278h+var_38], rax
0x180003b29  mov     rbx, r8
0x180003b2c  mov     rsi, rdx
0x180003b2f  mov     r14, rcx
0x180003b32  xor     r15d, r15d
0x180003b35  test    rdx, rdx
0x180003b38  jz      loc_180003D91
0x180003b3e  test    rcx, rcx
0x180003b41  jz      loc_180003D91
0x180003b47  mov     [rcx], r15w
0x180003b4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003b52  test    rax, rax
0x180003b55  jz      short loc_180003B78
0x180003b57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003b5e  jz      short loc_180003B78
0x180003b60  mov     r8, rdx
0x180003b63  mov     rdx, rcx
0x180003b66  mov     rcx, rbx
0x180003b69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003b6e  cmp     [r14], r15w
0x180003b72  jnz     loc_180003D91
0x180003b78  mov     ecx, [rbx]
0x180003b7a  mov     bpl, 8
0x180003b7d  test    ecx, ecx
0x180003b7f  jz      short loc_180003BCA
0x180003b81  sub     ecx, 1
0x180003b84  jz      short loc_180003BB2
0x180003b86  sub     ecx, 1
0x180003b89  jz      short loc_180003BA2
0x180003b8b  cmp     ecx, 1
0x180003b8e  jz      short loc_180003B99
0x180003b90  lea     rdi, word_18000C9DA
0x180003b97  jmp     short loc_180003BD1
0x180003b99  lea     rdi, aFailfast; "FailFast"
0x180003ba0  jmp     short loc_180003BD1
0x180003ba2  lea     rax, aLoghr; "LogHr"
0x180003ba9  lea     rdi, aLognt; "LogNt"
0x180003bb0  jmp     short loc_180003BC0
0x180003bb2  lea     rax, aReturnhr; "ReturnHr"
0x180003bb9  lea     rdi, aReturnnt; "ReturnNt"
0x180003bc0  test    [rbx+4], bpl
0x180003bc4  cmovz   rdi, rax
0x180003bc8  jmp     short loc_180003BD1
0x180003bca  lea     rdi, aException; "Exception"
0x180003bd1  xor     edx, edx; Val
0x180003bd3  mov     r8d, 200h; Size
0x180003bd9  lea     rcx, [rsp+278h+Buffer]; void *
0x180003bde  call    memset_0
0x180003be3  test    [rbx+4], bpl
0x180003be7  jz      short loc_180003C0C
0x180003be9  mov     ebp, [rbx+0Ch]
0x180003bec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003bf3  test    rax, rax
0x180003bf6  jz      short loc_180003C3C
0x180003bf8  mov     r8d, 100h
0x180003bfe  lea     rdx, [rsp+278h+Buffer]
0x180003c03  mov     ecx, ebp
0x180003c05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003c0a  jmp     short loc_180003C3C
0x180003c0c  mov     ebp, [rbx+8]
0x180003c0f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003c14  mov     [rsp+278h+nSize], 100h; nSize
0x180003c1c  lea     rax, [rsp+278h+Buffer]
0x180003c21  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003c26  mov     r9d, 400h; dwLanguageId
0x180003c2c  mov     r8d, ebp; dwMessageId
0x180003c2f  xor     edx, edx; lpSource
0x180003c31  mov     ecx, 1200h; dwFlags
0x180003c36  call    cs:__imp_FormatMessageW
0x180003c3c  lea     rsi, [r14+rsi*2]
0x180003c40  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003c44  mov     rax, [rbx+88h]
0x180003c4b  mov     rcx, [rbx+80h]
0x180003c52  mov     rdx, rsi; unsigned __int16 *
0x180003c55  test    r9, r9
0x180003c58  jz      short loc_180003C7C
0x180003c5a  mov     [rsp+278h+Arguments], rax
0x180003c5f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003c64  mov     eax, [rbx+40h]
0x180003c67  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003c6b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003c72  mov     rcx, r14; this
0x180003c75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c7a  jmp     short loc_180003C93
0x180003c7c  mov     [rsp+278h+lpBuffer], rax
0x180003c81  mov     r9, rcx; unsigned __int16 *
0x180003c84  lea     r8, aHsP; "%hs!%p: "
0x180003c8b  mov     rcx, r14; this
0x180003c8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003c93  mov     r14, rax
0x180003c96  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003c9d  test    r9, r9
0x180003ca0  jz      short loc_180003CB7
0x180003ca2  lea     r8, aCallerP; "(caller: %p) "
0x180003ca9  mov     rdx, rsi; unsigned __int16 *
0x180003cac  mov     rcx, rax; this
0x180003caf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003cb4  mov     r14, rax
0x180003cb7  call    cs:__imp_GetCurrentThreadId
0x180003cbd  lea     rcx, [rsp+278h+Buffer]
0x180003cc2  mov     [rsp+278h+var_240], rcx
0x180003cc7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003ccb  mov     [rsp+278h+nSize], eax
0x180003ccf  mov     eax, [rbx+44h]
0x180003cd2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003cd6  mov     r9, rdi; unsigned __int16 *
0x180003cd9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003ce0  mov     rdx, rsi; unsigned __int16 *
0x180003ce3  mov     rcx, r14; this
0x180003ce6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ceb  cmp     [rbx+18h], r15
0x180003cef  jnz     short loc_180003D01
0x180003cf1  cmp     [rbx+48h], r15
0x180003cf5  jnz     short loc_180003D01
0x180003cf7  cmp     [rbx+30h], r15
0x180003cfb  jz      loc_180003D91
0x180003d01  lea     r8, asc_18000CAC8; "    "
0x180003d08  mov     rdx, rsi; unsigned __int16 *
0x180003d0b  mov     rcx, rax; this
0x180003d0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d13  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003d17  test    r9, r9
0x180003d1a  jz      short loc_180003D2E
0x180003d1c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003d23  mov     rdx, rsi; unsigned __int16 *
0x180003d26  mov     rcx, rax; this
0x180003d29  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d2e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003d32  test    r9, r9
0x180003d35  jz      short loc_180003D49
0x180003d37  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003d3e  mov     rdx, rsi; unsigned __int16 *
0x180003d41  mov     rcx, rax; this
0x180003d44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d49  mov     rcx, [rbx+28h]
0x180003d4d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003d51  mov     rdx, rsi; unsigned __int16 *
0x180003d54  test    rcx, rcx
0x180003d57  jz      short loc_180003D6F
0x180003d59  mov     [rsp+278h+lpBuffer], rcx
0x180003d5e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003d65  mov     rcx, rax; this
0x180003d68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d6d  jmp     short loc_180003D91
0x180003d6f  mov     rcx, rax; this
0x180003d72  test    r9, r9
0x180003d75  jz      short loc_180003D85
0x180003d77  lea     r8, aHs; "[%hs]\n"
0x180003d7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d83  jmp     short loc_180003D91
0x180003d85  lea     r8, asc_18000CB40; "\n"
0x180003d8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003d91  xor     eax, eax
0x180003d93  mov     rcx, [rsp+278h+var_38]
0x180003d9b  xor     rcx, rsp; StackCookie
0x180003d9e  call    __security_check_cookie
0x180003da3  mov     rbx, [rsp+278h+arg_18]
0x180003dab  add     rsp, 250h
0x180003db2  pop     r15
0x180003db4  pop     r14
0x180003db6  pop     rdi
0x180003db7  pop     rsi
0x180003db8  pop     rbp
0x180003db9  retn
```
