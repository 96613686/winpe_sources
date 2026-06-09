# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008254`
- end: `0x18000850a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `9`
- callee_count: `5`
- tags: ``

## callers

- `0x180006910`
- `0x180006b90`
- `0x180008d5c`
- `0x18000ac70`
- `0x18002a138`
- `0x1800609d4`
- `0x180060b08`
- `0x1800616a8`
- `0x180061a9b`

## callees

- `0x180003bb0`
- `0x180004708`
- `0x180008254`
- `0x18000905c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008407`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008407`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008386`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008386`

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
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = (const char *)&qword_180067AD0;
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
0x180008254  mov     [rsp+arg_18], rbx
0x180008259  push    rbp
0x18000825a  push    rsi
0x18000825b  push    rdi
0x18000825c  push    r14
0x18000825e  push    r15
0x180008260  sub     rsp, 250h
0x180008267  mov     rax, cs:__security_cookie
0x18000826e  xor     rax, rsp
0x180008271  mov     [rsp+278h+var_38], rax
0x180008279  mov     rbx, r8
0x18000827c  mov     rsi, rdx
0x18000827f  mov     r14, rcx
0x180008282  xor     r15d, r15d
0x180008285  test    rdx, rdx
0x180008288  jz      loc_1800084E1
0x18000828e  test    rcx, rcx
0x180008291  jz      loc_1800084E1
0x180008297  mov     [rcx], r15w
0x18000829b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800082a2  test    rax, rax
0x1800082a5  jz      short loc_1800082C8
0x1800082a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800082ae  jz      short loc_1800082C8
0x1800082b0  mov     r8, rdx
0x1800082b3  mov     rdx, rcx
0x1800082b6  mov     rcx, rbx
0x1800082b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082be  cmp     [r14], r15w
0x1800082c2  jnz     loc_1800084E1
0x1800082c8  mov     ecx, [rbx]
0x1800082ca  mov     bpl, 8
0x1800082cd  test    ecx, ecx
0x1800082cf  jz      short loc_18000831A
0x1800082d1  sub     ecx, 1
0x1800082d4  jz      short loc_180008302
0x1800082d6  sub     ecx, 1
0x1800082d9  jz      short loc_1800082F2
0x1800082db  cmp     ecx, 1
0x1800082de  jz      short loc_1800082E9
0x1800082e0  lea     rdi, qword_180067AD0
0x1800082e7  jmp     short loc_180008321
0x1800082e9  lea     rdi, aFailfast; "FailFast"
0x1800082f0  jmp     short loc_180008321
0x1800082f2  lea     rax, aLoghr; "LogHr"
0x1800082f9  lea     rdi, aLognt; "LogNt"
0x180008300  jmp     short loc_180008310
0x180008302  lea     rax, aReturnhr; "ReturnHr"
0x180008309  lea     rdi, aReturnnt; "ReturnNt"
0x180008310  test    [rbx+4], bpl
0x180008314  cmovz   rdi, rax
0x180008318  jmp     short loc_180008321
0x18000831a  lea     rdi, aException; "Exception"
0x180008321  xor     edx, edx; Val
0x180008323  mov     r8d, 200h; Size
0x180008329  lea     rcx, [rsp+278h+Buffer]; void *
0x18000832e  call    memset_0
0x180008333  test    [rbx+4], bpl
0x180008337  jz      short loc_18000835C
0x180008339  mov     ebp, [rbx+0Ch]
0x18000833c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008343  test    rax, rax
0x180008346  jz      short loc_18000838C
0x180008348  mov     r8d, 100h
0x18000834e  lea     rdx, [rsp+278h+Buffer]
0x180008353  mov     ecx, ebp
0x180008355  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000835a  jmp     short loc_18000838C
0x18000835c  mov     ebp, [rbx+8]
0x18000835f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008364  mov     [rsp+278h+nSize], 100h; nSize
0x18000836c  lea     rax, [rsp+278h+Buffer]
0x180008371  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008376  mov     r9d, 400h; dwLanguageId
0x18000837c  mov     r8d, ebp; dwMessageId
0x18000837f  xor     edx, edx; lpSource
0x180008381  mov     ecx, 1200h; dwFlags
0x180008386  call    cs:__imp_FormatMessageW
0x18000838c  lea     rsi, [r14+rsi*2]
0x180008390  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008394  mov     rax, [rbx+88h]
0x18000839b  mov     rcx, [rbx+80h]
0x1800083a2  mov     rdx, rsi; unsigned __int16 *
0x1800083a5  test    r9, r9
0x1800083a8  jz      short loc_1800083CC
0x1800083aa  mov     [rsp+278h+Arguments], rax
0x1800083af  mov     qword ptr [rsp+278h+nSize], rcx
0x1800083b4  mov     eax, [rbx+40h]
0x1800083b7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800083bb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800083c2  mov     rcx, r14; this
0x1800083c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800083ca  jmp     short loc_1800083E3
0x1800083cc  mov     [rsp+278h+lpBuffer], rax
0x1800083d1  mov     r9, rcx; unsigned __int16 *
0x1800083d4  lea     r8, aHsP; "%hs!%p: "
0x1800083db  mov     rcx, r14; this
0x1800083de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800083e3  mov     r14, rax
0x1800083e6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800083ed  test    r9, r9
0x1800083f0  jz      short loc_180008407
0x1800083f2  lea     r8, aCallerP; "(caller: %p) "
0x1800083f9  mov     rdx, rsi; unsigned __int16 *
0x1800083fc  mov     rcx, rax; this
0x1800083ff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008404  mov     r14, rax
0x180008407  call    cs:__imp_GetCurrentThreadId
0x18000840d  lea     rcx, [rsp+278h+Buffer]
0x180008412  mov     [rsp+278h+var_240], rcx
0x180008417  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000841b  mov     [rsp+278h+nSize], eax
0x18000841f  mov     eax, [rbx+44h]
0x180008422  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008426  mov     r9, rdi; unsigned __int16 *
0x180008429  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008430  mov     rdx, rsi; unsigned __int16 *
0x180008433  mov     rcx, r14; this
0x180008436  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000843b  cmp     [rbx+18h], r15
0x18000843f  jnz     short loc_180008451
0x180008441  cmp     [rbx+48h], r15
0x180008445  jnz     short loc_180008451
0x180008447  cmp     [rbx+30h], r15
0x18000844b  jz      loc_1800084E1
0x180008451  lea     r8, asc_180067BC0; "    "
0x180008458  mov     rdx, rsi; unsigned __int16 *
0x18000845b  mov     rcx, rax; this
0x18000845e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008463  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008467  test    r9, r9
0x18000846a  jz      short loc_18000847E
0x18000846c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008473  mov     rdx, rsi; unsigned __int16 *
0x180008476  mov     rcx, rax; this
0x180008479  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000847e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008482  test    r9, r9
0x180008485  jz      short loc_180008499
0x180008487  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000848e  mov     rdx, rsi; unsigned __int16 *
0x180008491  mov     rcx, rax; this
0x180008494  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008499  mov     rcx, [rbx+28h]
0x18000849d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800084a1  mov     rdx, rsi; unsigned __int16 *
0x1800084a4  test    rcx, rcx
0x1800084a7  jz      short loc_1800084BF
0x1800084a9  mov     [rsp+278h+lpBuffer], rcx
0x1800084ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800084b5  mov     rcx, rax; this
0x1800084b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800084bd  jmp     short loc_1800084E1
0x1800084bf  mov     rcx, rax; this
0x1800084c2  test    r9, r9
0x1800084c5  jz      short loc_1800084D5
0x1800084c7  lea     r8, aHs; "[%hs]\n"
0x1800084ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800084d3  jmp     short loc_1800084E1
0x1800084d5  lea     r8, asc_180067C38; "\n"
0x1800084dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800084e1  xor     eax, eax
0x1800084e3  mov     rcx, [rsp+278h+var_38]
0x1800084eb  xor     rcx, rsp; StackCookie
0x1800084ee  call    __security_check_cookie
0x1800084f3  mov     rbx, [rsp+278h+arg_18]
0x1800084fb  add     rsp, 250h
0x180008502  pop     r15
0x180008504  pop     r14
0x180008506  pop     rdi
0x180008507  pop     rsi
0x180008508  pop     rbp
0x180008509  retn
```
