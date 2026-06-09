# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400053a4`
- end: `0x14000565a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140003e04`
- `0x140005f80`
- `0x14000644c`
- `0x140007c90`

## callees

- `0x140002930`
- `0x14000349c`
- `0x1400053a4`
- `0x140006280`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005557`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005557`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400054d6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400054d6`

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
          v7 = (const char *)&byte_14001ACA1;
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
0x1400053a4  mov     [rsp+arg_18], rbx
0x1400053a9  push    rbp
0x1400053aa  push    rsi
0x1400053ab  push    rdi
0x1400053ac  push    r14
0x1400053ae  push    r15
0x1400053b0  sub     rsp, 250h
0x1400053b7  mov     rax, cs:__security_cookie
0x1400053be  xor     rax, rsp
0x1400053c1  mov     [rsp+278h+var_38], rax
0x1400053c9  mov     rbx, r8
0x1400053cc  mov     rsi, rdx
0x1400053cf  mov     r14, rcx
0x1400053d2  xor     r15d, r15d
0x1400053d5  test    rdx, rdx
0x1400053d8  jz      loc_140005631
0x1400053de  test    rcx, rcx
0x1400053e1  jz      loc_140005631
0x1400053e7  mov     [rcx], r15w
0x1400053eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1400053f2  test    rax, rax
0x1400053f5  jz      short loc_140005418
0x1400053f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400053fe  jz      short loc_140005418
0x140005400  mov     r8, rdx
0x140005403  mov     rdx, rcx
0x140005406  mov     rcx, rbx
0x140005409  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000540e  cmp     [r14], r15w
0x140005412  jnz     loc_140005631
0x140005418  mov     ecx, [rbx]
0x14000541a  mov     bpl, 8
0x14000541d  test    ecx, ecx
0x14000541f  jz      short loc_14000546A
0x140005421  sub     ecx, 1
0x140005424  jz      short loc_140005452
0x140005426  sub     ecx, 1
0x140005429  jz      short loc_140005442
0x14000542b  cmp     ecx, 1
0x14000542e  jz      short loc_140005439
0x140005430  lea     rdi, byte_14001ACA1
0x140005437  jmp     short loc_140005471
0x140005439  lea     rdi, aFailfast; "FailFast"
0x140005440  jmp     short loc_140005471
0x140005442  lea     rax, aLoghr; "LogHr"
0x140005449  lea     rdi, aLognt; "LogNt"
0x140005450  jmp     short loc_140005460
0x140005452  lea     rax, aReturnhr; "ReturnHr"
0x140005459  lea     rdi, aReturnnt; "ReturnNt"
0x140005460  test    [rbx+4], bpl
0x140005464  cmovz   rdi, rax
0x140005468  jmp     short loc_140005471
0x14000546a  lea     rdi, aException; "Exception"
0x140005471  xor     edx, edx; Val
0x140005473  mov     r8d, 200h; Size
0x140005479  lea     rcx, [rsp+278h+Buffer]; void *
0x14000547e  call    memset_0
0x140005483  test    [rbx+4], bpl
0x140005487  jz      short loc_1400054AC
0x140005489  mov     ebp, [rbx+0Ch]
0x14000548c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005493  test    rax, rax
0x140005496  jz      short loc_1400054DC
0x140005498  mov     r8d, 100h
0x14000549e  lea     rdx, [rsp+278h+Buffer]
0x1400054a3  mov     ecx, ebp
0x1400054a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400054aa  jmp     short loc_1400054DC
0x1400054ac  mov     ebp, [rbx+8]
0x1400054af  mov     [rsp+278h+Arguments], r15; Arguments
0x1400054b4  mov     [rsp+278h+nSize], 100h; nSize
0x1400054bc  lea     rax, [rsp+278h+Buffer]
0x1400054c1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400054c6  mov     r9d, 400h; dwLanguageId
0x1400054cc  mov     r8d, ebp; dwMessageId
0x1400054cf  xor     edx, edx; lpSource
0x1400054d1  mov     ecx, 1200h; dwFlags
0x1400054d6  call    cs:__imp_FormatMessageW
0x1400054dc  lea     rsi, [r14+rsi*2]
0x1400054e0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400054e4  mov     rax, [rbx+88h]
0x1400054eb  mov     rcx, [rbx+80h]
0x1400054f2  mov     rdx, rsi; unsigned __int16 *
0x1400054f5  test    r9, r9
0x1400054f8  jz      short loc_14000551C
0x1400054fa  mov     [rsp+278h+Arguments], rax
0x1400054ff  mov     qword ptr [rsp+278h+nSize], rcx
0x140005504  mov     eax, [rbx+40h]
0x140005507  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000550b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005512  mov     rcx, r14; this
0x140005515  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000551a  jmp     short loc_140005533
0x14000551c  mov     [rsp+278h+lpBuffer], rax
0x140005521  mov     r9, rcx; unsigned __int16 *
0x140005524  lea     r8, aHsP; "%hs!%p: "
0x14000552b  mov     rcx, r14; this
0x14000552e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005533  mov     r14, rax
0x140005536  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000553d  test    r9, r9
0x140005540  jz      short loc_140005557
0x140005542  lea     r8, aCallerP; "(caller: %p) "
0x140005549  mov     rdx, rsi; unsigned __int16 *
0x14000554c  mov     rcx, rax; this
0x14000554f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005554  mov     r14, rax
0x140005557  call    cs:__imp_GetCurrentThreadId
0x14000555d  lea     rcx, [rsp+278h+Buffer]
0x140005562  mov     [rsp+278h+var_240], rcx
0x140005567  mov     dword ptr [rsp+278h+Arguments], ebp
0x14000556b  mov     [rsp+278h+nSize], eax
0x14000556f  mov     eax, [rbx+44h]
0x140005572  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005576  mov     r9, rdi; unsigned __int16 *
0x140005579  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005580  mov     rdx, rsi; unsigned __int16 *
0x140005583  mov     rcx, r14; this
0x140005586  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000558b  cmp     [rbx+18h], r15
0x14000558f  jnz     short loc_1400055A1
0x140005591  cmp     [rbx+48h], r15
0x140005595  jnz     short loc_1400055A1
0x140005597  cmp     [rbx+30h], r15
0x14000559b  jz      loc_140005631
0x1400055a1  lea     r8, asc_14001ADC0; "    "
0x1400055a8  mov     rdx, rsi; unsigned __int16 *
0x1400055ab  mov     rcx, rax; this
0x1400055ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055b3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400055b7  test    r9, r9
0x1400055ba  jz      short loc_1400055CE
0x1400055bc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400055c3  mov     rdx, rsi; unsigned __int16 *
0x1400055c6  mov     rcx, rax; this
0x1400055c9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055ce  mov     r9, [rbx+48h]; unsigned __int16 *
0x1400055d2  test    r9, r9
0x1400055d5  jz      short loc_1400055E9
0x1400055d7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1400055de  mov     rdx, rsi; unsigned __int16 *
0x1400055e1  mov     rcx, rax; this
0x1400055e4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400055e9  mov     rcx, [rbx+28h]
0x1400055ed  mov     r9, [rbx+30h]; unsigned __int16 *
0x1400055f1  mov     rdx, rsi; unsigned __int16 *
0x1400055f4  test    rcx, rcx
0x1400055f7  jz      short loc_14000560F
0x1400055f9  mov     [rsp+278h+lpBuffer], rcx
0x1400055fe  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005605  mov     rcx, rax; this
0x140005608  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000560d  jmp     short loc_140005631
0x14000560f  mov     rcx, rax; this
0x140005612  test    r9, r9
0x140005615  jz      short loc_140005625
0x140005617  lea     r8, aHs; "[%hs]\n"
0x14000561e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005623  jmp     short loc_140005631
0x140005625  lea     r8, asc_14001AE38; "\n"
0x14000562c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005631  xor     eax, eax
0x140005633  mov     rcx, [rsp+278h+var_38]
0x14000563b  xor     rcx, rsp; StackCookie
0x14000563e  call    __security_check_cookie
0x140005643  mov     rbx, [rsp+278h+arg_18]
0x14000564b  add     rsp, 250h
0x140005652  pop     r15
0x140005654  pop     r14
0x140005656  pop     rdi
0x140005657  pop     rsi
0x140005658  pop     rbp
0x140005659  retn
```
