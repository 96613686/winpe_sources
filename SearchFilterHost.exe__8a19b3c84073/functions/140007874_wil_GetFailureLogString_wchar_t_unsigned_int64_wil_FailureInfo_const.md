# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140007874`
- end: `0x140007b35`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140005840`
- `0x1400084cc`
- `0x140008bb8`
- `0x14000be60`

## callees

- `0x1400030a0`
- `0x140003c74`
- `0x140007874`
- `0x1400087d8`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007a32`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007a32`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400079b1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400079b1`

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
          v7 = (const char *)&byte_140053AD0;
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
0x140007874  mov     rax, rsp
0x140007877  push    rbp
0x140007878  push    rsi
0x140007879  push    rdi
0x14000787a  push    r14
0x14000787c  push    r15
0x14000787e  sub     rsp, 260h
0x140007885  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x14000788e  mov     [rax+20h], rbx
0x140007892  mov     rax, cs:__security_cookie
0x140007899  xor     rax, rsp
0x14000789c  mov     [rsp+288h+var_38], rax
0x1400078a4  mov     rbx, r8
0x1400078a7  mov     rsi, rdx
0x1400078aa  mov     r14, rcx
0x1400078ad  xor     r15d, r15d
0x1400078b0  test    rdx, rdx
0x1400078b3  jz      loc_140007B0C
0x1400078b9  test    rcx, rcx
0x1400078bc  jz      loc_140007B0C
0x1400078c2  mov     [rcx], r15w
0x1400078c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400078cd  test    rax, rax
0x1400078d0  jz      short loc_1400078F3
0x1400078d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400078d9  jz      short loc_1400078F3
0x1400078db  mov     r8, rdx
0x1400078de  mov     rdx, rcx
0x1400078e1  mov     rcx, rbx
0x1400078e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078e9  cmp     [r14], r15w
0x1400078ed  jnz     loc_140007B0C
0x1400078f3  mov     ecx, [rbx]
0x1400078f5  mov     bpl, 8
0x1400078f8  test    ecx, ecx
0x1400078fa  jz      short loc_140007945
0x1400078fc  sub     ecx, 1
0x1400078ff  jz      short loc_14000792D
0x140007901  sub     ecx, 1
0x140007904  jz      short loc_14000791D
0x140007906  cmp     ecx, 1
0x140007909  jz      short loc_140007914
0x14000790b  lea     rdi, byte_140053AD0
0x140007912  jmp     short loc_14000794C
0x140007914  lea     rdi, aFailfast; "FailFast"
0x14000791b  jmp     short loc_14000794C
0x14000791d  lea     rax, aLoghr; "LogHr"
0x140007924  lea     rdi, aLognt; "LogNt"
0x14000792b  jmp     short loc_14000793B
0x14000792d  lea     rax, aReturnhr; "ReturnHr"
0x140007934  lea     rdi, aReturnnt; "ReturnNt"
0x14000793b  test    [rbx+4], bpl
0x14000793f  cmovz   rdi, rax
0x140007943  jmp     short loc_14000794C
0x140007945  lea     rdi, aException; "Exception"
0x14000794c  xor     edx, edx; Val
0x14000794e  mov     r8d, 200h; Size
0x140007954  lea     rcx, [rsp+288h+Buffer]; void *
0x140007959  call    memset_0
0x14000795e  test    [rbx+4], bpl
0x140007962  jz      short loc_140007987
0x140007964  mov     ebp, [rbx+0Ch]
0x140007967  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x14000796e  test    rax, rax
0x140007971  jz      short loc_1400079B7
0x140007973  mov     r8d, 100h
0x140007979  lea     rdx, [rsp+288h+Buffer]
0x14000797e  mov     ecx, ebp
0x140007980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007985  jmp     short loc_1400079B7
0x140007987  mov     ebp, [rbx+8]
0x14000798a  mov     [rsp+288h+Arguments], r15; Arguments
0x14000798f  mov     [rsp+288h+nSize], 100h; nSize
0x140007997  lea     rax, [rsp+288h+Buffer]
0x14000799c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1400079a1  mov     r9d, 400h; dwLanguageId
0x1400079a7  mov     r8d, ebp; dwMessageId
0x1400079aa  xor     edx, edx; lpSource
0x1400079ac  mov     ecx, 1200h; dwFlags
0x1400079b1  call    cs:__imp_FormatMessageW
0x1400079b7  lea     rsi, [r14+rsi*2]
0x1400079bb  mov     r9, [rbx+38h]; wchar_t *
0x1400079bf  mov     rax, [rbx+88h]
0x1400079c6  mov     rcx, [rbx+80h]
0x1400079cd  mov     rdx, rsi; wchar_t *
0x1400079d0  test    r9, r9
0x1400079d3  jz      short loc_1400079F7
0x1400079d5  mov     [rsp+288h+Arguments], rax
0x1400079da  mov     qword ptr [rsp+288h+nSize], rcx
0x1400079df  mov     eax, [rbx+40h]
0x1400079e2  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1400079e6  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400079ed  mov     rcx, r14; this
0x1400079f0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400079f5  jmp     short loc_140007A0E
0x1400079f7  mov     [rsp+288h+lpBuffer], rax
0x1400079fc  mov     r9, rcx; wchar_t *
0x1400079ff  lea     r8, aHsP; "%hs!%p: "
0x140007a06  mov     rcx, r14; this
0x140007a09  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a0e  mov     r14, rax
0x140007a11  mov     r9, [rbx+90h]; wchar_t *
0x140007a18  test    r9, r9
0x140007a1b  jz      short loc_140007A32
0x140007a1d  lea     r8, aCallerP; "(caller: %p) "
0x140007a24  mov     rdx, rsi; wchar_t *
0x140007a27  mov     rcx, rax; this
0x140007a2a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a2f  mov     r14, rax
0x140007a32  call    cs:__imp_GetCurrentThreadId
0x140007a38  lea     rcx, [rsp+288h+Buffer]
0x140007a3d  mov     [rsp+288h+var_250], rcx
0x140007a42  mov     dword ptr [rsp+288h+Arguments], ebp
0x140007a46  mov     [rsp+288h+nSize], eax
0x140007a4a  mov     eax, [rbx+44h]
0x140007a4d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x140007a51  mov     r9, rdi; wchar_t *
0x140007a54  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140007a5b  mov     rdx, rsi; wchar_t *
0x140007a5e  mov     rcx, r14; this
0x140007a61  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a66  cmp     [rbx+18h], r15
0x140007a6a  jnz     short loc_140007A7C
0x140007a6c  cmp     [rbx+48h], r15
0x140007a70  jnz     short loc_140007A7C
0x140007a72  cmp     [rbx+30h], r15
0x140007a76  jz      loc_140007B0C
0x140007a7c  lea     r8, asc_140053C00; "    "
0x140007a83  mov     rdx, rsi; wchar_t *
0x140007a86  mov     rcx, rax; this
0x140007a89  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a8e  mov     r9, [rbx+18h]; wchar_t *
0x140007a92  test    r9, r9
0x140007a95  jz      short loc_140007AA9
0x140007a97  lea     r8, aMsgWs; "Msg:[%ws] "
0x140007a9e  mov     rdx, rsi; wchar_t *
0x140007aa1  mov     rcx, rax; this
0x140007aa4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007aa9  mov     r9, [rbx+48h]; wchar_t *
0x140007aad  test    r9, r9
0x140007ab0  jz      short loc_140007AC4
0x140007ab2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140007ab9  mov     rdx, rsi; wchar_t *
0x140007abc  mov     rcx, rax; this
0x140007abf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007ac4  mov     rcx, [rbx+28h]
0x140007ac8  mov     r9, [rbx+30h]; wchar_t *
0x140007acc  mov     rdx, rsi; wchar_t *
0x140007acf  test    rcx, rcx
0x140007ad2  jz      short loc_140007AEA
0x140007ad4  mov     [rsp+288h+lpBuffer], rcx
0x140007ad9  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x140007ae0  mov     rcx, rax; this
0x140007ae3  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007ae8  jmp     short loc_140007B0C
0x140007aea  mov     rcx, rax; this
0x140007aed  test    r9, r9
0x140007af0  jz      short loc_140007B00
0x140007af2  lea     r8, aHs; "[%hs]\n"
0x140007af9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007afe  jmp     short loc_140007B0C
0x140007b00  lea     r8, asc_140053C78; "\n"
0x140007b07  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007b0c  xor     eax, eax
0x140007b0e  mov     rcx, [rsp+288h+var_38]
0x140007b16  xor     rcx, rsp; StackCookie
0x140007b19  call    __security_check_cookie
0x140007b1e  mov     rbx, [rsp+288h+arg_18]
0x140007b26  add     rsp, 260h
0x140007b2d  pop     r15
0x140007b2f  pop     r14
0x140007b31  pop     rdi
0x140007b32  pop     rsi
0x140007b33  pop     rbp
0x140007b34  retn
```
