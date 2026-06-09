# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005c44`
- end: `0x140005efa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000303c`
- `0x1400032a4`
- `0x140006e5c`

## callees

- `0x140005c44`
- `0x14000715c`
- `0x140015ac2`
- `0x140015b00`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005df7`
- `KERNEL32!GetCurrentThreadId` at `0x140005df7`
- `KERNEL32!FormatMessageW` at `0x140005d76`
- `KERNEL32!FormatMessageW` at `0x140005d76`

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
          v8 = (const char *)&word_140018C4A;
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
0x140005c44  mov     [rsp+arg_18], rbx
0x140005c49  push    rbp
0x140005c4a  push    rsi
0x140005c4b  push    rdi
0x140005c4c  push    r14
0x140005c4e  push    r15
0x140005c50  sub     rsp, 250h
0x140005c57  mov     rax, cs:__security_cookie
0x140005c5e  xor     rax, rsp
0x140005c61  mov     [rsp+278h+var_38], rax
0x140005c69  xor     r15d, r15d
0x140005c6c  mov     rbx, r8
0x140005c6f  mov     rsi, rdx
0x140005c72  mov     r14, rcx
0x140005c75  test    rdx, rdx
0x140005c78  jz      loc_140005ED1
0x140005c7e  test    rcx, rcx
0x140005c81  jz      loc_140005ED1
0x140005c87  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c8e  mov     [rcx], r15w
0x140005c92  test    rax, rax
0x140005c95  jz      short loc_140005CB8
0x140005c97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005c9e  jz      short loc_140005CB8
0x140005ca0  mov     r8, rdx
0x140005ca3  mov     rdx, rcx
0x140005ca6  mov     rcx, rbx
0x140005ca9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cae  cmp     [r14], r15w
0x140005cb2  jnz     loc_140005ED1
0x140005cb8  mov     ecx, [rbx]
0x140005cba  mov     bpl, 8
0x140005cbd  test    ecx, ecx
0x140005cbf  jz      short loc_140005D0A
0x140005cc1  sub     ecx, 1
0x140005cc4  jz      short loc_140005CF2
0x140005cc6  sub     ecx, 1
0x140005cc9  jz      short loc_140005CE2
0x140005ccb  cmp     ecx, 1
0x140005cce  jz      short loc_140005CD9
0x140005cd0  lea     rdi, word_140018C4A
0x140005cd7  jmp     short loc_140005D11
0x140005cd9  lea     rdi, aFailfast; "FailFast"
0x140005ce0  jmp     short loc_140005D11
0x140005ce2  lea     rax, aLoghr; "LogHr"
0x140005ce9  lea     rdi, aLognt; "LogNt"
0x140005cf0  jmp     short loc_140005D00
0x140005cf2  lea     rax, aReturnhr; "ReturnHr"
0x140005cf9  lea     rdi, aReturnnt; "ReturnNt"
0x140005d00  test    [rbx+4], bpl
0x140005d04  cmovz   rdi, rax
0x140005d08  jmp     short loc_140005D11
0x140005d0a  lea     rdi, aException; "Exception"
0x140005d11  xor     edx, edx; Val
0x140005d13  lea     rcx, [rsp+278h+Buffer]; void *
0x140005d18  mov     r8d, 200h; Size
0x140005d1e  call    memset_0
0x140005d23  test    [rbx+4], bpl
0x140005d27  jz      short loc_140005D4C
0x140005d29  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005d30  mov     ebp, [rbx+0Ch]
0x140005d33  test    rax, rax
0x140005d36  jz      short loc_140005D7C
0x140005d38  mov     r8d, 100h
0x140005d3e  lea     rdx, [rsp+278h+Buffer]
0x140005d43  mov     ecx, ebp
0x140005d45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d4a  jmp     short loc_140005D7C
0x140005d4c  mov     ebp, [rbx+8]
0x140005d4f  lea     rax, [rsp+278h+Buffer]
0x140005d54  mov     [rsp+278h+Arguments], r15; Arguments
0x140005d59  mov     r8d, ebp; dwMessageId
0x140005d5c  mov     [rsp+278h+nSize], 100h; nSize
0x140005d64  mov     r9d, 400h; dwLanguageId
0x140005d6a  xor     edx, edx; lpSource
0x140005d6c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005d71  mov     ecx, 1200h; dwFlags
0x140005d76  call    cs:__imp_FormatMessageW
0x140005d7c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005d80  lea     rsi, [r14+rsi*2]
0x140005d84  mov     rax, [rbx+88h]
0x140005d8b  mov     rdx, rsi; unsigned __int16 *
0x140005d8e  mov     rcx, [rbx+80h]
0x140005d95  test    r9, r9
0x140005d98  jz      short loc_140005DBC
0x140005d9a  mov     [rsp+278h+Arguments], rax
0x140005d9f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005da6  mov     eax, [rbx+40h]
0x140005da9  mov     qword ptr [rsp+278h+nSize], rcx
0x140005dae  mov     rcx, r14; this
0x140005db1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005db5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005dba  jmp     short loc_140005DD3
0x140005dbc  mov     r9, rcx; unsigned __int16 *
0x140005dbf  mov     [rsp+278h+lpBuffer], rax
0x140005dc4  mov     rcx, r14; this
0x140005dc7  lea     r8, aHsP; "%hs!%p: "
0x140005dce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005dd3  mov     r9, [rbx+90h]; unsigned __int16 *
0x140005dda  mov     r14, rax
0x140005ddd  test    r9, r9
0x140005de0  jz      short loc_140005DF7
0x140005de2  lea     r8, aCallerP; "(caller: %p) "
0x140005de9  mov     rdx, rsi; unsigned __int16 *
0x140005dec  mov     rcx, rax; this
0x140005def  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005df4  mov     r14, rax
0x140005df7  call    cs:__imp_GetCurrentThreadId
0x140005dfd  lea     rcx, [rsp+278h+Buffer]
0x140005e02  mov     r9, rdi; unsigned __int16 *
0x140005e05  mov     [rsp+278h+var_240], rcx
0x140005e0a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005e11  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005e15  mov     rdx, rsi; unsigned __int16 *
0x140005e18  mov     [rsp+278h+nSize], eax
0x140005e1c  mov     rcx, r14; this
0x140005e1f  mov     eax, [rbx+44h]
0x140005e22  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005e26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005e2b  cmp     [rbx+18h], r15
0x140005e2f  jnz     short loc_140005E41
0x140005e31  cmp     [rbx+48h], r15
0x140005e35  jnz     short loc_140005E41
0x140005e37  cmp     [rbx+30h], r15
0x140005e3b  jz      loc_140005ED1
0x140005e41  lea     r8, asc_140018D38; "    "
0x140005e48  mov     rdx, rsi; unsigned __int16 *
0x140005e4b  mov     rcx, rax; this
0x140005e4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005e53  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005e57  test    r9, r9
0x140005e5a  jz      short loc_140005E6E
0x140005e5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005e63  mov     rdx, rsi; unsigned __int16 *
0x140005e66  mov     rcx, rax; this
0x140005e69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005e6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005e72  test    r9, r9
0x140005e75  jz      short loc_140005E89
0x140005e77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140005e7e  mov     rdx, rsi; unsigned __int16 *
0x140005e81  mov     rcx, rax; this
0x140005e84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005e89  mov     rcx, [rbx+28h]
0x140005e8d  mov     rdx, rsi; unsigned __int16 *
0x140005e90  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005e94  test    rcx, rcx
0x140005e97  jz      short loc_140005EAF
0x140005e99  mov     [rsp+278h+lpBuffer], rcx
0x140005e9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005ea5  mov     rcx, rax; this
0x140005ea8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ead  jmp     short loc_140005ED1
0x140005eaf  mov     rcx, rax; this
0x140005eb2  test    r9, r9
0x140005eb5  jz      short loc_140005EC5
0x140005eb7  lea     r8, aHs; "[%hs]\n"
0x140005ebe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ec3  jmp     short loc_140005ED1
0x140005ec5  lea     r8, asc_140018DB0; "\n"
0x140005ecc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ed1  xor     eax, eax
0x140005ed3  mov     rcx, [rsp+278h+var_38]
0x140005edb  xor     rcx, rsp; StackCookie
0x140005ede  call    __security_check_cookie
0x140005ee3  mov     rbx, [rsp+278h+arg_18]
0x140005eeb  add     rsp, 250h
0x140005ef2  pop     r15
0x140005ef4  pop     r14
0x140005ef6  pop     rdi
0x140005ef7  pop     rsi
0x140005ef8  pop     rbp
0x140005ef9  retn
```
