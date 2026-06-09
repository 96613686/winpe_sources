# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003d120`
- end: `0x18003d3e3`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18003cbd0`
- `0x18003d3ec`

## callees

- `0x1800293a0`
- `0x18003d120`
- `0x18003d704`
- `0x180099cb0`
- `0x1800a0020`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18003d2d9`
- `KERNEL32!GetCurrentThreadId` at `0x18003d2d9`
- `KERNEL32!FormatMessageW` at `0x18003d252`
- `KERNEL32!FormatMessageW` at `0x18003d252`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const wchar_t *v11; // r9
  wchar_t *v12; // rsi
  __int64 v13; // rax
  wchar_t *v14; // rax
  const wchar_t *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, wchar_t *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&byte_1800AEF2D;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const wchar_t **)(a3 + 128), v13);
  }
  v15 = *(const wchar_t **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003d120  mov     [rsp+arg_18], rbx
0x18003d125  push    rbp
0x18003d126  push    rsi
0x18003d127  push    rdi
0x18003d128  push    r14
0x18003d12a  push    r15
0x18003d12c  sub     rsp, 250h
0x18003d133  mov     rax, cs:__security_cookie
0x18003d13a  xor     rax, rsp
0x18003d13d  mov     [rsp+278h+var_38], rax
0x18003d145  xor     r15d, r15d
0x18003d148  mov     rbx, r8
0x18003d14b  mov     rsi, rdx
0x18003d14e  mov     r14, rcx
0x18003d151  test    rdx, rdx
0x18003d154  jz      loc_18003D3B9
0x18003d15a  test    rcx, rcx
0x18003d15d  jz      loc_18003D3B9
0x18003d163  mov     rax, cs:g_pfnResultLoggingCallback
0x18003d16a  mov     [rcx], r15w
0x18003d16e  test    rax, rax
0x18003d171  jz      short loc_18003D194
0x18003d173  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003d17a  jz      short loc_18003D194
0x18003d17c  mov     r8, rdx
0x18003d17f  mov     rdx, rcx
0x18003d182  mov     rcx, rbx
0x18003d185  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d18a  cmp     [r14], r15w
0x18003d18e  jnz     loc_18003D3B9
0x18003d194  mov     ecx, [rbx]
0x18003d196  mov     bpl, 8
0x18003d199  test    ecx, ecx
0x18003d19b  jz      short loc_18003D1E6
0x18003d19d  sub     ecx, 1
0x18003d1a0  jz      short loc_18003D1CE
0x18003d1a2  sub     ecx, 1
0x18003d1a5  jz      short loc_18003D1BE
0x18003d1a7  cmp     ecx, 1
0x18003d1aa  jz      short loc_18003D1B5
0x18003d1ac  lea     rdi, byte_1800AEF2D
0x18003d1b3  jmp     short loc_18003D1ED
0x18003d1b5  lea     rdi, aFailfast; "FailFast"
0x18003d1bc  jmp     short loc_18003D1ED
0x18003d1be  lea     rax, aLoghr; "LogHr"
0x18003d1c5  lea     rdi, aLognt; "LogNt"
0x18003d1cc  jmp     short loc_18003D1DC
0x18003d1ce  lea     rax, aReturnhr; "ReturnHr"
0x18003d1d5  lea     rdi, aReturnnt; "ReturnNt"
0x18003d1dc  test    [rbx+4], bpl
0x18003d1e0  cmovz   rdi, rax
0x18003d1e4  jmp     short loc_18003D1ED
0x18003d1e6  lea     rdi, aException; "Exception"
0x18003d1ed  xor     edx, edx; Val
0x18003d1ef  lea     rcx, [rsp+278h+Buffer]; void *
0x18003d1f4  mov     r8d, 200h; Size
0x18003d1fa  call    memset
0x18003d1ff  test    [rbx+4], bpl
0x18003d203  jz      short loc_18003D228
0x18003d205  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18003d20c  mov     ebp, [rbx+0Ch]
0x18003d20f  test    rax, rax
0x18003d212  jz      short loc_18003D25E
0x18003d214  mov     r8d, 100h
0x18003d21a  lea     rdx, [rsp+278h+Buffer]
0x18003d21f  mov     ecx, ebp
0x18003d221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003d226  jmp     short loc_18003D25E
0x18003d228  mov     ebp, [rbx+8]
0x18003d22b  lea     rax, [rsp+278h+Buffer]
0x18003d230  mov     [rsp+278h+Arguments], r15; Arguments
0x18003d235  mov     r8d, ebp; dwMessageId
0x18003d238  mov     [rsp+278h+nSize], 100h; nSize
0x18003d240  mov     r9d, 400h; dwLanguageId
0x18003d246  xor     edx, edx; lpSource
0x18003d248  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003d24d  mov     ecx, 1200h; dwFlags
0x18003d252  call    cs:__imp_FormatMessageW
0x18003d259  nop     dword ptr [rax+rax+00h]
0x18003d25e  mov     r9, [rbx+38h]; wchar_t *
0x18003d262  lea     rsi, [r14+rsi*2]
0x18003d266  mov     rax, [rbx+88h]
0x18003d26d  mov     rdx, rsi; wchar_t *
0x18003d270  mov     rcx, [rbx+80h]
0x18003d277  test    r9, r9
0x18003d27a  jz      short loc_18003D29E
0x18003d27c  mov     [rsp+278h+Arguments], rax
0x18003d281  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003d288  mov     eax, [rbx+40h]
0x18003d28b  mov     qword ptr [rsp+278h+nSize], rcx
0x18003d290  mov     rcx, r14; this
0x18003d293  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003d297  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d29c  jmp     short loc_18003D2B5
0x18003d29e  mov     r9, rcx; wchar_t *
0x18003d2a1  mov     [rsp+278h+lpBuffer], rax
0x18003d2a6  mov     rcx, r14; this
0x18003d2a9  lea     r8, aHsP; "%hs!%p: "
0x18003d2b0  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d2b5  mov     r9, [rbx+90h]; wchar_t *
0x18003d2bc  mov     r14, rax
0x18003d2bf  test    r9, r9
0x18003d2c2  jz      short loc_18003D2D9
0x18003d2c4  lea     r8, aCallerP; "(caller: %p) "
0x18003d2cb  mov     rdx, rsi; wchar_t *
0x18003d2ce  mov     rcx, rax; this
0x18003d2d1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d2d6  mov     r14, rax
0x18003d2d9  call    cs:__imp_GetCurrentThreadId
0x18003d2e0  nop     dword ptr [rax+rax+00h]
0x18003d2e5  lea     rcx, [rsp+278h+Buffer]
0x18003d2ea  mov     r9, rdi; wchar_t *
0x18003d2ed  mov     [rsp+278h+var_240], rcx
0x18003d2f2  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003d2f9  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003d2fd  mov     rdx, rsi; wchar_t *
0x18003d300  mov     [rsp+278h+nSize], eax
0x18003d304  mov     rcx, r14; this
0x18003d307  mov     eax, [rbx+44h]
0x18003d30a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003d30e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d313  cmp     [rbx+18h], r15
0x18003d317  jnz     short loc_18003D329
0x18003d319  cmp     [rbx+48h], r15
0x18003d31d  jnz     short loc_18003D329
0x18003d31f  cmp     [rbx+30h], r15
0x18003d323  jz      loc_18003D3B9
0x18003d329  lea     r8, asc_1800AF018; "    "
0x18003d330  mov     rdx, rsi; wchar_t *
0x18003d333  mov     rcx, rax; this
0x18003d336  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d33b  mov     r9, [rbx+18h]; wchar_t *
0x18003d33f  test    r9, r9
0x18003d342  jz      short loc_18003D356
0x18003d344  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003d34b  mov     rdx, rsi; wchar_t *
0x18003d34e  mov     rcx, rax; this
0x18003d351  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d356  mov     r9, [rbx+48h]; wchar_t *
0x18003d35a  test    r9, r9
0x18003d35d  jz      short loc_18003D371
0x18003d35f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003d366  mov     rdx, rsi; wchar_t *
0x18003d369  mov     rcx, rax; this
0x18003d36c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d371  mov     rcx, [rbx+28h]
0x18003d375  mov     rdx, rsi; wchar_t *
0x18003d378  mov     r9, [rbx+30h]; wchar_t *
0x18003d37c  test    rcx, rcx
0x18003d37f  jz      short loc_18003D397
0x18003d381  mov     [rsp+278h+lpBuffer], rcx
0x18003d386  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003d38d  mov     rcx, rax; this
0x18003d390  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d395  jmp     short loc_18003D3B9
0x18003d397  mov     rcx, rax; this
0x18003d39a  test    r9, r9
0x18003d39d  jz      short loc_18003D3AD
0x18003d39f  lea     r8, aHs_0; "[%hs]\n"
0x18003d3a6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d3ab  jmp     short loc_18003D3B9
0x18003d3ad  lea     r8, asc_1800AF090; "\n"
0x18003d3b4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18003d3b9  xor     eax, eax
0x18003d3bb  mov     rcx, [rsp+278h+var_38]
0x18003d3c3  xor     rcx, rsp; StackCookie
0x18003d3c6  call    __security_check_cookie
0x18003d3cb  mov     rbx, [rsp+278h+arg_18]
0x18003d3d3  add     rsp, 250h
0x18003d3da  pop     r15
0x18003d3dc  pop     r14
0x18003d3de  pop     rdi
0x18003d3df  pop     rsi
0x18003d3e0  pop     rbp
0x18003d3e1  retn
```
