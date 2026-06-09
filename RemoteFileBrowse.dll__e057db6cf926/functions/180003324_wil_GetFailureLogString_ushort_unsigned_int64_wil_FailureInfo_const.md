# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003324`
- end: `0x1800035da`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180004450`
- `0x180004a58`
- `0x180004cd8`
- `0x180004fa4`
- `0x180006a48`
- `0x180017600`
- `0x180017734`

## callees

- `0x180002030`
- `0x180002dc4`
- `0x180003324`
- `0x1800038d0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034d7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800034d7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003456`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003456`

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
          v7 = (const char *)&word_18001BF9A;
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
0x180003324  mov     [rsp+arg_18], rbx
0x180003329  push    rbp
0x18000332a  push    rsi
0x18000332b  push    rdi
0x18000332c  push    r14
0x18000332e  push    r15
0x180003330  sub     rsp, 250h
0x180003337  mov     rax, cs:__security_cookie
0x18000333e  xor     rax, rsp
0x180003341  mov     [rsp+278h+var_38], rax
0x180003349  mov     rbx, r8
0x18000334c  mov     rsi, rdx
0x18000334f  mov     r14, rcx
0x180003352  xor     r15d, r15d
0x180003355  test    rdx, rdx
0x180003358  jz      loc_1800035B1
0x18000335e  test    rcx, rcx
0x180003361  jz      loc_1800035B1
0x180003367  mov     [rcx], r15w
0x18000336b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003372  test    rax, rax
0x180003375  jz      short loc_180003398
0x180003377  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000337e  jz      short loc_180003398
0x180003380  mov     r8, rdx
0x180003383  mov     rdx, rcx
0x180003386  mov     rcx, rbx
0x180003389  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000338e  cmp     [r14], r15w
0x180003392  jnz     loc_1800035B1
0x180003398  mov     ecx, [rbx]
0x18000339a  mov     bpl, 8
0x18000339d  test    ecx, ecx
0x18000339f  jz      short loc_1800033EA
0x1800033a1  sub     ecx, 1
0x1800033a4  jz      short loc_1800033D2
0x1800033a6  sub     ecx, 1
0x1800033a9  jz      short loc_1800033C2
0x1800033ab  cmp     ecx, 1
0x1800033ae  jz      short loc_1800033B9
0x1800033b0  lea     rdi, word_18001BF9A
0x1800033b7  jmp     short loc_1800033F1
0x1800033b9  lea     rdi, aFailfast; "FailFast"
0x1800033c0  jmp     short loc_1800033F1
0x1800033c2  lea     rax, aLoghr; "LogHr"
0x1800033c9  lea     rdi, aLognt; "LogNt"
0x1800033d0  jmp     short loc_1800033E0
0x1800033d2  lea     rax, aReturnhr; "ReturnHr"
0x1800033d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800033e0  test    [rbx+4], bpl
0x1800033e4  cmovz   rdi, rax
0x1800033e8  jmp     short loc_1800033F1
0x1800033ea  lea     rdi, aException; "Exception"
0x1800033f1  xor     edx, edx; Val
0x1800033f3  mov     r8d, 200h; Size
0x1800033f9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800033fe  call    memset_0
0x180003403  test    [rbx+4], bpl
0x180003407  jz      short loc_18000342C
0x180003409  mov     ebp, [rbx+0Ch]
0x18000340c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003413  test    rax, rax
0x180003416  jz      short loc_18000345C
0x180003418  mov     r8d, 100h
0x18000341e  lea     rdx, [rsp+278h+Buffer]
0x180003423  mov     ecx, ebp
0x180003425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000342a  jmp     short loc_18000345C
0x18000342c  mov     ebp, [rbx+8]
0x18000342f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003434  mov     [rsp+278h+nSize], 100h; nSize
0x18000343c  lea     rax, [rsp+278h+Buffer]
0x180003441  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003446  mov     r9d, 400h; dwLanguageId
0x18000344c  mov     r8d, ebp; dwMessageId
0x18000344f  xor     edx, edx; lpSource
0x180003451  mov     ecx, 1200h; dwFlags
0x180003456  call    cs:__imp_FormatMessageW
0x18000345c  lea     rsi, [r14+rsi*2]
0x180003460  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003464  mov     rax, [rbx+88h]
0x18000346b  mov     rcx, [rbx+80h]
0x180003472  mov     rdx, rsi; unsigned __int16 *
0x180003475  test    r9, r9
0x180003478  jz      short loc_18000349C
0x18000347a  mov     [rsp+278h+Arguments], rax
0x18000347f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003484  mov     eax, [rbx+40h]
0x180003487  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000348b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003492  mov     rcx, r14; this
0x180003495  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000349a  jmp     short loc_1800034B3
0x18000349c  mov     [rsp+278h+lpBuffer], rax
0x1800034a1  mov     r9, rcx; unsigned __int16 *
0x1800034a4  lea     r8, aHsP; "%hs!%p: "
0x1800034ab  mov     rcx, r14; this
0x1800034ae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800034b3  mov     r14, rax
0x1800034b6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800034bd  test    r9, r9
0x1800034c0  jz      short loc_1800034D7
0x1800034c2  lea     r8, aCallerP; "(caller: %p) "
0x1800034c9  mov     rdx, rsi; unsigned __int16 *
0x1800034cc  mov     rcx, rax; this
0x1800034cf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800034d4  mov     r14, rax
0x1800034d7  call    cs:__imp_GetCurrentThreadId
0x1800034dd  lea     rcx, [rsp+278h+Buffer]
0x1800034e2  mov     [rsp+278h+var_240], rcx
0x1800034e7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800034eb  mov     [rsp+278h+nSize], eax
0x1800034ef  mov     eax, [rbx+44h]
0x1800034f2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800034f6  mov     r9, rdi; unsigned __int16 *
0x1800034f9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003500  mov     rdx, rsi; unsigned __int16 *
0x180003503  mov     rcx, r14; this
0x180003506  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000350b  cmp     [rbx+18h], r15
0x18000350f  jnz     short loc_180003521
0x180003511  cmp     [rbx+48h], r15
0x180003515  jnz     short loc_180003521
0x180003517  cmp     [rbx+30h], r15
0x18000351b  jz      loc_1800035B1
0x180003521  lea     r8, asc_18001C088; "    "
0x180003528  mov     rdx, rsi; unsigned __int16 *
0x18000352b  mov     rcx, rax; this
0x18000352e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003533  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003537  test    r9, r9
0x18000353a  jz      short loc_18000354E
0x18000353c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003543  mov     rdx, rsi; unsigned __int16 *
0x180003546  mov     rcx, rax; this
0x180003549  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000354e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003552  test    r9, r9
0x180003555  jz      short loc_180003569
0x180003557  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000355e  mov     rdx, rsi; unsigned __int16 *
0x180003561  mov     rcx, rax; this
0x180003564  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003569  mov     rcx, [rbx+28h]
0x18000356d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003571  mov     rdx, rsi; unsigned __int16 *
0x180003574  test    rcx, rcx
0x180003577  jz      short loc_18000358F
0x180003579  mov     [rsp+278h+lpBuffer], rcx
0x18000357e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003585  mov     rcx, rax; this
0x180003588  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000358d  jmp     short loc_1800035B1
0x18000358f  mov     rcx, rax; this
0x180003592  test    r9, r9
0x180003595  jz      short loc_1800035A5
0x180003597  lea     r8, aHs; "[%hs]\n"
0x18000359e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800035a3  jmp     short loc_1800035B1
0x1800035a5  lea     r8, asc_18001C100; "\n"
0x1800035ac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800035b1  xor     eax, eax
0x1800035b3  mov     rcx, [rsp+278h+var_38]
0x1800035bb  xor     rcx, rsp; StackCookie
0x1800035be  call    __security_check_cookie
0x1800035c3  mov     rbx, [rsp+278h+arg_18]
0x1800035cb  add     rsp, 250h
0x1800035d2  pop     r15
0x1800035d4  pop     r14
0x1800035d6  pop     rdi
0x1800035d7  pop     rsi
0x1800035d8  pop     rbp
0x1800035d9  retn
```
