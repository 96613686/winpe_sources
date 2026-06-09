# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004214`
- end: `0x1800044ca`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800048f0`
- `0x180005610`
- `0x180005e9c`
- `0x180006270`

## callees

- `0x180002020`
- `0x180002b78`
- `0x180004214`
- `0x1800048a0`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043c7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043c7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004346`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004346`

## pseudocode

```c
// Hidden C++ exception states: #wind=11
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
          v7 = (const char *)&dword_18001A274;
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
0x180004214  mov     [rsp+arg_18], rbx
0x180004219  push    rbp
0x18000421a  push    rsi
0x18000421b  push    rdi
0x18000421c  push    r14
0x18000421e  push    r15
0x180004220  sub     rsp, 250h
0x180004227  mov     rax, cs:__security_cookie
0x18000422e  xor     rax, rsp
0x180004231  mov     [rsp+278h+var_38], rax
0x180004239  mov     rbx, r8
0x18000423c  mov     rsi, rdx
0x18000423f  mov     r14, rcx
0x180004242  xor     r15d, r15d
0x180004245  test    rdx, rdx
0x180004248  jz      loc_1800044A1
0x18000424e  test    rcx, rcx
0x180004251  jz      loc_1800044A1
0x180004257  mov     [rcx], r15w
0x18000425b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004262  test    rax, rax
0x180004265  jz      short loc_180004288
0x180004267  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000426e  jz      short loc_180004288
0x180004270  mov     r8, rdx
0x180004273  mov     rdx, rcx
0x180004276  mov     rcx, rbx
0x180004279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000427e  cmp     [r14], r15w
0x180004282  jnz     loc_1800044A1
0x180004288  mov     ecx, [rbx]
0x18000428a  mov     bpl, 8
0x18000428d  test    ecx, ecx
0x18000428f  jz      short loc_1800042DA
0x180004291  sub     ecx, 1
0x180004294  jz      short loc_1800042C2
0x180004296  sub     ecx, 1
0x180004299  jz      short loc_1800042B2
0x18000429b  cmp     ecx, 1
0x18000429e  jz      short loc_1800042A9
0x1800042a0  lea     rdi, dword_18001A274
0x1800042a7  jmp     short loc_1800042E1
0x1800042a9  lea     rdi, aFailfast; "FailFast"
0x1800042b0  jmp     short loc_1800042E1
0x1800042b2  lea     rax, aLoghr; "LogHr"
0x1800042b9  lea     rdi, aLognt; "LogNt"
0x1800042c0  jmp     short loc_1800042D0
0x1800042c2  lea     rax, aReturnhr; "ReturnHr"
0x1800042c9  lea     rdi, aReturnnt; "ReturnNt"
0x1800042d0  test    [rbx+4], bpl
0x1800042d4  cmovz   rdi, rax
0x1800042d8  jmp     short loc_1800042E1
0x1800042da  lea     rdi, aException; "Exception"
0x1800042e1  xor     edx, edx; Val
0x1800042e3  mov     r8d, 200h; Size
0x1800042e9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800042ee  call    memset_0
0x1800042f3  test    [rbx+4], bpl
0x1800042f7  jz      short loc_18000431C
0x1800042f9  mov     ebp, [rbx+0Ch]
0x1800042fc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004303  test    rax, rax
0x180004306  jz      short loc_18000434C
0x180004308  mov     r8d, 100h
0x18000430e  lea     rdx, [rsp+278h+Buffer]
0x180004313  mov     ecx, ebp
0x180004315  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000431a  jmp     short loc_18000434C
0x18000431c  mov     ebp, [rbx+8]
0x18000431f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004324  mov     [rsp+278h+nSize], 100h; nSize
0x18000432c  lea     rax, [rsp+278h+Buffer]
0x180004331  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004336  mov     r9d, 400h; dwLanguageId
0x18000433c  mov     r8d, ebp; dwMessageId
0x18000433f  xor     edx, edx; lpSource
0x180004341  mov     ecx, 1200h; dwFlags
0x180004346  call    cs:__imp_FormatMessageW
0x18000434c  lea     rsi, [r14+rsi*2]
0x180004350  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004354  mov     rax, [rbx+88h]
0x18000435b  mov     rcx, [rbx+80h]
0x180004362  mov     rdx, rsi; unsigned __int16 *
0x180004365  test    r9, r9
0x180004368  jz      short loc_18000438C
0x18000436a  mov     [rsp+278h+Arguments], rax
0x18000436f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004374  mov     eax, [rbx+40h]
0x180004377  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000437b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004382  mov     rcx, r14; this
0x180004385  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000438a  jmp     short loc_1800043A3
0x18000438c  mov     [rsp+278h+lpBuffer], rax
0x180004391  mov     r9, rcx; unsigned __int16 *
0x180004394  lea     r8, aHsP; "%hs!%p: "
0x18000439b  mov     rcx, r14; this
0x18000439e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043a3  mov     r14, rax
0x1800043a6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800043ad  test    r9, r9
0x1800043b0  jz      short loc_1800043C7
0x1800043b2  lea     r8, aCallerP; "(caller: %p) "
0x1800043b9  mov     rdx, rsi; unsigned __int16 *
0x1800043bc  mov     rcx, rax; this
0x1800043bf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043c4  mov     r14, rax
0x1800043c7  call    cs:__imp_GetCurrentThreadId
0x1800043cd  lea     rcx, [rsp+278h+Buffer]
0x1800043d2  mov     [rsp+278h+var_240], rcx
0x1800043d7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800043db  mov     [rsp+278h+nSize], eax
0x1800043df  mov     eax, [rbx+44h]
0x1800043e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800043e6  mov     r9, rdi; unsigned __int16 *
0x1800043e9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800043f0  mov     rdx, rsi; unsigned __int16 *
0x1800043f3  mov     rcx, r14; this
0x1800043f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043fb  cmp     [rbx+18h], r15
0x1800043ff  jnz     short loc_180004411
0x180004401  cmp     [rbx+48h], r15
0x180004405  jnz     short loc_180004411
0x180004407  cmp     [rbx+30h], r15
0x18000440b  jz      loc_1800044A1
0x180004411  lea     r8, asc_18001A378; "    "
0x180004418  mov     rdx, rsi; unsigned __int16 *
0x18000441b  mov     rcx, rax; this
0x18000441e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004423  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004427  test    r9, r9
0x18000442a  jz      short loc_18000443E
0x18000442c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004433  mov     rdx, rsi; unsigned __int16 *
0x180004436  mov     rcx, rax; this
0x180004439  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000443e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004442  test    r9, r9
0x180004445  jz      short loc_180004459
0x180004447  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000444e  mov     rdx, rsi; unsigned __int16 *
0x180004451  mov     rcx, rax; this
0x180004454  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004459  mov     rcx, [rbx+28h]
0x18000445d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004461  mov     rdx, rsi; unsigned __int16 *
0x180004464  test    rcx, rcx
0x180004467  jz      short loc_18000447F
0x180004469  mov     [rsp+278h+lpBuffer], rcx
0x18000446e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004475  mov     rcx, rax; this
0x180004478  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000447d  jmp     short loc_1800044A1
0x18000447f  mov     rcx, rax; this
0x180004482  test    r9, r9
0x180004485  jz      short loc_180004495
0x180004487  lea     r8, aHs; "[%hs]\n"
0x18000448e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004493  jmp     short loc_1800044A1
0x180004495  lea     r8, asc_18001A3F0; "\n"
0x18000449c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044a1  xor     eax, eax
0x1800044a3  mov     rcx, [rsp+278h+var_38]
0x1800044ab  xor     rcx, rsp; StackCookie
0x1800044ae  call    __security_check_cookie
0x1800044b3  mov     rbx, [rsp+278h+arg_18]
0x1800044bb  add     rsp, 250h
0x1800044c2  pop     r15
0x1800044c4  pop     r14
0x1800044c6  pop     rdi
0x1800044c7  pop     rsi
0x1800044c8  pop     rbp
0x1800044c9  retn
```
