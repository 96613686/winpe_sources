# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140011cf4`
- end: `0x140011faa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140012574`
- `0x140012c2c`
- `0x1400150e0`

## callees

- `0x14000f6a0`
- `0x140010514`
- `0x140011cf4`
- `0x140012870`
- `0x140071010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140011e26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140011e26`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011ea7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140011ea7`

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
          v7 = (const char *)&word_1400793A6;
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
0x140011cf4  mov     [rsp+arg_18], rbx
0x140011cf9  push    rbp
0x140011cfa  push    rsi
0x140011cfb  push    rdi
0x140011cfc  push    r14
0x140011cfe  push    r15
0x140011d00  sub     rsp, 250h
0x140011d07  mov     rax, cs:__security_cookie
0x140011d0e  xor     rax, rsp
0x140011d11  mov     [rsp+278h+var_38], rax
0x140011d19  mov     rbx, r8
0x140011d1c  mov     rsi, rdx
0x140011d1f  mov     r14, rcx
0x140011d22  xor     r15d, r15d
0x140011d25  test    rdx, rdx
0x140011d28  jz      loc_140011F81
0x140011d2e  test    rcx, rcx
0x140011d31  jz      loc_140011F81
0x140011d37  mov     [rcx], r15w
0x140011d3b  mov     rax, cs:g_pfnResultLoggingCallback
0x140011d42  test    rax, rax
0x140011d45  jz      short loc_140011D68
0x140011d47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140011d4e  jz      short loc_140011D68
0x140011d50  mov     r8, rdx
0x140011d53  mov     rdx, rcx
0x140011d56  mov     rcx, rbx
0x140011d59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011d5e  cmp     [r14], r15w
0x140011d62  jnz     loc_140011F81
0x140011d68  mov     ecx, [rbx]
0x140011d6a  mov     bpl, 8
0x140011d6d  test    ecx, ecx
0x140011d6f  jz      short loc_140011DBA
0x140011d71  sub     ecx, 1
0x140011d74  jz      short loc_140011DA2
0x140011d76  sub     ecx, 1
0x140011d79  jz      short loc_140011D92
0x140011d7b  cmp     ecx, 1
0x140011d7e  jz      short loc_140011D89
0x140011d80  lea     rdi, word_1400793A6
0x140011d87  jmp     short loc_140011DC1
0x140011d89  lea     rdi, aFailfast; "FailFast"
0x140011d90  jmp     short loc_140011DC1
0x140011d92  lea     rax, aLoghr; "LogHr"
0x140011d99  lea     rdi, aLognt; "LogNt"
0x140011da0  jmp     short loc_140011DB0
0x140011da2  lea     rax, aReturnhr; "ReturnHr"
0x140011da9  lea     rdi, aReturnnt; "ReturnNt"
0x140011db0  test    [rbx+4], bpl
0x140011db4  cmovz   rdi, rax
0x140011db8  jmp     short loc_140011DC1
0x140011dba  lea     rdi, aException; "Exception"
0x140011dc1  xor     edx, edx; Val
0x140011dc3  mov     r8d, 200h; Size
0x140011dc9  lea     rcx, [rsp+278h+Buffer]; void *
0x140011dce  call    memset_0
0x140011dd3  test    [rbx+4], bpl
0x140011dd7  jz      short loc_140011DFC
0x140011dd9  mov     ebp, [rbx+0Ch]
0x140011ddc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140011de3  test    rax, rax
0x140011de6  jz      short loc_140011E2C
0x140011de8  mov     r8d, 100h
0x140011dee  lea     rdx, [rsp+278h+Buffer]
0x140011df3  mov     ecx, ebp
0x140011df5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011dfa  jmp     short loc_140011E2C
0x140011dfc  mov     ebp, [rbx+8]
0x140011dff  mov     [rsp+278h+Arguments], r15; Arguments
0x140011e04  mov     [rsp+278h+nSize], 100h; nSize
0x140011e0c  lea     rax, [rsp+278h+Buffer]
0x140011e11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140011e16  mov     r9d, 400h; dwLanguageId
0x140011e1c  mov     r8d, ebp; dwMessageId
0x140011e1f  xor     edx, edx; lpSource
0x140011e21  mov     ecx, 1200h; dwFlags
0x140011e26  call    cs:__imp_FormatMessageW
0x140011e2c  lea     rsi, [r14+rsi*2]
0x140011e30  mov     r9, [rbx+38h]; unsigned __int16 *
0x140011e34  mov     rax, [rbx+88h]
0x140011e3b  mov     rcx, [rbx+80h]
0x140011e42  mov     rdx, rsi; unsigned __int16 *
0x140011e45  test    r9, r9
0x140011e48  jz      short loc_140011E6C
0x140011e4a  mov     [rsp+278h+Arguments], rax
0x140011e4f  mov     qword ptr [rsp+278h+nSize], rcx
0x140011e54  mov     eax, [rbx+40h]
0x140011e57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140011e5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140011e62  mov     rcx, r14; this
0x140011e65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011e6a  jmp     short loc_140011E83
0x140011e6c  mov     [rsp+278h+lpBuffer], rax
0x140011e71  mov     r9, rcx; unsigned __int16 *
0x140011e74  lea     r8, aHsP; "%hs!%p: "
0x140011e7b  mov     rcx, r14; this
0x140011e7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011e83  mov     r14, rax
0x140011e86  mov     r9, [rbx+90h]; unsigned __int16 *
0x140011e8d  test    r9, r9
0x140011e90  jz      short loc_140011EA7
0x140011e92  lea     r8, aCallerP; "(caller: %p) "
0x140011e99  mov     rdx, rsi; unsigned __int16 *
0x140011e9c  mov     rcx, rax; this
0x140011e9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011ea4  mov     r14, rax
0x140011ea7  call    cs:__imp_GetCurrentThreadId
0x140011ead  lea     rcx, [rsp+278h+Buffer]
0x140011eb2  mov     [rsp+278h+var_240], rcx
0x140011eb7  mov     dword ptr [rsp+278h+Arguments], ebp
0x140011ebb  mov     [rsp+278h+nSize], eax
0x140011ebf  mov     eax, [rbx+44h]
0x140011ec2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140011ec6  mov     r9, rdi; unsigned __int16 *
0x140011ec9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140011ed0  mov     rdx, rsi; unsigned __int16 *
0x140011ed3  mov     rcx, r14; this
0x140011ed6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011edb  cmp     [rbx+18h], r15
0x140011edf  jnz     short loc_140011EF1
0x140011ee1  cmp     [rbx+48h], r15
0x140011ee5  jnz     short loc_140011EF1
0x140011ee7  cmp     [rbx+30h], r15
0x140011eeb  jz      loc_140011F81
0x140011ef1  lea     r8, asc_140079948; "    "
0x140011ef8  mov     rdx, rsi; unsigned __int16 *
0x140011efb  mov     rcx, rax; this
0x140011efe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f03  mov     r9, [rbx+18h]; unsigned __int16 *
0x140011f07  test    r9, r9
0x140011f0a  jz      short loc_140011F1E
0x140011f0c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140011f13  mov     rdx, rsi; unsigned __int16 *
0x140011f16  mov     rcx, rax; this
0x140011f19  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f1e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140011f22  test    r9, r9
0x140011f25  jz      short loc_140011F39
0x140011f27  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140011f2e  mov     rdx, rsi; unsigned __int16 *
0x140011f31  mov     rcx, rax; this
0x140011f34  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f39  mov     rcx, [rbx+28h]
0x140011f3d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140011f41  mov     rdx, rsi; unsigned __int16 *
0x140011f44  test    rcx, rcx
0x140011f47  jz      short loc_140011F5F
0x140011f49  mov     [rsp+278h+lpBuffer], rcx
0x140011f4e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140011f55  mov     rcx, rax; this
0x140011f58  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f5d  jmp     short loc_140011F81
0x140011f5f  mov     rcx, rax; this
0x140011f62  test    r9, r9
0x140011f65  jz      short loc_140011F75
0x140011f67  lea     r8, aHs; "[%hs]\n"
0x140011f6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f73  jmp     short loc_140011F81
0x140011f75  lea     r8, asc_1400799C0; "\n"
0x140011f7c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140011f81  xor     eax, eax
0x140011f83  mov     rcx, [rsp+278h+var_38]
0x140011f8b  xor     rcx, rsp; StackCookie
0x140011f8e  call    __security_check_cookie
0x140011f93  mov     rbx, [rsp+278h+arg_18]
0x140011f9b  add     rsp, 250h
0x140011fa2  pop     r15
0x140011fa4  pop     r14
0x140011fa6  pop     rdi
0x140011fa7  pop     rsi
0x140011fa8  pop     rbp
0x140011fa9  retn
```
