# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003f84`
- end: `0x18000423a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d7c`
- `0x180002fec`
- `0x180003288`

## callees

- `0x180003f84`
- `0x180004984`
- `0x18000c966`
- `0x18000c990`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004137`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004137`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800040b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800040b6`

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
          v8 = (const char *)&word_18000FECE;
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
0x180003f84  mov     [rsp+arg_18], rbx
0x180003f89  push    rbp
0x180003f8a  push    rsi
0x180003f8b  push    rdi
0x180003f8c  push    r14
0x180003f8e  push    r15
0x180003f90  sub     rsp, 250h
0x180003f97  mov     rax, cs:__security_cookie
0x180003f9e  xor     rax, rsp
0x180003fa1  mov     [rsp+278h+var_38], rax
0x180003fa9  xor     r15d, r15d
0x180003fac  mov     rbx, r8
0x180003faf  mov     rsi, rdx
0x180003fb2  mov     r14, rcx
0x180003fb5  test    rdx, rdx
0x180003fb8  jz      loc_180004211
0x180003fbe  test    rcx, rcx
0x180003fc1  jz      loc_180004211
0x180003fc7  mov     rax, cs:g_pfnResultLoggingCallback
0x180003fce  mov     [rcx], r15w
0x180003fd2  test    rax, rax
0x180003fd5  jz      short loc_180003FF8
0x180003fd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003fde  jz      short loc_180003FF8
0x180003fe0  mov     r8, rdx
0x180003fe3  mov     rdx, rcx
0x180003fe6  mov     rcx, rbx
0x180003fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fee  cmp     [r14], r15w
0x180003ff2  jnz     loc_180004211
0x180003ff8  mov     ecx, [rbx]
0x180003ffa  mov     bpl, 8
0x180003ffd  test    ecx, ecx
0x180003fff  jz      short loc_18000404A
0x180004001  sub     ecx, 1
0x180004004  jz      short loc_180004032
0x180004006  sub     ecx, 1
0x180004009  jz      short loc_180004022
0x18000400b  cmp     ecx, 1
0x18000400e  jz      short loc_180004019
0x180004010  lea     rdi, word_18000FECE
0x180004017  jmp     short loc_180004051
0x180004019  lea     rdi, aFailfast; "FailFast"
0x180004020  jmp     short loc_180004051
0x180004022  lea     rax, aLoghr; "LogHr"
0x180004029  lea     rdi, aLognt; "LogNt"
0x180004030  jmp     short loc_180004040
0x180004032  lea     rax, aReturnhr; "ReturnHr"
0x180004039  lea     rdi, aReturnnt; "ReturnNt"
0x180004040  test    [rbx+4], bpl
0x180004044  cmovz   rdi, rax
0x180004048  jmp     short loc_180004051
0x18000404a  lea     rdi, aException; "Exception"
0x180004051  xor     edx, edx; Val
0x180004053  lea     rcx, [rsp+278h+Buffer]; void *
0x180004058  mov     r8d, 200h; Size
0x18000405e  call    memset_0
0x180004063  test    [rbx+4], bpl
0x180004067  jz      short loc_18000408C
0x180004069  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004070  mov     ebp, [rbx+0Ch]
0x180004073  test    rax, rax
0x180004076  jz      short loc_1800040BC
0x180004078  mov     r8d, 100h
0x18000407e  lea     rdx, [rsp+278h+Buffer]
0x180004083  mov     ecx, ebp
0x180004085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000408a  jmp     short loc_1800040BC
0x18000408c  mov     ebp, [rbx+8]
0x18000408f  lea     rax, [rsp+278h+Buffer]
0x180004094  mov     [rsp+278h+Arguments], r15; Arguments
0x180004099  mov     r8d, ebp; dwMessageId
0x18000409c  mov     [rsp+278h+nSize], 100h; nSize
0x1800040a4  mov     r9d, 400h; dwLanguageId
0x1800040aa  xor     edx, edx; lpSource
0x1800040ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800040b1  mov     ecx, 1200h; dwFlags
0x1800040b6  call    cs:__imp_FormatMessageW
0x1800040bc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800040c0  lea     rsi, [r14+rsi*2]
0x1800040c4  mov     rax, [rbx+88h]
0x1800040cb  mov     rdx, rsi; unsigned __int16 *
0x1800040ce  mov     rcx, [rbx+80h]
0x1800040d5  test    r9, r9
0x1800040d8  jz      short loc_1800040FC
0x1800040da  mov     [rsp+278h+Arguments], rax
0x1800040df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800040e6  mov     eax, [rbx+40h]
0x1800040e9  mov     qword ptr [rsp+278h+nSize], rcx
0x1800040ee  mov     rcx, r14; this
0x1800040f1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800040f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800040fa  jmp     short loc_180004113
0x1800040fc  mov     r9, rcx; unsigned __int16 *
0x1800040ff  mov     [rsp+278h+lpBuffer], rax
0x180004104  mov     rcx, r14; this
0x180004107  lea     r8, aHsP; "%hs!%p: "
0x18000410e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004113  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000411a  mov     r14, rax
0x18000411d  test    r9, r9
0x180004120  jz      short loc_180004137
0x180004122  lea     r8, aCallerP; "(caller: %p) "
0x180004129  mov     rdx, rsi; unsigned __int16 *
0x18000412c  mov     rcx, rax; this
0x18000412f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004134  mov     r14, rax
0x180004137  call    cs:__imp_GetCurrentThreadId
0x18000413d  lea     rcx, [rsp+278h+Buffer]
0x180004142  mov     r9, rdi; unsigned __int16 *
0x180004145  mov     [rsp+278h+var_240], rcx
0x18000414a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004151  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004155  mov     rdx, rsi; unsigned __int16 *
0x180004158  mov     [rsp+278h+nSize], eax
0x18000415c  mov     rcx, r14; this
0x18000415f  mov     eax, [rbx+44h]
0x180004162  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004166  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000416b  cmp     [rbx+18h], r15
0x18000416f  jnz     short loc_180004181
0x180004171  cmp     [rbx+48h], r15
0x180004175  jnz     short loc_180004181
0x180004177  cmp     [rbx+30h], r15
0x18000417b  jz      loc_180004211
0x180004181  lea     r8, asc_18000FFB8; "    "
0x180004188  mov     rdx, rsi; unsigned __int16 *
0x18000418b  mov     rcx, rax; this
0x18000418e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004193  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004197  test    r9, r9
0x18000419a  jz      short loc_1800041AE
0x18000419c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800041a3  mov     rdx, rsi; unsigned __int16 *
0x1800041a6  mov     rcx, rax; this
0x1800041a9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041ae  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800041b2  test    r9, r9
0x1800041b5  jz      short loc_1800041C9
0x1800041b7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800041be  mov     rdx, rsi; unsigned __int16 *
0x1800041c1  mov     rcx, rax; this
0x1800041c4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041c9  mov     rcx, [rbx+28h]
0x1800041cd  mov     rdx, rsi; unsigned __int16 *
0x1800041d0  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800041d4  test    rcx, rcx
0x1800041d7  jz      short loc_1800041EF
0x1800041d9  mov     [rsp+278h+lpBuffer], rcx
0x1800041de  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800041e5  mov     rcx, rax; this
0x1800041e8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800041ed  jmp     short loc_180004211
0x1800041ef  mov     rcx, rax; this
0x1800041f2  test    r9, r9
0x1800041f5  jz      short loc_180004205
0x1800041f7  lea     r8, aHs; "[%hs]\n"
0x1800041fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004203  jmp     short loc_180004211
0x180004205  lea     r8, asc_180010030; "\n"
0x18000420c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004211  xor     eax, eax
0x180004213  mov     rcx, [rsp+278h+var_38]
0x18000421b  xor     rcx, rsp; StackCookie
0x18000421e  call    __security_check_cookie
0x180004223  mov     rbx, [rsp+278h+arg_18]
0x18000422b  add     rsp, 250h
0x180004232  pop     r15
0x180004234  pop     r14
0x180004236  pop     rdi
0x180004237  pop     rsi
0x180004238  pop     rbp
0x180004239  retn
```
