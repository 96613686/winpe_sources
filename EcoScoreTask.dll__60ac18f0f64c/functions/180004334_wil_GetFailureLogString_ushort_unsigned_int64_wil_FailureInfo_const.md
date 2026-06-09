# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004334`
- end: `0x1800045ea`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800028b4`
- `0x180002b24`
- `0x180004e10`

## callees

- `0x180004334`
- `0x180005110`
- `0x180007c62`
- `0x180007c90`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044e7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044e7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004466`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004466`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
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
          v8 = (const char *)&byte_18000A6E0;
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
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
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
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
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
0x180004334  mov     [rsp+arg_18], rbx
0x180004339  push    rbp
0x18000433a  push    rsi
0x18000433b  push    rdi
0x18000433c  push    r14
0x18000433e  push    r15
0x180004340  sub     rsp, 250h
0x180004347  mov     rax, cs:__security_cookie
0x18000434e  xor     rax, rsp
0x180004351  mov     [rsp+278h+var_38], rax
0x180004359  xor     r15d, r15d
0x18000435c  mov     rbx, r8
0x18000435f  mov     rsi, rdx
0x180004362  mov     r14, rcx
0x180004365  test    rdx, rdx
0x180004368  jz      loc_1800045C1
0x18000436e  test    rcx, rcx
0x180004371  jz      loc_1800045C1
0x180004377  mov     rax, cs:g_pfnResultLoggingCallback
0x18000437e  mov     [rcx], r15w
0x180004382  test    rax, rax
0x180004385  jz      short loc_1800043A8
0x180004387  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000438e  jz      short loc_1800043A8
0x180004390  mov     r8, rdx
0x180004393  mov     rdx, rcx
0x180004396  mov     rcx, rbx
0x180004399  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000439e  cmp     [r14], r15w
0x1800043a2  jnz     loc_1800045C1
0x1800043a8  mov     ecx, [rbx]
0x1800043aa  mov     bpl, 8
0x1800043ad  test    ecx, ecx
0x1800043af  jz      short loc_1800043FA
0x1800043b1  sub     ecx, 1
0x1800043b4  jz      short loc_1800043E2
0x1800043b6  sub     ecx, 1
0x1800043b9  jz      short loc_1800043D2
0x1800043bb  cmp     ecx, 1
0x1800043be  jz      short loc_1800043C9
0x1800043c0  lea     rdi, byte_18000A6E0
0x1800043c7  jmp     short loc_180004401
0x1800043c9  lea     rdi, aFailfast; "FailFast"
0x1800043d0  jmp     short loc_180004401
0x1800043d2  lea     rax, aLoghr; "LogHr"
0x1800043d9  lea     rdi, aLognt; "LogNt"
0x1800043e0  jmp     short loc_1800043F0
0x1800043e2  lea     rax, aReturnhr; "ReturnHr"
0x1800043e9  lea     rdi, aReturnnt; "ReturnNt"
0x1800043f0  test    [rbx+4], bpl
0x1800043f4  cmovz   rdi, rax
0x1800043f8  jmp     short loc_180004401
0x1800043fa  lea     rdi, aException; "Exception"
0x180004401  xor     edx, edx; Val
0x180004403  lea     rcx, [rsp+278h+Buffer]; void *
0x180004408  mov     r8d, 200h; Size
0x18000440e  call    memset_0
0x180004413  test    [rbx+4], bpl
0x180004417  jz      short loc_18000443C
0x180004419  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004420  mov     ebp, [rbx+0Ch]
0x180004423  test    rax, rax
0x180004426  jz      short loc_18000446C
0x180004428  mov     r8d, 100h
0x18000442e  lea     rdx, [rsp+278h+Buffer]
0x180004433  mov     ecx, ebp
0x180004435  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000443a  jmp     short loc_18000446C
0x18000443c  mov     ebp, [rbx+8]
0x18000443f  lea     rax, [rsp+278h+Buffer]
0x180004444  mov     [rsp+278h+Arguments], r15; Arguments
0x180004449  mov     r8d, ebp; dwMessageId
0x18000444c  mov     [rsp+278h+nSize], 100h; nSize
0x180004454  mov     r9d, 400h; dwLanguageId
0x18000445a  xor     edx, edx; lpSource
0x18000445c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004461  mov     ecx, 1200h; dwFlags
0x180004466  call    cs:__imp_FormatMessageW
0x18000446c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004470  lea     rsi, [r14+rsi*2]
0x180004474  mov     rax, [rbx+88h]
0x18000447b  mov     rdx, rsi; unsigned __int16 *
0x18000447e  mov     rcx, [rbx+80h]
0x180004485  test    r9, r9
0x180004488  jz      short loc_1800044AC
0x18000448a  mov     [rsp+278h+Arguments], rax
0x18000448f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004496  mov     eax, [rbx+40h]
0x180004499  mov     qword ptr [rsp+278h+nSize], rcx
0x18000449e  mov     rcx, r14; this
0x1800044a1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800044a5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044aa  jmp     short loc_1800044C3
0x1800044ac  mov     r9, rcx; unsigned __int16 *
0x1800044af  mov     [rsp+278h+lpBuffer], rax
0x1800044b4  mov     rcx, r14; this
0x1800044b7  lea     r8, aHsP; "%hs!%p: "
0x1800044be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044c3  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800044ca  mov     r14, rax
0x1800044cd  test    r9, r9
0x1800044d0  jz      short loc_1800044E7
0x1800044d2  lea     r8, aCallerP; "(caller: %p) "
0x1800044d9  mov     rdx, rsi; unsigned __int16 *
0x1800044dc  mov     rcx, rax; this
0x1800044df  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800044e4  mov     r14, rax
0x1800044e7  call    cs:__imp_GetCurrentThreadId
0x1800044ed  lea     rcx, [rsp+278h+Buffer]
0x1800044f2  mov     r9, rdi; unsigned __int16 *
0x1800044f5  mov     [rsp+278h+var_240], rcx
0x1800044fa  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004501  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004505  mov     rdx, rsi; unsigned __int16 *
0x180004508  mov     [rsp+278h+nSize], eax
0x18000450c  mov     rcx, r14; this
0x18000450f  mov     eax, [rbx+44h]
0x180004512  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004516  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000451b  cmp     [rbx+18h], r15
0x18000451f  jnz     short loc_180004531
0x180004521  cmp     [rbx+48h], r15
0x180004525  jnz     short loc_180004531
0x180004527  cmp     [rbx+30h], r15
0x18000452b  jz      loc_1800045C1
0x180004531  lea     r8, asc_18000A7D0; "    "
0x180004538  mov     rdx, rsi; unsigned __int16 *
0x18000453b  mov     rcx, rax; this
0x18000453e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004543  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004547  test    r9, r9
0x18000454a  jz      short loc_18000455E
0x18000454c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004553  mov     rdx, rsi; unsigned __int16 *
0x180004556  mov     rcx, rax; this
0x180004559  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000455e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004562  test    r9, r9
0x180004565  jz      short loc_180004579
0x180004567  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000456e  mov     rdx, rsi; unsigned __int16 *
0x180004571  mov     rcx, rax; this
0x180004574  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004579  mov     rcx, [rbx+28h]
0x18000457d  mov     rdx, rsi; unsigned __int16 *
0x180004580  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004584  test    rcx, rcx
0x180004587  jz      short loc_18000459F
0x180004589  mov     [rsp+278h+lpBuffer], rcx
0x18000458e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004595  mov     rcx, rax; this
0x180004598  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000459d  jmp     short loc_1800045C1
0x18000459f  mov     rcx, rax; this
0x1800045a2  test    r9, r9
0x1800045a5  jz      short loc_1800045B5
0x1800045a7  lea     r8, aHs; "[%hs]\n"
0x1800045ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045b3  jmp     short loc_1800045C1
0x1800045b5  lea     r8, asc_18000A848; "\n"
0x1800045bc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800045c1  xor     eax, eax
0x1800045c3  mov     rcx, [rsp+278h+var_38]
0x1800045cb  xor     rcx, rsp; StackCookie
0x1800045ce  call    __security_check_cookie
0x1800045d3  mov     rbx, [rsp+278h+arg_18]
0x1800045db  add     rsp, 250h
0x1800045e2  pop     r15
0x1800045e4  pop     r14
0x1800045e6  pop     rdi
0x1800045e7  pop     rsi
0x1800045e8  pop     rbp
0x1800045e9  retn
```
