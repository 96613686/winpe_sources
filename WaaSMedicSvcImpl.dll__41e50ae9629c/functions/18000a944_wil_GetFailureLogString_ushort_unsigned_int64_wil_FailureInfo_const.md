# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a944`
- end: `0x18000abfa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180009224`
- `0x1800094a4`
- `0x18000b354`
- `0x18000cce0`
- `0x18000e500`
- `0x18006b546`
- `0x18006b67a`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x18000a944`
- `0x18000b654`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aaf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aaf7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aa76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000aa76`

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
          v7 = (const char *)&word_180072C40;
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
0x18000a944  mov     [rsp+arg_18], rbx
0x18000a949  push    rbp
0x18000a94a  push    rsi
0x18000a94b  push    rdi
0x18000a94c  push    r14
0x18000a94e  push    r15
0x18000a950  sub     rsp, 250h
0x18000a957  mov     rax, cs:__security_cookie
0x18000a95e  xor     rax, rsp
0x18000a961  mov     [rsp+278h+var_38], rax
0x18000a969  mov     rbx, r8
0x18000a96c  mov     rsi, rdx
0x18000a96f  mov     r14, rcx
0x18000a972  xor     r15d, r15d
0x18000a975  test    rdx, rdx
0x18000a978  jz      loc_18000ABD1
0x18000a97e  test    rcx, rcx
0x18000a981  jz      loc_18000ABD1
0x18000a987  mov     [rcx], r15w
0x18000a98b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a992  test    rax, rax
0x18000a995  jz      short loc_18000A9B8
0x18000a997  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a99e  jz      short loc_18000A9B8
0x18000a9a0  mov     r8, rdx
0x18000a9a3  mov     rdx, rcx
0x18000a9a6  mov     rcx, rbx
0x18000a9a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9ae  cmp     [r14], r15w
0x18000a9b2  jnz     loc_18000ABD1
0x18000a9b8  mov     ecx, [rbx]
0x18000a9ba  mov     bpl, 8
0x18000a9bd  test    ecx, ecx
0x18000a9bf  jz      short loc_18000AA0A
0x18000a9c1  sub     ecx, 1
0x18000a9c4  jz      short loc_18000A9F2
0x18000a9c6  sub     ecx, 1
0x18000a9c9  jz      short loc_18000A9E2
0x18000a9cb  cmp     ecx, 1
0x18000a9ce  jz      short loc_18000A9D9
0x18000a9d0  lea     rdi, word_180072C40
0x18000a9d7  jmp     short loc_18000AA11
0x18000a9d9  lea     rdi, aFailfast; "FailFast"
0x18000a9e0  jmp     short loc_18000AA11
0x18000a9e2  lea     rax, aLoghr; "LogHr"
0x18000a9e9  lea     rdi, aLognt; "LogNt"
0x18000a9f0  jmp     short loc_18000AA00
0x18000a9f2  lea     rax, aReturnhr; "ReturnHr"
0x18000a9f9  lea     rdi, aReturnnt; "ReturnNt"
0x18000aa00  test    [rbx+4], bpl
0x18000aa04  cmovz   rdi, rax
0x18000aa08  jmp     short loc_18000AA11
0x18000aa0a  lea     rdi, aException; "Exception"
0x18000aa11  xor     edx, edx; Val
0x18000aa13  mov     r8d, 200h; Size
0x18000aa19  lea     rcx, [rsp+278h+Buffer]; void *
0x18000aa1e  call    memset_0
0x18000aa23  test    [rbx+4], bpl
0x18000aa27  jz      short loc_18000AA4C
0x18000aa29  mov     ebp, [rbx+0Ch]
0x18000aa2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000aa33  test    rax, rax
0x18000aa36  jz      short loc_18000AA7C
0x18000aa38  mov     r8d, 100h
0x18000aa3e  lea     rdx, [rsp+278h+Buffer]
0x18000aa43  mov     ecx, ebp
0x18000aa45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aa4a  jmp     short loc_18000AA7C
0x18000aa4c  mov     ebp, [rbx+8]
0x18000aa4f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000aa54  mov     [rsp+278h+nSize], 100h; nSize
0x18000aa5c  lea     rax, [rsp+278h+Buffer]
0x18000aa61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000aa66  mov     r9d, 400h; dwLanguageId
0x18000aa6c  mov     r8d, ebp; dwMessageId
0x18000aa6f  xor     edx, edx; lpSource
0x18000aa71  mov     ecx, 1200h; dwFlags
0x18000aa76  call    cs:__imp_FormatMessageW
0x18000aa7c  lea     rsi, [r14+rsi*2]
0x18000aa80  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000aa84  mov     rax, [rbx+88h]
0x18000aa8b  mov     rcx, [rbx+80h]
0x18000aa92  mov     rdx, rsi; unsigned __int16 *
0x18000aa95  test    r9, r9
0x18000aa98  jz      short loc_18000AABC
0x18000aa9a  mov     [rsp+278h+Arguments], rax
0x18000aa9f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000aaa4  mov     eax, [rbx+40h]
0x18000aaa7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000aaab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000aab2  mov     rcx, r14; this
0x18000aab5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aaba  jmp     short loc_18000AAD3
0x18000aabc  mov     [rsp+278h+lpBuffer], rax
0x18000aac1  mov     r9, rcx; unsigned __int16 *
0x18000aac4  lea     r8, aHsP; "%hs!%p: "
0x18000aacb  mov     rcx, r14; this
0x18000aace  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aad3  mov     r14, rax
0x18000aad6  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000aadd  test    r9, r9
0x18000aae0  jz      short loc_18000AAF7
0x18000aae2  lea     r8, aCallerP; "(caller: %p) "
0x18000aae9  mov     rdx, rsi; unsigned __int16 *
0x18000aaec  mov     rcx, rax; this
0x18000aaef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000aaf4  mov     r14, rax
0x18000aaf7  call    cs:__imp_GetCurrentThreadId
0x18000aafd  lea     rcx, [rsp+278h+Buffer]
0x18000ab02  mov     [rsp+278h+var_240], rcx
0x18000ab07  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000ab0b  mov     [rsp+278h+nSize], eax
0x18000ab0f  mov     eax, [rbx+44h]
0x18000ab12  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ab16  mov     r9, rdi; unsigned __int16 *
0x18000ab19  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000ab20  mov     rdx, rsi; unsigned __int16 *
0x18000ab23  mov     rcx, r14; this
0x18000ab26  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab2b  cmp     [rbx+18h], r15
0x18000ab2f  jnz     short loc_18000AB41
0x18000ab31  cmp     [rbx+48h], r15
0x18000ab35  jnz     short loc_18000AB41
0x18000ab37  cmp     [rbx+30h], r15
0x18000ab3b  jz      loc_18000ABD1
0x18000ab41  lea     r8, asc_180072D60; "    "
0x18000ab48  mov     rdx, rsi; unsigned __int16 *
0x18000ab4b  mov     rcx, rax; this
0x18000ab4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab53  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000ab57  test    r9, r9
0x18000ab5a  jz      short loc_18000AB6E
0x18000ab5c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000ab63  mov     rdx, rsi; unsigned __int16 *
0x18000ab66  mov     rcx, rax; this
0x18000ab69  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab6e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000ab72  test    r9, r9
0x18000ab75  jz      short loc_18000AB89
0x18000ab77  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000ab7e  mov     rdx, rsi; unsigned __int16 *
0x18000ab81  mov     rcx, rax; this
0x18000ab84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ab89  mov     rcx, [rbx+28h]
0x18000ab8d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000ab91  mov     rdx, rsi; unsigned __int16 *
0x18000ab94  test    rcx, rcx
0x18000ab97  jz      short loc_18000ABAF
0x18000ab99  mov     [rsp+278h+lpBuffer], rcx
0x18000ab9e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000aba5  mov     rcx, rax; this
0x18000aba8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000abad  jmp     short loc_18000ABD1
0x18000abaf  mov     rcx, rax; this
0x18000abb2  test    r9, r9
0x18000abb5  jz      short loc_18000ABC5
0x18000abb7  lea     r8, aHs; "[%hs]\n"
0x18000abbe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000abc3  jmp     short loc_18000ABD1
0x18000abc5  lea     r8, asc_180072DD8; "\n"
0x18000abcc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000abd1  xor     eax, eax
0x18000abd3  mov     rcx, [rsp+278h+var_38]
0x18000abdb  xor     rcx, rsp; StackCookie
0x18000abde  call    __security_check_cookie
0x18000abe3  mov     rbx, [rsp+278h+arg_18]
0x18000abeb  add     rsp, 250h
0x18000abf2  pop     r15
0x18000abf4  pop     r14
0x18000abf6  pop     rdi
0x18000abf7  pop     rsi
0x18000abf8  pop     rbp
0x18000abf9  retn
```
