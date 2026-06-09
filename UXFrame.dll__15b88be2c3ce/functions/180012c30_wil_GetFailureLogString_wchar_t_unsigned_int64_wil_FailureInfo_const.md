# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180012c30`
- end: `0x180012ee6`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180013878`
- `0x180052d50`
- `0x180055500`

## callees

- `0x180002b20`
- `0x180003cf6`
- `0x180012c30`
- `0x180013b54`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012de3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012de3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012d62`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180012d62`

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
          v7 = (const char *)&word_18005FD0E;
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
0x180012c30  mov     [rsp+arg_18], rbx
0x180012c35  push    rbp
0x180012c36  push    rsi
0x180012c37  push    rdi
0x180012c38  push    r14
0x180012c3a  push    r15
0x180012c3c  sub     rsp, 250h
0x180012c43  mov     rax, cs:__security_cookie
0x180012c4a  xor     rax, rsp
0x180012c4d  mov     [rsp+278h+var_38], rax
0x180012c55  mov     rbx, r8
0x180012c58  mov     rsi, rdx
0x180012c5b  mov     r14, rcx
0x180012c5e  xor     r15d, r15d
0x180012c61  test    rdx, rdx
0x180012c64  jz      loc_180012EBD
0x180012c6a  test    rcx, rcx
0x180012c6d  jz      loc_180012EBD
0x180012c73  mov     [rcx], r15w
0x180012c77  mov     rax, cs:g_pfnResultLoggingCallback
0x180012c7e  test    rax, rax
0x180012c81  jz      short loc_180012CA4
0x180012c83  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180012c8a  jz      short loc_180012CA4
0x180012c8c  mov     r8, rdx
0x180012c8f  mov     rdx, rcx
0x180012c92  mov     rcx, rbx
0x180012c95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012c9a  cmp     [r14], r15w
0x180012c9e  jnz     loc_180012EBD
0x180012ca4  mov     ecx, [rbx]
0x180012ca6  mov     bpl, 8
0x180012ca9  test    ecx, ecx
0x180012cab  jz      short loc_180012CF6
0x180012cad  sub     ecx, 1
0x180012cb0  jz      short loc_180012CDE
0x180012cb2  sub     ecx, 1
0x180012cb5  jz      short loc_180012CCE
0x180012cb7  cmp     ecx, 1
0x180012cba  jz      short loc_180012CC5
0x180012cbc  lea     rdi, word_18005FD0E
0x180012cc3  jmp     short loc_180012CFD
0x180012cc5  lea     rdi, aFailfast; "FailFast"
0x180012ccc  jmp     short loc_180012CFD
0x180012cce  lea     rax, aLoghr; "LogHr"
0x180012cd5  lea     rdi, aLognt; "LogNt"
0x180012cdc  jmp     short loc_180012CEC
0x180012cde  lea     rax, aReturnhr; "ReturnHr"
0x180012ce5  lea     rdi, aReturnnt; "ReturnNt"
0x180012cec  test    [rbx+4], bpl
0x180012cf0  cmovz   rdi, rax
0x180012cf4  jmp     short loc_180012CFD
0x180012cf6  lea     rdi, aException; "Exception"
0x180012cfd  xor     edx, edx; Val
0x180012cff  mov     r8d, 200h; Size
0x180012d05  lea     rcx, [rsp+278h+Buffer]; void *
0x180012d0a  call    memset_0
0x180012d0f  test    [rbx+4], bpl
0x180012d13  jz      short loc_180012D38
0x180012d15  mov     ebp, [rbx+0Ch]
0x180012d18  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180012d1f  test    rax, rax
0x180012d22  jz      short loc_180012D68
0x180012d24  mov     r8d, 100h
0x180012d2a  lea     rdx, [rsp+278h+Buffer]
0x180012d2f  mov     ecx, ebp
0x180012d31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d36  jmp     short loc_180012D68
0x180012d38  mov     ebp, [rbx+8]
0x180012d3b  mov     [rsp+278h+Arguments], r15; Arguments
0x180012d40  mov     [rsp+278h+nSize], 100h; nSize
0x180012d48  lea     rax, [rsp+278h+Buffer]
0x180012d4d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180012d52  mov     r9d, 400h; dwLanguageId
0x180012d58  mov     r8d, ebp; dwMessageId
0x180012d5b  xor     edx, edx; lpSource
0x180012d5d  mov     ecx, 1200h; dwFlags
0x180012d62  call    cs:__imp_FormatMessageW
0x180012d68  lea     rsi, [r14+rsi*2]
0x180012d6c  mov     r9, [rbx+38h]; wchar_t *
0x180012d70  mov     rax, [rbx+88h]
0x180012d77  mov     rcx, [rbx+80h]
0x180012d7e  mov     rdx, rsi; wchar_t *
0x180012d81  test    r9, r9
0x180012d84  jz      short loc_180012DA8
0x180012d86  mov     [rsp+278h+Arguments], rax
0x180012d8b  mov     qword ptr [rsp+278h+nSize], rcx
0x180012d90  mov     eax, [rbx+40h]
0x180012d93  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012d97  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180012d9e  mov     rcx, r14; this
0x180012da1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012da6  jmp     short loc_180012DBF
0x180012da8  mov     [rsp+278h+lpBuffer], rax
0x180012dad  mov     r9, rcx; wchar_t *
0x180012db0  lea     r8, aHsP; "%hs!%p: "
0x180012db7  mov     rcx, r14; this
0x180012dba  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012dbf  mov     r14, rax
0x180012dc2  mov     r9, [rbx+90h]; wchar_t *
0x180012dc9  test    r9, r9
0x180012dcc  jz      short loc_180012DE3
0x180012dce  lea     r8, aCallerP; "(caller: %p) "
0x180012dd5  mov     rdx, rsi; wchar_t *
0x180012dd8  mov     rcx, rax; this
0x180012ddb  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012de0  mov     r14, rax
0x180012de3  call    cs:__imp_GetCurrentThreadId
0x180012de9  lea     rcx, [rsp+278h+Buffer]
0x180012dee  mov     [rsp+278h+var_240], rcx
0x180012df3  mov     dword ptr [rsp+278h+Arguments], ebp
0x180012df7  mov     [rsp+278h+nSize], eax
0x180012dfb  mov     eax, [rbx+44h]
0x180012dfe  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180012e02  mov     r9, rdi; wchar_t *
0x180012e05  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180012e0c  mov     rdx, rsi; wchar_t *
0x180012e0f  mov     rcx, r14; this
0x180012e12  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012e17  cmp     [rbx+18h], r15
0x180012e1b  jnz     short loc_180012E2D
0x180012e1d  cmp     [rbx+48h], r15
0x180012e21  jnz     short loc_180012E2D
0x180012e23  cmp     [rbx+30h], r15
0x180012e27  jz      loc_180012EBD
0x180012e2d  lea     r8, asc_18005FC30; "    "
0x180012e34  mov     rdx, rsi; wchar_t *
0x180012e37  mov     rcx, rax; this
0x180012e3a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012e3f  mov     r9, [rbx+18h]; wchar_t *
0x180012e43  test    r9, r9
0x180012e46  jz      short loc_180012E5A
0x180012e48  lea     r8, aMsgWs; "Msg:[%ws] "
0x180012e4f  mov     rdx, rsi; wchar_t *
0x180012e52  mov     rcx, rax; this
0x180012e55  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012e5a  mov     r9, [rbx+48h]; wchar_t *
0x180012e5e  test    r9, r9
0x180012e61  jz      short loc_180012E75
0x180012e63  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180012e6a  mov     rdx, rsi; wchar_t *
0x180012e6d  mov     rcx, rax; this
0x180012e70  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012e75  mov     rcx, [rbx+28h]
0x180012e79  mov     r9, [rbx+30h]; wchar_t *
0x180012e7d  mov     rdx, rsi; wchar_t *
0x180012e80  test    rcx, rcx
0x180012e83  jz      short loc_180012E9B
0x180012e85  mov     [rsp+278h+lpBuffer], rcx
0x180012e8a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180012e91  mov     rcx, rax; this
0x180012e94  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012e99  jmp     short loc_180012EBD
0x180012e9b  mov     rcx, rax; this
0x180012e9e  test    r9, r9
0x180012ea1  jz      short loc_180012EB1
0x180012ea3  lea     r8, aHs; "[%hs]\n"
0x180012eaa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012eaf  jmp     short loc_180012EBD
0x180012eb1  lea     r8, asc_18005FCA8; "\n"
0x180012eb8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180012ebd  xor     eax, eax
0x180012ebf  mov     rcx, [rsp+278h+var_38]
0x180012ec7  xor     rcx, rsp; StackCookie
0x180012eca  call    __security_check_cookie
0x180012ecf  mov     rbx, [rsp+278h+arg_18]
0x180012ed7  add     rsp, 250h
0x180012ede  pop     r15
0x180012ee0  pop     r14
0x180012ee2  pop     rdi
0x180012ee3  pop     rsi
0x180012ee4  pop     rbp
0x180012ee5  retn
```
