# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180077204`
- end: `0x1800774ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18007542c`
- `0x180075694`
- `0x180077f80`

## callees

- `0x180077204`
- `0x180078280`
- `0x18009110a`
- `0x180091140`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800773b7`
- `KERNEL32!GetCurrentThreadId` at `0x1800773b7`
- `KERNEL32!FormatMessageW` at `0x180077336`
- `KERNEL32!FormatMessageW` at `0x180077336`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  void (__fastcall *v7)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *); // rax
  const char *v8; // rdi
  const char *v9; // rax
  DWORD v10; // ebp
  const unsigned __int16 *v11; // r9
  unsigned __int16 *v12; // rsi
  __int64 v13; // rax
  unsigned __int16 *v14; // rax
  const unsigned __int16 *v15; // r9
  wil::details *v16; // r14
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
  v7 = (void (__fastcall *)(__int64, wil *, unsigned __int16 *, const struct wil::FailureInfo *))g_pfnResultLoggingCallback;
  *(_WORD *)this = 0;
  if ( v7 )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      v7(a3, this, a2, a4);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v9 = "ReturnHr";
      v8 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v8 = "FailFast";
        else
          v8 = (const char *)&word_18009982E;
        goto LABEL_18;
      }
      v9 = "LogHr";
      v8 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v8 = v9;
    goto LABEL_18;
  }
  v8 = "Exception";
LABEL_18:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v10 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v10, Buffer, 0x100u);
  }
  else
  {
    v10 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v10, 0x400u, Buffer, 0x100u, 0);
  }
  v11 = *(const unsigned __int16 **)(a3 + 56);
  v12 = (unsigned __int16 *)((char *)this + 2 * (_QWORD)a2);
  v13 = *(_QWORD *)(a3 + 136);
  if ( v11 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs(%u)\\%hs!%p: ", v11, lpBuffer, *(_QWORD *)(a3 + 128), v13);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v12, L"%hs!%p: ", *(const unsigned __int16 **)(a3 + 128), v13);
  }
  v15 = *(const unsigned __int16 **)(a3 + 144);
  v16 = (wil::details *)v14;
  if ( v15 )
    v16 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v12, L"(caller: %p) ", v15);
  LODWORD(Arguments) = v10;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v16,
                          v12,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v8,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v12, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v12, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v12, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180077204  mov     [rsp+arg_18], rbx
0x180077209  push    rbp
0x18007720a  push    rsi
0x18007720b  push    rdi
0x18007720c  push    r14
0x18007720e  push    r15
0x180077210  sub     rsp, 250h
0x180077217  mov     rax, cs:__security_cookie
0x18007721e  xor     rax, rsp
0x180077221  mov     [rsp+278h+var_38], rax
0x180077229  xor     r15d, r15d
0x18007722c  mov     rbx, r8
0x18007722f  mov     rsi, rdx
0x180077232  mov     r14, rcx
0x180077235  test    rdx, rdx
0x180077238  jz      loc_180077491
0x18007723e  test    rcx, rcx
0x180077241  jz      loc_180077491
0x180077247  mov     rax, cs:g_pfnResultLoggingCallback
0x18007724e  mov     [rcx], r15w
0x180077252  test    rax, rax
0x180077255  jz      short loc_180077278
0x180077257  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18007725e  jz      short loc_180077278
0x180077260  mov     r8, rdx
0x180077263  mov     rdx, rcx
0x180077266  mov     rcx, rbx
0x180077269  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007726e  cmp     [r14], r15w
0x180077272  jnz     loc_180077491
0x180077278  mov     ecx, [rbx]
0x18007727a  mov     bpl, 8
0x18007727d  test    ecx, ecx
0x18007727f  jz      short loc_1800772CA
0x180077281  sub     ecx, 1
0x180077284  jz      short loc_1800772B2
0x180077286  sub     ecx, 1
0x180077289  jz      short loc_1800772A2
0x18007728b  cmp     ecx, 1
0x18007728e  jz      short loc_180077299
0x180077290  lea     rdi, word_18009982E
0x180077297  jmp     short loc_1800772D1
0x180077299  lea     rdi, aFailfast; "FailFast"
0x1800772a0  jmp     short loc_1800772D1
0x1800772a2  lea     rax, aLoghr; "LogHr"
0x1800772a9  lea     rdi, aLognt; "LogNt"
0x1800772b0  jmp     short loc_1800772C0
0x1800772b2  lea     rax, aReturnhr; "ReturnHr"
0x1800772b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800772c0  test    [rbx+4], bpl
0x1800772c4  cmovz   rdi, rax
0x1800772c8  jmp     short loc_1800772D1
0x1800772ca  lea     rdi, aException; "Exception"
0x1800772d1  xor     edx, edx; Val
0x1800772d3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800772d8  mov     r8d, 200h; Size
0x1800772de  call    memset_0
0x1800772e3  test    [rbx+4], bpl
0x1800772e7  jz      short loc_18007730C
0x1800772e9  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800772f0  mov     ebp, [rbx+0Ch]
0x1800772f3  test    rax, rax
0x1800772f6  jz      short loc_18007733C
0x1800772f8  mov     r8d, 100h
0x1800772fe  lea     rdx, [rsp+278h+Buffer]
0x180077303  mov     ecx, ebp
0x180077305  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007730a  jmp     short loc_18007733C
0x18007730c  mov     ebp, [rbx+8]
0x18007730f  lea     rax, [rsp+278h+Buffer]
0x180077314  mov     [rsp+278h+Arguments], r15; Arguments
0x180077319  mov     r8d, ebp; dwMessageId
0x18007731c  mov     [rsp+278h+nSize], 100h; nSize
0x180077324  mov     r9d, 400h; dwLanguageId
0x18007732a  xor     edx, edx; lpSource
0x18007732c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180077331  mov     ecx, 1200h; dwFlags
0x180077336  call    cs:__imp_FormatMessageW
0x18007733c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180077340  lea     rsi, [r14+rsi*2]
0x180077344  mov     rax, [rbx+88h]
0x18007734b  mov     rdx, rsi; unsigned __int16 *
0x18007734e  mov     rcx, [rbx+80h]
0x180077355  test    r9, r9
0x180077358  jz      short loc_18007737C
0x18007735a  mov     [rsp+278h+Arguments], rax
0x18007735f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180077366  mov     eax, [rbx+40h]
0x180077369  mov     qword ptr [rsp+278h+nSize], rcx
0x18007736e  mov     rcx, r14; this
0x180077371  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180077375  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007737a  jmp     short loc_180077393
0x18007737c  mov     r9, rcx; unsigned __int16 *
0x18007737f  mov     [rsp+278h+lpBuffer], rax
0x180077384  mov     rcx, r14; this
0x180077387  lea     r8, aHsP; "%hs!%p: "
0x18007738e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077393  mov     r9, [rbx+90h]; unsigned __int16 *
0x18007739a  mov     r14, rax
0x18007739d  test    r9, r9
0x1800773a0  jz      short loc_1800773B7
0x1800773a2  lea     r8, aCallerP; "(caller: %p) "
0x1800773a9  mov     rdx, rsi; unsigned __int16 *
0x1800773ac  mov     rcx, rax; this
0x1800773af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800773b4  mov     r14, rax
0x1800773b7  call    cs:__imp_GetCurrentThreadId
0x1800773bd  lea     rcx, [rsp+278h+Buffer]
0x1800773c2  mov     r9, rdi; unsigned __int16 *
0x1800773c5  mov     [rsp+278h+var_240], rcx
0x1800773ca  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800773d1  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800773d5  mov     rdx, rsi; unsigned __int16 *
0x1800773d8  mov     [rsp+278h+nSize], eax
0x1800773dc  mov     rcx, r14; this
0x1800773df  mov     eax, [rbx+44h]
0x1800773e2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800773e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800773eb  cmp     [rbx+18h], r15
0x1800773ef  jnz     short loc_180077401
0x1800773f1  cmp     [rbx+48h], r15
0x1800773f5  jnz     short loc_180077401
0x1800773f7  cmp     [rbx+30h], r15
0x1800773fb  jz      loc_180077491
0x180077401  lea     r8, asc_180099918; "    "
0x180077408  mov     rdx, rsi; unsigned __int16 *
0x18007740b  mov     rcx, rax; this
0x18007740e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077413  mov     r9, [rbx+18h]; unsigned __int16 *
0x180077417  test    r9, r9
0x18007741a  jz      short loc_18007742E
0x18007741c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180077423  mov     rdx, rsi; unsigned __int16 *
0x180077426  mov     rcx, rax; this
0x180077429  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007742e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180077432  test    r9, r9
0x180077435  jz      short loc_180077449
0x180077437  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18007743e  mov     rdx, rsi; unsigned __int16 *
0x180077441  mov     rcx, rax; this
0x180077444  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077449  mov     rcx, [rbx+28h]
0x18007744d  mov     rdx, rsi; unsigned __int16 *
0x180077450  mov     r9, [rbx+30h]; unsigned __int16 *
0x180077454  test    rcx, rcx
0x180077457  jz      short loc_18007746F
0x180077459  mov     [rsp+278h+lpBuffer], rcx
0x18007745e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180077465  mov     rcx, rax; this
0x180077468  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18007746d  jmp     short loc_180077491
0x18007746f  mov     rcx, rax; this
0x180077472  test    r9, r9
0x180077475  jz      short loc_180077485
0x180077477  lea     r8, aHs; "[%hs]\n"
0x18007747e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077483  jmp     short loc_180077491
0x180077485  lea     r8, asc_180099990; "\n"
0x18007748c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180077491  xor     eax, eax
0x180077493  mov     rcx, [rsp+278h+var_38]
0x18007749b  xor     rcx, rsp; StackCookie
0x18007749e  call    __security_check_cookie
0x1800774a3  mov     rbx, [rsp+278h+arg_18]
0x1800774ab  add     rsp, 250h
0x1800774b2  pop     r15
0x1800774b4  pop     r14
0x1800774b6  pop     rdi
0x1800774b7  pop     rsi
0x1800774b8  pop     rbp
0x1800774b9  retn
```
