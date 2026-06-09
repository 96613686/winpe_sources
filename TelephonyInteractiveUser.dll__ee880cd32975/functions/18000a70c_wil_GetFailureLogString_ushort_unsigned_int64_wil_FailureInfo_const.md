# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000a70c`
- end: `0x18000a9c2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000650c`
- `0x18000677c`
- `0x18000cb88`

## callees

- `0x180001dc0`
- `0x1800027c0`
- `0x18000a70c`
- `0x18000ce88`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a83e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000a83e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a8bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a8bf`

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
          v8 = (const char *)&qword_18001CE98;
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
0x18000a70c  mov     [rsp+arg_18], rbx
0x18000a711  push    rbp
0x18000a712  push    rsi
0x18000a713  push    rdi
0x18000a714  push    r14
0x18000a716  push    r15
0x18000a718  sub     rsp, 250h
0x18000a71f  mov     rax, cs:__security_cookie
0x18000a726  xor     rax, rsp
0x18000a729  mov     [rsp+278h+var_38], rax
0x18000a731  xor     r15d, r15d
0x18000a734  mov     rbx, r8
0x18000a737  mov     rsi, rdx
0x18000a73a  mov     r14, rcx
0x18000a73d  test    rdx, rdx
0x18000a740  jz      loc_18000A999
0x18000a746  test    rcx, rcx
0x18000a749  jz      loc_18000A999
0x18000a74f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a756  mov     [rcx], r15w
0x18000a75a  test    rax, rax
0x18000a75d  jz      short loc_18000A780
0x18000a75f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000a766  jz      short loc_18000A780
0x18000a768  mov     r8, rdx
0x18000a76b  mov     rdx, rcx
0x18000a76e  mov     rcx, rbx
0x18000a771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a776  cmp     [r14], r15w
0x18000a77a  jnz     loc_18000A999
0x18000a780  mov     ecx, [rbx]
0x18000a782  mov     bpl, 8
0x18000a785  test    ecx, ecx
0x18000a787  jz      short loc_18000A7D2
0x18000a789  sub     ecx, 1
0x18000a78c  jz      short loc_18000A7BA
0x18000a78e  sub     ecx, 1
0x18000a791  jz      short loc_18000A7AA
0x18000a793  cmp     ecx, 1
0x18000a796  jz      short loc_18000A7A1
0x18000a798  lea     rdi, qword_18001CE98
0x18000a79f  jmp     short loc_18000A7D9
0x18000a7a1  lea     rdi, aFailfast; "FailFast"
0x18000a7a8  jmp     short loc_18000A7D9
0x18000a7aa  lea     rax, aLoghr; "LogHr"
0x18000a7b1  lea     rdi, aLognt; "LogNt"
0x18000a7b8  jmp     short loc_18000A7C8
0x18000a7ba  lea     rax, aReturnhr; "ReturnHr"
0x18000a7c1  lea     rdi, aReturnnt; "ReturnNt"
0x18000a7c8  test    [rbx+4], bpl
0x18000a7cc  cmovz   rdi, rax
0x18000a7d0  jmp     short loc_18000A7D9
0x18000a7d2  lea     rdi, aException; "Exception"
0x18000a7d9  xor     edx, edx; Val
0x18000a7db  lea     rcx, [rsp+278h+Buffer]; void *
0x18000a7e0  mov     r8d, 200h; Size
0x18000a7e6  call    memset_0
0x18000a7eb  test    [rbx+4], bpl
0x18000a7ef  jz      short loc_18000A814
0x18000a7f1  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000a7f8  mov     ebp, [rbx+0Ch]
0x18000a7fb  test    rax, rax
0x18000a7fe  jz      short loc_18000A844
0x18000a800  mov     r8d, 100h
0x18000a806  lea     rdx, [rsp+278h+Buffer]
0x18000a80b  mov     ecx, ebp
0x18000a80d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a812  jmp     short loc_18000A844
0x18000a814  mov     ebp, [rbx+8]
0x18000a817  lea     rax, [rsp+278h+Buffer]
0x18000a81c  mov     [rsp+278h+Arguments], r15; Arguments
0x18000a821  mov     r8d, ebp; dwMessageId
0x18000a824  mov     [rsp+278h+nSize], 100h; nSize
0x18000a82c  mov     r9d, 400h; dwLanguageId
0x18000a832  xor     edx, edx; lpSource
0x18000a834  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000a839  mov     ecx, 1200h; dwFlags
0x18000a83e  call    cs:__imp_FormatMessageW
0x18000a844  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000a848  lea     rsi, [r14+rsi*2]
0x18000a84c  mov     rax, [rbx+88h]
0x18000a853  mov     rdx, rsi; unsigned __int16 *
0x18000a856  mov     rcx, [rbx+80h]
0x18000a85d  test    r9, r9
0x18000a860  jz      short loc_18000A884
0x18000a862  mov     [rsp+278h+Arguments], rax
0x18000a867  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000a86e  mov     eax, [rbx+40h]
0x18000a871  mov     qword ptr [rsp+278h+nSize], rcx
0x18000a876  mov     rcx, r14; this
0x18000a879  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a87d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a882  jmp     short loc_18000A89B
0x18000a884  mov     r9, rcx; unsigned __int16 *
0x18000a887  mov     [rsp+278h+lpBuffer], rax
0x18000a88c  mov     rcx, r14; this
0x18000a88f  lea     r8, aHsP; "%hs!%p: "
0x18000a896  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a89b  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000a8a2  mov     r14, rax
0x18000a8a5  test    r9, r9
0x18000a8a8  jz      short loc_18000A8BF
0x18000a8aa  lea     r8, aCallerP; "(caller: %p) "
0x18000a8b1  mov     rdx, rsi; unsigned __int16 *
0x18000a8b4  mov     rcx, rax; this
0x18000a8b7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a8bc  mov     r14, rax
0x18000a8bf  call    cs:__imp_GetCurrentThreadId
0x18000a8c5  lea     rcx, [rsp+278h+Buffer]
0x18000a8ca  mov     r9, rdi; unsigned __int16 *
0x18000a8cd  mov     [rsp+278h+var_240], rcx
0x18000a8d2  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000a8d9  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000a8dd  mov     rdx, rsi; unsigned __int16 *
0x18000a8e0  mov     [rsp+278h+nSize], eax
0x18000a8e4  mov     rcx, r14; this
0x18000a8e7  mov     eax, [rbx+44h]
0x18000a8ea  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000a8ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a8f3  cmp     [rbx+18h], r15
0x18000a8f7  jnz     short loc_18000A909
0x18000a8f9  cmp     [rbx+48h], r15
0x18000a8fd  jnz     short loc_18000A909
0x18000a8ff  cmp     [rbx+30h], r15
0x18000a903  jz      loc_18000A999
0x18000a909  lea     r8, asc_18001D7E0; "    "
0x18000a910  mov     rdx, rsi; unsigned __int16 *
0x18000a913  mov     rcx, rax; this
0x18000a916  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a91b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18000a91f  test    r9, r9
0x18000a922  jz      short loc_18000A936
0x18000a924  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000a92b  mov     rdx, rsi; unsigned __int16 *
0x18000a92e  mov     rcx, rax; this
0x18000a931  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a936  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000a93a  test    r9, r9
0x18000a93d  jz      short loc_18000A951
0x18000a93f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000a946  mov     rdx, rsi; unsigned __int16 *
0x18000a949  mov     rcx, rax; this
0x18000a94c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a951  mov     rcx, [rbx+28h]
0x18000a955  mov     rdx, rsi; unsigned __int16 *
0x18000a958  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000a95c  test    rcx, rcx
0x18000a95f  jz      short loc_18000A977
0x18000a961  mov     [rsp+278h+lpBuffer], rcx
0x18000a966  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000a96d  mov     rcx, rax; this
0x18000a970  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a975  jmp     short loc_18000A999
0x18000a977  mov     rcx, rax; this
0x18000a97a  test    r9, r9
0x18000a97d  jz      short loc_18000A98D
0x18000a97f  lea     r8, aHs; "[%hs]\n"
0x18000a986  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a98b  jmp     short loc_18000A999
0x18000a98d  lea     r8, asc_18001D858; "\n"
0x18000a994  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000a999  xor     eax, eax
0x18000a99b  mov     rcx, [rsp+278h+var_38]
0x18000a9a3  xor     rcx, rsp; StackCookie
0x18000a9a6  call    __security_check_cookie
0x18000a9ab  mov     rbx, [rsp+278h+arg_18]
0x18000a9b3  add     rsp, 250h
0x18000a9ba  pop     r15
0x18000a9bc  pop     r14
0x18000a9be  pop     rdi
0x18000a9bf  pop     rsi
0x18000a9c0  pop     rbp
0x18000a9c1  retn
```
