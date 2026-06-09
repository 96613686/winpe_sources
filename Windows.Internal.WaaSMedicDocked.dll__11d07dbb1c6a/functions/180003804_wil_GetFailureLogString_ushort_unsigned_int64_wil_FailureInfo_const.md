# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003804`
- end: `0x180003aba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000240c`
- `0x180002674`
- `0x180004168`
- `0x1800057f0`

## callees

- `0x180001570`
- `0x180001fde`
- `0x180003804`
- `0x180004468`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800039b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003936`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003936`

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
          v7 = (const char *)&qword_18000EEA8;
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
0x180003804  mov     [rsp+arg_18], rbx
0x180003809  push    rbp
0x18000380a  push    rsi
0x18000380b  push    rdi
0x18000380c  push    r14
0x18000380e  push    r15
0x180003810  sub     rsp, 250h
0x180003817  mov     rax, cs:__security_cookie
0x18000381e  xor     rax, rsp
0x180003821  mov     [rsp+278h+var_38], rax
0x180003829  mov     rbx, r8
0x18000382c  mov     rsi, rdx
0x18000382f  mov     r14, rcx
0x180003832  xor     r15d, r15d
0x180003835  test    rdx, rdx
0x180003838  jz      loc_180003A91
0x18000383e  test    rcx, rcx
0x180003841  jz      loc_180003A91
0x180003847  mov     [rcx], r15w
0x18000384b  mov     rax, cs:g_pfnResultLoggingCallback
0x180003852  test    rax, rax
0x180003855  jz      short loc_180003878
0x180003857  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000385e  jz      short loc_180003878
0x180003860  mov     r8, rdx
0x180003863  mov     rdx, rcx
0x180003866  mov     rcx, rbx
0x180003869  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000386e  cmp     [r14], r15w
0x180003872  jnz     loc_180003A91
0x180003878  mov     ecx, [rbx]
0x18000387a  mov     bpl, 8
0x18000387d  test    ecx, ecx
0x18000387f  jz      short loc_1800038CA
0x180003881  sub     ecx, 1
0x180003884  jz      short loc_1800038B2
0x180003886  sub     ecx, 1
0x180003889  jz      short loc_1800038A2
0x18000388b  cmp     ecx, 1
0x18000388e  jz      short loc_180003899
0x180003890  lea     rdi, qword_18000EEA8
0x180003897  jmp     short loc_1800038D1
0x180003899  lea     rdi, aFailfast; "FailFast"
0x1800038a0  jmp     short loc_1800038D1
0x1800038a2  lea     rax, aLoghr; "LogHr"
0x1800038a9  lea     rdi, aLognt; "LogNt"
0x1800038b0  jmp     short loc_1800038C0
0x1800038b2  lea     rax, aReturnhr; "ReturnHr"
0x1800038b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800038c0  test    [rbx+4], bpl
0x1800038c4  cmovz   rdi, rax
0x1800038c8  jmp     short loc_1800038D1
0x1800038ca  lea     rdi, aException; "Exception"
0x1800038d1  xor     edx, edx; Val
0x1800038d3  mov     r8d, 200h; Size
0x1800038d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800038de  call    memset_0
0x1800038e3  test    [rbx+4], bpl
0x1800038e7  jz      short loc_18000390C
0x1800038e9  mov     ebp, [rbx+0Ch]
0x1800038ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800038f3  test    rax, rax
0x1800038f6  jz      short loc_18000393C
0x1800038f8  mov     r8d, 100h
0x1800038fe  lea     rdx, [rsp+278h+Buffer]
0x180003903  mov     ecx, ebp
0x180003905  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000390a  jmp     short loc_18000393C
0x18000390c  mov     ebp, [rbx+8]
0x18000390f  mov     [rsp+278h+Arguments], r15; Arguments
0x180003914  mov     [rsp+278h+nSize], 100h; nSize
0x18000391c  lea     rax, [rsp+278h+Buffer]
0x180003921  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003926  mov     r9d, 400h; dwLanguageId
0x18000392c  mov     r8d, ebp; dwMessageId
0x18000392f  xor     edx, edx; lpSource
0x180003931  mov     ecx, 1200h; dwFlags
0x180003936  call    cs:__imp_FormatMessageW
0x18000393c  lea     rsi, [r14+rsi*2]
0x180003940  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003944  mov     rax, [rbx+88h]
0x18000394b  mov     rcx, [rbx+80h]
0x180003952  mov     rdx, rsi; unsigned __int16 *
0x180003955  test    r9, r9
0x180003958  jz      short loc_18000397C
0x18000395a  mov     [rsp+278h+Arguments], rax
0x18000395f  mov     qword ptr [rsp+278h+nSize], rcx
0x180003964  mov     eax, [rbx+40h]
0x180003967  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000396b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003972  mov     rcx, r14; this
0x180003975  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000397a  jmp     short loc_180003993
0x18000397c  mov     [rsp+278h+lpBuffer], rax
0x180003981  mov     r9, rcx; unsigned __int16 *
0x180003984  lea     r8, aHsP; "%hs!%p: "
0x18000398b  mov     rcx, r14; this
0x18000398e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003993  mov     r14, rax
0x180003996  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000399d  test    r9, r9
0x1800039a0  jz      short loc_1800039B7
0x1800039a2  lea     r8, aCallerP; "(caller: %p) "
0x1800039a9  mov     rdx, rsi; unsigned __int16 *
0x1800039ac  mov     rcx, rax; this
0x1800039af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039b4  mov     r14, rax
0x1800039b7  call    cs:__imp_GetCurrentThreadId
0x1800039bd  lea     rcx, [rsp+278h+Buffer]
0x1800039c2  mov     [rsp+278h+var_240], rcx
0x1800039c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800039cb  mov     [rsp+278h+nSize], eax
0x1800039cf  mov     eax, [rbx+44h]
0x1800039d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800039d6  mov     r9, rdi; unsigned __int16 *
0x1800039d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800039e0  mov     rdx, rsi; unsigned __int16 *
0x1800039e3  mov     rcx, r14; this
0x1800039e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800039eb  cmp     [rbx+18h], r15
0x1800039ef  jnz     short loc_180003A01
0x1800039f1  cmp     [rbx+48h], r15
0x1800039f5  jnz     short loc_180003A01
0x1800039f7  cmp     [rbx+30h], r15
0x1800039fb  jz      loc_180003A91
0x180003a01  lea     r8, asc_18000EFB0; "    "
0x180003a08  mov     rdx, rsi; unsigned __int16 *
0x180003a0b  mov     rcx, rax; this
0x180003a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a13  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003a17  test    r9, r9
0x180003a1a  jz      short loc_180003A2E
0x180003a1c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003a23  mov     rdx, rsi; unsigned __int16 *
0x180003a26  mov     rcx, rax; this
0x180003a29  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a2e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003a32  test    r9, r9
0x180003a35  jz      short loc_180003A49
0x180003a37  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003a3e  mov     rdx, rsi; unsigned __int16 *
0x180003a41  mov     rcx, rax; this
0x180003a44  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a49  mov     rcx, [rbx+28h]
0x180003a4d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003a51  mov     rdx, rsi; unsigned __int16 *
0x180003a54  test    rcx, rcx
0x180003a57  jz      short loc_180003A6F
0x180003a59  mov     [rsp+278h+lpBuffer], rcx
0x180003a5e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003a65  mov     rcx, rax; this
0x180003a68  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a6d  jmp     short loc_180003A91
0x180003a6f  mov     rcx, rax; this
0x180003a72  test    r9, r9
0x180003a75  jz      short loc_180003A85
0x180003a77  lea     r8, aHs; "[%hs]\n"
0x180003a7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a83  jmp     short loc_180003A91
0x180003a85  lea     r8, asc_18000F028; "\n"
0x180003a8c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a91  xor     eax, eax
0x180003a93  mov     rcx, [rsp+278h+var_38]
0x180003a9b  xor     rcx, rsp; StackCookie
0x180003a9e  call    __security_check_cookie
0x180003aa3  mov     rbx, [rsp+278h+arg_18]
0x180003aab  add     rsp, 250h
0x180003ab2  pop     r15
0x180003ab4  pop     r14
0x180003ab6  pop     rdi
0x180003ab7  pop     rsi
0x180003ab8  pop     rbp
0x180003ab9  retn
```
