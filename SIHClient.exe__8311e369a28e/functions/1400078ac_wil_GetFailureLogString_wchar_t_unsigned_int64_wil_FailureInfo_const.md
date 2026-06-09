# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400078ac`
- end: `0x140007b60`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x140008720`
- `0x140009c14`
- `0x14000a0dc`
- `0x14000a3e4`
- `0x140043cd8`
- `0x14004dcdf`
- `0x14004de18`

## callees

- `0x140007840`
- `0x1400078ac`
- `0x140045dc0`
- `0x14004cd00`
- `0x14004cd80`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007a5d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007a5d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400079dc`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400079dc`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
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
  v7 = (const char *)&pszCabPath;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
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
0x1400078ac  mov     [rsp+arg_18], rbx
0x1400078b1  push    rbp
0x1400078b2  push    rsi
0x1400078b3  push    rdi
0x1400078b4  push    r14
0x1400078b6  push    r15
0x1400078b8  sub     rsp, 250h
0x1400078bf  mov     rax, cs:__security_cookie
0x1400078c6  xor     rax, rsp
0x1400078c9  mov     [rsp+278h+var_38], rax
0x1400078d1  mov     rbx, r8
0x1400078d4  mov     rdi, rdx
0x1400078d7  mov     r14, rcx
0x1400078da  xor     r15d, r15d
0x1400078dd  test    rdx, rdx
0x1400078e0  jz      loc_140007B37
0x1400078e6  test    rcx, rcx
0x1400078e9  jz      loc_140007B37
0x1400078ef  mov     [rcx], r15w
0x1400078f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400078fa  test    rax, rax
0x1400078fd  jz      short loc_140007920
0x1400078ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140007906  jz      short loc_140007920
0x140007908  mov     r8, rdx
0x14000790b  mov     rdx, rcx
0x14000790e  mov     rcx, rbx
0x140007911  call    _guard_dispatch_icall
0x140007916  cmp     [r14], r15w
0x14000791a  jnz     loc_140007B37
0x140007920  lea     rsi, pszCabPath
0x140007927  mov     ecx, [rbx]
0x140007929  mov     bpl, 8
0x14000792c  test    ecx, ecx
0x14000792e  jz      short loc_140007970
0x140007930  sub     ecx, 1
0x140007933  jz      short loc_140007958
0x140007935  sub     ecx, 1
0x140007938  jz      short loc_140007948
0x14000793a  cmp     ecx, 1
0x14000793d  jnz     short loc_140007977
0x14000793f  lea     rsi, aFailfast; "FailFast"
0x140007946  jmp     short loc_140007977
0x140007948  lea     rax, aLoghr; "LogHr"
0x14000794f  lea     rsi, aLognt; "LogNt"
0x140007956  jmp     short loc_140007966
0x140007958  lea     rax, aReturnhr; "ReturnHr"
0x14000795f  lea     rsi, aReturnnt; "ReturnNt"
0x140007966  test    [rbx+4], bpl
0x14000796a  cmovz   rsi, rax
0x14000796e  jmp     short loc_140007977
0x140007970  lea     rsi, aException; "Exception"
0x140007977  xor     edx, edx; Val
0x140007979  mov     r8d, 200h; Size
0x14000797f  lea     rcx, [rsp+278h+Buffer]; void *
0x140007984  call    memset
0x140007989  test    [rbx+4], bpl
0x14000798d  jz      short loc_1400079B2
0x14000798f  mov     ebp, [rbx+0Ch]
0x140007992  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140007999  test    rax, rax
0x14000799c  jz      short loc_1400079E2
0x14000799e  mov     r8d, 100h
0x1400079a4  lea     rdx, [rsp+278h+Buffer]
0x1400079a9  mov     ecx, ebp
0x1400079ab  call    _guard_dispatch_icall
0x1400079b0  jmp     short loc_1400079E2
0x1400079b2  mov     ebp, [rbx+8]
0x1400079b5  mov     [rsp+278h+Arguments], r15; Arguments
0x1400079ba  mov     [rsp+278h+nSize], 100h; nSize
0x1400079c2  lea     rax, [rsp+278h+Buffer]
0x1400079c7  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400079cc  mov     r9d, 400h; dwLanguageId
0x1400079d2  mov     r8d, ebp; dwMessageId
0x1400079d5  xor     edx, edx; lpSource
0x1400079d7  mov     ecx, 1200h; dwFlags
0x1400079dc  call    cs:__imp_FormatMessageW
0x1400079e2  lea     rdi, [r14+rdi*2]
0x1400079e6  mov     r9, [rbx+38h]; wchar_t *
0x1400079ea  mov     rax, [rbx+88h]
0x1400079f1  mov     rcx, [rbx+80h]
0x1400079f8  mov     rdx, rdi; wchar_t *
0x1400079fb  test    r9, r9
0x1400079fe  jz      short loc_140007A22
0x140007a00  mov     [rsp+278h+Arguments], rax
0x140007a05  mov     qword ptr [rsp+278h+nSize], rcx
0x140007a0a  mov     eax, [rbx+40h]
0x140007a0d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140007a11  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140007a18  mov     rcx, r14; this
0x140007a1b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a20  jmp     short loc_140007A39
0x140007a22  mov     [rsp+278h+lpBuffer], rax
0x140007a27  mov     r9, rcx; wchar_t *
0x140007a2a  lea     r8, aHsP; "%hs!%p: "
0x140007a31  mov     rcx, r14; this
0x140007a34  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a39  mov     r14, rax
0x140007a3c  mov     r9, [rbx+90h]; wchar_t *
0x140007a43  test    r9, r9
0x140007a46  jz      short loc_140007A5D
0x140007a48  lea     r8, aCallerP; "(caller: %p) "
0x140007a4f  mov     rdx, rdi; wchar_t *
0x140007a52  mov     rcx, rax; this
0x140007a55  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a5a  mov     r14, rax
0x140007a5d  call    cs:__imp_GetCurrentThreadId
0x140007a63  lea     rcx, [rsp+278h+Buffer]
0x140007a68  mov     [rsp+278h+var_240], rcx
0x140007a6d  mov     dword ptr [rsp+278h+Arguments], ebp
0x140007a71  mov     [rsp+278h+nSize], eax
0x140007a75  mov     eax, [rbx+44h]
0x140007a78  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140007a7c  mov     r9, rsi; wchar_t *
0x140007a7f  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140007a86  mov     rdx, rdi; wchar_t *
0x140007a89  mov     rcx, r14; this
0x140007a8c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007a91  cmp     [rbx+18h], r15
0x140007a95  jnz     short loc_140007AA7
0x140007a97  cmp     [rbx+48h], r15
0x140007a9b  jnz     short loc_140007AA7
0x140007a9d  cmp     [rbx+30h], r15
0x140007aa1  jz      loc_140007B37
0x140007aa7  lea     r8, asc_1400537B8; "    "
0x140007aae  mov     rdx, rdi; wchar_t *
0x140007ab1  mov     rcx, rax; this
0x140007ab4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007ab9  mov     r9, [rbx+18h]; wchar_t *
0x140007abd  test    r9, r9
0x140007ac0  jz      short loc_140007AD4
0x140007ac2  lea     r8, aMsgWs; "Msg:[%ws] "
0x140007ac9  mov     rdx, rdi; wchar_t *
0x140007acc  mov     rcx, rax; this
0x140007acf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007ad4  mov     r9, [rbx+48h]; wchar_t *
0x140007ad8  test    r9, r9
0x140007adb  jz      short loc_140007AEF
0x140007add  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140007ae4  mov     rdx, rdi; wchar_t *
0x140007ae7  mov     rcx, rax; this
0x140007aea  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007aef  mov     rcx, [rbx+28h]
0x140007af3  mov     r9, [rbx+30h]; wchar_t *
0x140007af7  mov     rdx, rdi; wchar_t *
0x140007afa  test    rcx, rcx
0x140007afd  jz      short loc_140007B15
0x140007aff  mov     [rsp+278h+lpBuffer], rcx
0x140007b04  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140007b0b  mov     rcx, rax; this
0x140007b0e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007b13  jmp     short loc_140007B37
0x140007b15  mov     rcx, rax; this
0x140007b18  test    r9, r9
0x140007b1b  jz      short loc_140007B2B
0x140007b1d  lea     r8, aHs; "[%hs]\n"
0x140007b24  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007b29  jmp     short loc_140007B37
0x140007b2b  lea     r8, asc_140053830; "\n"
0x140007b32  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140007b37  xor     eax, eax
0x140007b39  mov     rcx, [rsp+278h+var_38]
0x140007b41  xor     rcx, rsp; StackCookie
0x140007b44  call    __security_check_cookie
0x140007b49  mov     rbx, [rsp+278h+arg_18]
0x140007b51  add     rsp, 250h
0x140007b58  pop     r15
0x140007b5a  pop     r14
0x140007b5c  pop     rdi
0x140007b5d  pop     rsi
0x140007b5e  pop     rbp
0x140007b5f  retn
```
