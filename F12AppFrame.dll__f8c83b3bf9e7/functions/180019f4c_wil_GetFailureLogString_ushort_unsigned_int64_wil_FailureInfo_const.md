# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180019f4c`
- end: `0x18001a202`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800180c0`
- `0x180018330`
- `0x18001ba40`
- `0x18001e250`

## callees

- `0x180001800`
- `0x180002678`
- `0x180019f4c`
- `0x18001bd40`
- `0x180035010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18001a0ff`
- `KERNEL32!GetCurrentThreadId` at `0x18001a0ff`
- `KERNEL32!FormatMessageW` at `0x18001a07e`
- `KERNEL32!FormatMessageW` at `0x18001a07e`

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
          v7 = (const char *)&qword_18003AAF8;
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
0x180019f4c  mov     [rsp+arg_18], rbx
0x180019f51  push    rbp
0x180019f52  push    rsi
0x180019f53  push    rdi
0x180019f54  push    r14
0x180019f56  push    r15
0x180019f58  sub     rsp, 250h
0x180019f5f  mov     rax, cs:__security_cookie
0x180019f66  xor     rax, rsp
0x180019f69  mov     [rsp+278h+var_38], rax
0x180019f71  mov     rbx, r8
0x180019f74  mov     rsi, rdx
0x180019f77  mov     r14, rcx
0x180019f7a  xor     r15d, r15d
0x180019f7d  test    rdx, rdx
0x180019f80  jz      loc_18001A1D9
0x180019f86  test    rcx, rcx
0x180019f89  jz      loc_18001A1D9
0x180019f8f  mov     [rcx], r15w
0x180019f93  mov     rax, cs:g_pfnResultLoggingCallback
0x180019f9a  test    rax, rax
0x180019f9d  jz      short loc_180019FC0
0x180019f9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180019fa6  jz      short loc_180019FC0
0x180019fa8  mov     r8, rdx
0x180019fab  mov     rdx, rcx
0x180019fae  mov     rcx, rbx
0x180019fb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fb6  cmp     [r14], r15w
0x180019fba  jnz     loc_18001A1D9
0x180019fc0  mov     ecx, [rbx]
0x180019fc2  mov     bpl, 8
0x180019fc5  test    ecx, ecx
0x180019fc7  jz      short loc_18001A012
0x180019fc9  sub     ecx, 1
0x180019fcc  jz      short loc_180019FFA
0x180019fce  sub     ecx, 1
0x180019fd1  jz      short loc_180019FEA
0x180019fd3  cmp     ecx, 1
0x180019fd6  jz      short loc_180019FE1
0x180019fd8  lea     rdi, qword_18003AAF8
0x180019fdf  jmp     short loc_18001A019
0x180019fe1  lea     rdi, aFailfast; "FailFast"
0x180019fe8  jmp     short loc_18001A019
0x180019fea  lea     rax, aLoghr; "LogHr"
0x180019ff1  lea     rdi, aLognt; "LogNt"
0x180019ff8  jmp     short loc_18001A008
0x180019ffa  lea     rax, aReturnhr; "ReturnHr"
0x18001a001  lea     rdi, aReturnnt; "ReturnNt"
0x18001a008  test    [rbx+4], bpl
0x18001a00c  cmovz   rdi, rax
0x18001a010  jmp     short loc_18001A019
0x18001a012  lea     rdi, aException; "Exception"
0x18001a019  xor     edx, edx; Val
0x18001a01b  mov     r8d, 200h; Size
0x18001a021  lea     rcx, [rsp+278h+Buffer]; void *
0x18001a026  call    memset_0
0x18001a02b  test    [rbx+4], bpl
0x18001a02f  jz      short loc_18001A054
0x18001a031  mov     ebp, [rbx+0Ch]
0x18001a034  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001a03b  test    rax, rax
0x18001a03e  jz      short loc_18001A084
0x18001a040  mov     r8d, 100h
0x18001a046  lea     rdx, [rsp+278h+Buffer]
0x18001a04b  mov     ecx, ebp
0x18001a04d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a052  jmp     short loc_18001A084
0x18001a054  mov     ebp, [rbx+8]
0x18001a057  mov     [rsp+278h+Arguments], r15; Arguments
0x18001a05c  mov     [rsp+278h+nSize], 100h; nSize
0x18001a064  lea     rax, [rsp+278h+Buffer]
0x18001a069  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001a06e  mov     r9d, 400h; dwLanguageId
0x18001a074  mov     r8d, ebp; dwMessageId
0x18001a077  xor     edx, edx; lpSource
0x18001a079  mov     ecx, 1200h; dwFlags
0x18001a07e  call    cs:__imp_FormatMessageW
0x18001a084  lea     rsi, [r14+rsi*2]
0x18001a088  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001a08c  mov     rax, [rbx+88h]
0x18001a093  mov     rcx, [rbx+80h]
0x18001a09a  mov     rdx, rsi; unsigned __int16 *
0x18001a09d  test    r9, r9
0x18001a0a0  jz      short loc_18001A0C4
0x18001a0a2  mov     [rsp+278h+Arguments], rax
0x18001a0a7  mov     qword ptr [rsp+278h+nSize], rcx
0x18001a0ac  mov     eax, [rbx+40h]
0x18001a0af  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001a0b3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001a0ba  mov     rcx, r14; this
0x18001a0bd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a0c2  jmp     short loc_18001A0DB
0x18001a0c4  mov     [rsp+278h+lpBuffer], rax
0x18001a0c9  mov     r9, rcx; unsigned __int16 *
0x18001a0cc  lea     r8, aHsP; "%hs!%p: "
0x18001a0d3  mov     rcx, r14; this
0x18001a0d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a0db  mov     r14, rax
0x18001a0de  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001a0e5  test    r9, r9
0x18001a0e8  jz      short loc_18001A0FF
0x18001a0ea  lea     r8, aCallerP; "(caller: %p) "
0x18001a0f1  mov     rdx, rsi; unsigned __int16 *
0x18001a0f4  mov     rcx, rax; this
0x18001a0f7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a0fc  mov     r14, rax
0x18001a0ff  call    cs:__imp_GetCurrentThreadId
0x18001a105  lea     rcx, [rsp+278h+Buffer]
0x18001a10a  mov     [rsp+278h+var_240], rcx
0x18001a10f  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001a113  mov     [rsp+278h+nSize], eax
0x18001a117  mov     eax, [rbx+44h]
0x18001a11a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001a11e  mov     r9, rdi; unsigned __int16 *
0x18001a121  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001a128  mov     rdx, rsi; unsigned __int16 *
0x18001a12b  mov     rcx, r14; this
0x18001a12e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a133  cmp     [rbx+18h], r15
0x18001a137  jnz     short loc_18001A149
0x18001a139  cmp     [rbx+48h], r15
0x18001a13d  jnz     short loc_18001A149
0x18001a13f  cmp     [rbx+30h], r15
0x18001a143  jz      loc_18001A1D9
0x18001a149  lea     r8, asc_18003ABE8; "    "
0x18001a150  mov     rdx, rsi; unsigned __int16 *
0x18001a153  mov     rcx, rax; this
0x18001a156  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a15b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001a15f  test    r9, r9
0x18001a162  jz      short loc_18001A176
0x18001a164  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001a16b  mov     rdx, rsi; unsigned __int16 *
0x18001a16e  mov     rcx, rax; this
0x18001a171  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a176  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001a17a  test    r9, r9
0x18001a17d  jz      short loc_18001A191
0x18001a17f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001a186  mov     rdx, rsi; unsigned __int16 *
0x18001a189  mov     rcx, rax; this
0x18001a18c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a191  mov     rcx, [rbx+28h]
0x18001a195  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001a199  mov     rdx, rsi; unsigned __int16 *
0x18001a19c  test    rcx, rcx
0x18001a19f  jz      short loc_18001A1B7
0x18001a1a1  mov     [rsp+278h+lpBuffer], rcx
0x18001a1a6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001a1ad  mov     rcx, rax; this
0x18001a1b0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a1b5  jmp     short loc_18001A1D9
0x18001a1b7  mov     rcx, rax; this
0x18001a1ba  test    r9, r9
0x18001a1bd  jz      short loc_18001A1CD
0x18001a1bf  lea     r8, aHs; "[%hs]\n"
0x18001a1c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a1cb  jmp     short loc_18001A1D9
0x18001a1cd  lea     r8, asc_18003AC60; "\n"
0x18001a1d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001a1d9  xor     eax, eax
0x18001a1db  mov     rcx, [rsp+278h+var_38]
0x18001a1e3  xor     rcx, rsp; StackCookie
0x18001a1e6  call    __security_check_cookie
0x18001a1eb  mov     rbx, [rsp+278h+arg_18]
0x18001a1f3  add     rsp, 250h
0x18001a1fa  pop     r15
0x18001a1fc  pop     r14
0x18001a1fe  pop     rdi
0x18001a1ff  pop     rsi
0x18001a200  pop     rbp
0x18001a201  retn
```
