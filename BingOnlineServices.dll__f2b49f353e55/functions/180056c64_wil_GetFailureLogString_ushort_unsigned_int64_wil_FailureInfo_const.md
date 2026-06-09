# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180056c64`
- end: `0x180056f1a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180055e30`
- `0x180057710`
- `0x180057bc8`
- `0x180058d90`

## callees

- `0x180004fa0`
- `0x180005e6c`
- `0x180056c64`
- `0x180057a10`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180056d96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180056d96`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056e17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056e17`

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
          v7 = (const char *)&word_180067AF6;
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
0x180056c64  mov     [rsp+arg_18], rbx
0x180056c69  push    rbp
0x180056c6a  push    rsi
0x180056c6b  push    rdi
0x180056c6c  push    r14
0x180056c6e  push    r15
0x180056c70  sub     rsp, 250h
0x180056c77  mov     rax, cs:__security_cookie
0x180056c7e  xor     rax, rsp
0x180056c81  mov     [rsp+278h+var_38], rax
0x180056c89  mov     rbx, r8
0x180056c8c  mov     rsi, rdx
0x180056c8f  mov     r14, rcx
0x180056c92  xor     r15d, r15d
0x180056c95  test    rdx, rdx
0x180056c98  jz      loc_180056EF1
0x180056c9e  test    rcx, rcx
0x180056ca1  jz      loc_180056EF1
0x180056ca7  mov     [rcx], r15w
0x180056cab  mov     rax, cs:g_pfnResultLoggingCallback
0x180056cb2  test    rax, rax
0x180056cb5  jz      short loc_180056CD8
0x180056cb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180056cbe  jz      short loc_180056CD8
0x180056cc0  mov     r8, rdx
0x180056cc3  mov     rdx, rcx
0x180056cc6  mov     rcx, rbx
0x180056cc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056cce  cmp     [r14], r15w
0x180056cd2  jnz     loc_180056EF1
0x180056cd8  mov     ecx, [rbx]
0x180056cda  mov     bpl, 8
0x180056cdd  test    ecx, ecx
0x180056cdf  jz      short loc_180056D2A
0x180056ce1  sub     ecx, 1
0x180056ce4  jz      short loc_180056D12
0x180056ce6  sub     ecx, 1
0x180056ce9  jz      short loc_180056D02
0x180056ceb  cmp     ecx, 1
0x180056cee  jz      short loc_180056CF9
0x180056cf0  lea     rdi, word_180067AF6
0x180056cf7  jmp     short loc_180056D31
0x180056cf9  lea     rdi, aFailfast; "FailFast"
0x180056d00  jmp     short loc_180056D31
0x180056d02  lea     rax, aLoghr; "LogHr"
0x180056d09  lea     rdi, aLognt; "LogNt"
0x180056d10  jmp     short loc_180056D20
0x180056d12  lea     rax, aReturnhr; "ReturnHr"
0x180056d19  lea     rdi, aReturnnt; "ReturnNt"
0x180056d20  test    [rbx+4], bpl
0x180056d24  cmovz   rdi, rax
0x180056d28  jmp     short loc_180056D31
0x180056d2a  lea     rdi, aException; "Exception"
0x180056d31  xor     edx, edx; Val
0x180056d33  mov     r8d, 200h; Size
0x180056d39  lea     rcx, [rsp+278h+Buffer]; void *
0x180056d3e  call    memset_0
0x180056d43  test    [rbx+4], bpl
0x180056d47  jz      short loc_180056D6C
0x180056d49  mov     ebp, [rbx+0Ch]
0x180056d4c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180056d53  test    rax, rax
0x180056d56  jz      short loc_180056D9C
0x180056d58  mov     r8d, 100h
0x180056d5e  lea     rdx, [rsp+278h+Buffer]
0x180056d63  mov     ecx, ebp
0x180056d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056d6a  jmp     short loc_180056D9C
0x180056d6c  mov     ebp, [rbx+8]
0x180056d6f  mov     [rsp+278h+Arguments], r15; Arguments
0x180056d74  mov     [rsp+278h+nSize], 100h; nSize
0x180056d7c  lea     rax, [rsp+278h+Buffer]
0x180056d81  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180056d86  mov     r9d, 400h; dwLanguageId
0x180056d8c  mov     r8d, ebp; dwMessageId
0x180056d8f  xor     edx, edx; lpSource
0x180056d91  mov     ecx, 1200h; dwFlags
0x180056d96  call    cs:__imp_FormatMessageW
0x180056d9c  lea     rsi, [r14+rsi*2]
0x180056da0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180056da4  mov     rax, [rbx+88h]
0x180056dab  mov     rcx, [rbx+80h]
0x180056db2  mov     rdx, rsi; unsigned __int16 *
0x180056db5  test    r9, r9
0x180056db8  jz      short loc_180056DDC
0x180056dba  mov     [rsp+278h+Arguments], rax
0x180056dbf  mov     qword ptr [rsp+278h+nSize], rcx
0x180056dc4  mov     eax, [rbx+40h]
0x180056dc7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180056dcb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180056dd2  mov     rcx, r14; this
0x180056dd5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056dda  jmp     short loc_180056DF3
0x180056ddc  mov     [rsp+278h+lpBuffer], rax
0x180056de1  mov     r9, rcx; unsigned __int16 *
0x180056de4  lea     r8, aHsP; "%hs!%p: "
0x180056deb  mov     rcx, r14; this
0x180056dee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056df3  mov     r14, rax
0x180056df6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180056dfd  test    r9, r9
0x180056e00  jz      short loc_180056E17
0x180056e02  lea     r8, aCallerP; "(caller: %p) "
0x180056e09  mov     rdx, rsi; unsigned __int16 *
0x180056e0c  mov     rcx, rax; this
0x180056e0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056e14  mov     r14, rax
0x180056e17  call    cs:__imp_GetCurrentThreadId
0x180056e1d  lea     rcx, [rsp+278h+Buffer]
0x180056e22  mov     [rsp+278h+var_240], rcx
0x180056e27  mov     dword ptr [rsp+278h+Arguments], ebp
0x180056e2b  mov     [rsp+278h+nSize], eax
0x180056e2f  mov     eax, [rbx+44h]
0x180056e32  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180056e36  mov     r9, rdi; unsigned __int16 *
0x180056e39  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180056e40  mov     rdx, rsi; unsigned __int16 *
0x180056e43  mov     rcx, r14; this
0x180056e46  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056e4b  cmp     [rbx+18h], r15
0x180056e4f  jnz     short loc_180056E61
0x180056e51  cmp     [rbx+48h], r15
0x180056e55  jnz     short loc_180056E61
0x180056e57  cmp     [rbx+30h], r15
0x180056e5b  jz      loc_180056EF1
0x180056e61  lea     r8, asc_18006A910; "    "
0x180056e68  mov     rdx, rsi; unsigned __int16 *
0x180056e6b  mov     rcx, rax; this
0x180056e6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056e73  mov     r9, [rbx+18h]; unsigned __int16 *
0x180056e77  test    r9, r9
0x180056e7a  jz      short loc_180056E8E
0x180056e7c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180056e83  mov     rdx, rsi; unsigned __int16 *
0x180056e86  mov     rcx, rax; this
0x180056e89  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056e8e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180056e92  test    r9, r9
0x180056e95  jz      short loc_180056EA9
0x180056e97  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180056e9e  mov     rdx, rsi; unsigned __int16 *
0x180056ea1  mov     rcx, rax; this
0x180056ea4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056ea9  mov     rcx, [rbx+28h]
0x180056ead  mov     r9, [rbx+30h]; unsigned __int16 *
0x180056eb1  mov     rdx, rsi; unsigned __int16 *
0x180056eb4  test    rcx, rcx
0x180056eb7  jz      short loc_180056ECF
0x180056eb9  mov     [rsp+278h+lpBuffer], rcx
0x180056ebe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180056ec5  mov     rcx, rax; this
0x180056ec8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056ecd  jmp     short loc_180056EF1
0x180056ecf  mov     rcx, rax; this
0x180056ed2  test    r9, r9
0x180056ed5  jz      short loc_180056EE5
0x180056ed7  lea     r8, aHs; "[%hs]\n"
0x180056ede  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056ee3  jmp     short loc_180056EF1
0x180056ee5  lea     r8, asc_18006A9D4; "\n"
0x180056eec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180056ef1  xor     eax, eax
0x180056ef3  mov     rcx, [rsp+278h+var_38]
0x180056efb  xor     rcx, rsp; StackCookie
0x180056efe  call    __security_check_cookie
0x180056f03  mov     rbx, [rsp+278h+arg_18]
0x180056f0b  add     rsp, 250h
0x180056f12  pop     r15
0x180056f14  pop     r14
0x180056f16  pop     rdi
0x180056f17  pop     rsi
0x180056f18  pop     rbp
0x180056f19  retn
```
