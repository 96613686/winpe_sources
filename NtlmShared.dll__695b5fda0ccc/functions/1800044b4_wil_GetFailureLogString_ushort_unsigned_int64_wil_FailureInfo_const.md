# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800044b4`
- end: `0x18000476a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180002394`
- `0x1800025fc`
- `0x180004ef8`

## callees

- `0x1800044b4`
- `0x1800051f8`
- `0x18000c4a4`
- `0x18000c560`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004667`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004667`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800045e6`

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
          v8 = (const char *)&qword_18000E7A8;
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
0x1800044b4  mov     [rsp+arg_18], rbx
0x1800044b9  push    rbp
0x1800044ba  push    rsi
0x1800044bb  push    rdi
0x1800044bc  push    r14
0x1800044be  push    r15
0x1800044c0  sub     rsp, 250h
0x1800044c7  mov     rax, cs:__security_cookie
0x1800044ce  xor     rax, rsp
0x1800044d1  mov     [rsp+278h+var_38], rax
0x1800044d9  xor     r15d, r15d
0x1800044dc  mov     rbx, r8
0x1800044df  mov     rsi, rdx
0x1800044e2  mov     r14, rcx
0x1800044e5  test    rdx, rdx
0x1800044e8  jz      loc_180004741
0x1800044ee  test    rcx, rcx
0x1800044f1  jz      loc_180004741
0x1800044f7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044fe  mov     [rcx], r15w
0x180004502  test    rax, rax
0x180004505  jz      short loc_180004528
0x180004507  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000450e  jz      short loc_180004528
0x180004510  mov     r8, rdx
0x180004513  mov     rdx, rcx
0x180004516  mov     rcx, rbx
0x180004519  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000451e  cmp     [r14], r15w
0x180004522  jnz     loc_180004741
0x180004528  mov     ecx, [rbx]
0x18000452a  mov     bpl, 8
0x18000452d  test    ecx, ecx
0x18000452f  jz      short loc_18000457A
0x180004531  sub     ecx, 1
0x180004534  jz      short loc_180004562
0x180004536  sub     ecx, 1
0x180004539  jz      short loc_180004552
0x18000453b  cmp     ecx, 1
0x18000453e  jz      short loc_180004549
0x180004540  lea     rdi, qword_18000E7A8
0x180004547  jmp     short loc_180004581
0x180004549  lea     rdi, aFailfast; "FailFast"
0x180004550  jmp     short loc_180004581
0x180004552  lea     rax, aLoghr; "LogHr"
0x180004559  lea     rdi, aLognt; "LogNt"
0x180004560  jmp     short loc_180004570
0x180004562  lea     rax, aReturnhr; "ReturnHr"
0x180004569  lea     rdi, aReturnnt; "ReturnNt"
0x180004570  test    [rbx+4], bpl
0x180004574  cmovz   rdi, rax
0x180004578  jmp     short loc_180004581
0x18000457a  lea     rdi, aException; "Exception"
0x180004581  xor     edx, edx; Val
0x180004583  lea     rcx, [rsp+278h+Buffer]; void *
0x180004588  mov     r8d, 200h; Size
0x18000458e  call    memset_0
0x180004593  test    [rbx+4], bpl
0x180004597  jz      short loc_1800045BC
0x180004599  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800045a0  mov     ebp, [rbx+0Ch]
0x1800045a3  test    rax, rax
0x1800045a6  jz      short loc_1800045EC
0x1800045a8  mov     r8d, 100h
0x1800045ae  lea     rdx, [rsp+278h+Buffer]
0x1800045b3  mov     ecx, ebp
0x1800045b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ba  jmp     short loc_1800045EC
0x1800045bc  mov     ebp, [rbx+8]
0x1800045bf  lea     rax, [rsp+278h+Buffer]
0x1800045c4  mov     [rsp+278h+Arguments], r15; Arguments
0x1800045c9  mov     r8d, ebp; dwMessageId
0x1800045cc  mov     [rsp+278h+nSize], 100h; nSize
0x1800045d4  mov     r9d, 400h; dwLanguageId
0x1800045da  xor     edx, edx; lpSource
0x1800045dc  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800045e1  mov     ecx, 1200h; dwFlags
0x1800045e6  call    cs:__imp_FormatMessageW
0x1800045ec  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800045f0  lea     rsi, [r14+rsi*2]
0x1800045f4  mov     rax, [rbx+88h]
0x1800045fb  mov     rdx, rsi; unsigned __int16 *
0x1800045fe  mov     rcx, [rbx+80h]
0x180004605  test    r9, r9
0x180004608  jz      short loc_18000462C
0x18000460a  mov     [rsp+278h+Arguments], rax
0x18000460f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004616  mov     eax, [rbx+40h]
0x180004619  mov     qword ptr [rsp+278h+nSize], rcx
0x18000461e  mov     rcx, r14; this
0x180004621  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004625  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000462a  jmp     short loc_180004643
0x18000462c  mov     r9, rcx; unsigned __int16 *
0x18000462f  mov     [rsp+278h+lpBuffer], rax
0x180004634  mov     rcx, r14; this
0x180004637  lea     r8, aHsP; "%hs!%p: "
0x18000463e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004643  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000464a  mov     r14, rax
0x18000464d  test    r9, r9
0x180004650  jz      short loc_180004667
0x180004652  lea     r8, aCallerP; "(caller: %p) "
0x180004659  mov     rdx, rsi; unsigned __int16 *
0x18000465c  mov     rcx, rax; this
0x18000465f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004664  mov     r14, rax
0x180004667  call    cs:__imp_GetCurrentThreadId
0x18000466d  lea     rcx, [rsp+278h+Buffer]
0x180004672  mov     r9, rdi; unsigned __int16 *
0x180004675  mov     [rsp+278h+var_240], rcx
0x18000467a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004681  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004685  mov     rdx, rsi; unsigned __int16 *
0x180004688  mov     [rsp+278h+nSize], eax
0x18000468c  mov     rcx, r14; this
0x18000468f  mov     eax, [rbx+44h]
0x180004692  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004696  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000469b  cmp     [rbx+18h], r15
0x18000469f  jnz     short loc_1800046B1
0x1800046a1  cmp     [rbx+48h], r15
0x1800046a5  jnz     short loc_1800046B1
0x1800046a7  cmp     [rbx+30h], r15
0x1800046ab  jz      loc_180004741
0x1800046b1  lea     r8, asc_18000E8B8; "    "
0x1800046b8  mov     rdx, rsi; unsigned __int16 *
0x1800046bb  mov     rcx, rax; this
0x1800046be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800046c7  test    r9, r9
0x1800046ca  jz      short loc_1800046DE
0x1800046cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800046d3  mov     rdx, rsi; unsigned __int16 *
0x1800046d6  mov     rcx, rax; this
0x1800046d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800046e2  test    r9, r9
0x1800046e5  jz      short loc_1800046F9
0x1800046e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800046ee  mov     rdx, rsi; unsigned __int16 *
0x1800046f1  mov     rcx, rax; this
0x1800046f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800046f9  mov     rcx, [rbx+28h]
0x1800046fd  mov     rdx, rsi; unsigned __int16 *
0x180004700  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004704  test    rcx, rcx
0x180004707  jz      short loc_18000471F
0x180004709  mov     [rsp+278h+lpBuffer], rcx
0x18000470e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004715  mov     rcx, rax; this
0x180004718  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000471d  jmp     short loc_180004741
0x18000471f  mov     rcx, rax; this
0x180004722  test    r9, r9
0x180004725  jz      short loc_180004735
0x180004727  lea     r8, aHs; "[%hs]\n"
0x18000472e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004733  jmp     short loc_180004741
0x180004735  lea     r8, asc_18000E930; "\n"
0x18000473c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004741  xor     eax, eax
0x180004743  mov     rcx, [rsp+278h+var_38]
0x18000474b  xor     rcx, rsp; StackCookie
0x18000474e  call    __security_check_cookie
0x180004753  mov     rbx, [rsp+278h+arg_18]
0x18000475b  add     rsp, 250h
0x180004762  pop     r15
0x180004764  pop     r14
0x180004766  pop     rdi
0x180004767  pop     rsi
0x180004768  pop     rbp
0x180004769  retn
```
