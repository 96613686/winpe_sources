# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006be4`
- end: `0x180006e9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800050b0`
- `0x18000785c`
- `0x180007f3c`
- `0x18000aa60`

## callees

- `0x180003450`
- `0x180003fe4`
- `0x180006be4`
- `0x180007b5c`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006d16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006d16`

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
          v7 = byte_18004A6C5;
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
0x180006be4  mov     [rsp+arg_18], rbx
0x180006be9  push    rbp
0x180006bea  push    rsi
0x180006beb  push    rdi
0x180006bec  push    r14
0x180006bee  push    r15
0x180006bf0  sub     rsp, 250h
0x180006bf7  mov     rax, cs:__security_cookie
0x180006bfe  xor     rax, rsp
0x180006c01  mov     [rsp+278h+var_38], rax
0x180006c09  mov     rbx, r8
0x180006c0c  mov     rsi, rdx
0x180006c0f  mov     r14, rcx
0x180006c12  xor     r15d, r15d
0x180006c15  test    rdx, rdx
0x180006c18  jz      loc_180006E71
0x180006c1e  test    rcx, rcx
0x180006c21  jz      loc_180006E71
0x180006c27  mov     [rcx], r15w
0x180006c2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006c32  test    rax, rax
0x180006c35  jz      short loc_180006C58
0x180006c37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006c3e  jz      short loc_180006C58
0x180006c40  mov     r8, rdx
0x180006c43  mov     rdx, rcx
0x180006c46  mov     rcx, rbx
0x180006c49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006c4e  cmp     [r14], r15w
0x180006c52  jnz     loc_180006E71
0x180006c58  mov     ecx, [rbx]
0x180006c5a  mov     bpl, 8
0x180006c5d  test    ecx, ecx
0x180006c5f  jz      short loc_180006CAA
0x180006c61  sub     ecx, 1
0x180006c64  jz      short loc_180006C92
0x180006c66  sub     ecx, 1
0x180006c69  jz      short loc_180006C82
0x180006c6b  cmp     ecx, 1
0x180006c6e  jz      short loc_180006C79
0x180006c70  lea     rdi, byte_18004A6C5
0x180006c77  jmp     short loc_180006CB1
0x180006c79  lea     rdi, aFailfast; "FailFast"
0x180006c80  jmp     short loc_180006CB1
0x180006c82  lea     rax, aLoghr; "LogHr"
0x180006c89  lea     rdi, aLognt; "LogNt"
0x180006c90  jmp     short loc_180006CA0
0x180006c92  lea     rax, aReturnhr; "ReturnHr"
0x180006c99  lea     rdi, aReturnnt; "ReturnNt"
0x180006ca0  test    [rbx+4], bpl
0x180006ca4  cmovz   rdi, rax
0x180006ca8  jmp     short loc_180006CB1
0x180006caa  lea     rdi, aException; "Exception"
0x180006cb1  xor     edx, edx; Val
0x180006cb3  mov     r8d, 200h; Size
0x180006cb9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006cbe  call    memset_0
0x180006cc3  test    [rbx+4], bpl
0x180006cc7  jz      short loc_180006CEC
0x180006cc9  mov     ebp, [rbx+0Ch]
0x180006ccc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006cd3  test    rax, rax
0x180006cd6  jz      short loc_180006D1C
0x180006cd8  mov     r8d, 100h
0x180006cde  lea     rdx, [rsp+278h+Buffer]
0x180006ce3  mov     ecx, ebp
0x180006ce5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006cea  jmp     short loc_180006D1C
0x180006cec  mov     ebp, [rbx+8]
0x180006cef  mov     [rsp+278h+Arguments], r15; Arguments
0x180006cf4  mov     [rsp+278h+nSize], 100h; nSize
0x180006cfc  lea     rax, [rsp+278h+Buffer]
0x180006d01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006d06  mov     r9d, 400h; dwLanguageId
0x180006d0c  mov     r8d, ebp; dwMessageId
0x180006d0f  xor     edx, edx; lpSource
0x180006d11  mov     ecx, 1200h; dwFlags
0x180006d16  call    cs:__imp_FormatMessageW
0x180006d1c  lea     rsi, [r14+rsi*2]
0x180006d20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006d24  mov     rax, [rbx+88h]
0x180006d2b  mov     rcx, [rbx+80h]
0x180006d32  mov     rdx, rsi; unsigned __int16 *
0x180006d35  test    r9, r9
0x180006d38  jz      short loc_180006D5C
0x180006d3a  mov     [rsp+278h+Arguments], rax
0x180006d3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006d44  mov     eax, [rbx+40h]
0x180006d47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006d4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006d52  mov     rcx, r14; this
0x180006d55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d5a  jmp     short loc_180006D73
0x180006d5c  mov     [rsp+278h+lpBuffer], rax
0x180006d61  mov     r9, rcx; unsigned __int16 *
0x180006d64  lea     r8, aHsP; "%hs!%p: "
0x180006d6b  mov     rcx, r14; this
0x180006d6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d73  mov     r14, rax
0x180006d76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006d7d  test    r9, r9
0x180006d80  jz      short loc_180006D97
0x180006d82  lea     r8, aCallerP; "(caller: %p) "
0x180006d89  mov     rdx, rsi; unsigned __int16 *
0x180006d8c  mov     rcx, rax; this
0x180006d8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006d94  mov     r14, rax
0x180006d97  call    cs:__imp_GetCurrentThreadId
0x180006d9d  lea     rcx, [rsp+278h+Buffer]
0x180006da2  mov     [rsp+278h+var_240], rcx
0x180006da7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006dab  mov     [rsp+278h+nSize], eax
0x180006daf  mov     eax, [rbx+44h]
0x180006db2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006db6  mov     r9, rdi; unsigned __int16 *
0x180006db9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006dc0  mov     rdx, rsi; unsigned __int16 *
0x180006dc3  mov     rcx, r14; this
0x180006dc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006dcb  cmp     [rbx+18h], r15
0x180006dcf  jnz     short loc_180006DE1
0x180006dd1  cmp     [rbx+48h], r15
0x180006dd5  jnz     short loc_180006DE1
0x180006dd7  cmp     [rbx+30h], r15
0x180006ddb  jz      loc_180006E71
0x180006de1  lea     r8, asc_18004A7C8; "    "
0x180006de8  mov     rdx, rsi; unsigned __int16 *
0x180006deb  mov     rcx, rax; this
0x180006dee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006df3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006df7  test    r9, r9
0x180006dfa  jz      short loc_180006E0E
0x180006dfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006e03  mov     rdx, rsi; unsigned __int16 *
0x180006e06  mov     rcx, rax; this
0x180006e09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006e12  test    r9, r9
0x180006e15  jz      short loc_180006E29
0x180006e17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006e1e  mov     rdx, rsi; unsigned __int16 *
0x180006e21  mov     rcx, rax; this
0x180006e24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e29  mov     rcx, [rbx+28h]
0x180006e2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006e31  mov     rdx, rsi; unsigned __int16 *
0x180006e34  test    rcx, rcx
0x180006e37  jz      short loc_180006E4F
0x180006e39  mov     [rsp+278h+lpBuffer], rcx
0x180006e3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006e45  mov     rcx, rax; this
0x180006e48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e4d  jmp     short loc_180006E71
0x180006e4f  mov     rcx, rax; this
0x180006e52  test    r9, r9
0x180006e55  jz      short loc_180006E65
0x180006e57  lea     r8, aHs_0; "[%hs]\n"
0x180006e5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e63  jmp     short loc_180006E71
0x180006e65  lea     r8, asc_18004A840; "\n"
0x180006e6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006e71  xor     eax, eax
0x180006e73  mov     rcx, [rsp+278h+var_38]
0x180006e7b  xor     rcx, rsp; StackCookie
0x180006e7e  call    __security_check_cookie
0x180006e83  mov     rbx, [rsp+278h+arg_18]
0x180006e8b  add     rsp, 250h
0x180006e92  pop     r15
0x180006e94  pop     r14
0x180006e96  pop     rdi
0x180006e97  pop     rsi
0x180006e98  pop     rbp
0x180006e99  retn
```
