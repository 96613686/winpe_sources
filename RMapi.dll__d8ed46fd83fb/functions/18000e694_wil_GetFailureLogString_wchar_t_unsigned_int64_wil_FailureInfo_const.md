# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000e694`
- end: `0x18000e94a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000eae8`
- `0x18000ee70`
- `0x18000f350`
- `0x18000fe40`

## callees

- `0x18000d2a0`
- `0x18000df4c`
- `0x18000e694`
- `0x18000ea7c`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e847`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e847`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e7c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000e7c6`

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
          v7 = (const char *)&byte_18002AE5D;
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
0x18000e694  mov     [rsp+arg_18], rbx
0x18000e699  push    rbp
0x18000e69a  push    rsi
0x18000e69b  push    rdi
0x18000e69c  push    r14
0x18000e69e  push    r15
0x18000e6a0  sub     rsp, 250h
0x18000e6a7  mov     rax, cs:__security_cookie
0x18000e6ae  xor     rax, rsp
0x18000e6b1  mov     [rsp+278h+var_38], rax
0x18000e6b9  mov     rbx, r8
0x18000e6bc  mov     rsi, rdx
0x18000e6bf  mov     r14, rcx
0x18000e6c2  xor     r15d, r15d
0x18000e6c5  test    rdx, rdx
0x18000e6c8  jz      loc_18000E921
0x18000e6ce  test    rcx, rcx
0x18000e6d1  jz      loc_18000E921
0x18000e6d7  mov     [rcx], r15w
0x18000e6db  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e6e2  test    rax, rax
0x18000e6e5  jz      short loc_18000E708
0x18000e6e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000e6ee  jz      short loc_18000E708
0x18000e6f0  mov     r8, rdx
0x18000e6f3  mov     rdx, rcx
0x18000e6f6  mov     rcx, rbx
0x18000e6f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6fe  cmp     [r14], r15w
0x18000e702  jnz     loc_18000E921
0x18000e708  mov     ecx, [rbx]
0x18000e70a  mov     bpl, 8
0x18000e70d  test    ecx, ecx
0x18000e70f  jz      short loc_18000E75A
0x18000e711  sub     ecx, 1
0x18000e714  jz      short loc_18000E742
0x18000e716  sub     ecx, 1
0x18000e719  jz      short loc_18000E732
0x18000e71b  cmp     ecx, 1
0x18000e71e  jz      short loc_18000E729
0x18000e720  lea     rdi, byte_18002AE5D
0x18000e727  jmp     short loc_18000E761
0x18000e729  lea     rdi, aFailfast; "FailFast"
0x18000e730  jmp     short loc_18000E761
0x18000e732  lea     rax, aLoghr; "LogHr"
0x18000e739  lea     rdi, aLognt; "LogNt"
0x18000e740  jmp     short loc_18000E750
0x18000e742  lea     rax, aReturnhr; "ReturnHr"
0x18000e749  lea     rdi, aReturnnt; "ReturnNt"
0x18000e750  test    [rbx+4], bpl
0x18000e754  cmovz   rdi, rax
0x18000e758  jmp     short loc_18000E761
0x18000e75a  lea     rdi, aException; "Exception"
0x18000e761  xor     edx, edx; Val
0x18000e763  mov     r8d, 200h; Size
0x18000e769  lea     rcx, [rsp+278h+Buffer]; void *
0x18000e76e  call    memset_0
0x18000e773  test    [rbx+4], bpl
0x18000e777  jz      short loc_18000E79C
0x18000e779  mov     ebp, [rbx+0Ch]
0x18000e77c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000e783  test    rax, rax
0x18000e786  jz      short loc_18000E7CC
0x18000e788  mov     r8d, 100h
0x18000e78e  lea     rdx, [rsp+278h+Buffer]
0x18000e793  mov     ecx, ebp
0x18000e795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e79a  jmp     short loc_18000E7CC
0x18000e79c  mov     ebp, [rbx+8]
0x18000e79f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000e7a4  mov     [rsp+278h+nSize], 100h; nSize
0x18000e7ac  lea     rax, [rsp+278h+Buffer]
0x18000e7b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000e7b6  mov     r9d, 400h; dwLanguageId
0x18000e7bc  mov     r8d, ebp; dwMessageId
0x18000e7bf  xor     edx, edx; lpSource
0x18000e7c1  mov     ecx, 1200h; dwFlags
0x18000e7c6  call    cs:__imp_FormatMessageW
0x18000e7cc  lea     rsi, [r14+rsi*2]
0x18000e7d0  mov     r9, [rbx+38h]; wchar_t *
0x18000e7d4  mov     rax, [rbx+88h]
0x18000e7db  mov     rcx, [rbx+80h]
0x18000e7e2  mov     rdx, rsi; wchar_t *
0x18000e7e5  test    r9, r9
0x18000e7e8  jz      short loc_18000E80C
0x18000e7ea  mov     [rsp+278h+Arguments], rax
0x18000e7ef  mov     qword ptr [rsp+278h+nSize], rcx
0x18000e7f4  mov     eax, [rbx+40h]
0x18000e7f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e7fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000e802  mov     rcx, r14; this
0x18000e805  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e80a  jmp     short loc_18000E823
0x18000e80c  mov     [rsp+278h+lpBuffer], rax
0x18000e811  mov     r9, rcx; wchar_t *
0x18000e814  lea     r8, aHsP; "%hs!%p: "
0x18000e81b  mov     rcx, r14; this
0x18000e81e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e823  mov     r14, rax
0x18000e826  mov     r9, [rbx+90h]; wchar_t *
0x18000e82d  test    r9, r9
0x18000e830  jz      short loc_18000E847
0x18000e832  lea     r8, aCallerP; "(caller: %p) "
0x18000e839  mov     rdx, rsi; wchar_t *
0x18000e83c  mov     rcx, rax; this
0x18000e83f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e844  mov     r14, rax
0x18000e847  call    cs:__imp_GetCurrentThreadId
0x18000e84d  lea     rcx, [rsp+278h+Buffer]
0x18000e852  mov     [rsp+278h+var_240], rcx
0x18000e857  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000e85b  mov     [rsp+278h+nSize], eax
0x18000e85f  mov     eax, [rbx+44h]
0x18000e862  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000e866  mov     r9, rdi; wchar_t *
0x18000e869  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000e870  mov     rdx, rsi; wchar_t *
0x18000e873  mov     rcx, r14; this
0x18000e876  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e87b  cmp     [rbx+18h], r15
0x18000e87f  jnz     short loc_18000E891
0x18000e881  cmp     [rbx+48h], r15
0x18000e885  jnz     short loc_18000E891
0x18000e887  cmp     [rbx+30h], r15
0x18000e88b  jz      loc_18000E921
0x18000e891  lea     r8, asc_18002B410; "    "
0x18000e898  mov     rdx, rsi; wchar_t *
0x18000e89b  mov     rcx, rax; this
0x18000e89e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e8a3  mov     r9, [rbx+18h]; wchar_t *
0x18000e8a7  test    r9, r9
0x18000e8aa  jz      short loc_18000E8BE
0x18000e8ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000e8b3  mov     rdx, rsi; wchar_t *
0x18000e8b6  mov     rcx, rax; this
0x18000e8b9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e8be  mov     r9, [rbx+48h]; wchar_t *
0x18000e8c2  test    r9, r9
0x18000e8c5  jz      short loc_18000E8D9
0x18000e8c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000e8ce  mov     rdx, rsi; wchar_t *
0x18000e8d1  mov     rcx, rax; this
0x18000e8d4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e8d9  mov     rcx, [rbx+28h]
0x18000e8dd  mov     r9, [rbx+30h]; wchar_t *
0x18000e8e1  mov     rdx, rsi; wchar_t *
0x18000e8e4  test    rcx, rcx
0x18000e8e7  jz      short loc_18000E8FF
0x18000e8e9  mov     [rsp+278h+lpBuffer], rcx
0x18000e8ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000e8f5  mov     rcx, rax; this
0x18000e8f8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e8fd  jmp     short loc_18000E921
0x18000e8ff  mov     rcx, rax; this
0x18000e902  test    r9, r9
0x18000e905  jz      short loc_18000E915
0x18000e907  lea     r8, aHs; "[%hs]\n"
0x18000e90e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e913  jmp     short loc_18000E921
0x18000e915  lea     r8, asc_18002B488; "\n"
0x18000e91c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000e921  xor     eax, eax
0x18000e923  mov     rcx, [rsp+278h+var_38]
0x18000e92b  xor     rcx, rsp; StackCookie
0x18000e92e  call    __security_check_cookie
0x18000e933  mov     rbx, [rsp+278h+arg_18]
0x18000e93b  add     rsp, 250h
0x18000e942  pop     r15
0x18000e944  pop     r14
0x18000e946  pop     rdi
0x18000e947  pop     rsi
0x18000e948  pop     rbp
0x18000e949  retn
```
