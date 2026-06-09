# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18004871c`
- end: `0x1800489d2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180047568`
- `0x180048c40`
- `0x180048f90`
- `0x18004a2d0`

## callees

- `0x180043c30`
- `0x1800446fc`
- `0x18004871c`
- `0x180048f40`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800488cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800488cf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004884e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18004884e`

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
          v7 = (const char *)&word_18007ACCE;
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
0x18004871c  mov     [rsp+arg_18], rbx
0x180048721  push    rbp
0x180048722  push    rsi
0x180048723  push    rdi
0x180048724  push    r14
0x180048726  push    r15
0x180048728  sub     rsp, 250h
0x18004872f  mov     rax, cs:__security_cookie
0x180048736  xor     rax, rsp
0x180048739  mov     [rsp+278h+var_38], rax
0x180048741  mov     rbx, r8
0x180048744  mov     rsi, rdx
0x180048747  mov     r14, rcx
0x18004874a  xor     r15d, r15d
0x18004874d  test    rdx, rdx
0x180048750  jz      loc_1800489A9
0x180048756  test    rcx, rcx
0x180048759  jz      loc_1800489A9
0x18004875f  mov     [rcx], r15w
0x180048763  mov     rax, cs:g_pfnResultLoggingCallback
0x18004876a  test    rax, rax
0x18004876d  jz      short loc_180048790
0x18004876f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180048776  jz      short loc_180048790
0x180048778  mov     r8, rdx
0x18004877b  mov     rdx, rcx
0x18004877e  mov     rcx, rbx
0x180048781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048786  cmp     [r14], r15w
0x18004878a  jnz     loc_1800489A9
0x180048790  mov     ecx, [rbx]
0x180048792  mov     bpl, 8
0x180048795  test    ecx, ecx
0x180048797  jz      short loc_1800487E2
0x180048799  sub     ecx, 1
0x18004879c  jz      short loc_1800487CA
0x18004879e  sub     ecx, 1
0x1800487a1  jz      short loc_1800487BA
0x1800487a3  cmp     ecx, 1
0x1800487a6  jz      short loc_1800487B1
0x1800487a8  lea     rdi, word_18007ACCE
0x1800487af  jmp     short loc_1800487E9
0x1800487b1  lea     rdi, aFailfast; "FailFast"
0x1800487b8  jmp     short loc_1800487E9
0x1800487ba  lea     rax, aLoghr; "LogHr"
0x1800487c1  lea     rdi, aLognt; "LogNt"
0x1800487c8  jmp     short loc_1800487D8
0x1800487ca  lea     rax, aReturnhr; "ReturnHr"
0x1800487d1  lea     rdi, aReturnnt; "ReturnNt"
0x1800487d8  test    [rbx+4], bpl
0x1800487dc  cmovz   rdi, rax
0x1800487e0  jmp     short loc_1800487E9
0x1800487e2  lea     rdi, aException; "Exception"
0x1800487e9  xor     edx, edx; Val
0x1800487eb  mov     r8d, 200h; Size
0x1800487f1  lea     rcx, [rsp+278h+Buffer]; void *
0x1800487f6  call    memset_0
0x1800487fb  test    [rbx+4], bpl
0x1800487ff  jz      short loc_180048824
0x180048801  mov     ebp, [rbx+0Ch]
0x180048804  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18004880b  test    rax, rax
0x18004880e  jz      short loc_180048854
0x180048810  mov     r8d, 100h
0x180048816  lea     rdx, [rsp+278h+Buffer]
0x18004881b  mov     ecx, ebp
0x18004881d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048822  jmp     short loc_180048854
0x180048824  mov     ebp, [rbx+8]
0x180048827  mov     [rsp+278h+Arguments], r15; Arguments
0x18004882c  mov     [rsp+278h+nSize], 100h; nSize
0x180048834  lea     rax, [rsp+278h+Buffer]
0x180048839  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18004883e  mov     r9d, 400h; dwLanguageId
0x180048844  mov     r8d, ebp; dwMessageId
0x180048847  xor     edx, edx; lpSource
0x180048849  mov     ecx, 1200h; dwFlags
0x18004884e  call    cs:__imp_FormatMessageW
0x180048854  lea     rsi, [r14+rsi*2]
0x180048858  mov     r9, [rbx+38h]; unsigned __int16 *
0x18004885c  mov     rax, [rbx+88h]
0x180048863  mov     rcx, [rbx+80h]
0x18004886a  mov     rdx, rsi; unsigned __int16 *
0x18004886d  test    r9, r9
0x180048870  jz      short loc_180048894
0x180048872  mov     [rsp+278h+Arguments], rax
0x180048877  mov     qword ptr [rsp+278h+nSize], rcx
0x18004887c  mov     eax, [rbx+40h]
0x18004887f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180048883  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18004888a  mov     rcx, r14; this
0x18004888d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180048892  jmp     short loc_1800488AB
0x180048894  mov     [rsp+278h+lpBuffer], rax
0x180048899  mov     r9, rcx; unsigned __int16 *
0x18004889c  lea     r8, aHsP; "%hs!%p: "
0x1800488a3  mov     rcx, r14; this
0x1800488a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800488ab  mov     r14, rax
0x1800488ae  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800488b5  test    r9, r9
0x1800488b8  jz      short loc_1800488CF
0x1800488ba  lea     r8, aCallerP; "(caller: %p) "
0x1800488c1  mov     rdx, rsi; unsigned __int16 *
0x1800488c4  mov     rcx, rax; this
0x1800488c7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800488cc  mov     r14, rax
0x1800488cf  call    cs:__imp_GetCurrentThreadId
0x1800488d5  lea     rcx, [rsp+278h+Buffer]
0x1800488da  mov     [rsp+278h+var_240], rcx
0x1800488df  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800488e3  mov     [rsp+278h+nSize], eax
0x1800488e7  mov     eax, [rbx+44h]
0x1800488ea  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800488ee  mov     r9, rdi; unsigned __int16 *
0x1800488f1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800488f8  mov     rdx, rsi; unsigned __int16 *
0x1800488fb  mov     rcx, r14; this
0x1800488fe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180048903  cmp     [rbx+18h], r15
0x180048907  jnz     short loc_180048919
0x180048909  cmp     [rbx+48h], r15
0x18004890d  jnz     short loc_180048919
0x18004890f  cmp     [rbx+30h], r15
0x180048913  jz      loc_1800489A9
0x180048919  lea     r8, asc_18007BB28; "    "
0x180048920  mov     rdx, rsi; unsigned __int16 *
0x180048923  mov     rcx, rax; this
0x180048926  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004892b  mov     r9, [rbx+18h]; unsigned __int16 *
0x18004892f  test    r9, r9
0x180048932  jz      short loc_180048946
0x180048934  lea     r8, aMsgWs; "Msg:[%ws] "
0x18004893b  mov     rdx, rsi; unsigned __int16 *
0x18004893e  mov     rcx, rax; this
0x180048941  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180048946  mov     r9, [rbx+48h]; unsigned __int16 *
0x18004894a  test    r9, r9
0x18004894d  jz      short loc_180048961
0x18004894f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180048956  mov     rdx, rsi; unsigned __int16 *
0x180048959  mov     rcx, rax; this
0x18004895c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180048961  mov     rcx, [rbx+28h]
0x180048965  mov     r9, [rbx+30h]; unsigned __int16 *
0x180048969  mov     rdx, rsi; unsigned __int16 *
0x18004896c  test    rcx, rcx
0x18004896f  jz      short loc_180048987
0x180048971  mov     [rsp+278h+lpBuffer], rcx
0x180048976  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18004897d  mov     rcx, rax; this
0x180048980  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180048985  jmp     short loc_1800489A9
0x180048987  mov     rcx, rax; this
0x18004898a  test    r9, r9
0x18004898d  jz      short loc_18004899D
0x18004898f  lea     r8, aHs; "[%hs]\n"
0x180048996  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18004899b  jmp     short loc_1800489A9
0x18004899d  lea     r8, asc_18007BBA0; "\n"
0x1800489a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800489a9  xor     eax, eax
0x1800489ab  mov     rcx, [rsp+278h+var_38]
0x1800489b3  xor     rcx, rsp; StackCookie
0x1800489b6  call    __security_check_cookie
0x1800489bb  mov     rbx, [rsp+278h+arg_18]
0x1800489c3  add     rsp, 250h
0x1800489ca  pop     r15
0x1800489cc  pop     r14
0x1800489ce  pop     rdi
0x1800489cf  pop     rsi
0x1800489d0  pop     rbp
0x1800489d1  retn
```
