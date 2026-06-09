# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003b7e8`
- end: `0x18003ba9e`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18003c2bc`
- `0x180094b5c`
- `0x1800b478c`
- `0x1800b5020`

## callees

- `0x1800049e0`
- `0x180005e44`
- `0x18003b7e8`
- `0x18003c5dc`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003b91a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003b91a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b99b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b99b`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
          v7 = (const char *)&word_1801017B2;
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x18003b7e8  mov     [rsp+arg_18], rbx
0x18003b7ed  push    rbp
0x18003b7ee  push    rsi
0x18003b7ef  push    rdi
0x18003b7f0  push    r14
0x18003b7f2  push    r15
0x18003b7f4  sub     rsp, 250h
0x18003b7fb  mov     rax, cs:__security_cookie
0x18003b802  xor     rax, rsp
0x18003b805  mov     [rsp+278h+var_38], rax
0x18003b80d  mov     rbx, r8
0x18003b810  mov     rsi, rdx
0x18003b813  mov     r14, rcx
0x18003b816  xor     r15d, r15d
0x18003b819  test    rdx, rdx
0x18003b81c  jz      loc_18003BA75
0x18003b822  test    rcx, rcx
0x18003b825  jz      loc_18003BA75
0x18003b82b  mov     [rcx], r15w
0x18003b82f  mov     rax, cs:g_pfnResultLoggingCallback
0x18003b836  test    rax, rax
0x18003b839  jz      short loc_18003B85C
0x18003b83b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003b842  jz      short loc_18003B85C
0x18003b844  mov     r8, rdx
0x18003b847  mov     rdx, rcx
0x18003b84a  mov     rcx, rbx
0x18003b84d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b852  cmp     [r14], r15w
0x18003b856  jnz     loc_18003BA75
0x18003b85c  mov     ecx, [rbx]
0x18003b85e  mov     bpl, 8
0x18003b861  test    ecx, ecx
0x18003b863  jz      short loc_18003B8AE
0x18003b865  sub     ecx, 1
0x18003b868  jz      short loc_18003B896
0x18003b86a  sub     ecx, 1
0x18003b86d  jz      short loc_18003B886
0x18003b86f  cmp     ecx, 1
0x18003b872  jz      short loc_18003B87D
0x18003b874  lea     rdi, word_1801017B2
0x18003b87b  jmp     short loc_18003B8B5
0x18003b87d  lea     rdi, aFailfast; "FailFast"
0x18003b884  jmp     short loc_18003B8B5
0x18003b886  lea     rax, aLoghr; "LogHr"
0x18003b88d  lea     rdi, aLognt; "LogNt"
0x18003b894  jmp     short loc_18003B8A4
0x18003b896  lea     rax, aReturnhr; "ReturnHr"
0x18003b89d  lea     rdi, aReturnnt; "ReturnNt"
0x18003b8a4  test    [rbx+4], bpl
0x18003b8a8  cmovz   rdi, rax
0x18003b8ac  jmp     short loc_18003B8B5
0x18003b8ae  lea     rdi, aException; "Exception"
0x18003b8b5  xor     edx, edx; Val
0x18003b8b7  mov     r8d, 200h; Size
0x18003b8bd  lea     rcx, [rsp+278h+Buffer]; void *
0x18003b8c2  call    memset_0
0x18003b8c7  test    [rbx+4], bpl
0x18003b8cb  jz      short loc_18003B8F0
0x18003b8cd  mov     ebp, [rbx+0Ch]
0x18003b8d0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18003b8d7  test    rax, rax
0x18003b8da  jz      short loc_18003B920
0x18003b8dc  mov     r8d, 100h
0x18003b8e2  lea     rdx, [rsp+278h+Buffer]
0x18003b8e7  mov     ecx, ebp
0x18003b8e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b8ee  jmp     short loc_18003B920
0x18003b8f0  mov     ebp, [rbx+8]
0x18003b8f3  mov     [rsp+278h+Arguments], r15; Arguments
0x18003b8f8  mov     [rsp+278h+nSize], 100h; nSize
0x18003b900  lea     rax, [rsp+278h+Buffer]
0x18003b905  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003b90a  mov     r9d, 400h; dwLanguageId
0x18003b910  mov     r8d, ebp; dwMessageId
0x18003b913  xor     edx, edx; lpSource
0x18003b915  mov     ecx, 1200h; dwFlags
0x18003b91a  call    cs:__imp_FormatMessageW
0x18003b920  lea     rsi, [r14+rsi*2]
0x18003b924  mov     r9, [rbx+38h]; wchar_t *
0x18003b928  mov     rax, [rbx+88h]
0x18003b92f  mov     rcx, [rbx+80h]
0x18003b936  mov     rdx, rsi; wchar_t *
0x18003b939  test    r9, r9
0x18003b93c  jz      short loc_18003B960
0x18003b93e  mov     [rsp+278h+Arguments], rax
0x18003b943  mov     qword ptr [rsp+278h+nSize], rcx
0x18003b948  mov     eax, [rbx+40h]
0x18003b94b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003b94f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003b956  mov     rcx, r14; this
0x18003b959  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003b95e  jmp     short loc_18003B977
0x18003b960  mov     [rsp+278h+lpBuffer], rax
0x18003b965  mov     r9, rcx; wchar_t *
0x18003b968  lea     r8, aHsP; "%hs!%p: "
0x18003b96f  mov     rcx, r14; this
0x18003b972  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003b977  mov     r14, rax
0x18003b97a  mov     r9, [rbx+90h]; wchar_t *
0x18003b981  test    r9, r9
0x18003b984  jz      short loc_18003B99B
0x18003b986  lea     r8, aCallerP; "(caller: %p) "
0x18003b98d  mov     rdx, rsi; wchar_t *
0x18003b990  mov     rcx, rax; this
0x18003b993  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003b998  mov     r14, rax
0x18003b99b  call    cs:__imp_GetCurrentThreadId
0x18003b9a1  lea     rcx, [rsp+278h+Buffer]
0x18003b9a6  mov     [rsp+278h+var_240], rcx
0x18003b9ab  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003b9af  mov     [rsp+278h+nSize], eax
0x18003b9b3  mov     eax, [rbx+44h]
0x18003b9b6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003b9ba  mov     r9, rdi; wchar_t *
0x18003b9bd  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003b9c4  mov     rdx, rsi; wchar_t *
0x18003b9c7  mov     rcx, r14; this
0x18003b9ca  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003b9cf  cmp     [rbx+18h], r15
0x18003b9d3  jnz     short loc_18003B9E5
0x18003b9d5  cmp     [rbx+48h], r15
0x18003b9d9  jnz     short loc_18003B9E5
0x18003b9db  cmp     [rbx+30h], r15
0x18003b9df  jz      loc_18003BA75
0x18003b9e5  lea     r8, asc_180103660; "    "
0x18003b9ec  mov     rdx, rsi; wchar_t *
0x18003b9ef  mov     rcx, rax; this
0x18003b9f2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003b9f7  mov     r9, [rbx+18h]; wchar_t *
0x18003b9fb  test    r9, r9
0x18003b9fe  jz      short loc_18003BA12
0x18003ba00  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003ba07  mov     rdx, rsi; wchar_t *
0x18003ba0a  mov     rcx, rax; this
0x18003ba0d  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003ba12  mov     r9, [rbx+48h]; wchar_t *
0x18003ba16  test    r9, r9
0x18003ba19  jz      short loc_18003BA2D
0x18003ba1b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003ba22  mov     rdx, rsi; wchar_t *
0x18003ba25  mov     rcx, rax; this
0x18003ba28  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003ba2d  mov     rcx, [rbx+28h]
0x18003ba31  mov     r9, [rbx+30h]; wchar_t *
0x18003ba35  mov     rdx, rsi; wchar_t *
0x18003ba38  test    rcx, rcx
0x18003ba3b  jz      short loc_18003BA53
0x18003ba3d  mov     [rsp+278h+lpBuffer], rcx
0x18003ba42  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003ba49  mov     rcx, rax; this
0x18003ba4c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003ba51  jmp     short loc_18003BA75
0x18003ba53  mov     rcx, rax; this
0x18003ba56  test    r9, r9
0x18003ba59  jz      short loc_18003BA69
0x18003ba5b  lea     r8, aHs; "[%hs]\n"
0x18003ba62  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003ba67  jmp     short loc_18003BA75
0x18003ba69  lea     r8, asc_180103710; "\n"
0x18003ba70  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003ba75  xor     eax, eax
0x18003ba77  mov     rcx, [rsp+278h+var_38]
0x18003ba7f  xor     rcx, rsp; StackCookie
0x18003ba82  call    __security_check_cookie
0x18003ba87  mov     rbx, [rsp+278h+arg_18]
0x18003ba8f  add     rsp, 250h
0x18003ba96  pop     r15
0x18003ba98  pop     r14
0x18003ba9a  pop     rdi
0x18003ba9b  pop     rsi
0x18003ba9c  pop     rbp
0x18003ba9d  retn
```
