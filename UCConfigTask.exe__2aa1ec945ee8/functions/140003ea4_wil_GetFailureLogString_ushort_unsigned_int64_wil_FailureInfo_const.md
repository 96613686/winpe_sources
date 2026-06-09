# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003ea4`
- end: `0x14000415a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002594`
- `0x140004a0c`
- `0x140007610`

## callees

- `0x1400014c0`
- `0x14000209c`
- `0x140003ea4`
- `0x140004d0c`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004057`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004057`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003fd6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003fd6`

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
          v7 = (const char *)&word_14000A74A;
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
0x140003ea4  mov     [rsp+arg_18], rbx
0x140003ea9  push    rbp
0x140003eaa  push    rsi
0x140003eab  push    rdi
0x140003eac  push    r14
0x140003eae  push    r15
0x140003eb0  sub     rsp, 250h
0x140003eb7  mov     rax, cs:__security_cookie
0x140003ebe  xor     rax, rsp
0x140003ec1  mov     [rsp+278h+var_38], rax
0x140003ec9  mov     rbx, r8
0x140003ecc  mov     rsi, rdx
0x140003ecf  mov     r14, rcx
0x140003ed2  xor     r15d, r15d
0x140003ed5  test    rdx, rdx
0x140003ed8  jz      loc_140004131
0x140003ede  test    rcx, rcx
0x140003ee1  jz      loc_140004131
0x140003ee7  mov     [rcx], r15w
0x140003eeb  mov     rax, cs:g_pfnResultLoggingCallback
0x140003ef2  test    rax, rax
0x140003ef5  jz      short loc_140003F18
0x140003ef7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003efe  jz      short loc_140003F18
0x140003f00  mov     r8, rdx
0x140003f03  mov     rdx, rcx
0x140003f06  mov     rcx, rbx
0x140003f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003f0e  cmp     [r14], r15w
0x140003f12  jnz     loc_140004131
0x140003f18  mov     ecx, [rbx]
0x140003f1a  mov     bpl, 8
0x140003f1d  test    ecx, ecx
0x140003f1f  jz      short loc_140003F6A
0x140003f21  sub     ecx, 1
0x140003f24  jz      short loc_140003F52
0x140003f26  sub     ecx, 1
0x140003f29  jz      short loc_140003F42
0x140003f2b  cmp     ecx, 1
0x140003f2e  jz      short loc_140003F39
0x140003f30  lea     rdi, word_14000A74A
0x140003f37  jmp     short loc_140003F71
0x140003f39  lea     rdi, aFailfast; "FailFast"
0x140003f40  jmp     short loc_140003F71
0x140003f42  lea     rax, aLoghr; "LogHr"
0x140003f49  lea     rdi, aLognt; "LogNt"
0x140003f50  jmp     short loc_140003F60
0x140003f52  lea     rax, aReturnhr; "ReturnHr"
0x140003f59  lea     rdi, aReturnnt; "ReturnNt"
0x140003f60  test    [rbx+4], bpl
0x140003f64  cmovz   rdi, rax
0x140003f68  jmp     short loc_140003F71
0x140003f6a  lea     rdi, aException; "Exception"
0x140003f71  xor     edx, edx; Val
0x140003f73  mov     r8d, 200h; Size
0x140003f79  lea     rcx, [rsp+278h+Buffer]; void *
0x140003f7e  call    memset_0
0x140003f83  test    [rbx+4], bpl
0x140003f87  jz      short loc_140003FAC
0x140003f89  mov     ebp, [rbx+0Ch]
0x140003f8c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003f93  test    rax, rax
0x140003f96  jz      short loc_140003FDC
0x140003f98  mov     r8d, 100h
0x140003f9e  lea     rdx, [rsp+278h+Buffer]
0x140003fa3  mov     ecx, ebp
0x140003fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003faa  jmp     short loc_140003FDC
0x140003fac  mov     ebp, [rbx+8]
0x140003faf  mov     [rsp+278h+Arguments], r15; Arguments
0x140003fb4  mov     [rsp+278h+nSize], 100h; nSize
0x140003fbc  lea     rax, [rsp+278h+Buffer]
0x140003fc1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003fc6  mov     r9d, 400h; dwLanguageId
0x140003fcc  mov     r8d, ebp; dwMessageId
0x140003fcf  xor     edx, edx; lpSource
0x140003fd1  mov     ecx, 1200h; dwFlags
0x140003fd6  call    cs:__imp_FormatMessageW
0x140003fdc  lea     rsi, [r14+rsi*2]
0x140003fe0  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003fe4  mov     rax, [rbx+88h]
0x140003feb  mov     rcx, [rbx+80h]
0x140003ff2  mov     rdx, rsi; unsigned __int16 *
0x140003ff5  test    r9, r9
0x140003ff8  jz      short loc_14000401C
0x140003ffa  mov     [rsp+278h+Arguments], rax
0x140003fff  mov     qword ptr [rsp+278h+nSize], rcx
0x140004004  mov     eax, [rbx+40h]
0x140004007  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000400b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140004012  mov     rcx, r14; this
0x140004015  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000401a  jmp     short loc_140004033
0x14000401c  mov     [rsp+278h+lpBuffer], rax
0x140004021  mov     r9, rcx; unsigned __int16 *
0x140004024  lea     r8, aHsP; "%hs!%p: "
0x14000402b  mov     rcx, r14; this
0x14000402e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004033  mov     r14, rax
0x140004036  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000403d  test    r9, r9
0x140004040  jz      short loc_140004057
0x140004042  lea     r8, aCallerP; "(caller: %p) "
0x140004049  mov     rdx, rsi; unsigned __int16 *
0x14000404c  mov     rcx, rax; this
0x14000404f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004054  mov     r14, rax
0x140004057  call    cs:__imp_GetCurrentThreadId
0x14000405d  lea     rcx, [rsp+278h+Buffer]
0x140004062  mov     [rsp+278h+var_240], rcx
0x140004067  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000406b  mov     [rsp+278h+nSize], eax
0x14000406f  mov     eax, [rbx+44h]
0x140004072  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004076  mov     r9, rdi; unsigned __int16 *
0x140004079  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004080  mov     rdx, rsi; unsigned __int16 *
0x140004083  mov     rcx, r14; this
0x140004086  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000408b  cmp     [rbx+18h], r15
0x14000408f  jnz     short loc_1400040A1
0x140004091  cmp     [rbx+48h], r15
0x140004095  jnz     short loc_1400040A1
0x140004097  cmp     [rbx+30h], r15
0x14000409b  jz      loc_140004131
0x1400040a1  lea     r8, asc_14000A838; "    "
0x1400040a8  mov     rdx, rsi; unsigned __int16 *
0x1400040ab  mov     rcx, rax; this
0x1400040ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400040b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400040b7  test    r9, r9
0x1400040ba  jz      short loc_1400040CE
0x1400040bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400040c3  mov     rdx, rsi; unsigned __int16 *
0x1400040c6  mov     rcx, rax; this
0x1400040c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400040ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400040d2  test    r9, r9
0x1400040d5  jz      short loc_1400040E9
0x1400040d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400040de  mov     rdx, rsi; unsigned __int16 *
0x1400040e1  mov     rcx, rax; this
0x1400040e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400040e9  mov     rcx, [rbx+28h]
0x1400040ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400040f1  mov     rdx, rsi; unsigned __int16 *
0x1400040f4  test    rcx, rcx
0x1400040f7  jz      short loc_14000410F
0x1400040f9  mov     [rsp+278h+lpBuffer], rcx
0x1400040fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004105  mov     rcx, rax; this
0x140004108  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000410d  jmp     short loc_140004131
0x14000410f  mov     rcx, rax; this
0x140004112  test    r9, r9
0x140004115  jz      short loc_140004125
0x140004117  lea     r8, aHs; "[%hs]\n"
0x14000411e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004123  jmp     short loc_140004131
0x140004125  lea     r8, asc_14000A8B0; "\n"
0x14000412c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004131  xor     eax, eax
0x140004133  mov     rcx, [rsp+278h+var_38]
0x14000413b  xor     rcx, rsp; StackCookie
0x14000413e  call    __security_check_cookie
0x140004143  mov     rbx, [rsp+278h+arg_18]
0x14000414b  add     rsp, 250h
0x140004152  pop     r15
0x140004154  pop     r14
0x140004156  pop     rdi
0x140004157  pop     rsi
0x140004158  pop     rbp
0x140004159  retn
```
