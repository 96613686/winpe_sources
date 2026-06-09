# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003f554`
- end: `0x18003f815`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800406b0`
- `0x180040c80`
- `0x18004a534`

## callees

- `0x18003f554`
- `0x18003f954`
- `0x18009e2c2`
- `0x18009e300`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f712`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003f712`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003f691`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003f691`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&qword_1800BF170;
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
                          Buffer,
                          -2);
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
0x18003f554  mov     rax, rsp
0x18003f557  push    rbp
0x18003f558  push    rsi
0x18003f559  push    rdi
0x18003f55a  push    r14
0x18003f55c  push    r15
0x18003f55e  sub     rsp, 260h
0x18003f565  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18003f56e  mov     [rax+20h], rbx
0x18003f572  mov     rax, cs:__security_cookie
0x18003f579  xor     rax, rsp
0x18003f57c  mov     [rsp+288h+var_38], rax
0x18003f584  mov     rbx, r8
0x18003f587  mov     rsi, rdx
0x18003f58a  mov     r14, rcx
0x18003f58d  xor     r15d, r15d
0x18003f590  test    rdx, rdx
0x18003f593  jz      loc_18003F7EC
0x18003f599  test    rcx, rcx
0x18003f59c  jz      loc_18003F7EC
0x18003f5a2  mov     [rcx], r15w
0x18003f5a6  mov     rax, cs:g_pfnResultLoggingCallback
0x18003f5ad  test    rax, rax
0x18003f5b0  jz      short loc_18003F5D3
0x18003f5b2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003f5b9  jz      short loc_18003F5D3
0x18003f5bb  mov     r8, rdx
0x18003f5be  mov     rdx, rcx
0x18003f5c1  mov     rcx, rbx
0x18003f5c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f5c9  cmp     [r14], r15w
0x18003f5cd  jnz     loc_18003F7EC
0x18003f5d3  mov     ecx, [rbx]
0x18003f5d5  mov     bpl, 8
0x18003f5d8  test    ecx, ecx
0x18003f5da  jz      short loc_18003F625
0x18003f5dc  sub     ecx, 1
0x18003f5df  jz      short loc_18003F60D
0x18003f5e1  sub     ecx, 1
0x18003f5e4  jz      short loc_18003F5FD
0x18003f5e6  cmp     ecx, 1
0x18003f5e9  jz      short loc_18003F5F4
0x18003f5eb  lea     rdi, qword_1800BF170
0x18003f5f2  jmp     short loc_18003F62C
0x18003f5f4  lea     rdi, aFailfast; "FailFast"
0x18003f5fb  jmp     short loc_18003F62C
0x18003f5fd  lea     rax, aLoghr; "LogHr"
0x18003f604  lea     rdi, aLognt; "LogNt"
0x18003f60b  jmp     short loc_18003F61B
0x18003f60d  lea     rax, aReturnhr; "ReturnHr"
0x18003f614  lea     rdi, aReturnnt; "ReturnNt"
0x18003f61b  test    [rbx+4], bpl
0x18003f61f  cmovz   rdi, rax
0x18003f623  jmp     short loc_18003F62C
0x18003f625  lea     rdi, aException; "Exception"
0x18003f62c  xor     edx, edx; Val
0x18003f62e  mov     r8d, 200h; Size
0x18003f634  lea     rcx, [rsp+288h+Buffer]; void *
0x18003f639  call    memset_0
0x18003f63e  test    [rbx+4], bpl
0x18003f642  jz      short loc_18003F667
0x18003f644  mov     ebp, [rbx+0Ch]
0x18003f647  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003f64e  test    rax, rax
0x18003f651  jz      short loc_18003F697
0x18003f653  mov     r8d, 100h
0x18003f659  lea     rdx, [rsp+288h+Buffer]
0x18003f65e  mov     ecx, ebp
0x18003f660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003f665  jmp     short loc_18003F697
0x18003f667  mov     ebp, [rbx+8]
0x18003f66a  mov     [rsp+288h+Arguments], r15; Arguments
0x18003f66f  mov     [rsp+288h+nSize], 100h; nSize
0x18003f677  lea     rax, [rsp+288h+Buffer]
0x18003f67c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x18003f681  mov     r9d, 400h; dwLanguageId
0x18003f687  mov     r8d, ebp; dwMessageId
0x18003f68a  xor     edx, edx; lpSource
0x18003f68c  mov     ecx, 1200h; dwFlags
0x18003f691  call    cs:__imp_FormatMessageW
0x18003f697  lea     rsi, [r14+rsi*2]
0x18003f69b  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003f69f  mov     rax, [rbx+88h]
0x18003f6a6  mov     rcx, [rbx+80h]
0x18003f6ad  mov     rdx, rsi; unsigned __int16 *
0x18003f6b0  test    r9, r9
0x18003f6b3  jz      short loc_18003F6D7
0x18003f6b5  mov     [rsp+288h+Arguments], rax
0x18003f6ba  mov     qword ptr [rsp+288h+nSize], rcx
0x18003f6bf  mov     eax, [rbx+40h]
0x18003f6c2  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18003f6c6  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003f6cd  mov     rcx, r14; this
0x18003f6d0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f6d5  jmp     short loc_18003F6EE
0x18003f6d7  mov     [rsp+288h+lpBuffer], rax
0x18003f6dc  mov     r9, rcx; unsigned __int16 *
0x18003f6df  lea     r8, aHsP; "%hs!%p: "
0x18003f6e6  mov     rcx, r14; this
0x18003f6e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f6ee  mov     r14, rax
0x18003f6f1  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003f6f8  test    r9, r9
0x18003f6fb  jz      short loc_18003F712
0x18003f6fd  lea     r8, aCallerP; "(caller: %p) "
0x18003f704  mov     rdx, rsi; unsigned __int16 *
0x18003f707  mov     rcx, rax; this
0x18003f70a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f70f  mov     r14, rax
0x18003f712  call    cs:__imp_GetCurrentThreadId
0x18003f718  lea     rcx, [rsp+288h+Buffer]
0x18003f71d  mov     [rsp+288h+var_250], rcx
0x18003f722  mov     dword ptr [rsp+288h+Arguments], ebp
0x18003f726  mov     [rsp+288h+nSize], eax
0x18003f72a  mov     eax, [rbx+44h]
0x18003f72d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18003f731  mov     r9, rdi; unsigned __int16 *
0x18003f734  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003f73b  mov     rdx, rsi; unsigned __int16 *
0x18003f73e  mov     rcx, r14; this
0x18003f741  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f746  cmp     [rbx+18h], r15
0x18003f74a  jnz     short loc_18003F75C
0x18003f74c  cmp     [rbx+48h], r15
0x18003f750  jnz     short loc_18003F75C
0x18003f752  cmp     [rbx+30h], r15
0x18003f756  jz      loc_18003F7EC
0x18003f75c  lea     r8, asc_1800BF2A8; "    "
0x18003f763  mov     rdx, rsi; unsigned __int16 *
0x18003f766  mov     rcx, rax; this
0x18003f769  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f76e  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003f772  test    r9, r9
0x18003f775  jz      short loc_18003F789
0x18003f777  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003f77e  mov     rdx, rsi; unsigned __int16 *
0x18003f781  mov     rcx, rax; this
0x18003f784  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f789  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003f78d  test    r9, r9
0x18003f790  jz      short loc_18003F7A4
0x18003f792  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003f799  mov     rdx, rsi; unsigned __int16 *
0x18003f79c  mov     rcx, rax; this
0x18003f79f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f7a4  mov     rcx, [rbx+28h]
0x18003f7a8  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003f7ac  mov     rdx, rsi; unsigned __int16 *
0x18003f7af  test    rcx, rcx
0x18003f7b2  jz      short loc_18003F7CA
0x18003f7b4  mov     [rsp+288h+lpBuffer], rcx
0x18003f7b9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003f7c0  mov     rcx, rax; this
0x18003f7c3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f7c8  jmp     short loc_18003F7EC
0x18003f7ca  mov     rcx, rax; this
0x18003f7cd  test    r9, r9
0x18003f7d0  jz      short loc_18003F7E0
0x18003f7d2  lea     r8, aHs; "[%hs]\n"
0x18003f7d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f7de  jmp     short loc_18003F7EC
0x18003f7e0  lea     r8, asc_1800BF320; "\n"
0x18003f7e7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003f7ec  xor     eax, eax
0x18003f7ee  mov     rcx, [rsp+288h+var_38]
0x18003f7f6  xor     rcx, rsp; StackCookie
0x18003f7f9  call    __security_check_cookie
0x18003f7fe  mov     rbx, [rsp+288h+arg_18]
0x18003f806  add     rsp, 260h
0x18003f80d  pop     r15
0x18003f80f  pop     r14
0x18003f811  pop     rdi
0x18003f812  pop     rsi
0x18003f813  pop     rbp
0x18003f814  retn
```
