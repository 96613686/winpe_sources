# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800048c4`
- end: `0x180004b7a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002970`
- `0x180002bd8`
- `0x180005220`

## callees

- `0x1800018e0`
- `0x1800024d4`
- `0x1800048c4`
- `0x180005520`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004a77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800049f6`

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
          v8 = (const char *)&dword_180028EC4;
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
0x1800048c4  mov     [rsp+arg_18], rbx
0x1800048c9  push    rbp
0x1800048ca  push    rsi
0x1800048cb  push    rdi
0x1800048cc  push    r14
0x1800048ce  push    r15
0x1800048d0  sub     rsp, 250h
0x1800048d7  mov     rax, cs:__security_cookie
0x1800048de  xor     rax, rsp
0x1800048e1  mov     [rsp+278h+var_38], rax
0x1800048e9  xor     r15d, r15d
0x1800048ec  mov     rbx, r8
0x1800048ef  mov     rsi, rdx
0x1800048f2  mov     r14, rcx
0x1800048f5  test    rdx, rdx
0x1800048f8  jz      loc_180004B51
0x1800048fe  test    rcx, rcx
0x180004901  jz      loc_180004B51
0x180004907  mov     rax, cs:g_pfnResultLoggingCallback
0x18000490e  mov     [rcx], r15w
0x180004912  test    rax, rax
0x180004915  jz      short loc_180004938
0x180004917  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000491e  jz      short loc_180004938
0x180004920  mov     r8, rdx
0x180004923  mov     rdx, rcx
0x180004926  mov     rcx, rbx
0x180004929  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000492e  cmp     [r14], r15w
0x180004932  jnz     loc_180004B51
0x180004938  mov     ecx, [rbx]
0x18000493a  mov     bpl, 8
0x18000493d  test    ecx, ecx
0x18000493f  jz      short loc_18000498A
0x180004941  sub     ecx, 1
0x180004944  jz      short loc_180004972
0x180004946  sub     ecx, 1
0x180004949  jz      short loc_180004962
0x18000494b  cmp     ecx, 1
0x18000494e  jz      short loc_180004959
0x180004950  lea     rdi, dword_180028EC4
0x180004957  jmp     short loc_180004991
0x180004959  lea     rdi, aFailfast; "FailFast"
0x180004960  jmp     short loc_180004991
0x180004962  lea     rax, aLoghr; "LogHr"
0x180004969  lea     rdi, aLognt; "LogNt"
0x180004970  jmp     short loc_180004980
0x180004972  lea     rax, aReturnhr; "ReturnHr"
0x180004979  lea     rdi, aReturnnt; "ReturnNt"
0x180004980  test    [rbx+4], bpl
0x180004984  cmovz   rdi, rax
0x180004988  jmp     short loc_180004991
0x18000498a  lea     rdi, aException; "Exception"
0x180004991  xor     edx, edx; Val
0x180004993  lea     rcx, [rsp+278h+Buffer]; void *
0x180004998  mov     r8d, 200h; Size
0x18000499e  call    memset_0
0x1800049a3  test    [rbx+4], bpl
0x1800049a7  jz      short loc_1800049CC
0x1800049a9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800049b0  mov     ebp, [rbx+0Ch]
0x1800049b3  test    rax, rax
0x1800049b6  jz      short loc_1800049FC
0x1800049b8  mov     r8d, 100h
0x1800049be  lea     rdx, [rsp+278h+Buffer]
0x1800049c3  mov     ecx, ebp
0x1800049c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ca  jmp     short loc_1800049FC
0x1800049cc  mov     ebp, [rbx+8]
0x1800049cf  lea     rax, [rsp+278h+Buffer]
0x1800049d4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800049d9  mov     r8d, ebp; dwMessageId
0x1800049dc  mov     [rsp+278h+nSize], 100h; nSize
0x1800049e4  mov     r9d, 400h; dwLanguageId
0x1800049ea  xor     edx, edx; lpSource
0x1800049ec  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800049f1  mov     ecx, 1200h; dwFlags
0x1800049f6  call    cs:__imp_FormatMessageW
0x1800049fc  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004a00  lea     rsi, [r14+rsi*2]
0x180004a04  mov     rax, [rbx+88h]
0x180004a0b  mov     rdx, rsi; unsigned __int16 *
0x180004a0e  mov     rcx, [rbx+80h]
0x180004a15  test    r9, r9
0x180004a18  jz      short loc_180004A3C
0x180004a1a  mov     [rsp+278h+Arguments], rax
0x180004a1f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004a26  mov     eax, [rbx+40h]
0x180004a29  mov     qword ptr [rsp+278h+nSize], rcx
0x180004a2e  mov     rcx, r14; this
0x180004a31  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004a35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a3a  jmp     short loc_180004A53
0x180004a3c  mov     r9, rcx; unsigned __int16 *
0x180004a3f  mov     [rsp+278h+lpBuffer], rax
0x180004a44  mov     rcx, r14; this
0x180004a47  lea     r8, aHsP; "%hs!%p: "
0x180004a4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a53  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004a5a  mov     r14, rax
0x180004a5d  test    r9, r9
0x180004a60  jz      short loc_180004A77
0x180004a62  lea     r8, aCallerP; "(caller: %p) "
0x180004a69  mov     rdx, rsi; unsigned __int16 *
0x180004a6c  mov     rcx, rax; this
0x180004a6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004a74  mov     r14, rax
0x180004a77  call    cs:__imp_GetCurrentThreadId
0x180004a7d  lea     rcx, [rsp+278h+Buffer]
0x180004a82  mov     r9, rdi; unsigned __int16 *
0x180004a85  mov     [rsp+278h+var_240], rcx
0x180004a8a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004a91  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004a95  mov     rdx, rsi; unsigned __int16 *
0x180004a98  mov     [rsp+278h+nSize], eax
0x180004a9c  mov     rcx, r14; this
0x180004a9f  mov     eax, [rbx+44h]
0x180004aa2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004aa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004aab  cmp     [rbx+18h], r15
0x180004aaf  jnz     short loc_180004AC1
0x180004ab1  cmp     [rbx+48h], r15
0x180004ab5  jnz     short loc_180004AC1
0x180004ab7  cmp     [rbx+30h], r15
0x180004abb  jz      loc_180004B51
0x180004ac1  lea     r8, asc_180028FB0; "    "
0x180004ac8  mov     rdx, rsi; unsigned __int16 *
0x180004acb  mov     rcx, rax; this
0x180004ace  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ad3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004ad7  test    r9, r9
0x180004ada  jz      short loc_180004AEE
0x180004adc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004ae3  mov     rdx, rsi; unsigned __int16 *
0x180004ae6  mov     rcx, rax; this
0x180004ae9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004aee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004af2  test    r9, r9
0x180004af5  jz      short loc_180004B09
0x180004af7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004afe  mov     rdx, rsi; unsigned __int16 *
0x180004b01  mov     rcx, rax; this
0x180004b04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b09  mov     rcx, [rbx+28h]
0x180004b0d  mov     rdx, rsi; unsigned __int16 *
0x180004b10  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004b14  test    rcx, rcx
0x180004b17  jz      short loc_180004B2F
0x180004b19  mov     [rsp+278h+lpBuffer], rcx
0x180004b1e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004b25  mov     rcx, rax; this
0x180004b28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b2d  jmp     short loc_180004B51
0x180004b2f  mov     rcx, rax; this
0x180004b32  test    r9, r9
0x180004b35  jz      short loc_180004B45
0x180004b37  lea     r8, aHs; "[%hs]\n"
0x180004b3e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b43  jmp     short loc_180004B51
0x180004b45  lea     r8, asc_180029028; "\n"
0x180004b4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b51  xor     eax, eax
0x180004b53  mov     rcx, [rsp+278h+var_38]
0x180004b5b  xor     rcx, rsp; StackCookie
0x180004b5e  call    __security_check_cookie
0x180004b63  mov     rbx, [rsp+278h+arg_18]
0x180004b6b  add     rsp, 250h
0x180004b72  pop     r15
0x180004b74  pop     r14
0x180004b76  pop     rdi
0x180004b77  pop     rsi
0x180004b78  pop     rbp
0x180004b79  retn
```
