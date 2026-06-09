# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000b174`
- end: `0x18000b42a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a28c`
- `0x18000bb0c`
- `0x18000cfa0`

## callees

- `0x180008830`
- `0x1800093c4`
- `0x18000b174`
- `0x18000be0c`
- `0x18004a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x18000b2a6`
- `KERNEL32!FormatMessageW` at `0x18000b2a6`
- `KERNEL32!GetCurrentThreadId` at `0x18000b327`
- `KERNEL32!GetCurrentThreadId` at `0x18000b327`

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
          v7 = (const char *)&qword_18004CC60;
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
0x18000b174  mov     [rsp+arg_18], rbx
0x18000b179  push    rbp
0x18000b17a  push    rsi
0x18000b17b  push    rdi
0x18000b17c  push    r14
0x18000b17e  push    r15
0x18000b180  sub     rsp, 250h
0x18000b187  mov     rax, cs:__security_cookie
0x18000b18e  xor     rax, rsp
0x18000b191  mov     [rsp+278h+var_38], rax
0x18000b199  mov     rbx, r8
0x18000b19c  mov     rsi, rdx
0x18000b19f  mov     r14, rcx
0x18000b1a2  xor     r15d, r15d
0x18000b1a5  test    rdx, rdx
0x18000b1a8  jz      loc_18000B401
0x18000b1ae  test    rcx, rcx
0x18000b1b1  jz      loc_18000B401
0x18000b1b7  mov     [rcx], r15w
0x18000b1bb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000b1c2  test    rax, rax
0x18000b1c5  jz      short loc_18000B1E8
0x18000b1c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000b1ce  jz      short loc_18000B1E8
0x18000b1d0  mov     r8, rdx
0x18000b1d3  mov     rdx, rcx
0x18000b1d6  mov     rcx, rbx
0x18000b1d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b1de  cmp     [r14], r15w
0x18000b1e2  jnz     loc_18000B401
0x18000b1e8  mov     ecx, [rbx]
0x18000b1ea  mov     bpl, 8
0x18000b1ed  test    ecx, ecx
0x18000b1ef  jz      short loc_18000B23A
0x18000b1f1  sub     ecx, 1
0x18000b1f4  jz      short loc_18000B222
0x18000b1f6  sub     ecx, 1
0x18000b1f9  jz      short loc_18000B212
0x18000b1fb  cmp     ecx, 1
0x18000b1fe  jz      short loc_18000B209
0x18000b200  lea     rdi, qword_18004CC60
0x18000b207  jmp     short loc_18000B241
0x18000b209  lea     rdi, aFailfast; "FailFast"
0x18000b210  jmp     short loc_18000B241
0x18000b212  lea     rax, aLoghr; "LogHr"
0x18000b219  lea     rdi, aLognt; "LogNt"
0x18000b220  jmp     short loc_18000B230
0x18000b222  lea     rax, aReturnhr; "ReturnHr"
0x18000b229  lea     rdi, aReturnnt; "ReturnNt"
0x18000b230  test    [rbx+4], bpl
0x18000b234  cmovz   rdi, rax
0x18000b238  jmp     short loc_18000B241
0x18000b23a  lea     rdi, aException; "Exception"
0x18000b241  xor     edx, edx; Val
0x18000b243  mov     r8d, 200h; Size
0x18000b249  lea     rcx, [rsp+278h+Buffer]; void *
0x18000b24e  call    memset_0
0x18000b253  test    [rbx+4], bpl
0x18000b257  jz      short loc_18000B27C
0x18000b259  mov     ebp, [rbx+0Ch]
0x18000b25c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x18000b263  test    rax, rax
0x18000b266  jz      short loc_18000B2AC
0x18000b268  mov     r8d, 100h
0x18000b26e  lea     rdx, [rsp+278h+Buffer]
0x18000b273  mov     ecx, ebp
0x18000b275  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b27a  jmp     short loc_18000B2AC
0x18000b27c  mov     ebp, [rbx+8]
0x18000b27f  mov     [rsp+278h+Arguments], r15; Arguments
0x18000b284  mov     [rsp+278h+nSize], 100h; nSize
0x18000b28c  lea     rax, [rsp+278h+Buffer]
0x18000b291  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000b296  mov     r9d, 400h; dwLanguageId
0x18000b29c  mov     r8d, ebp; dwMessageId
0x18000b29f  xor     edx, edx; lpSource
0x18000b2a1  mov     ecx, 1200h; dwFlags
0x18000b2a6  call    cs:__imp_FormatMessageW
0x18000b2ac  lea     rsi, [r14+rsi*2]
0x18000b2b0  mov     r9, [rbx+38h]; wchar_t *
0x18000b2b4  mov     rax, [rbx+88h]
0x18000b2bb  mov     rcx, [rbx+80h]
0x18000b2c2  mov     rdx, rsi; wchar_t *
0x18000b2c5  test    r9, r9
0x18000b2c8  jz      short loc_18000B2EC
0x18000b2ca  mov     [rsp+278h+Arguments], rax
0x18000b2cf  mov     qword ptr [rsp+278h+nSize], rcx
0x18000b2d4  mov     eax, [rbx+40h]
0x18000b2d7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b2db  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000b2e2  mov     rcx, r14; this
0x18000b2e5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b2ea  jmp     short loc_18000B303
0x18000b2ec  mov     [rsp+278h+lpBuffer], rax
0x18000b2f1  mov     r9, rcx; wchar_t *
0x18000b2f4  lea     r8, aHsP; "%hs!%p: "
0x18000b2fb  mov     rcx, r14; this
0x18000b2fe  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b303  mov     r14, rax
0x18000b306  mov     r9, [rbx+90h]; wchar_t *
0x18000b30d  test    r9, r9
0x18000b310  jz      short loc_18000B327
0x18000b312  lea     r8, aCallerP; "(caller: %p) "
0x18000b319  mov     rdx, rsi; wchar_t *
0x18000b31c  mov     rcx, rax; this
0x18000b31f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b324  mov     r14, rax
0x18000b327  call    cs:__imp_GetCurrentThreadId
0x18000b32d  lea     rcx, [rsp+278h+Buffer]
0x18000b332  mov     [rsp+278h+var_240], rcx
0x18000b337  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000b33b  mov     [rsp+278h+nSize], eax
0x18000b33f  mov     eax, [rbx+44h]
0x18000b342  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000b346  mov     r9, rdi; wchar_t *
0x18000b349  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000b350  mov     rdx, rsi; wchar_t *
0x18000b353  mov     rcx, r14; this
0x18000b356  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b35b  cmp     [rbx+18h], r15
0x18000b35f  jnz     short loc_18000B371
0x18000b361  cmp     [rbx+48h], r15
0x18000b365  jnz     short loc_18000B371
0x18000b367  cmp     [rbx+30h], r15
0x18000b36b  jz      loc_18000B401
0x18000b371  lea     r8, asc_18004CD68; "    "
0x18000b378  mov     rdx, rsi; wchar_t *
0x18000b37b  mov     rcx, rax; this
0x18000b37e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b383  mov     r9, [rbx+18h]; wchar_t *
0x18000b387  test    r9, r9
0x18000b38a  jz      short loc_18000B39E
0x18000b38c  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000b393  mov     rdx, rsi; wchar_t *
0x18000b396  mov     rcx, rax; this
0x18000b399  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b39e  mov     r9, [rbx+48h]; wchar_t *
0x18000b3a2  test    r9, r9
0x18000b3a5  jz      short loc_18000B3B9
0x18000b3a7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000b3ae  mov     rdx, rsi; wchar_t *
0x18000b3b1  mov     rcx, rax; this
0x18000b3b4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b3b9  mov     rcx, [rbx+28h]
0x18000b3bd  mov     r9, [rbx+30h]; wchar_t *
0x18000b3c1  mov     rdx, rsi; wchar_t *
0x18000b3c4  test    rcx, rcx
0x18000b3c7  jz      short loc_18000B3DF
0x18000b3c9  mov     [rsp+278h+lpBuffer], rcx
0x18000b3ce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000b3d5  mov     rcx, rax; this
0x18000b3d8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b3dd  jmp     short loc_18000B401
0x18000b3df  mov     rcx, rax; this
0x18000b3e2  test    r9, r9
0x18000b3e5  jz      short loc_18000B3F5
0x18000b3e7  lea     r8, aHs; "[%hs]\n"
0x18000b3ee  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b3f3  jmp     short loc_18000B401
0x18000b3f5  lea     r8, asc_18004CDE0; "\n"
0x18000b3fc  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000b401  xor     eax, eax
0x18000b403  mov     rcx, [rsp+278h+var_38]
0x18000b40b  xor     rcx, rsp; StackCookie
0x18000b40e  call    __security_check_cookie
0x18000b413  mov     rbx, [rsp+278h+arg_18]
0x18000b41b  add     rsp, 250h
0x18000b422  pop     r15
0x18000b424  pop     r14
0x18000b426  pop     rdi
0x18000b427  pop     rsi
0x18000b428  pop     rbp
0x18000b429  retn
```
