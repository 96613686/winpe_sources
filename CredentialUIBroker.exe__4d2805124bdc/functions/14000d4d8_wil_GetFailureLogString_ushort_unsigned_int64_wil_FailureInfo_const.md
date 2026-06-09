# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000d4d8`
- end: `0x14000d78e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140006ac8`
- `0x14000ee4c`

## callees

- `0x140003620`
- `0x1400042c4`
- `0x14000d4d8`
- `0x14000f23c`
- `0x14001f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000d68b`
- `KERNEL32!GetCurrentThreadId` at `0x14000d68b`
- `KERNEL32!FormatMessageW` at `0x14000d60a`
- `KERNEL32!FormatMessageW` at `0x14000d60a`

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
          v8 = (const char *)&byte_140023040;
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
0x14000d4d8  mov     [rsp+arg_18], rbx
0x14000d4dd  push    rbp
0x14000d4de  push    rsi
0x14000d4df  push    rdi
0x14000d4e0  push    r14
0x14000d4e2  push    r15
0x14000d4e4  sub     rsp, 250h
0x14000d4eb  mov     rax, cs:__security_cookie
0x14000d4f2  xor     rax, rsp
0x14000d4f5  mov     [rsp+278h+var_38], rax
0x14000d4fd  xor     r15d, r15d
0x14000d500  mov     rbx, r8
0x14000d503  mov     rsi, rdx
0x14000d506  mov     r14, rcx
0x14000d509  test    rdx, rdx
0x14000d50c  jz      loc_14000D765
0x14000d512  test    rcx, rcx
0x14000d515  jz      loc_14000D765
0x14000d51b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000d522  mov     [rcx], r15w
0x14000d526  test    rax, rax
0x14000d529  jz      short loc_14000D54C
0x14000d52b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000d532  jz      short loc_14000D54C
0x14000d534  mov     r8, rdx
0x14000d537  mov     rdx, rcx
0x14000d53a  mov     rcx, rbx
0x14000d53d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d542  cmp     [r14], r15w
0x14000d546  jnz     loc_14000D765
0x14000d54c  mov     ecx, [rbx]
0x14000d54e  mov     bpl, 8
0x14000d551  test    ecx, ecx
0x14000d553  jz      short loc_14000D59E
0x14000d555  sub     ecx, 1
0x14000d558  jz      short loc_14000D586
0x14000d55a  sub     ecx, 1
0x14000d55d  jz      short loc_14000D576
0x14000d55f  cmp     ecx, 1
0x14000d562  jz      short loc_14000D56D
0x14000d564  lea     rdi, byte_140023040
0x14000d56b  jmp     short loc_14000D5A5
0x14000d56d  lea     rdi, aFailfast; "FailFast"
0x14000d574  jmp     short loc_14000D5A5
0x14000d576  lea     rax, aLoghr; "LogHr"
0x14000d57d  lea     rdi, aLognt; "LogNt"
0x14000d584  jmp     short loc_14000D594
0x14000d586  lea     rax, aReturnhr; "ReturnHr"
0x14000d58d  lea     rdi, aReturnnt; "ReturnNt"
0x14000d594  test    [rbx+4], bpl
0x14000d598  cmovz   rdi, rax
0x14000d59c  jmp     short loc_14000D5A5
0x14000d59e  lea     rdi, aException; "Exception"
0x14000d5a5  xor     edx, edx; Val
0x14000d5a7  lea     rcx, [rsp+278h+Buffer]; void *
0x14000d5ac  mov     r8d, 200h; Size
0x14000d5b2  call    memset_0
0x14000d5b7  test    [rbx+4], bpl
0x14000d5bb  jz      short loc_14000D5E0
0x14000d5bd  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000d5c4  mov     ebp, [rbx+0Ch]
0x14000d5c7  test    rax, rax
0x14000d5ca  jz      short loc_14000D610
0x14000d5cc  mov     r8d, 100h
0x14000d5d2  lea     rdx, [rsp+278h+Buffer]
0x14000d5d7  mov     ecx, ebp
0x14000d5d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d5de  jmp     short loc_14000D610
0x14000d5e0  mov     ebp, [rbx+8]
0x14000d5e3  lea     rax, [rsp+278h+Buffer]
0x14000d5e8  mov     [rsp+278h+Arguments], r15; Arguments
0x14000d5ed  mov     r8d, ebp; dwMessageId
0x14000d5f0  mov     [rsp+278h+nSize], 100h; nSize
0x14000d5f8  mov     r9d, 400h; dwLanguageId
0x14000d5fe  xor     edx, edx; lpSource
0x14000d600  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000d605  mov     ecx, 1200h; dwFlags
0x14000d60a  call    cs:__imp_FormatMessageW
0x14000d610  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000d614  lea     rsi, [r14+rsi*2]
0x14000d618  mov     rax, [rbx+88h]
0x14000d61f  mov     rdx, rsi; unsigned __int16 *
0x14000d622  mov     rcx, [rbx+80h]
0x14000d629  test    r9, r9
0x14000d62c  jz      short loc_14000D650
0x14000d62e  mov     [rsp+278h+Arguments], rax
0x14000d633  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000d63a  mov     eax, [rbx+40h]
0x14000d63d  mov     qword ptr [rsp+278h+nSize], rcx
0x14000d642  mov     rcx, r14; this
0x14000d645  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000d649  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d64e  jmp     short loc_14000D667
0x14000d650  mov     r9, rcx; unsigned __int16 *
0x14000d653  mov     [rsp+278h+lpBuffer], rax
0x14000d658  mov     rcx, r14; this
0x14000d65b  lea     r8, aHsP; "%hs!%p: "
0x14000d662  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d667  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000d66e  mov     r14, rax
0x14000d671  test    r9, r9
0x14000d674  jz      short loc_14000D68B
0x14000d676  lea     r8, aCallerP; "(caller: %p) "
0x14000d67d  mov     rdx, rsi; unsigned __int16 *
0x14000d680  mov     rcx, rax; this
0x14000d683  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d688  mov     r14, rax
0x14000d68b  call    cs:__imp_GetCurrentThreadId
0x14000d691  lea     rcx, [rsp+278h+Buffer]
0x14000d696  mov     r9, rdi; unsigned __int16 *
0x14000d699  mov     [rsp+278h+var_240], rcx
0x14000d69e  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000d6a5  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000d6a9  mov     rdx, rsi; unsigned __int16 *
0x14000d6ac  mov     [rsp+278h+nSize], eax
0x14000d6b0  mov     rcx, r14; this
0x14000d6b3  mov     eax, [rbx+44h]
0x14000d6b6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000d6ba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d6bf  cmp     [rbx+18h], r15
0x14000d6c3  jnz     short loc_14000D6D5
0x14000d6c5  cmp     [rbx+48h], r15
0x14000d6c9  jnz     short loc_14000D6D5
0x14000d6cb  cmp     [rbx+30h], r15
0x14000d6cf  jz      loc_14000D765
0x14000d6d5  lea     r8, asc_140023130; "    "
0x14000d6dc  mov     rdx, rsi; unsigned __int16 *
0x14000d6df  mov     rcx, rax; this
0x14000d6e2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d6e7  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000d6eb  test    r9, r9
0x14000d6ee  jz      short loc_14000D702
0x14000d6f0  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000d6f7  mov     rdx, rsi; unsigned __int16 *
0x14000d6fa  mov     rcx, rax; this
0x14000d6fd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d702  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000d706  test    r9, r9
0x14000d709  jz      short loc_14000D71D
0x14000d70b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000d712  mov     rdx, rsi; unsigned __int16 *
0x14000d715  mov     rcx, rax; this
0x14000d718  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d71d  mov     rcx, [rbx+28h]
0x14000d721  mov     rdx, rsi; unsigned __int16 *
0x14000d724  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000d728  test    rcx, rcx
0x14000d72b  jz      short loc_14000D743
0x14000d72d  mov     [rsp+278h+lpBuffer], rcx
0x14000d732  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000d739  mov     rcx, rax; this
0x14000d73c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d741  jmp     short loc_14000D765
0x14000d743  mov     rcx, rax; this
0x14000d746  test    r9, r9
0x14000d749  jz      short loc_14000D759
0x14000d74b  lea     r8, aHs; "[%hs]\n"
0x14000d752  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d757  jmp     short loc_14000D765
0x14000d759  lea     r8, asc_1400231A8; "\n"
0x14000d760  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000d765  xor     eax, eax
0x14000d767  mov     rcx, [rsp+278h+var_38]
0x14000d76f  xor     rcx, rsp; StackCookie
0x14000d772  call    __security_check_cookie
0x14000d777  mov     rbx, [rsp+278h+arg_18]
0x14000d77f  add     rsp, 250h
0x14000d786  pop     r15
0x14000d788  pop     r14
0x14000d78a  pop     rdi
0x14000d78b  pop     rsi
0x14000d78c  pop     rbp
0x14000d78d  retn
```
