# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005dc4`
- end: `0x18000607a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180004e94`
- `0x1800067dc`
- `0x180006c90`
- `0x180007f40`

## callees

- `0x1800032b0`
- `0x180004200`
- `0x180005dc4`
- `0x180006adc`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005ef6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005ef6`

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
          v7 = dword_180054434;
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
0x180005dc4  mov     [rsp+arg_18], rbx
0x180005dc9  push    rbp
0x180005dca  push    rsi
0x180005dcb  push    rdi
0x180005dcc  push    r14
0x180005dce  push    r15
0x180005dd0  sub     rsp, 250h
0x180005dd7  mov     rax, cs:__security_cookie
0x180005dde  xor     rax, rsp
0x180005de1  mov     [rsp+278h+var_38], rax
0x180005de9  mov     rbx, r8
0x180005dec  mov     rsi, rdx
0x180005def  mov     r14, rcx
0x180005df2  xor     r15d, r15d
0x180005df5  test    rdx, rdx
0x180005df8  jz      loc_180006051
0x180005dfe  test    rcx, rcx
0x180005e01  jz      loc_180006051
0x180005e07  mov     [rcx], r15w
0x180005e0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e12  test    rax, rax
0x180005e15  jz      short loc_180005E38
0x180005e17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e1e  jz      short loc_180005E38
0x180005e20  mov     r8, rdx
0x180005e23  mov     rdx, rcx
0x180005e26  mov     rcx, rbx
0x180005e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e2e  cmp     [r14], r15w
0x180005e32  jnz     loc_180006051
0x180005e38  mov     ecx, [rbx]
0x180005e3a  mov     bpl, 8
0x180005e3d  test    ecx, ecx
0x180005e3f  jz      short loc_180005E8A
0x180005e41  sub     ecx, 1
0x180005e44  jz      short loc_180005E72
0x180005e46  sub     ecx, 1
0x180005e49  jz      short loc_180005E62
0x180005e4b  cmp     ecx, 1
0x180005e4e  jz      short loc_180005E59
0x180005e50  lea     rdi, dword_180054434
0x180005e57  jmp     short loc_180005E91
0x180005e59  lea     rdi, aFailfast; "FailFast"
0x180005e60  jmp     short loc_180005E91
0x180005e62  lea     rax, aLoghr; "LogHr"
0x180005e69  lea     rdi, aLognt; "LogNt"
0x180005e70  jmp     short loc_180005E80
0x180005e72  lea     rax, aReturnhr; "ReturnHr"
0x180005e79  lea     rdi, aReturnnt; "ReturnNt"
0x180005e80  test    [rbx+4], bpl
0x180005e84  cmovz   rdi, rax
0x180005e88  jmp     short loc_180005E91
0x180005e8a  lea     rdi, aException; "Exception"
0x180005e91  xor     edx, edx; Val
0x180005e93  mov     r8d, 200h; Size
0x180005e99  lea     rcx, [rsp+278h+Buffer]; void *
0x180005e9e  call    memset_0
0x180005ea3  test    [rbx+4], bpl
0x180005ea7  jz      short loc_180005ECC
0x180005ea9  mov     ebp, [rbx+0Ch]
0x180005eac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005eb3  test    rax, rax
0x180005eb6  jz      short loc_180005EFC
0x180005eb8  mov     r8d, 100h
0x180005ebe  lea     rdx, [rsp+278h+Buffer]
0x180005ec3  mov     ecx, ebp
0x180005ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eca  jmp     short loc_180005EFC
0x180005ecc  mov     ebp, [rbx+8]
0x180005ecf  mov     [rsp+278h+Arguments], r15; Arguments
0x180005ed4  mov     [rsp+278h+nSize], 100h; nSize
0x180005edc  lea     rax, [rsp+278h+Buffer]
0x180005ee1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005ee6  mov     r9d, 400h; dwLanguageId
0x180005eec  mov     r8d, ebp; dwMessageId
0x180005eef  xor     edx, edx; lpSource
0x180005ef1  mov     ecx, 1200h; dwFlags
0x180005ef6  call    cs:__imp_FormatMessageW
0x180005efc  lea     rsi, [r14+rsi*2]
0x180005f00  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005f04  mov     rax, [rbx+88h]
0x180005f0b  mov     rcx, [rbx+80h]
0x180005f12  mov     rdx, rsi; unsigned __int16 *
0x180005f15  test    r9, r9
0x180005f18  jz      short loc_180005F3C
0x180005f1a  mov     [rsp+278h+Arguments], rax
0x180005f1f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005f24  mov     eax, [rbx+40h]
0x180005f27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f2b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005f32  mov     rcx, r14; this
0x180005f35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f3a  jmp     short loc_180005F53
0x180005f3c  mov     [rsp+278h+lpBuffer], rax
0x180005f41  mov     r9, rcx; unsigned __int16 *
0x180005f44  lea     r8, aHsP; "%hs!%p: "
0x180005f4b  mov     rcx, r14; this
0x180005f4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f53  mov     r14, rax
0x180005f56  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005f5d  test    r9, r9
0x180005f60  jz      short loc_180005F77
0x180005f62  lea     r8, aCallerP; "(caller: %p) "
0x180005f69  mov     rdx, rsi; unsigned __int16 *
0x180005f6c  mov     rcx, rax; this
0x180005f6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f74  mov     r14, rax
0x180005f77  call    cs:__imp_GetCurrentThreadId
0x180005f7d  lea     rcx, [rsp+278h+Buffer]
0x180005f82  mov     [rsp+278h+var_240], rcx
0x180005f87  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005f8b  mov     [rsp+278h+nSize], eax
0x180005f8f  mov     eax, [rbx+44h]
0x180005f92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f96  mov     r9, rdi; unsigned __int16 *
0x180005f99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005fa0  mov     rdx, rsi; unsigned __int16 *
0x180005fa3  mov     rcx, r14; this
0x180005fa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fab  cmp     [rbx+18h], r15
0x180005faf  jnz     short loc_180005FC1
0x180005fb1  cmp     [rbx+48h], r15
0x180005fb5  jnz     short loc_180005FC1
0x180005fb7  cmp     [rbx+30h], r15
0x180005fbb  jz      loc_180006051
0x180005fc1  lea     r8, asc_180054538; "    "
0x180005fc8  mov     rdx, rsi; unsigned __int16 *
0x180005fcb  mov     rcx, rax; this
0x180005fce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fd3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005fd7  test    r9, r9
0x180005fda  jz      short loc_180005FEE
0x180005fdc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005fe3  mov     rdx, rsi; unsigned __int16 *
0x180005fe6  mov     rcx, rax; this
0x180005fe9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005ff2  test    r9, r9
0x180005ff5  jz      short loc_180006009
0x180005ff7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005ffe  mov     rdx, rsi; unsigned __int16 *
0x180006001  mov     rcx, rax; this
0x180006004  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006009  mov     rcx, [rbx+28h]
0x18000600d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006011  mov     rdx, rsi; unsigned __int16 *
0x180006014  test    rcx, rcx
0x180006017  jz      short loc_18000602F
0x180006019  mov     [rsp+278h+lpBuffer], rcx
0x18000601e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006025  mov     rcx, rax; this
0x180006028  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000602d  jmp     short loc_180006051
0x18000602f  mov     rcx, rax; this
0x180006032  test    r9, r9
0x180006035  jz      short loc_180006045
0x180006037  lea     r8, aHs; "[%hs]\n"
0x18000603e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006043  jmp     short loc_180006051
0x180006045  lea     r8, asc_1800545B0; "\n"
0x18000604c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006051  xor     eax, eax
0x180006053  mov     rcx, [rsp+278h+var_38]
0x18000605b  xor     rcx, rsp; StackCookie
0x18000605e  call    __security_check_cookie
0x180006063  mov     rbx, [rsp+278h+arg_18]
0x18000606b  add     rsp, 250h
0x180006072  pop     r15
0x180006074  pop     r14
0x180006076  pop     rdi
0x180006077  pop     rsi
0x180006078  pop     rbp
0x180006079  retn
```
