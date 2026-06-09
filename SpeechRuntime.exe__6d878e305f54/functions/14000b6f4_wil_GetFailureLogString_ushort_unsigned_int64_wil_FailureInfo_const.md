# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000b6f4`
- end: `0x14000b9aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140006dac`
- `0x14000c948`
- `0x14000cf68`
- `0x140011380`

## callees

- `0x140002d30`
- `0x140003848`
- `0x14000b6f4`
- `0x14000cc48`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b8a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000b8a7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000b826`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x14000b826`

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
          v7 = (const char *)&word_140034BFE;
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
0x14000b6f4  mov     [rsp+arg_18], rbx
0x14000b6f9  push    rbp
0x14000b6fa  push    rsi
0x14000b6fb  push    rdi
0x14000b6fc  push    r14
0x14000b6fe  push    r15
0x14000b700  sub     rsp, 250h
0x14000b707  mov     rax, cs:__security_cookie
0x14000b70e  xor     rax, rsp
0x14000b711  mov     [rsp+278h+var_38], rax
0x14000b719  mov     rbx, r8
0x14000b71c  mov     rsi, rdx
0x14000b71f  mov     r14, rcx
0x14000b722  xor     r15d, r15d
0x14000b725  test    rdx, rdx
0x14000b728  jz      loc_14000B981
0x14000b72e  test    rcx, rcx
0x14000b731  jz      loc_14000B981
0x14000b737  mov     [rcx], r15w
0x14000b73b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b742  test    rax, rax
0x14000b745  jz      short loc_14000B768
0x14000b747  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000b74e  jz      short loc_14000B768
0x14000b750  mov     r8, rdx
0x14000b753  mov     rdx, rcx
0x14000b756  mov     rcx, rbx
0x14000b759  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b75e  cmp     [r14], r15w
0x14000b762  jnz     loc_14000B981
0x14000b768  mov     ecx, [rbx]
0x14000b76a  mov     bpl, 8
0x14000b76d  test    ecx, ecx
0x14000b76f  jz      short loc_14000B7BA
0x14000b771  sub     ecx, 1
0x14000b774  jz      short loc_14000B7A2
0x14000b776  sub     ecx, 1
0x14000b779  jz      short loc_14000B792
0x14000b77b  cmp     ecx, 1
0x14000b77e  jz      short loc_14000B789
0x14000b780  lea     rdi, word_140034BFE
0x14000b787  jmp     short loc_14000B7C1
0x14000b789  lea     rdi, aFailfast; "FailFast"
0x14000b790  jmp     short loc_14000B7C1
0x14000b792  lea     rax, aLoghr; "LogHr"
0x14000b799  lea     rdi, aLognt; "LogNt"
0x14000b7a0  jmp     short loc_14000B7B0
0x14000b7a2  lea     rax, aReturnhr; "ReturnHr"
0x14000b7a9  lea     rdi, aReturnnt; "ReturnNt"
0x14000b7b0  test    [rbx+4], bpl
0x14000b7b4  cmovz   rdi, rax
0x14000b7b8  jmp     short loc_14000B7C1
0x14000b7ba  lea     rdi, aException; "Exception"
0x14000b7c1  xor     edx, edx; Val
0x14000b7c3  mov     r8d, 200h; Size
0x14000b7c9  lea     rcx, [rsp+278h+Buffer]; void *
0x14000b7ce  call    memset_0
0x14000b7d3  test    [rbx+4], bpl
0x14000b7d7  jz      short loc_14000B7FC
0x14000b7d9  mov     ebp, [rbx+0Ch]
0x14000b7dc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x14000b7e3  test    rax, rax
0x14000b7e6  jz      short loc_14000B82C
0x14000b7e8  mov     r8d, 100h
0x14000b7ee  lea     rdx, [rsp+278h+Buffer]
0x14000b7f3  mov     ecx, ebp
0x14000b7f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b7fa  jmp     short loc_14000B82C
0x14000b7fc  mov     ebp, [rbx+8]
0x14000b7ff  mov     [rsp+278h+Arguments], r15; Arguments
0x14000b804  mov     [rsp+278h+nSize], 100h; nSize
0x14000b80c  lea     rax, [rsp+278h+Buffer]
0x14000b811  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000b816  mov     r9d, 400h; dwLanguageId
0x14000b81c  mov     r8d, ebp; dwMessageId
0x14000b81f  xor     edx, edx; lpSource
0x14000b821  mov     ecx, 1200h; dwFlags
0x14000b826  call    cs:__imp_FormatMessageW
0x14000b82c  lea     rsi, [r14+rsi*2]
0x14000b830  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000b834  mov     rax, [rbx+88h]
0x14000b83b  mov     rcx, [rbx+80h]
0x14000b842  mov     rdx, rsi; unsigned __int16 *
0x14000b845  test    r9, r9
0x14000b848  jz      short loc_14000B86C
0x14000b84a  mov     [rsp+278h+Arguments], rax
0x14000b84f  mov     qword ptr [rsp+278h+nSize], rcx
0x14000b854  mov     eax, [rbx+40h]
0x14000b857  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b85b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000b862  mov     rcx, r14; this
0x14000b865  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b86a  jmp     short loc_14000B883
0x14000b86c  mov     [rsp+278h+lpBuffer], rax
0x14000b871  mov     r9, rcx; unsigned __int16 *
0x14000b874  lea     r8, aHsP; "%hs!%p: "
0x14000b87b  mov     rcx, r14; this
0x14000b87e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b883  mov     r14, rax
0x14000b886  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000b88d  test    r9, r9
0x14000b890  jz      short loc_14000B8A7
0x14000b892  lea     r8, aCallerP; "(caller: %p) "
0x14000b899  mov     rdx, rsi; unsigned __int16 *
0x14000b89c  mov     rcx, rax; this
0x14000b89f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b8a4  mov     r14, rax
0x14000b8a7  call    cs:__imp_GetCurrentThreadId
0x14000b8ad  lea     rcx, [rsp+278h+Buffer]
0x14000b8b2  mov     [rsp+278h+var_240], rcx
0x14000b8b7  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000b8bb  mov     [rsp+278h+nSize], eax
0x14000b8bf  mov     eax, [rbx+44h]
0x14000b8c2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000b8c6  mov     r9, rdi; unsigned __int16 *
0x14000b8c9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x14000b8d0  mov     rdx, rsi; unsigned __int16 *
0x14000b8d3  mov     rcx, r14; this
0x14000b8d6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b8db  cmp     [rbx+18h], r15
0x14000b8df  jnz     short loc_14000B8F1
0x14000b8e1  cmp     [rbx+48h], r15
0x14000b8e5  jnz     short loc_14000B8F1
0x14000b8e7  cmp     [rbx+30h], r15
0x14000b8eb  jz      loc_14000B981
0x14000b8f1  lea     r8, asc_140034D78; "    "
0x14000b8f8  mov     rdx, rsi; unsigned __int16 *
0x14000b8fb  mov     rcx, rax; this
0x14000b8fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b903  mov     r9, [rbx+18h]; unsigned __int16 *
0x14000b907  test    r9, r9
0x14000b90a  jz      short loc_14000B91E
0x14000b90c  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000b913  mov     rdx, rsi; unsigned __int16 *
0x14000b916  mov     rcx, rax; this
0x14000b919  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b91e  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000b922  test    r9, r9
0x14000b925  jz      short loc_14000B939
0x14000b927  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000b92e  mov     rdx, rsi; unsigned __int16 *
0x14000b931  mov     rcx, rax; this
0x14000b934  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b939  mov     rcx, [rbx+28h]
0x14000b93d  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000b941  mov     rdx, rsi; unsigned __int16 *
0x14000b944  test    rcx, rcx
0x14000b947  jz      short loc_14000B95F
0x14000b949  mov     [rsp+278h+lpBuffer], rcx
0x14000b94e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000b955  mov     rcx, rax; this
0x14000b958  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b95d  jmp     short loc_14000B981
0x14000b95f  mov     rcx, rax; this
0x14000b962  test    r9, r9
0x14000b965  jz      short loc_14000B975
0x14000b967  lea     r8, aHs; "[%hs]\n"
0x14000b96e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b973  jmp     short loc_14000B981
0x14000b975  lea     r8, asc_140034DF0; "\n"
0x14000b97c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000b981  xor     eax, eax
0x14000b983  mov     rcx, [rsp+278h+var_38]
0x14000b98b  xor     rcx, rsp; StackCookie
0x14000b98e  call    __security_check_cookie
0x14000b993  mov     rbx, [rsp+278h+arg_18]
0x14000b99b  add     rsp, 250h
0x14000b9a2  pop     r15
0x14000b9a4  pop     r14
0x14000b9a6  pop     rdi
0x14000b9a7  pop     rsi
0x14000b9a8  pop     rbp
0x14000b9a9  retn
```
