# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800f0494`
- end: `0x1800f0755`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800ef668`
- `0x1800f0cac`
- `0x1800f2040`

## callees

- `0x1800d5fe4`
- `0x1800f0494`
- `0x1800f0fb4`
- `0x180117740`
- `0x18012a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0652`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800f0652`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800f05d1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800f05d1`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

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
          v7 = (const char *)&word_18013A0B6;
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
                          Buffer,
                          -2);
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
0x1800f0494  mov     rax, rsp
0x1800f0497  push    rbp
0x1800f0498  push    rsi
0x1800f0499  push    rdi
0x1800f049a  push    r14
0x1800f049c  push    r15
0x1800f049e  sub     rsp, 260h
0x1800f04a5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800f04ae  mov     [rax+20h], rbx
0x1800f04b2  mov     rax, cs:__security_cookie
0x1800f04b9  xor     rax, rsp
0x1800f04bc  mov     [rsp+288h+var_38], rax
0x1800f04c4  mov     rbx, r8
0x1800f04c7  mov     rsi, rdx
0x1800f04ca  mov     r14, rcx
0x1800f04cd  xor     r15d, r15d
0x1800f04d0  test    rdx, rdx
0x1800f04d3  jz      loc_1800F072C
0x1800f04d9  test    rcx, rcx
0x1800f04dc  jz      loc_1800F072C
0x1800f04e2  mov     [rcx], r15w
0x1800f04e6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800f04ed  test    rax, rax
0x1800f04f0  jz      short loc_1800F0513
0x1800f04f2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800f04f9  jz      short loc_1800F0513
0x1800f04fb  mov     r8, rdx
0x1800f04fe  mov     rdx, rcx
0x1800f0501  mov     rcx, rbx
0x1800f0504  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f0509  cmp     [r14], r15w
0x1800f050d  jnz     loc_1800F072C
0x1800f0513  mov     ecx, [rbx]
0x1800f0515  mov     bpl, 8
0x1800f0518  test    ecx, ecx
0x1800f051a  jz      short loc_1800F0565
0x1800f051c  sub     ecx, 1
0x1800f051f  jz      short loc_1800F054D
0x1800f0521  sub     ecx, 1
0x1800f0524  jz      short loc_1800F053D
0x1800f0526  cmp     ecx, 1
0x1800f0529  jz      short loc_1800F0534
0x1800f052b  lea     rdi, word_18013A0B6
0x1800f0532  jmp     short loc_1800F056C
0x1800f0534  lea     rdi, aFailfast; "FailFast"
0x1800f053b  jmp     short loc_1800F056C
0x1800f053d  lea     rax, aLoghr; "LogHr"
0x1800f0544  lea     rdi, aLognt; "LogNt"
0x1800f054b  jmp     short loc_1800F055B
0x1800f054d  lea     rax, aReturnhr; "ReturnHr"
0x1800f0554  lea     rdi, aReturnnt; "ReturnNt"
0x1800f055b  test    [rbx+4], bpl
0x1800f055f  cmovz   rdi, rax
0x1800f0563  jmp     short loc_1800F056C
0x1800f0565  lea     rdi, aException; "Exception"
0x1800f056c  xor     edx, edx; Val
0x1800f056e  mov     r8d, 200h; Size
0x1800f0574  lea     rcx, [rsp+288h+Buffer]; void *
0x1800f0579  call    memset_0
0x1800f057e  test    [rbx+4], bpl
0x1800f0582  jz      short loc_1800F05A7
0x1800f0584  mov     ebp, [rbx+0Ch]
0x1800f0587  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800f058e  test    rax, rax
0x1800f0591  jz      short loc_1800F05D7
0x1800f0593  mov     r8d, 100h
0x1800f0599  lea     rdx, [rsp+288h+Buffer]
0x1800f059e  mov     ecx, ebp
0x1800f05a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800f05a5  jmp     short loc_1800F05D7
0x1800f05a7  mov     ebp, [rbx+8]
0x1800f05aa  mov     [rsp+288h+Arguments], r15; Arguments
0x1800f05af  mov     [rsp+288h+nSize], 100h; nSize
0x1800f05b7  lea     rax, [rsp+288h+Buffer]
0x1800f05bc  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800f05c1  mov     r9d, 400h; dwLanguageId
0x1800f05c7  mov     r8d, ebp; dwMessageId
0x1800f05ca  xor     edx, edx; lpSource
0x1800f05cc  mov     ecx, 1200h; dwFlags
0x1800f05d1  call    cs:__imp_FormatMessageW
0x1800f05d7  lea     rsi, [r14+rsi*2]
0x1800f05db  mov     r9, [rbx+38h]; wchar_t *
0x1800f05df  mov     rax, [rbx+88h]
0x1800f05e6  mov     rcx, [rbx+80h]
0x1800f05ed  mov     rdx, rsi; wchar_t *
0x1800f05f0  test    r9, r9
0x1800f05f3  jz      short loc_1800F0617
0x1800f05f5  mov     [rsp+288h+Arguments], rax
0x1800f05fa  mov     qword ptr [rsp+288h+nSize], rcx
0x1800f05ff  mov     eax, [rbx+40h]
0x1800f0602  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800f0606  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800f060d  mov     rcx, r14; this
0x1800f0610  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0615  jmp     short loc_1800F062E
0x1800f0617  mov     [rsp+288h+lpBuffer], rax
0x1800f061c  mov     r9, rcx; wchar_t *
0x1800f061f  lea     r8, aHsP; "%hs!%p: "
0x1800f0626  mov     rcx, r14; this
0x1800f0629  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f062e  mov     r14, rax
0x1800f0631  mov     r9, [rbx+90h]; wchar_t *
0x1800f0638  test    r9, r9
0x1800f063b  jz      short loc_1800F0652
0x1800f063d  lea     r8, aCallerP; "(caller: %p) "
0x1800f0644  mov     rdx, rsi; wchar_t *
0x1800f0647  mov     rcx, rax; this
0x1800f064a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f064f  mov     r14, rax
0x1800f0652  call    cs:__imp_GetCurrentThreadId
0x1800f0658  lea     rcx, [rsp+288h+Buffer]
0x1800f065d  mov     [rsp+288h+var_250], rcx
0x1800f0662  mov     dword ptr [rsp+288h+Arguments], ebp
0x1800f0666  mov     [rsp+288h+nSize], eax
0x1800f066a  mov     eax, [rbx+44h]
0x1800f066d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800f0671  mov     r9, rdi; wchar_t *
0x1800f0674  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800f067b  mov     rdx, rsi; wchar_t *
0x1800f067e  mov     rcx, r14; this
0x1800f0681  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0686  cmp     [rbx+18h], r15
0x1800f068a  jnz     short loc_1800F069C
0x1800f068c  cmp     [rbx+48h], r15
0x1800f0690  jnz     short loc_1800F069C
0x1800f0692  cmp     [rbx+30h], r15
0x1800f0696  jz      loc_1800F072C
0x1800f069c  lea     r8, asc_18014A268; "    "
0x1800f06a3  mov     rdx, rsi; wchar_t *
0x1800f06a6  mov     rcx, rax; this
0x1800f06a9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f06ae  mov     r9, [rbx+18h]; wchar_t *
0x1800f06b2  test    r9, r9
0x1800f06b5  jz      short loc_1800F06C9
0x1800f06b7  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800f06be  mov     rdx, rsi; wchar_t *
0x1800f06c1  mov     rcx, rax; this
0x1800f06c4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f06c9  mov     r9, [rbx+48h]; wchar_t *
0x1800f06cd  test    r9, r9
0x1800f06d0  jz      short loc_1800F06E4
0x1800f06d2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800f06d9  mov     rdx, rsi; wchar_t *
0x1800f06dc  mov     rcx, rax; this
0x1800f06df  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f06e4  mov     rcx, [rbx+28h]
0x1800f06e8  mov     r9, [rbx+30h]; wchar_t *
0x1800f06ec  mov     rdx, rsi; wchar_t *
0x1800f06ef  test    rcx, rcx
0x1800f06f2  jz      short loc_1800F070A
0x1800f06f4  mov     [rsp+288h+lpBuffer], rcx
0x1800f06f9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800f0700  mov     rcx, rax; this
0x1800f0703  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f0708  jmp     short loc_1800F072C
0x1800f070a  mov     rcx, rax; this
0x1800f070d  test    r9, r9
0x1800f0710  jz      short loc_1800F0720
0x1800f0712  lea     r8, aHs; "[%hs]\n"
0x1800f0719  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f071e  jmp     short loc_1800F072C
0x1800f0720  lea     r8, asc_18014A2B8; "\n"
0x1800f0727  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800f072c  xor     eax, eax
0x1800f072e  mov     rcx, [rsp+288h+var_38]
0x1800f0736  xor     rcx, rsp; StackCookie
0x1800f0739  call    __security_check_cookie
0x1800f073e  mov     rbx, [rsp+288h+arg_18]
0x1800f0746  add     rsp, 260h
0x1800f074d  pop     r15
0x1800f074f  pop     r14
0x1800f0751  pop     rdi
0x1800f0752  pop     rsi
0x1800f0753  pop     rbp
0x1800f0754  retn
```
