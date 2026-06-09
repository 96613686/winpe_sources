# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180034454`
- end: `0x18003470a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001ff64`
- `0x180034f18`
- `0x180036cc0`

## callees

- `0x180031960`
- `0x1800327f8`
- `0x180034454`
- `0x180034b9c`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034607`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180034607`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180034586`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180034586`

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
          v7 = (const char *)&qword_180053CA0;
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
0x180034454  mov     [rsp+arg_18], rbx
0x180034459  push    rbp
0x18003445a  push    rsi
0x18003445b  push    rdi
0x18003445c  push    r14
0x18003445e  push    r15
0x180034460  sub     rsp, 250h
0x180034467  mov     rax, cs:__security_cookie
0x18003446e  xor     rax, rsp
0x180034471  mov     [rsp+278h+var_38], rax
0x180034479  mov     rbx, r8
0x18003447c  mov     rsi, rdx
0x18003447f  mov     r14, rcx
0x180034482  xor     r15d, r15d
0x180034485  test    rdx, rdx
0x180034488  jz      loc_1800346E1
0x18003448e  test    rcx, rcx
0x180034491  jz      loc_1800346E1
0x180034497  mov     [rcx], r15w
0x18003449b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800344a2  test    rax, rax
0x1800344a5  jz      short loc_1800344C8
0x1800344a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800344ae  jz      short loc_1800344C8
0x1800344b0  mov     r8, rdx
0x1800344b3  mov     rdx, rcx
0x1800344b6  mov     rcx, rbx
0x1800344b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800344be  cmp     [r14], r15w
0x1800344c2  jnz     loc_1800346E1
0x1800344c8  mov     ecx, [rbx]
0x1800344ca  mov     bpl, 8
0x1800344cd  test    ecx, ecx
0x1800344cf  jz      short loc_18003451A
0x1800344d1  sub     ecx, 1
0x1800344d4  jz      short loc_180034502
0x1800344d6  sub     ecx, 1
0x1800344d9  jz      short loc_1800344F2
0x1800344db  cmp     ecx, 1
0x1800344de  jz      short loc_1800344E9
0x1800344e0  lea     rdi, qword_180053CA0
0x1800344e7  jmp     short loc_180034521
0x1800344e9  lea     rdi, aFailfast; "FailFast"
0x1800344f0  jmp     short loc_180034521
0x1800344f2  lea     rax, aLoghr; "LogHr"
0x1800344f9  lea     rdi, aLognt; "LogNt"
0x180034500  jmp     short loc_180034510
0x180034502  lea     rax, aReturnhr; "ReturnHr"
0x180034509  lea     rdi, aReturnnt; "ReturnNt"
0x180034510  test    [rbx+4], bpl
0x180034514  cmovz   rdi, rax
0x180034518  jmp     short loc_180034521
0x18003451a  lea     rdi, aException; "Exception"
0x180034521  xor     edx, edx; Val
0x180034523  mov     r8d, 200h; Size
0x180034529  lea     rcx, [rsp+278h+Buffer]; void *
0x18003452e  call    memset_0
0x180034533  test    [rbx+4], bpl
0x180034537  jz      short loc_18003455C
0x180034539  mov     ebp, [rbx+0Ch]
0x18003453c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180034543  test    rax, rax
0x180034546  jz      short loc_18003458C
0x180034548  mov     r8d, 100h
0x18003454e  lea     rdx, [rsp+278h+Buffer]
0x180034553  mov     ecx, ebp
0x180034555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003455a  jmp     short loc_18003458C
0x18003455c  mov     ebp, [rbx+8]
0x18003455f  mov     [rsp+278h+Arguments], r15; Arguments
0x180034564  mov     [rsp+278h+nSize], 100h; nSize
0x18003456c  lea     rax, [rsp+278h+Buffer]
0x180034571  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180034576  mov     r9d, 400h; dwLanguageId
0x18003457c  mov     r8d, ebp; dwMessageId
0x18003457f  xor     edx, edx; lpSource
0x180034581  mov     ecx, 1200h; dwFlags
0x180034586  call    cs:__imp_FormatMessageW
0x18003458c  lea     rsi, [r14+rsi*2]
0x180034590  mov     r9, [rbx+38h]; unsigned __int16 *
0x180034594  mov     rax, [rbx+88h]
0x18003459b  mov     rcx, [rbx+80h]
0x1800345a2  mov     rdx, rsi; unsigned __int16 *
0x1800345a5  test    r9, r9
0x1800345a8  jz      short loc_1800345CC
0x1800345aa  mov     [rsp+278h+Arguments], rax
0x1800345af  mov     qword ptr [rsp+278h+nSize], rcx
0x1800345b4  mov     eax, [rbx+40h]
0x1800345b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800345bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800345c2  mov     rcx, r14; this
0x1800345c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800345ca  jmp     short loc_1800345E3
0x1800345cc  mov     [rsp+278h+lpBuffer], rax
0x1800345d1  mov     r9, rcx; unsigned __int16 *
0x1800345d4  lea     r8, aHsP; "%hs!%p: "
0x1800345db  mov     rcx, r14; this
0x1800345de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800345e3  mov     r14, rax
0x1800345e6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800345ed  test    r9, r9
0x1800345f0  jz      short loc_180034607
0x1800345f2  lea     r8, aCallerP; "(caller: %p) "
0x1800345f9  mov     rdx, rsi; unsigned __int16 *
0x1800345fc  mov     rcx, rax; this
0x1800345ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034604  mov     r14, rax
0x180034607  call    cs:__imp_GetCurrentThreadId
0x18003460d  lea     rcx, [rsp+278h+Buffer]
0x180034612  mov     [rsp+278h+var_240], rcx
0x180034617  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003461b  mov     [rsp+278h+nSize], eax
0x18003461f  mov     eax, [rbx+44h]
0x180034622  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180034626  mov     r9, rdi; unsigned __int16 *
0x180034629  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180034630  mov     rdx, rsi; unsigned __int16 *
0x180034633  mov     rcx, r14; this
0x180034636  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003463b  cmp     [rbx+18h], r15
0x18003463f  jnz     short loc_180034651
0x180034641  cmp     [rbx+48h], r15
0x180034645  jnz     short loc_180034651
0x180034647  cmp     [rbx+30h], r15
0x18003464b  jz      loc_1800346E1
0x180034651  lea     r8, asc_180054898; "    "
0x180034658  mov     rdx, rsi; unsigned __int16 *
0x18003465b  mov     rcx, rax; this
0x18003465e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034663  mov     r9, [rbx+18h]; unsigned __int16 *
0x180034667  test    r9, r9
0x18003466a  jz      short loc_18003467E
0x18003466c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180034673  mov     rdx, rsi; unsigned __int16 *
0x180034676  mov     rcx, rax; this
0x180034679  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003467e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180034682  test    r9, r9
0x180034685  jz      short loc_180034699
0x180034687  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003468e  mov     rdx, rsi; unsigned __int16 *
0x180034691  mov     rcx, rax; this
0x180034694  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180034699  mov     rcx, [rbx+28h]
0x18003469d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800346a1  mov     rdx, rsi; unsigned __int16 *
0x1800346a4  test    rcx, rcx
0x1800346a7  jz      short loc_1800346BF
0x1800346a9  mov     [rsp+278h+lpBuffer], rcx
0x1800346ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800346b5  mov     rcx, rax; this
0x1800346b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800346bd  jmp     short loc_1800346E1
0x1800346bf  mov     rcx, rax; this
0x1800346c2  test    r9, r9
0x1800346c5  jz      short loc_1800346D5
0x1800346c7  lea     r8, aHs; "[%hs]\n"
0x1800346ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800346d3  jmp     short loc_1800346E1
0x1800346d5  lea     r8, asc_180054910; "\n"
0x1800346dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800346e1  xor     eax, eax
0x1800346e3  mov     rcx, [rsp+278h+var_38]
0x1800346eb  xor     rcx, rsp; StackCookie
0x1800346ee  call    __security_check_cookie
0x1800346f3  mov     rbx, [rsp+278h+arg_18]
0x1800346fb  add     rsp, 250h
0x180034702  pop     r15
0x180034704  pop     r14
0x180034706  pop     rdi
0x180034707  pop     rsi
0x180034708  pop     rbp
0x180034709  retn
```
