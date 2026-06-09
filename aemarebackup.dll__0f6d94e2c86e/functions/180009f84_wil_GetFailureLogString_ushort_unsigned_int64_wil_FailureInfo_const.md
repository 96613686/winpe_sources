# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009f84`
- end: `0x18000a23a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x18000793c`
- `0x180007ba4`
- `0x18000acf8`
- `0x18000e780`
- `0x18000f644`
- `0x1800e6a6e`
- `0x1800e6ba2`
- `0x1800e9642`
- `0x1800e98fe`

## callees

- `0x180004ea0`
- `0x180005914`
- `0x180009f84`
- `0x18000aff8`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a137`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a0b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a0b6`

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
          v7 = (const char *)&word_1800F2B62;
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
0x180009f84  mov     [rsp+arg_18], rbx
0x180009f89  push    rbp
0x180009f8a  push    rsi
0x180009f8b  push    rdi
0x180009f8c  push    r14
0x180009f8e  push    r15
0x180009f90  sub     rsp, 250h
0x180009f97  mov     rax, cs:__security_cookie
0x180009f9e  xor     rax, rsp
0x180009fa1  mov     [rsp+278h+var_38], rax
0x180009fa9  mov     rbx, r8
0x180009fac  mov     rsi, rdx
0x180009faf  mov     r14, rcx
0x180009fb2  xor     r15d, r15d
0x180009fb5  test    rdx, rdx
0x180009fb8  jz      loc_18000A211
0x180009fbe  test    rcx, rcx
0x180009fc1  jz      loc_18000A211
0x180009fc7  mov     [rcx], r15w
0x180009fcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180009fd2  test    rax, rax
0x180009fd5  jz      short loc_180009FF8
0x180009fd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009fde  jz      short loc_180009FF8
0x180009fe0  mov     r8, rdx
0x180009fe3  mov     rdx, rcx
0x180009fe6  mov     rcx, rbx
0x180009fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009fee  cmp     [r14], r15w
0x180009ff2  jnz     loc_18000A211
0x180009ff8  mov     ecx, [rbx]
0x180009ffa  mov     bpl, 8
0x180009ffd  test    ecx, ecx
0x180009fff  jz      short loc_18000A04A
0x18000a001  sub     ecx, 1
0x18000a004  jz      short loc_18000A032
0x18000a006  sub     ecx, 1
0x18000a009  jz      short loc_18000A022
0x18000a00b  cmp     ecx, 1
0x18000a00e  jz      short loc_18000A019
0x18000a010  lea     rdi, word_1800F2B62
0x18000a017  jmp     short loc_18000A051
0x18000a019  lea     rdi, aFailfast; "FailFast"
0x18000a020  jmp     short loc_18000A051
0x18000a022  lea     rax, aLoghr; "LogHr"
0x18000a029  lea     rdi, aLognt; "LogNt"
0x18000a030  jmp     short loc_18000A040
0x18000a032  lea     rax, aReturnhr; "ReturnHr"
0x18000a039  lea     rdi, aReturnnt; "ReturnNt"
0x18000a040  test    [rbx+4], bpl
0x18000a044  cmovz   rdi, rax
0x18000a048  jmp     short loc_18000A051
0x18000a04a  lea     rdi, aException; "Exception"
0x18000a051  xor     edx, edx; Val
0x18000a053  mov     r8d, 200h; Size
0x18000a059  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a05e  call    memset_0
0x18000a063  test    [rbx+4], bpl
0x18000a067  jz      short loc_18000A08C
0x18000a069  mov     ebp, [rbx+0Ch]
0x18000a06c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a073  test    rax, rax
0x18000a076  jz      short loc_18000A0BC
0x18000a078  mov     r8d, 100h
0x18000a07e  lea     rdx, [rsp+278h+Buffer]
0x18000a083  mov     ecx, ebp
0x18000a085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a08a  jmp     short loc_18000A0BC
0x18000a08c  mov     ebp, [rbx+8]
0x18000a08f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a094  mov     [rsp+278h+nSize], 100h; nSize
0x18000a09c  lea     rax, [rsp+278h+Buffer]
0x18000a0a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a0a6  mov     r9d, 400h; dwLanguageId
0x18000a0ac  mov     r8d, ebp; dwMessageId
0x18000a0af  xor     edx, edx; lpSource
0x18000a0b1  mov     ecx, 1200h; dwFlags
0x18000a0b6  call    cs:__imp_FormatMessageW
0x18000a0bc  lea     rsi, [r14+rsi*2]
0x18000a0c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a0c4  mov     rax, [rbx+88h]
0x18000a0cb  mov     rcx, [rbx+80h]
0x18000a0d2  mov     rdx, rsi; unsigned __int16 *
0x18000a0d5  test    r9, r9
0x18000a0d8  jz      short loc_18000A0FC
0x18000a0da  mov     [rsp+278h+Arguments], rax
0x18000a0df  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a0e4  mov     eax, [rbx+40h]
0x18000a0e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a0eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a0f2  mov     rcx, r14; this
0x18000a0f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a0fa  jmp     short loc_18000A113
0x18000a0fc  mov     [rsp+278h+lpBuffer], rax
0x18000a101  mov     r9, rcx; unsigned __int16 *
0x18000a104  lea     r8, aHsP; "%hs!%p: "
0x18000a10b  mov     rcx, r14; this
0x18000a10e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a113  mov     r14, rax
0x18000a116  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a11d  test    r9, r9
0x18000a120  jz      short loc_18000A137
0x18000a122  lea     r8, aCallerP; "(caller: %p) "
0x18000a129  mov     rdx, rsi; unsigned __int16 *
0x18000a12c  mov     rcx, rax; this
0x18000a12f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a134  mov     r14, rax
0x18000a137  call    cs:__imp_GetCurrentThreadId
0x18000a13d  lea     rcx, [rsp+278h+Buffer]
0x18000a142  mov     [rsp+278h+var_240], rcx
0x18000a147  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a14b  mov     [rsp+278h+nSize], eax
0x18000a14f  mov     eax, [rbx+44h]
0x18000a152  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a156  mov     r9, rdi; unsigned __int16 *
0x18000a159  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a160  mov     rdx, rsi; unsigned __int16 *
0x18000a163  mov     rcx, r14; this
0x18000a166  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a16b  cmp     [rbx+18h], r15
0x18000a16f  jnz     short loc_18000A181
0x18000a171  cmp     [rbx+48h], r15
0x18000a175  jnz     short loc_18000A181
0x18000a177  cmp     [rbx+30h], r15
0x18000a17b  jz      loc_18000A211
0x18000a181  lea     r8, asc_1800F2C68; "    "
0x18000a188  mov     rdx, rsi; unsigned __int16 *
0x18000a18b  mov     rcx, rax; this
0x18000a18e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a193  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a197  test    r9, r9
0x18000a19a  jz      short loc_18000A1AE
0x18000a19c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a1a3  mov     rdx, rsi; unsigned __int16 *
0x18000a1a6  mov     rcx, rax; this
0x18000a1a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a1ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a1b2  test    r9, r9
0x18000a1b5  jz      short loc_18000A1C9
0x18000a1b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a1be  mov     rdx, rsi; unsigned __int16 *
0x18000a1c1  mov     rcx, rax; this
0x18000a1c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a1c9  mov     rcx, [rbx+28h]
0x18000a1cd  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a1d1  mov     rdx, rsi; unsigned __int16 *
0x18000a1d4  test    rcx, rcx
0x18000a1d7  jz      short loc_18000A1EF
0x18000a1d9  mov     [rsp+278h+lpBuffer], rcx
0x18000a1de  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x18000a1e5  mov     rcx, rax; this
0x18000a1e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a1ed  jmp     short loc_18000A211
0x18000a1ef  mov     rcx, rax; this
0x18000a1f2  test    r9, r9
0x18000a1f5  jz      short loc_18000A205
0x18000a1f7  lea     r8, aHs_0; "[%hs]\n"
0x18000a1fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a203  jmp     short loc_18000A211
0x18000a205  lea     r8, asc_1800F2CE0; "\n"
0x18000a20c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a211  xor     eax, eax
0x18000a213  mov     rcx, [rsp+278h+var_38]
0x18000a21b  xor     rcx, rsp; StackCookie
0x18000a21e  call    __security_check_cookie
0x18000a223  mov     rbx, [rsp+278h+arg_18]
0x18000a22b  add     rsp, 250h
0x18000a232  pop     r15
0x18000a234  pop     r14
0x18000a236  pop     rdi
0x18000a237  pop     rsi
0x18000a238  pop     rbp
0x18000a239  retn
```
