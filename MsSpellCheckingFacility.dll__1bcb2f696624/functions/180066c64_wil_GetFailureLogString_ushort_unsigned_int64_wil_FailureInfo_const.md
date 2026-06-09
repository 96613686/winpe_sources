# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180066c64`
- end: `0x180066f1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18003a960`
- `0x180067f38`
- `0x18006a2d0`

## callees

- `0x180061320`
- `0x180062314`
- `0x180066c64`
- `0x180067b9c`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180066d96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180066d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066e17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180066e17`

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
          v7 = (const char *)&word_1800E0132;
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
0x180066c64  mov     [rsp+arg_18], rbx
0x180066c69  push    rbp
0x180066c6a  push    rsi
0x180066c6b  push    rdi
0x180066c6c  push    r14
0x180066c6e  push    r15
0x180066c70  sub     rsp, 250h
0x180066c77  mov     rax, cs:__security_cookie
0x180066c7e  xor     rax, rsp
0x180066c81  mov     [rsp+278h+var_38], rax
0x180066c89  mov     rbx, r8
0x180066c8c  mov     rsi, rdx
0x180066c8f  mov     r14, rcx
0x180066c92  xor     r15d, r15d
0x180066c95  test    rdx, rdx
0x180066c98  jz      loc_180066EF1
0x180066c9e  test    rcx, rcx
0x180066ca1  jz      loc_180066EF1
0x180066ca7  mov     [rcx], r15w
0x180066cab  mov     rax, cs:g_pfnResultLoggingCallback
0x180066cb2  test    rax, rax
0x180066cb5  jz      short loc_180066CD8
0x180066cb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180066cbe  jz      short loc_180066CD8
0x180066cc0  mov     r8, rdx
0x180066cc3  mov     rdx, rcx
0x180066cc6  mov     rcx, rbx
0x180066cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066cce  cmp     [r14], r15w
0x180066cd2  jnz     loc_180066EF1
0x180066cd8  mov     ecx, [rbx]
0x180066cda  mov     bpl, 8
0x180066cdd  test    ecx, ecx
0x180066cdf  jz      short loc_180066D2A
0x180066ce1  sub     ecx, 1
0x180066ce4  jz      short loc_180066D12
0x180066ce6  sub     ecx, 1
0x180066ce9  jz      short loc_180066D02
0x180066ceb  cmp     ecx, 1
0x180066cee  jz      short loc_180066CF9
0x180066cf0  lea     rdi, word_1800E0132
0x180066cf7  jmp     short loc_180066D31
0x180066cf9  lea     rdi, aFailfast; "FailFast"
0x180066d00  jmp     short loc_180066D31
0x180066d02  lea     rax, aLoghr; "LogHr"
0x180066d09  lea     rdi, aLognt; "LogNt"
0x180066d10  jmp     short loc_180066D20
0x180066d12  lea     rax, aReturnhr; "ReturnHr"
0x180066d19  lea     rdi, aReturnnt; "ReturnNt"
0x180066d20  test    [rbx+4], bpl
0x180066d24  cmovz   rdi, rax
0x180066d28  jmp     short loc_180066D31
0x180066d2a  lea     rdi, aException; "Exception"
0x180066d31  xor     edx, edx; Val
0x180066d33  mov     r8d, 200h; Size
0x180066d39  lea     rcx, [rsp+278h+Buffer]; void *
0x180066d3e  call    memset_0
0x180066d43  test    [rbx+4], bpl
0x180066d47  jz      short loc_180066D6C
0x180066d49  mov     ebp, [rbx+0Ch]
0x180066d4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180066d53  test    rax, rax
0x180066d56  jz      short loc_180066D9C
0x180066d58  mov     r8d, 100h
0x180066d5e  lea     rdx, [rsp+278h+Buffer]
0x180066d63  mov     ecx, ebp
0x180066d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180066d6a  jmp     short loc_180066D9C
0x180066d6c  mov     ebp, [rbx+8]
0x180066d6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180066d74  mov     [rsp+278h+nSize], 100h; nSize
0x180066d7c  lea     rax, [rsp+278h+Buffer]
0x180066d81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180066d86  mov     r9d, 400h; dwLanguageId
0x180066d8c  mov     r8d, ebp; dwMessageId
0x180066d8f  xor     edx, edx; lpSource
0x180066d91  mov     ecx, 1200h; dwFlags
0x180066d96  call    cs:__imp_FormatMessageW
0x180066d9c  lea     rsi, [r14+rsi*2]
0x180066da0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180066da4  mov     rax, [rbx+88h]
0x180066dab  mov     rcx, [rbx+80h]
0x180066db2  mov     rdx, rsi; unsigned __int16 *
0x180066db5  test    r9, r9
0x180066db8  jz      short loc_180066DDC
0x180066dba  mov     [rsp+278h+Arguments], rax
0x180066dbf  mov     qword ptr [rsp+278h+nSize], rcx
0x180066dc4  mov     eax, [rbx+40h]
0x180066dc7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180066dcb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180066dd2  mov     rcx, r14; this
0x180066dd5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066dda  jmp     short loc_180066DF3
0x180066ddc  mov     [rsp+278h+lpBuffer], rax
0x180066de1  mov     r9, rcx; unsigned __int16 *
0x180066de4  lea     r8, aHsP; "%hs!%p: "
0x180066deb  mov     rcx, r14; this
0x180066dee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066df3  mov     r14, rax
0x180066df6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180066dfd  test    r9, r9
0x180066e00  jz      short loc_180066E17
0x180066e02  lea     r8, aCallerP; "(caller: %p) "
0x180066e09  mov     rdx, rsi; unsigned __int16 *
0x180066e0c  mov     rcx, rax; this
0x180066e0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066e14  mov     r14, rax
0x180066e17  call    cs:__imp_GetCurrentThreadId
0x180066e1d  lea     rcx, [rsp+278h+Buffer]
0x180066e22  mov     [rsp+278h+var_240], rcx
0x180066e27  mov     dword ptr [rsp+278h+Arguments], ebp
0x180066e2b  mov     [rsp+278h+nSize], eax
0x180066e2f  mov     eax, [rbx+44h]
0x180066e32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180066e36  mov     r9, rdi; unsigned __int16 *
0x180066e39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180066e40  mov     rdx, rsi; unsigned __int16 *
0x180066e43  mov     rcx, r14; this
0x180066e46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066e4b  cmp     [rbx+18h], r15
0x180066e4f  jnz     short loc_180066E61
0x180066e51  cmp     [rbx+48h], r15
0x180066e55  jnz     short loc_180066E61
0x180066e57  cmp     [rbx+30h], r15
0x180066e5b  jz      loc_180066EF1
0x180066e61  lea     r8, asc_1800E0220; "    "
0x180066e68  mov     rdx, rsi; unsigned __int16 *
0x180066e6b  mov     rcx, rax; this
0x180066e6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066e73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180066e77  test    r9, r9
0x180066e7a  jz      short loc_180066E8E
0x180066e7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180066e83  mov     rdx, rsi; unsigned __int16 *
0x180066e86  mov     rcx, rax; this
0x180066e89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066e8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180066e92  test    r9, r9
0x180066e95  jz      short loc_180066EA9
0x180066e97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180066e9e  mov     rdx, rsi; unsigned __int16 *
0x180066ea1  mov     rcx, rax; this
0x180066ea4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066ea9  mov     rcx, [rbx+28h]
0x180066ead  mov     r9, [rbx+30h]; unsigned __int16 *
0x180066eb1  mov     rdx, rsi; unsigned __int16 *
0x180066eb4  test    rcx, rcx
0x180066eb7  jz      short loc_180066ECF
0x180066eb9  mov     [rsp+278h+lpBuffer], rcx
0x180066ebe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180066ec5  mov     rcx, rax; this
0x180066ec8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066ecd  jmp     short loc_180066EF1
0x180066ecf  mov     rcx, rax; this
0x180066ed2  test    r9, r9
0x180066ed5  jz      short loc_180066EE5
0x180066ed7  lea     r8, aHs; "[%hs]\n"
0x180066ede  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066ee3  jmp     short loc_180066EF1
0x180066ee5  lea     r8, asc_1800E0298; "\n"
0x180066eec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180066ef1  xor     eax, eax
0x180066ef3  mov     rcx, [rsp+278h+var_38]
0x180066efb  xor     rcx, rsp; StackCookie
0x180066efe  call    __security_check_cookie
0x180066f03  mov     rbx, [rsp+278h+arg_18]
0x180066f0b  add     rsp, 250h
0x180066f12  pop     r15
0x180066f14  pop     r14
0x180066f16  pop     rdi
0x180066f17  pop     rsi
0x180066f18  pop     rbp
0x180066f19  retn
```
