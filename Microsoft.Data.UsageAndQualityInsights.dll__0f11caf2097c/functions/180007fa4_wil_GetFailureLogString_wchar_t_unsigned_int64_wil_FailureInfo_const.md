# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007fa4`
- end: `0x18000825a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180005828`
- `0x180005aa8`
- `0x180008a9c`
- `0x18000c870`
- `0x18000d630`
- `0x180101c9b`
- `0x180101dcf`
- `0x180101f38`
- `0x1801021b5`

## callees

- `0x1800033d0`
- `0x180003fb8`
- `0x180007fa4`
- `0x180008d9c`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008157`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008157`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800080d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800080d6`

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
0x180007fa4  mov     [rsp+arg_18], rbx
0x180007fa9  push    rbp
0x180007faa  push    rsi
0x180007fab  push    rdi
0x180007fac  push    r14
0x180007fae  push    r15
0x180007fb0  sub     rsp, 250h
0x180007fb7  mov     rax, cs:__security_cookie
0x180007fbe  xor     rax, rsp
0x180007fc1  mov     [rsp+278h+var_38], rax
0x180007fc9  mov     rbx, r8
0x180007fcc  mov     rsi, rdx
0x180007fcf  mov     r14, rcx
0x180007fd2  xor     r15d, r15d
0x180007fd5  test    rdx, rdx
0x180007fd8  jz      loc_180008231
0x180007fde  test    rcx, rcx
0x180007fe1  jz      loc_180008231
0x180007fe7  mov     [rcx], r15w
0x180007feb  mov     rax, cs:g_pfnResultLoggingCallback
0x180007ff2  test    rax, rax
0x180007ff5  jz      short loc_180008018
0x180007ff7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007ffe  jz      short loc_180008018
0x180008000  mov     r8, rdx
0x180008003  mov     rdx, rcx
0x180008006  mov     rcx, rbx
0x180008009  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000800e  cmp     [r14], r15w
0x180008012  jnz     loc_180008231
0x180008018  mov     ecx, [rbx]
0x18000801a  mov     bpl, 8
0x18000801d  test    ecx, ecx
0x18000801f  jz      short loc_18000806A
0x180008021  sub     ecx, 1
0x180008024  jz      short loc_180008052
0x180008026  sub     ecx, 1
0x180008029  jz      short loc_180008042
0x18000802b  cmp     ecx, 1
0x18000802e  jz      short loc_180008039
0x180008030  lea     rdi, Src
0x180008037  jmp     short loc_180008071
0x180008039  lea     rdi, aFailfast; "FailFast"
0x180008040  jmp     short loc_180008071
0x180008042  lea     rax, aLoghr; "LogHr"
0x180008049  lea     rdi, aLognt; "LogNt"
0x180008050  jmp     short loc_180008060
0x180008052  lea     rax, aReturnhr; "ReturnHr"
0x180008059  lea     rdi, aReturnnt; "ReturnNt"
0x180008060  test    [rbx+4], bpl
0x180008064  cmovz   rdi, rax
0x180008068  jmp     short loc_180008071
0x18000806a  lea     rdi, aException; "Exception"
0x180008071  xor     edx, edx; Val
0x180008073  mov     r8d, 200h; Size
0x180008079  lea     rcx, [rsp+278h+Buffer]; void *
0x18000807e  call    memset_0
0x180008083  test    [rbx+4], bpl
0x180008087  jz      short loc_1800080AC
0x180008089  mov     ebp, [rbx+0Ch]
0x18000808c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x180008093  test    rax, rax
0x180008096  jz      short loc_1800080DC
0x180008098  mov     r8d, 100h
0x18000809e  lea     rdx, [rsp+278h+Buffer]
0x1800080a3  mov     ecx, ebp
0x1800080a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080aa  jmp     short loc_1800080DC
0x1800080ac  mov     ebp, [rbx+8]
0x1800080af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800080b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800080bc  lea     rax, [rsp+278h+Buffer]
0x1800080c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800080c6  mov     r9d, 400h; dwLanguageId
0x1800080cc  mov     r8d, ebp; dwMessageId
0x1800080cf  xor     edx, edx; lpSource
0x1800080d1  mov     ecx, 1200h; dwFlags
0x1800080d6  call    cs:__imp_FormatMessageW
0x1800080dc  lea     rsi, [r14+rsi*2]
0x1800080e0  mov     r9, [rbx+38h]; wchar_t *
0x1800080e4  mov     rax, [rbx+88h]
0x1800080eb  mov     rcx, [rbx+80h]
0x1800080f2  mov     rdx, rsi; wchar_t *
0x1800080f5  test    r9, r9
0x1800080f8  jz      short loc_18000811C
0x1800080fa  mov     [rsp+278h+Arguments], rax
0x1800080ff  mov     qword ptr [rsp+278h+nSize], rcx
0x180008104  mov     eax, [rbx+40h]
0x180008107  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000810b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180008112  mov     rcx, r14; this
0x180008115  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000811a  jmp     short loc_180008133
0x18000811c  mov     [rsp+278h+lpBuffer], rax
0x180008121  mov     r9, rcx; wchar_t *
0x180008124  lea     r8, aHsP; "%hs!%p: "
0x18000812b  mov     rcx, r14; this
0x18000812e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008133  mov     r14, rax
0x180008136  mov     r9, [rbx+90h]; wchar_t *
0x18000813d  test    r9, r9
0x180008140  jz      short loc_180008157
0x180008142  lea     r8, aCallerP; "(caller: %p) "
0x180008149  mov     rdx, rsi; wchar_t *
0x18000814c  mov     rcx, rax; this
0x18000814f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008154  mov     r14, rax
0x180008157  call    cs:__imp_GetCurrentThreadId
0x18000815d  lea     rcx, [rsp+278h+Buffer]
0x180008162  mov     [rsp+278h+var_240], rcx
0x180008167  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000816b  mov     [rsp+278h+nSize], eax
0x18000816f  mov     eax, [rbx+44h]
0x180008172  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008176  mov     r9, rdi; wchar_t *
0x180008179  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008180  mov     rdx, rsi; wchar_t *
0x180008183  mov     rcx, r14; this
0x180008186  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000818b  cmp     [rbx+18h], r15
0x18000818f  jnz     short loc_1800081A1
0x180008191  cmp     [rbx+48h], r15
0x180008195  jnz     short loc_1800081A1
0x180008197  cmp     [rbx+30h], r15
0x18000819b  jz      loc_180008231
0x1800081a1  lea     r8, asc_18012C310; "    "
0x1800081a8  mov     rdx, rsi; wchar_t *
0x1800081ab  mov     rcx, rax; this
0x1800081ae  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800081b3  mov     r9, [rbx+18h]; wchar_t *
0x1800081b7  test    r9, r9
0x1800081ba  jz      short loc_1800081CE
0x1800081bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800081c3  mov     rdx, rsi; wchar_t *
0x1800081c6  mov     rcx, rax; this
0x1800081c9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800081ce  mov     r9, [rbx+48h]; wchar_t *
0x1800081d2  test    r9, r9
0x1800081d5  jz      short loc_1800081E9
0x1800081d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800081de  mov     rdx, rsi; wchar_t *
0x1800081e1  mov     rcx, rax; this
0x1800081e4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800081e9  mov     rcx, [rbx+28h]
0x1800081ed  mov     r9, [rbx+30h]; wchar_t *
0x1800081f1  mov     rdx, rsi; wchar_t *
0x1800081f4  test    rcx, rcx
0x1800081f7  jz      short loc_18000820F
0x1800081f9  mov     [rsp+278h+lpBuffer], rcx
0x1800081fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180008205  mov     rcx, rax; this
0x180008208  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000820d  jmp     short loc_180008231
0x18000820f  mov     rcx, rax; this
0x180008212  test    r9, r9
0x180008215  jz      short loc_180008225
0x180008217  lea     r8, aHs; "[%hs]\n"
0x18000821e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008223  jmp     short loc_180008231
0x180008225  lea     r8, asc_18012C388; "\n"
0x18000822c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180008231  xor     eax, eax
0x180008233  mov     rcx, [rsp+278h+var_38]
0x18000823b  xor     rcx, rsp; StackCookie
0x18000823e  call    __security_check_cookie
0x180008243  mov     rbx, [rsp+278h+arg_18]
0x18000824b  add     rsp, 250h
0x180008252  pop     r15
0x180008254  pop     r14
0x180008256  pop     rdi
0x180008257  pop     rsi
0x180008258  pop     rbp
0x180008259  retn
```
