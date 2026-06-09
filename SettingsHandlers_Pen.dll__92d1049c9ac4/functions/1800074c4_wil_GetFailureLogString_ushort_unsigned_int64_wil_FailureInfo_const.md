# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800074c4`
- end: `0x18000777a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005218`
- `0x1800083f8`
- `0x180008b34`
- `0x18000bfd0`

## callees

- `0x1800030e0`
- `0x180003c64`
- `0x1800074c4`
- `0x1800086f8`
- `0x18005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007677`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007677`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800075f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800075f6`

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
          v7 = (const char *)&word_180065FB2;
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
0x1800074c4  mov     [rsp+arg_18], rbx
0x1800074c9  push    rbp
0x1800074ca  push    rsi
0x1800074cb  push    rdi
0x1800074cc  push    r14
0x1800074ce  push    r15
0x1800074d0  sub     rsp, 250h
0x1800074d7  mov     rax, cs:__security_cookie
0x1800074de  xor     rax, rsp
0x1800074e1  mov     [rsp+278h+var_38], rax
0x1800074e9  mov     rbx, r8
0x1800074ec  mov     rsi, rdx
0x1800074ef  mov     r14, rcx
0x1800074f2  xor     r15d, r15d
0x1800074f5  test    rdx, rdx
0x1800074f8  jz      loc_180007751
0x1800074fe  test    rcx, rcx
0x180007501  jz      loc_180007751
0x180007507  mov     [rcx], r15w
0x18000750b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007512  test    rax, rax
0x180007515  jz      short loc_180007538
0x180007517  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000751e  jz      short loc_180007538
0x180007520  mov     r8, rdx
0x180007523  mov     rdx, rcx
0x180007526  mov     rcx, rbx
0x180007529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752e  cmp     [r14], r15w
0x180007532  jnz     loc_180007751
0x180007538  mov     ecx, [rbx]
0x18000753a  mov     bpl, 8
0x18000753d  test    ecx, ecx
0x18000753f  jz      short loc_18000758A
0x180007541  sub     ecx, 1
0x180007544  jz      short loc_180007572
0x180007546  sub     ecx, 1
0x180007549  jz      short loc_180007562
0x18000754b  cmp     ecx, 1
0x18000754e  jz      short loc_180007559
0x180007550  lea     rdi, word_180065FB2
0x180007557  jmp     short loc_180007591
0x180007559  lea     rdi, aFailfast; "FailFast"
0x180007560  jmp     short loc_180007591
0x180007562  lea     rax, aLoghr; "LogHr"
0x180007569  lea     rdi, aLognt; "LogNt"
0x180007570  jmp     short loc_180007580
0x180007572  lea     rax, aReturnhr; "ReturnHr"
0x180007579  lea     rdi, aReturnnt; "ReturnNt"
0x180007580  test    [rbx+4], bpl
0x180007584  cmovz   rdi, rax
0x180007588  jmp     short loc_180007591
0x18000758a  lea     rdi, aException; "Exception"
0x180007591  xor     edx, edx; Val
0x180007593  mov     r8d, 200h; Size
0x180007599  lea     rcx, [rsp+278h+Buffer]; void *
0x18000759e  call    memset_0
0x1800075a3  test    [rbx+4], bpl
0x1800075a7  jz      short loc_1800075CC
0x1800075a9  mov     ebp, [rbx+0Ch]
0x1800075ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800075b3  test    rax, rax
0x1800075b6  jz      short loc_1800075FC
0x1800075b8  mov     r8d, 100h
0x1800075be  lea     rdx, [rsp+278h+Buffer]
0x1800075c3  mov     ecx, ebp
0x1800075c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800075ca  jmp     short loc_1800075FC
0x1800075cc  mov     ebp, [rbx+8]
0x1800075cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800075d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800075dc  lea     rax, [rsp+278h+Buffer]
0x1800075e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800075e6  mov     r9d, 400h; dwLanguageId
0x1800075ec  mov     r8d, ebp; dwMessageId
0x1800075ef  xor     edx, edx; lpSource
0x1800075f1  mov     ecx, 1200h; dwFlags
0x1800075f6  call    cs:__imp_FormatMessageW
0x1800075fc  lea     rsi, [r14+rsi*2]
0x180007600  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007604  mov     rax, [rbx+88h]
0x18000760b  mov     rcx, [rbx+80h]
0x180007612  mov     rdx, rsi; unsigned __int16 *
0x180007615  test    r9, r9
0x180007618  jz      short loc_18000763C
0x18000761a  mov     [rsp+278h+Arguments], rax
0x18000761f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007624  mov     eax, [rbx+40h]
0x180007627  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000762b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007632  mov     rcx, r14; this
0x180007635  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000763a  jmp     short loc_180007653
0x18000763c  mov     [rsp+278h+lpBuffer], rax
0x180007641  mov     r9, rcx; unsigned __int16 *
0x180007644  lea     r8, aHsP; "%hs!%p: "
0x18000764b  mov     rcx, r14; this
0x18000764e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007653  mov     r14, rax
0x180007656  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000765d  test    r9, r9
0x180007660  jz      short loc_180007677
0x180007662  lea     r8, aCallerP; "(caller: %p) "
0x180007669  mov     rdx, rsi; unsigned __int16 *
0x18000766c  mov     rcx, rax; this
0x18000766f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007674  mov     r14, rax
0x180007677  call    cs:__imp_GetCurrentThreadId
0x18000767d  lea     rcx, [rsp+278h+Buffer]
0x180007682  mov     [rsp+278h+var_240], rcx
0x180007687  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000768b  mov     [rsp+278h+nSize], eax
0x18000768f  mov     eax, [rbx+44h]
0x180007692  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007696  mov     r9, rdi; unsigned __int16 *
0x180007699  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800076a0  mov     rdx, rsi; unsigned __int16 *
0x1800076a3  mov     rcx, r14; this
0x1800076a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076ab  cmp     [rbx+18h], r15
0x1800076af  jnz     short loc_1800076C1
0x1800076b1  cmp     [rbx+48h], r15
0x1800076b5  jnz     short loc_1800076C1
0x1800076b7  cmp     [rbx+30h], r15
0x1800076bb  jz      loc_180007751
0x1800076c1  lea     r8, asc_1800660A0; "    "
0x1800076c8  mov     rdx, rsi; unsigned __int16 *
0x1800076cb  mov     rcx, rax; this
0x1800076ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800076d7  test    r9, r9
0x1800076da  jz      short loc_1800076EE
0x1800076dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800076e3  mov     rdx, rsi; unsigned __int16 *
0x1800076e6  mov     rcx, rax; this
0x1800076e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800076ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800076f2  test    r9, r9
0x1800076f5  jz      short loc_180007709
0x1800076f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800076fe  mov     rdx, rsi; unsigned __int16 *
0x180007701  mov     rcx, rax; this
0x180007704  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007709  mov     rcx, [rbx+28h]
0x18000770d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007711  mov     rdx, rsi; unsigned __int16 *
0x180007714  test    rcx, rcx
0x180007717  jz      short loc_18000772F
0x180007719  mov     [rsp+278h+lpBuffer], rcx
0x18000771e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007725  mov     rcx, rax; this
0x180007728  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000772d  jmp     short loc_180007751
0x18000772f  mov     rcx, rax; this
0x180007732  test    r9, r9
0x180007735  jz      short loc_180007745
0x180007737  lea     r8, aHs; "[%hs]\n"
0x18000773e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007743  jmp     short loc_180007751
0x180007745  lea     r8, asc_180066118; "\n"
0x18000774c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007751  xor     eax, eax
0x180007753  mov     rcx, [rsp+278h+var_38]
0x18000775b  xor     rcx, rsp; StackCookie
0x18000775e  call    __security_check_cookie
0x180007763  mov     rbx, [rsp+278h+arg_18]
0x18000776b  add     rsp, 250h
0x180007772  pop     r15
0x180007774  pop     r14
0x180007776  pop     rdi
0x180007777  pop     rsi
0x180007778  pop     rbp
0x180007779  retn
```
