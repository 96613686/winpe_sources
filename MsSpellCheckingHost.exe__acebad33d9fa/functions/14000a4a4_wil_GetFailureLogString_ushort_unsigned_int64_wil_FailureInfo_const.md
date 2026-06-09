# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000a4a4`
- end: `0x14000a75a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140007144`
- `0x1400073ac`
- `0x14000b5b4`
- `0x14000f660`

## callees

- `0x1400023f3`
- `0x14000a4a4`
- `0x14000b8b4`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a657`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a657`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000a5d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000a5d6`

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
          v7 = (const char *)&qword_140016C68;
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
0x14000a4a4  mov     [rsp+arg_18], rbx
0x14000a4a9  push    rbp
0x14000a4aa  push    rsi
0x14000a4ab  push    rdi
0x14000a4ac  push    r14
0x14000a4ae  push    r15
0x14000a4b0  sub     rsp, 250h
0x14000a4b7  mov     rax, cs:__security_cookie
0x14000a4be  xor     rax, rsp
0x14000a4c1  mov     [rsp+278h+var_38], rax
0x14000a4c9  mov     rbx, r8
0x14000a4cc  mov     rsi, rdx
0x14000a4cf  mov     r14, rcx
0x14000a4d2  xor     r15d, r15d
0x14000a4d5  test    rdx, rdx
0x14000a4d8  jz      loc_14000A731
0x14000a4de  test    rcx, rcx
0x14000a4e1  jz      loc_14000A731
0x14000a4e7  mov     [rcx], r15w
0x14000a4eb  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a4f2  test    rax, rax
0x14000a4f5  jz      short loc_14000A518
0x14000a4f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000a4fe  jz      short loc_14000A518
0x14000a500  mov     r8, rdx
0x14000a503  mov     rdx, rcx
0x14000a506  mov     rcx, rbx
0x14000a509  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a50e  cmp     [r14], r15w
0x14000a512  jnz     loc_14000A731
0x14000a518  mov     ecx, [rbx]
0x14000a51a  mov     bpl, 8
0x14000a51d  test    ecx, ecx
0x14000a51f  jz      short loc_14000A56A
0x14000a521  sub     ecx, 1
0x14000a524  jz      short loc_14000A552
0x14000a526  sub     ecx, 1
0x14000a529  jz      short loc_14000A542
0x14000a52b  cmp     ecx, 1
0x14000a52e  jz      short loc_14000A539
0x14000a530  lea     rdi, qword_140016C68
0x14000a537  jmp     short loc_14000A571
0x14000a539  lea     rdi, aFailfast; "FailFast"
0x14000a540  jmp     short loc_14000A571
0x14000a542  lea     rax, aLoghr; "LogHr"
0x14000a549  lea     rdi, aLognt; "LogNt"
0x14000a550  jmp     short loc_14000A560
0x14000a552  lea     rax, aReturnhr; "ReturnHr"
0x14000a559  lea     rdi, aReturnnt; "ReturnNt"
0x14000a560  test    [rbx+4], bpl
0x14000a564  cmovz   rdi, rax
0x14000a568  jmp     short loc_14000A571
0x14000a56a  lea     rdi, aException; "Exception"
0x14000a571  xor     edx, edx; Val
0x14000a573  mov     r8d, 200h; Size
0x14000a579  lea     rcx, [rsp+278h+Buffer]; void *
0x14000a57e  call    memset_0
0x14000a583  test    [rbx+4], bpl
0x14000a587  jz      short loc_14000A5AC
0x14000a589  mov     ebp, [rbx+0Ch]
0x14000a58c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000a593  test    rax, rax
0x14000a596  jz      short loc_14000A5DC
0x14000a598  mov     r8d, 100h
0x14000a59e  lea     rdx, [rsp+278h+Buffer]
0x14000a5a3  mov     ecx, ebp
0x14000a5a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a5aa  jmp     short loc_14000A5DC
0x14000a5ac  mov     ebp, [rbx+8]
0x14000a5af  mov     [rsp+278h+Arguments], r15; Arguments
0x14000a5b4  mov     [rsp+278h+nSize], 100h; nSize
0x14000a5bc  lea     rax, [rsp+278h+Buffer]
0x14000a5c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000a5c6  mov     r9d, 400h; dwLanguageId
0x14000a5cc  mov     r8d, ebp; dwMessageId
0x14000a5cf  xor     edx, edx; lpSource
0x14000a5d1  mov     ecx, 1200h; dwFlags
0x14000a5d6  call    cs:__imp_FormatMessageW
0x14000a5dc  lea     rsi, [r14+rsi*2]
0x14000a5e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000a5e4  mov     rax, [rbx+88h]
0x14000a5eb  mov     rcx, [rbx+80h]
0x14000a5f2  mov     rdx, rsi; unsigned __int16 *
0x14000a5f5  test    r9, r9
0x14000a5f8  jz      short loc_14000A61C
0x14000a5fa  mov     [rsp+278h+Arguments], rax
0x14000a5ff  mov     qword ptr [rsp+278h+nSize], rcx
0x14000a604  mov     eax, [rbx+40h]
0x14000a607  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000a60b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000a612  mov     rcx, r14; this
0x14000a615  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a61a  jmp     short loc_14000A633
0x14000a61c  mov     [rsp+278h+lpBuffer], rax
0x14000a621  mov     r9, rcx; unsigned __int16 *
0x14000a624  lea     r8, aHsP; "%hs!%p: "
0x14000a62b  mov     rcx, r14; this
0x14000a62e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a633  mov     r14, rax
0x14000a636  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000a63d  test    r9, r9
0x14000a640  jz      short loc_14000A657
0x14000a642  lea     r8, aCallerP; "(caller: %p) "
0x14000a649  mov     rdx, rsi; unsigned __int16 *
0x14000a64c  mov     rcx, rax; this
0x14000a64f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a654  mov     r14, rax
0x14000a657  call    cs:__imp_GetCurrentThreadId
0x14000a65d  lea     rcx, [rsp+278h+Buffer]
0x14000a662  mov     [rsp+278h+var_240], rcx
0x14000a667  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000a66b  mov     [rsp+278h+nSize], eax
0x14000a66f  mov     eax, [rbx+44h]
0x14000a672  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000a676  mov     r9, rdi; unsigned __int16 *
0x14000a679  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000a680  mov     rdx, rsi; unsigned __int16 *
0x14000a683  mov     rcx, r14; this
0x14000a686  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a68b  cmp     [rbx+18h], r15
0x14000a68f  jnz     short loc_14000A6A1
0x14000a691  cmp     [rbx+48h], r15
0x14000a695  jnz     short loc_14000A6A1
0x14000a697  cmp     [rbx+30h], r15
0x14000a69b  jz      loc_14000A731
0x14000a6a1  lea     r8, asc_140016D58; "    "
0x14000a6a8  mov     rdx, rsi; unsigned __int16 *
0x14000a6ab  mov     rcx, rax; this
0x14000a6ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a6b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000a6b7  test    r9, r9
0x14000a6ba  jz      short loc_14000A6CE
0x14000a6bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000a6c3  mov     rdx, rsi; unsigned __int16 *
0x14000a6c6  mov     rcx, rax; this
0x14000a6c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a6ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000a6d2  test    r9, r9
0x14000a6d5  jz      short loc_14000A6E9
0x14000a6d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000a6de  mov     rdx, rsi; unsigned __int16 *
0x14000a6e1  mov     rcx, rax; this
0x14000a6e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a6e9  mov     rcx, [rbx+28h]
0x14000a6ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000a6f1  mov     rdx, rsi; unsigned __int16 *
0x14000a6f4  test    rcx, rcx
0x14000a6f7  jz      short loc_14000A70F
0x14000a6f9  mov     [rsp+278h+lpBuffer], rcx
0x14000a6fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000a705  mov     rcx, rax; this
0x14000a708  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a70d  jmp     short loc_14000A731
0x14000a70f  mov     rcx, rax; this
0x14000a712  test    r9, r9
0x14000a715  jz      short loc_14000A725
0x14000a717  lea     r8, aHs; "[%hs]\n"
0x14000a71e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a723  jmp     short loc_14000A731
0x14000a725  lea     r8, asc_140016DD0; "\n"
0x14000a72c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000a731  xor     eax, eax
0x14000a733  mov     rcx, [rsp+278h+var_38]
0x14000a73b  xor     rcx, rsp; StackCookie
0x14000a73e  call    __security_check_cookie
0x14000a743  mov     rbx, [rsp+278h+arg_18]
0x14000a74b  add     rsp, 250h
0x14000a752  pop     r15
0x14000a754  pop     r14
0x14000a756  pop     rdi
0x14000a757  pop     rsi
0x14000a758  pop     rbp
0x14000a759  retn
```
