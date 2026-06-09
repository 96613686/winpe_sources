# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000f604`
- end: `0x18000f8ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000e778`
- `0x18000ff9c`
- `0x180010454`
- `0x1800115a0`

## callees

- `0x18000d090`
- `0x18000dcb0`
- `0x18000f604`
- `0x18001029c`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f7b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000f7b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f736`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000f736`

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
          v7 = (const char *)&word_1800A076A;
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
0x18000f604  mov     [rsp+arg_18], rbx
0x18000f609  push    rbp
0x18000f60a  push    rsi
0x18000f60b  push    rdi
0x18000f60c  push    r14
0x18000f60e  push    r15
0x18000f610  sub     rsp, 250h
0x18000f617  mov     rax, cs:__security_cookie
0x18000f61e  xor     rax, rsp
0x18000f621  mov     [rsp+278h+var_38], rax
0x18000f629  mov     rbx, r8
0x18000f62c  mov     rsi, rdx
0x18000f62f  mov     r14, rcx
0x18000f632  xor     r15d, r15d
0x18000f635  test    rdx, rdx
0x18000f638  jz      loc_18000F891
0x18000f63e  test    rcx, rcx
0x18000f641  jz      loc_18000F891
0x18000f647  mov     [rcx], r15w
0x18000f64b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f652  test    rax, rax
0x18000f655  jz      short loc_18000F678
0x18000f657  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000f65e  jz      short loc_18000F678
0x18000f660  mov     r8, rdx
0x18000f663  mov     rdx, rcx
0x18000f666  mov     rcx, rbx
0x18000f669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f66e  cmp     [r14], r15w
0x18000f672  jnz     loc_18000F891
0x18000f678  mov     ecx, [rbx]
0x18000f67a  mov     bpl, 8
0x18000f67d  test    ecx, ecx
0x18000f67f  jz      short loc_18000F6CA
0x18000f681  sub     ecx, 1
0x18000f684  jz      short loc_18000F6B2
0x18000f686  sub     ecx, 1
0x18000f689  jz      short loc_18000F6A2
0x18000f68b  cmp     ecx, 1
0x18000f68e  jz      short loc_18000F699
0x18000f690  lea     rdi, word_1800A076A
0x18000f697  jmp     short loc_18000F6D1
0x18000f699  lea     rdi, aFailfast; "FailFast"
0x18000f6a0  jmp     short loc_18000F6D1
0x18000f6a2  lea     rax, aLoghr; "LogHr"
0x18000f6a9  lea     rdi, aLognt; "LogNt"
0x18000f6b0  jmp     short loc_18000F6C0
0x18000f6b2  lea     rax, aReturnhr; "ReturnHr"
0x18000f6b9  lea     rdi, aReturnnt; "ReturnNt"
0x18000f6c0  test    [rbx+4], bpl
0x18000f6c4  cmovz   rdi, rax
0x18000f6c8  jmp     short loc_18000F6D1
0x18000f6ca  lea     rdi, aException_0; "Exception"
0x18000f6d1  xor     edx, edx; Val
0x18000f6d3  mov     r8d, 200h; Size
0x18000f6d9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000f6de  call    memset_0
0x18000f6e3  test    [rbx+4], bpl
0x18000f6e7  jz      short loc_18000F70C
0x18000f6e9  mov     ebp, [rbx+0Ch]
0x18000f6ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000f6f3  test    rax, rax
0x18000f6f6  jz      short loc_18000F73C
0x18000f6f8  mov     r8d, 100h
0x18000f6fe  lea     rdx, [rsp+278h+Buffer]
0x18000f703  mov     ecx, ebp
0x18000f705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f70a  jmp     short loc_18000F73C
0x18000f70c  mov     ebp, [rbx+8]
0x18000f70f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000f714  mov     [rsp+278h+nSize], 100h; nSize
0x18000f71c  lea     rax, [rsp+278h+Buffer]
0x18000f721  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000f726  mov     r9d, 400h; dwLanguageId
0x18000f72c  mov     r8d, ebp; dwMessageId
0x18000f72f  xor     edx, edx; lpSource
0x18000f731  mov     ecx, 1200h; dwFlags
0x18000f736  call    cs:__imp_FormatMessageW
0x18000f73c  lea     rsi, [r14+rsi*2]
0x18000f740  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000f744  mov     rax, [rbx+88h]
0x18000f74b  mov     rcx, [rbx+80h]
0x18000f752  mov     rdx, rsi; unsigned __int16 *
0x18000f755  test    r9, r9
0x18000f758  jz      short loc_18000F77C
0x18000f75a  mov     [rsp+278h+Arguments], rax
0x18000f75f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000f764  mov     eax, [rbx+40h]
0x18000f767  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f76b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000f772  mov     rcx, r14; this
0x18000f775  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f77a  jmp     short loc_18000F793
0x18000f77c  mov     [rsp+278h+lpBuffer], rax
0x18000f781  mov     r9, rcx; unsigned __int16 *
0x18000f784  lea     r8, aHsP; "%hs!%p: "
0x18000f78b  mov     rcx, r14; this
0x18000f78e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f793  mov     r14, rax
0x18000f796  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000f79d  test    r9, r9
0x18000f7a0  jz      short loc_18000F7B7
0x18000f7a2  lea     r8, aCallerP; "(caller: %p) "
0x18000f7a9  mov     rdx, rsi; unsigned __int16 *
0x18000f7ac  mov     rcx, rax; this
0x18000f7af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f7b4  mov     r14, rax
0x18000f7b7  call    cs:__imp_GetCurrentThreadId
0x18000f7bd  lea     rcx, [rsp+278h+Buffer]
0x18000f7c2  mov     [rsp+278h+var_240], rcx
0x18000f7c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000f7cb  mov     [rsp+278h+nSize], eax
0x18000f7cf  mov     eax, [rbx+44h]
0x18000f7d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000f7d6  mov     r9, rdi; unsigned __int16 *
0x18000f7d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000f7e0  mov     rdx, rsi; unsigned __int16 *
0x18000f7e3  mov     rcx, r14; this
0x18000f7e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f7eb  cmp     [rbx+18h], r15
0x18000f7ef  jnz     short loc_18000F801
0x18000f7f1  cmp     [rbx+48h], r15
0x18000f7f5  jnz     short loc_18000F801
0x18000f7f7  cmp     [rbx+30h], r15
0x18000f7fb  jz      loc_18000F891
0x18000f801  lea     r8, asc_1800A0858; "    "
0x18000f808  mov     rdx, rsi; unsigned __int16 *
0x18000f80b  mov     rcx, rax; this
0x18000f80e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f813  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000f817  test    r9, r9
0x18000f81a  jz      short loc_18000F82E
0x18000f81c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000f823  mov     rdx, rsi; unsigned __int16 *
0x18000f826  mov     rcx, rax; this
0x18000f829  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f82e  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000f832  test    r9, r9
0x18000f835  jz      short loc_18000F849
0x18000f837  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000f83e  mov     rdx, rsi; unsigned __int16 *
0x18000f841  mov     rcx, rax; this
0x18000f844  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f849  mov     rcx, [rbx+28h]
0x18000f84d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000f851  mov     rdx, rsi; unsigned __int16 *
0x18000f854  test    rcx, rcx
0x18000f857  jz      short loc_18000F86F
0x18000f859  mov     [rsp+278h+lpBuffer], rcx
0x18000f85e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000f865  mov     rcx, rax; this
0x18000f868  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f86d  jmp     short loc_18000F891
0x18000f86f  mov     rcx, rax; this
0x18000f872  test    r9, r9
0x18000f875  jz      short loc_18000F885
0x18000f877  lea     r8, aHs; "[%hs]\n"
0x18000f87e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f883  jmp     short loc_18000F891
0x18000f885  lea     r8, asc_1800A08D0; "\n"
0x18000f88c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000f891  xor     eax, eax
0x18000f893  mov     rcx, [rsp+278h+var_38]
0x18000f89b  xor     rcx, rsp; StackCookie
0x18000f89e  call    __security_check_cookie
0x18000f8a3  mov     rbx, [rsp+278h+arg_18]
0x18000f8ab  add     rsp, 250h
0x18000f8b2  pop     r15
0x18000f8b4  pop     r14
0x18000f8b6  pop     rdi
0x18000f8b7  pop     rsi
0x18000f8b8  pop     rbp
0x18000f8b9  retn
```
