# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180055274`
- end: `0x180055537`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800534c0`
- `0x180055eec`
- `0x1800565e8`
- `0x1800596a0`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x180055274`
- `0x180056200`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005542d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005542d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800553a6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800553a6`

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
          v7 = (const char *)&qword_1800CEFB8;
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
0x180055274  mov     [rsp+arg_18], rbx
0x180055279  push    rbp
0x18005527a  push    rsi
0x18005527b  push    rdi
0x18005527c  push    r14
0x18005527e  push    r15
0x180055280  sub     rsp, 250h
0x180055287  mov     rax, cs:__security_cookie
0x18005528e  xor     rax, rsp
0x180055291  mov     [rsp+278h+var_38], rax
0x180055299  mov     rbx, r8
0x18005529c  mov     rsi, rdx
0x18005529f  mov     r14, rcx
0x1800552a2  xor     r15d, r15d
0x1800552a5  test    rdx, rdx
0x1800552a8  jz      loc_18005550D
0x1800552ae  test    rcx, rcx
0x1800552b1  jz      loc_18005550D
0x1800552b7  mov     [rcx], r15w
0x1800552bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800552c2  test    rax, rax
0x1800552c5  jz      short loc_1800552E8
0x1800552c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800552ce  jz      short loc_1800552E8
0x1800552d0  mov     r8, rdx
0x1800552d3  mov     rdx, rcx
0x1800552d6  mov     rcx, rbx
0x1800552d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552de  cmp     [r14], r15w
0x1800552e2  jnz     loc_18005550D
0x1800552e8  mov     ecx, [rbx]
0x1800552ea  mov     bpl, 8
0x1800552ed  test    ecx, ecx
0x1800552ef  jz      short loc_18005533A
0x1800552f1  sub     ecx, 1
0x1800552f4  jz      short loc_180055322
0x1800552f6  sub     ecx, 1
0x1800552f9  jz      short loc_180055312
0x1800552fb  cmp     ecx, 1
0x1800552fe  jz      short loc_180055309
0x180055300  lea     rdi, qword_1800CEFB8
0x180055307  jmp     short loc_180055341
0x180055309  lea     rdi, aFailfast; "FailFast"
0x180055310  jmp     short loc_180055341
0x180055312  lea     rax, aLoghr; "LogHr"
0x180055319  lea     rdi, aLognt; "LogNt"
0x180055320  jmp     short loc_180055330
0x180055322  lea     rax, aReturnhr; "ReturnHr"
0x180055329  lea     rdi, aReturnnt; "ReturnNt"
0x180055330  test    [rbx+4], bpl
0x180055334  cmovz   rdi, rax
0x180055338  jmp     short loc_180055341
0x18005533a  lea     rdi, aException; "Exception"
0x180055341  xor     edx, edx; Val
0x180055343  mov     r8d, 200h; Size
0x180055349  lea     rcx, [rsp+278h+Buffer]; void *
0x18005534e  call    memset_0
0x180055353  test    [rbx+4], bpl
0x180055357  jz      short loc_18005537C
0x180055359  mov     ebp, [rbx+0Ch]
0x18005535c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180055363  test    rax, rax
0x180055366  jz      short loc_1800553B2
0x180055368  mov     r8d, 100h
0x18005536e  lea     rdx, [rsp+278h+Buffer]
0x180055373  mov     ecx, ebp
0x180055375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005537a  jmp     short loc_1800553B2
0x18005537c  mov     ebp, [rbx+8]
0x18005537f  mov     [rsp+278h+Arguments], r15; Arguments
0x180055384  mov     [rsp+278h+nSize], 100h; nSize
0x18005538c  lea     rax, [rsp+278h+Buffer]
0x180055391  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180055396  mov     r9d, 400h; dwLanguageId
0x18005539c  mov     r8d, ebp; dwMessageId
0x18005539f  xor     edx, edx; lpSource
0x1800553a1  mov     ecx, 1200h; dwFlags
0x1800553a6  call    cs:__imp_FormatMessageW
0x1800553ad  nop     dword ptr [rax+rax+00h]
0x1800553b2  lea     rsi, [r14+rsi*2]
0x1800553b6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800553ba  mov     rax, [rbx+88h]
0x1800553c1  mov     rcx, [rbx+80h]
0x1800553c8  mov     rdx, rsi; unsigned __int16 *
0x1800553cb  test    r9, r9
0x1800553ce  jz      short loc_1800553F2
0x1800553d0  mov     [rsp+278h+Arguments], rax
0x1800553d5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800553da  mov     eax, [rbx+40h]
0x1800553dd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800553e1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800553e8  mov     rcx, r14; this
0x1800553eb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800553f0  jmp     short loc_180055409
0x1800553f2  mov     [rsp+278h+lpBuffer], rax
0x1800553f7  mov     r9, rcx; unsigned __int16 *
0x1800553fa  lea     r8, aHsP; "%hs!%p: "
0x180055401  mov     rcx, r14; this
0x180055404  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180055409  mov     r14, rax
0x18005540c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180055413  test    r9, r9
0x180055416  jz      short loc_18005542D
0x180055418  lea     r8, aCallerP; "(caller: %p) "
0x18005541f  mov     rdx, rsi; unsigned __int16 *
0x180055422  mov     rcx, rax; this
0x180055425  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005542a  mov     r14, rax
0x18005542d  call    cs:__imp_GetCurrentThreadId
0x180055434  nop     dword ptr [rax+rax+00h]
0x180055439  lea     rcx, [rsp+278h+Buffer]
0x18005543e  mov     [rsp+278h+var_240], rcx
0x180055443  mov     dword ptr [rsp+278h+Arguments], ebp
0x180055447  mov     [rsp+278h+nSize], eax
0x18005544b  mov     eax, [rbx+44h]
0x18005544e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180055452  mov     r9, rdi; unsigned __int16 *
0x180055455  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005545c  mov     rdx, rsi; unsigned __int16 *
0x18005545f  mov     rcx, r14; this
0x180055462  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180055467  cmp     [rbx+18h], r15
0x18005546b  jnz     short loc_18005547D
0x18005546d  cmp     [rbx+48h], r15
0x180055471  jnz     short loc_18005547D
0x180055473  cmp     [rbx+30h], r15
0x180055477  jz      loc_18005550D
0x18005547d  lea     r8, asc_1800CF0C0; "    "
0x180055484  mov     rdx, rsi; unsigned __int16 *
0x180055487  mov     rcx, rax; this
0x18005548a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005548f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180055493  test    r9, r9
0x180055496  jz      short loc_1800554AA
0x180055498  lea     r8, aMsgWs; "Msg:[%ws] "
0x18005549f  mov     rdx, rsi; unsigned __int16 *
0x1800554a2  mov     rcx, rax; this
0x1800554a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800554aa  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800554ae  test    r9, r9
0x1800554b1  jz      short loc_1800554C5
0x1800554b3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800554ba  mov     rdx, rsi; unsigned __int16 *
0x1800554bd  mov     rcx, rax; this
0x1800554c0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800554c5  mov     rcx, [rbx+28h]
0x1800554c9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800554cd  mov     rdx, rsi; unsigned __int16 *
0x1800554d0  test    rcx, rcx
0x1800554d3  jz      short loc_1800554EB
0x1800554d5  mov     [rsp+278h+lpBuffer], rcx
0x1800554da  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800554e1  mov     rcx, rax; this
0x1800554e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800554e9  jmp     short loc_18005550D
0x1800554eb  mov     rcx, rax; this
0x1800554ee  test    r9, r9
0x1800554f1  jz      short loc_180055501
0x1800554f3  lea     r8, aHs; "[%hs]\n"
0x1800554fa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800554ff  jmp     short loc_18005550D
0x180055501  lea     r8, asc_1800CF138; "\n"
0x180055508  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005550d  xor     eax, eax
0x18005550f  mov     rcx, [rsp+278h+var_38]
0x180055517  xor     rcx, rsp; StackCookie
0x18005551a  call    __security_check_cookie
0x18005551f  mov     rbx, [rsp+278h+arg_18]
0x180055527  add     rsp, 250h
0x18005552e  pop     r15
0x180055530  pop     r14
0x180055532  pop     rdi
0x180055533  pop     rsi
0x180055534  pop     rbp
0x180055535  retn
```
