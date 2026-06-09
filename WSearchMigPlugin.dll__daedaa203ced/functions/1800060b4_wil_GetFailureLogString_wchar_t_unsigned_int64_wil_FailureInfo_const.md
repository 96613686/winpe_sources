# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800060b4`
- end: `0x180006375`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b9c`
- `0x180003e10`
- `0x180006b1c`
- `0x18000a140`

## callees

- `0x1800026f0`
- `0x18000329c`
- `0x1800060b4`
- `0x180006e24`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006272`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006272`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800061f1`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800061f1`

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
          v7 = (const char *)&byte_18001AA01;
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
0x1800060b4  mov     rax, rsp
0x1800060b7  push    rbp
0x1800060b8  push    rsi
0x1800060b9  push    rdi
0x1800060ba  push    r14
0x1800060bc  push    r15
0x1800060be  sub     rsp, 260h
0x1800060c5  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x1800060ce  mov     [rax+20h], rbx
0x1800060d2  mov     rax, cs:__security_cookie
0x1800060d9  xor     rax, rsp
0x1800060dc  mov     [rsp+288h+var_38], rax
0x1800060e4  mov     rbx, r8
0x1800060e7  mov     rsi, rdx
0x1800060ea  mov     r14, rcx
0x1800060ed  xor     r15d, r15d
0x1800060f0  test    rdx, rdx
0x1800060f3  jz      loc_18000634C
0x1800060f9  test    rcx, rcx
0x1800060fc  jz      loc_18000634C
0x180006102  mov     [rcx], r15w
0x180006106  mov     rax, cs:g_pfnResultLoggingCallback
0x18000610d  test    rax, rax
0x180006110  jz      short loc_180006133
0x180006112  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006119  jz      short loc_180006133
0x18000611b  mov     r8, rdx
0x18000611e  mov     rdx, rcx
0x180006121  mov     rcx, rbx
0x180006124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006129  cmp     [r14], r15w
0x18000612d  jnz     loc_18000634C
0x180006133  mov     ecx, [rbx]
0x180006135  mov     bpl, 8
0x180006138  test    ecx, ecx
0x18000613a  jz      short loc_180006185
0x18000613c  sub     ecx, 1
0x18000613f  jz      short loc_18000616D
0x180006141  sub     ecx, 1
0x180006144  jz      short loc_18000615D
0x180006146  cmp     ecx, 1
0x180006149  jz      short loc_180006154
0x18000614b  lea     rdi, byte_18001AA01
0x180006152  jmp     short loc_18000618C
0x180006154  lea     rdi, aFailfast; "FailFast"
0x18000615b  jmp     short loc_18000618C
0x18000615d  lea     rax, aLoghr; "LogHr"
0x180006164  lea     rdi, aLognt; "LogNt"
0x18000616b  jmp     short loc_18000617B
0x18000616d  lea     rax, aReturnhr; "ReturnHr"
0x180006174  lea     rdi, aReturnnt; "ReturnNt"
0x18000617b  test    [rbx+4], bpl
0x18000617f  cmovz   rdi, rax
0x180006183  jmp     short loc_18000618C
0x180006185  lea     rdi, aException; "Exception"
0x18000618c  xor     edx, edx; Val
0x18000618e  mov     r8d, 200h; Size
0x180006194  lea     rcx, [rsp+288h+Buffer]; void *
0x180006199  call    memset_0
0x18000619e  test    [rbx+4], bpl
0x1800061a2  jz      short loc_1800061C7
0x1800061a4  mov     ebp, [rbx+0Ch]
0x1800061a7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800061ae  test    rax, rax
0x1800061b1  jz      short loc_1800061F7
0x1800061b3  mov     r8d, 100h
0x1800061b9  lea     rdx, [rsp+288h+Buffer]
0x1800061be  mov     ecx, ebp
0x1800061c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061c5  jmp     short loc_1800061F7
0x1800061c7  mov     ebp, [rbx+8]
0x1800061ca  mov     [rsp+288h+Arguments], r15; Arguments
0x1800061cf  mov     [rsp+288h+nSize], 100h; nSize
0x1800061d7  lea     rax, [rsp+288h+Buffer]
0x1800061dc  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x1800061e1  mov     r9d, 400h; dwLanguageId
0x1800061e7  mov     r8d, ebp; dwMessageId
0x1800061ea  xor     edx, edx; lpSource
0x1800061ec  mov     ecx, 1200h; dwFlags
0x1800061f1  call    cs:__imp_FormatMessageW
0x1800061f7  lea     rsi, [r14+rsi*2]
0x1800061fb  mov     r9, [rbx+38h]; wchar_t *
0x1800061ff  mov     rax, [rbx+88h]
0x180006206  mov     rcx, [rbx+80h]
0x18000620d  mov     rdx, rsi; wchar_t *
0x180006210  test    r9, r9
0x180006213  jz      short loc_180006237
0x180006215  mov     [rsp+288h+Arguments], rax
0x18000621a  mov     qword ptr [rsp+288h+nSize], rcx
0x18000621f  mov     eax, [rbx+40h]
0x180006222  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180006226  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000622d  mov     rcx, r14; this
0x180006230  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006235  jmp     short loc_18000624E
0x180006237  mov     [rsp+288h+lpBuffer], rax
0x18000623c  mov     r9, rcx; wchar_t *
0x18000623f  lea     r8, aHsP; "%hs!%p: "
0x180006246  mov     rcx, r14; this
0x180006249  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000624e  mov     r14, rax
0x180006251  mov     r9, [rbx+90h]; wchar_t *
0x180006258  test    r9, r9
0x18000625b  jz      short loc_180006272
0x18000625d  lea     r8, aCallerP; "(caller: %p) "
0x180006264  mov     rdx, rsi; wchar_t *
0x180006267  mov     rcx, rax; this
0x18000626a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000626f  mov     r14, rax
0x180006272  call    cs:__imp_GetCurrentThreadId
0x180006278  lea     rcx, [rsp+288h+Buffer]
0x18000627d  mov     [rsp+288h+var_250], rcx
0x180006282  mov     dword ptr [rsp+288h+Arguments], ebp
0x180006286  mov     [rsp+288h+nSize], eax
0x18000628a  mov     eax, [rbx+44h]
0x18000628d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180006291  mov     r9, rdi; wchar_t *
0x180006294  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000629b  mov     rdx, rsi; wchar_t *
0x18000629e  mov     rcx, r14; this
0x1800062a1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800062a6  cmp     [rbx+18h], r15
0x1800062aa  jnz     short loc_1800062BC
0x1800062ac  cmp     [rbx+48h], r15
0x1800062b0  jnz     short loc_1800062BC
0x1800062b2  cmp     [rbx+30h], r15
0x1800062b6  jz      loc_18000634C
0x1800062bc  lea     r8, asc_18001AB08; "    "
0x1800062c3  mov     rdx, rsi; wchar_t *
0x1800062c6  mov     rcx, rax; this
0x1800062c9  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800062ce  mov     r9, [rbx+18h]; wchar_t *
0x1800062d2  test    r9, r9
0x1800062d5  jz      short loc_1800062E9
0x1800062d7  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800062de  mov     rdx, rsi; wchar_t *
0x1800062e1  mov     rcx, rax; this
0x1800062e4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800062e9  mov     r9, [rbx+48h]; wchar_t *
0x1800062ed  test    r9, r9
0x1800062f0  jz      short loc_180006304
0x1800062f2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800062f9  mov     rdx, rsi; wchar_t *
0x1800062fc  mov     rcx, rax; this
0x1800062ff  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006304  mov     rcx, [rbx+28h]
0x180006308  mov     r9, [rbx+30h]; wchar_t *
0x18000630c  mov     rdx, rsi; wchar_t *
0x18000630f  test    rcx, rcx
0x180006312  jz      short loc_18000632A
0x180006314  mov     [rsp+288h+lpBuffer], rcx
0x180006319  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180006320  mov     rcx, rax; this
0x180006323  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180006328  jmp     short loc_18000634C
0x18000632a  mov     rcx, rax; this
0x18000632d  test    r9, r9
0x180006330  jz      short loc_180006340
0x180006332  lea     r8, aHs; "[%hs]\n"
0x180006339  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000633e  jmp     short loc_18000634C
0x180006340  lea     r8, asc_18001AB80; "\n"
0x180006347  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000634c  xor     eax, eax
0x18000634e  mov     rcx, [rsp+288h+var_38]
0x180006356  xor     rcx, rsp; StackCookie
0x180006359  call    __security_check_cookie
0x18000635e  mov     rbx, [rsp+288h+arg_18]
0x180006366  add     rsp, 260h
0x18000636d  pop     r15
0x18000636f  pop     r14
0x180006371  pop     rdi
0x180006372  pop     rsi
0x180006373  pop     rbp
0x180006374  retn
```
