# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800053a4`
- end: `0x18000565a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002d90`
- `0x180003000`
- `0x180005e70`
- `0x180008b00`

## callees

- `0x180002000`
- `0x180002a68`
- `0x1800053a4`
- `0x180006170`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005557`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005557`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800054d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800054d6`

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
          v7 = (const char *)&word_18000FE2A;
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
0x1800053a4  mov     [rsp+arg_18], rbx
0x1800053a9  push    rbp
0x1800053aa  push    rsi
0x1800053ab  push    rdi
0x1800053ac  push    r14
0x1800053ae  push    r15
0x1800053b0  sub     rsp, 250h
0x1800053b7  mov     rax, cs:__security_cookie
0x1800053be  xor     rax, rsp
0x1800053c1  mov     [rsp+278h+var_38], rax
0x1800053c9  mov     rbx, r8
0x1800053cc  mov     rsi, rdx
0x1800053cf  mov     r14, rcx
0x1800053d2  xor     r15d, r15d
0x1800053d5  test    rdx, rdx
0x1800053d8  jz      loc_180005631
0x1800053de  test    rcx, rcx
0x1800053e1  jz      loc_180005631
0x1800053e7  mov     [rcx], r15w
0x1800053eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800053f2  test    rax, rax
0x1800053f5  jz      short loc_180005418
0x1800053f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800053fe  jz      short loc_180005418
0x180005400  mov     r8, rdx
0x180005403  mov     rdx, rcx
0x180005406  mov     rcx, rbx
0x180005409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540e  cmp     [r14], r15w
0x180005412  jnz     loc_180005631
0x180005418  mov     ecx, [rbx]
0x18000541a  mov     bpl, 8
0x18000541d  test    ecx, ecx
0x18000541f  jz      short loc_18000546A
0x180005421  sub     ecx, 1
0x180005424  jz      short loc_180005452
0x180005426  sub     ecx, 1
0x180005429  jz      short loc_180005442
0x18000542b  cmp     ecx, 1
0x18000542e  jz      short loc_180005439
0x180005430  lea     rdi, word_18000FE2A
0x180005437  jmp     short loc_180005471
0x180005439  lea     rdi, aFailfast; "FailFast"
0x180005440  jmp     short loc_180005471
0x180005442  lea     rax, aLoghr; "LogHr"
0x180005449  lea     rdi, aLognt; "LogNt"
0x180005450  jmp     short loc_180005460
0x180005452  lea     rax, aReturnhr; "ReturnHr"
0x180005459  lea     rdi, aReturnnt; "ReturnNt"
0x180005460  test    [rbx+4], bpl
0x180005464  cmovz   rdi, rax
0x180005468  jmp     short loc_180005471
0x18000546a  lea     rdi, aException; "Exception"
0x180005471  xor     edx, edx; Val
0x180005473  mov     r8d, 200h; Size
0x180005479  lea     rcx, [rsp+278h+Buffer]; void *
0x18000547e  call    memset_0
0x180005483  test    [rbx+4], bpl
0x180005487  jz      short loc_1800054AC
0x180005489  mov     ebp, [rbx+0Ch]
0x18000548c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005493  test    rax, rax
0x180005496  jz      short loc_1800054DC
0x180005498  mov     r8d, 100h
0x18000549e  lea     rdx, [rsp+278h+Buffer]
0x1800054a3  mov     ecx, ebp
0x1800054a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054aa  jmp     short loc_1800054DC
0x1800054ac  mov     ebp, [rbx+8]
0x1800054af  mov     [rsp+278h+Arguments], r15; Arguments
0x1800054b4  mov     [rsp+278h+nSize], 100h; nSize
0x1800054bc  lea     rax, [rsp+278h+Buffer]
0x1800054c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800054c6  mov     r9d, 400h; dwLanguageId
0x1800054cc  mov     r8d, ebp; dwMessageId
0x1800054cf  xor     edx, edx; lpSource
0x1800054d1  mov     ecx, 1200h; dwFlags
0x1800054d6  call    cs:__imp_FormatMessageW
0x1800054dc  lea     rsi, [r14+rsi*2]
0x1800054e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800054e4  mov     rax, [rbx+88h]
0x1800054eb  mov     rcx, [rbx+80h]
0x1800054f2  mov     rdx, rsi; unsigned __int16 *
0x1800054f5  test    r9, r9
0x1800054f8  jz      short loc_18000551C
0x1800054fa  mov     [rsp+278h+Arguments], rax
0x1800054ff  mov     qword ptr [rsp+278h+nSize], rcx
0x180005504  mov     eax, [rbx+40h]
0x180005507  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000550b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005512  mov     rcx, r14; this
0x180005515  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000551a  jmp     short loc_180005533
0x18000551c  mov     [rsp+278h+lpBuffer], rax
0x180005521  mov     r9, rcx; unsigned __int16 *
0x180005524  lea     r8, aHsP; "%hs!%p: "
0x18000552b  mov     rcx, r14; this
0x18000552e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005533  mov     r14, rax
0x180005536  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000553d  test    r9, r9
0x180005540  jz      short loc_180005557
0x180005542  lea     r8, aCallerP; "(caller: %p) "
0x180005549  mov     rdx, rsi; unsigned __int16 *
0x18000554c  mov     rcx, rax; this
0x18000554f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005554  mov     r14, rax
0x180005557  call    cs:__imp_GetCurrentThreadId
0x18000555d  lea     rcx, [rsp+278h+Buffer]
0x180005562  mov     [rsp+278h+var_240], rcx
0x180005567  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000556b  mov     [rsp+278h+nSize], eax
0x18000556f  mov     eax, [rbx+44h]
0x180005572  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005576  mov     r9, rdi; unsigned __int16 *
0x180005579  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005580  mov     rdx, rsi; unsigned __int16 *
0x180005583  mov     rcx, r14; this
0x180005586  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000558b  cmp     [rbx+18h], r15
0x18000558f  jnz     short loc_1800055A1
0x180005591  cmp     [rbx+48h], r15
0x180005595  jnz     short loc_1800055A1
0x180005597  cmp     [rbx+30h], r15
0x18000559b  jz      loc_180005631
0x1800055a1  lea     r8, asc_18000FF38; "    "
0x1800055a8  mov     rdx, rsi; unsigned __int16 *
0x1800055ab  mov     rcx, rax; this
0x1800055ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800055b7  test    r9, r9
0x1800055ba  jz      short loc_1800055CE
0x1800055bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800055c3  mov     rdx, rsi; unsigned __int16 *
0x1800055c6  mov     rcx, rax; this
0x1800055c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800055d2  test    r9, r9
0x1800055d5  jz      short loc_1800055E9
0x1800055d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800055de  mov     rdx, rsi; unsigned __int16 *
0x1800055e1  mov     rcx, rax; this
0x1800055e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055e9  mov     rcx, [rbx+28h]
0x1800055ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800055f1  mov     rdx, rsi; unsigned __int16 *
0x1800055f4  test    rcx, rcx
0x1800055f7  jz      short loc_18000560F
0x1800055f9  mov     [rsp+278h+lpBuffer], rcx
0x1800055fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005605  mov     rcx, rax; this
0x180005608  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000560d  jmp     short loc_180005631
0x18000560f  mov     rcx, rax; this
0x180005612  test    r9, r9
0x180005615  jz      short loc_180005625
0x180005617  lea     r8, aHs; "[%hs]\n"
0x18000561e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005623  jmp     short loc_180005631
0x180005625  lea     r8, asc_18000FFB0; "\n"
0x18000562c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005631  xor     eax, eax
0x180005633  mov     rcx, [rsp+278h+var_38]
0x18000563b  xor     rcx, rsp; StackCookie
0x18000563e  call    __security_check_cookie
0x180005643  mov     rbx, [rsp+278h+arg_18]
0x18000564b  add     rsp, 250h
0x180005652  pop     r15
0x180005654  pop     r14
0x180005656  pop     rdi
0x180005657  pop     rsi
0x180005658  pop     rbp
0x180005659  retn
```
