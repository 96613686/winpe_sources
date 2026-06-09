# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004d64`
- end: `0x180005019`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `693`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x1800049dc`

## callees

- `0x180001fa3`
- `0x180004d64`
- `0x180005cbc`
- `0x180006956`
- `0x180006980`
- `0x180007010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004e96`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004e96`

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
          v8 = (const char *)&qword_180009170;
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
  nSize[0] = GetCurrentThreadId_0();
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
0x180004d64  mov     [rsp+arg_18], rbx
0x180004d69  push    rbp
0x180004d6a  push    rsi
0x180004d6b  push    rdi
0x180004d6c  push    r14
0x180004d6e  push    r15
0x180004d70  sub     rsp, 250h
0x180004d77  mov     rax, cs:__security_cookie
0x180004d7e  xor     rax, rsp
0x180004d81  mov     [rsp+278h+var_38], rax
0x180004d89  xor     r15d, r15d
0x180004d8c  mov     rbx, r8
0x180004d8f  mov     rsi, rdx
0x180004d92  mov     r14, rcx
0x180004d95  test    rdx, rdx
0x180004d98  jz      loc_180004FF0
0x180004d9e  test    rcx, rcx
0x180004da1  jz      loc_180004FF0
0x180004da7  mov     rax, cs:g_pfnResultLoggingCallback
0x180004dae  mov     [rcx], r15w
0x180004db2  test    rax, rax
0x180004db5  jz      short loc_180004DD8
0x180004db7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004dbe  jz      short loc_180004DD8
0x180004dc0  mov     r8, rdx
0x180004dc3  mov     rdx, rcx
0x180004dc6  mov     rcx, rbx
0x180004dc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dce  cmp     [r14], r15w
0x180004dd2  jnz     loc_180004FF0
0x180004dd8  mov     ecx, [rbx]
0x180004dda  mov     bpl, 8
0x180004ddd  test    ecx, ecx
0x180004ddf  jz      short loc_180004E2A
0x180004de1  sub     ecx, 1
0x180004de4  jz      short loc_180004E12
0x180004de6  sub     ecx, 1
0x180004de9  jz      short loc_180004E02
0x180004deb  cmp     ecx, 1
0x180004dee  jz      short loc_180004DF9
0x180004df0  lea     rdi, qword_180009170
0x180004df7  jmp     short loc_180004E31
0x180004df9  lea     rdi, aFailfast; "FailFast"
0x180004e00  jmp     short loc_180004E31
0x180004e02  lea     rax, aLoghr; "LogHr"
0x180004e09  lea     rdi, aLognt; "LogNt"
0x180004e10  jmp     short loc_180004E20
0x180004e12  lea     rax, aReturnhr; "ReturnHr"
0x180004e19  lea     rdi, aReturnnt; "ReturnNt"
0x180004e20  test    [rbx+4], bpl
0x180004e24  cmovz   rdi, rax
0x180004e28  jmp     short loc_180004E31
0x180004e2a  lea     rdi, aException; "Exception"
0x180004e31  xor     edx, edx; Val
0x180004e33  lea     rcx, [rsp+278h+Buffer]; void *
0x180004e38  mov     r8d, 200h; Size
0x180004e3e  call    memset_0
0x180004e43  test    [rbx+4], bpl
0x180004e47  jz      short loc_180004E6C
0x180004e49  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004e50  mov     ebp, [rbx+0Ch]
0x180004e53  test    rax, rax
0x180004e56  jz      short loc_180004E9C
0x180004e58  mov     r8d, 100h
0x180004e5e  lea     rdx, [rsp+278h+Buffer]
0x180004e63  mov     ecx, ebp
0x180004e65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e6a  jmp     short loc_180004E9C
0x180004e6c  mov     ebp, [rbx+8]
0x180004e6f  lea     rax, [rsp+278h+Buffer]
0x180004e74  mov     [rsp+278h+Arguments], r15; Arguments
0x180004e79  mov     r8d, ebp; dwMessageId
0x180004e7c  mov     [rsp+278h+nSize], 100h; nSize
0x180004e84  mov     r9d, 400h; dwLanguageId
0x180004e8a  xor     edx, edx; lpSource
0x180004e8c  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004e91  mov     ecx, 1200h; dwFlags
0x180004e96  call    cs:__imp_FormatMessageW
0x180004e9c  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004ea0  lea     rsi, [r14+rsi*2]
0x180004ea4  mov     rax, [rbx+88h]
0x180004eab  mov     rdx, rsi; unsigned __int16 *
0x180004eae  mov     rcx, [rbx+80h]
0x180004eb5  test    r9, r9
0x180004eb8  jz      short loc_180004EDC
0x180004eba  mov     [rsp+278h+Arguments], rax
0x180004ebf  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004ec6  mov     eax, [rbx+40h]
0x180004ec9  mov     qword ptr [rsp+278h+nSize], rcx
0x180004ece  mov     rcx, r14; this
0x180004ed1  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004ed5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004eda  jmp     short loc_180004EF3
0x180004edc  mov     r9, rcx; unsigned __int16 *
0x180004edf  mov     [rsp+278h+lpBuffer], rax
0x180004ee4  mov     rcx, r14; this
0x180004ee7  lea     r8, aHsP; "%hs!%p: "
0x180004eee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ef3  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004efa  mov     r14, rax
0x180004efd  test    r9, r9
0x180004f00  jz      short loc_180004F17
0x180004f02  lea     r8, aCallerP; "(caller: %p) "
0x180004f09  mov     rdx, rsi; unsigned __int16 *
0x180004f0c  mov     rcx, rax; this
0x180004f0f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f14  mov     r14, rax
0x180004f17  call    GetCurrentThreadId_0
0x180004f1c  lea     rcx, [rsp+278h+Buffer]
0x180004f21  mov     r9, rdi; unsigned __int16 *
0x180004f24  mov     [rsp+278h+var_240], rcx
0x180004f29  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004f30  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004f34  mov     rdx, rsi; unsigned __int16 *
0x180004f37  mov     [rsp+278h+nSize], eax
0x180004f3b  mov     rcx, r14; this
0x180004f3e  mov     eax, [rbx+44h]
0x180004f41  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f4a  cmp     [rbx+18h], r15
0x180004f4e  jnz     short loc_180004F60
0x180004f50  cmp     [rbx+48h], r15
0x180004f54  jnz     short loc_180004F60
0x180004f56  cmp     [rbx+30h], r15
0x180004f5a  jz      loc_180004FF0
0x180004f60  lea     r8, asc_180009260; "    "
0x180004f67  mov     rdx, rsi; unsigned __int16 *
0x180004f6a  mov     rcx, rax; this
0x180004f6d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f72  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004f76  test    r9, r9
0x180004f79  jz      short loc_180004F8D
0x180004f7b  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004f82  mov     rdx, rsi; unsigned __int16 *
0x180004f85  mov     rcx, rax; this
0x180004f88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f8d  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004f91  test    r9, r9
0x180004f94  jz      short loc_180004FA8
0x180004f96  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004f9d  mov     rdx, rsi; unsigned __int16 *
0x180004fa0  mov     rcx, rax; this
0x180004fa3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fa8  mov     rcx, [rbx+28h]
0x180004fac  mov     rdx, rsi; unsigned __int16 *
0x180004faf  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004fb3  test    rcx, rcx
0x180004fb6  jz      short loc_180004FCE
0x180004fb8  mov     [rsp+278h+lpBuffer], rcx
0x180004fbd  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004fc4  mov     rcx, rax; this
0x180004fc7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fcc  jmp     short loc_180004FF0
0x180004fce  mov     rcx, rax; this
0x180004fd1  test    r9, r9
0x180004fd4  jz      short loc_180004FE4
0x180004fd6  lea     r8, aHs_0; "[%hs]\n"
0x180004fdd  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fe2  jmp     short loc_180004FF0
0x180004fe4  lea     r8, asc_1800092D8; "\n"
0x180004feb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004ff0  xor     eax, eax
0x180004ff2  mov     rcx, [rsp+278h+var_38]
0x180004ffa  xor     rcx, rsp; StackCookie
0x180004ffd  call    __security_check_cookie
0x180005002  mov     rbx, [rsp+278h+arg_18]
0x18000500a  add     rsp, 250h
0x180005011  pop     r15
0x180005013  pop     r14
0x180005015  pop     rdi
0x180005016  pop     rsi
0x180005017  pop     rbp
0x180005018  retn
```
