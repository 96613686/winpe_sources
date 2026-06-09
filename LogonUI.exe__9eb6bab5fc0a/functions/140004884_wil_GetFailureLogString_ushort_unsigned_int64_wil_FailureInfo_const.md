# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140004884`
- end: `0x140004b3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400050c4`

## callees

- `0x140002530`
- `0x140002910`
- `0x1400032d0`
- `0x140004884`
- `0x140008010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004a37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400049b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1400049b6`

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
          v8 = (const char *)&byte_1400096BF;
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
0x140004884  mov     [rsp+arg_18], rbx
0x140004889  push    rbp
0x14000488a  push    rsi
0x14000488b  push    rdi
0x14000488c  push    r14
0x14000488e  push    r15
0x140004890  sub     rsp, 250h
0x140004897  mov     rax, cs:__security_cookie
0x14000489e  xor     rax, rsp
0x1400048a1  mov     [rsp+278h+var_38], rax
0x1400048a9  xor     r15d, r15d
0x1400048ac  mov     rbx, r8
0x1400048af  mov     rsi, rdx
0x1400048b2  mov     r14, rcx
0x1400048b5  test    rdx, rdx
0x1400048b8  jz      loc_140004B11
0x1400048be  test    rcx, rcx
0x1400048c1  jz      loc_140004B11
0x1400048c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400048ce  mov     [rcx], r15w
0x1400048d2  test    rax, rax
0x1400048d5  jz      short loc_1400048F8
0x1400048d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1400048de  jz      short loc_1400048F8
0x1400048e0  mov     r8, rdx
0x1400048e3  mov     rdx, rcx
0x1400048e6  mov     rcx, rbx
0x1400048e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048ee  cmp     [r14], r15w
0x1400048f2  jnz     loc_140004B11
0x1400048f8  mov     ecx, [rbx]
0x1400048fa  mov     bpl, 8
0x1400048fd  test    ecx, ecx
0x1400048ff  jz      short loc_14000494A
0x140004901  sub     ecx, 1
0x140004904  jz      short loc_140004932
0x140004906  sub     ecx, 1
0x140004909  jz      short loc_140004922
0x14000490b  cmp     ecx, 1
0x14000490e  jz      short loc_140004919
0x140004910  lea     rdi, byte_1400096BF
0x140004917  jmp     short loc_140004951
0x140004919  lea     rdi, aFailfast; "FailFast"
0x140004920  jmp     short loc_140004951
0x140004922  lea     rax, aLoghr; "LogHr"
0x140004929  lea     rdi, aLognt; "LogNt"
0x140004930  jmp     short loc_140004940
0x140004932  lea     rax, aReturnhr; "ReturnHr"
0x140004939  lea     rdi, aReturnnt; "ReturnNt"
0x140004940  test    [rbx+4], bpl
0x140004944  cmovz   rdi, rax
0x140004948  jmp     short loc_140004951
0x14000494a  lea     rdi, aException; "Exception"
0x140004951  xor     edx, edx; Val
0x140004953  lea     rcx, [rsp+278h+Buffer]; void *
0x140004958  mov     r8d, 200h; Size
0x14000495e  call    memset_0
0x140004963  test    [rbx+4], bpl
0x140004967  jz      short loc_14000498C
0x140004969  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140004970  mov     ebp, [rbx+0Ch]
0x140004973  test    rax, rax
0x140004976  jz      short loc_1400049BC
0x140004978  mov     r8d, 100h
0x14000497e  lea     rdx, [rsp+278h+Buffer]
0x140004983  mov     ecx, ebp
0x140004985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000498a  jmp     short loc_1400049BC
0x14000498c  mov     ebp, [rbx+8]
0x14000498f  lea     rax, [rsp+278h+Buffer]
0x140004994  mov     [rsp+278h+Arguments], r15; Arguments
0x140004999  mov     r8d, ebp; dwMessageId
0x14000499c  mov     [rsp+278h+nSize], 100h; nSize
0x1400049a4  mov     r9d, 400h; dwLanguageId
0x1400049aa  xor     edx, edx; lpSource
0x1400049ac  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400049b1  mov     ecx, 1200h; dwFlags
0x1400049b6  call    cs:__imp_FormatMessageW
0x1400049bc  mov     r9, [rbx+38h]; unsigned __int16 *
0x1400049c0  lea     rsi, [r14+rsi*2]
0x1400049c4  mov     rax, [rbx+88h]
0x1400049cb  mov     rdx, rsi; unsigned __int16 *
0x1400049ce  mov     rcx, [rbx+80h]
0x1400049d5  test    r9, r9
0x1400049d8  jz      short loc_1400049FC
0x1400049da  mov     [rsp+278h+Arguments], rax
0x1400049df  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1400049e6  mov     eax, [rbx+40h]
0x1400049e9  mov     qword ptr [rsp+278h+nSize], rcx
0x1400049ee  mov     rcx, r14; this
0x1400049f1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400049f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400049fa  jmp     short loc_140004A13
0x1400049fc  mov     r9, rcx; unsigned __int16 *
0x1400049ff  mov     [rsp+278h+lpBuffer], rax
0x140004a04  mov     rcx, r14; this
0x140004a07  lea     r8, aHsP; "%hs!%p: "
0x140004a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a13  mov     r9, [rbx+90h]; unsigned __int16 *
0x140004a1a  mov     r14, rax
0x140004a1d  test    r9, r9
0x140004a20  jz      short loc_140004A37
0x140004a22  lea     r8, aCallerP; "(caller: %p) "
0x140004a29  mov     rdx, rsi; unsigned __int16 *
0x140004a2c  mov     rcx, rax; this
0x140004a2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a34  mov     r14, rax
0x140004a37  call    cs:__imp_GetCurrentThreadId
0x140004a3d  lea     rcx, [rsp+278h+Buffer]
0x140004a42  mov     r9, rdi; unsigned __int16 *
0x140004a45  mov     [rsp+278h+var_240], rcx
0x140004a4a  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140004a51  mov     dword ptr [rsp+278h+Arguments], ebp
0x140004a55  mov     rdx, rsi; unsigned __int16 *
0x140004a58  mov     [rsp+278h+nSize], eax
0x140004a5c  mov     rcx, r14; this
0x140004a5f  mov     eax, [rbx+44h]
0x140004a62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140004a66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a6b  cmp     [rbx+18h], r15
0x140004a6f  jnz     short loc_140004A81
0x140004a71  cmp     [rbx+48h], r15
0x140004a75  jnz     short loc_140004A81
0x140004a77  cmp     [rbx+30h], r15
0x140004a7b  jz      loc_140004B11
0x140004a81  lea     r8, asc_1400097A8; "    "
0x140004a88  mov     rdx, rsi; unsigned __int16 *
0x140004a8b  mov     rcx, rax; this
0x140004a8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004a93  mov     r9, [rbx+18h]; unsigned __int16 *
0x140004a97  test    r9, r9
0x140004a9a  jz      short loc_140004AAE
0x140004a9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140004aa3  mov     rdx, rsi; unsigned __int16 *
0x140004aa6  mov     rcx, rax; this
0x140004aa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004aae  mov     r9, [rbx+48h]; unsigned __int16 *
0x140004ab2  test    r9, r9
0x140004ab5  jz      short loc_140004AC9
0x140004ab7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140004abe  mov     rdx, rsi; unsigned __int16 *
0x140004ac1  mov     rcx, rax; this
0x140004ac4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004ac9  mov     rcx, [rbx+28h]
0x140004acd  mov     rdx, rsi; unsigned __int16 *
0x140004ad0  mov     r9, [rbx+30h]; unsigned __int16 *
0x140004ad4  test    rcx, rcx
0x140004ad7  jz      short loc_140004AEF
0x140004ad9  mov     [rsp+278h+lpBuffer], rcx
0x140004ade  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140004ae5  mov     rcx, rax; this
0x140004ae8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004aed  jmp     short loc_140004B11
0x140004aef  mov     rcx, rax; this
0x140004af2  test    r9, r9
0x140004af5  jz      short loc_140004B05
0x140004af7  lea     r8, aHs; "[%hs]\n"
0x140004afe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b03  jmp     short loc_140004B11
0x140004b05  lea     r8, asc_140009820; "\n"
0x140004b0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140004b11  xor     eax, eax
0x140004b13  mov     rcx, [rsp+278h+var_38]
0x140004b1b  xor     rcx, rsp; StackCookie
0x140004b1e  call    __security_check_cookie
0x140004b23  mov     rbx, [rsp+278h+arg_18]
0x140004b2b  add     rsp, 250h
0x140004b32  pop     r15
0x140004b34  pop     r14
0x140004b36  pop     rdi
0x140004b37  pop     rsi
0x140004b38  pop     rbp
0x140004b39  retn
```
