# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005464`
- end: `0x18000571a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002e4c`
- `0x1800030cc`
- `0x180005eb8`
- `0x180009680`
- `0x18000a0b8`
- `0x180032e66`
- `0x180032f9a`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x180005464`
- `0x1800061b8`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005617`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005617`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005596`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005596`

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
          v7 = (const char *)&dword_18003A9FC;
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
0x180005464  mov     [rsp+arg_18], rbx
0x180005469  push    rbp
0x18000546a  push    rsi
0x18000546b  push    rdi
0x18000546c  push    r14
0x18000546e  push    r15
0x180005470  sub     rsp, 250h
0x180005477  mov     rax, cs:__security_cookie
0x18000547e  xor     rax, rsp
0x180005481  mov     [rsp+278h+var_38], rax
0x180005489  mov     rbx, r8
0x18000548c  mov     rsi, rdx
0x18000548f  mov     r14, rcx
0x180005492  xor     r15d, r15d
0x180005495  test    rdx, rdx
0x180005498  jz      loc_1800056F1
0x18000549e  test    rcx, rcx
0x1800054a1  jz      loc_1800056F1
0x1800054a7  mov     [rcx], r15w
0x1800054ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800054b2  test    rax, rax
0x1800054b5  jz      short loc_1800054D8
0x1800054b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800054be  jz      short loc_1800054D8
0x1800054c0  mov     r8, rdx
0x1800054c3  mov     rdx, rcx
0x1800054c6  mov     rcx, rbx
0x1800054c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800054ce  cmp     [r14], r15w
0x1800054d2  jnz     loc_1800056F1
0x1800054d8  mov     ecx, [rbx]
0x1800054da  mov     bpl, 8
0x1800054dd  test    ecx, ecx
0x1800054df  jz      short loc_18000552A
0x1800054e1  sub     ecx, 1
0x1800054e4  jz      short loc_180005512
0x1800054e6  sub     ecx, 1
0x1800054e9  jz      short loc_180005502
0x1800054eb  cmp     ecx, 1
0x1800054ee  jz      short loc_1800054F9
0x1800054f0  lea     rdi, dword_18003A9FC
0x1800054f7  jmp     short loc_180005531
0x1800054f9  lea     rdi, aFailfast; "FailFast"
0x180005500  jmp     short loc_180005531
0x180005502  lea     rax, aLoghr; "LogHr"
0x180005509  lea     rdi, aLognt; "LogNt"
0x180005510  jmp     short loc_180005520
0x180005512  lea     rax, aReturnhr; "ReturnHr"
0x180005519  lea     rdi, aReturnnt; "ReturnNt"
0x180005520  test    [rbx+4], bpl
0x180005524  cmovz   rdi, rax
0x180005528  jmp     short loc_180005531
0x18000552a  lea     rdi, aException; "Exception"
0x180005531  xor     edx, edx; Val
0x180005533  mov     r8d, 200h; Size
0x180005539  lea     rcx, [rsp+278h+Buffer]; void *
0x18000553e  call    memset_0
0x180005543  test    [rbx+4], bpl
0x180005547  jz      short loc_18000556C
0x180005549  mov     ebp, [rbx+0Ch]
0x18000554c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005553  test    rax, rax
0x180005556  jz      short loc_18000559C
0x180005558  mov     r8d, 100h
0x18000555e  lea     rdx, [rsp+278h+Buffer]
0x180005563  mov     ecx, ebp
0x180005565  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000556a  jmp     short loc_18000559C
0x18000556c  mov     ebp, [rbx+8]
0x18000556f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005574  mov     [rsp+278h+nSize], 100h; nSize
0x18000557c  lea     rax, [rsp+278h+Buffer]
0x180005581  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005586  mov     r9d, 400h; dwLanguageId
0x18000558c  mov     r8d, ebp; dwMessageId
0x18000558f  xor     edx, edx; lpSource
0x180005591  mov     ecx, 1200h; dwFlags
0x180005596  call    cs:__imp_FormatMessageW
0x18000559c  lea     rsi, [r14+rsi*2]
0x1800055a0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800055a4  mov     rax, [rbx+88h]
0x1800055ab  mov     rcx, [rbx+80h]
0x1800055b2  mov     rdx, rsi; unsigned __int16 *
0x1800055b5  test    r9, r9
0x1800055b8  jz      short loc_1800055DC
0x1800055ba  mov     [rsp+278h+Arguments], rax
0x1800055bf  mov     qword ptr [rsp+278h+nSize], rcx
0x1800055c4  mov     eax, [rbx+40h]
0x1800055c7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800055cb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800055d2  mov     rcx, r14; this
0x1800055d5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055da  jmp     short loc_1800055F3
0x1800055dc  mov     [rsp+278h+lpBuffer], rax
0x1800055e1  mov     r9, rcx; unsigned __int16 *
0x1800055e4  lea     r8, aHsP; "%hs!%p: "
0x1800055eb  mov     rcx, r14; this
0x1800055ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800055f3  mov     r14, rax
0x1800055f6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800055fd  test    r9, r9
0x180005600  jz      short loc_180005617
0x180005602  lea     r8, aCallerP; "(caller: %p) "
0x180005609  mov     rdx, rsi; unsigned __int16 *
0x18000560c  mov     rcx, rax; this
0x18000560f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005614  mov     r14, rax
0x180005617  call    cs:__imp_GetCurrentThreadId
0x18000561d  lea     rcx, [rsp+278h+Buffer]
0x180005622  mov     [rsp+278h+var_240], rcx
0x180005627  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000562b  mov     [rsp+278h+nSize], eax
0x18000562f  mov     eax, [rbx+44h]
0x180005632  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005636  mov     r9, rdi; unsigned __int16 *
0x180005639  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005640  mov     rdx, rsi; unsigned __int16 *
0x180005643  mov     rcx, r14; this
0x180005646  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000564b  cmp     [rbx+18h], r15
0x18000564f  jnz     short loc_180005661
0x180005651  cmp     [rbx+48h], r15
0x180005655  jnz     short loc_180005661
0x180005657  cmp     [rbx+30h], r15
0x18000565b  jz      loc_1800056F1
0x180005661  lea     r8, asc_18003AB00; "    "
0x180005668  mov     rdx, rsi; unsigned __int16 *
0x18000566b  mov     rcx, rax; this
0x18000566e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005673  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005677  test    r9, r9
0x18000567a  jz      short loc_18000568E
0x18000567c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005683  mov     rdx, rsi; unsigned __int16 *
0x180005686  mov     rcx, rax; this
0x180005689  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000568e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005692  test    r9, r9
0x180005695  jz      short loc_1800056A9
0x180005697  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000569e  mov     rdx, rsi; unsigned __int16 *
0x1800056a1  mov     rcx, rax; this
0x1800056a4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056a9  mov     rcx, [rbx+28h]
0x1800056ad  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800056b1  mov     rdx, rsi; unsigned __int16 *
0x1800056b4  test    rcx, rcx
0x1800056b7  jz      short loc_1800056CF
0x1800056b9  mov     [rsp+278h+lpBuffer], rcx
0x1800056be  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800056c5  mov     rcx, rax; this
0x1800056c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056cd  jmp     short loc_1800056F1
0x1800056cf  mov     rcx, rax; this
0x1800056d2  test    r9, r9
0x1800056d5  jz      short loc_1800056E5
0x1800056d7  lea     r8, aHs; "[%hs]\n"
0x1800056de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056e3  jmp     short loc_1800056F1
0x1800056e5  lea     r8, asc_18003AB78; "\n"
0x1800056ec  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056f1  xor     eax, eax
0x1800056f3  mov     rcx, [rsp+278h+var_38]
0x1800056fb  xor     rcx, rsp; StackCookie
0x1800056fe  call    __security_check_cookie
0x180005703  mov     rbx, [rsp+278h+arg_18]
0x18000570b  add     rsp, 250h
0x180005712  pop     r15
0x180005714  pop     r14
0x180005716  pop     rdi
0x180005717  pop     rsi
0x180005718  pop     rbp
0x180005719  retn
```
