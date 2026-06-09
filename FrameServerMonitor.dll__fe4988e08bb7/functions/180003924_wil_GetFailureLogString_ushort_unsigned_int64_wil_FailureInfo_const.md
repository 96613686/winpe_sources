# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180003924`
- end: `0x180003bda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180002aec`
- `0x1800042cc`

## callees

- `0x1800019f0`
- `0x180002346`
- `0x180003924`
- `0x1800045dc`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ad7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003ad7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003a56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180003a56`

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
          v8 = Format;
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
0x180003924  mov     [rsp+arg_18], rbx
0x180003929  push    rbp
0x18000392a  push    rsi
0x18000392b  push    rdi
0x18000392c  push    r14
0x18000392e  push    r15
0x180003930  sub     rsp, 250h
0x180003937  mov     rax, cs:__security_cookie
0x18000393e  xor     rax, rsp
0x180003941  mov     [rsp+278h+var_38], rax
0x180003949  xor     r15d, r15d
0x18000394c  mov     rbx, r8
0x18000394f  mov     rsi, rdx
0x180003952  mov     r14, rcx
0x180003955  test    rdx, rdx
0x180003958  jz      loc_180003BB1
0x18000395e  test    rcx, rcx
0x180003961  jz      loc_180003BB1
0x180003967  mov     rax, cs:g_pfnResultLoggingCallback
0x18000396e  mov     [rcx], r15w
0x180003972  test    rax, rax
0x180003975  jz      short loc_180003998
0x180003977  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000397e  jz      short loc_180003998
0x180003980  mov     r8, rdx
0x180003983  mov     rdx, rcx
0x180003986  mov     rcx, rbx
0x180003989  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000398e  cmp     [r14], r15w
0x180003992  jnz     loc_180003BB1
0x180003998  mov     ecx, [rbx]
0x18000399a  mov     bpl, 8
0x18000399d  test    ecx, ecx
0x18000399f  jz      short loc_1800039EA
0x1800039a1  sub     ecx, 1
0x1800039a4  jz      short loc_1800039D2
0x1800039a6  sub     ecx, 1
0x1800039a9  jz      short loc_1800039C2
0x1800039ab  cmp     ecx, 1
0x1800039ae  jz      short loc_1800039B9
0x1800039b0  lea     rdi, Format
0x1800039b7  jmp     short loc_1800039F1
0x1800039b9  lea     rdi, aFailfast; "FailFast"
0x1800039c0  jmp     short loc_1800039F1
0x1800039c2  lea     rax, aLoghr; "LogHr"
0x1800039c9  lea     rdi, aLognt; "LogNt"
0x1800039d0  jmp     short loc_1800039E0
0x1800039d2  lea     rax, aReturnhr; "ReturnHr"
0x1800039d9  lea     rdi, aReturnnt; "ReturnNt"
0x1800039e0  test    [rbx+4], bpl
0x1800039e4  cmovz   rdi, rax
0x1800039e8  jmp     short loc_1800039F1
0x1800039ea  lea     rdi, aException; "Exception"
0x1800039f1  xor     edx, edx; Val
0x1800039f3  lea     rcx, [rsp+278h+Buffer]; void *
0x1800039f8  mov     r8d, 200h; Size
0x1800039fe  call    memset_0
0x180003a03  test    [rbx+4], bpl
0x180003a07  jz      short loc_180003A2C
0x180003a09  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180003a10  mov     ebp, [rbx+0Ch]
0x180003a13  test    rax, rax
0x180003a16  jz      short loc_180003A5C
0x180003a18  mov     r8d, 100h
0x180003a1e  lea     rdx, [rsp+278h+Buffer]
0x180003a23  mov     ecx, ebp
0x180003a25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a2a  jmp     short loc_180003A5C
0x180003a2c  mov     ebp, [rbx+8]
0x180003a2f  lea     rax, [rsp+278h+Buffer]
0x180003a34  mov     [rsp+278h+Arguments], r15; Arguments
0x180003a39  mov     r8d, ebp; dwMessageId
0x180003a3c  mov     [rsp+278h+nSize], 100h; nSize
0x180003a44  mov     r9d, 400h; dwLanguageId
0x180003a4a  xor     edx, edx; lpSource
0x180003a4c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180003a51  mov     ecx, 1200h; dwFlags
0x180003a56  call    cs:__imp_FormatMessageW
0x180003a5c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180003a60  lea     rsi, [r14+rsi*2]
0x180003a64  mov     rax, [rbx+88h]
0x180003a6b  mov     rdx, rsi; unsigned __int16 *
0x180003a6e  mov     rcx, [rbx+80h]
0x180003a75  test    r9, r9
0x180003a78  jz      short loc_180003A9C
0x180003a7a  mov     [rsp+278h+Arguments], rax
0x180003a7f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180003a86  mov     eax, [rbx+40h]
0x180003a89  mov     qword ptr [rsp+278h+nSize], rcx
0x180003a8e  mov     rcx, r14; this
0x180003a91  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003a95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003a9a  jmp     short loc_180003AB3
0x180003a9c  mov     r9, rcx; unsigned __int16 *
0x180003a9f  mov     [rsp+278h+lpBuffer], rax
0x180003aa4  mov     rcx, r14; this
0x180003aa7  lea     r8, aHsP; "%hs!%p: "
0x180003aae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ab3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180003aba  mov     r14, rax
0x180003abd  test    r9, r9
0x180003ac0  jz      short loc_180003AD7
0x180003ac2  lea     r8, aCallerP; "(caller: %p) "
0x180003ac9  mov     rdx, rsi; unsigned __int16 *
0x180003acc  mov     rcx, rax; this
0x180003acf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ad4  mov     r14, rax
0x180003ad7  call    cs:__imp_GetCurrentThreadId
0x180003add  lea     rcx, [rsp+278h+Buffer]
0x180003ae2  mov     r9, rdi; unsigned __int16 *
0x180003ae5  mov     [rsp+278h+var_240], rcx
0x180003aea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180003af1  mov     dword ptr [rsp+278h+Arguments], ebp
0x180003af5  mov     rdx, rsi; unsigned __int16 *
0x180003af8  mov     [rsp+278h+nSize], eax
0x180003afc  mov     rcx, r14; this
0x180003aff  mov     eax, [rbx+44h]
0x180003b02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180003b06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b0b  cmp     [rbx+18h], r15
0x180003b0f  jnz     short loc_180003B21
0x180003b11  cmp     [rbx+48h], r15
0x180003b15  jnz     short loc_180003B21
0x180003b17  cmp     [rbx+30h], r15
0x180003b1b  jz      loc_180003BB1
0x180003b21  lea     r8, asc_180051C10; "    "
0x180003b28  mov     rdx, rsi; unsigned __int16 *
0x180003b2b  mov     rcx, rax; this
0x180003b2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b33  mov     r9, [rbx+18h]; unsigned __int16 *
0x180003b37  test    r9, r9
0x180003b3a  jz      short loc_180003B4E
0x180003b3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180003b43  mov     rdx, rsi; unsigned __int16 *
0x180003b46  mov     rcx, rax; this
0x180003b49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180003b52  test    r9, r9
0x180003b55  jz      short loc_180003B69
0x180003b57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180003b5e  mov     rdx, rsi; unsigned __int16 *
0x180003b61  mov     rcx, rax; this
0x180003b64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b69  mov     rcx, [rbx+28h]
0x180003b6d  mov     rdx, rsi; unsigned __int16 *
0x180003b70  mov     r9, [rbx+30h]; unsigned __int16 *
0x180003b74  test    rcx, rcx
0x180003b77  jz      short loc_180003B8F
0x180003b79  mov     [rsp+278h+lpBuffer], rcx
0x180003b7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180003b85  mov     rcx, rax; this
0x180003b88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003b8d  jmp     short loc_180003BB1
0x180003b8f  mov     rcx, rax; this
0x180003b92  test    r9, r9
0x180003b95  jz      short loc_180003BA5
0x180003b97  lea     r8, aHs; "[%hs]\n"
0x180003b9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003ba3  jmp     short loc_180003BB1
0x180003ba5  lea     r8, asc_180051C88; "\n"
0x180003bac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180003bb1  xor     eax, eax
0x180003bb3  mov     rcx, [rsp+278h+var_38]
0x180003bbb  xor     rcx, rsp; StackCookie
0x180003bbe  call    __security_check_cookie
0x180003bc3  mov     rbx, [rsp+278h+arg_18]
0x180003bcb  add     rsp, 250h
0x180003bd2  pop     r15
0x180003bd4  pop     r14
0x180003bd6  pop     rdi
0x180003bd7  pop     rsi
0x180003bd8  pop     rbp
0x180003bd9  retn
```
