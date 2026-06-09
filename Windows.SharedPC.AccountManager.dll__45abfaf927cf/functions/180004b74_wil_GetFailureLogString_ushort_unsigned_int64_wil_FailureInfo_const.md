# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004b74`
- end: `0x180004e2a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x18000519c`
- `0x180005af0`
- `0x180006a58`
- `0x180008324`

## callees

- `0x180003530`
- `0x180003fc0`
- `0x180004b74`
- `0x18000514c`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d27`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d27`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ca6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ca6`

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
          v7 = (const char *)&byte_180029221;
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
0x180004b74  mov     [rsp+arg_18], rbx
0x180004b79  push    rbp
0x180004b7a  push    rsi
0x180004b7b  push    rdi
0x180004b7c  push    r14
0x180004b7e  push    r15
0x180004b80  sub     rsp, 250h
0x180004b87  mov     rax, cs:__security_cookie
0x180004b8e  xor     rax, rsp
0x180004b91  mov     [rsp+278h+var_38], rax
0x180004b99  mov     rbx, r8
0x180004b9c  mov     rsi, rdx
0x180004b9f  mov     r14, rcx
0x180004ba2  xor     r15d, r15d
0x180004ba5  test    rdx, rdx
0x180004ba8  jz      loc_180004E01
0x180004bae  test    rcx, rcx
0x180004bb1  jz      loc_180004E01
0x180004bb7  mov     [rcx], r15w
0x180004bbb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004bc2  test    rax, rax
0x180004bc5  jz      short loc_180004BE8
0x180004bc7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004bce  jz      short loc_180004BE8
0x180004bd0  mov     r8, rdx
0x180004bd3  mov     rdx, rcx
0x180004bd6  mov     rcx, rbx
0x180004bd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bde  cmp     [r14], r15w
0x180004be2  jnz     loc_180004E01
0x180004be8  mov     ecx, [rbx]
0x180004bea  mov     bpl, 8
0x180004bed  test    ecx, ecx
0x180004bef  jz      short loc_180004C3A
0x180004bf1  sub     ecx, 1
0x180004bf4  jz      short loc_180004C22
0x180004bf6  sub     ecx, 1
0x180004bf9  jz      short loc_180004C12
0x180004bfb  cmp     ecx, 1
0x180004bfe  jz      short loc_180004C09
0x180004c00  lea     rdi, byte_180029221
0x180004c07  jmp     short loc_180004C41
0x180004c09  lea     rdi, aFailfast; "FailFast"
0x180004c10  jmp     short loc_180004C41
0x180004c12  lea     rax, aLoghr; "LogHr"
0x180004c19  lea     rdi, aLognt; "LogNt"
0x180004c20  jmp     short loc_180004C30
0x180004c22  lea     rax, aReturnhr; "ReturnHr"
0x180004c29  lea     rdi, aReturnnt; "ReturnNt"
0x180004c30  test    [rbx+4], bpl
0x180004c34  cmovz   rdi, rax
0x180004c38  jmp     short loc_180004C41
0x180004c3a  lea     rdi, aException; "Exception"
0x180004c41  xor     edx, edx; Val
0x180004c43  mov     r8d, 200h; Size
0x180004c49  lea     rcx, [rsp+278h+Buffer]; void *
0x180004c4e  call    memset_0
0x180004c53  test    [rbx+4], bpl
0x180004c57  jz      short loc_180004C7C
0x180004c59  mov     ebp, [rbx+0Ch]
0x180004c5c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004c63  test    rax, rax
0x180004c66  jz      short loc_180004CAC
0x180004c68  mov     r8d, 100h
0x180004c6e  lea     rdx, [rsp+278h+Buffer]
0x180004c73  mov     ecx, ebp
0x180004c75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c7a  jmp     short loc_180004CAC
0x180004c7c  mov     ebp, [rbx+8]
0x180004c7f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004c84  mov     [rsp+278h+nSize], 100h; nSize
0x180004c8c  lea     rax, [rsp+278h+Buffer]
0x180004c91  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004c96  mov     r9d, 400h; dwLanguageId
0x180004c9c  mov     r8d, ebp; dwMessageId
0x180004c9f  xor     edx, edx; lpSource
0x180004ca1  mov     ecx, 1200h; dwFlags
0x180004ca6  call    cs:__imp_FormatMessageW
0x180004cac  lea     rsi, [r14+rsi*2]
0x180004cb0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004cb4  mov     rax, [rbx+88h]
0x180004cbb  mov     rcx, [rbx+80h]
0x180004cc2  mov     rdx, rsi; unsigned __int16 *
0x180004cc5  test    r9, r9
0x180004cc8  jz      short loc_180004CEC
0x180004cca  mov     [rsp+278h+Arguments], rax
0x180004ccf  mov     qword ptr [rsp+278h+nSize], rcx
0x180004cd4  mov     eax, [rbx+40h]
0x180004cd7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004cdb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004ce2  mov     rcx, r14; this
0x180004ce5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004cea  jmp     short loc_180004D03
0x180004cec  mov     [rsp+278h+lpBuffer], rax
0x180004cf1  mov     r9, rcx; unsigned __int16 *
0x180004cf4  lea     r8, aHsP; "%hs!%p: "
0x180004cfb  mov     rcx, r14; this
0x180004cfe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d03  mov     r14, rax
0x180004d06  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004d0d  test    r9, r9
0x180004d10  jz      short loc_180004D27
0x180004d12  lea     r8, aCallerP; "(caller: %p) "
0x180004d19  mov     rdx, rsi; unsigned __int16 *
0x180004d1c  mov     rcx, rax; this
0x180004d1f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d24  mov     r14, rax
0x180004d27  call    cs:__imp_GetCurrentThreadId
0x180004d2d  lea     rcx, [rsp+278h+Buffer]
0x180004d32  mov     [rsp+278h+var_240], rcx
0x180004d37  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004d3b  mov     [rsp+278h+nSize], eax
0x180004d3f  mov     eax, [rbx+44h]
0x180004d42  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004d46  mov     r9, rdi; unsigned __int16 *
0x180004d49  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004d50  mov     rdx, rsi; unsigned __int16 *
0x180004d53  mov     rcx, r14; this
0x180004d56  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d5b  cmp     [rbx+18h], r15
0x180004d5f  jnz     short loc_180004D71
0x180004d61  cmp     [rbx+48h], r15
0x180004d65  jnz     short loc_180004D71
0x180004d67  cmp     [rbx+30h], r15
0x180004d6b  jz      loc_180004E01
0x180004d71  lea     r8, asc_180029328; "    "
0x180004d78  mov     rdx, rsi; unsigned __int16 *
0x180004d7b  mov     rcx, rax; this
0x180004d7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d83  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004d87  test    r9, r9
0x180004d8a  jz      short loc_180004D9E
0x180004d8c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004d93  mov     rdx, rsi; unsigned __int16 *
0x180004d96  mov     rcx, rax; this
0x180004d99  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004d9e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004da2  test    r9, r9
0x180004da5  jz      short loc_180004DB9
0x180004da7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004dae  mov     rdx, rsi; unsigned __int16 *
0x180004db1  mov     rcx, rax; this
0x180004db4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004db9  mov     rcx, [rbx+28h]
0x180004dbd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004dc1  mov     rdx, rsi; unsigned __int16 *
0x180004dc4  test    rcx, rcx
0x180004dc7  jz      short loc_180004DDF
0x180004dc9  mov     [rsp+278h+lpBuffer], rcx
0x180004dce  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004dd5  mov     rcx, rax; this
0x180004dd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ddd  jmp     short loc_180004E01
0x180004ddf  mov     rcx, rax; this
0x180004de2  test    r9, r9
0x180004de5  jz      short loc_180004DF5
0x180004de7  lea     r8, aHs; "[%hs]\n"
0x180004dee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004df3  jmp     short loc_180004E01
0x180004df5  lea     r8, asc_1800293A0; "\n"
0x180004dfc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004e01  xor     eax, eax
0x180004e03  mov     rcx, [rsp+278h+var_38]
0x180004e0b  xor     rcx, rsp; StackCookie
0x180004e0e  call    __security_check_cookie
0x180004e13  mov     rbx, [rsp+278h+arg_18]
0x180004e1b  add     rsp, 250h
0x180004e22  pop     r15
0x180004e24  pop     r14
0x180004e26  pop     rdi
0x180004e27  pop     rsi
0x180004e28  pop     rbp
0x180004e29  retn
```
