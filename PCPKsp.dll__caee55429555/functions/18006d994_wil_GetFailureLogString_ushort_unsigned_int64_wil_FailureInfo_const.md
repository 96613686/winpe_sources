# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18006d994`
- end: `0x18006dc57`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180058514`
- `0x18006d840`
- `0x1800791c8`

## callees

- `0x18006d994`
- `0x1800764d0`
- `0x18007704c`
- `0x180078f78`
- `0x1800c8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006db4d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18006db4d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006dac6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18006dac6`

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
          v7 = (const char *)&word_1800DBB72;
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
0x18006d994  mov     [rsp+arg_18], rbx
0x18006d999  push    rbp
0x18006d99a  push    rsi
0x18006d99b  push    rdi
0x18006d99c  push    r14
0x18006d99e  push    r15
0x18006d9a0  sub     rsp, 250h
0x18006d9a7  mov     rax, cs:__security_cookie
0x18006d9ae  xor     rax, rsp
0x18006d9b1  mov     [rsp+278h+var_38], rax
0x18006d9b9  mov     rbx, r8
0x18006d9bc  mov     rsi, rdx
0x18006d9bf  mov     r14, rcx
0x18006d9c2  xor     r15d, r15d
0x18006d9c5  test    rdx, rdx
0x18006d9c8  jz      loc_18006DC2D
0x18006d9ce  test    rcx, rcx
0x18006d9d1  jz      loc_18006DC2D
0x18006d9d7  mov     [rcx], r15w
0x18006d9db  mov     rax, cs:g_pfnResultLoggingCallback
0x18006d9e2  test    rax, rax
0x18006d9e5  jz      short loc_18006DA08
0x18006d9e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18006d9ee  jz      short loc_18006DA08
0x18006d9f0  mov     r8, rdx
0x18006d9f3  mov     rdx, rcx
0x18006d9f6  mov     rcx, rbx
0x18006d9f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006d9fe  cmp     [r14], r15w
0x18006da02  jnz     loc_18006DC2D
0x18006da08  mov     ecx, [rbx]
0x18006da0a  mov     bpl, 8
0x18006da0d  test    ecx, ecx
0x18006da0f  jz      short loc_18006DA5A
0x18006da11  sub     ecx, 1
0x18006da14  jz      short loc_18006DA42
0x18006da16  sub     ecx, 1
0x18006da19  jz      short loc_18006DA32
0x18006da1b  cmp     ecx, 1
0x18006da1e  jz      short loc_18006DA29
0x18006da20  lea     rdi, word_1800DBB72
0x18006da27  jmp     short loc_18006DA61
0x18006da29  lea     rdi, aFailfast; "FailFast"
0x18006da30  jmp     short loc_18006DA61
0x18006da32  lea     rax, aLoghr; "LogHr"
0x18006da39  lea     rdi, aLognt; "LogNt"
0x18006da40  jmp     short loc_18006DA50
0x18006da42  lea     rax, aReturnhr; "ReturnHr"
0x18006da49  lea     rdi, aReturnnt; "ReturnNt"
0x18006da50  test    [rbx+4], bpl
0x18006da54  cmovz   rdi, rax
0x18006da58  jmp     short loc_18006DA61
0x18006da5a  lea     rdi, aException; "Exception"
0x18006da61  xor     edx, edx; Val
0x18006da63  mov     r8d, 200h; Size
0x18006da69  lea     rcx, [rsp+278h+Buffer]; void *
0x18006da6e  call    memset_0
0x18006da73  test    [rbx+4], bpl
0x18006da77  jz      short loc_18006DA9C
0x18006da79  mov     ebp, [rbx+0Ch]
0x18006da7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18006da83  test    rax, rax
0x18006da86  jz      short loc_18006DAD2
0x18006da88  mov     r8d, 100h
0x18006da8e  lea     rdx, [rsp+278h+Buffer]
0x18006da93  mov     ecx, ebp
0x18006da95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18006da9a  jmp     short loc_18006DAD2
0x18006da9c  mov     ebp, [rbx+8]
0x18006da9f  mov     [rsp+278h+Arguments], r15; Arguments
0x18006daa4  mov     [rsp+278h+nSize], 100h; nSize
0x18006daac  lea     rax, [rsp+278h+Buffer]
0x18006dab1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18006dab6  mov     r9d, 400h; dwLanguageId
0x18006dabc  mov     r8d, ebp; dwMessageId
0x18006dabf  xor     edx, edx; lpSource
0x18006dac1  mov     ecx, 1200h; dwFlags
0x18006dac6  call    cs:__imp_FormatMessageW
0x18006dacd  nop     dword ptr [rax+rax+00h]
0x18006dad2  lea     rsi, [r14+rsi*2]
0x18006dad6  mov     r9, [rbx+38h]; unsigned __int16 *
0x18006dada  mov     rax, [rbx+88h]
0x18006dae1  mov     rcx, [rbx+80h]
0x18006dae8  mov     rdx, rsi; unsigned __int16 *
0x18006daeb  test    r9, r9
0x18006daee  jz      short loc_18006DB12
0x18006daf0  mov     [rsp+278h+Arguments], rax
0x18006daf5  mov     qword ptr [rsp+278h+nSize], rcx
0x18006dafa  mov     eax, [rbx+40h]
0x18006dafd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18006db01  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18006db08  mov     rcx, r14; this
0x18006db0b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006db10  jmp     short loc_18006DB29
0x18006db12  mov     [rsp+278h+lpBuffer], rax
0x18006db17  mov     r9, rcx; unsigned __int16 *
0x18006db1a  lea     r8, aHsP; "%hs!%p: "
0x18006db21  mov     rcx, r14; this
0x18006db24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006db29  mov     r14, rax
0x18006db2c  mov     r9, [rbx+90h]; unsigned __int16 *
0x18006db33  test    r9, r9
0x18006db36  jz      short loc_18006DB4D
0x18006db38  lea     r8, aCallerP; "(caller: %p) "
0x18006db3f  mov     rdx, rsi; unsigned __int16 *
0x18006db42  mov     rcx, rax; this
0x18006db45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006db4a  mov     r14, rax
0x18006db4d  call    cs:__imp_GetCurrentThreadId
0x18006db54  nop     dword ptr [rax+rax+00h]
0x18006db59  lea     rcx, [rsp+278h+Buffer]
0x18006db5e  mov     [rsp+278h+var_240], rcx
0x18006db63  mov     dword ptr [rsp+278h+Arguments], ebp
0x18006db67  mov     [rsp+278h+nSize], eax
0x18006db6b  mov     eax, [rbx+44h]
0x18006db6e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18006db72  mov     r9, rdi; unsigned __int16 *
0x18006db75  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18006db7c  mov     rdx, rsi; unsigned __int16 *
0x18006db7f  mov     rcx, r14; this
0x18006db82  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006db87  cmp     [rbx+18h], r15
0x18006db8b  jnz     short loc_18006DB9D
0x18006db8d  cmp     [rbx+48h], r15
0x18006db91  jnz     short loc_18006DB9D
0x18006db93  cmp     [rbx+30h], r15
0x18006db97  jz      loc_18006DC2D
0x18006db9d  lea     r8, asc_1800DEDF8; "    "
0x18006dba4  mov     rdx, rsi; unsigned __int16 *
0x18006dba7  mov     rcx, rax; this
0x18006dbaa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006dbaf  mov     r9, [rbx+18h]; unsigned __int16 *
0x18006dbb3  test    r9, r9
0x18006dbb6  jz      short loc_18006DBCA
0x18006dbb8  lea     r8, aMsgWs; "Msg:[%ws] "
0x18006dbbf  mov     rdx, rsi; unsigned __int16 *
0x18006dbc2  mov     rcx, rax; this
0x18006dbc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006dbca  mov     r9, [rbx+48h]; unsigned __int16 *
0x18006dbce  test    r9, r9
0x18006dbd1  jz      short loc_18006DBE5
0x18006dbd3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18006dbda  mov     rdx, rsi; unsigned __int16 *
0x18006dbdd  mov     rcx, rax; this
0x18006dbe0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006dbe5  mov     rcx, [rbx+28h]
0x18006dbe9  mov     r9, [rbx+30h]; unsigned __int16 *
0x18006dbed  mov     rdx, rsi; unsigned __int16 *
0x18006dbf0  test    rcx, rcx
0x18006dbf3  jz      short loc_18006DC0B
0x18006dbf5  mov     [rsp+278h+lpBuffer], rcx
0x18006dbfa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18006dc01  mov     rcx, rax; this
0x18006dc04  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006dc09  jmp     short loc_18006DC2D
0x18006dc0b  mov     rcx, rax; this
0x18006dc0e  test    r9, r9
0x18006dc11  jz      short loc_18006DC21
0x18006dc13  lea     r8, aHs; "[%hs]\n"
0x18006dc1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006dc1f  jmp     short loc_18006DC2D
0x18006dc21  lea     r8, asc_1800DEE70; "\n"
0x18006dc28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18006dc2d  xor     eax, eax
0x18006dc2f  mov     rcx, [rsp+278h+var_38]
0x18006dc37  xor     rcx, rsp; StackCookie
0x18006dc3a  call    __security_check_cookie
0x18006dc3f  mov     rbx, [rsp+278h+arg_18]
0x18006dc47  add     rsp, 250h
0x18006dc4e  pop     r15
0x18006dc50  pop     r14
0x18006dc52  pop     rdi
0x18006dc53  pop     rsi
0x18006dc54  pop     rbp
0x18006dc55  retn
```
