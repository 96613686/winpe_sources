# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18001e3d4`
- end: `0x18001e68a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180015c90`
- `0x18001d490`
- `0x18001ebbc`
- `0x180020130`

## callees

- `0x18001a540`
- `0x18001b004`
- `0x18001e3d4`
- `0x18001eb6c`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e587`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001e587`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e506`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18001e506`

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
          v7 = (const char *)&byte_1800FAB55;
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
0x18001e3d4  mov     [rsp+arg_18], rbx
0x18001e3d9  push    rbp
0x18001e3da  push    rsi
0x18001e3db  push    rdi
0x18001e3dc  push    r14
0x18001e3de  push    r15
0x18001e3e0  sub     rsp, 250h
0x18001e3e7  mov     rax, cs:__security_cookie
0x18001e3ee  xor     rax, rsp
0x18001e3f1  mov     [rsp+278h+var_38], rax
0x18001e3f9  mov     rbx, r8
0x18001e3fc  mov     rsi, rdx
0x18001e3ff  mov     r14, rcx
0x18001e402  xor     r15d, r15d
0x18001e405  test    rdx, rdx
0x18001e408  jz      loc_18001E661
0x18001e40e  test    rcx, rcx
0x18001e411  jz      loc_18001E661
0x18001e417  mov     [rcx], r15w
0x18001e41b  mov     rax, cs:g_pfnResultLoggingCallback
0x18001e422  test    rax, rax
0x18001e425  jz      short loc_18001E448
0x18001e427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18001e42e  jz      short loc_18001E448
0x18001e430  mov     r8, rdx
0x18001e433  mov     rdx, rcx
0x18001e436  mov     rcx, rbx
0x18001e439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e43e  cmp     [r14], r15w
0x18001e442  jnz     loc_18001E661
0x18001e448  mov     ecx, [rbx]
0x18001e44a  mov     bpl, 8
0x18001e44d  test    ecx, ecx
0x18001e44f  jz      short loc_18001E49A
0x18001e451  sub     ecx, 1
0x18001e454  jz      short loc_18001E482
0x18001e456  sub     ecx, 1
0x18001e459  jz      short loc_18001E472
0x18001e45b  cmp     ecx, 1
0x18001e45e  jz      short loc_18001E469
0x18001e460  lea     rdi, byte_1800FAB55
0x18001e467  jmp     short loc_18001E4A1
0x18001e469  lea     rdi, aFailfast; "FailFast"
0x18001e470  jmp     short loc_18001E4A1
0x18001e472  lea     rax, aLoghr; "LogHr"
0x18001e479  lea     rdi, aLognt; "LogNt"
0x18001e480  jmp     short loc_18001E490
0x18001e482  lea     rax, aReturnhr; "ReturnHr"
0x18001e489  lea     rdi, aReturnnt; "ReturnNt"
0x18001e490  test    [rbx+4], bpl
0x18001e494  cmovz   rdi, rax
0x18001e498  jmp     short loc_18001E4A1
0x18001e49a  lea     rdi, aException; "Exception"
0x18001e4a1  xor     edx, edx; Val
0x18001e4a3  mov     r8d, 200h; Size
0x18001e4a9  lea     rcx, [rsp+278h+Buffer]; void *
0x18001e4ae  call    memset_0
0x18001e4b3  test    [rbx+4], bpl
0x18001e4b7  jz      short loc_18001E4DC
0x18001e4b9  mov     ebp, [rbx+0Ch]
0x18001e4bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18001e4c3  test    rax, rax
0x18001e4c6  jz      short loc_18001E50C
0x18001e4c8  mov     r8d, 100h
0x18001e4ce  lea     rdx, [rsp+278h+Buffer]
0x18001e4d3  mov     ecx, ebp
0x18001e4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e4da  jmp     short loc_18001E50C
0x18001e4dc  mov     ebp, [rbx+8]
0x18001e4df  mov     [rsp+278h+Arguments], r15; Arguments
0x18001e4e4  mov     [rsp+278h+nSize], 100h; nSize
0x18001e4ec  lea     rax, [rsp+278h+Buffer]
0x18001e4f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18001e4f6  mov     r9d, 400h; dwLanguageId
0x18001e4fc  mov     r8d, ebp; dwMessageId
0x18001e4ff  xor     edx, edx; lpSource
0x18001e501  mov     ecx, 1200h; dwFlags
0x18001e506  call    cs:__imp_FormatMessageW
0x18001e50c  lea     rsi, [r14+rsi*2]
0x18001e510  mov     r9, [rbx+38h]; unsigned __int16 *
0x18001e514  mov     rax, [rbx+88h]
0x18001e51b  mov     rcx, [rbx+80h]
0x18001e522  mov     rdx, rsi; unsigned __int16 *
0x18001e525  test    r9, r9
0x18001e528  jz      short loc_18001E54C
0x18001e52a  mov     [rsp+278h+Arguments], rax
0x18001e52f  mov     qword ptr [rsp+278h+nSize], rcx
0x18001e534  mov     eax, [rbx+40h]
0x18001e537  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e53b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18001e542  mov     rcx, r14; this
0x18001e545  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e54a  jmp     short loc_18001E563
0x18001e54c  mov     [rsp+278h+lpBuffer], rax
0x18001e551  mov     r9, rcx; unsigned __int16 *
0x18001e554  lea     r8, aHsP; "%hs!%p: "
0x18001e55b  mov     rcx, r14; this
0x18001e55e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e563  mov     r14, rax
0x18001e566  mov     r9, [rbx+90h]; unsigned __int16 *
0x18001e56d  test    r9, r9
0x18001e570  jz      short loc_18001E587
0x18001e572  lea     r8, aCallerP; "(caller: %p) "
0x18001e579  mov     rdx, rsi; unsigned __int16 *
0x18001e57c  mov     rcx, rax; this
0x18001e57f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e584  mov     r14, rax
0x18001e587  call    cs:__imp_GetCurrentThreadId
0x18001e58d  lea     rcx, [rsp+278h+Buffer]
0x18001e592  mov     [rsp+278h+var_240], rcx
0x18001e597  mov     dword ptr [rsp+278h+Arguments], ebp
0x18001e59b  mov     [rsp+278h+nSize], eax
0x18001e59f  mov     eax, [rbx+44h]
0x18001e5a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18001e5a6  mov     r9, rdi; unsigned __int16 *
0x18001e5a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18001e5b0  mov     rdx, rsi; unsigned __int16 *
0x18001e5b3  mov     rcx, r14; this
0x18001e5b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e5bb  cmp     [rbx+18h], r15
0x18001e5bf  jnz     short loc_18001E5D1
0x18001e5c1  cmp     [rbx+48h], r15
0x18001e5c5  jnz     short loc_18001E5D1
0x18001e5c7  cmp     [rbx+30h], r15
0x18001e5cb  jz      loc_18001E661
0x18001e5d1  lea     r8, asc_1800FAC58; "    "
0x18001e5d8  mov     rdx, rsi; unsigned __int16 *
0x18001e5db  mov     rcx, rax; this
0x18001e5de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e5e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x18001e5e7  test    r9, r9
0x18001e5ea  jz      short loc_18001E5FE
0x18001e5ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x18001e5f3  mov     rdx, rsi; unsigned __int16 *
0x18001e5f6  mov     rcx, rax; this
0x18001e5f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e5fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x18001e602  test    r9, r9
0x18001e605  jz      short loc_18001E619
0x18001e607  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001e60e  mov     rdx, rsi; unsigned __int16 *
0x18001e611  mov     rcx, rax; this
0x18001e614  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e619  mov     rcx, [rbx+28h]
0x18001e61d  mov     r9, [rbx+30h]; unsigned __int16 *
0x18001e621  mov     rdx, rsi; unsigned __int16 *
0x18001e624  test    rcx, rcx
0x18001e627  jz      short loc_18001E63F
0x18001e629  mov     [rsp+278h+lpBuffer], rcx
0x18001e62e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18001e635  mov     rcx, rax; this
0x18001e638  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e63d  jmp     short loc_18001E661
0x18001e63f  mov     rcx, rax; this
0x18001e642  test    r9, r9
0x18001e645  jz      short loc_18001E655
0x18001e647  lea     r8, aHs; "[%hs]\n"
0x18001e64e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e653  jmp     short loc_18001E661
0x18001e655  lea     r8, asc_1800FACD0; "\n"
0x18001e65c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001e661  xor     eax, eax
0x18001e663  mov     rcx, [rsp+278h+var_38]
0x18001e66b  xor     rcx, rsp; StackCookie
0x18001e66e  call    __security_check_cookie
0x18001e673  mov     rbx, [rsp+278h+arg_18]
0x18001e67b  add     rsp, 250h
0x18001e682  pop     r15
0x18001e684  pop     r14
0x18001e686  pop     rdi
0x18001e687  pop     rsi
0x18001e688  pop     rbp
0x18001e689  retn
```
