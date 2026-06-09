# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004dc4`
- end: `0x18000507a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002adc`
- `0x180002d44`
- `0x180005724`
- `0x180008860`

## callees

- `0x1800017c0`
- `0x180002570`
- `0x180004dc4`
- `0x180005a24`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f77`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f77`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ef6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004ef6`

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
          v7 = (const char *)&qword_1800126F8;
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
0x180004dc4  mov     [rsp+arg_18], rbx
0x180004dc9  push    rbp
0x180004dca  push    rsi
0x180004dcb  push    rdi
0x180004dcc  push    r14
0x180004dce  push    r15
0x180004dd0  sub     rsp, 250h
0x180004dd7  mov     rax, cs:__security_cookie
0x180004dde  xor     rax, rsp
0x180004de1  mov     [rsp+278h+var_38], rax
0x180004de9  mov     rbx, r8
0x180004dec  mov     rsi, rdx
0x180004def  mov     r14, rcx
0x180004df2  xor     r15d, r15d
0x180004df5  test    rdx, rdx
0x180004df8  jz      loc_180005051
0x180004dfe  test    rcx, rcx
0x180004e01  jz      loc_180005051
0x180004e07  mov     [rcx], r15w
0x180004e0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e12  test    rax, rax
0x180004e15  jz      short loc_180004E38
0x180004e17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004e1e  jz      short loc_180004E38
0x180004e20  mov     r8, rdx
0x180004e23  mov     rdx, rcx
0x180004e26  mov     rcx, rbx
0x180004e29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2e  cmp     [r14], r15w
0x180004e32  jnz     loc_180005051
0x180004e38  mov     ecx, [rbx]
0x180004e3a  mov     bpl, 8
0x180004e3d  test    ecx, ecx
0x180004e3f  jz      short loc_180004E8A
0x180004e41  sub     ecx, 1
0x180004e44  jz      short loc_180004E72
0x180004e46  sub     ecx, 1
0x180004e49  jz      short loc_180004E62
0x180004e4b  cmp     ecx, 1
0x180004e4e  jz      short loc_180004E59
0x180004e50  lea     rdi, qword_1800126F8
0x180004e57  jmp     short loc_180004E91
0x180004e59  lea     rdi, aFailfast; "FailFast"
0x180004e60  jmp     short loc_180004E91
0x180004e62  lea     rax, aLoghr; "LogHr"
0x180004e69  lea     rdi, aLognt; "LogNt"
0x180004e70  jmp     short loc_180004E80
0x180004e72  lea     rax, aReturnhr; "ReturnHr"
0x180004e79  lea     rdi, aReturnnt; "ReturnNt"
0x180004e80  test    [rbx+4], bpl
0x180004e84  cmovz   rdi, rax
0x180004e88  jmp     short loc_180004E91
0x180004e8a  lea     rdi, aException; "Exception"
0x180004e91  xor     edx, edx; Val
0x180004e93  mov     r8d, 200h; Size
0x180004e99  lea     rcx, [rsp+278h+Buffer]; void *
0x180004e9e  call    memset_0
0x180004ea3  test    [rbx+4], bpl
0x180004ea7  jz      short loc_180004ECC
0x180004ea9  mov     ebp, [rbx+0Ch]
0x180004eac  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004eb3  test    rax, rax
0x180004eb6  jz      short loc_180004EFC
0x180004eb8  mov     r8d, 100h
0x180004ebe  lea     rdx, [rsp+278h+Buffer]
0x180004ec3  mov     ecx, ebp
0x180004ec5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004eca  jmp     short loc_180004EFC
0x180004ecc  mov     ebp, [rbx+8]
0x180004ecf  mov     [rsp+278h+Arguments], r15; Arguments
0x180004ed4  mov     [rsp+278h+nSize], 100h; nSize
0x180004edc  lea     rax, [rsp+278h+Buffer]
0x180004ee1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004ee6  mov     r9d, 400h; dwLanguageId
0x180004eec  mov     r8d, ebp; dwMessageId
0x180004eef  xor     edx, edx; lpSource
0x180004ef1  mov     ecx, 1200h; dwFlags
0x180004ef6  call    cs:__imp_FormatMessageW
0x180004efc  lea     rsi, [r14+rsi*2]
0x180004f00  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004f04  mov     rax, [rbx+88h]
0x180004f0b  mov     rcx, [rbx+80h]
0x180004f12  mov     rdx, rsi; unsigned __int16 *
0x180004f15  test    r9, r9
0x180004f18  jz      short loc_180004F3C
0x180004f1a  mov     [rsp+278h+Arguments], rax
0x180004f1f  mov     qword ptr [rsp+278h+nSize], rcx
0x180004f24  mov     eax, [rbx+40h]
0x180004f27  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f2b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004f32  mov     rcx, r14; this
0x180004f35  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f3a  jmp     short loc_180004F53
0x180004f3c  mov     [rsp+278h+lpBuffer], rax
0x180004f41  mov     r9, rcx; unsigned __int16 *
0x180004f44  lea     r8, aHsP; "%hs!%p: "
0x180004f4b  mov     rcx, r14; this
0x180004f4e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f53  mov     r14, rax
0x180004f56  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004f5d  test    r9, r9
0x180004f60  jz      short loc_180004F77
0x180004f62  lea     r8, aCallerP; "(caller: %p) "
0x180004f69  mov     rdx, rsi; unsigned __int16 *
0x180004f6c  mov     rcx, rax; this
0x180004f6f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f74  mov     r14, rax
0x180004f77  call    cs:__imp_GetCurrentThreadId
0x180004f7d  lea     rcx, [rsp+278h+Buffer]
0x180004f82  mov     [rsp+278h+var_240], rcx
0x180004f87  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004f8b  mov     [rsp+278h+nSize], eax
0x180004f8f  mov     eax, [rbx+44h]
0x180004f92  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f96  mov     r9, rdi; unsigned __int16 *
0x180004f99  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004fa0  mov     rdx, rsi; unsigned __int16 *
0x180004fa3  mov     rcx, r14; this
0x180004fa6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fab  cmp     [rbx+18h], r15
0x180004faf  jnz     short loc_180004FC1
0x180004fb1  cmp     [rbx+48h], r15
0x180004fb5  jnz     short loc_180004FC1
0x180004fb7  cmp     [rbx+30h], r15
0x180004fbb  jz      loc_180005051
0x180004fc1  lea     r8, asc_180012800; "    "
0x180004fc8  mov     rdx, rsi; unsigned __int16 *
0x180004fcb  mov     rcx, rax; this
0x180004fce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fd3  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004fd7  test    r9, r9
0x180004fda  jz      short loc_180004FEE
0x180004fdc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004fe3  mov     rdx, rsi; unsigned __int16 *
0x180004fe6  mov     rcx, rax; this
0x180004fe9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fee  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004ff2  test    r9, r9
0x180004ff5  jz      short loc_180005009
0x180004ff7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004ffe  mov     rdx, rsi; unsigned __int16 *
0x180005001  mov     rcx, rax; this
0x180005004  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005009  mov     rcx, [rbx+28h]
0x18000500d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005011  mov     rdx, rsi; unsigned __int16 *
0x180005014  test    rcx, rcx
0x180005017  jz      short loc_18000502F
0x180005019  mov     [rsp+278h+lpBuffer], rcx
0x18000501e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005025  mov     rcx, rax; this
0x180005028  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000502d  jmp     short loc_180005051
0x18000502f  mov     rcx, rax; this
0x180005032  test    r9, r9
0x180005035  jz      short loc_180005045
0x180005037  lea     r8, aHs; "[%hs]\n"
0x18000503e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005043  jmp     short loc_180005051
0x180005045  lea     r8, asc_180012878; "\n"
0x18000504c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005051  xor     eax, eax
0x180005053  mov     rcx, [rsp+278h+var_38]
0x18000505b  xor     rcx, rsp; StackCookie
0x18000505e  call    __security_check_cookie
0x180005063  mov     rbx, [rsp+278h+arg_18]
0x18000506b  add     rsp, 250h
0x180005072  pop     r15
0x180005074  pop     r14
0x180005076  pop     rdi
0x180005077  pop     rsi
0x180005078  pop     rbp
0x180005079  retn
```
