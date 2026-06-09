# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000b4c4`
- end: `0x14000b77a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x1400099c0`
- `0x140009c40`
- `0x140009eec`
- `0x14000d4e0`
- `0x1400169db`
- `0x140016b0f`
- `0x140016c78`
- `0x1400170be`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x14000b4c4`
- `0x14000be30`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b677`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000b5f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000b5f6`

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
          v7 = (const char *)&byte_14001C467;
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
0x14000b4c4  mov     [rsp+arg_18], rbx
0x14000b4c9  push    rbp
0x14000b4ca  push    rsi
0x14000b4cb  push    rdi
0x14000b4cc  push    r14
0x14000b4ce  push    r15
0x14000b4d0  sub     rsp, 250h
0x14000b4d7  mov     rax, cs:__security_cookie
0x14000b4de  xor     rax, rsp
0x14000b4e1  mov     [rsp+278h+var_38], rax
0x14000b4e9  mov     rbx, r8
0x14000b4ec  mov     rsi, rdx
0x14000b4ef  mov     r14, rcx
0x14000b4f2  xor     r15d, r15d
0x14000b4f5  test    rdx, rdx
0x14000b4f8  jz      loc_14000B751
0x14000b4fe  test    rcx, rcx
0x14000b501  jz      loc_14000B751
0x14000b507  mov     [rcx], r15w
0x14000b50b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b512  test    rax, rax
0x14000b515  jz      short loc_14000B538
0x14000b517  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000b51e  jz      short loc_14000B538
0x14000b520  mov     r8, rdx
0x14000b523  mov     rdx, rcx
0x14000b526  mov     rcx, rbx
0x14000b529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b52e  cmp     [r14], r15w
0x14000b532  jnz     loc_14000B751
0x14000b538  mov     ecx, [rbx]
0x14000b53a  mov     bpl, 8
0x14000b53d  test    ecx, ecx
0x14000b53f  jz      short loc_14000B58A
0x14000b541  sub     ecx, 1
0x14000b544  jz      short loc_14000B572
0x14000b546  sub     ecx, 1
0x14000b549  jz      short loc_14000B562
0x14000b54b  cmp     ecx, 1
0x14000b54e  jz      short loc_14000B559
0x14000b550  lea     rdi, byte_14001C467
0x14000b557  jmp     short loc_14000B591
0x14000b559  lea     rdi, aFailfast; "FailFast"
0x14000b560  jmp     short loc_14000B591
0x14000b562  lea     rax, aLoghr; "LogHr"
0x14000b569  lea     rdi, aLognt; "LogNt"
0x14000b570  jmp     short loc_14000B580
0x14000b572  lea     rax, aReturnhr; "ReturnHr"
0x14000b579  lea     rdi, aReturnnt; "ReturnNt"
0x14000b580  test    [rbx+4], bpl
0x14000b584  cmovz   rdi, rax
0x14000b588  jmp     short loc_14000B591
0x14000b58a  lea     rdi, aException; "Exception"
0x14000b591  xor     edx, edx; Val
0x14000b593  mov     r8d, 200h; Size
0x14000b599  lea     rcx, [rsp+278h+Buffer]; void *
0x14000b59e  call    memset_0
0x14000b5a3  test    [rbx+4], bpl
0x14000b5a7  jz      short loc_14000B5CC
0x14000b5a9  mov     ebp, [rbx+0Ch]
0x14000b5ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000b5b3  test    rax, rax
0x14000b5b6  jz      short loc_14000B5FC
0x14000b5b8  mov     r8d, 100h
0x14000b5be  lea     rdx, [rsp+278h+Buffer]
0x14000b5c3  mov     ecx, ebp
0x14000b5c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b5ca  jmp     short loc_14000B5FC
0x14000b5cc  mov     ebp, [rbx+8]
0x14000b5cf  mov     [rsp+278h+Arguments], r15; Arguments
0x14000b5d4  mov     [rsp+278h+nSize], 100h; nSize
0x14000b5dc  lea     rax, [rsp+278h+Buffer]
0x14000b5e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000b5e6  mov     r9d, 400h; dwLanguageId
0x14000b5ec  mov     r8d, ebp; dwMessageId
0x14000b5ef  xor     edx, edx; lpSource
0x14000b5f1  mov     ecx, 1200h; dwFlags
0x14000b5f6  call    cs:__imp_FormatMessageW
0x14000b5fc  lea     rsi, [r14+rsi*2]
0x14000b600  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000b604  mov     rax, [rbx+88h]
0x14000b60b  mov     rcx, [rbx+80h]
0x14000b612  mov     rdx, rsi; unsigned __int16 *
0x14000b615  test    r9, r9
0x14000b618  jz      short loc_14000B63C
0x14000b61a  mov     [rsp+278h+Arguments], rax
0x14000b61f  mov     qword ptr [rsp+278h+nSize], rcx
0x14000b624  mov     eax, [rbx+40h]
0x14000b627  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b62b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000b632  mov     rcx, r14; this
0x14000b635  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b63a  jmp     short loc_14000B653
0x14000b63c  mov     [rsp+278h+lpBuffer], rax
0x14000b641  mov     r9, rcx; unsigned __int16 *
0x14000b644  lea     r8, aHsP; "%hs!%p: "
0x14000b64b  mov     rcx, r14; this
0x14000b64e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b653  mov     r14, rax
0x14000b656  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000b65d  test    r9, r9
0x14000b660  jz      short loc_14000B677
0x14000b662  lea     r8, aCallerP; "(caller: %p) "
0x14000b669  mov     rdx, rsi; unsigned __int16 *
0x14000b66c  mov     rcx, rax; this
0x14000b66f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b674  mov     r14, rax
0x14000b677  call    cs:__imp_GetCurrentThreadId
0x14000b67d  lea     rcx, [rsp+278h+Buffer]
0x14000b682  mov     [rsp+278h+var_240], rcx
0x14000b687  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000b68b  mov     [rsp+278h+nSize], eax
0x14000b68f  mov     eax, [rbx+44h]
0x14000b692  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b696  mov     r9, rdi; unsigned __int16 *
0x14000b699  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000b6a0  mov     rdx, rsi; unsigned __int16 *
0x14000b6a3  mov     rcx, r14; this
0x14000b6a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6ab  cmp     [rbx+18h], r15
0x14000b6af  jnz     short loc_14000B6C1
0x14000b6b1  cmp     [rbx+48h], r15
0x14000b6b5  jnz     short loc_14000B6C1
0x14000b6b7  cmp     [rbx+30h], r15
0x14000b6bb  jz      loc_14000B751
0x14000b6c1  lea     r8, asc_14001C558; "    "
0x14000b6c8  mov     rdx, rsi; unsigned __int16 *
0x14000b6cb  mov     rcx, rax; this
0x14000b6ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000b6d7  test    r9, r9
0x14000b6da  jz      short loc_14000B6EE
0x14000b6dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000b6e3  mov     rdx, rsi; unsigned __int16 *
0x14000b6e6  mov     rcx, rax; this
0x14000b6e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b6ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000b6f2  test    r9, r9
0x14000b6f5  jz      short loc_14000B709
0x14000b6f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000b6fe  mov     rdx, rsi; unsigned __int16 *
0x14000b701  mov     rcx, rax; this
0x14000b704  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b709  mov     rcx, [rbx+28h]
0x14000b70d  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000b711  mov     rdx, rsi; unsigned __int16 *
0x14000b714  test    rcx, rcx
0x14000b717  jz      short loc_14000B72F
0x14000b719  mov     [rsp+278h+lpBuffer], rcx
0x14000b71e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000b725  mov     rcx, rax; this
0x14000b728  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b72d  jmp     short loc_14000B751
0x14000b72f  mov     rcx, rax; this
0x14000b732  test    r9, r9
0x14000b735  jz      short loc_14000B745
0x14000b737  lea     r8, aHs; "[%hs]\n"
0x14000b73e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b743  jmp     short loc_14000B751
0x14000b745  lea     r8, asc_14001C5D0; "\n"
0x14000b74c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b751  xor     eax, eax
0x14000b753  mov     rcx, [rsp+278h+var_38]
0x14000b75b  xor     rcx, rsp; StackCookie
0x14000b75e  call    __security_check_cookie
0x14000b763  mov     rbx, [rsp+278h+arg_18]
0x14000b76b  add     rsp, 250h
0x14000b772  pop     r15
0x14000b774  pop     r14
0x14000b776  pop     rdi
0x14000b777  pop     rsi
0x14000b778  pop     rbp
0x14000b779  retn
```
