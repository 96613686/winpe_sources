# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180011364`
- end: `0x18001161a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18001030c`
- `0x180011d90`
- `0x180012288`
- `0x180013590`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x180011364`
- `0x180012070`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011517`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011517`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011496`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180011496`

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
          v7 = (const char *)&qword_180092798;
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
0x180011364  mov     [rsp+arg_18], rbx
0x180011369  push    rbp
0x18001136a  push    rsi
0x18001136b  push    rdi
0x18001136c  push    r14
0x18001136e  push    r15
0x180011370  sub     rsp, 250h
0x180011377  mov     rax, cs:__security_cookie
0x18001137e  xor     rax, rsp
0x180011381  mov     [rsp+278h+var_38], rax
0x180011389  mov     rbx, r8
0x18001138c  mov     rsi, rdx
0x18001138f  mov     r14, rcx
0x180011392  xor     r15d, r15d
0x180011395  test    rdx, rdx
0x180011398  jz      loc_1800115F1
0x18001139e  test    rcx, rcx
0x1800113a1  jz      loc_1800115F1
0x1800113a7  mov     [rcx], r15w
0x1800113ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800113b2  test    rax, rax
0x1800113b5  jz      short loc_1800113D8
0x1800113b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800113be  jz      short loc_1800113D8
0x1800113c0  mov     r8, rdx
0x1800113c3  mov     rdx, rcx
0x1800113c6  mov     rcx, rbx
0x1800113c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800113ce  cmp     [r14], r15w
0x1800113d2  jnz     loc_1800115F1
0x1800113d8  mov     ecx, [rbx]
0x1800113da  mov     bpl, 8
0x1800113dd  test    ecx, ecx
0x1800113df  jz      short loc_18001142A
0x1800113e1  sub     ecx, 1
0x1800113e4  jz      short loc_180011412
0x1800113e6  sub     ecx, 1
0x1800113e9  jz      short loc_180011402
0x1800113eb  cmp     ecx, 1
0x1800113ee  jz      short loc_1800113F9
0x1800113f0  lea     rdi, qword_180092798
0x1800113f7  jmp     short loc_180011431
0x1800113f9  lea     rdi, aFailfast; "FailFast"
0x180011400  jmp     short loc_180011431
0x180011402  lea     rax, aLoghr; "LogHr"
0x180011409  lea     rdi, aLognt; "LogNt"
0x180011410  jmp     short loc_180011420
0x180011412  lea     rax, aReturnhr; "ReturnHr"
0x180011419  lea     rdi, aReturnnt; "ReturnNt"
0x180011420  test    [rbx+4], bpl
0x180011424  cmovz   rdi, rax
0x180011428  jmp     short loc_180011431
0x18001142a  lea     rdi, aException; "Exception"
0x180011431  xor     edx, edx; Val
0x180011433  mov     r8d, 200h; Size
0x180011439  lea     rcx, [rsp+278h+Buffer]; void *
0x18001143e  call    memset_0
0x180011443  test    [rbx+4], bpl
0x180011447  jz      short loc_18001146C
0x180011449  mov     ebp, [rbx+0Ch]
0x18001144c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180011453  test    rax, rax
0x180011456  jz      short loc_18001149C
0x180011458  mov     r8d, 100h
0x18001145e  lea     rdx, [rsp+278h+Buffer]
0x180011463  mov     ecx, ebp
0x180011465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001146a  jmp     short loc_18001149C
0x18001146c  mov     ebp, [rbx+8]
0x18001146f  mov     [rsp+278h+Arguments], r15; Arguments
0x180011474  mov     [rsp+278h+nSize], 100h; nSize
0x18001147c  lea     rax, [rsp+278h+Buffer]
0x180011481  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180011486  mov     r9d, 400h; dwLanguageId
0x18001148c  mov     r8d, ebp; dwMessageId
0x18001148f  xor     edx, edx; lpSource
0x180011491  mov     ecx, 1200h; dwFlags
0x180011496  call    cs:__imp_FormatMessageW
0x18001149c  lea     rsi, [r14+rsi*2]
0x1800114a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800114a4  mov     rax, [rbx+88h]
0x1800114ab  mov     rcx, [rbx+80h]
0x1800114b2  mov     rdx, rsi; unsigned __int16 *
0x1800114b5  test    r9, r9
0x1800114b8  jz      short loc_1800114DC
0x1800114ba  mov     [rsp+278h+Arguments], rax
0x1800114bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800114c4  mov     eax, [rbx+40h]
0x1800114c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800114cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800114d2  mov     rcx, r14; this
0x1800114d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800114da  jmp     short loc_1800114F3
0x1800114dc  mov     [rsp+278h+lpBuffer], rax
0x1800114e1  mov     r9, rcx; unsigned __int16 *
0x1800114e4  lea     r8, aHsP; "%hs!%p: "
0x1800114eb  mov     rcx, r14; this
0x1800114ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800114f3  mov     r14, rax
0x1800114f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800114fd  test    r9, r9
0x180011500  jz      short loc_180011517
0x180011502  lea     r8, aCallerP; "(caller: %p) "
0x180011509  mov     rdx, rsi; unsigned __int16 *
0x18001150c  mov     rcx, rax; this
0x18001150f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011514  mov     r14, rax
0x180011517  call    cs:__imp_GetCurrentThreadId
0x18001151d  lea     rcx, [rsp+278h+Buffer]
0x180011522  mov     [rsp+278h+var_240], rcx
0x180011527  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001152b  mov     [rsp+278h+nSize], eax
0x18001152f  mov     eax, [rbx+44h]
0x180011532  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180011536  mov     r9, rdi; unsigned __int16 *
0x180011539  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180011540  mov     rdx, rsi; unsigned __int16 *
0x180011543  mov     rcx, r14; this
0x180011546  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001154b  cmp     [rbx+18h], r15
0x18001154f  jnz     short loc_180011561
0x180011551  cmp     [rbx+48h], r15
0x180011555  jnz     short loc_180011561
0x180011557  cmp     [rbx+30h], r15
0x18001155b  jz      loc_1800115F1
0x180011561  lea     r8, asc_1800928A0; "    "
0x180011568  mov     rdx, rsi; unsigned __int16 *
0x18001156b  mov     rcx, rax; this
0x18001156e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180011573  mov     r9, [rbx+18h]; unsigned __int16 *
0x180011577  test    r9, r9
0x18001157a  jz      short loc_18001158E
0x18001157c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180011583  mov     rdx, rsi; unsigned __int16 *
0x180011586  mov     rcx, rax; this
0x180011589  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001158e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180011592  test    r9, r9
0x180011595  jz      short loc_1800115A9
0x180011597  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001159e  mov     rdx, rsi; unsigned __int16 *
0x1800115a1  mov     rcx, rax; this
0x1800115a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800115a9  mov     rcx, [rbx+28h]
0x1800115ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800115b1  mov     rdx, rsi; unsigned __int16 *
0x1800115b4  test    rcx, rcx
0x1800115b7  jz      short loc_1800115CF
0x1800115b9  mov     [rsp+278h+lpBuffer], rcx
0x1800115be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800115c5  mov     rcx, rax; this
0x1800115c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800115cd  jmp     short loc_1800115F1
0x1800115cf  mov     rcx, rax; this
0x1800115d2  test    r9, r9
0x1800115d5  jz      short loc_1800115E5
0x1800115d7  lea     r8, aHs; "[%hs]\n"
0x1800115de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800115e3  jmp     short loc_1800115F1
0x1800115e5  lea     r8, asc_180092918; "\n"
0x1800115ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800115f1  xor     eax, eax
0x1800115f3  mov     rcx, [rsp+278h+var_38]
0x1800115fb  xor     rcx, rsp; StackCookie
0x1800115fe  call    __security_check_cookie
0x180011603  mov     rbx, [rsp+278h+arg_18]
0x18001160b  add     rsp, 250h
0x180011612  pop     r15
0x180011614  pop     r14
0x180011616  pop     rdi
0x180011617  pop     rsi
0x180011618  pop     rbp
0x180011619  retn
```
