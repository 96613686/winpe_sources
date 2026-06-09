# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004c44`
- end: `0x180004efa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800035cc`
- `0x18000383c`
- `0x18000568c`
- `0x180007240`
- `0x1800074fc`

## callees

- `0x180002550`
- `0x180002fc4`
- `0x180004c44`
- `0x18000598c`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004df7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004df7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004d76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004d76`

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
          v7 = (const char *)&word_1800159FE;
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
0x180004c44  mov     [rsp+arg_18], rbx
0x180004c49  push    rbp
0x180004c4a  push    rsi
0x180004c4b  push    rdi
0x180004c4c  push    r14
0x180004c4e  push    r15
0x180004c50  sub     rsp, 250h
0x180004c57  mov     rax, cs:__security_cookie
0x180004c5e  xor     rax, rsp
0x180004c61  mov     [rsp+278h+var_38], rax
0x180004c69  mov     rbx, r8
0x180004c6c  mov     rsi, rdx
0x180004c6f  mov     r14, rcx
0x180004c72  xor     r15d, r15d
0x180004c75  test    rdx, rdx
0x180004c78  jz      loc_180004ED1
0x180004c7e  test    rcx, rcx
0x180004c81  jz      loc_180004ED1
0x180004c87  mov     [rcx], r15w
0x180004c8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c92  test    rax, rax
0x180004c95  jz      short loc_180004CB8
0x180004c97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004c9e  jz      short loc_180004CB8
0x180004ca0  mov     r8, rdx
0x180004ca3  mov     rdx, rcx
0x180004ca6  mov     rcx, rbx
0x180004ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cae  cmp     [r14], r15w
0x180004cb2  jnz     loc_180004ED1
0x180004cb8  mov     ecx, [rbx]
0x180004cba  mov     bpl, 8
0x180004cbd  test    ecx, ecx
0x180004cbf  jz      short loc_180004D0A
0x180004cc1  sub     ecx, 1
0x180004cc4  jz      short loc_180004CF2
0x180004cc6  sub     ecx, 1
0x180004cc9  jz      short loc_180004CE2
0x180004ccb  cmp     ecx, 1
0x180004cce  jz      short loc_180004CD9
0x180004cd0  lea     rdi, word_1800159FE
0x180004cd7  jmp     short loc_180004D11
0x180004cd9  lea     rdi, aFailfast; "FailFast"
0x180004ce0  jmp     short loc_180004D11
0x180004ce2  lea     rax, aLoghr; "LogHr"
0x180004ce9  lea     rdi, aLognt; "LogNt"
0x180004cf0  jmp     short loc_180004D00
0x180004cf2  lea     rax, aReturnhr; "ReturnHr"
0x180004cf9  lea     rdi, aReturnnt; "ReturnNt"
0x180004d00  test    [rbx+4], bpl
0x180004d04  cmovz   rdi, rax
0x180004d08  jmp     short loc_180004D11
0x180004d0a  lea     rdi, aException; "Exception"
0x180004d11  xor     edx, edx; Val
0x180004d13  mov     r8d, 200h; Size
0x180004d19  lea     rcx, [rsp+278h+Buffer]; void *
0x180004d1e  call    memset_0
0x180004d23  test    [rbx+4], bpl
0x180004d27  jz      short loc_180004D4C
0x180004d29  mov     ebp, [rbx+0Ch]
0x180004d2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004d33  test    rax, rax
0x180004d36  jz      short loc_180004D7C
0x180004d38  mov     r8d, 100h
0x180004d3e  lea     rdx, [rsp+278h+Buffer]
0x180004d43  mov     ecx, ebp
0x180004d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d4a  jmp     short loc_180004D7C
0x180004d4c  mov     ebp, [rbx+8]
0x180004d4f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004d54  mov     [rsp+278h+nSize], 100h; nSize
0x180004d5c  lea     rax, [rsp+278h+Buffer]
0x180004d61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004d66  mov     r9d, 400h; dwLanguageId
0x180004d6c  mov     r8d, ebp; dwMessageId
0x180004d6f  xor     edx, edx; lpSource
0x180004d71  mov     ecx, 1200h; dwFlags
0x180004d76  call    cs:__imp_FormatMessageW
0x180004d7c  lea     rsi, [r14+rsi*2]
0x180004d80  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004d84  mov     rax, [rbx+88h]
0x180004d8b  mov     rcx, [rbx+80h]
0x180004d92  mov     rdx, rsi; unsigned __int16 *
0x180004d95  test    r9, r9
0x180004d98  jz      short loc_180004DBC
0x180004d9a  mov     [rsp+278h+Arguments], rax
0x180004d9f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004da4  mov     eax, [rbx+40h]
0x180004da7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004dab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004db2  mov     rcx, r14; this
0x180004db5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dba  jmp     short loc_180004DD3
0x180004dbc  mov     [rsp+278h+lpBuffer], rax
0x180004dc1  mov     r9, rcx; unsigned __int16 *
0x180004dc4  lea     r8, aHsP; "%hs!%p: "
0x180004dcb  mov     rcx, r14; this
0x180004dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004dd3  mov     r14, rax
0x180004dd6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004ddd  test    r9, r9
0x180004de0  jz      short loc_180004DF7
0x180004de2  lea     r8, aCallerP; "(caller: %p) "
0x180004de9  mov     rdx, rsi; unsigned __int16 *
0x180004dec  mov     rcx, rax; this
0x180004def  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004df4  mov     r14, rax
0x180004df7  call    cs:__imp_GetCurrentThreadId
0x180004dfd  lea     rcx, [rsp+278h+Buffer]
0x180004e02  mov     [rsp+278h+var_240], rcx
0x180004e07  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004e0b  mov     [rsp+278h+nSize], eax
0x180004e0f  mov     eax, [rbx+44h]
0x180004e12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004e16  mov     r9, rdi; unsigned __int16 *
0x180004e19  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004e20  mov     rdx, rsi; unsigned __int16 *
0x180004e23  mov     rcx, r14; this
0x180004e26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e2b  cmp     [rbx+18h], r15
0x180004e2f  jnz     short loc_180004E41
0x180004e31  cmp     [rbx+48h], r15
0x180004e35  jnz     short loc_180004E41
0x180004e37  cmp     [rbx+30h], r15
0x180004e3b  jz      loc_180004ED1
0x180004e41  lea     r8, asc_180015B00; "    "
0x180004e48  mov     rdx, rsi; unsigned __int16 *
0x180004e4b  mov     rcx, rax; this
0x180004e4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e53  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004e57  test    r9, r9
0x180004e5a  jz      short loc_180004E6E
0x180004e5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004e63  mov     rdx, rsi; unsigned __int16 *
0x180004e66  mov     rcx, rax; this
0x180004e69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004e72  test    r9, r9
0x180004e75  jz      short loc_180004E89
0x180004e77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004e7e  mov     rdx, rsi; unsigned __int16 *
0x180004e81  mov     rcx, rax; this
0x180004e84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e89  mov     rcx, [rbx+28h]
0x180004e8d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004e91  mov     rdx, rsi; unsigned __int16 *
0x180004e94  test    rcx, rcx
0x180004e97  jz      short loc_180004EAF
0x180004e99  mov     [rsp+278h+lpBuffer], rcx
0x180004e9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004ea5  mov     rcx, rax; this
0x180004ea8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ead  jmp     short loc_180004ED1
0x180004eaf  mov     rcx, rax; this
0x180004eb2  test    r9, r9
0x180004eb5  jz      short loc_180004EC5
0x180004eb7  lea     r8, aHs; "[%hs]\n"
0x180004ebe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ec3  jmp     short loc_180004ED1
0x180004ec5  lea     r8, asc_180015B78; "\n"
0x180004ecc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ed1  xor     eax, eax
0x180004ed3  mov     rcx, [rsp+278h+var_38]
0x180004edb  xor     rcx, rsp; StackCookie
0x180004ede  call    __security_check_cookie
0x180004ee3  mov     rbx, [rsp+278h+arg_18]
0x180004eeb  add     rsp, 250h
0x180004ef2  pop     r15
0x180004ef4  pop     r14
0x180004ef6  pop     rdi
0x180004ef7  pop     rsi
0x180004ef8  pop     rbp
0x180004ef9  retn
```
