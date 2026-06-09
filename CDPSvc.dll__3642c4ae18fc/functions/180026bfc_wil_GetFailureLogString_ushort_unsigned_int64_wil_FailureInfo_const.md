# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180026bfc`
- end: `0x180026eb2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180016e74`
- `0x1800262b4`
- `0x180026eb8`
- `0x180027540`
- `0x18003a030`

## callees

- `0x180004350`
- `0x1800225a0`
- `0x180023148`
- `0x180026bfc`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026daf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180026daf`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180026d2e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180026d2e`

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
          v7 = qword_180076D60;
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
0x180026bfc  mov     [rsp+arg_18], rbx
0x180026c01  push    rbp
0x180026c02  push    rsi
0x180026c03  push    rdi
0x180026c04  push    r14
0x180026c06  push    r15
0x180026c08  sub     rsp, 250h
0x180026c0f  mov     rax, cs:__security_cookie
0x180026c16  xor     rax, rsp
0x180026c19  mov     [rsp+278h+var_38], rax
0x180026c21  mov     rbx, r8
0x180026c24  mov     rsi, rdx
0x180026c27  mov     r14, rcx
0x180026c2a  xor     r15d, r15d
0x180026c2d  test    rdx, rdx
0x180026c30  jz      loc_180026E89
0x180026c36  test    rcx, rcx
0x180026c39  jz      loc_180026E89
0x180026c3f  mov     [rcx], r15w
0x180026c43  mov     rax, cs:g_pfnResultLoggingCallback
0x180026c4a  test    rax, rax
0x180026c4d  jz      short loc_180026C70
0x180026c4f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180026c56  jz      short loc_180026C70
0x180026c58  mov     r8, rdx
0x180026c5b  mov     rdx, rcx
0x180026c5e  mov     rcx, rbx
0x180026c61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026c66  cmp     [r14], r15w
0x180026c6a  jnz     loc_180026E89
0x180026c70  mov     ecx, [rbx]
0x180026c72  mov     bpl, 8
0x180026c75  test    ecx, ecx
0x180026c77  jz      short loc_180026CC2
0x180026c79  sub     ecx, 1
0x180026c7c  jz      short loc_180026CAA
0x180026c7e  sub     ecx, 1
0x180026c81  jz      short loc_180026C9A
0x180026c83  cmp     ecx, 1
0x180026c86  jz      short loc_180026C91
0x180026c88  lea     rdi, qword_180076D60
0x180026c8f  jmp     short loc_180026CC9
0x180026c91  lea     rdi, aFailfast; "FailFast"
0x180026c98  jmp     short loc_180026CC9
0x180026c9a  lea     rax, aLoghr; "LogHr"
0x180026ca1  lea     rdi, aLognt; "LogNt"
0x180026ca8  jmp     short loc_180026CB8
0x180026caa  lea     rax, aReturnhr; "ReturnHr"
0x180026cb1  lea     rdi, aReturnnt; "ReturnNt"
0x180026cb8  test    [rbx+4], bpl
0x180026cbc  cmovz   rdi, rax
0x180026cc0  jmp     short loc_180026CC9
0x180026cc2  lea     rdi, aException; "Exception"
0x180026cc9  xor     edx, edx; Val
0x180026ccb  mov     r8d, 200h; Size
0x180026cd1  lea     rcx, [rsp+278h+Buffer]; void *
0x180026cd6  call    memset_0
0x180026cdb  test    [rbx+4], bpl
0x180026cdf  jz      short loc_180026D04
0x180026ce1  mov     ebp, [rbx+0Ch]
0x180026ce4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180026ceb  test    rax, rax
0x180026cee  jz      short loc_180026D34
0x180026cf0  mov     r8d, 100h
0x180026cf6  lea     rdx, [rsp+278h+Buffer]
0x180026cfb  mov     ecx, ebp
0x180026cfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026d02  jmp     short loc_180026D34
0x180026d04  mov     ebp, [rbx+8]
0x180026d07  mov     [rsp+278h+Arguments], r15; Arguments
0x180026d0c  mov     [rsp+278h+nSize], 100h; nSize
0x180026d14  lea     rax, [rsp+278h+Buffer]
0x180026d19  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180026d1e  mov     r9d, 400h; dwLanguageId
0x180026d24  mov     r8d, ebp; dwMessageId
0x180026d27  xor     edx, edx; lpSource
0x180026d29  mov     ecx, 1200h; dwFlags
0x180026d2e  call    cs:__imp_FormatMessageW
0x180026d34  lea     rsi, [r14+rsi*2]
0x180026d38  mov     r9, [rbx+38h]; unsigned __int16 *
0x180026d3c  mov     rax, [rbx+88h]
0x180026d43  mov     rcx, [rbx+80h]
0x180026d4a  mov     rdx, rsi; unsigned __int16 *
0x180026d4d  test    r9, r9
0x180026d50  jz      short loc_180026D74
0x180026d52  mov     [rsp+278h+Arguments], rax
0x180026d57  mov     qword ptr [rsp+278h+nSize], rcx
0x180026d5c  mov     eax, [rbx+40h]
0x180026d5f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180026d63  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180026d6a  mov     rcx, r14; this
0x180026d6d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026d72  jmp     short loc_180026D8B
0x180026d74  mov     [rsp+278h+lpBuffer], rax
0x180026d79  mov     r9, rcx; unsigned __int16 *
0x180026d7c  lea     r8, aHsP; "%hs!%p: "
0x180026d83  mov     rcx, r14; this
0x180026d86  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026d8b  mov     r14, rax
0x180026d8e  mov     r9, [rbx+90h]; unsigned __int16 *
0x180026d95  test    r9, r9
0x180026d98  jz      short loc_180026DAF
0x180026d9a  lea     r8, aCallerP; "(caller: %p) "
0x180026da1  mov     rdx, rsi; unsigned __int16 *
0x180026da4  mov     rcx, rax; this
0x180026da7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026dac  mov     r14, rax
0x180026daf  call    cs:__imp_GetCurrentThreadId
0x180026db5  lea     rcx, [rsp+278h+Buffer]
0x180026dba  mov     [rsp+278h+var_240], rcx
0x180026dbf  mov     dword ptr [rsp+278h+Arguments], ebp
0x180026dc3  mov     [rsp+278h+nSize], eax
0x180026dc7  mov     eax, [rbx+44h]
0x180026dca  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180026dce  mov     r9, rdi; unsigned __int16 *
0x180026dd1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180026dd8  mov     rdx, rsi; unsigned __int16 *
0x180026ddb  mov     rcx, r14; this
0x180026dde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026de3  cmp     [rbx+18h], r15
0x180026de7  jnz     short loc_180026DF9
0x180026de9  cmp     [rbx+48h], r15
0x180026ded  jnz     short loc_180026DF9
0x180026def  cmp     [rbx+30h], r15
0x180026df3  jz      loc_180026E89
0x180026df9  lea     r8, asc_180076E50; "    "
0x180026e00  mov     rdx, rsi; unsigned __int16 *
0x180026e03  mov     rcx, rax; this
0x180026e06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026e0b  mov     r9, [rbx+18h]; unsigned __int16 *
0x180026e0f  test    r9, r9
0x180026e12  jz      short loc_180026E26
0x180026e14  lea     r8, aMsgWs; "Msg:[%ws] "
0x180026e1b  mov     rdx, rsi; unsigned __int16 *
0x180026e1e  mov     rcx, rax; this
0x180026e21  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026e26  mov     r9, [rbx+48h]; unsigned __int16 *
0x180026e2a  test    r9, r9
0x180026e2d  jz      short loc_180026E41
0x180026e2f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180026e36  mov     rdx, rsi; unsigned __int16 *
0x180026e39  mov     rcx, rax; this
0x180026e3c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026e41  mov     rcx, [rbx+28h]
0x180026e45  mov     r9, [rbx+30h]; unsigned __int16 *
0x180026e49  mov     rdx, rsi; unsigned __int16 *
0x180026e4c  test    rcx, rcx
0x180026e4f  jz      short loc_180026E67
0x180026e51  mov     [rsp+278h+lpBuffer], rcx
0x180026e56  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180026e5d  mov     rcx, rax; this
0x180026e60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026e65  jmp     short loc_180026E89
0x180026e67  mov     rcx, rax; this
0x180026e6a  test    r9, r9
0x180026e6d  jz      short loc_180026E7D
0x180026e6f  lea     r8, aHs; "[%hs]\n"
0x180026e76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026e7b  jmp     short loc_180026E89
0x180026e7d  lea     r8, asc_180076EC8; "\n"
0x180026e84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180026e89  xor     eax, eax
0x180026e8b  mov     rcx, [rsp+278h+var_38]
0x180026e93  xor     rcx, rsp; StackCookie
0x180026e96  call    __security_check_cookie
0x180026e9b  mov     rbx, [rsp+278h+arg_18]
0x180026ea3  add     rsp, 250h
0x180026eaa  pop     r15
0x180026eac  pop     r14
0x180026eae  pop     rdi
0x180026eaf  pop     rsi
0x180026eb0  pop     rbp
0x180026eb1  retn
```
