# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800056d4`
- end: `0x18000598a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000478c`
- `0x180006184`
- `0x180006650`
- `0x1800078c0`

## callees

- `0x180003560`
- `0x180003fd4`
- `0x1800056d4`
- `0x180006484`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005887`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005887`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005806`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005806`

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
          v7 = (const char *)&qword_180033B90;
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
0x1800056d4  mov     [rsp+arg_18], rbx
0x1800056d9  push    rbp
0x1800056da  push    rsi
0x1800056db  push    rdi
0x1800056dc  push    r14
0x1800056de  push    r15
0x1800056e0  sub     rsp, 250h
0x1800056e7  mov     rax, cs:__security_cookie
0x1800056ee  xor     rax, rsp
0x1800056f1  mov     [rsp+278h+var_38], rax
0x1800056f9  mov     rbx, r8
0x1800056fc  mov     rsi, rdx
0x1800056ff  mov     r14, rcx
0x180005702  xor     r15d, r15d
0x180005705  test    rdx, rdx
0x180005708  jz      loc_180005961
0x18000570e  test    rcx, rcx
0x180005711  jz      loc_180005961
0x180005717  mov     [rcx], r15w
0x18000571b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005722  test    rax, rax
0x180005725  jz      short loc_180005748
0x180005727  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000572e  jz      short loc_180005748
0x180005730  mov     r8, rdx
0x180005733  mov     rdx, rcx
0x180005736  mov     rcx, rbx
0x180005739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000573e  cmp     [r14], r15w
0x180005742  jnz     loc_180005961
0x180005748  mov     ecx, [rbx]
0x18000574a  mov     bpl, 8
0x18000574d  test    ecx, ecx
0x18000574f  jz      short loc_18000579A
0x180005751  sub     ecx, 1
0x180005754  jz      short loc_180005782
0x180005756  sub     ecx, 1
0x180005759  jz      short loc_180005772
0x18000575b  cmp     ecx, 1
0x18000575e  jz      short loc_180005769
0x180005760  lea     rdi, qword_180033B90
0x180005767  jmp     short loc_1800057A1
0x180005769  lea     rdi, aFailfast; "FailFast"
0x180005770  jmp     short loc_1800057A1
0x180005772  lea     rax, aLoghr; "LogHr"
0x180005779  lea     rdi, aLognt; "LogNt"
0x180005780  jmp     short loc_180005790
0x180005782  lea     rax, aReturnhr; "ReturnHr"
0x180005789  lea     rdi, aReturnnt; "ReturnNt"
0x180005790  test    [rbx+4], bpl
0x180005794  cmovz   rdi, rax
0x180005798  jmp     short loc_1800057A1
0x18000579a  lea     rdi, aException; "Exception"
0x1800057a1  xor     edx, edx; Val
0x1800057a3  mov     r8d, 200h; Size
0x1800057a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800057ae  call    memset_0
0x1800057b3  test    [rbx+4], bpl
0x1800057b7  jz      short loc_1800057DC
0x1800057b9  mov     ebp, [rbx+0Ch]
0x1800057bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800057c3  test    rax, rax
0x1800057c6  jz      short loc_18000580C
0x1800057c8  mov     r8d, 100h
0x1800057ce  lea     rdx, [rsp+278h+Buffer]
0x1800057d3  mov     ecx, ebp
0x1800057d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057da  jmp     short loc_18000580C
0x1800057dc  mov     ebp, [rbx+8]
0x1800057df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800057e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800057ec  lea     rax, [rsp+278h+Buffer]
0x1800057f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800057f6  mov     r9d, 400h; dwLanguageId
0x1800057fc  mov     r8d, ebp; dwMessageId
0x1800057ff  xor     edx, edx; lpSource
0x180005801  mov     ecx, 1200h; dwFlags
0x180005806  call    cs:__imp_FormatMessageW
0x18000580c  lea     rsi, [r14+rsi*2]
0x180005810  mov     r9, [rbx+38h]; wchar_t *
0x180005814  mov     rax, [rbx+88h]
0x18000581b  mov     rcx, [rbx+80h]
0x180005822  mov     rdx, rsi; wchar_t *
0x180005825  test    r9, r9
0x180005828  jz      short loc_18000584C
0x18000582a  mov     [rsp+278h+Arguments], rax
0x18000582f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005834  mov     eax, [rbx+40h]
0x180005837  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000583b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005842  mov     rcx, r14; this
0x180005845  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000584a  jmp     short loc_180005863
0x18000584c  mov     [rsp+278h+lpBuffer], rax
0x180005851  mov     r9, rcx; wchar_t *
0x180005854  lea     r8, aHsP; "%hs!%p: "
0x18000585b  mov     rcx, r14; this
0x18000585e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005863  mov     r14, rax
0x180005866  mov     r9, [rbx+90h]; wchar_t *
0x18000586d  test    r9, r9
0x180005870  jz      short loc_180005887
0x180005872  lea     r8, aCallerP; "(caller: %p) "
0x180005879  mov     rdx, rsi; wchar_t *
0x18000587c  mov     rcx, rax; this
0x18000587f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005884  mov     r14, rax
0x180005887  call    cs:__imp_GetCurrentThreadId
0x18000588d  lea     rcx, [rsp+278h+Buffer]
0x180005892  mov     [rsp+278h+var_240], rcx
0x180005897  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000589b  mov     [rsp+278h+nSize], eax
0x18000589f  mov     eax, [rbx+44h]
0x1800058a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800058a6  mov     r9, rdi; wchar_t *
0x1800058a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800058b0  mov     rdx, rsi; wchar_t *
0x1800058b3  mov     rcx, r14; this
0x1800058b6  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800058bb  cmp     [rbx+18h], r15
0x1800058bf  jnz     short loc_1800058D1
0x1800058c1  cmp     [rbx+48h], r15
0x1800058c5  jnz     short loc_1800058D1
0x1800058c7  cmp     [rbx+30h], r15
0x1800058cb  jz      loc_180005961
0x1800058d1  lea     r8, asc_180033C98; "    "
0x1800058d8  mov     rdx, rsi; wchar_t *
0x1800058db  mov     rcx, rax; this
0x1800058de  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800058e3  mov     r9, [rbx+18h]; wchar_t *
0x1800058e7  test    r9, r9
0x1800058ea  jz      short loc_1800058FE
0x1800058ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800058f3  mov     rdx, rsi; wchar_t *
0x1800058f6  mov     rcx, rax; this
0x1800058f9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800058fe  mov     r9, [rbx+48h]; wchar_t *
0x180005902  test    r9, r9
0x180005905  jz      short loc_180005919
0x180005907  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000590e  mov     rdx, rsi; wchar_t *
0x180005911  mov     rcx, rax; this
0x180005914  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005919  mov     rcx, [rbx+28h]
0x18000591d  mov     r9, [rbx+30h]; wchar_t *
0x180005921  mov     rdx, rsi; wchar_t *
0x180005924  test    rcx, rcx
0x180005927  jz      short loc_18000593F
0x180005929  mov     [rsp+278h+lpBuffer], rcx
0x18000592e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005935  mov     rcx, rax; this
0x180005938  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000593d  jmp     short loc_180005961
0x18000593f  mov     rcx, rax; this
0x180005942  test    r9, r9
0x180005945  jz      short loc_180005955
0x180005947  lea     r8, aHs; "[%hs]\n"
0x18000594e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005953  jmp     short loc_180005961
0x180005955  lea     r8, asc_180033D10; "\n"
0x18000595c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180005961  xor     eax, eax
0x180005963  mov     rcx, [rsp+278h+var_38]
0x18000596b  xor     rcx, rsp; StackCookie
0x18000596e  call    __security_check_cookie
0x180005973  mov     rbx, [rsp+278h+arg_18]
0x18000597b  add     rsp, 250h
0x180005982  pop     r15
0x180005984  pop     r14
0x180005986  pop     rdi
0x180005987  pop     rsi
0x180005988  pop     rbp
0x180005989  retn
```
