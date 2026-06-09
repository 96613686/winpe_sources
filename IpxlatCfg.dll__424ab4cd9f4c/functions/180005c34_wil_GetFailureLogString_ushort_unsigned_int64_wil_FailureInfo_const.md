# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005c34`
- end: `0x180005eea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180003724`
- `0x18000398c`
- `0x18000667c`
- `0x180009e00`
- `0x180018065`
- `0x180018199`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180005c34`
- `0x18000697c`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005d66`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005d66`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005de7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005de7`

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
          v7 = (const char *)&byte_18001B4DB;
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
0x180005c34  mov     [rsp+arg_18], rbx
0x180005c39  push    rbp
0x180005c3a  push    rsi
0x180005c3b  push    rdi
0x180005c3c  push    r14
0x180005c3e  push    r15
0x180005c40  sub     rsp, 250h
0x180005c47  mov     rax, cs:__security_cookie
0x180005c4e  xor     rax, rsp
0x180005c51  mov     [rsp+278h+var_38], rax
0x180005c59  mov     rbx, r8
0x180005c5c  mov     rsi, rdx
0x180005c5f  mov     r14, rcx
0x180005c62  xor     r15d, r15d
0x180005c65  test    rdx, rdx
0x180005c68  jz      loc_180005EC1
0x180005c6e  test    rcx, rcx
0x180005c71  jz      loc_180005EC1
0x180005c77  mov     [rcx], r15w
0x180005c7b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c82  test    rax, rax
0x180005c85  jz      short loc_180005CA8
0x180005c87  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005c8e  jz      short loc_180005CA8
0x180005c90  mov     r8, rdx
0x180005c93  mov     rdx, rcx
0x180005c96  mov     rcx, rbx
0x180005c99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c9e  cmp     [r14], r15w
0x180005ca2  jnz     loc_180005EC1
0x180005ca8  mov     ecx, [rbx]
0x180005caa  mov     bpl, 8
0x180005cad  test    ecx, ecx
0x180005caf  jz      short loc_180005CFA
0x180005cb1  sub     ecx, 1
0x180005cb4  jz      short loc_180005CE2
0x180005cb6  sub     ecx, 1
0x180005cb9  jz      short loc_180005CD2
0x180005cbb  cmp     ecx, 1
0x180005cbe  jz      short loc_180005CC9
0x180005cc0  lea     rdi, byte_18001B4DB
0x180005cc7  jmp     short loc_180005D01
0x180005cc9  lea     rdi, aFailfast; "FailFast"
0x180005cd0  jmp     short loc_180005D01
0x180005cd2  lea     rax, aLoghr; "LogHr"
0x180005cd9  lea     rdi, aLognt; "LogNt"
0x180005ce0  jmp     short loc_180005CF0
0x180005ce2  lea     rax, aReturnhr; "ReturnHr"
0x180005ce9  lea     rdi, aReturnnt; "ReturnNt"
0x180005cf0  test    [rbx+4], bpl
0x180005cf4  cmovz   rdi, rax
0x180005cf8  jmp     short loc_180005D01
0x180005cfa  lea     rdi, aException; "Exception"
0x180005d01  xor     edx, edx; Val
0x180005d03  mov     r8d, 200h; Size
0x180005d09  lea     rcx, [rsp+278h+Buffer]; void *
0x180005d0e  call    memset_0
0x180005d13  test    [rbx+4], bpl
0x180005d17  jz      short loc_180005D3C
0x180005d19  mov     ebp, [rbx+0Ch]
0x180005d1c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005d23  test    rax, rax
0x180005d26  jz      short loc_180005D6C
0x180005d28  mov     r8d, 100h
0x180005d2e  lea     rdx, [rsp+278h+Buffer]
0x180005d33  mov     ecx, ebp
0x180005d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005d3a  jmp     short loc_180005D6C
0x180005d3c  mov     ebp, [rbx+8]
0x180005d3f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005d44  mov     [rsp+278h+nSize], 100h; nSize
0x180005d4c  lea     rax, [rsp+278h+Buffer]
0x180005d51  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005d56  mov     r9d, 400h; dwLanguageId
0x180005d5c  mov     r8d, ebp; dwMessageId
0x180005d5f  xor     edx, edx; lpSource
0x180005d61  mov     ecx, 1200h; dwFlags
0x180005d66  call    cs:__imp_FormatMessageW
0x180005d6c  lea     rsi, [r14+rsi*2]
0x180005d70  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005d74  mov     rax, [rbx+88h]
0x180005d7b  mov     rcx, [rbx+80h]
0x180005d82  mov     rdx, rsi; unsigned __int16 *
0x180005d85  test    r9, r9
0x180005d88  jz      short loc_180005DAC
0x180005d8a  mov     [rsp+278h+Arguments], rax
0x180005d8f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005d94  mov     eax, [rbx+40h]
0x180005d97  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005d9b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005da2  mov     rcx, r14; this
0x180005da5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005daa  jmp     short loc_180005DC3
0x180005dac  mov     [rsp+278h+lpBuffer], rax
0x180005db1  mov     r9, rcx; unsigned __int16 *
0x180005db4  lea     r8, aHsP; "%hs!%p: "
0x180005dbb  mov     rcx, r14; this
0x180005dbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005dc3  mov     r14, rax
0x180005dc6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005dcd  test    r9, r9
0x180005dd0  jz      short loc_180005DE7
0x180005dd2  lea     r8, aCallerP; "(caller: %p) "
0x180005dd9  mov     rdx, rsi; unsigned __int16 *
0x180005ddc  mov     rcx, rax; this
0x180005ddf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005de4  mov     r14, rax
0x180005de7  call    cs:__imp_GetCurrentThreadId
0x180005ded  lea     rcx, [rsp+278h+Buffer]
0x180005df2  mov     [rsp+278h+var_240], rcx
0x180005df7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005dfb  mov     [rsp+278h+nSize], eax
0x180005dff  mov     eax, [rbx+44h]
0x180005e02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005e06  mov     r9, rdi; unsigned __int16 *
0x180005e09  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005e10  mov     rdx, rsi; unsigned __int16 *
0x180005e13  mov     rcx, r14; this
0x180005e16  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e1b  cmp     [rbx+18h], r15
0x180005e1f  jnz     short loc_180005E31
0x180005e21  cmp     [rbx+48h], r15
0x180005e25  jnz     short loc_180005E31
0x180005e27  cmp     [rbx+30h], r15
0x180005e2b  jz      loc_180005EC1
0x180005e31  lea     r8, asc_18001B5E0; "    "
0x180005e38  mov     rdx, rsi; unsigned __int16 *
0x180005e3b  mov     rcx, rax; this
0x180005e3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e43  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005e47  test    r9, r9
0x180005e4a  jz      short loc_180005E5E
0x180005e4c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005e53  mov     rdx, rsi; unsigned __int16 *
0x180005e56  mov     rcx, rax; this
0x180005e59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e5e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005e62  test    r9, r9
0x180005e65  jz      short loc_180005E79
0x180005e67  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005e6e  mov     rdx, rsi; unsigned __int16 *
0x180005e71  mov     rcx, rax; this
0x180005e74  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e79  mov     rcx, [rbx+28h]
0x180005e7d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005e81  mov     rdx, rsi; unsigned __int16 *
0x180005e84  test    rcx, rcx
0x180005e87  jz      short loc_180005E9F
0x180005e89  mov     [rsp+278h+lpBuffer], rcx
0x180005e8e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005e95  mov     rcx, rax; this
0x180005e98  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005e9d  jmp     short loc_180005EC1
0x180005e9f  mov     rcx, rax; this
0x180005ea2  test    r9, r9
0x180005ea5  jz      short loc_180005EB5
0x180005ea7  lea     r8, aHs; "[%hs]\n"
0x180005eae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005eb3  jmp     short loc_180005EC1
0x180005eb5  lea     r8, asc_18001B658; "\n"
0x180005ebc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ec1  xor     eax, eax
0x180005ec3  mov     rcx, [rsp+278h+var_38]
0x180005ecb  xor     rcx, rsp; StackCookie
0x180005ece  call    __security_check_cookie
0x180005ed3  mov     rbx, [rsp+278h+arg_18]
0x180005edb  add     rsp, 250h
0x180005ee2  pop     r15
0x180005ee4  pop     r14
0x180005ee6  pop     rdi
0x180005ee7  pop     rsi
0x180005ee8  pop     rbp
0x180005ee9  retn
```
