# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002f4d4`
- end: `0x18002f797`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001a46c`
- `0x180030020`
- `0x180031df0`

## callees

- `0x18002c640`
- `0x18002d518`
- `0x18002f4d4`
- `0x18002fcfc`
- `0x180080010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f68d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002f68d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f606`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002f606`

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
          v7 = word_1800912AA;
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
0x18002f4d4  mov     [rsp+arg_18], rbx
0x18002f4d9  push    rbp
0x18002f4da  push    rsi
0x18002f4db  push    rdi
0x18002f4dc  push    r14
0x18002f4de  push    r15
0x18002f4e0  sub     rsp, 250h
0x18002f4e7  mov     rax, cs:__security_cookie
0x18002f4ee  xor     rax, rsp
0x18002f4f1  mov     [rsp+278h+var_38], rax
0x18002f4f9  mov     rbx, r8
0x18002f4fc  mov     rsi, rdx
0x18002f4ff  mov     r14, rcx
0x18002f502  xor     r15d, r15d
0x18002f505  test    rdx, rdx
0x18002f508  jz      loc_18002F76D
0x18002f50e  test    rcx, rcx
0x18002f511  jz      loc_18002F76D
0x18002f517  mov     [rcx], r15w
0x18002f51b  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f522  test    rax, rax
0x18002f525  jz      short loc_18002F548
0x18002f527  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002f52e  jz      short loc_18002F548
0x18002f530  mov     r8, rdx
0x18002f533  mov     rdx, rcx
0x18002f536  mov     rcx, rbx
0x18002f539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f53e  cmp     [r14], r15w
0x18002f542  jnz     loc_18002F76D
0x18002f548  mov     ecx, [rbx]
0x18002f54a  mov     bpl, 8
0x18002f54d  test    ecx, ecx
0x18002f54f  jz      short loc_18002F59A
0x18002f551  sub     ecx, 1
0x18002f554  jz      short loc_18002F582
0x18002f556  sub     ecx, 1
0x18002f559  jz      short loc_18002F572
0x18002f55b  cmp     ecx, 1
0x18002f55e  jz      short loc_18002F569
0x18002f560  lea     rdi, word_1800912AA
0x18002f567  jmp     short loc_18002F5A1
0x18002f569  lea     rdi, aFailfast; "FailFast"
0x18002f570  jmp     short loc_18002F5A1
0x18002f572  lea     rax, aLoghr; "LogHr"
0x18002f579  lea     rdi, aLognt; "LogNt"
0x18002f580  jmp     short loc_18002F590
0x18002f582  lea     rax, aReturnhr; "ReturnHr"
0x18002f589  lea     rdi, aReturnnt; "ReturnNt"
0x18002f590  test    [rbx+4], bpl
0x18002f594  cmovz   rdi, rax
0x18002f598  jmp     short loc_18002F5A1
0x18002f59a  lea     rdi, aException; "Exception"
0x18002f5a1  xor     edx, edx; Val
0x18002f5a3  mov     r8d, 200h; Size
0x18002f5a9  lea     rcx, [rsp+278h+Buffer]; void *
0x18002f5ae  call    memset_0
0x18002f5b3  test    [rbx+4], bpl
0x18002f5b7  jz      short loc_18002F5DC
0x18002f5b9  mov     ebp, [rbx+0Ch]
0x18002f5bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002f5c3  test    rax, rax
0x18002f5c6  jz      short loc_18002F612
0x18002f5c8  mov     r8d, 100h
0x18002f5ce  lea     rdx, [rsp+278h+Buffer]
0x18002f5d3  mov     ecx, ebp
0x18002f5d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f5da  jmp     short loc_18002F612
0x18002f5dc  mov     ebp, [rbx+8]
0x18002f5df  mov     [rsp+278h+Arguments], r15; Arguments
0x18002f5e4  mov     [rsp+278h+nSize], 100h; nSize
0x18002f5ec  lea     rax, [rsp+278h+Buffer]
0x18002f5f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002f5f6  mov     r9d, 400h; dwLanguageId
0x18002f5fc  mov     r8d, ebp; dwMessageId
0x18002f5ff  xor     edx, edx; lpSource
0x18002f601  mov     ecx, 1200h; dwFlags
0x18002f606  call    cs:__imp_FormatMessageW
0x18002f60d  nop     dword ptr [rax+rax+00h]
0x18002f612  lea     rsi, [r14+rsi*2]
0x18002f616  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002f61a  mov     rax, [rbx+88h]
0x18002f621  mov     rcx, [rbx+80h]
0x18002f628  mov     rdx, rsi; unsigned __int16 *
0x18002f62b  test    r9, r9
0x18002f62e  jz      short loc_18002F652
0x18002f630  mov     [rsp+278h+Arguments], rax
0x18002f635  mov     qword ptr [rsp+278h+nSize], rcx
0x18002f63a  mov     eax, [rbx+40h]
0x18002f63d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002f641  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18002f648  mov     rcx, r14; this
0x18002f64b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f650  jmp     short loc_18002F669
0x18002f652  mov     [rsp+278h+lpBuffer], rax
0x18002f657  mov     r9, rcx; unsigned __int16 *
0x18002f65a  lea     r8, aHsP; "%hs!%p: "
0x18002f661  mov     rcx, r14; this
0x18002f664  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f669  mov     r14, rax
0x18002f66c  mov     r9, [rbx+90h]; unsigned __int16 *
0x18002f673  test    r9, r9
0x18002f676  jz      short loc_18002F68D
0x18002f678  lea     r8, aCallerP; "(caller: %p) "
0x18002f67f  mov     rdx, rsi; unsigned __int16 *
0x18002f682  mov     rcx, rax; this
0x18002f685  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f68a  mov     r14, rax
0x18002f68d  call    cs:__imp_GetCurrentThreadId
0x18002f694  nop     dword ptr [rax+rax+00h]
0x18002f699  lea     rcx, [rsp+278h+Buffer]
0x18002f69e  mov     [rsp+278h+var_240], rcx
0x18002f6a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x18002f6a7  mov     [rsp+278h+nSize], eax
0x18002f6ab  mov     eax, [rbx+44h]
0x18002f6ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18002f6b2  mov     r9, rdi; unsigned __int16 *
0x18002f6b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18002f6bc  mov     rdx, rsi; unsigned __int16 *
0x18002f6bf  mov     rcx, r14; this
0x18002f6c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f6c7  cmp     [rbx+18h], r15
0x18002f6cb  jnz     short loc_18002F6DD
0x18002f6cd  cmp     [rbx+48h], r15
0x18002f6d1  jnz     short loc_18002F6DD
0x18002f6d3  cmp     [rbx+30h], r15
0x18002f6d7  jz      loc_18002F76D
0x18002f6dd  lea     r8, asc_180092620; "    "
0x18002f6e4  mov     rdx, rsi; unsigned __int16 *
0x18002f6e7  mov     rcx, rax; this
0x18002f6ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f6ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x18002f6f3  test    r9, r9
0x18002f6f6  jz      short loc_18002F70A
0x18002f6f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x18002f6ff  mov     rdx, rsi; unsigned __int16 *
0x18002f702  mov     rcx, rax; this
0x18002f705  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f70a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18002f70e  test    r9, r9
0x18002f711  jz      short loc_18002F725
0x18002f713  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18002f71a  mov     rdx, rsi; unsigned __int16 *
0x18002f71d  mov     rcx, rax; this
0x18002f720  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f725  mov     rcx, [rbx+28h]
0x18002f729  mov     r9, [rbx+30h]; unsigned __int16 *
0x18002f72d  mov     rdx, rsi; unsigned __int16 *
0x18002f730  test    rcx, rcx
0x18002f733  jz      short loc_18002F74B
0x18002f735  mov     [rsp+278h+lpBuffer], rcx
0x18002f73a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18002f741  mov     rcx, rax; this
0x18002f744  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f749  jmp     short loc_18002F76D
0x18002f74b  mov     rcx, rax; this
0x18002f74e  test    r9, r9
0x18002f751  jz      short loc_18002F761
0x18002f753  lea     r8, aHs; "[%hs]\n"
0x18002f75a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f75f  jmp     short loc_18002F76D
0x18002f761  lea     r8, asc_180092698; "\n"
0x18002f768  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18002f76d  xor     eax, eax
0x18002f76f  mov     rcx, [rsp+278h+var_38]
0x18002f777  xor     rcx, rsp; StackCookie
0x18002f77a  call    __security_check_cookie
0x18002f77f  mov     rbx, [rsp+278h+arg_18]
0x18002f787  add     rsp, 250h
0x18002f78e  pop     r15
0x18002f790  pop     r14
0x18002f792  pop     rdi
0x18002f793  pop     rsi
0x18002f794  pop     rbp
0x18002f795  retn
```
