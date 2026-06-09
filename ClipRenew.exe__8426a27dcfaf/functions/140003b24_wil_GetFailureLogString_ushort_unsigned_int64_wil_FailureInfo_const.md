# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003b24`
- end: `0x140003dda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x140002934`
- `0x140002b9c`
- `0x140004480`

## callees

- `0x140003b24`
- `0x140004834`
- `0x14001346e`
- `0x1400134a0`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003cd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003cd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003c56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003c56`

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
          v8 = (const char *)&qword_1400158A0;
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
0x140003b24  mov     [rsp+arg_18], rbx
0x140003b29  push    rbp
0x140003b2a  push    rsi
0x140003b2b  push    rdi
0x140003b2c  push    r14
0x140003b2e  push    r15
0x140003b30  sub     rsp, 250h
0x140003b37  mov     rax, cs:__security_cookie
0x140003b3e  xor     rax, rsp
0x140003b41  mov     [rsp+278h+var_38], rax
0x140003b49  xor     r15d, r15d
0x140003b4c  mov     rbx, r8
0x140003b4f  mov     rsi, rdx
0x140003b52  mov     r14, rcx
0x140003b55  test    rdx, rdx
0x140003b58  jz      loc_140003DB1
0x140003b5e  test    rcx, rcx
0x140003b61  jz      loc_140003DB1
0x140003b67  mov     rax, cs:g_pfnResultLoggingCallback
0x140003b6e  mov     [rcx], r15w
0x140003b72  test    rax, rax
0x140003b75  jz      short loc_140003B98
0x140003b77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003b7e  jz      short loc_140003B98
0x140003b80  mov     r8, rdx
0x140003b83  mov     rdx, rcx
0x140003b86  mov     rcx, rbx
0x140003b89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b8e  cmp     [r14], r15w
0x140003b92  jnz     loc_140003DB1
0x140003b98  mov     ecx, [rbx]
0x140003b9a  mov     bpl, 8
0x140003b9d  test    ecx, ecx
0x140003b9f  jz      short loc_140003BEA
0x140003ba1  sub     ecx, 1
0x140003ba4  jz      short loc_140003BD2
0x140003ba6  sub     ecx, 1
0x140003ba9  jz      short loc_140003BC2
0x140003bab  cmp     ecx, 1
0x140003bae  jz      short loc_140003BB9
0x140003bb0  lea     rdi, qword_1400158A0
0x140003bb7  jmp     short loc_140003BF1
0x140003bb9  lea     rdi, aFailfast; "FailFast"
0x140003bc0  jmp     short loc_140003BF1
0x140003bc2  lea     rax, aLoghr; "LogHr"
0x140003bc9  lea     rdi, aLognt; "LogNt"
0x140003bd0  jmp     short loc_140003BE0
0x140003bd2  lea     rax, aReturnhr; "ReturnHr"
0x140003bd9  lea     rdi, aReturnnt; "ReturnNt"
0x140003be0  test    [rbx+4], bpl
0x140003be4  cmovz   rdi, rax
0x140003be8  jmp     short loc_140003BF1
0x140003bea  lea     rdi, aException; "Exception"
0x140003bf1  xor     edx, edx; Val
0x140003bf3  lea     rcx, [rsp+278h+Buffer]; void *
0x140003bf8  mov     r8d, 200h; Size
0x140003bfe  call    memset_0
0x140003c03  test    [rbx+4], bpl
0x140003c07  jz      short loc_140003C2C
0x140003c09  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003c10  mov     ebp, [rbx+0Ch]
0x140003c13  test    rax, rax
0x140003c16  jz      short loc_140003C5C
0x140003c18  mov     r8d, 100h
0x140003c1e  lea     rdx, [rsp+278h+Buffer]
0x140003c23  mov     ecx, ebp
0x140003c25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003c2a  jmp     short loc_140003C5C
0x140003c2c  mov     ebp, [rbx+8]
0x140003c2f  lea     rax, [rsp+278h+Buffer]
0x140003c34  mov     [rsp+278h+Arguments], r15; Arguments
0x140003c39  mov     r8d, ebp; dwMessageId
0x140003c3c  mov     [rsp+278h+nSize], 100h; nSize
0x140003c44  mov     r9d, 400h; dwLanguageId
0x140003c4a  xor     edx, edx; lpSource
0x140003c4c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003c51  mov     ecx, 1200h; dwFlags
0x140003c56  call    cs:__imp_FormatMessageW
0x140003c5c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003c60  lea     rsi, [r14+rsi*2]
0x140003c64  mov     rax, [rbx+88h]
0x140003c6b  mov     rdx, rsi; unsigned __int16 *
0x140003c6e  mov     rcx, [rbx+80h]
0x140003c75  test    r9, r9
0x140003c78  jz      short loc_140003C9C
0x140003c7a  mov     [rsp+278h+Arguments], rax
0x140003c7f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003c86  mov     eax, [rbx+40h]
0x140003c89  mov     qword ptr [rsp+278h+nSize], rcx
0x140003c8e  mov     rcx, r14; this
0x140003c91  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003c95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003c9a  jmp     short loc_140003CB3
0x140003c9c  mov     r9, rcx; unsigned __int16 *
0x140003c9f  mov     [rsp+278h+lpBuffer], rax
0x140003ca4  mov     rcx, r14; this
0x140003ca7  lea     r8, aHsP; "%hs!%p: "
0x140003cae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003cb3  mov     r9, [rbx+90h]; unsigned __int16 *
0x140003cba  mov     r14, rax
0x140003cbd  test    r9, r9
0x140003cc0  jz      short loc_140003CD7
0x140003cc2  lea     r8, aCallerP; "(caller: %p) "
0x140003cc9  mov     rdx, rsi; unsigned __int16 *
0x140003ccc  mov     rcx, rax; this
0x140003ccf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003cd4  mov     r14, rax
0x140003cd7  call    cs:__imp_GetCurrentThreadId
0x140003cdd  lea     rcx, [rsp+278h+Buffer]
0x140003ce2  mov     r9, rdi; unsigned __int16 *
0x140003ce5  mov     [rsp+278h+var_240], rcx
0x140003cea  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003cf1  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003cf5  mov     rdx, rsi; unsigned __int16 *
0x140003cf8  mov     [rsp+278h+nSize], eax
0x140003cfc  mov     rcx, r14; this
0x140003cff  mov     eax, [rbx+44h]
0x140003d02  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003d06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d0b  cmp     [rbx+18h], r15
0x140003d0f  jnz     short loc_140003D21
0x140003d11  cmp     [rbx+48h], r15
0x140003d15  jnz     short loc_140003D21
0x140003d17  cmp     [rbx+30h], r15
0x140003d1b  jz      loc_140003DB1
0x140003d21  lea     r8, asc_1400159A8; "    "
0x140003d28  mov     rdx, rsi; unsigned __int16 *
0x140003d2b  mov     rcx, rax; this
0x140003d2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d33  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003d37  test    r9, r9
0x140003d3a  jz      short loc_140003D4E
0x140003d3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003d43  mov     rdx, rsi; unsigned __int16 *
0x140003d46  mov     rcx, rax; this
0x140003d49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003d52  test    r9, r9
0x140003d55  jz      short loc_140003D69
0x140003d57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140003d5e  mov     rdx, rsi; unsigned __int16 *
0x140003d61  mov     rcx, rax; this
0x140003d64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d69  mov     rcx, [rbx+28h]
0x140003d6d  mov     rdx, rsi; unsigned __int16 *
0x140003d70  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003d74  test    rcx, rcx
0x140003d77  jz      short loc_140003D8F
0x140003d79  mov     [rsp+278h+lpBuffer], rcx
0x140003d7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003d85  mov     rcx, rax; this
0x140003d88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003d8d  jmp     short loc_140003DB1
0x140003d8f  mov     rcx, rax; this
0x140003d92  test    r9, r9
0x140003d95  jz      short loc_140003DA5
0x140003d97  lea     r8, aHs; "[%hs]\n"
0x140003d9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003da3  jmp     short loc_140003DB1
0x140003da5  lea     r8, asc_140015A20; "\n"
0x140003dac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003db1  xor     eax, eax
0x140003db3  mov     rcx, [rsp+278h+var_38]
0x140003dbb  xor     rcx, rsp; StackCookie
0x140003dbe  call    __security_check_cookie
0x140003dc3  mov     rbx, [rsp+278h+arg_18]
0x140003dcb  add     rsp, 250h
0x140003dd2  pop     r15
0x140003dd4  pop     r14
0x140003dd6  pop     rdi
0x140003dd7  pop     rsi
0x140003dd8  pop     rbp
0x140003dd9  retn
```
