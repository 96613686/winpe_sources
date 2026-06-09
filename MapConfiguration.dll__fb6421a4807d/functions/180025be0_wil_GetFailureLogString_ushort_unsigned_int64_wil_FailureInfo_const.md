# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180025be0`
- end: `0x180025e96`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180026228`
- `0x1800268cc`
- `0x180028940`

## callees

- `0x1800094a0`
- `0x18000a074`
- `0x180025be0`
- `0x180026528`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025d93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025d93`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180025d12`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180025d12`

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
          v7 = (const char *)&byte_180068819;
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
0x180025be0  mov     [rsp+arg_18], rbx
0x180025be5  push    rbp
0x180025be6  push    rsi
0x180025be7  push    rdi
0x180025be8  push    r14
0x180025bea  push    r15
0x180025bec  sub     rsp, 250h
0x180025bf3  mov     rax, cs:__security_cookie
0x180025bfa  xor     rax, rsp
0x180025bfd  mov     [rsp+278h+var_38], rax
0x180025c05  mov     rbx, r8
0x180025c08  mov     rsi, rdx
0x180025c0b  mov     r14, rcx
0x180025c0e  xor     r15d, r15d
0x180025c11  test    rdx, rdx
0x180025c14  jz      loc_180025E6D
0x180025c1a  test    rcx, rcx
0x180025c1d  jz      loc_180025E6D
0x180025c23  mov     [rcx], r15w
0x180025c27  mov     rax, cs:g_pfnResultLoggingCallback
0x180025c2e  test    rax, rax
0x180025c31  jz      short loc_180025C54
0x180025c33  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180025c3a  jz      short loc_180025C54
0x180025c3c  mov     r8, rdx
0x180025c3f  mov     rdx, rcx
0x180025c42  mov     rcx, rbx
0x180025c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c4a  cmp     [r14], r15w
0x180025c4e  jnz     loc_180025E6D
0x180025c54  mov     ecx, [rbx]
0x180025c56  mov     bpl, 8
0x180025c59  test    ecx, ecx
0x180025c5b  jz      short loc_180025CA6
0x180025c5d  sub     ecx, 1
0x180025c60  jz      short loc_180025C8E
0x180025c62  sub     ecx, 1
0x180025c65  jz      short loc_180025C7E
0x180025c67  cmp     ecx, 1
0x180025c6a  jz      short loc_180025C75
0x180025c6c  lea     rdi, byte_180068819
0x180025c73  jmp     short loc_180025CAD
0x180025c75  lea     rdi, aFailfast; "FailFast"
0x180025c7c  jmp     short loc_180025CAD
0x180025c7e  lea     rax, aLoghr; "LogHr"
0x180025c85  lea     rdi, aLognt; "LogNt"
0x180025c8c  jmp     short loc_180025C9C
0x180025c8e  lea     rax, aReturnhr; "ReturnHr"
0x180025c95  lea     rdi, aReturnnt; "ReturnNt"
0x180025c9c  test    [rbx+4], bpl
0x180025ca0  cmovz   rdi, rax
0x180025ca4  jmp     short loc_180025CAD
0x180025ca6  lea     rdi, aException; "Exception"
0x180025cad  xor     edx, edx; Val
0x180025caf  mov     r8d, 200h; Size
0x180025cb5  lea     rcx, [rsp+278h+Buffer]; void *
0x180025cba  call    memset_0
0x180025cbf  test    [rbx+4], bpl
0x180025cc3  jz      short loc_180025CE8
0x180025cc5  mov     ebp, [rbx+0Ch]
0x180025cc8  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180025ccf  test    rax, rax
0x180025cd2  jz      short loc_180025D18
0x180025cd4  mov     r8d, 100h
0x180025cda  lea     rdx, [rsp+278h+Buffer]
0x180025cdf  mov     ecx, ebp
0x180025ce1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ce6  jmp     short loc_180025D18
0x180025ce8  mov     ebp, [rbx+8]
0x180025ceb  mov     [rsp+278h+Arguments], r15; Arguments
0x180025cf0  mov     [rsp+278h+nSize], 100h; nSize
0x180025cf8  lea     rax, [rsp+278h+Buffer]
0x180025cfd  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180025d02  mov     r9d, 400h; dwLanguageId
0x180025d08  mov     r8d, ebp; dwMessageId
0x180025d0b  xor     edx, edx; lpSource
0x180025d0d  mov     ecx, 1200h; dwFlags
0x180025d12  call    cs:__imp_FormatMessageW
0x180025d18  lea     rsi, [r14+rsi*2]
0x180025d1c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180025d20  mov     rax, [rbx+88h]
0x180025d27  mov     rcx, [rbx+80h]
0x180025d2e  mov     rdx, rsi; unsigned __int16 *
0x180025d31  test    r9, r9
0x180025d34  jz      short loc_180025D58
0x180025d36  mov     [rsp+278h+Arguments], rax
0x180025d3b  mov     qword ptr [rsp+278h+nSize], rcx
0x180025d40  mov     eax, [rbx+40h]
0x180025d43  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025d47  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180025d4e  mov     rcx, r14; this
0x180025d51  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025d56  jmp     short loc_180025D6F
0x180025d58  mov     [rsp+278h+lpBuffer], rax
0x180025d5d  mov     r9, rcx; unsigned __int16 *
0x180025d60  lea     r8, aHsP; "%hs!%p: "
0x180025d67  mov     rcx, r14; this
0x180025d6a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025d6f  mov     r14, rax
0x180025d72  mov     r9, [rbx+90h]; unsigned __int16 *
0x180025d79  test    r9, r9
0x180025d7c  jz      short loc_180025D93
0x180025d7e  lea     r8, aCallerP; "(caller: %p) "
0x180025d85  mov     rdx, rsi; unsigned __int16 *
0x180025d88  mov     rcx, rax; this
0x180025d8b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025d90  mov     r14, rax
0x180025d93  call    cs:__imp_GetCurrentThreadId
0x180025d99  lea     rcx, [rsp+278h+Buffer]
0x180025d9e  mov     [rsp+278h+var_240], rcx
0x180025da3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180025da7  mov     [rsp+278h+nSize], eax
0x180025dab  mov     eax, [rbx+44h]
0x180025dae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180025db2  mov     r9, rdi; unsigned __int16 *
0x180025db5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180025dbc  mov     rdx, rsi; unsigned __int16 *
0x180025dbf  mov     rcx, r14; this
0x180025dc2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025dc7  cmp     [rbx+18h], r15
0x180025dcb  jnz     short loc_180025DDD
0x180025dcd  cmp     [rbx+48h], r15
0x180025dd1  jnz     short loc_180025DDD
0x180025dd3  cmp     [rbx+30h], r15
0x180025dd7  jz      loc_180025E6D
0x180025ddd  lea     r8, asc_180068890; "    "
0x180025de4  mov     rdx, rsi; unsigned __int16 *
0x180025de7  mov     rcx, rax; this
0x180025dea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025def  mov     r9, [rbx+18h]; unsigned __int16 *
0x180025df3  test    r9, r9
0x180025df6  jz      short loc_180025E0A
0x180025df8  lea     r8, aMsgWs; "Msg:[%ws] "
0x180025dff  mov     rdx, rsi; unsigned __int16 *
0x180025e02  mov     rcx, rax; this
0x180025e05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025e0a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180025e0e  test    r9, r9
0x180025e11  jz      short loc_180025E25
0x180025e13  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180025e1a  mov     rdx, rsi; unsigned __int16 *
0x180025e1d  mov     rcx, rax; this
0x180025e20  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025e25  mov     rcx, [rbx+28h]
0x180025e29  mov     r9, [rbx+30h]; unsigned __int16 *
0x180025e2d  mov     rdx, rsi; unsigned __int16 *
0x180025e30  test    rcx, rcx
0x180025e33  jz      short loc_180025E4B
0x180025e35  mov     [rsp+278h+lpBuffer], rcx
0x180025e3a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180025e41  mov     rcx, rax; this
0x180025e44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025e49  jmp     short loc_180025E6D
0x180025e4b  mov     rcx, rax; this
0x180025e4e  test    r9, r9
0x180025e51  jz      short loc_180025E61
0x180025e53  lea     r8, aHs; "[%hs]\n"
0x180025e5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025e5f  jmp     short loc_180025E6D
0x180025e61  lea     r8, asc_180068960; "\n"
0x180025e68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180025e6d  xor     eax, eax
0x180025e6f  mov     rcx, [rsp+278h+var_38]
0x180025e77  xor     rcx, rsp; StackCookie
0x180025e7a  call    __security_check_cookie
0x180025e7f  mov     rbx, [rsp+278h+arg_18]
0x180025e87  add     rsp, 250h
0x180025e8e  pop     r15
0x180025e90  pop     r14
0x180025e92  pop     rdi
0x180025e93  pop     rsi
0x180025e94  pop     rbp
0x180025e95  retn
```
