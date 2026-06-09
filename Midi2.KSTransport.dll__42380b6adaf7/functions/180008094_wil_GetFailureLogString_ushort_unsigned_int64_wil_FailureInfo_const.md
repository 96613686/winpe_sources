# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008094`
- end: `0x18000834a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x18000580c`
- `0x180005a7c`
- `0x180008b80`
- `0x18000bd00`
- `0x18000bf64`

## callees

- `0x180004410`
- `0x18000526c`
- `0x180008094`
- `0x180008e8c`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008247`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008247`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800081c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800081c6`

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
          v7 = (const char *)&Src;
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
0x180008094  mov     [rsp+arg_18], rbx
0x180008099  push    rbp
0x18000809a  push    rsi
0x18000809b  push    rdi
0x18000809c  push    r14
0x18000809e  push    r15
0x1800080a0  sub     rsp, 250h
0x1800080a7  mov     rax, cs:__security_cookie
0x1800080ae  xor     rax, rsp
0x1800080b1  mov     [rsp+278h+var_38], rax
0x1800080b9  mov     rbx, r8
0x1800080bc  mov     rsi, rdx
0x1800080bf  mov     r14, rcx
0x1800080c2  xor     r15d, r15d
0x1800080c5  test    rdx, rdx
0x1800080c8  jz      loc_180008321
0x1800080ce  test    rcx, rcx
0x1800080d1  jz      loc_180008321
0x1800080d7  mov     [rcx], r15w
0x1800080db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080e2  test    rax, rax
0x1800080e5  jz      short loc_180008108
0x1800080e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800080ee  jz      short loc_180008108
0x1800080f0  mov     r8, rdx
0x1800080f3  mov     rdx, rcx
0x1800080f6  mov     rcx, rbx
0x1800080f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080fe  cmp     [r14], r15w
0x180008102  jnz     loc_180008321
0x180008108  mov     ecx, [rbx]
0x18000810a  mov     bpl, 8
0x18000810d  test    ecx, ecx
0x18000810f  jz      short loc_18000815A
0x180008111  sub     ecx, 1
0x180008114  jz      short loc_180008142
0x180008116  sub     ecx, 1
0x180008119  jz      short loc_180008132
0x18000811b  cmp     ecx, 1
0x18000811e  jz      short loc_180008129
0x180008120  lea     rdi, Src
0x180008127  jmp     short loc_180008161
0x180008129  lea     rdi, aFailfast; "FailFast"
0x180008130  jmp     short loc_180008161
0x180008132  lea     rax, aLoghr; "LogHr"
0x180008139  lea     rdi, aLognt; "LogNt"
0x180008140  jmp     short loc_180008150
0x180008142  lea     rax, aReturnhr; "ReturnHr"
0x180008149  lea     rdi, aReturnnt; "ReturnNt"
0x180008150  test    [rbx+4], bpl
0x180008154  cmovz   rdi, rax
0x180008158  jmp     short loc_180008161
0x18000815a  lea     rdi, aException; "Exception"
0x180008161  xor     edx, edx; Val
0x180008163  mov     r8d, 200h; Size
0x180008169  lea     rcx, [rsp+278h+Buffer]; void *
0x18000816e  call    memset_0
0x180008173  test    [rbx+4], bpl
0x180008177  jz      short loc_18000819C
0x180008179  mov     ebp, [rbx+0Ch]
0x18000817c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008183  test    rax, rax
0x180008186  jz      short loc_1800081CC
0x180008188  mov     r8d, 100h
0x18000818e  lea     rdx, [rsp+278h+Buffer]
0x180008193  mov     ecx, ebp
0x180008195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000819a  jmp     short loc_1800081CC
0x18000819c  mov     ebp, [rbx+8]
0x18000819f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800081a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800081ac  lea     rax, [rsp+278h+Buffer]
0x1800081b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800081b6  mov     r9d, 400h; dwLanguageId
0x1800081bc  mov     r8d, ebp; dwMessageId
0x1800081bf  xor     edx, edx; lpSource
0x1800081c1  mov     ecx, 1200h; dwFlags
0x1800081c6  call    cs:__imp_FormatMessageW
0x1800081cc  lea     rsi, [r14+rsi*2]
0x1800081d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800081d4  mov     rax, [rbx+88h]
0x1800081db  mov     rcx, [rbx+80h]
0x1800081e2  mov     rdx, rsi; unsigned __int16 *
0x1800081e5  test    r9, r9
0x1800081e8  jz      short loc_18000820C
0x1800081ea  mov     [rsp+278h+Arguments], rax
0x1800081ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800081f4  mov     eax, [rbx+40h]
0x1800081f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800081fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008202  mov     rcx, r14; this
0x180008205  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000820a  jmp     short loc_180008223
0x18000820c  mov     [rsp+278h+lpBuffer], rax
0x180008211  mov     r9, rcx; unsigned __int16 *
0x180008214  lea     r8, aHsP; "%hs!%p: "
0x18000821b  mov     rcx, r14; this
0x18000821e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008223  mov     r14, rax
0x180008226  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000822d  test    r9, r9
0x180008230  jz      short loc_180008247
0x180008232  lea     r8, aCallerP; "(caller: %p) "
0x180008239  mov     rdx, rsi; unsigned __int16 *
0x18000823c  mov     rcx, rax; this
0x18000823f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008244  mov     r14, rax
0x180008247  call    cs:__imp_GetCurrentThreadId
0x18000824d  lea     rcx, [rsp+278h+Buffer]
0x180008252  mov     [rsp+278h+var_240], rcx
0x180008257  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000825b  mov     [rsp+278h+nSize], eax
0x18000825f  mov     eax, [rbx+44h]
0x180008262  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008266  mov     r9, rdi; unsigned __int16 *
0x180008269  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008270  mov     rdx, rsi; unsigned __int16 *
0x180008273  mov     rcx, r14; this
0x180008276  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000827b  cmp     [rbx+18h], r15
0x18000827f  jnz     short loc_180008291
0x180008281  cmp     [rbx+48h], r15
0x180008285  jnz     short loc_180008291
0x180008287  cmp     [rbx+30h], r15
0x18000828b  jz      loc_180008321
0x180008291  lea     r8, asc_180060FA8; "    "
0x180008298  mov     rdx, rsi; unsigned __int16 *
0x18000829b  mov     rcx, rax; this
0x18000829e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800082a7  test    r9, r9
0x1800082aa  jz      short loc_1800082BE
0x1800082ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800082b3  mov     rdx, rsi; unsigned __int16 *
0x1800082b6  mov     rcx, rax; this
0x1800082b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800082c2  test    r9, r9
0x1800082c5  jz      short loc_1800082D9
0x1800082c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800082ce  mov     rdx, rsi; unsigned __int16 *
0x1800082d1  mov     rcx, rax; this
0x1800082d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082d9  mov     rcx, [rbx+28h]
0x1800082dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800082e1  mov     rdx, rsi; unsigned __int16 *
0x1800082e4  test    rcx, rcx
0x1800082e7  jz      short loc_1800082FF
0x1800082e9  mov     [rsp+278h+lpBuffer], rcx
0x1800082ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800082f5  mov     rcx, rax; this
0x1800082f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800082fd  jmp     short loc_180008321
0x1800082ff  mov     rcx, rax; this
0x180008302  test    r9, r9
0x180008305  jz      short loc_180008315
0x180008307  lea     r8, aHs; "[%hs]\n"
0x18000830e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008313  jmp     short loc_180008321
0x180008315  lea     r8, asc_180061020; "\n"
0x18000831c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008321  xor     eax, eax
0x180008323  mov     rcx, [rsp+278h+var_38]
0x18000832b  xor     rcx, rsp; StackCookie
0x18000832e  call    __security_check_cookie
0x180008333  mov     rbx, [rsp+278h+arg_18]
0x18000833b  add     rsp, 250h
0x180008342  pop     r15
0x180008344  pop     r14
0x180008346  pop     rdi
0x180008347  pop     rsi
0x180008348  pop     rbp
0x180008349  retn
```
