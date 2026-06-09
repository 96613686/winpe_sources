# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800aa334`
- end: `0x1800aa5ea`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x1800aaf1c`
- `0x1800ae120`

## callees

- `0x180078968`
- `0x1800789c0`
- `0x1800aa334`
- `0x1800ab218`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa4e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800aa4e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800aa466`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800aa466`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&Src;
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
0x1800aa334  mov     [rsp+arg_18], rbx
0x1800aa339  push    rbp
0x1800aa33a  push    rsi
0x1800aa33b  push    rdi
0x1800aa33c  push    r14
0x1800aa33e  push    r15
0x1800aa340  sub     rsp, 250h
0x1800aa347  mov     rax, cs:__security_cookie
0x1800aa34e  xor     rax, rsp
0x1800aa351  mov     [rsp+278h+var_38], rax
0x1800aa359  mov     rbx, r8
0x1800aa35c  mov     rsi, rdx
0x1800aa35f  mov     r14, rcx
0x1800aa362  xor     r15d, r15d
0x1800aa365  test    rdx, rdx
0x1800aa368  jz      loc_1800AA5C1
0x1800aa36e  test    rcx, rcx
0x1800aa371  jz      loc_1800AA5C1
0x1800aa377  mov     [rcx], r15w
0x1800aa37b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800aa382  test    rax, rax
0x1800aa385  jz      short loc_1800AA3A8
0x1800aa387  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800aa38e  jz      short loc_1800AA3A8
0x1800aa390  mov     r8, rdx
0x1800aa393  mov     rdx, rcx
0x1800aa396  mov     rcx, rbx
0x1800aa399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa39e  cmp     [r14], r15w
0x1800aa3a2  jnz     loc_1800AA5C1
0x1800aa3a8  mov     ecx, [rbx]
0x1800aa3aa  mov     bpl, 8
0x1800aa3ad  test    ecx, ecx
0x1800aa3af  jz      short loc_1800AA3FA
0x1800aa3b1  sub     ecx, 1
0x1800aa3b4  jz      short loc_1800AA3E2
0x1800aa3b6  sub     ecx, 1
0x1800aa3b9  jz      short loc_1800AA3D2
0x1800aa3bb  cmp     ecx, 1
0x1800aa3be  jz      short loc_1800AA3C9
0x1800aa3c0  lea     rdi, Src
0x1800aa3c7  jmp     short loc_1800AA401
0x1800aa3c9  lea     rdi, aFailfast; "FailFast"
0x1800aa3d0  jmp     short loc_1800AA401
0x1800aa3d2  lea     rax, aLoghr; "LogHr"
0x1800aa3d9  lea     rdi, aLognt; "LogNt"
0x1800aa3e0  jmp     short loc_1800AA3F0
0x1800aa3e2  lea     rax, aReturnhr; "ReturnHr"
0x1800aa3e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800aa3f0  test    [rbx+4], bpl
0x1800aa3f4  cmovz   rdi, rax
0x1800aa3f8  jmp     short loc_1800AA401
0x1800aa3fa  lea     rdi, aException; "Exception"
0x1800aa401  xor     edx, edx; Val
0x1800aa403  mov     r8d, 200h; Size
0x1800aa409  lea     rcx, [rsp+278h+Buffer]; void *
0x1800aa40e  call    memset_0
0x1800aa413  test    [rbx+4], bpl
0x1800aa417  jz      short loc_1800AA43C
0x1800aa419  mov     ebp, [rbx+0Ch]
0x1800aa41c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800aa423  test    rax, rax
0x1800aa426  jz      short loc_1800AA46C
0x1800aa428  mov     r8d, 100h
0x1800aa42e  lea     rdx, [rsp+278h+Buffer]
0x1800aa433  mov     ecx, ebp
0x1800aa435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800aa43a  jmp     short loc_1800AA46C
0x1800aa43c  mov     ebp, [rbx+8]
0x1800aa43f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800aa444  mov     [rsp+278h+nSize], 100h; nSize
0x1800aa44c  lea     rax, [rsp+278h+Buffer]
0x1800aa451  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800aa456  mov     r9d, 400h; dwLanguageId
0x1800aa45c  mov     r8d, ebp; dwMessageId
0x1800aa45f  xor     edx, edx; lpSource
0x1800aa461  mov     ecx, 1200h; dwFlags
0x1800aa466  call    cs:__imp_FormatMessageW
0x1800aa46c  lea     rsi, [r14+rsi*2]
0x1800aa470  mov     r9, [rbx+38h]; wchar_t *
0x1800aa474  mov     rax, [rbx+88h]
0x1800aa47b  mov     rcx, [rbx+80h]
0x1800aa482  mov     rdx, rsi; wchar_t *
0x1800aa485  test    r9, r9
0x1800aa488  jz      short loc_1800AA4AC
0x1800aa48a  mov     [rsp+278h+Arguments], rax
0x1800aa48f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800aa494  mov     eax, [rbx+40h]
0x1800aa497  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800aa49b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800aa4a2  mov     rcx, r14; this
0x1800aa4a5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa4aa  jmp     short loc_1800AA4C3
0x1800aa4ac  mov     [rsp+278h+lpBuffer], rax
0x1800aa4b1  mov     r9, rcx; wchar_t *
0x1800aa4b4  lea     r8, aHsP; "%hs!%p: "
0x1800aa4bb  mov     rcx, r14; this
0x1800aa4be  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa4c3  mov     r14, rax
0x1800aa4c6  mov     r9, [rbx+90h]; wchar_t *
0x1800aa4cd  test    r9, r9
0x1800aa4d0  jz      short loc_1800AA4E7
0x1800aa4d2  lea     r8, aCallerP; "(caller: %p) "
0x1800aa4d9  mov     rdx, rsi; wchar_t *
0x1800aa4dc  mov     rcx, rax; this
0x1800aa4df  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa4e4  mov     r14, rax
0x1800aa4e7  call    cs:__imp_GetCurrentThreadId
0x1800aa4ed  lea     rcx, [rsp+278h+Buffer]
0x1800aa4f2  mov     [rsp+278h+var_240], rcx
0x1800aa4f7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800aa4fb  mov     [rsp+278h+nSize], eax
0x1800aa4ff  mov     eax, [rbx+44h]
0x1800aa502  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800aa506  mov     r9, rdi; wchar_t *
0x1800aa509  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800aa510  mov     rdx, rsi; wchar_t *
0x1800aa513  mov     rcx, r14; this
0x1800aa516  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa51b  cmp     [rbx+18h], r15
0x1800aa51f  jnz     short loc_1800AA531
0x1800aa521  cmp     [rbx+48h], r15
0x1800aa525  jnz     short loc_1800AA531
0x1800aa527  cmp     [rbx+30h], r15
0x1800aa52b  jz      loc_1800AA5C1
0x1800aa531  lea     r8, asc_1800C16E0; "    "
0x1800aa538  mov     rdx, rsi; wchar_t *
0x1800aa53b  mov     rcx, rax; this
0x1800aa53e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa543  mov     r9, [rbx+18h]; wchar_t *
0x1800aa547  test    r9, r9
0x1800aa54a  jz      short loc_1800AA55E
0x1800aa54c  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800aa553  mov     rdx, rsi; wchar_t *
0x1800aa556  mov     rcx, rax; this
0x1800aa559  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa55e  mov     r9, [rbx+48h]; wchar_t *
0x1800aa562  test    r9, r9
0x1800aa565  jz      short loc_1800AA579
0x1800aa567  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800aa56e  mov     rdx, rsi; wchar_t *
0x1800aa571  mov     rcx, rax; this
0x1800aa574  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa579  mov     rcx, [rbx+28h]
0x1800aa57d  mov     r9, [rbx+30h]; wchar_t *
0x1800aa581  mov     rdx, rsi; wchar_t *
0x1800aa584  test    rcx, rcx
0x1800aa587  jz      short loc_1800AA59F
0x1800aa589  mov     [rsp+278h+lpBuffer], rcx
0x1800aa58e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800aa595  mov     rcx, rax; this
0x1800aa598  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa59d  jmp     short loc_1800AA5C1
0x1800aa59f  mov     rcx, rax; this
0x1800aa5a2  test    r9, r9
0x1800aa5a5  jz      short loc_1800AA5B5
0x1800aa5a7  lea     r8, aHs; "[%hs]\n"
0x1800aa5ae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa5b3  jmp     short loc_1800AA5C1
0x1800aa5b5  lea     r8, asc_1800C1758; "\n"
0x1800aa5bc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800aa5c1  xor     eax, eax
0x1800aa5c3  mov     rcx, [rsp+278h+var_38]
0x1800aa5cb  xor     rcx, rsp; StackCookie
0x1800aa5ce  call    __security_check_cookie
0x1800aa5d3  mov     rbx, [rsp+278h+arg_18]
0x1800aa5db  add     rsp, 250h
0x1800aa5e2  pop     r15
0x1800aa5e4  pop     r14
0x1800aa5e6  pop     rdi
0x1800aa5e7  pop     rsi
0x1800aa5e8  pop     rbp
0x1800aa5e9  retn
```
