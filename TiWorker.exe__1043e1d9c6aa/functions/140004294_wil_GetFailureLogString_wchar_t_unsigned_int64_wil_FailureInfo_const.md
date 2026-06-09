# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004294`
- end: `0x14000454a`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x140003670`
- `0x140004c4c`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x140004294`
- `0x140004f4c`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004447`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400043c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400043c6`

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
          v8 = (const char *)&qword_14002E968;
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
  memset_0(Buffer, 0, sizeof(Buffer));
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
0x140004294  mov     [rsp+arg_18], rbx
0x140004299  push    rbp
0x14000429a  push    rsi
0x14000429b  push    rdi
0x14000429c  push    r14
0x14000429e  push    r15
0x1400042a0  sub     rsp, 250h
0x1400042a7  mov     rax, cs:__security_cookie
0x1400042ae  xor     rax, rsp
0x1400042b1  mov     [rsp+278h+var_38], rax
0x1400042b9  xor     r15d, r15d
0x1400042bc  mov     rbx, r8
0x1400042bf  mov     rsi, rdx
0x1400042c2  mov     r14, rcx
0x1400042c5  test    rdx, rdx
0x1400042c8  jz      loc_140004521
0x1400042ce  test    rcx, rcx
0x1400042d1  jz      loc_140004521
0x1400042d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042de  mov     [rcx], r15w
0x1400042e2  test    rax, rax
0x1400042e5  jz      short loc_140004308
0x1400042e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400042ee  jz      short loc_140004308
0x1400042f0  mov     r8, rdx
0x1400042f3  mov     rdx, rcx
0x1400042f6  mov     rcx, rbx
0x1400042f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042fe  cmp     [r14], r15w
0x140004302  jnz     loc_140004521
0x140004308  mov     ecx, [rbx]
0x14000430a  mov     bpl, 8
0x14000430d  test    ecx, ecx
0x14000430f  jz      short loc_14000435A
0x140004311  sub     ecx, 1
0x140004314  jz      short loc_140004342
0x140004316  sub     ecx, 1
0x140004319  jz      short loc_140004332
0x14000431b  cmp     ecx, 1
0x14000431e  jz      short loc_140004329
0x140004320  lea     rdi, qword_14002E968
0x140004327  jmp     short loc_140004361
0x140004329  lea     rdi, aFailfast; "FailFast"
0x140004330  jmp     short loc_140004361
0x140004332  lea     rax, aLoghr; "LogHr"
0x140004339  lea     rdi, aLognt; "LogNt"
0x140004340  jmp     short loc_140004350
0x140004342  lea     rax, aReturnhr; "ReturnHr"
0x140004349  lea     rdi, aReturnnt; "ReturnNt"
0x140004350  test    [rbx+4], bpl
0x140004354  cmovz   rdi, rax
0x140004358  jmp     short loc_140004361
0x14000435a  lea     rdi, aException; "Exception"
0x140004361  xor     edx, edx; Val
0x140004363  lea     rcx, [rsp+278h+Buffer]; void *
0x140004368  mov     r8d, 200h; Size
0x14000436e  call    memset_0
0x140004373  test    [rbx+4], bpl
0x140004377  jz      short loc_14000439C
0x140004379  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140004380  mov     ebp, [rbx+0Ch]
0x140004383  test    rax, rax
0x140004386  jz      short loc_1400043CC
0x140004388  mov     r8d, 100h
0x14000438e  lea     rdx, [rsp+278h+Buffer]
0x140004393  mov     ecx, ebp
0x140004395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000439a  jmp     short loc_1400043CC
0x14000439c  mov     ebp, [rbx+8]
0x14000439f  lea     rax, [rsp+278h+Buffer]
0x1400043a4  mov     [rsp+278h+Arguments], r15; Arguments
0x1400043a9  mov     r8d, ebp; dwMessageId
0x1400043ac  mov     [rsp+278h+nSize], 100h; nSize
0x1400043b4  mov     r9d, 400h; dwLanguageId
0x1400043ba  xor     edx, edx; lpSource
0x1400043bc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400043c1  mov     ecx, 1200h; dwFlags
0x1400043c6  call    cs:__imp_FormatMessageW
0x1400043cc  mov     r9, [rbx+38h]; wchar_t *
0x1400043d0  lea     rsi, [r14+rsi*2]
0x1400043d4  mov     rax, [rbx+88h]
0x1400043db  mov     rdx, rsi; wchar_t *
0x1400043de  mov     rcx, [rbx+80h]
0x1400043e5  test    r9, r9
0x1400043e8  jz      short loc_14000440C
0x1400043ea  mov     [rsp+278h+Arguments], rax
0x1400043ef  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400043f6  mov     eax, [rbx+40h]
0x1400043f9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400043fe  mov     rcx, r14; this
0x140004401  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004405  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000440a  jmp     short loc_140004423
0x14000440c  mov     r9, rcx; wchar_t *
0x14000440f  mov     [rsp+278h+lpBuffer], rax
0x140004414  mov     rcx, r14; this
0x140004417  lea     r8, aHsP; "%hs!%p: "
0x14000441e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004423  mov     r9, [rbx+90h]; wchar_t *
0x14000442a  mov     r14, rax
0x14000442d  test    r9, r9
0x140004430  jz      short loc_140004447
0x140004432  lea     r8, aCallerP; "(caller: %p) "
0x140004439  mov     rdx, rsi; wchar_t *
0x14000443c  mov     rcx, rax; this
0x14000443f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004444  mov     r14, rax
0x140004447  call    cs:__imp_GetCurrentThreadId
0x14000444d  lea     rcx, [rsp+278h+Buffer]
0x140004452  mov     r9, rdi; wchar_t *
0x140004455  mov     [rsp+278h+var_240], rcx
0x14000445a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004461  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004465  mov     rdx, rsi; wchar_t *
0x140004468  mov     [rsp+278h+nSize], eax
0x14000446c  mov     rcx, r14; this
0x14000446f  mov     eax, [rbx+44h]
0x140004472  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004476  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000447b  cmp     [rbx+18h], r15
0x14000447f  jnz     short loc_140004491
0x140004481  cmp     [rbx+48h], r15
0x140004485  jnz     short loc_140004491
0x140004487  cmp     [rbx+30h], r15
0x14000448b  jz      loc_140004521
0x140004491  lea     r8, asc_14002EA58; "    "
0x140004498  mov     rdx, rsi; wchar_t *
0x14000449b  mov     rcx, rax; this
0x14000449e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400044a3  mov     r9, [rbx+18h]; wchar_t *
0x1400044a7  test    r9, r9
0x1400044aa  jz      short loc_1400044BE
0x1400044ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400044b3  mov     rdx, rsi; wchar_t *
0x1400044b6  mov     rcx, rax; this
0x1400044b9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400044be  mov     r9, [rbx+48h]; wchar_t *
0x1400044c2  test    r9, r9
0x1400044c5  jz      short loc_1400044D9
0x1400044c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400044ce  mov     rdx, rsi; wchar_t *
0x1400044d1  mov     rcx, rax; this
0x1400044d4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400044d9  mov     rcx, [rbx+28h]
0x1400044dd  mov     rdx, rsi; wchar_t *
0x1400044e0  mov     r9, [rbx+30h]; wchar_t *
0x1400044e4  test    rcx, rcx
0x1400044e7  jz      short loc_1400044FF
0x1400044e9  mov     [rsp+278h+lpBuffer], rcx
0x1400044ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1400044f5  mov     rcx, rax; this
0x1400044f8  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400044fd  jmp     short loc_140004521
0x1400044ff  mov     rcx, rax; this
0x140004502  test    r9, r9
0x140004505  jz      short loc_140004515
0x140004507  lea     r8, aHs; "[%hs]\n"
0x14000450e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004513  jmp     short loc_140004521
0x140004515  lea     r8, asc_14002EAD0; "\n"
0x14000451c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140004521  xor     eax, eax
0x140004523  mov     rcx, [rsp+278h+var_38]
0x14000452b  xor     rcx, rsp; StackCookie
0x14000452e  call    __security_check_cookie
0x140004533  mov     rbx, [rsp+278h+arg_18]
0x14000453b  add     rsp, 250h
0x140004542  pop     r15
0x140004544  pop     r14
0x140004546  pop     rdi
0x140004547  pop     rsi
0x140004548  pop     rbp
0x140004549  retn
```
