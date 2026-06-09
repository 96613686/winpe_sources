# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800069e4`
- end: `0x180006c9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800045e0`
- `0x180007ab4`
- `0x180007fd0`
- `0x18000ab60`

## callees

- `0x180002a70`
- `0x18000365c`
- `0x1800069e4`
- `0x180007db4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006b97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006b16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006b16`

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
          v7 = (const char *)&byte_1800150A8;
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
0x1800069e4  mov     [rsp+arg_18], rbx
0x1800069e9  push    rbp
0x1800069ea  push    rsi
0x1800069eb  push    rdi
0x1800069ec  push    r14
0x1800069ee  push    r15
0x1800069f0  sub     rsp, 250h
0x1800069f7  mov     rax, cs:__security_cookie
0x1800069fe  xor     rax, rsp
0x180006a01  mov     [rsp+278h+var_38], rax
0x180006a09  mov     rbx, r8
0x180006a0c  mov     rsi, rdx
0x180006a0f  mov     r14, rcx
0x180006a12  xor     r15d, r15d
0x180006a15  test    rdx, rdx
0x180006a18  jz      loc_180006C71
0x180006a1e  test    rcx, rcx
0x180006a21  jz      loc_180006C71
0x180006a27  mov     [rcx], r15w
0x180006a2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a32  test    rax, rax
0x180006a35  jz      short loc_180006A58
0x180006a37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006a3e  jz      short loc_180006A58
0x180006a40  mov     r8, rdx
0x180006a43  mov     rdx, rcx
0x180006a46  mov     rcx, rbx
0x180006a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a4e  cmp     [r14], r15w
0x180006a52  jnz     loc_180006C71
0x180006a58  mov     ecx, [rbx]
0x180006a5a  mov     bpl, 8
0x180006a5d  test    ecx, ecx
0x180006a5f  jz      short loc_180006AAA
0x180006a61  sub     ecx, 1
0x180006a64  jz      short loc_180006A92
0x180006a66  sub     ecx, 1
0x180006a69  jz      short loc_180006A82
0x180006a6b  cmp     ecx, 1
0x180006a6e  jz      short loc_180006A79
0x180006a70  lea     rdi, byte_1800150A8
0x180006a77  jmp     short loc_180006AB1
0x180006a79  lea     rdi, aFailfast; "FailFast"
0x180006a80  jmp     short loc_180006AB1
0x180006a82  lea     rax, aLoghr; "LogHr"
0x180006a89  lea     rdi, aLognt; "LogNt"
0x180006a90  jmp     short loc_180006AA0
0x180006a92  lea     rax, aReturnhr; "ReturnHr"
0x180006a99  lea     rdi, aReturnnt; "ReturnNt"
0x180006aa0  test    [rbx+4], bpl
0x180006aa4  cmovz   rdi, rax
0x180006aa8  jmp     short loc_180006AB1
0x180006aaa  lea     rdi, aException; "Exception"
0x180006ab1  xor     edx, edx; Val
0x180006ab3  mov     r8d, 200h; Size
0x180006ab9  lea     rcx, [rsp+278h+Buffer]; void *
0x180006abe  call    memset_0
0x180006ac3  test    [rbx+4], bpl
0x180006ac7  jz      short loc_180006AEC
0x180006ac9  mov     ebp, [rbx+0Ch]
0x180006acc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006ad3  test    rax, rax
0x180006ad6  jz      short loc_180006B1C
0x180006ad8  mov     r8d, 100h
0x180006ade  lea     rdx, [rsp+278h+Buffer]
0x180006ae3  mov     ecx, ebp
0x180006ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006aea  jmp     short loc_180006B1C
0x180006aec  mov     ebp, [rbx+8]
0x180006aef  mov     [rsp+278h+Arguments], r15; Arguments
0x180006af4  mov     [rsp+278h+nSize], 100h; nSize
0x180006afc  lea     rax, [rsp+278h+Buffer]
0x180006b01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006b06  mov     r9d, 400h; dwLanguageId
0x180006b0c  mov     r8d, ebp; dwMessageId
0x180006b0f  xor     edx, edx; lpSource
0x180006b11  mov     ecx, 1200h; dwFlags
0x180006b16  call    cs:__imp_FormatMessageW
0x180006b1c  lea     rsi, [r14+rsi*2]
0x180006b20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006b24  mov     rax, [rbx+88h]
0x180006b2b  mov     rcx, [rbx+80h]
0x180006b32  mov     rdx, rsi; unsigned __int16 *
0x180006b35  test    r9, r9
0x180006b38  jz      short loc_180006B5C
0x180006b3a  mov     [rsp+278h+Arguments], rax
0x180006b3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180006b44  mov     eax, [rbx+40h]
0x180006b47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006b4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180006b52  mov     rcx, r14; this
0x180006b55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006b5a  jmp     short loc_180006B73
0x180006b5c  mov     [rsp+278h+lpBuffer], rax
0x180006b61  mov     r9, rcx; unsigned __int16 *
0x180006b64  lea     r8, aHsP; "%hs!%p: "
0x180006b6b  mov     rcx, r14; this
0x180006b6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006b73  mov     r14, rax
0x180006b76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180006b7d  test    r9, r9
0x180006b80  jz      short loc_180006B97
0x180006b82  lea     r8, aCallerP; "(caller: %p) "
0x180006b89  mov     rdx, rsi; unsigned __int16 *
0x180006b8c  mov     rcx, rax; this
0x180006b8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006b94  mov     r14, rax
0x180006b97  call    cs:__imp_GetCurrentThreadId
0x180006b9d  lea     rcx, [rsp+278h+Buffer]
0x180006ba2  mov     [rsp+278h+var_240], rcx
0x180006ba7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180006bab  mov     [rsp+278h+nSize], eax
0x180006baf  mov     eax, [rbx+44h]
0x180006bb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006bb6  mov     r9, rdi; unsigned __int16 *
0x180006bb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180006bc0  mov     rdx, rsi; unsigned __int16 *
0x180006bc3  mov     rcx, r14; this
0x180006bc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006bcb  cmp     [rbx+18h], r15
0x180006bcf  jnz     short loc_180006BE1
0x180006bd1  cmp     [rbx+48h], r15
0x180006bd5  jnz     short loc_180006BE1
0x180006bd7  cmp     [rbx+30h], r15
0x180006bdb  jz      loc_180006C71
0x180006be1  lea     r8, asc_180015198; "    "
0x180006be8  mov     rdx, rsi; unsigned __int16 *
0x180006beb  mov     rcx, rax; this
0x180006bee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006bf3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180006bf7  test    r9, r9
0x180006bfa  jz      short loc_180006C0E
0x180006bfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180006c03  mov     rdx, rsi; unsigned __int16 *
0x180006c06  mov     rcx, rax; this
0x180006c09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180006c12  test    r9, r9
0x180006c15  jz      short loc_180006C29
0x180006c17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006c1e  mov     rdx, rsi; unsigned __int16 *
0x180006c21  mov     rcx, rax; this
0x180006c24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c29  mov     rcx, [rbx+28h]
0x180006c2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006c31  mov     rdx, rsi; unsigned __int16 *
0x180006c34  test    rcx, rcx
0x180006c37  jz      short loc_180006C4F
0x180006c39  mov     [rsp+278h+lpBuffer], rcx
0x180006c3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006c45  mov     rcx, rax; this
0x180006c48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c4d  jmp     short loc_180006C71
0x180006c4f  mov     rcx, rax; this
0x180006c52  test    r9, r9
0x180006c55  jz      short loc_180006C65
0x180006c57  lea     r8, aHs; "[%hs]\n"
0x180006c5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c63  jmp     short loc_180006C71
0x180006c65  lea     r8, asc_180015210; "\n"
0x180006c6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006c71  xor     eax, eax
0x180006c73  mov     rcx, [rsp+278h+var_38]
0x180006c7b  xor     rcx, rsp; StackCookie
0x180006c7e  call    __security_check_cookie
0x180006c83  mov     rbx, [rsp+278h+arg_18]
0x180006c8b  add     rsp, 250h
0x180006c92  pop     r15
0x180006c94  pop     r14
0x180006c96  pop     rdi
0x180006c97  pop     rsi
0x180006c98  pop     rbp
0x180006c99  retn
```
