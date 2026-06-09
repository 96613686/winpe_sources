# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003c94`
- end: `0x140003f4a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002e10`
- `0x140004680`
- `0x140004b48`
- `0x140005d40`

## callees

- `0x140001c80`
- `0x1400028a8`
- `0x140003c94`
- `0x140004980`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003e47`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003e47`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003dc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003dc6`

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
          v7 = (const char *)&qword_1400194C8;
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
0x140003c94  mov     [rsp+arg_18], rbx
0x140003c99  push    rbp
0x140003c9a  push    rsi
0x140003c9b  push    rdi
0x140003c9c  push    r14
0x140003c9e  push    r15
0x140003ca0  sub     rsp, 250h
0x140003ca7  mov     rax, cs:__security_cookie
0x140003cae  xor     rax, rsp
0x140003cb1  mov     [rsp+278h+var_38], rax
0x140003cb9  mov     rbx, r8
0x140003cbc  mov     rsi, rdx
0x140003cbf  mov     r14, rcx
0x140003cc2  xor     r15d, r15d
0x140003cc5  test    rdx, rdx
0x140003cc8  jz      loc_140003F21
0x140003cce  test    rcx, rcx
0x140003cd1  jz      loc_140003F21
0x140003cd7  mov     [rcx], r15w
0x140003cdb  mov     rax, cs:g_pfnResultLoggingCallback
0x140003ce2  test    rax, rax
0x140003ce5  jz      short loc_140003D08
0x140003ce7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140003cee  jz      short loc_140003D08
0x140003cf0  mov     r8, rdx
0x140003cf3  mov     rdx, rcx
0x140003cf6  mov     rcx, rbx
0x140003cf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cfe  cmp     [r14], r15w
0x140003d02  jnz     loc_140003F21
0x140003d08  mov     ecx, [rbx]
0x140003d0a  mov     bpl, 8
0x140003d0d  test    ecx, ecx
0x140003d0f  jz      short loc_140003D5A
0x140003d11  sub     ecx, 1
0x140003d14  jz      short loc_140003D42
0x140003d16  sub     ecx, 1
0x140003d19  jz      short loc_140003D32
0x140003d1b  cmp     ecx, 1
0x140003d1e  jz      short loc_140003D29
0x140003d20  lea     rdi, qword_1400194C8
0x140003d27  jmp     short loc_140003D61
0x140003d29  lea     rdi, aFailfast; "FailFast"
0x140003d30  jmp     short loc_140003D61
0x140003d32  lea     rax, aLoghr; "LogHr"
0x140003d39  lea     rdi, aLognt; "LogNt"
0x140003d40  jmp     short loc_140003D50
0x140003d42  lea     rax, aReturnhr; "ReturnHr"
0x140003d49  lea     rdi, aReturnnt; "ReturnNt"
0x140003d50  test    [rbx+4], bpl
0x140003d54  cmovz   rdi, rax
0x140003d58  jmp     short loc_140003D61
0x140003d5a  lea     rdi, aException; "Exception"
0x140003d61  xor     edx, edx; Val
0x140003d63  mov     r8d, 200h; Size
0x140003d69  lea     rcx, [rsp+278h+Buffer]; void *
0x140003d6e  call    memset_0
0x140003d73  test    [rbx+4], bpl
0x140003d77  jz      short loc_140003D9C
0x140003d79  mov     ebp, [rbx+0Ch]
0x140003d7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140003d83  test    rax, rax
0x140003d86  jz      short loc_140003DCC
0x140003d88  mov     r8d, 100h
0x140003d8e  lea     rdx, [rsp+278h+Buffer]
0x140003d93  mov     ecx, ebp
0x140003d95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d9a  jmp     short loc_140003DCC
0x140003d9c  mov     ebp, [rbx+8]
0x140003d9f  mov     [rsp+278h+Arguments], r15; Arguments
0x140003da4  mov     [rsp+278h+nSize], 100h; nSize
0x140003dac  lea     rax, [rsp+278h+Buffer]
0x140003db1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003db6  mov     r9d, 400h; dwLanguageId
0x140003dbc  mov     r8d, ebp; dwMessageId
0x140003dbf  xor     edx, edx; lpSource
0x140003dc1  mov     ecx, 1200h; dwFlags
0x140003dc6  call    cs:__imp_FormatMessageW
0x140003dcc  lea     rsi, [r14+rsi*2]
0x140003dd0  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003dd4  mov     rax, [rbx+88h]
0x140003ddb  mov     rcx, [rbx+80h]
0x140003de2  mov     rdx, rsi; unsigned __int16 *
0x140003de5  test    r9, r9
0x140003de8  jz      short loc_140003E0C
0x140003dea  mov     [rsp+278h+Arguments], rax
0x140003def  mov     qword ptr [rsp+278h+nSize], rcx
0x140003df4  mov     eax, [rbx+40h]
0x140003df7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003dfb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003e02  mov     rcx, r14; this
0x140003e05  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003e0a  jmp     short loc_140003E23
0x140003e0c  mov     [rsp+278h+lpBuffer], rax
0x140003e11  mov     r9, rcx; unsigned __int16 *
0x140003e14  lea     r8, aHsP; "%hs!%p: "
0x140003e1b  mov     rcx, r14; this
0x140003e1e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003e23  mov     r14, rax
0x140003e26  mov     r9, [rbx+90h]; unsigned __int16 *
0x140003e2d  test    r9, r9
0x140003e30  jz      short loc_140003E47
0x140003e32  lea     r8, aCallerP; "(caller: %p) "
0x140003e39  mov     rdx, rsi; unsigned __int16 *
0x140003e3c  mov     rcx, rax; this
0x140003e3f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003e44  mov     r14, rax
0x140003e47  call    cs:__imp_GetCurrentThreadId
0x140003e4d  lea     rcx, [rsp+278h+Buffer]
0x140003e52  mov     [rsp+278h+var_240], rcx
0x140003e57  mov     dword ptr [rsp+278h+Arguments], ebp
0x140003e5b  mov     [rsp+278h+nSize], eax
0x140003e5f  mov     eax, [rbx+44h]
0x140003e62  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140003e66  mov     r9, rdi; unsigned __int16 *
0x140003e69  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140003e70  mov     rdx, rsi; unsigned __int16 *
0x140003e73  mov     rcx, r14; this
0x140003e76  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003e7b  cmp     [rbx+18h], r15
0x140003e7f  jnz     short loc_140003E91
0x140003e81  cmp     [rbx+48h], r15
0x140003e85  jnz     short loc_140003E91
0x140003e87  cmp     [rbx+30h], r15
0x140003e8b  jz      loc_140003F21
0x140003e91  lea     r8, asc_1400195D0; "    "
0x140003e98  mov     rdx, rsi; unsigned __int16 *
0x140003e9b  mov     rcx, rax; this
0x140003e9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003ea3  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003ea7  test    r9, r9
0x140003eaa  jz      short loc_140003EBE
0x140003eac  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003eb3  mov     rdx, rsi; unsigned __int16 *
0x140003eb6  mov     rcx, rax; this
0x140003eb9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003ebe  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003ec2  test    r9, r9
0x140003ec5  jz      short loc_140003ED9
0x140003ec7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140003ece  mov     rdx, rsi; unsigned __int16 *
0x140003ed1  mov     rcx, rax; this
0x140003ed4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003ed9  mov     rcx, [rbx+28h]
0x140003edd  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003ee1  mov     rdx, rsi; unsigned __int16 *
0x140003ee4  test    rcx, rcx
0x140003ee7  jz      short loc_140003EFF
0x140003ee9  mov     [rsp+278h+lpBuffer], rcx
0x140003eee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003ef5  mov     rcx, rax; this
0x140003ef8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003efd  jmp     short loc_140003F21
0x140003eff  mov     rcx, rax; this
0x140003f02  test    r9, r9
0x140003f05  jz      short loc_140003F15
0x140003f07  lea     r8, aHs; "[%hs]\n"
0x140003f0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003f13  jmp     short loc_140003F21
0x140003f15  lea     r8, asc_140019648; "\n"
0x140003f1c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003f21  xor     eax, eax
0x140003f23  mov     rcx, [rsp+278h+var_38]
0x140003f2b  xor     rcx, rsp; StackCookie
0x140003f2e  call    __security_check_cookie
0x140003f33  mov     rbx, [rsp+278h+arg_18]
0x140003f3b  add     rsp, 250h
0x140003f42  pop     r15
0x140003f44  pop     r14
0x140003f46  pop     rdi
0x140003f47  pop     rsi
0x140003f48  pop     rbp
0x140003f49  retn
```
