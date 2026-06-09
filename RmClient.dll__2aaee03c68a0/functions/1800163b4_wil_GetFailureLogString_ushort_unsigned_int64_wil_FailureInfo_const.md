# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800163b4`
- end: `0x18001666a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180012cf0`

## callees

- `0x1800163b4`
- `0x1800169a0`
- `0x18001ae8e`
- `0x18001aec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016567`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016567`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800164e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800164e6`

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
          v8 = (const char *)&qword_1800237D8;
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
0x1800163b4  mov     [rsp+arg_18], rbx
0x1800163b9  push    rbp
0x1800163ba  push    rsi
0x1800163bb  push    rdi
0x1800163bc  push    r14
0x1800163be  push    r15
0x1800163c0  sub     rsp, 250h
0x1800163c7  mov     rax, cs:__security_cookie
0x1800163ce  xor     rax, rsp
0x1800163d1  mov     [rsp+278h+var_38], rax
0x1800163d9  xor     r15d, r15d
0x1800163dc  mov     rbx, r8
0x1800163df  mov     rsi, rdx
0x1800163e2  mov     r14, rcx
0x1800163e5  test    rdx, rdx
0x1800163e8  jz      loc_180016641
0x1800163ee  test    rcx, rcx
0x1800163f1  jz      loc_180016641
0x1800163f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800163fe  mov     [rcx], r15w
0x180016402  test    rax, rax
0x180016405  jz      short loc_180016428
0x180016407  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001640e  jz      short loc_180016428
0x180016410  mov     r8, rdx
0x180016413  mov     rdx, rcx
0x180016416  mov     rcx, rbx
0x180016419  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001641e  cmp     [r14], r15w
0x180016422  jnz     loc_180016641
0x180016428  mov     ecx, [rbx]
0x18001642a  mov     bpl, 8
0x18001642d  test    ecx, ecx
0x18001642f  jz      short loc_18001647A
0x180016431  sub     ecx, 1
0x180016434  jz      short loc_180016462
0x180016436  sub     ecx, 1
0x180016439  jz      short loc_180016452
0x18001643b  cmp     ecx, 1
0x18001643e  jz      short loc_180016449
0x180016440  lea     rdi, qword_1800237D8
0x180016447  jmp     short loc_180016481
0x180016449  lea     rdi, aFailfast; "FailFast"
0x180016450  jmp     short loc_180016481
0x180016452  lea     rax, aLoghr; "LogHr"
0x180016459  lea     rdi, aLognt; "LogNt"
0x180016460  jmp     short loc_180016470
0x180016462  lea     rax, aReturnhr; "ReturnHr"
0x180016469  lea     rdi, aReturnnt; "ReturnNt"
0x180016470  test    [rbx+4], bpl
0x180016474  cmovz   rdi, rax
0x180016478  jmp     short loc_180016481
0x18001647a  lea     rdi, aException; "Exception"
0x180016481  xor     edx, edx; Val
0x180016483  lea     rcx, [rsp+278h+Buffer]; void *
0x180016488  mov     r8d, 200h; Size
0x18001648e  call    memset_0
0x180016493  test    [rbx+4], bpl
0x180016497  jz      short loc_1800164BC
0x180016499  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800164a0  mov     ebp, [rbx+0Ch]
0x1800164a3  test    rax, rax
0x1800164a6  jz      short loc_1800164EC
0x1800164a8  mov     r8d, 100h
0x1800164ae  lea     rdx, [rsp+278h+Buffer]
0x1800164b3  mov     ecx, ebp
0x1800164b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800164ba  jmp     short loc_1800164EC
0x1800164bc  mov     ebp, [rbx+8]
0x1800164bf  lea     rax, [rsp+278h+Buffer]
0x1800164c4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800164c9  mov     r8d, ebp; dwMessageId
0x1800164cc  mov     [rsp+278h+nSize], 100h; nSize
0x1800164d4  mov     r9d, 400h; dwLanguageId
0x1800164da  xor     edx, edx; lpSource
0x1800164dc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800164e1  mov     ecx, 1200h; dwFlags
0x1800164e6  call    cs:__imp_FormatMessageW
0x1800164ec  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800164f0  lea     rsi, [r14+rsi*2]
0x1800164f4  mov     rax, [rbx+88h]
0x1800164fb  mov     rdx, rsi; unsigned __int16 *
0x1800164fe  mov     rcx, [rbx+80h]
0x180016505  test    r9, r9
0x180016508  jz      short loc_18001652C
0x18001650a  mov     [rsp+278h+Arguments], rax
0x18001650f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180016516  mov     eax, [rbx+40h]
0x180016519  mov     qword ptr [rsp+278h+nSize], rcx
0x18001651e  mov     rcx, r14; this
0x180016521  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180016525  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001652a  jmp     short loc_180016543
0x18001652c  mov     r9, rcx; unsigned __int16 *
0x18001652f  mov     [rsp+278h+lpBuffer], rax
0x180016534  mov     rcx, r14; this
0x180016537  lea     r8, aHsP; "%hs!%p: "
0x18001653e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016543  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001654a  mov     r14, rax
0x18001654d  test    r9, r9
0x180016550  jz      short loc_180016567
0x180016552  lea     r8, aCallerP; "(caller: %p) "
0x180016559  mov     rdx, rsi; unsigned __int16 *
0x18001655c  mov     rcx, rax; this
0x18001655f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016564  mov     r14, rax
0x180016567  call    cs:__imp_GetCurrentThreadId
0x18001656d  lea     rcx, [rsp+278h+Buffer]
0x180016572  mov     r9, rdi; unsigned __int16 *
0x180016575  mov     [rsp+278h+var_240], rcx
0x18001657a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180016581  mov     dword ptr [rsp+278h+Arguments], ebp
0x180016585  mov     rdx, rsi; unsigned __int16 *
0x180016588  mov     [rsp+278h+nSize], eax
0x18001658c  mov     rcx, r14; this
0x18001658f  mov     eax, [rbx+44h]
0x180016592  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180016596  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001659b  cmp     [rbx+18h], r15
0x18001659f  jnz     short loc_1800165B1
0x1800165a1  cmp     [rbx+48h], r15
0x1800165a5  jnz     short loc_1800165B1
0x1800165a7  cmp     [rbx+30h], r15
0x1800165ab  jz      loc_180016641
0x1800165b1  lea     r8, asc_1800238C8; "    "
0x1800165b8  mov     rdx, rsi; unsigned __int16 *
0x1800165bb  mov     rcx, rax; this
0x1800165be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800165c7  test    r9, r9
0x1800165ca  jz      short loc_1800165DE
0x1800165cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800165d3  mov     rdx, rsi; unsigned __int16 *
0x1800165d6  mov     rcx, rax; this
0x1800165d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800165e2  test    r9, r9
0x1800165e5  jz      short loc_1800165F9
0x1800165e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800165ee  mov     rdx, rsi; unsigned __int16 *
0x1800165f1  mov     rcx, rax; this
0x1800165f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800165f9  mov     rcx, [rbx+28h]
0x1800165fd  mov     rdx, rsi; unsigned __int16 *
0x180016600  mov     r9, [rbx+30h]; unsigned __int16 *
0x180016604  test    rcx, rcx
0x180016607  jz      short loc_18001661F
0x180016609  mov     [rsp+278h+lpBuffer], rcx
0x18001660e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180016615  mov     rcx, rax; this
0x180016618  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001661d  jmp     short loc_180016641
0x18001661f  mov     rcx, rax; this
0x180016622  test    r9, r9
0x180016625  jz      short loc_180016635
0x180016627  lea     r8, aHs; "[%hs]\n"
0x18001662e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016633  jmp     short loc_180016641
0x180016635  lea     r8, asc_180023940; "\n"
0x18001663c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180016641  xor     eax, eax
0x180016643  mov     rcx, [rsp+278h+var_38]
0x18001664b  xor     rcx, rsp; StackCookie
0x18001664e  call    __security_check_cookie
0x180016653  mov     rbx, [rsp+278h+arg_18]
0x18001665b  add     rsp, 250h
0x180016662  pop     r15
0x180016664  pop     r14
0x180016666  pop     rdi
0x180016667  pop     rsi
0x180016668  pop     rbp
0x180016669  retn
```
