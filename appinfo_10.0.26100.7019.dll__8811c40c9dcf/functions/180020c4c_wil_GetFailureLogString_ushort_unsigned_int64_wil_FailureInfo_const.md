# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180020c4c`
- end: `0x180020f0d`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180011894`

## callees

- `0x180020c4c`
- `0x18002139c`
- `0x18004292a`
- `0x180042950`
- `0x180043010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020e03`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020d7c`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180020d7c`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rsi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rdi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v8 = (const char *)&word_180048468;
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        goto LABEL_17;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_17;
  }
  v8 = "Exception";
LABEL_17:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180020c4c  mov     [rsp+arg_18], rbx
0x180020c51  push    rbp
0x180020c52  push    rsi
0x180020c53  push    rdi
0x180020c54  push    r14
0x180020c56  push    r15
0x180020c58  sub     rsp, 250h
0x180020c5f  mov     rax, cs:__security_cookie
0x180020c66  xor     rax, rsp
0x180020c69  mov     [rsp+278h+var_38], rax
0x180020c71  xor     r15d, r15d
0x180020c74  mov     rbx, r8
0x180020c77  mov     rdi, rdx
0x180020c7a  mov     r14, rcx
0x180020c7d  test    rdx, rdx
0x180020c80  jz      loc_180020EE3
0x180020c86  test    rcx, rcx
0x180020c89  jz      loc_180020EE3
0x180020c8f  mov     rax, cs:g_pfnResultLoggingCallback
0x180020c96  mov     [rcx], r15w
0x180020c9a  test    rax, rax
0x180020c9d  jz      short loc_180020CC0
0x180020c9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180020ca6  jz      short loc_180020CC0
0x180020ca8  mov     r8, rdx
0x180020cab  mov     rdx, rcx
0x180020cae  mov     rcx, rbx
0x180020cb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020cb6  cmp     [r14], r15w
0x180020cba  jnz     loc_180020EE3
0x180020cc0  mov     ecx, [rbx]
0x180020cc2  lea     rsi, word_180048468
0x180020cc9  mov     bpl, 8
0x180020ccc  test    ecx, ecx
0x180020cce  jz      short loc_180020D10
0x180020cd0  sub     ecx, 1
0x180020cd3  jz      short loc_180020CF8
0x180020cd5  sub     ecx, 1
0x180020cd8  jz      short loc_180020CE8
0x180020cda  cmp     ecx, 1
0x180020cdd  jnz     short loc_180020D17
0x180020cdf  lea     rsi, aFailfast; "FailFast"
0x180020ce6  jmp     short loc_180020D17
0x180020ce8  lea     rax, aLoghr; "LogHr"
0x180020cef  lea     rsi, aLognt; "LogNt"
0x180020cf6  jmp     short loc_180020D06
0x180020cf8  lea     rax, aReturnhr; "ReturnHr"
0x180020cff  lea     rsi, aReturnnt; "ReturnNt"
0x180020d06  test    [rbx+4], bpl
0x180020d0a  cmovz   rsi, rax
0x180020d0e  jmp     short loc_180020D17
0x180020d10  lea     rsi, aException; "Exception"
0x180020d17  xor     edx, edx; Val
0x180020d19  lea     rcx, [rsp+278h+Buffer]; void *
0x180020d1e  mov     r8d, 200h; Size
0x180020d24  call    memset_0
0x180020d29  test    [rbx+4], bpl
0x180020d2d  jz      short loc_180020D52
0x180020d2f  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180020d36  mov     ebp, [rbx+0Ch]
0x180020d39  test    rax, rax
0x180020d3c  jz      short loc_180020D88
0x180020d3e  mov     r8d, 100h
0x180020d44  lea     rdx, [rsp+278h+Buffer]
0x180020d49  mov     ecx, ebp
0x180020d4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020d50  jmp     short loc_180020D88
0x180020d52  mov     ebp, [rbx+8]
0x180020d55  lea     rax, [rsp+278h+Buffer]
0x180020d5a  mov     [rsp+278h+Arguments], r15; Arguments
0x180020d5f  mov     r8d, ebp; dwMessageId
0x180020d62  mov     [rsp+278h+nSize], 100h; nSize
0x180020d6a  mov     r9d, 400h; dwLanguageId
0x180020d70  xor     edx, edx; lpSource
0x180020d72  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180020d77  mov     ecx, 1200h; dwFlags
0x180020d7c  call    cs:__imp_FormatMessageW
0x180020d83  nop     dword ptr [rax+rax+00h]
0x180020d88  mov     r9, [rbx+38h]; unsigned __int16 *
0x180020d8c  lea     rdi, [r14+rdi*2]
0x180020d90  mov     rax, [rbx+88h]
0x180020d97  mov     rdx, rdi; unsigned __int16 *
0x180020d9a  mov     rcx, [rbx+80h]
0x180020da1  test    r9, r9
0x180020da4  jz      short loc_180020DC8
0x180020da6  mov     [rsp+278h+Arguments], rax
0x180020dab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180020db2  mov     eax, [rbx+40h]
0x180020db5  mov     qword ptr [rsp+278h+nSize], rcx
0x180020dba  mov     rcx, r14; this
0x180020dbd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180020dc1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020dc6  jmp     short loc_180020DDF
0x180020dc8  mov     r9, rcx; unsigned __int16 *
0x180020dcb  mov     [rsp+278h+lpBuffer], rax
0x180020dd0  mov     rcx, r14; this
0x180020dd3  lea     r8, aHsP; "%hs!%p: "
0x180020dda  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020ddf  mov     r9, [rbx+90h]; unsigned __int16 *
0x180020de6  mov     r14, rax
0x180020de9  test    r9, r9
0x180020dec  jz      short loc_180020E03
0x180020dee  lea     r8, aCallerP; "(caller: %p) "
0x180020df5  mov     rdx, rdi; unsigned __int16 *
0x180020df8  mov     rcx, rax; this
0x180020dfb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020e00  mov     r14, rax
0x180020e03  call    cs:__imp_GetCurrentThreadId
0x180020e0a  nop     dword ptr [rax+rax+00h]
0x180020e0f  mov     ecx, [rbx+44h]
0x180020e12  lea     rdx, [rsp+278h+Buffer]
0x180020e17  mov     [rsp+278h+var_240], rdx
0x180020e1c  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180020e23  mov     dword ptr [rsp+278h+Arguments], ebp
0x180020e27  mov     r9, rsi; unsigned __int16 *
0x180020e2a  mov     [rsp+278h+nSize], eax
0x180020e2e  mov     rdx, rdi; unsigned __int16 *
0x180020e31  mov     dword ptr [rsp+278h+lpBuffer], ecx
0x180020e35  mov     rcx, r14; this
0x180020e38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020e3d  cmp     [rbx+18h], r15
0x180020e41  jnz     short loc_180020E53
0x180020e43  cmp     [rbx+48h], r15
0x180020e47  jnz     short loc_180020E53
0x180020e49  cmp     [rbx+30h], r15
0x180020e4d  jz      loc_180020EE3
0x180020e53  lea     r8, asc_18004A338; "    "
0x180020e5a  mov     rdx, rdi; unsigned __int16 *
0x180020e5d  mov     rcx, rax; this
0x180020e60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020e65  mov     r9, [rbx+18h]; unsigned __int16 *
0x180020e69  test    r9, r9
0x180020e6c  jz      short loc_180020E80
0x180020e6e  lea     r8, aMsgWs; "Msg:[%ws] "
0x180020e75  mov     rdx, rdi; unsigned __int16 *
0x180020e78  mov     rcx, rax; this
0x180020e7b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020e80  mov     r9, [rbx+48h]; unsigned __int16 *
0x180020e84  test    r9, r9
0x180020e87  jz      short loc_180020E9B
0x180020e89  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180020e90  mov     rdx, rdi; unsigned __int16 *
0x180020e93  mov     rcx, rax; this
0x180020e96  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020e9b  mov     rcx, [rbx+28h]
0x180020e9f  mov     rdx, rdi; unsigned __int16 *
0x180020ea2  mov     r9, [rbx+30h]; unsigned __int16 *
0x180020ea6  test    rcx, rcx
0x180020ea9  jz      short loc_180020EC1
0x180020eab  mov     [rsp+278h+lpBuffer], rcx
0x180020eb0  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180020eb7  mov     rcx, rax; this
0x180020eba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020ebf  jmp     short loc_180020EE3
0x180020ec1  mov     rcx, rax; this
0x180020ec4  test    r9, r9
0x180020ec7  jz      short loc_180020ED7
0x180020ec9  lea     r8, aHs; "[%hs]\n"
0x180020ed0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020ed5  jmp     short loc_180020EE3
0x180020ed7  lea     r8, asc_18004A3B0; "\n"
0x180020ede  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180020ee3  xor     eax, eax
0x180020ee5  mov     rcx, [rsp+278h+var_38]
0x180020eed  xor     rcx, rsp; StackCookie
0x180020ef0  call    __security_check_cookie
0x180020ef5  mov     rbx, [rsp+278h+arg_18]
0x180020efd  add     rsp, 250h
0x180020f04  pop     r15
0x180020f06  pop     r14
0x180020f08  pop     rdi
0x180020f09  pop     rsi
0x180020f0a  pop     rbp
0x180020f0b  retn
```
