# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005294`
- end: `0x18000554a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002c80`
- `0x180002ef0`
- `0x180005d60`
- `0x1800089e0`

## callees

- `0x180001ef0`
- `0x180002958`
- `0x180005294`
- `0x180006060`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005447`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800053c6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800053c6`

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
          v7 = (const char *)&word_180010E0A;
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
0x180005294  mov     [rsp+arg_18], rbx
0x180005299  push    rbp
0x18000529a  push    rsi
0x18000529b  push    rdi
0x18000529c  push    r14
0x18000529e  push    r15
0x1800052a0  sub     rsp, 250h
0x1800052a7  mov     rax, cs:__security_cookie
0x1800052ae  xor     rax, rsp
0x1800052b1  mov     [rsp+278h+var_38], rax
0x1800052b9  mov     rbx, r8
0x1800052bc  mov     rsi, rdx
0x1800052bf  mov     r14, rcx
0x1800052c2  xor     r15d, r15d
0x1800052c5  test    rdx, rdx
0x1800052c8  jz      loc_180005521
0x1800052ce  test    rcx, rcx
0x1800052d1  jz      loc_180005521
0x1800052d7  mov     [rcx], r15w
0x1800052db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052e2  test    rax, rax
0x1800052e5  jz      short loc_180005308
0x1800052e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800052ee  jz      short loc_180005308
0x1800052f0  mov     r8, rdx
0x1800052f3  mov     rdx, rcx
0x1800052f6  mov     rcx, rbx
0x1800052f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fe  cmp     [r14], r15w
0x180005302  jnz     loc_180005521
0x180005308  mov     ecx, [rbx]
0x18000530a  mov     bpl, 8
0x18000530d  test    ecx, ecx
0x18000530f  jz      short loc_18000535A
0x180005311  sub     ecx, 1
0x180005314  jz      short loc_180005342
0x180005316  sub     ecx, 1
0x180005319  jz      short loc_180005332
0x18000531b  cmp     ecx, 1
0x18000531e  jz      short loc_180005329
0x180005320  lea     rdi, word_180010E0A
0x180005327  jmp     short loc_180005361
0x180005329  lea     rdi, aFailfast; "FailFast"
0x180005330  jmp     short loc_180005361
0x180005332  lea     rax, aLoghr; "LogHr"
0x180005339  lea     rdi, aLognt; "LogNt"
0x180005340  jmp     short loc_180005350
0x180005342  lea     rax, aReturnhr; "ReturnHr"
0x180005349  lea     rdi, aReturnnt; "ReturnNt"
0x180005350  test    [rbx+4], bpl
0x180005354  cmovz   rdi, rax
0x180005358  jmp     short loc_180005361
0x18000535a  lea     rdi, aException; "Exception"
0x180005361  xor     edx, edx; Val
0x180005363  mov     r8d, 200h; Size
0x180005369  lea     rcx, [rsp+278h+Buffer]; void *
0x18000536e  call    memset_0
0x180005373  test    [rbx+4], bpl
0x180005377  jz      short loc_18000539C
0x180005379  mov     ebp, [rbx+0Ch]
0x18000537c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005383  test    rax, rax
0x180005386  jz      short loc_1800053CC
0x180005388  mov     r8d, 100h
0x18000538e  lea     rdx, [rsp+278h+Buffer]
0x180005393  mov     ecx, ebp
0x180005395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539a  jmp     short loc_1800053CC
0x18000539c  mov     ebp, [rbx+8]
0x18000539f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800053a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800053ac  lea     rax, [rsp+278h+Buffer]
0x1800053b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800053b6  mov     r9d, 400h; dwLanguageId
0x1800053bc  mov     r8d, ebp; dwMessageId
0x1800053bf  xor     edx, edx; lpSource
0x1800053c1  mov     ecx, 1200h; dwFlags
0x1800053c6  call    cs:__imp_FormatMessageW
0x1800053cc  lea     rsi, [r14+rsi*2]
0x1800053d0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800053d4  mov     rax, [rbx+88h]
0x1800053db  mov     rcx, [rbx+80h]
0x1800053e2  mov     rdx, rsi; unsigned __int16 *
0x1800053e5  test    r9, r9
0x1800053e8  jz      short loc_18000540C
0x1800053ea  mov     [rsp+278h+Arguments], rax
0x1800053ef  mov     qword ptr [rsp+278h+nSize], rcx
0x1800053f4  mov     eax, [rbx+40h]
0x1800053f7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800053fb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005402  mov     rcx, r14; this
0x180005405  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000540a  jmp     short loc_180005423
0x18000540c  mov     [rsp+278h+lpBuffer], rax
0x180005411  mov     r9, rcx; unsigned __int16 *
0x180005414  lea     r8, aHsP; "%hs!%p: "
0x18000541b  mov     rcx, r14; this
0x18000541e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005423  mov     r14, rax
0x180005426  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000542d  test    r9, r9
0x180005430  jz      short loc_180005447
0x180005432  lea     r8, aCallerP; "(caller: %p) "
0x180005439  mov     rdx, rsi; unsigned __int16 *
0x18000543c  mov     rcx, rax; this
0x18000543f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005444  mov     r14, rax
0x180005447  call    cs:__imp_GetCurrentThreadId
0x18000544d  lea     rcx, [rsp+278h+Buffer]
0x180005452  mov     [rsp+278h+var_240], rcx
0x180005457  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000545b  mov     [rsp+278h+nSize], eax
0x18000545f  mov     eax, [rbx+44h]
0x180005462  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005466  mov     r9, rdi; unsigned __int16 *
0x180005469  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005470  mov     rdx, rsi; unsigned __int16 *
0x180005473  mov     rcx, r14; this
0x180005476  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000547b  cmp     [rbx+18h], r15
0x18000547f  jnz     short loc_180005491
0x180005481  cmp     [rbx+48h], r15
0x180005485  jnz     short loc_180005491
0x180005487  cmp     [rbx+30h], r15
0x18000548b  jz      loc_180005521
0x180005491  lea     r8, asc_180010F18; "    "
0x180005498  mov     rdx, rsi; unsigned __int16 *
0x18000549b  mov     rcx, rax; this
0x18000549e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800054a7  test    r9, r9
0x1800054aa  jz      short loc_1800054BE
0x1800054ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800054b3  mov     rdx, rsi; unsigned __int16 *
0x1800054b6  mov     rcx, rax; this
0x1800054b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800054c2  test    r9, r9
0x1800054c5  jz      short loc_1800054D9
0x1800054c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800054ce  mov     rdx, rsi; unsigned __int16 *
0x1800054d1  mov     rcx, rax; this
0x1800054d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054d9  mov     rcx, [rbx+28h]
0x1800054dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800054e1  mov     rdx, rsi; unsigned __int16 *
0x1800054e4  test    rcx, rcx
0x1800054e7  jz      short loc_1800054FF
0x1800054e9  mov     [rsp+278h+lpBuffer], rcx
0x1800054ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800054f5  mov     rcx, rax; this
0x1800054f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054fd  jmp     short loc_180005521
0x1800054ff  mov     rcx, rax; this
0x180005502  test    r9, r9
0x180005505  jz      short loc_180005515
0x180005507  lea     r8, aHs; "[%hs]\n"
0x18000550e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005513  jmp     short loc_180005521
0x180005515  lea     r8, asc_180010F90; "\n"
0x18000551c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005521  xor     eax, eax
0x180005523  mov     rcx, [rsp+278h+var_38]
0x18000552b  xor     rcx, rsp; StackCookie
0x18000552e  call    __security_check_cookie
0x180005533  mov     rbx, [rsp+278h+arg_18]
0x18000553b  add     rsp, 250h
0x180005542  pop     r15
0x180005544  pop     r14
0x180005546  pop     rdi
0x180005547  pop     rsi
0x180005548  pop     rbp
0x180005549  retn
```
