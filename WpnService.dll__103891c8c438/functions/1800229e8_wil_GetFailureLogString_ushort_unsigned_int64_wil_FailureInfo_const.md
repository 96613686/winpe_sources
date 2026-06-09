# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800229e8`
- end: `0x180022c9e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001199c`
- `0x180015bec`
- `0x1800228b0`

## callees

- `0x18000dd90`
- `0x1800229e8`
- `0x180026200`
- `0x180026cd0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180022b9b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180022b1a`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180022b1a`

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
          v7 = (const char *)&byte_18003A073;
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
0x1800229e8  mov     [rsp+arg_18], rbx
0x1800229ed  push    rbp
0x1800229ee  push    rsi
0x1800229ef  push    rdi
0x1800229f0  push    r14
0x1800229f2  push    r15
0x1800229f4  sub     rsp, 250h
0x1800229fb  mov     rax, cs:__security_cookie
0x180022a02  xor     rax, rsp
0x180022a05  mov     [rsp+278h+var_38], rax
0x180022a0d  mov     rbx, r8
0x180022a10  mov     rsi, rdx
0x180022a13  mov     r14, rcx
0x180022a16  xor     r15d, r15d
0x180022a19  test    rdx, rdx
0x180022a1c  jz      loc_180022C75
0x180022a22  test    rcx, rcx
0x180022a25  jz      loc_180022C75
0x180022a2b  mov     [rcx], r15w
0x180022a2f  mov     rax, cs:g_pfnResultLoggingCallback
0x180022a36  test    rax, rax
0x180022a39  jz      short loc_180022A5C
0x180022a3b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180022a42  jz      short loc_180022A5C
0x180022a44  mov     r8, rdx
0x180022a47  mov     rdx, rcx
0x180022a4a  mov     rcx, rbx
0x180022a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022a52  cmp     [r14], r15w
0x180022a56  jnz     loc_180022C75
0x180022a5c  mov     ecx, [rbx]
0x180022a5e  mov     bpl, 8
0x180022a61  test    ecx, ecx
0x180022a63  jz      short loc_180022AAE
0x180022a65  sub     ecx, 1
0x180022a68  jz      short loc_180022A96
0x180022a6a  sub     ecx, 1
0x180022a6d  jz      short loc_180022A86
0x180022a6f  cmp     ecx, 1
0x180022a72  jz      short loc_180022A7D
0x180022a74  lea     rdi, byte_18003A073
0x180022a7b  jmp     short loc_180022AB5
0x180022a7d  lea     rdi, aFailfast; "FailFast"
0x180022a84  jmp     short loc_180022AB5
0x180022a86  lea     rax, aLoghr; "LogHr"
0x180022a8d  lea     rdi, aLognt; "LogNt"
0x180022a94  jmp     short loc_180022AA4
0x180022a96  lea     rax, aReturnhr; "ReturnHr"
0x180022a9d  lea     rdi, aReturnnt; "ReturnNt"
0x180022aa4  test    [rbx+4], bpl
0x180022aa8  cmovz   rdi, rax
0x180022aac  jmp     short loc_180022AB5
0x180022aae  lea     rdi, aException; "Exception"
0x180022ab5  xor     edx, edx; Val
0x180022ab7  mov     r8d, 200h; Size
0x180022abd  lea     rcx, [rsp+278h+Buffer]; void *
0x180022ac2  call    memset_0
0x180022ac7  test    [rbx+4], bpl
0x180022acb  jz      short loc_180022AF0
0x180022acd  mov     ebp, [rbx+0Ch]
0x180022ad0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180022ad7  test    rax, rax
0x180022ada  jz      short loc_180022B20
0x180022adc  mov     r8d, 100h
0x180022ae2  lea     rdx, [rsp+278h+Buffer]
0x180022ae7  mov     ecx, ebp
0x180022ae9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022aee  jmp     short loc_180022B20
0x180022af0  mov     ebp, [rbx+8]
0x180022af3  mov     [rsp+278h+Arguments], r15; Arguments
0x180022af8  mov     [rsp+278h+nSize], 100h; nSize
0x180022b00  lea     rax, [rsp+278h+Buffer]
0x180022b05  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180022b0a  mov     r9d, 400h; dwLanguageId
0x180022b10  mov     r8d, ebp; dwMessageId
0x180022b13  xor     edx, edx; lpSource
0x180022b15  mov     ecx, 1200h; dwFlags
0x180022b1a  call    cs:__imp_FormatMessageW
0x180022b20  lea     rsi, [r14+rsi*2]
0x180022b24  mov     r9, [rbx+38h]; unsigned __int16 *
0x180022b28  mov     rax, [rbx+88h]
0x180022b2f  mov     rcx, [rbx+80h]
0x180022b36  mov     rdx, rsi; unsigned __int16 *
0x180022b39  test    r9, r9
0x180022b3c  jz      short loc_180022B60
0x180022b3e  mov     [rsp+278h+Arguments], rax
0x180022b43  mov     qword ptr [rsp+278h+nSize], rcx
0x180022b48  mov     eax, [rbx+40h]
0x180022b4b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180022b4f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180022b56  mov     rcx, r14; this
0x180022b59  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022b5e  jmp     short loc_180022B77
0x180022b60  mov     [rsp+278h+lpBuffer], rax
0x180022b65  mov     r9, rcx; unsigned __int16 *
0x180022b68  lea     r8, aHsP; "%hs!%p: "
0x180022b6f  mov     rcx, r14; this
0x180022b72  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022b77  mov     r14, rax
0x180022b7a  mov     r9, [rbx+90h]; unsigned __int16 *
0x180022b81  test    r9, r9
0x180022b84  jz      short loc_180022B9B
0x180022b86  lea     r8, aCallerP; "(caller: %p) "
0x180022b8d  mov     rdx, rsi; unsigned __int16 *
0x180022b90  mov     rcx, rax; this
0x180022b93  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022b98  mov     r14, rax
0x180022b9b  call    cs:__imp_GetCurrentThreadId
0x180022ba1  lea     rcx, [rsp+278h+Buffer]
0x180022ba6  mov     [rsp+278h+var_240], rcx
0x180022bab  mov     dword ptr [rsp+278h+Arguments], ebp
0x180022baf  mov     [rsp+278h+nSize], eax
0x180022bb3  mov     eax, [rbx+44h]
0x180022bb6  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180022bba  mov     r9, rdi; unsigned __int16 *
0x180022bbd  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180022bc4  mov     rdx, rsi; unsigned __int16 *
0x180022bc7  mov     rcx, r14; this
0x180022bca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022bcf  cmp     [rbx+18h], r15
0x180022bd3  jnz     short loc_180022BE5
0x180022bd5  cmp     [rbx+48h], r15
0x180022bd9  jnz     short loc_180022BE5
0x180022bdb  cmp     [rbx+30h], r15
0x180022bdf  jz      loc_180022C75
0x180022be5  lea     r8, asc_18003A8B0; "    "
0x180022bec  mov     rdx, rsi; unsigned __int16 *
0x180022bef  mov     rcx, rax; this
0x180022bf2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022bf7  mov     r9, [rbx+18h]; unsigned __int16 *
0x180022bfb  test    r9, r9
0x180022bfe  jz      short loc_180022C12
0x180022c00  lea     r8, aMsgWs; "Msg:[%ws] "
0x180022c07  mov     rdx, rsi; unsigned __int16 *
0x180022c0a  mov     rcx, rax; this
0x180022c0d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c12  mov     r9, [rbx+48h]; unsigned __int16 *
0x180022c16  test    r9, r9
0x180022c19  jz      short loc_180022C2D
0x180022c1b  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180022c22  mov     rdx, rsi; unsigned __int16 *
0x180022c25  mov     rcx, rax; this
0x180022c28  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c2d  mov     rcx, [rbx+28h]
0x180022c31  mov     r9, [rbx+30h]; unsigned __int16 *
0x180022c35  mov     rdx, rsi; unsigned __int16 *
0x180022c38  test    rcx, rcx
0x180022c3b  jz      short loc_180022C53
0x180022c3d  mov     [rsp+278h+lpBuffer], rcx
0x180022c42  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180022c49  mov     rcx, rax; this
0x180022c4c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c51  jmp     short loc_180022C75
0x180022c53  mov     rcx, rax; this
0x180022c56  test    r9, r9
0x180022c59  jz      short loc_180022C69
0x180022c5b  lea     r8, aHs; "[%hs]\n"
0x180022c62  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c67  jmp     short loc_180022C75
0x180022c69  lea     r8, asc_18003A928; "\n"
0x180022c70  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180022c75  xor     eax, eax
0x180022c77  mov     rcx, [rsp+278h+var_38]
0x180022c7f  xor     rcx, rsp; StackCookie
0x180022c82  call    __security_check_cookie
0x180022c87  mov     rbx, [rsp+278h+arg_18]
0x180022c8f  add     rsp, 250h
0x180022c96  pop     r15
0x180022c98  pop     r14
0x180022c9a  pop     rdi
0x180022c9b  pop     rsi
0x180022c9c  pop     rbp
0x180022c9d  retn
```
