# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800055e4`
- end: `0x18000589a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800026a4`
- `0x18000290c`
- `0x1800069f0`
- `0x18000b320`

## callees

- `0x1800055e4`
- `0x180006cf0`
- `0x18000c5e2`
- `0x18000c610`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005797`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005797`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005716`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005716`

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
          v7 = (const char *)&qword_18000FE78;
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
0x1800055e4  mov     [rsp+arg_18], rbx
0x1800055e9  push    rbp
0x1800055ea  push    rsi
0x1800055eb  push    rdi
0x1800055ec  push    r14
0x1800055ee  push    r15
0x1800055f0  sub     rsp, 250h
0x1800055f7  mov     rax, cs:__security_cookie
0x1800055fe  xor     rax, rsp
0x180005601  mov     [rsp+278h+var_38], rax
0x180005609  mov     rbx, r8
0x18000560c  mov     rsi, rdx
0x18000560f  mov     r14, rcx
0x180005612  xor     r15d, r15d
0x180005615  test    rdx, rdx
0x180005618  jz      loc_180005871
0x18000561e  test    rcx, rcx
0x180005621  jz      loc_180005871
0x180005627  mov     [rcx], r15w
0x18000562b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005632  test    rax, rax
0x180005635  jz      short loc_180005658
0x180005637  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000563e  jz      short loc_180005658
0x180005640  mov     r8, rdx
0x180005643  mov     rdx, rcx
0x180005646  mov     rcx, rbx
0x180005649  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564e  cmp     [r14], r15w
0x180005652  jnz     loc_180005871
0x180005658  mov     ecx, [rbx]
0x18000565a  mov     bpl, 8
0x18000565d  test    ecx, ecx
0x18000565f  jz      short loc_1800056AA
0x180005661  sub     ecx, 1
0x180005664  jz      short loc_180005692
0x180005666  sub     ecx, 1
0x180005669  jz      short loc_180005682
0x18000566b  cmp     ecx, 1
0x18000566e  jz      short loc_180005679
0x180005670  lea     rdi, qword_18000FE78
0x180005677  jmp     short loc_1800056B1
0x180005679  lea     rdi, aFailfast; "FailFast"
0x180005680  jmp     short loc_1800056B1
0x180005682  lea     rax, aLoghr; "LogHr"
0x180005689  lea     rdi, aLognt; "LogNt"
0x180005690  jmp     short loc_1800056A0
0x180005692  lea     rax, aReturnhr; "ReturnHr"
0x180005699  lea     rdi, aReturnnt; "ReturnNt"
0x1800056a0  test    [rbx+4], bpl
0x1800056a4  cmovz   rdi, rax
0x1800056a8  jmp     short loc_1800056B1
0x1800056aa  lea     rdi, aException; "Exception"
0x1800056b1  xor     edx, edx; Val
0x1800056b3  mov     r8d, 200h; Size
0x1800056b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800056be  call    memset_0
0x1800056c3  test    [rbx+4], bpl
0x1800056c7  jz      short loc_1800056EC
0x1800056c9  mov     ebp, [rbx+0Ch]
0x1800056cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800056d3  test    rax, rax
0x1800056d6  jz      short loc_18000571C
0x1800056d8  mov     r8d, 100h
0x1800056de  lea     rdx, [rsp+278h+Buffer]
0x1800056e3  mov     ecx, ebp
0x1800056e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056ea  jmp     short loc_18000571C
0x1800056ec  mov     ebp, [rbx+8]
0x1800056ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800056f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800056fc  lea     rax, [rsp+278h+Buffer]
0x180005701  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005706  mov     r9d, 400h; dwLanguageId
0x18000570c  mov     r8d, ebp; dwMessageId
0x18000570f  xor     edx, edx; lpSource
0x180005711  mov     ecx, 1200h; dwFlags
0x180005716  call    cs:__imp_FormatMessageW
0x18000571c  lea     rsi, [r14+rsi*2]
0x180005720  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005724  mov     rax, [rbx+88h]
0x18000572b  mov     rcx, [rbx+80h]
0x180005732  mov     rdx, rsi; unsigned __int16 *
0x180005735  test    r9, r9
0x180005738  jz      short loc_18000575C
0x18000573a  mov     [rsp+278h+Arguments], rax
0x18000573f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005744  mov     eax, [rbx+40h]
0x180005747  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000574b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005752  mov     rcx, r14; this
0x180005755  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000575a  jmp     short loc_180005773
0x18000575c  mov     [rsp+278h+lpBuffer], rax
0x180005761  mov     r9, rcx; unsigned __int16 *
0x180005764  lea     r8, aHsP; "%hs!%p: "
0x18000576b  mov     rcx, r14; this
0x18000576e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005773  mov     r14, rax
0x180005776  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000577d  test    r9, r9
0x180005780  jz      short loc_180005797
0x180005782  lea     r8, aCallerP; "(caller: %p) "
0x180005789  mov     rdx, rsi; unsigned __int16 *
0x18000578c  mov     rcx, rax; this
0x18000578f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005794  mov     r14, rax
0x180005797  call    cs:__imp_GetCurrentThreadId
0x18000579d  lea     rcx, [rsp+278h+Buffer]
0x1800057a2  mov     [rsp+278h+var_240], rcx
0x1800057a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800057ab  mov     [rsp+278h+nSize], eax
0x1800057af  mov     eax, [rbx+44h]
0x1800057b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800057b6  mov     r9, rdi; unsigned __int16 *
0x1800057b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800057c0  mov     rdx, rsi; unsigned __int16 *
0x1800057c3  mov     rcx, r14; this
0x1800057c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057cb  cmp     [rbx+18h], r15
0x1800057cf  jnz     short loc_1800057E1
0x1800057d1  cmp     [rbx+48h], r15
0x1800057d5  jnz     short loc_1800057E1
0x1800057d7  cmp     [rbx+30h], r15
0x1800057db  jz      loc_180005871
0x1800057e1  lea     r8, asc_18000FF78; "    "
0x1800057e8  mov     rdx, rsi; unsigned __int16 *
0x1800057eb  mov     rcx, rax; this
0x1800057ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800057f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800057f7  test    r9, r9
0x1800057fa  jz      short loc_18000580E
0x1800057fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005803  mov     rdx, rsi; unsigned __int16 *
0x180005806  mov     rcx, rax; this
0x180005809  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000580e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005812  test    r9, r9
0x180005815  jz      short loc_180005829
0x180005817  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000581e  mov     rdx, rsi; unsigned __int16 *
0x180005821  mov     rcx, rax; this
0x180005824  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005829  mov     rcx, [rbx+28h]
0x18000582d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005831  mov     rdx, rsi; unsigned __int16 *
0x180005834  test    rcx, rcx
0x180005837  jz      short loc_18000584F
0x180005839  mov     [rsp+278h+lpBuffer], rcx
0x18000583e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005845  mov     rcx, rax; this
0x180005848  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000584d  jmp     short loc_180005871
0x18000584f  mov     rcx, rax; this
0x180005852  test    r9, r9
0x180005855  jz      short loc_180005865
0x180005857  lea     r8, aHs; "[%hs]\n"
0x18000585e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005863  jmp     short loc_180005871
0x180005865  lea     r8, asc_18000FFF0; "\n"
0x18000586c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005871  xor     eax, eax
0x180005873  mov     rcx, [rsp+278h+var_38]
0x18000587b  xor     rcx, rsp; StackCookie
0x18000587e  call    __security_check_cookie
0x180005883  mov     rbx, [rsp+278h+arg_18]
0x18000588b  add     rsp, 250h
0x180005892  pop     r15
0x180005894  pop     r14
0x180005896  pop     rdi
0x180005897  pop     rsi
0x180005898  pop     rbp
0x180005899  retn
```
