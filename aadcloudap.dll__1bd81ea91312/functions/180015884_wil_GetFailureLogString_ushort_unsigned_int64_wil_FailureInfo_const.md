# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180015884`
- end: `0x180015b3a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x1800087fc`
- `0x180016640`
- `0x18001c840`

## callees

- `0x180003c20`
- `0x180004a24`
- `0x180015884`
- `0x180016940`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015a37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800159b6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800159b6`

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
          v7 = (const char *)&word_1800B0ED2;
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
0x180015884  mov     [rsp+arg_18], rbx
0x180015889  push    rbp
0x18001588a  push    rsi
0x18001588b  push    rdi
0x18001588c  push    r14
0x18001588e  push    r15
0x180015890  sub     rsp, 250h
0x180015897  mov     rax, cs:__security_cookie
0x18001589e  xor     rax, rsp
0x1800158a1  mov     [rsp+278h+var_38], rax
0x1800158a9  mov     rbx, r8
0x1800158ac  mov     rsi, rdx
0x1800158af  mov     r14, rcx
0x1800158b2  xor     r15d, r15d
0x1800158b5  test    rdx, rdx
0x1800158b8  jz      loc_180015B11
0x1800158be  test    rcx, rcx
0x1800158c1  jz      loc_180015B11
0x1800158c7  mov     [rcx], r15w
0x1800158cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800158d2  test    rax, rax
0x1800158d5  jz      short loc_1800158F8
0x1800158d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800158de  jz      short loc_1800158F8
0x1800158e0  mov     r8, rdx
0x1800158e3  mov     rdx, rcx
0x1800158e6  mov     rcx, rbx
0x1800158e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800158ee  cmp     [r14], r15w
0x1800158f2  jnz     loc_180015B11
0x1800158f8  mov     ecx, [rbx]
0x1800158fa  mov     bpl, 8
0x1800158fd  test    ecx, ecx
0x1800158ff  jz      short loc_18001594A
0x180015901  sub     ecx, 1
0x180015904  jz      short loc_180015932
0x180015906  sub     ecx, 1
0x180015909  jz      short loc_180015922
0x18001590b  cmp     ecx, 1
0x18001590e  jz      short loc_180015919
0x180015910  lea     rdi, word_1800B0ED2
0x180015917  jmp     short loc_180015951
0x180015919  lea     rdi, aFailfast; "FailFast"
0x180015920  jmp     short loc_180015951
0x180015922  lea     rax, aLoghr; "LogHr"
0x180015929  lea     rdi, aLognt; "LogNt"
0x180015930  jmp     short loc_180015940
0x180015932  lea     rax, aReturnhr; "ReturnHr"
0x180015939  lea     rdi, aReturnnt; "ReturnNt"
0x180015940  test    [rbx+4], bpl
0x180015944  cmovz   rdi, rax
0x180015948  jmp     short loc_180015951
0x18001594a  lea     rdi, aException; "Exception"
0x180015951  xor     edx, edx; Val
0x180015953  mov     r8d, 200h; Size
0x180015959  lea     rcx, [rsp+278h+Buffer]; void *
0x18001595e  call    memset_0
0x180015963  test    [rbx+4], bpl
0x180015967  jz      short loc_18001598C
0x180015969  mov     ebp, [rbx+0Ch]
0x18001596c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180015973  test    rax, rax
0x180015976  jz      short loc_1800159BC
0x180015978  mov     r8d, 100h
0x18001597e  lea     rdx, [rsp+278h+Buffer]
0x180015983  mov     ecx, ebp
0x180015985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001598a  jmp     short loc_1800159BC
0x18001598c  mov     ebp, [rbx+8]
0x18001598f  mov     [rsp+278h+Arguments], r15; Arguments
0x180015994  mov     [rsp+278h+nSize], 100h; nSize
0x18001599c  lea     rax, [rsp+278h+Buffer]
0x1800159a1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800159a6  mov     r9d, 400h; dwLanguageId
0x1800159ac  mov     r8d, ebp; dwMessageId
0x1800159af  xor     edx, edx; lpSource
0x1800159b1  mov     ecx, 1200h; dwFlags
0x1800159b6  call    cs:__imp_FormatMessageW
0x1800159bc  lea     rsi, [r14+rsi*2]
0x1800159c0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800159c4  mov     rax, [rbx+88h]
0x1800159cb  mov     rcx, [rbx+80h]
0x1800159d2  mov     rdx, rsi; unsigned __int16 *
0x1800159d5  test    r9, r9
0x1800159d8  jz      short loc_1800159FC
0x1800159da  mov     [rsp+278h+Arguments], rax
0x1800159df  mov     qword ptr [rsp+278h+nSize], rcx
0x1800159e4  mov     eax, [rbx+40h]
0x1800159e7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800159eb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800159f2  mov     rcx, r14; this
0x1800159f5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800159fa  jmp     short loc_180015A13
0x1800159fc  mov     [rsp+278h+lpBuffer], rax
0x180015a01  mov     r9, rcx; unsigned __int16 *
0x180015a04  lea     r8, aHsP; "%hs!%p: "
0x180015a0b  mov     rcx, r14; this
0x180015a0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015a13  mov     r14, rax
0x180015a16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180015a1d  test    r9, r9
0x180015a20  jz      short loc_180015A37
0x180015a22  lea     r8, aCallerP; "(caller: %p) "
0x180015a29  mov     rdx, rsi; unsigned __int16 *
0x180015a2c  mov     rcx, rax; this
0x180015a2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015a34  mov     r14, rax
0x180015a37  call    cs:__imp_GetCurrentThreadId
0x180015a3d  lea     rcx, [rsp+278h+Buffer]
0x180015a42  mov     [rsp+278h+var_240], rcx
0x180015a47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180015a4b  mov     [rsp+278h+nSize], eax
0x180015a4f  mov     eax, [rbx+44h]
0x180015a52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180015a56  mov     r9, rdi; unsigned __int16 *
0x180015a59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180015a60  mov     rdx, rsi; unsigned __int16 *
0x180015a63  mov     rcx, r14; this
0x180015a66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015a6b  cmp     [rbx+18h], r15
0x180015a6f  jnz     short loc_180015A81
0x180015a71  cmp     [rbx+48h], r15
0x180015a75  jnz     short loc_180015A81
0x180015a77  cmp     [rbx+30h], r15
0x180015a7b  jz      loc_180015B11
0x180015a81  lea     r8, asc_1800AF670; "    "
0x180015a88  mov     rdx, rsi; unsigned __int16 *
0x180015a8b  mov     rcx, rax; this
0x180015a8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015a93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180015a97  test    r9, r9
0x180015a9a  jz      short loc_180015AAE
0x180015a9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180015aa3  mov     rdx, rsi; unsigned __int16 *
0x180015aa6  mov     rcx, rax; this
0x180015aa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015aae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180015ab2  test    r9, r9
0x180015ab5  jz      short loc_180015AC9
0x180015ab7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180015abe  mov     rdx, rsi; unsigned __int16 *
0x180015ac1  mov     rcx, rax; this
0x180015ac4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015ac9  mov     rcx, [rbx+28h]
0x180015acd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180015ad1  mov     rdx, rsi; unsigned __int16 *
0x180015ad4  test    rcx, rcx
0x180015ad7  jz      short loc_180015AEF
0x180015ad9  mov     [rsp+278h+lpBuffer], rcx
0x180015ade  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180015ae5  mov     rcx, rax; this
0x180015ae8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015aed  jmp     short loc_180015B11
0x180015aef  mov     rcx, rax; this
0x180015af2  test    r9, r9
0x180015af5  jz      short loc_180015B05
0x180015af7  lea     r8, aHs; "[%hs]\n"
0x180015afe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015b03  jmp     short loc_180015B11
0x180015b05  lea     r8, asc_1800AF6E8; "\n"
0x180015b0c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180015b11  xor     eax, eax
0x180015b13  mov     rcx, [rsp+278h+var_38]
0x180015b1b  xor     rcx, rsp; StackCookie
0x180015b1e  call    __security_check_cookie
0x180015b23  mov     rbx, [rsp+278h+arg_18]
0x180015b2b  add     rsp, 250h
0x180015b32  pop     r15
0x180015b34  pop     r14
0x180015b36  pop     rdi
0x180015b37  pop     rsi
0x180015b38  pop     rbp
0x180015b39  retn
```
