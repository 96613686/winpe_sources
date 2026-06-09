# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009b94`
- end: `0x180009e55`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a2f8`
- `0x18000bb10`

## callees

- `0x180009b94`
- `0x18000a5fc`
- `0x1800119c2`
- `0x1800119f0`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d52`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d52`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009cd1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009cd1`

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
          v7 = (const char *)&dword_18001DF7C;
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
0x180009b94  mov     rax, rsp
0x180009b97  push    rbp
0x180009b98  push    rsi
0x180009b99  push    rdi
0x180009b9a  push    r14
0x180009b9c  push    r15
0x180009b9e  sub     rsp, 260h
0x180009ba5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180009bae  mov     [rax+20h], rbx
0x180009bb2  mov     rax, cs:__security_cookie
0x180009bb9  xor     rax, rsp
0x180009bbc  mov     [rsp+288h+var_38], rax
0x180009bc4  mov     rbx, r8
0x180009bc7  mov     rsi, rdx
0x180009bca  mov     r14, rcx
0x180009bcd  xor     r15d, r15d
0x180009bd0  test    rdx, rdx
0x180009bd3  jz      loc_180009E2C
0x180009bd9  test    rcx, rcx
0x180009bdc  jz      loc_180009E2C
0x180009be2  mov     [rcx], r15w
0x180009be6  mov     rax, cs:g_pfnResultLoggingCallback
0x180009bed  test    rax, rax
0x180009bf0  jz      short loc_180009C13
0x180009bf2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009bf9  jz      short loc_180009C13
0x180009bfb  mov     r8, rdx
0x180009bfe  mov     rdx, rcx
0x180009c01  mov     rcx, rbx
0x180009c04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c09  cmp     [r14], r15w
0x180009c0d  jnz     loc_180009E2C
0x180009c13  mov     ecx, [rbx]
0x180009c15  mov     bpl, 8
0x180009c18  test    ecx, ecx
0x180009c1a  jz      short loc_180009C65
0x180009c1c  sub     ecx, 1
0x180009c1f  jz      short loc_180009C4D
0x180009c21  sub     ecx, 1
0x180009c24  jz      short loc_180009C3D
0x180009c26  cmp     ecx, 1
0x180009c29  jz      short loc_180009C34
0x180009c2b  lea     rdi, dword_18001DF7C
0x180009c32  jmp     short loc_180009C6C
0x180009c34  lea     rdi, aFailfast; "FailFast"
0x180009c3b  jmp     short loc_180009C6C
0x180009c3d  lea     rax, aLoghr; "LogHr"
0x180009c44  lea     rdi, aLognt; "LogNt"
0x180009c4b  jmp     short loc_180009C5B
0x180009c4d  lea     rax, aReturnhr; "ReturnHr"
0x180009c54  lea     rdi, aReturnnt; "ReturnNt"
0x180009c5b  test    [rbx+4], bpl
0x180009c5f  cmovz   rdi, rax
0x180009c63  jmp     short loc_180009C6C
0x180009c65  lea     rdi, aException; "Exception"
0x180009c6c  xor     edx, edx; Val
0x180009c6e  mov     r8d, 200h; Size
0x180009c74  lea     rcx, [rsp+288h+Buffer]; void *
0x180009c79  call    memset_0
0x180009c7e  test    [rbx+4], bpl
0x180009c82  jz      short loc_180009CA7
0x180009c84  mov     ebp, [rbx+0Ch]
0x180009c87  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180009c8e  test    rax, rax
0x180009c91  jz      short loc_180009CD7
0x180009c93  mov     r8d, 100h
0x180009c99  lea     rdx, [rsp+288h+Buffer]
0x180009c9e  mov     ecx, ebp
0x180009ca0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ca5  jmp     short loc_180009CD7
0x180009ca7  mov     ebp, [rbx+8]
0x180009caa  mov     [rsp+288h+Arguments], r15; Arguments
0x180009caf  mov     [rsp+288h+nSize], 100h; nSize
0x180009cb7  lea     rax, [rsp+288h+Buffer]
0x180009cbc  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180009cc1  mov     r9d, 400h; dwLanguageId
0x180009cc7  mov     r8d, ebp; dwMessageId
0x180009cca  xor     edx, edx; lpSource
0x180009ccc  mov     ecx, 1200h; dwFlags
0x180009cd1  call    cs:__imp_FormatMessageW
0x180009cd7  lea     rsi, [r14+rsi*2]
0x180009cdb  mov     r9, [rbx+38h]; wchar_t *
0x180009cdf  mov     rax, [rbx+88h]
0x180009ce6  mov     rcx, [rbx+80h]
0x180009ced  mov     rdx, rsi; wchar_t *
0x180009cf0  test    r9, r9
0x180009cf3  jz      short loc_180009D17
0x180009cf5  mov     [rsp+288h+Arguments], rax
0x180009cfa  mov     qword ptr [rsp+288h+nSize], rcx
0x180009cff  mov     eax, [rbx+40h]
0x180009d02  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180009d06  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009d0d  mov     rcx, r14; this
0x180009d10  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009d15  jmp     short loc_180009D2E
0x180009d17  mov     [rsp+288h+lpBuffer], rax
0x180009d1c  mov     r9, rcx; wchar_t *
0x180009d1f  lea     r8, aHsP; "%hs!%p: "
0x180009d26  mov     rcx, r14; this
0x180009d29  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009d2e  mov     r14, rax
0x180009d31  mov     r9, [rbx+90h]; wchar_t *
0x180009d38  test    r9, r9
0x180009d3b  jz      short loc_180009D52
0x180009d3d  lea     r8, aCallerP; "(caller: %p) "
0x180009d44  mov     rdx, rsi; wchar_t *
0x180009d47  mov     rcx, rax; this
0x180009d4a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009d4f  mov     r14, rax
0x180009d52  call    cs:__imp_GetCurrentThreadId
0x180009d58  lea     rcx, [rsp+288h+Buffer]
0x180009d5d  mov     [rsp+288h+var_250], rcx
0x180009d62  mov     dword ptr [rsp+288h+Arguments], ebp
0x180009d66  mov     [rsp+288h+nSize], eax
0x180009d6a  mov     eax, [rbx+44h]
0x180009d6d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180009d71  mov     r9, rdi; wchar_t *
0x180009d74  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009d7b  mov     rdx, rsi; wchar_t *
0x180009d7e  mov     rcx, r14; this
0x180009d81  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009d86  cmp     [rbx+18h], r15
0x180009d8a  jnz     short loc_180009D9C
0x180009d8c  cmp     [rbx+48h], r15
0x180009d90  jnz     short loc_180009D9C
0x180009d92  cmp     [rbx+30h], r15
0x180009d96  jz      loc_180009E2C
0x180009d9c  lea     r8, asc_18001E0B0; "    "
0x180009da3  mov     rdx, rsi; wchar_t *
0x180009da6  mov     rcx, rax; this
0x180009da9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009dae  mov     r9, [rbx+18h]; wchar_t *
0x180009db2  test    r9, r9
0x180009db5  jz      short loc_180009DC9
0x180009db7  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009dbe  mov     rdx, rsi; wchar_t *
0x180009dc1  mov     rcx, rax; this
0x180009dc4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009dc9  mov     r9, [rbx+48h]; wchar_t *
0x180009dcd  test    r9, r9
0x180009dd0  jz      short loc_180009DE4
0x180009dd2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009dd9  mov     rdx, rsi; wchar_t *
0x180009ddc  mov     rcx, rax; this
0x180009ddf  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009de4  mov     rcx, [rbx+28h]
0x180009de8  mov     r9, [rbx+30h]; wchar_t *
0x180009dec  mov     rdx, rsi; wchar_t *
0x180009def  test    rcx, rcx
0x180009df2  jz      short loc_180009E0A
0x180009df4  mov     [rsp+288h+lpBuffer], rcx
0x180009df9  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009e00  mov     rcx, rax; this
0x180009e03  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009e08  jmp     short loc_180009E2C
0x180009e0a  mov     rcx, rax; this
0x180009e0d  test    r9, r9
0x180009e10  jz      short loc_180009E20
0x180009e12  lea     r8, aHs; "[%hs]\n"
0x180009e19  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009e1e  jmp     short loc_180009E2C
0x180009e20  lea     r8, asc_18001E128; "\n"
0x180009e27  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180009e2c  xor     eax, eax
0x180009e2e  mov     rcx, [rsp+288h+var_38]
0x180009e36  xor     rcx, rsp; StackCookie
0x180009e39  call    __security_check_cookie
0x180009e3e  mov     rbx, [rsp+288h+arg_18]
0x180009e46  add     rsp, 260h
0x180009e4d  pop     r15
0x180009e4f  pop     r14
0x180009e51  pop     rdi
0x180009e52  pop     rsi
0x180009e53  pop     rbp
0x180009e54  retn
```
