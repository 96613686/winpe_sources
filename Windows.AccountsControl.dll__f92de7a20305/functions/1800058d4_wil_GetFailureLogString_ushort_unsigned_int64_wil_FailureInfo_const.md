# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800058d4`
- end: `0x180005b8a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004814`
- `0x1800063a8`
- `0x180035740`
- `0x180035d40`

## callees

- `0x1800058d4`
- `0x1800066a8`
- `0x1800696f2`
- `0x180069730`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a87`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005a06`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005a06`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
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
        else
          v8 = (const char *)&dword_18008CC8C;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
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
0x1800058d4  mov     [rsp+arg_18], rbx
0x1800058d9  push    rbp
0x1800058da  push    rsi
0x1800058db  push    rdi
0x1800058dc  push    r14
0x1800058de  push    r15
0x1800058e0  sub     rsp, 250h
0x1800058e7  mov     rax, cs:__security_cookie
0x1800058ee  xor     rax, rsp
0x1800058f1  mov     [rsp+278h+var_38], rax
0x1800058f9  xor     r15d, r15d
0x1800058fc  mov     rbx, r8
0x1800058ff  mov     rsi, rdx
0x180005902  mov     r14, rcx
0x180005905  test    rdx, rdx
0x180005908  jz      loc_180005B61
0x18000590e  test    rcx, rcx
0x180005911  jz      loc_180005B61
0x180005917  mov     rax, cs:g_pfnResultLoggingCallback
0x18000591e  mov     [rcx], r15w
0x180005922  test    rax, rax
0x180005925  jz      short loc_180005948
0x180005927  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000592e  jz      short loc_180005948
0x180005930  mov     r8, rdx
0x180005933  mov     rdx, rcx
0x180005936  mov     rcx, rbx
0x180005939  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000593e  cmp     [r14], r15w
0x180005942  jnz     loc_180005B61
0x180005948  mov     ecx, [rbx]
0x18000594a  mov     bpl, 8
0x18000594d  test    ecx, ecx
0x18000594f  jz      short loc_18000599A
0x180005951  sub     ecx, 1
0x180005954  jz      short loc_180005982
0x180005956  sub     ecx, 1
0x180005959  jz      short loc_180005972
0x18000595b  cmp     ecx, 1
0x18000595e  jz      short loc_180005969
0x180005960  lea     rdi, dword_18008CC8C
0x180005967  jmp     short loc_1800059A1
0x180005969  lea     rdi, aFailfast; "FailFast"
0x180005970  jmp     short loc_1800059A1
0x180005972  lea     rax, aLoghr; "LogHr"
0x180005979  lea     rdi, aLognt; "LogNt"
0x180005980  jmp     short loc_180005990
0x180005982  lea     rax, aReturnhr; "ReturnHr"
0x180005989  lea     rdi, aReturnnt; "ReturnNt"
0x180005990  test    [rbx+4], bpl
0x180005994  cmovz   rdi, rax
0x180005998  jmp     short loc_1800059A1
0x18000599a  lea     rdi, aException; "Exception"
0x1800059a1  xor     edx, edx; Val
0x1800059a3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800059a8  mov     r8d, 200h; Size
0x1800059ae  call    memset_0
0x1800059b3  test    [rbx+4], bpl
0x1800059b7  jz      short loc_1800059DC
0x1800059b9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800059c0  mov     ebp, [rbx+0Ch]
0x1800059c3  test    rax, rax
0x1800059c6  jz      short loc_180005A0C
0x1800059c8  mov     r8d, 100h
0x1800059ce  lea     rdx, [rsp+278h+Buffer]
0x1800059d3  mov     ecx, ebp
0x1800059d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059da  jmp     short loc_180005A0C
0x1800059dc  mov     ebp, [rbx+8]
0x1800059df  lea     rax, [rsp+278h+Buffer]
0x1800059e4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800059e9  mov     r8d, ebp; dwMessageId
0x1800059ec  mov     [rsp+278h+nSize], 100h; nSize
0x1800059f4  mov     r9d, 400h; dwLanguageId
0x1800059fa  xor     edx, edx; lpSource
0x1800059fc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005a01  mov     ecx, 1200h; dwFlags
0x180005a06  call    cs:__imp_FormatMessageW
0x180005a0c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005a10  lea     rsi, [r14+rsi*2]
0x180005a14  mov     rax, [rbx+88h]
0x180005a1b  mov     rdx, rsi; unsigned __int16 *
0x180005a1e  mov     rcx, [rbx+80h]
0x180005a25  test    r9, r9
0x180005a28  jz      short loc_180005A4C
0x180005a2a  mov     [rsp+278h+Arguments], rax
0x180005a2f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005a36  mov     eax, [rbx+40h]
0x180005a39  mov     qword ptr [rsp+278h+nSize], rcx
0x180005a3e  mov     rcx, r14; this
0x180005a41  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005a45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a4a  jmp     short loc_180005A63
0x180005a4c  mov     r9, rcx; unsigned __int16 *
0x180005a4f  mov     [rsp+278h+lpBuffer], rax
0x180005a54  mov     rcx, r14; this
0x180005a57  lea     r8, aHsP; "%hs!%p: "
0x180005a5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a63  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005a6a  mov     r14, rax
0x180005a6d  test    r9, r9
0x180005a70  jz      short loc_180005A87
0x180005a72  lea     r8, aCallerP; "(caller: %p) "
0x180005a79  mov     rdx, rsi; unsigned __int16 *
0x180005a7c  mov     rcx, rax; this
0x180005a7f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005a84  mov     r14, rax
0x180005a87  call    cs:__imp_GetCurrentThreadId
0x180005a8d  lea     rcx, [rsp+278h+Buffer]
0x180005a92  mov     r9, rdi; unsigned __int16 *
0x180005a95  mov     [rsp+278h+var_240], rcx
0x180005a9a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005aa1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005aa5  mov     rdx, rsi; unsigned __int16 *
0x180005aa8  mov     [rsp+278h+nSize], eax
0x180005aac  mov     rcx, r14; this
0x180005aaf  mov     eax, [rbx+44h]
0x180005ab2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005ab6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005abb  cmp     [rbx+18h], r15
0x180005abf  jnz     short loc_180005AD1
0x180005ac1  cmp     [rbx+48h], r15
0x180005ac5  jnz     short loc_180005AD1
0x180005ac7  cmp     [rbx+30h], r15
0x180005acb  jz      loc_180005B61
0x180005ad1  lea     r8, asc_18008CD80; "    "
0x180005ad8  mov     rdx, rsi; unsigned __int16 *
0x180005adb  mov     rcx, rax; this
0x180005ade  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ae3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005ae7  test    r9, r9
0x180005aea  jz      short loc_180005AFE
0x180005aec  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005af3  mov     rdx, rsi; unsigned __int16 *
0x180005af6  mov     rcx, rax; this
0x180005af9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005afe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005b02  test    r9, r9
0x180005b05  jz      short loc_180005B19
0x180005b07  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005b0e  mov     rdx, rsi; unsigned __int16 *
0x180005b11  mov     rcx, rax; this
0x180005b14  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b19  mov     rcx, [rbx+28h]
0x180005b1d  mov     rdx, rsi; unsigned __int16 *
0x180005b20  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005b24  test    rcx, rcx
0x180005b27  jz      short loc_180005B3F
0x180005b29  mov     [rsp+278h+lpBuffer], rcx
0x180005b2e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005b35  mov     rcx, rax; this
0x180005b38  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b3d  jmp     short loc_180005B61
0x180005b3f  mov     rcx, rax; this
0x180005b42  test    r9, r9
0x180005b45  jz      short loc_180005B55
0x180005b47  lea     r8, aHs; "[%hs]\n"
0x180005b4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b53  jmp     short loc_180005B61
0x180005b55  lea     r8, asc_18008CDF8; "\n"
0x180005b5c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005b61  xor     eax, eax
0x180005b63  mov     rcx, [rsp+278h+var_38]
0x180005b6b  xor     rcx, rsp; StackCookie
0x180005b6e  call    __security_check_cookie
0x180005b73  mov     rbx, [rsp+278h+arg_18]
0x180005b7b  add     rsp, 250h
0x180005b82  pop     r15
0x180005b84  pop     r14
0x180005b86  pop     rdi
0x180005b87  pop     rsi
0x180005b88  pop     rbp
0x180005b89  retn
```
