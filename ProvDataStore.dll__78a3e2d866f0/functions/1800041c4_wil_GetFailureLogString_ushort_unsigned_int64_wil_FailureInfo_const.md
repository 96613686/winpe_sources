# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800041c4`
- end: `0x18000447a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a3c`
- `0x180002cbc`
- `0x180004be8`
- `0x180006890`
- `0x1800080b4`
- `0x18001141f`
- `0x180011553`

## callees

- `0x1800041c4`
- `0x180004ee8`
- `0x180010f4e`
- `0x180010f80`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004377`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004377`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800042f6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800042f6`

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
          v7 = (const char *)&dword_180013F94;
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
0x1800041c4  mov     [rsp+arg_18], rbx
0x1800041c9  push    rbp
0x1800041ca  push    rsi
0x1800041cb  push    rdi
0x1800041cc  push    r14
0x1800041ce  push    r15
0x1800041d0  sub     rsp, 250h
0x1800041d7  mov     rax, cs:__security_cookie
0x1800041de  xor     rax, rsp
0x1800041e1  mov     [rsp+278h+var_38], rax
0x1800041e9  mov     rbx, r8
0x1800041ec  mov     rsi, rdx
0x1800041ef  mov     r14, rcx
0x1800041f2  xor     r15d, r15d
0x1800041f5  test    rdx, rdx
0x1800041f8  jz      loc_180004451
0x1800041fe  test    rcx, rcx
0x180004201  jz      loc_180004451
0x180004207  mov     [rcx], r15w
0x18000420b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004212  test    rax, rax
0x180004215  jz      short loc_180004238
0x180004217  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000421e  jz      short loc_180004238
0x180004220  mov     r8, rdx
0x180004223  mov     rdx, rcx
0x180004226  mov     rcx, rbx
0x180004229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000422e  cmp     [r14], r15w
0x180004232  jnz     loc_180004451
0x180004238  mov     ecx, [rbx]
0x18000423a  mov     bpl, 8
0x18000423d  test    ecx, ecx
0x18000423f  jz      short loc_18000428A
0x180004241  sub     ecx, 1
0x180004244  jz      short loc_180004272
0x180004246  sub     ecx, 1
0x180004249  jz      short loc_180004262
0x18000424b  cmp     ecx, 1
0x18000424e  jz      short loc_180004259
0x180004250  lea     rdi, dword_180013F94
0x180004257  jmp     short loc_180004291
0x180004259  lea     rdi, aFailfast; "FailFast"
0x180004260  jmp     short loc_180004291
0x180004262  lea     rax, aLoghr; "LogHr"
0x180004269  lea     rdi, aLognt; "LogNt"
0x180004270  jmp     short loc_180004280
0x180004272  lea     rax, aReturnhr; "ReturnHr"
0x180004279  lea     rdi, aReturnnt; "ReturnNt"
0x180004280  test    [rbx+4], bpl
0x180004284  cmovz   rdi, rax
0x180004288  jmp     short loc_180004291
0x18000428a  lea     rdi, aException; "Exception"
0x180004291  xor     edx, edx; Val
0x180004293  mov     r8d, 200h; Size
0x180004299  lea     rcx, [rsp+278h+Buffer]; void *
0x18000429e  call    memset_0
0x1800042a3  test    [rbx+4], bpl
0x1800042a7  jz      short loc_1800042CC
0x1800042a9  mov     ebp, [rbx+0Ch]
0x1800042ac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800042b3  test    rax, rax
0x1800042b6  jz      short loc_1800042FC
0x1800042b8  mov     r8d, 100h
0x1800042be  lea     rdx, [rsp+278h+Buffer]
0x1800042c3  mov     ecx, ebp
0x1800042c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ca  jmp     short loc_1800042FC
0x1800042cc  mov     ebp, [rbx+8]
0x1800042cf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800042d4  mov     [rsp+278h+nSize], 100h; nSize
0x1800042dc  lea     rax, [rsp+278h+Buffer]
0x1800042e1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800042e6  mov     r9d, 400h; dwLanguageId
0x1800042ec  mov     r8d, ebp; dwMessageId
0x1800042ef  xor     edx, edx; lpSource
0x1800042f1  mov     ecx, 1200h; dwFlags
0x1800042f6  call    cs:__imp_FormatMessageW
0x1800042fc  lea     rsi, [r14+rsi*2]
0x180004300  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004304  mov     rax, [rbx+88h]
0x18000430b  mov     rcx, [rbx+80h]
0x180004312  mov     rdx, rsi; unsigned __int16 *
0x180004315  test    r9, r9
0x180004318  jz      short loc_18000433C
0x18000431a  mov     [rsp+278h+Arguments], rax
0x18000431f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004324  mov     eax, [rbx+40h]
0x180004327  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000432b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004332  mov     rcx, r14; this
0x180004335  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000433a  jmp     short loc_180004353
0x18000433c  mov     [rsp+278h+lpBuffer], rax
0x180004341  mov     r9, rcx; unsigned __int16 *
0x180004344  lea     r8, aHsP; "%hs!%p: "
0x18000434b  mov     rcx, r14; this
0x18000434e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004353  mov     r14, rax
0x180004356  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000435d  test    r9, r9
0x180004360  jz      short loc_180004377
0x180004362  lea     r8, aCallerP; "(caller: %p) "
0x180004369  mov     rdx, rsi; unsigned __int16 *
0x18000436c  mov     rcx, rax; this
0x18000436f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004374  mov     r14, rax
0x180004377  call    cs:__imp_GetCurrentThreadId
0x18000437d  lea     rcx, [rsp+278h+Buffer]
0x180004382  mov     [rsp+278h+var_240], rcx
0x180004387  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000438b  mov     [rsp+278h+nSize], eax
0x18000438f  mov     eax, [rbx+44h]
0x180004392  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004396  mov     r9, rdi; unsigned __int16 *
0x180004399  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800043a0  mov     rdx, rsi; unsigned __int16 *
0x1800043a3  mov     rcx, r14; this
0x1800043a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043ab  cmp     [rbx+18h], r15
0x1800043af  jnz     short loc_1800043C1
0x1800043b1  cmp     [rbx+48h], r15
0x1800043b5  jnz     short loc_1800043C1
0x1800043b7  cmp     [rbx+30h], r15
0x1800043bb  jz      loc_180004451
0x1800043c1  lea     r8, asc_180014080; "    "
0x1800043c8  mov     rdx, rsi; unsigned __int16 *
0x1800043cb  mov     rcx, rax; this
0x1800043ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043d3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800043d7  test    r9, r9
0x1800043da  jz      short loc_1800043EE
0x1800043dc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800043e3  mov     rdx, rsi; unsigned __int16 *
0x1800043e6  mov     rcx, rax; this
0x1800043e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800043ee  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800043f2  test    r9, r9
0x1800043f5  jz      short loc_180004409
0x1800043f7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800043fe  mov     rdx, rsi; unsigned __int16 *
0x180004401  mov     rcx, rax; this
0x180004404  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004409  mov     rcx, [rbx+28h]
0x18000440d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004411  mov     rdx, rsi; unsigned __int16 *
0x180004414  test    rcx, rcx
0x180004417  jz      short loc_18000442F
0x180004419  mov     [rsp+278h+lpBuffer], rcx
0x18000441e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004425  mov     rcx, rax; this
0x180004428  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000442d  jmp     short loc_180004451
0x18000442f  mov     rcx, rax; this
0x180004432  test    r9, r9
0x180004435  jz      short loc_180004445
0x180004437  lea     r8, aHs; "[%hs]\n"
0x18000443e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004443  jmp     short loc_180004451
0x180004445  lea     r8, asc_1800140F8; "\n"
0x18000444c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004451  xor     eax, eax
0x180004453  mov     rcx, [rsp+278h+var_38]
0x18000445b  xor     rcx, rsp; StackCookie
0x18000445e  call    __security_check_cookie
0x180004463  mov     rbx, [rsp+278h+arg_18]
0x18000446b  add     rsp, 250h
0x180004472  pop     r15
0x180004474  pop     r14
0x180004476  pop     rdi
0x180004477  pop     rsi
0x180004478  pop     rbp
0x180004479  retn
```
