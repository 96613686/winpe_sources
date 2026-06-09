# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800054d4`
- end: `0x18000578a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800037d4`
- `0x180003a54`
- `0x18000610c`
- `0x180007b40`
- `0x1800085c0`

## callees

- `0x180002240`
- `0x180002db8`
- `0x1800054d4`
- `0x18000640c`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005687`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005606`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005606`

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
          v7 = (const char *)&word_18006CCAB;
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
0x1800054d4  mov     [rsp+arg_18], rbx
0x1800054d9  push    rbp
0x1800054da  push    rsi
0x1800054db  push    rdi
0x1800054dc  push    r14
0x1800054de  push    r15
0x1800054e0  sub     rsp, 250h
0x1800054e7  mov     rax, cs:__security_cookie
0x1800054ee  xor     rax, rsp
0x1800054f1  mov     [rsp+278h+var_38], rax
0x1800054f9  mov     rbx, r8
0x1800054fc  mov     rsi, rdx
0x1800054ff  mov     r14, rcx
0x180005502  xor     r15d, r15d
0x180005505  test    rdx, rdx
0x180005508  jz      loc_180005761
0x18000550e  test    rcx, rcx
0x180005511  jz      loc_180005761
0x180005517  mov     [rcx], r15w
0x18000551b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005522  test    rax, rax
0x180005525  jz      short loc_180005548
0x180005527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000552e  jz      short loc_180005548
0x180005530  mov     r8, rdx
0x180005533  mov     rdx, rcx
0x180005536  mov     rcx, rbx
0x180005539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000553e  cmp     [r14], r15w
0x180005542  jnz     loc_180005761
0x180005548  mov     ecx, [rbx]
0x18000554a  mov     bpl, 8
0x18000554d  test    ecx, ecx
0x18000554f  jz      short loc_18000559A
0x180005551  sub     ecx, 1
0x180005554  jz      short loc_180005582
0x180005556  sub     ecx, 1
0x180005559  jz      short loc_180005572
0x18000555b  cmp     ecx, 1
0x18000555e  jz      short loc_180005569
0x180005560  lea     rdi, word_18006CCAB
0x180005567  jmp     short loc_1800055A1
0x180005569  lea     rdi, aFailfast; "FailFast"
0x180005570  jmp     short loc_1800055A1
0x180005572  lea     rax, aLoghr; "LogHr"
0x180005579  lea     rdi, aLognt; "LogNt"
0x180005580  jmp     short loc_180005590
0x180005582  lea     rax, aReturnhr; "ReturnHr"
0x180005589  lea     rdi, aReturnnt; "ReturnNt"
0x180005590  test    [rbx+4], bpl
0x180005594  cmovz   rdi, rax
0x180005598  jmp     short loc_1800055A1
0x18000559a  lea     rdi, aException; "Exception"
0x1800055a1  xor     edx, edx; Val
0x1800055a3  mov     r8d, 200h; Size
0x1800055a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800055ae  call    memset_0
0x1800055b3  test    [rbx+4], bpl
0x1800055b7  jz      short loc_1800055DC
0x1800055b9  mov     ebp, [rbx+0Ch]
0x1800055bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800055c3  test    rax, rax
0x1800055c6  jz      short loc_18000560C
0x1800055c8  mov     r8d, 100h
0x1800055ce  lea     rdx, [rsp+278h+Buffer]
0x1800055d3  mov     ecx, ebp
0x1800055d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800055da  jmp     short loc_18000560C
0x1800055dc  mov     ebp, [rbx+8]
0x1800055df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800055e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800055ec  lea     rax, [rsp+278h+Buffer]
0x1800055f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800055f6  mov     r9d, 400h; dwLanguageId
0x1800055fc  mov     r8d, ebp; dwMessageId
0x1800055ff  xor     edx, edx; lpSource
0x180005601  mov     ecx, 1200h; dwFlags
0x180005606  call    cs:__imp_FormatMessageW
0x18000560c  lea     rsi, [r14+rsi*2]
0x180005610  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005614  mov     rax, [rbx+88h]
0x18000561b  mov     rcx, [rbx+80h]
0x180005622  mov     rdx, rsi; unsigned __int16 *
0x180005625  test    r9, r9
0x180005628  jz      short loc_18000564C
0x18000562a  mov     [rsp+278h+Arguments], rax
0x18000562f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005634  mov     eax, [rbx+40h]
0x180005637  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000563b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005642  mov     rcx, r14; this
0x180005645  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000564a  jmp     short loc_180005663
0x18000564c  mov     [rsp+278h+lpBuffer], rax
0x180005651  mov     r9, rcx; unsigned __int16 *
0x180005654  lea     r8, aHsP; "%hs!%p: "
0x18000565b  mov     rcx, r14; this
0x18000565e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005663  mov     r14, rax
0x180005666  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000566d  test    r9, r9
0x180005670  jz      short loc_180005687
0x180005672  lea     r8, aCallerP; "(caller: %p) "
0x180005679  mov     rdx, rsi; unsigned __int16 *
0x18000567c  mov     rcx, rax; this
0x18000567f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005684  mov     r14, rax
0x180005687  call    cs:__imp_GetCurrentThreadId
0x18000568d  lea     rcx, [rsp+278h+Buffer]
0x180005692  mov     [rsp+278h+var_240], rcx
0x180005697  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000569b  mov     [rsp+278h+nSize], eax
0x18000569f  mov     eax, [rbx+44h]
0x1800056a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800056a6  mov     r9, rdi; unsigned __int16 *
0x1800056a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800056b0  mov     rdx, rsi; unsigned __int16 *
0x1800056b3  mov     rcx, r14; this
0x1800056b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056bb  cmp     [rbx+18h], r15
0x1800056bf  jnz     short loc_1800056D1
0x1800056c1  cmp     [rbx+48h], r15
0x1800056c5  jnz     short loc_1800056D1
0x1800056c7  cmp     [rbx+30h], r15
0x1800056cb  jz      loc_180005761
0x1800056d1  lea     r8, asc_18006CDB0; "    "
0x1800056d8  mov     rdx, rsi; unsigned __int16 *
0x1800056db  mov     rcx, rax; this
0x1800056de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800056e7  test    r9, r9
0x1800056ea  jz      short loc_1800056FE
0x1800056ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800056f3  mov     rdx, rsi; unsigned __int16 *
0x1800056f6  mov     rcx, rax; this
0x1800056f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800056fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005702  test    r9, r9
0x180005705  jz      short loc_180005719
0x180005707  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000570e  mov     rdx, rsi; unsigned __int16 *
0x180005711  mov     rcx, rax; this
0x180005714  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005719  mov     rcx, [rbx+28h]
0x18000571d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005721  mov     rdx, rsi; unsigned __int16 *
0x180005724  test    rcx, rcx
0x180005727  jz      short loc_18000573F
0x180005729  mov     [rsp+278h+lpBuffer], rcx
0x18000572e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005735  mov     rcx, rax; this
0x180005738  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000573d  jmp     short loc_180005761
0x18000573f  mov     rcx, rax; this
0x180005742  test    r9, r9
0x180005745  jz      short loc_180005755
0x180005747  lea     r8, aHs; "[%hs]\n"
0x18000574e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005753  jmp     short loc_180005761
0x180005755  lea     r8, asc_18006CE28; "\n"
0x18000575c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005761  xor     eax, eax
0x180005763  mov     rcx, [rsp+278h+var_38]
0x18000576b  xor     rcx, rsp; StackCookie
0x18000576e  call    __security_check_cookie
0x180005773  mov     rbx, [rsp+278h+arg_18]
0x18000577b  add     rsp, 250h
0x180005782  pop     r15
0x180005784  pop     r14
0x180005786  pop     rdi
0x180005787  pop     rsi
0x180005788  pop     rbp
0x180005789  retn
```
