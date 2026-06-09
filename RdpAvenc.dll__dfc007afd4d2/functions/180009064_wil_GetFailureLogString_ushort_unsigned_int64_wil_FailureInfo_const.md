# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180009064`
- end: `0x18000931a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x1800077dc`
- `0x180007a5c`
- `0x1800099c8`
- `0x18000b190`
- `0x18000b688`
- `0x180083086`
- `0x1800831ba`

## callees

- `0x180006580`
- `0x180007018`
- `0x180009064`
- `0x180009cc8`
- `0x180089010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009217`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009217`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009196`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009196`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  unsigned __int16 *v10; // rsi
  const unsigned __int16 *v11; // r9
  __int64 v12; // rax
  const unsigned __int16 *v13; // rcx
  unsigned __int16 *v14; // rax
  wil::details *v15; // r14
  const unsigned __int16 *v16; // r9
  wil::details *v17; // rax
  const unsigned __int16 *v18; // r9
  unsigned __int16 *v19; // rax
  const unsigned __int16 *v20; // r9
  const unsigned __int16 *v21; // r9
  const unsigned __int16 *v22; // r9
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
          v7 = (const char *)&qword_18008EBC0;
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
  v10 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
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
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180009064  mov     [rsp+arg_18], rbx
0x180009069  push    rbp
0x18000906a  push    rsi
0x18000906b  push    rdi
0x18000906c  push    r14
0x18000906e  push    r15
0x180009070  sub     rsp, 250h
0x180009077  mov     rax, cs:__security_cookie
0x18000907e  xor     rax, rsp
0x180009081  mov     [rsp+278h+var_38], rax
0x180009089  mov     rbx, r8
0x18000908c  mov     rsi, rdx
0x18000908f  mov     r14, rcx
0x180009092  xor     r15d, r15d
0x180009095  test    rdx, rdx
0x180009098  jz      loc_1800092F1
0x18000909e  test    rcx, rcx
0x1800090a1  jz      loc_1800092F1
0x1800090a7  mov     [rcx], r15w
0x1800090ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090b2  test    rax, rax
0x1800090b5  jz      short loc_1800090D8
0x1800090b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800090be  jz      short loc_1800090D8
0x1800090c0  mov     r8, rdx
0x1800090c3  mov     rdx, rcx
0x1800090c6  mov     rcx, rbx
0x1800090c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090ce  cmp     [r14], r15w
0x1800090d2  jnz     loc_1800092F1
0x1800090d8  mov     ecx, [rbx]
0x1800090da  mov     bpl, 8
0x1800090dd  test    ecx, ecx
0x1800090df  jz      short loc_18000912A
0x1800090e1  sub     ecx, 1
0x1800090e4  jz      short loc_180009112
0x1800090e6  sub     ecx, 1
0x1800090e9  jz      short loc_180009102
0x1800090eb  cmp     ecx, 1
0x1800090ee  jz      short loc_1800090F9
0x1800090f0  lea     rdi, qword_18008EBC0
0x1800090f7  jmp     short loc_180009131
0x1800090f9  lea     rdi, aFailfast; "FailFast"
0x180009100  jmp     short loc_180009131
0x180009102  lea     rax, aLoghr; "LogHr"
0x180009109  lea     rdi, aLognt; "LogNt"
0x180009110  jmp     short loc_180009120
0x180009112  lea     rax, aReturnhr; "ReturnHr"
0x180009119  lea     rdi, aReturnnt; "ReturnNt"
0x180009120  test    [rbx+4], bpl
0x180009124  cmovz   rdi, rax
0x180009128  jmp     short loc_180009131
0x18000912a  lea     rdi, aException; "Exception"
0x180009131  xor     edx, edx; Val
0x180009133  mov     r8d, 200h; Size
0x180009139  lea     rcx, [rsp+278h+Buffer]; void *
0x18000913e  call    memset_0
0x180009143  test    [rbx+4], bpl
0x180009147  jz      short loc_18000916C
0x180009149  mov     ebp, [rbx+0Ch]
0x18000914c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180009153  test    rax, rax
0x180009156  jz      short loc_18000919C
0x180009158  mov     r8d, 100h
0x18000915e  lea     rdx, [rsp+278h+Buffer]
0x180009163  mov     ecx, ebp
0x180009165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000916a  jmp     short loc_18000919C
0x18000916c  mov     ebp, [rbx+8]
0x18000916f  mov     [rsp+278h+Arguments], r15; Arguments
0x180009174  mov     [rsp+278h+nSize], 100h; nSize
0x18000917c  lea     rax, [rsp+278h+Buffer]
0x180009181  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180009186  mov     r9d, 400h; dwLanguageId
0x18000918c  mov     r8d, ebp; dwMessageId
0x18000918f  xor     edx, edx; lpSource
0x180009191  mov     ecx, 1200h; dwFlags
0x180009196  call    cs:__imp_FormatMessageW
0x18000919c  lea     rsi, [r14+rsi*2]
0x1800091a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800091a4  mov     rax, [rbx+88h]
0x1800091ab  mov     rcx, [rbx+80h]
0x1800091b2  mov     rdx, rsi; unsigned __int16 *
0x1800091b5  test    r9, r9
0x1800091b8  jz      short loc_1800091DC
0x1800091ba  mov     [rsp+278h+Arguments], rax
0x1800091bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800091c4  mov     eax, [rbx+40h]
0x1800091c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800091cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800091d2  mov     rcx, r14; this
0x1800091d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800091da  jmp     short loc_1800091F3
0x1800091dc  mov     [rsp+278h+lpBuffer], rax
0x1800091e1  mov     r9, rcx; unsigned __int16 *
0x1800091e4  lea     r8, aHsP; "%hs!%p: "
0x1800091eb  mov     rcx, r14; this
0x1800091ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800091f3  mov     r14, rax
0x1800091f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800091fd  test    r9, r9
0x180009200  jz      short loc_180009217
0x180009202  lea     r8, aCallerP; "(caller: %p) "
0x180009209  mov     rdx, rsi; unsigned __int16 *
0x18000920c  mov     rcx, rax; this
0x18000920f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009214  mov     r14, rax
0x180009217  call    cs:__imp_GetCurrentThreadId
0x18000921d  lea     rcx, [rsp+278h+Buffer]
0x180009222  mov     [rsp+278h+var_240], rcx
0x180009227  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000922b  mov     [rsp+278h+nSize], eax
0x18000922f  mov     eax, [rbx+44h]
0x180009232  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009236  mov     r9, rdi; unsigned __int16 *
0x180009239  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009240  mov     rdx, rsi; unsigned __int16 *
0x180009243  mov     rcx, r14; this
0x180009246  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000924b  cmp     [rbx+18h], r15
0x18000924f  jnz     short loc_180009261
0x180009251  cmp     [rbx+48h], r15
0x180009255  jnz     short loc_180009261
0x180009257  cmp     [rbx+30h], r15
0x18000925b  jz      loc_1800092F1
0x180009261  lea     r8, asc_18008ECE0; "    "
0x180009268  mov     rdx, rsi; unsigned __int16 *
0x18000926b  mov     rcx, rax; this
0x18000926e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009273  mov     r9, [rbx+18h]; unsigned __int16 *
0x180009277  test    r9, r9
0x18000927a  jz      short loc_18000928E
0x18000927c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180009283  mov     rdx, rsi; unsigned __int16 *
0x180009286  mov     rcx, rax; this
0x180009289  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000928e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009292  test    r9, r9
0x180009295  jz      short loc_1800092A9
0x180009297  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000929e  mov     rdx, rsi; unsigned __int16 *
0x1800092a1  mov     rcx, rax; this
0x1800092a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800092a9  mov     rcx, [rbx+28h]
0x1800092ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800092b1  mov     rdx, rsi; unsigned __int16 *
0x1800092b4  test    rcx, rcx
0x1800092b7  jz      short loc_1800092CF
0x1800092b9  mov     [rsp+278h+lpBuffer], rcx
0x1800092be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800092c5  mov     rcx, rax; this
0x1800092c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800092cd  jmp     short loc_1800092F1
0x1800092cf  mov     rcx, rax; this
0x1800092d2  test    r9, r9
0x1800092d5  jz      short loc_1800092E5
0x1800092d7  lea     r8, aHs; "[%hs]\n"
0x1800092de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800092e3  jmp     short loc_1800092F1
0x1800092e5  lea     r8, asc_18008ED58; "\n"
0x1800092ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800092f1  xor     eax, eax
0x1800092f3  mov     rcx, [rsp+278h+var_38]
0x1800092fb  xor     rcx, rsp; StackCookie
0x1800092fe  call    __security_check_cookie
0x180009303  mov     rbx, [rsp+278h+arg_18]
0x18000930b  add     rsp, 250h
0x180009312  pop     r15
0x180009314  pop     r14
0x180009316  pop     rdi
0x180009317  pop     rsi
0x180009318  pop     rbp
0x180009319  retn
```
