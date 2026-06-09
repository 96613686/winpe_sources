# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008c14`
- end: `0x180008eca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000638c`
- `0x1800065fc`
- `0x180009700`
- `0x18000c880`
- `0x18000cb9c`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x180008c14`
- `0x180009a0c`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008dc7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008d46`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008d46`

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
          v7 = (const char *)&Src;
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
0x180008c14  mov     [rsp+arg_18], rbx
0x180008c19  push    rbp
0x180008c1a  push    rsi
0x180008c1b  push    rdi
0x180008c1c  push    r14
0x180008c1e  push    r15
0x180008c20  sub     rsp, 250h
0x180008c27  mov     rax, cs:__security_cookie
0x180008c2e  xor     rax, rsp
0x180008c31  mov     [rsp+278h+var_38], rax
0x180008c39  mov     rbx, r8
0x180008c3c  mov     rsi, rdx
0x180008c3f  mov     r14, rcx
0x180008c42  xor     r15d, r15d
0x180008c45  test    rdx, rdx
0x180008c48  jz      loc_180008EA1
0x180008c4e  test    rcx, rcx
0x180008c51  jz      loc_180008EA1
0x180008c57  mov     [rcx], r15w
0x180008c5b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008c62  test    rax, rax
0x180008c65  jz      short loc_180008C88
0x180008c67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180008c6e  jz      short loc_180008C88
0x180008c70  mov     r8, rdx
0x180008c73  mov     rdx, rcx
0x180008c76  mov     rcx, rbx
0x180008c79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c7e  cmp     [r14], r15w
0x180008c82  jnz     loc_180008EA1
0x180008c88  mov     ecx, [rbx]
0x180008c8a  mov     bpl, 8
0x180008c8d  test    ecx, ecx
0x180008c8f  jz      short loc_180008CDA
0x180008c91  sub     ecx, 1
0x180008c94  jz      short loc_180008CC2
0x180008c96  sub     ecx, 1
0x180008c99  jz      short loc_180008CB2
0x180008c9b  cmp     ecx, 1
0x180008c9e  jz      short loc_180008CA9
0x180008ca0  lea     rdi, Src
0x180008ca7  jmp     short loc_180008CE1
0x180008ca9  lea     rdi, aFailfast; "FailFast"
0x180008cb0  jmp     short loc_180008CE1
0x180008cb2  lea     rax, aLoghr; "LogHr"
0x180008cb9  lea     rdi, aLognt; "LogNt"
0x180008cc0  jmp     short loc_180008CD0
0x180008cc2  lea     rax, aReturnhr; "ReturnHr"
0x180008cc9  lea     rdi, aReturnnt; "ReturnNt"
0x180008cd0  test    [rbx+4], bpl
0x180008cd4  cmovz   rdi, rax
0x180008cd8  jmp     short loc_180008CE1
0x180008cda  lea     rdi, aException; "Exception"
0x180008ce1  xor     edx, edx; Val
0x180008ce3  mov     r8d, 200h; Size
0x180008ce9  lea     rcx, [rsp+278h+Buffer]; void *
0x180008cee  call    memset_0
0x180008cf3  test    [rbx+4], bpl
0x180008cf7  jz      short loc_180008D1C
0x180008cf9  mov     ebp, [rbx+0Ch]
0x180008cfc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008d03  test    rax, rax
0x180008d06  jz      short loc_180008D4C
0x180008d08  mov     r8d, 100h
0x180008d0e  lea     rdx, [rsp+278h+Buffer]
0x180008d13  mov     ecx, ebp
0x180008d15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d1a  jmp     short loc_180008D4C
0x180008d1c  mov     ebp, [rbx+8]
0x180008d1f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008d24  mov     [rsp+278h+nSize], 100h; nSize
0x180008d2c  lea     rax, [rsp+278h+Buffer]
0x180008d31  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008d36  mov     r9d, 400h; dwLanguageId
0x180008d3c  mov     r8d, ebp; dwMessageId
0x180008d3f  xor     edx, edx; lpSource
0x180008d41  mov     ecx, 1200h; dwFlags
0x180008d46  call    cs:__imp_FormatMessageW
0x180008d4c  lea     rsi, [r14+rsi*2]
0x180008d50  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008d54  mov     rax, [rbx+88h]
0x180008d5b  mov     rcx, [rbx+80h]
0x180008d62  mov     rdx, rsi; unsigned __int16 *
0x180008d65  test    r9, r9
0x180008d68  jz      short loc_180008D8C
0x180008d6a  mov     [rsp+278h+Arguments], rax
0x180008d6f  mov     qword ptr [rsp+278h+nSize], rcx
0x180008d74  mov     eax, [rbx+40h]
0x180008d77  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008d7b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008d82  mov     rcx, r14; this
0x180008d85  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008d8a  jmp     short loc_180008DA3
0x180008d8c  mov     [rsp+278h+lpBuffer], rax
0x180008d91  mov     r9, rcx; unsigned __int16 *
0x180008d94  lea     r8, aHsP; "%hs!%p: "
0x180008d9b  mov     rcx, r14; this
0x180008d9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008da3  mov     r14, rax
0x180008da6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180008dad  test    r9, r9
0x180008db0  jz      short loc_180008DC7
0x180008db2  lea     r8, aCallerP; "(caller: %p) "
0x180008db9  mov     rdx, rsi; unsigned __int16 *
0x180008dbc  mov     rcx, rax; this
0x180008dbf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008dc4  mov     r14, rax
0x180008dc7  call    cs:__imp_GetCurrentThreadId
0x180008dcd  lea     rcx, [rsp+278h+Buffer]
0x180008dd2  mov     [rsp+278h+var_240], rcx
0x180008dd7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180008ddb  mov     [rsp+278h+nSize], eax
0x180008ddf  mov     eax, [rbx+44h]
0x180008de2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008de6  mov     r9, rdi; unsigned __int16 *
0x180008de9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008df0  mov     rdx, rsi; unsigned __int16 *
0x180008df3  mov     rcx, r14; this
0x180008df6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008dfb  cmp     [rbx+18h], r15
0x180008dff  jnz     short loc_180008E11
0x180008e01  cmp     [rbx+48h], r15
0x180008e05  jnz     short loc_180008E11
0x180008e07  cmp     [rbx+30h], r15
0x180008e0b  jz      loc_180008EA1
0x180008e11  lea     r8, asc_18007E4C8; "    "
0x180008e18  mov     rdx, rsi; unsigned __int16 *
0x180008e1b  mov     rcx, rax; this
0x180008e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e23  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008e27  test    r9, r9
0x180008e2a  jz      short loc_180008E3E
0x180008e2c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008e33  mov     rdx, rsi; unsigned __int16 *
0x180008e36  mov     rcx, rax; this
0x180008e39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e3e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008e42  test    r9, r9
0x180008e45  jz      short loc_180008E59
0x180008e47  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180008e4e  mov     rdx, rsi; unsigned __int16 *
0x180008e51  mov     rcx, rax; this
0x180008e54  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e59  mov     rcx, [rbx+28h]
0x180008e5d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008e61  mov     rdx, rsi; unsigned __int16 *
0x180008e64  test    rcx, rcx
0x180008e67  jz      short loc_180008E7F
0x180008e69  mov     [rsp+278h+lpBuffer], rcx
0x180008e6e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008e75  mov     rcx, rax; this
0x180008e78  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e7d  jmp     short loc_180008EA1
0x180008e7f  mov     rcx, rax; this
0x180008e82  test    r9, r9
0x180008e85  jz      short loc_180008E95
0x180008e87  lea     r8, aHs; "[%hs]\n"
0x180008e8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008e93  jmp     short loc_180008EA1
0x180008e95  lea     r8, asc_18007E540; "\n"
0x180008e9c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008ea1  xor     eax, eax
0x180008ea3  mov     rcx, [rsp+278h+var_38]
0x180008eab  xor     rcx, rsp; StackCookie
0x180008eae  call    __security_check_cookie
0x180008eb3  mov     rbx, [rsp+278h+arg_18]
0x180008ebb  add     rsp, 250h
0x180008ec2  pop     r15
0x180008ec4  pop     r14
0x180008ec6  pop     rdi
0x180008ec7  pop     rsi
0x180008ec8  pop     rbp
0x180008ec9  retn
```
