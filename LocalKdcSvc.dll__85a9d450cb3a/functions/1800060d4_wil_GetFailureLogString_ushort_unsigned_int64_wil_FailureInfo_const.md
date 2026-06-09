# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800060d4`
- end: `0x18000638a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(STRSAFE_LPWSTR pszDest, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800045c0`
- `0x180006cec`
- `0x180009bd0`

## callees

- `0x180002ad0`
- `0x180003908`
- `0x1800060d4`
- `0x180006fec`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006287`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006287`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006206`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006206`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall wil::GetFailureLogString(
        STRSAFE_LPWSTR pszDest,
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
  wchar_t *v14; // rax
  wchar_t *v15; // r14
  const unsigned __int16 *v16; // r9
  wchar_t *v17; // rax
  const unsigned __int16 *v18; // r9
  wchar_t *v19; // rax
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
  if ( !pszDest )
    return 0;
  *pszDest = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, pszDest, a2);
      if ( *pszDest )
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
          v7 = (const char *)&dword_1800A120C;
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
  v10 = &pszDest[(_QWORD)a2];
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const unsigned __int16 **)(a3 + 128);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, v13, v12);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(pszDest, v10, L"%hs!%p: ", v13, v12);
  }
  v15 = v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = wil::details::LogStringPrintf(v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = wil::details::LogStringPrintf(
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
      v19 = wil::details::LogStringPrintf(v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf(v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf(v19, v10, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf(v19, v10, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x1800060d4  mov     [rsp+arg_18], rbx
0x1800060d9  push    rbp
0x1800060da  push    rsi
0x1800060db  push    rdi
0x1800060dc  push    r14
0x1800060de  push    r15
0x1800060e0  sub     rsp, 250h
0x1800060e7  mov     rax, cs:__security_cookie
0x1800060ee  xor     rax, rsp
0x1800060f1  mov     [rsp+278h+var_38], rax
0x1800060f9  mov     rbx, r8
0x1800060fc  mov     rsi, rdx
0x1800060ff  mov     r14, rcx
0x180006102  xor     r15d, r15d
0x180006105  test    rdx, rdx
0x180006108  jz      loc_180006361
0x18000610e  test    rcx, rcx
0x180006111  jz      loc_180006361
0x180006117  mov     [rcx], r15w
0x18000611b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006122  test    rax, rax
0x180006125  jz      short loc_180006148
0x180006127  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000612e  jz      short loc_180006148
0x180006130  mov     r8, rdx
0x180006133  mov     rdx, rcx
0x180006136  mov     rcx, rbx
0x180006139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000613e  cmp     [r14], r15w
0x180006142  jnz     loc_180006361
0x180006148  mov     ecx, [rbx]
0x18000614a  mov     bpl, 8
0x18000614d  test    ecx, ecx
0x18000614f  jz      short loc_18000619A
0x180006151  sub     ecx, 1
0x180006154  jz      short loc_180006182
0x180006156  sub     ecx, 1
0x180006159  jz      short loc_180006172
0x18000615b  cmp     ecx, 1
0x18000615e  jz      short loc_180006169
0x180006160  lea     rdi, dword_1800A120C
0x180006167  jmp     short loc_1800061A1
0x180006169  lea     rdi, aFailfast; "FailFast"
0x180006170  jmp     short loc_1800061A1
0x180006172  lea     rax, aLoghr; "LogHr"
0x180006179  lea     rdi, aLognt; "LogNt"
0x180006180  jmp     short loc_180006190
0x180006182  lea     rax, aReturnhr; "ReturnHr"
0x180006189  lea     rdi, aReturnnt; "ReturnNt"
0x180006190  test    [rbx+4], bpl
0x180006194  cmovz   rdi, rax
0x180006198  jmp     short loc_1800061A1
0x18000619a  lea     rdi, aException; "Exception"
0x1800061a1  xor     edx, edx; Val
0x1800061a3  mov     r8d, 200h; Size
0x1800061a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800061ae  call    memset_0
0x1800061b3  test    [rbx+4], bpl
0x1800061b7  jz      short loc_1800061DC
0x1800061b9  mov     ebp, [rbx+0Ch]
0x1800061bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800061c3  test    rax, rax
0x1800061c6  jz      short loc_18000620C
0x1800061c8  mov     r8d, 100h
0x1800061ce  lea     rdx, [rsp+278h+Buffer]
0x1800061d3  mov     ecx, ebp
0x1800061d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061da  jmp     short loc_18000620C
0x1800061dc  mov     ebp, [rbx+8]
0x1800061df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800061e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800061ec  lea     rax, [rsp+278h+Buffer]
0x1800061f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800061f6  mov     r9d, 400h; dwLanguageId
0x1800061fc  mov     r8d, ebp; dwMessageId
0x1800061ff  xor     edx, edx; lpSource
0x180006201  mov     ecx, 1200h; dwFlags
0x180006206  call    cs:__imp_FormatMessageW
0x18000620c  lea     rsi, [r14+rsi*2]
0x180006210  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006214  mov     rax, [rbx+88h]
0x18000621b  mov     rcx, [rbx+80h]
0x180006222  mov     rdx, rsi; unsigned __int16 *
0x180006225  test    r9, r9
0x180006228  jz      short loc_18000624C
0x18000622a  mov     [rsp+278h+Arguments], rax
0x18000622f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006234  mov     eax, [rbx+40h]
0x180006237  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000623b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006242  mov     rcx, r14; pszDest
0x180006245  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000624a  jmp     short loc_180006263
0x18000624c  mov     [rsp+278h+lpBuffer], rax
0x180006251  mov     r9, rcx; unsigned __int16 *
0x180006254  lea     r8, aHsP; "%hs!%p: "
0x18000625b  mov     rcx, r14; pszDest
0x18000625e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006263  mov     r14, rax
0x180006266  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000626d  test    r9, r9
0x180006270  jz      short loc_180006287
0x180006272  lea     r8, aCallerP; "(caller: %p) "
0x180006279  mov     rdx, rsi; unsigned __int16 *
0x18000627c  mov     rcx, rax; pszDest
0x18000627f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006284  mov     r14, rax
0x180006287  call    cs:__imp_GetCurrentThreadId
0x18000628d  lea     rcx, [rsp+278h+Buffer]
0x180006292  mov     [rsp+278h+var_240], rcx
0x180006297  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000629b  mov     [rsp+278h+nSize], eax
0x18000629f  mov     eax, [rbx+44h]
0x1800062a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800062a6  mov     r9, rdi; unsigned __int16 *
0x1800062a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800062b0  mov     rdx, rsi; unsigned __int16 *
0x1800062b3  mov     rcx, r14; pszDest
0x1800062b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062bb  cmp     [rbx+18h], r15
0x1800062bf  jnz     short loc_1800062D1
0x1800062c1  cmp     [rbx+48h], r15
0x1800062c5  jnz     short loc_1800062D1
0x1800062c7  cmp     [rbx+30h], r15
0x1800062cb  jz      loc_180006361
0x1800062d1  lea     r8, asc_1800A1310; "    "
0x1800062d8  mov     rdx, rsi; unsigned __int16 *
0x1800062db  mov     rcx, rax; pszDest
0x1800062de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800062e7  test    r9, r9
0x1800062ea  jz      short loc_1800062FE
0x1800062ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800062f3  mov     rdx, rsi; unsigned __int16 *
0x1800062f6  mov     rcx, rax; pszDest
0x1800062f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800062fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006302  test    r9, r9
0x180006305  jz      short loc_180006319
0x180006307  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000630e  mov     rdx, rsi; unsigned __int16 *
0x180006311  mov     rcx, rax; pszDest
0x180006314  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006319  mov     rcx, [rbx+28h]
0x18000631d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006321  mov     rdx, rsi; unsigned __int16 *
0x180006324  test    rcx, rcx
0x180006327  jz      short loc_18000633F
0x180006329  mov     [rsp+278h+lpBuffer], rcx
0x18000632e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006335  mov     rcx, rax; pszDest
0x180006338  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000633d  jmp     short loc_180006361
0x18000633f  mov     rcx, rax; pszDest
0x180006342  test    r9, r9
0x180006345  jz      short loc_180006355
0x180006347  lea     r8, aHs; "[%hs]\n"
0x18000634e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006353  jmp     short loc_180006361
0x180006355  lea     r8, asc_1800A1388; "\n"
0x18000635c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006361  xor     eax, eax
0x180006363  mov     rcx, [rsp+278h+var_38]
0x18000636b  xor     rcx, rsp; StackCookie
0x18000636e  call    __security_check_cookie
0x180006373  mov     rbx, [rsp+278h+arg_18]
0x18000637b  add     rsp, 250h
0x180006382  pop     r15
0x180006384  pop     r14
0x180006386  pop     rdi
0x180006387  pop     rsi
0x180006388  pop     rbp
0x180006389  retn
```
