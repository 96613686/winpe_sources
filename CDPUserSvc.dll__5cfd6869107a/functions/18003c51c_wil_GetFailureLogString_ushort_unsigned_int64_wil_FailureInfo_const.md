# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003c51c`
- end: `0x18003c7d2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18003ab80`
- `0x18003ca30`
- `0x18003ce24`
- `0x18003e940`

## callees

- `0x18002c570`
- `0x18002d1c8`
- `0x18003c51c`
- `0x18003cd30`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c6cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c6cf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003c64e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003c64e`

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
          v7 = qword_18006E2A0;
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
0x18003c51c  mov     [rsp+arg_18], rbx
0x18003c521  push    rbp
0x18003c522  push    rsi
0x18003c523  push    rdi
0x18003c524  push    r14
0x18003c526  push    r15
0x18003c528  sub     rsp, 250h
0x18003c52f  mov     rax, cs:__security_cookie
0x18003c536  xor     rax, rsp
0x18003c539  mov     [rsp+278h+var_38], rax
0x18003c541  mov     rbx, r8
0x18003c544  mov     rsi, rdx
0x18003c547  mov     r14, rcx
0x18003c54a  xor     r15d, r15d
0x18003c54d  test    rdx, rdx
0x18003c550  jz      loc_18003C7A9
0x18003c556  test    rcx, rcx
0x18003c559  jz      loc_18003C7A9
0x18003c55f  mov     [rcx], r15w
0x18003c563  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c56a  test    rax, rax
0x18003c56d  jz      short loc_18003C590
0x18003c56f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003c576  jz      short loc_18003C590
0x18003c578  mov     r8, rdx
0x18003c57b  mov     rdx, rcx
0x18003c57e  mov     rcx, rbx
0x18003c581  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c586  cmp     [r14], r15w
0x18003c58a  jnz     loc_18003C7A9
0x18003c590  mov     ecx, [rbx]
0x18003c592  mov     bpl, 8
0x18003c595  test    ecx, ecx
0x18003c597  jz      short loc_18003C5E2
0x18003c599  sub     ecx, 1
0x18003c59c  jz      short loc_18003C5CA
0x18003c59e  sub     ecx, 1
0x18003c5a1  jz      short loc_18003C5BA
0x18003c5a3  cmp     ecx, 1
0x18003c5a6  jz      short loc_18003C5B1
0x18003c5a8  lea     rdi, qword_18006E2A0
0x18003c5af  jmp     short loc_18003C5E9
0x18003c5b1  lea     rdi, aFailfast; "FailFast"
0x18003c5b8  jmp     short loc_18003C5E9
0x18003c5ba  lea     rax, aLoghr; "LogHr"
0x18003c5c1  lea     rdi, aLognt; "LogNt"
0x18003c5c8  jmp     short loc_18003C5D8
0x18003c5ca  lea     rax, aReturnhr; "ReturnHr"
0x18003c5d1  lea     rdi, aReturnnt; "ReturnNt"
0x18003c5d8  test    [rbx+4], bpl
0x18003c5dc  cmovz   rdi, rax
0x18003c5e0  jmp     short loc_18003C5E9
0x18003c5e2  lea     rdi, aException; "Exception"
0x18003c5e9  xor     edx, edx; Val
0x18003c5eb  mov     r8d, 200h; Size
0x18003c5f1  lea     rcx, [rsp+278h+Buffer]; void *
0x18003c5f6  call    memset_0
0x18003c5fb  test    [rbx+4], bpl
0x18003c5ff  jz      short loc_18003C624
0x18003c601  mov     ebp, [rbx+0Ch]
0x18003c604  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003c60b  test    rax, rax
0x18003c60e  jz      short loc_18003C654
0x18003c610  mov     r8d, 100h
0x18003c616  lea     rdx, [rsp+278h+Buffer]
0x18003c61b  mov     ecx, ebp
0x18003c61d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c622  jmp     short loc_18003C654
0x18003c624  mov     ebp, [rbx+8]
0x18003c627  mov     [rsp+278h+Arguments], r15; Arguments
0x18003c62c  mov     [rsp+278h+nSize], 100h; nSize
0x18003c634  lea     rax, [rsp+278h+Buffer]
0x18003c639  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003c63e  mov     r9d, 400h; dwLanguageId
0x18003c644  mov     r8d, ebp; dwMessageId
0x18003c647  xor     edx, edx; lpSource
0x18003c649  mov     ecx, 1200h; dwFlags
0x18003c64e  call    cs:__imp_FormatMessageW
0x18003c654  lea     rsi, [r14+rsi*2]
0x18003c658  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003c65c  mov     rax, [rbx+88h]
0x18003c663  mov     rcx, [rbx+80h]
0x18003c66a  mov     rdx, rsi; unsigned __int16 *
0x18003c66d  test    r9, r9
0x18003c670  jz      short loc_18003C694
0x18003c672  mov     [rsp+278h+Arguments], rax
0x18003c677  mov     qword ptr [rsp+278h+nSize], rcx
0x18003c67c  mov     eax, [rbx+40h]
0x18003c67f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003c683  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003c68a  mov     rcx, r14; this
0x18003c68d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c692  jmp     short loc_18003C6AB
0x18003c694  mov     [rsp+278h+lpBuffer], rax
0x18003c699  mov     r9, rcx; unsigned __int16 *
0x18003c69c  lea     r8, aHsP; "%hs!%p: "
0x18003c6a3  mov     rcx, r14; this
0x18003c6a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c6ab  mov     r14, rax
0x18003c6ae  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003c6b5  test    r9, r9
0x18003c6b8  jz      short loc_18003C6CF
0x18003c6ba  lea     r8, aCallerP; "(caller: %p) "
0x18003c6c1  mov     rdx, rsi; unsigned __int16 *
0x18003c6c4  mov     rcx, rax; this
0x18003c6c7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c6cc  mov     r14, rax
0x18003c6cf  call    cs:__imp_GetCurrentThreadId
0x18003c6d5  lea     rcx, [rsp+278h+Buffer]
0x18003c6da  mov     [rsp+278h+var_240], rcx
0x18003c6df  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003c6e3  mov     [rsp+278h+nSize], eax
0x18003c6e7  mov     eax, [rbx+44h]
0x18003c6ea  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003c6ee  mov     r9, rdi; unsigned __int16 *
0x18003c6f1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003c6f8  mov     rdx, rsi; unsigned __int16 *
0x18003c6fb  mov     rcx, r14; this
0x18003c6fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c703  cmp     [rbx+18h], r15
0x18003c707  jnz     short loc_18003C719
0x18003c709  cmp     [rbx+48h], r15
0x18003c70d  jnz     short loc_18003C719
0x18003c70f  cmp     [rbx+30h], r15
0x18003c713  jz      loc_18003C7A9
0x18003c719  lea     r8, asc_18006E390; "    "
0x18003c720  mov     rdx, rsi; unsigned __int16 *
0x18003c723  mov     rcx, rax; this
0x18003c726  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c72b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003c72f  test    r9, r9
0x18003c732  jz      short loc_18003C746
0x18003c734  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003c73b  mov     rdx, rsi; unsigned __int16 *
0x18003c73e  mov     rcx, rax; this
0x18003c741  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c746  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003c74a  test    r9, r9
0x18003c74d  jz      short loc_18003C761
0x18003c74f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003c756  mov     rdx, rsi; unsigned __int16 *
0x18003c759  mov     rcx, rax; this
0x18003c75c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c761  mov     rcx, [rbx+28h]
0x18003c765  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003c769  mov     rdx, rsi; unsigned __int16 *
0x18003c76c  test    rcx, rcx
0x18003c76f  jz      short loc_18003C787
0x18003c771  mov     [rsp+278h+lpBuffer], rcx
0x18003c776  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003c77d  mov     rcx, rax; this
0x18003c780  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c785  jmp     short loc_18003C7A9
0x18003c787  mov     rcx, rax; this
0x18003c78a  test    r9, r9
0x18003c78d  jz      short loc_18003C79D
0x18003c78f  lea     r8, aHs; "[%hs]\n"
0x18003c796  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c79b  jmp     short loc_18003C7A9
0x18003c79d  lea     r8, asc_18006E408; "\n"
0x18003c7a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003c7a9  xor     eax, eax
0x18003c7ab  mov     rcx, [rsp+278h+var_38]
0x18003c7b3  xor     rcx, rsp; StackCookie
0x18003c7b6  call    __security_check_cookie
0x18003c7bb  mov     rbx, [rsp+278h+arg_18]
0x18003c7c3  add     rsp, 250h
0x18003c7ca  pop     r15
0x18003c7cc  pop     r14
0x18003c7ce  pop     rdi
0x18003c7cf  pop     rsi
0x18003c7d0  pop     rbp
0x18003c7d1  retn
```
