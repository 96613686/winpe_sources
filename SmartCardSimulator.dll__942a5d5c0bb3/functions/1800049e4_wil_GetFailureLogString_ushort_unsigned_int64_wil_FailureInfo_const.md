# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800049e4`
- end: `0x180004c9a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003c04`
- `0x18000537c`
- `0x180005834`
- `0x180006990`

## callees

- `0x1800049e4`
- `0x18000567c`
- `0x1800586c6`
- `0x180058700`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b97`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b16`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004b16`

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
          v7 = (const char *)&qword_1800634A8;
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
0x1800049e4  mov     [rsp+arg_18], rbx
0x1800049e9  push    rbp
0x1800049ea  push    rsi
0x1800049eb  push    rdi
0x1800049ec  push    r14
0x1800049ee  push    r15
0x1800049f0  sub     rsp, 250h
0x1800049f7  mov     rax, cs:__security_cookie
0x1800049fe  xor     rax, rsp
0x180004a01  mov     [rsp+278h+var_38], rax
0x180004a09  mov     rbx, r8
0x180004a0c  mov     rsi, rdx
0x180004a0f  mov     r14, rcx
0x180004a12  xor     r15d, r15d
0x180004a15  test    rdx, rdx
0x180004a18  jz      loc_180004C71
0x180004a1e  test    rcx, rcx
0x180004a21  jz      loc_180004C71
0x180004a27  mov     [rcx], r15w
0x180004a2b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a32  test    rax, rax
0x180004a35  jz      short loc_180004A58
0x180004a37  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004a3e  jz      short loc_180004A58
0x180004a40  mov     r8, rdx
0x180004a43  mov     rdx, rcx
0x180004a46  mov     rcx, rbx
0x180004a49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a4e  cmp     [r14], r15w
0x180004a52  jnz     loc_180004C71
0x180004a58  mov     ecx, [rbx]
0x180004a5a  mov     bpl, 8
0x180004a5d  test    ecx, ecx
0x180004a5f  jz      short loc_180004AAA
0x180004a61  sub     ecx, 1
0x180004a64  jz      short loc_180004A92
0x180004a66  sub     ecx, 1
0x180004a69  jz      short loc_180004A82
0x180004a6b  cmp     ecx, 1
0x180004a6e  jz      short loc_180004A79
0x180004a70  lea     rdi, qword_1800634A8
0x180004a77  jmp     short loc_180004AB1
0x180004a79  lea     rdi, aFailfast; "FailFast"
0x180004a80  jmp     short loc_180004AB1
0x180004a82  lea     rax, aLoghr; "LogHr"
0x180004a89  lea     rdi, aLognt; "LogNt"
0x180004a90  jmp     short loc_180004AA0
0x180004a92  lea     rax, aReturnhr; "ReturnHr"
0x180004a99  lea     rdi, aReturnnt; "ReturnNt"
0x180004aa0  test    [rbx+4], bpl
0x180004aa4  cmovz   rdi, rax
0x180004aa8  jmp     short loc_180004AB1
0x180004aaa  lea     rdi, aException; "Exception"
0x180004ab1  xor     edx, edx; Val
0x180004ab3  mov     r8d, 200h; Size
0x180004ab9  lea     rcx, [rsp+278h+Buffer]; void *
0x180004abe  call    memset_0
0x180004ac3  test    [rbx+4], bpl
0x180004ac7  jz      short loc_180004AEC
0x180004ac9  mov     ebp, [rbx+0Ch]
0x180004acc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004ad3  test    rax, rax
0x180004ad6  jz      short loc_180004B1C
0x180004ad8  mov     r8d, 100h
0x180004ade  lea     rdx, [rsp+278h+Buffer]
0x180004ae3  mov     ecx, ebp
0x180004ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004aea  jmp     short loc_180004B1C
0x180004aec  mov     ebp, [rbx+8]
0x180004aef  mov     [rsp+278h+Arguments], r15; Arguments
0x180004af4  mov     [rsp+278h+nSize], 100h; nSize
0x180004afc  lea     rax, [rsp+278h+Buffer]
0x180004b01  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004b06  mov     r9d, 400h; dwLanguageId
0x180004b0c  mov     r8d, ebp; dwMessageId
0x180004b0f  xor     edx, edx; lpSource
0x180004b11  mov     ecx, 1200h; dwFlags
0x180004b16  call    cs:__imp_FormatMessageW
0x180004b1c  lea     rsi, [r14+rsi*2]
0x180004b20  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004b24  mov     rax, [rbx+88h]
0x180004b2b  mov     rcx, [rbx+80h]
0x180004b32  mov     rdx, rsi; unsigned __int16 *
0x180004b35  test    r9, r9
0x180004b38  jz      short loc_180004B5C
0x180004b3a  mov     [rsp+278h+Arguments], rax
0x180004b3f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004b44  mov     eax, [rbx+40h]
0x180004b47  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004b4b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004b52  mov     rcx, r14; this
0x180004b55  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b5a  jmp     short loc_180004B73
0x180004b5c  mov     [rsp+278h+lpBuffer], rax
0x180004b61  mov     r9, rcx; unsigned __int16 *
0x180004b64  lea     r8, aHsP; "%hs!%p: "
0x180004b6b  mov     rcx, r14; this
0x180004b6e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b73  mov     r14, rax
0x180004b76  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004b7d  test    r9, r9
0x180004b80  jz      short loc_180004B97
0x180004b82  lea     r8, aCallerP; "(caller: %p) "
0x180004b89  mov     rdx, rsi; unsigned __int16 *
0x180004b8c  mov     rcx, rax; this
0x180004b8f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004b94  mov     r14, rax
0x180004b97  call    cs:__imp_GetCurrentThreadId
0x180004b9d  lea     rcx, [rsp+278h+Buffer]
0x180004ba2  mov     [rsp+278h+var_240], rcx
0x180004ba7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004bab  mov     [rsp+278h+nSize], eax
0x180004baf  mov     eax, [rbx+44h]
0x180004bb2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004bb6  mov     r9, rdi; unsigned __int16 *
0x180004bb9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004bc0  mov     rdx, rsi; unsigned __int16 *
0x180004bc3  mov     rcx, r14; this
0x180004bc6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bcb  cmp     [rbx+18h], r15
0x180004bcf  jnz     short loc_180004BE1
0x180004bd1  cmp     [rbx+48h], r15
0x180004bd5  jnz     short loc_180004BE1
0x180004bd7  cmp     [rbx+30h], r15
0x180004bdb  jz      loc_180004C71
0x180004be1  lea     r8, asc_180063598; "    "
0x180004be8  mov     rdx, rsi; unsigned __int16 *
0x180004beb  mov     rcx, rax; this
0x180004bee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004bf3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004bf7  test    r9, r9
0x180004bfa  jz      short loc_180004C0E
0x180004bfc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004c03  mov     rdx, rsi; unsigned __int16 *
0x180004c06  mov     rcx, rax; this
0x180004c09  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c0e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004c12  test    r9, r9
0x180004c15  jz      short loc_180004C29
0x180004c17  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004c1e  mov     rdx, rsi; unsigned __int16 *
0x180004c21  mov     rcx, rax; this
0x180004c24  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c29  mov     rcx, [rbx+28h]
0x180004c2d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004c31  mov     rdx, rsi; unsigned __int16 *
0x180004c34  test    rcx, rcx
0x180004c37  jz      short loc_180004C4F
0x180004c39  mov     [rsp+278h+lpBuffer], rcx
0x180004c3e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004c45  mov     rcx, rax; this
0x180004c48  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c4d  jmp     short loc_180004C71
0x180004c4f  mov     rcx, rax; this
0x180004c52  test    r9, r9
0x180004c55  jz      short loc_180004C65
0x180004c57  lea     r8, aHs; "[%hs]\n"
0x180004c5e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c63  jmp     short loc_180004C71
0x180004c65  lea     r8, asc_180063610; "\n"
0x180004c6c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004c71  xor     eax, eax
0x180004c73  mov     rcx, [rsp+278h+var_38]
0x180004c7b  xor     rcx, rsp; StackCookie
0x180004c7e  call    __security_check_cookie
0x180004c83  mov     rbx, [rsp+278h+arg_18]
0x180004c8b  add     rsp, 250h
0x180004c92  pop     r15
0x180004c94  pop     r14
0x180004c96  pop     rdi
0x180004c97  pop     rsi
0x180004c98  pop     rbp
0x180004c99  retn
```
