# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18003b6ec`
- end: `0x18003b99c`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `688`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x18003bed0`

## callees

- `0x1800030b6`
- `0x18003b6ec`
- `0x18003c0cc`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b899`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003b899`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003b815`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18003b815`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(
        wil *this,
        unsigned __int16 *a2,
        __int64 a3,
        const struct wil::FailureInfo *a4)
{
  const char *v6; // rdi
  const char *v7; // rax
  DWORD v8; // ebp
  unsigned __int16 *v9; // rsi
  const unsigned __int16 *v10; // r9
  __int64 v11; // rax
  const unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rdx
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

  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, 2048);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  if ( *(_DWORD *)a3 )
  {
    if ( *(_DWORD *)a3 == 1 )
    {
      v7 = "ReturnHr";
      v6 = "ReturnNt";
    }
    else
    {
      if ( *(_DWORD *)a3 != 2 )
      {
        if ( *(_DWORD *)a3 == 3 )
          v6 = "FailFast";
        else
          v6 = (const char *)&byte_18008A910;
        goto LABEL_17;
      }
      v7 = "LogHr";
      v6 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v6 = v7;
    goto LABEL_17;
  }
  v6 = "Exception";
LABEL_17:
  memset_0(Buffer, 0, sizeof(Buffer));
  if ( (*(_BYTE *)(a3 + 4) & 8) != 0 )
  {
    v8 = *(_DWORD *)(a3 + 12);
    if ( wil::details::g_pfnFormatNtStatusMsg )
      wil::details::g_pfnFormatNtStatusMsg(v8, Buffer, 0x100u);
  }
  else
  {
    v8 = *(_DWORD *)(a3 + 8);
    FormatMessageW(0x1200u, 0, v8, 0x400u, Buffer, 0x100u, 0);
  }
  v9 = (unsigned __int16 *)((char *)this + 4096);
  v10 = *(const unsigned __int16 **)(a3 + 56);
  v11 = *(_QWORD *)(a3 + 136);
  v12 = *(const unsigned __int16 **)(a3 + 128);
  v13 = (unsigned __int16 *)((char *)this + 4096);
  if ( v10 )
  {
    LODWORD(lpBuffer) = *(_DWORD *)(a3 + 64);
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs(%u)\\%hs!%p: ", v10, lpBuffer, v12, v11);
  }
  else
  {
    v14 = wil::details::LogStringPrintf(this, v13, L"%hs!%p: ", v12, v11);
  }
  v15 = (wil::details *)v14;
  v16 = *(const unsigned __int16 **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v9, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v8;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v9,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const unsigned __int16 *)v6,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v9, L"    ", v18);
    v20 = *(const unsigned __int16 **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v9, L"Msg:[%ws] ", v20);
    v21 = *(const unsigned __int16 **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v9, L"CallContext:[%hs] ", v21);
    v22 = *(const unsigned __int16 **)(a3 + 48);
    if ( *(_QWORD *)(a3 + 40) )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v9, L"[%hs(%hs)]\n", v22, *(_QWORD *)(a3 + 40));
    }
    else if ( v22 )
    {
      wil::details::LogStringPrintf((wil::details *)v19, v9, L"[%hs]\n", v22);
    }
    else
    {
      wil::details::LogStringPrintf((wil::details *)v19, v9, L"\n", 0);
    }
  }
  return 0;
}

```

## disassembly

```asm
0x18003b6ec  mov     [rsp+arg_8], rbx
0x18003b6f1  push    rbp
0x18003b6f2  push    rsi
0x18003b6f3  push    rdi
0x18003b6f4  push    r14
0x18003b6f6  push    r15
0x18003b6f8  sub     rsp, 250h
0x18003b6ff  mov     rax, cs:__security_cookie
0x18003b706  xor     rax, rsp
0x18003b709  mov     [rsp+278h+var_38], rax
0x18003b711  mov     rbx, r8
0x18003b714  mov     r14, rcx
0x18003b717  xor     r15d, r15d
0x18003b71a  test    rcx, rcx
0x18003b71d  jz      loc_18003B973
0x18003b723  mov     [rcx], r15w
0x18003b727  mov     rax, cs:g_pfnResultLoggingCallback
0x18003b72e  test    rax, rax
0x18003b731  jz      short loc_18003B757
0x18003b733  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18003b73a  jz      short loc_18003B757
0x18003b73c  mov     r8d, 800h
0x18003b742  mov     rdx, rcx
0x18003b745  mov     rcx, rbx
0x18003b748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b74d  cmp     [r14], r15w
0x18003b751  jnz     loc_18003B973
0x18003b757  mov     ecx, [rbx]
0x18003b759  mov     sil, 8
0x18003b75c  test    ecx, ecx
0x18003b75e  jz      short loc_18003B7A9
0x18003b760  sub     ecx, 1
0x18003b763  jz      short loc_18003B791
0x18003b765  sub     ecx, 1
0x18003b768  jz      short loc_18003B781
0x18003b76a  cmp     ecx, 1
0x18003b76d  jz      short loc_18003B778
0x18003b76f  lea     rdi, byte_18008A910
0x18003b776  jmp     short loc_18003B7B0
0x18003b778  lea     rdi, aFailfast; "FailFast"
0x18003b77f  jmp     short loc_18003B7B0
0x18003b781  lea     rax, aLoghr; "LogHr"
0x18003b788  lea     rdi, aLognt; "LogNt"
0x18003b78f  jmp     short loc_18003B79F
0x18003b791  lea     rax, aReturnhr; "ReturnHr"
0x18003b798  lea     rdi, aReturnnt; "ReturnNt"
0x18003b79f  test    [rbx+4], sil
0x18003b7a3  cmovz   rdi, rax
0x18003b7a7  jmp     short loc_18003B7B0
0x18003b7a9  lea     rdi, aException; "Exception"
0x18003b7b0  xor     edx, edx; Val
0x18003b7b2  mov     r8d, 200h; Size
0x18003b7b8  lea     rcx, [rsp+278h+Buffer]; void *
0x18003b7bd  call    memset_0
0x18003b7c2  test    [rbx+4], sil
0x18003b7c6  jz      short loc_18003B7EB
0x18003b7c8  mov     ebp, [rbx+0Ch]
0x18003b7cb  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18003b7d2  test    rax, rax
0x18003b7d5  jz      short loc_18003B81B
0x18003b7d7  mov     r8d, 100h
0x18003b7dd  lea     rdx, [rsp+278h+Buffer]
0x18003b7e2  mov     ecx, ebp
0x18003b7e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b7e9  jmp     short loc_18003B81B
0x18003b7eb  mov     ebp, [rbx+8]
0x18003b7ee  mov     [rsp+278h+Arguments], r15; Arguments
0x18003b7f3  mov     [rsp+278h+nSize], 100h; nSize
0x18003b7fb  lea     rax, [rsp+278h+Buffer]
0x18003b800  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18003b805  mov     r9d, 400h; dwLanguageId
0x18003b80b  mov     r8d, ebp; dwMessageId
0x18003b80e  xor     edx, edx; lpSource
0x18003b810  mov     ecx, 1200h; dwFlags
0x18003b815  call    cs:__imp_FormatMessageW
0x18003b81b  lea     rsi, [r14+1000h]
0x18003b822  mov     r9, [rbx+38h]; unsigned __int16 *
0x18003b826  mov     rax, [rbx+88h]
0x18003b82d  mov     rcx, [rbx+80h]
0x18003b834  mov     rdx, rsi; unsigned __int16 *
0x18003b837  test    r9, r9
0x18003b83a  jz      short loc_18003B85E
0x18003b83c  mov     [rsp+278h+Arguments], rax
0x18003b841  mov     qword ptr [rsp+278h+nSize], rcx
0x18003b846  mov     eax, [rbx+40h]
0x18003b849  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003b84d  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18003b854  mov     rcx, r14; this
0x18003b857  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b85c  jmp     short loc_18003B875
0x18003b85e  mov     [rsp+278h+lpBuffer], rax
0x18003b863  mov     r9, rcx; unsigned __int16 *
0x18003b866  lea     r8, aHsP; "%hs!%p: "
0x18003b86d  mov     rcx, r14; this
0x18003b870  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b875  mov     r14, rax
0x18003b878  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003b87f  test    r9, r9
0x18003b882  jz      short loc_18003B899
0x18003b884  lea     r8, aCallerP; "(caller: %p) "
0x18003b88b  mov     rdx, rsi; unsigned __int16 *
0x18003b88e  mov     rcx, rax; this
0x18003b891  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b896  mov     r14, rax
0x18003b899  call    cs:__imp_GetCurrentThreadId
0x18003b89f  lea     rcx, [rsp+278h+Buffer]
0x18003b8a4  mov     [rsp+278h+var_240], rcx
0x18003b8a9  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003b8ad  mov     [rsp+278h+nSize], eax
0x18003b8b1  mov     eax, [rbx+44h]
0x18003b8b4  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003b8b8  mov     r9, rdi; unsigned __int16 *
0x18003b8bb  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18003b8c2  mov     rdx, rsi; unsigned __int16 *
0x18003b8c5  mov     rcx, r14; this
0x18003b8c8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b8cd  cmp     [rbx+18h], r15
0x18003b8d1  jnz     short loc_18003B8E3
0x18003b8d3  cmp     [rbx+48h], r15
0x18003b8d7  jnz     short loc_18003B8E3
0x18003b8d9  cmp     [rbx+30h], r15
0x18003b8dd  jz      loc_18003B973
0x18003b8e3  lea     r8, asc_18008AA00; "    "
0x18003b8ea  mov     rdx, rsi; unsigned __int16 *
0x18003b8ed  mov     rcx, rax; this
0x18003b8f0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b8f5  mov     r9, [rbx+18h]; unsigned __int16 *
0x18003b8f9  test    r9, r9
0x18003b8fc  jz      short loc_18003B910
0x18003b8fe  lea     r8, aMsgWs; "Msg:[%ws] "
0x18003b905  mov     rdx, rsi; unsigned __int16 *
0x18003b908  mov     rcx, rax; this
0x18003b90b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b910  mov     r9, [rbx+48h]; unsigned __int16 *
0x18003b914  test    r9, r9
0x18003b917  jz      short loc_18003B92B
0x18003b919  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18003b920  mov     rdx, rsi; unsigned __int16 *
0x18003b923  mov     rcx, rax; this
0x18003b926  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b92b  mov     rcx, [rbx+28h]
0x18003b92f  mov     r9, [rbx+30h]; unsigned __int16 *
0x18003b933  mov     rdx, rsi; unsigned __int16 *
0x18003b936  test    rcx, rcx
0x18003b939  jz      short loc_18003B951
0x18003b93b  mov     [rsp+278h+lpBuffer], rcx
0x18003b940  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18003b947  mov     rcx, rax; this
0x18003b94a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b94f  jmp     short loc_18003B973
0x18003b951  mov     rcx, rax; this
0x18003b954  test    r9, r9
0x18003b957  jz      short loc_18003B967
0x18003b959  lea     r8, aHs; "[%hs]\n"
0x18003b960  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b965  jmp     short loc_18003B973
0x18003b967  lea     r8, asc_18008AA78; "\n"
0x18003b96e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003b973  xor     eax, eax
0x18003b975  mov     rcx, [rsp+278h+var_38]
0x18003b97d  xor     rcx, rsp; StackCookie
0x18003b980  call    __security_check_cookie
0x18003b985  mov     rbx, [rsp+278h+arg_8]
0x18003b98d  add     rsp, 250h
0x18003b994  pop     r15
0x18003b996  pop     r14
0x18003b998  pop     rdi
0x18003b999  pop     rsi
0x18003b99a  pop     rbp
0x18003b99b  retn
```
