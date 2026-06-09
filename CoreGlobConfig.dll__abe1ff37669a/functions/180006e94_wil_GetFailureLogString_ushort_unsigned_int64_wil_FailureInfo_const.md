# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180006e94`
- end: `0x18000714a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180005fb0`
- `0x180007918`
- `0x180007dcc`
- `0x1800090f0`

## callees

- `0x180002380`
- `0x1800032dc`
- `0x180006e94`
- `0x180007c18`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007047`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007047`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006fc6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180006fc6`

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
          v7 = (const char *)&dword_180028054;
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
0x180006e94  mov     [rsp+arg_18], rbx
0x180006e99  push    rbp
0x180006e9a  push    rsi
0x180006e9b  push    rdi
0x180006e9c  push    r14
0x180006e9e  push    r15
0x180006ea0  sub     rsp, 250h
0x180006ea7  mov     rax, cs:__security_cookie
0x180006eae  xor     rax, rsp
0x180006eb1  mov     [rsp+278h+var_38], rax
0x180006eb9  mov     rbx, r8
0x180006ebc  mov     rsi, rdx
0x180006ebf  mov     r14, rcx
0x180006ec2  xor     r15d, r15d
0x180006ec5  test    rdx, rdx
0x180006ec8  jz      loc_180007121
0x180006ece  test    rcx, rcx
0x180006ed1  jz      loc_180007121
0x180006ed7  mov     [rcx], r15w
0x180006edb  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ee2  test    rax, rax
0x180006ee5  jz      short loc_180006F08
0x180006ee7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180006eee  jz      short loc_180006F08
0x180006ef0  mov     r8, rdx
0x180006ef3  mov     rdx, rcx
0x180006ef6  mov     rcx, rbx
0x180006ef9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006efe  cmp     [r14], r15w
0x180006f02  jnz     loc_180007121
0x180006f08  mov     ecx, [rbx]
0x180006f0a  mov     bpl, 8
0x180006f0d  test    ecx, ecx
0x180006f0f  jz      short loc_180006F5A
0x180006f11  sub     ecx, 1
0x180006f14  jz      short loc_180006F42
0x180006f16  sub     ecx, 1
0x180006f19  jz      short loc_180006F32
0x180006f1b  cmp     ecx, 1
0x180006f1e  jz      short loc_180006F29
0x180006f20  lea     rdi, dword_180028054
0x180006f27  jmp     short loc_180006F61
0x180006f29  lea     rdi, aFailfast; "FailFast"
0x180006f30  jmp     short loc_180006F61
0x180006f32  lea     rax, aLoghr; "LogHr"
0x180006f39  lea     rdi, aLognt; "LogNt"
0x180006f40  jmp     short loc_180006F50
0x180006f42  lea     rax, aReturnhr; "ReturnHr"
0x180006f49  lea     rdi, aReturnnt; "ReturnNt"
0x180006f50  test    [rbx+4], bpl
0x180006f54  cmovz   rdi, rax
0x180006f58  jmp     short loc_180006F61
0x180006f5a  lea     rdi, aException; "Exception"
0x180006f61  xor     edx, edx; Val
0x180006f63  mov     r8d, 200h; Size
0x180006f69  lea     rcx, [rsp+278h+Buffer]; void *
0x180006f6e  call    memset_0
0x180006f73  test    [rbx+4], bpl
0x180006f77  jz      short loc_180006F9C
0x180006f79  mov     ebp, [rbx+0Ch]
0x180006f7c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180006f83  test    rax, rax
0x180006f86  jz      short loc_180006FCC
0x180006f88  mov     r8d, 100h
0x180006f8e  lea     rdx, [rsp+278h+Buffer]
0x180006f93  mov     ecx, ebp
0x180006f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9a  jmp     short loc_180006FCC
0x180006f9c  mov     ebp, [rbx+8]
0x180006f9f  mov     [rsp+278h+Arguments], r15; Arguments
0x180006fa4  mov     [rsp+278h+nSize], 100h; nSize
0x180006fac  lea     rax, [rsp+278h+Buffer]
0x180006fb1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180006fb6  mov     r9d, 400h; dwLanguageId
0x180006fbc  mov     r8d, ebp; dwMessageId
0x180006fbf  xor     edx, edx; lpSource
0x180006fc1  mov     ecx, 1200h; dwFlags
0x180006fc6  call    cs:__imp_FormatMessageW
0x180006fcc  lea     rsi, [r14+rsi*2]
0x180006fd0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180006fd4  mov     rax, [rbx+88h]
0x180006fdb  mov     rcx, [rbx+80h]
0x180006fe2  mov     rdx, rsi; unsigned __int16 *
0x180006fe5  test    r9, r9
0x180006fe8  jz      short loc_18000700C
0x180006fea  mov     [rsp+278h+Arguments], rax
0x180006fef  mov     qword ptr [rsp+278h+nSize], rcx
0x180006ff4  mov     eax, [rbx+40h]
0x180006ff7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180006ffb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007002  mov     rcx, r14; this
0x180007005  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000700a  jmp     short loc_180007023
0x18000700c  mov     [rsp+278h+lpBuffer], rax
0x180007011  mov     r9, rcx; unsigned __int16 *
0x180007014  lea     r8, aHsP; "%hs!%p: "
0x18000701b  mov     rcx, r14; this
0x18000701e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007023  mov     r14, rax
0x180007026  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000702d  test    r9, r9
0x180007030  jz      short loc_180007047
0x180007032  lea     r8, aCallerP; "(caller: %p) "
0x180007039  mov     rdx, rsi; unsigned __int16 *
0x18000703c  mov     rcx, rax; this
0x18000703f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007044  mov     r14, rax
0x180007047  call    cs:__imp_GetCurrentThreadId
0x18000704d  lea     rcx, [rsp+278h+Buffer]
0x180007052  mov     [rsp+278h+var_240], rcx
0x180007057  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000705b  mov     [rsp+278h+nSize], eax
0x18000705f  mov     eax, [rbx+44h]
0x180007062  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007066  mov     r9, rdi; unsigned __int16 *
0x180007069  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007070  mov     rdx, rsi; unsigned __int16 *
0x180007073  mov     rcx, r14; this
0x180007076  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000707b  cmp     [rbx+18h], r15
0x18000707f  jnz     short loc_180007091
0x180007081  cmp     [rbx+48h], r15
0x180007085  jnz     short loc_180007091
0x180007087  cmp     [rbx+30h], r15
0x18000708b  jz      loc_180007121
0x180007091  lea     r8, asc_180028158; "    "
0x180007098  mov     rdx, rsi; unsigned __int16 *
0x18000709b  mov     rcx, rax; this
0x18000709e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800070a3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800070a7  test    r9, r9
0x1800070aa  jz      short loc_1800070BE
0x1800070ac  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800070b3  mov     rdx, rsi; unsigned __int16 *
0x1800070b6  mov     rcx, rax; this
0x1800070b9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800070be  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800070c2  test    r9, r9
0x1800070c5  jz      short loc_1800070D9
0x1800070c7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800070ce  mov     rdx, rsi; unsigned __int16 *
0x1800070d1  mov     rcx, rax; this
0x1800070d4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800070d9  mov     rcx, [rbx+28h]
0x1800070dd  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800070e1  mov     rdx, rsi; unsigned __int16 *
0x1800070e4  test    rcx, rcx
0x1800070e7  jz      short loc_1800070FF
0x1800070e9  mov     [rsp+278h+lpBuffer], rcx
0x1800070ee  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800070f5  mov     rcx, rax; this
0x1800070f8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800070fd  jmp     short loc_180007121
0x1800070ff  mov     rcx, rax; this
0x180007102  test    r9, r9
0x180007105  jz      short loc_180007115
0x180007107  lea     r8, aHs; "[%hs]\n"
0x18000710e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007113  jmp     short loc_180007121
0x180007115  lea     r8, asc_1800281D0; "\n"
0x18000711c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007121  xor     eax, eax
0x180007123  mov     rcx, [rsp+278h+var_38]
0x18000712b  xor     rcx, rsp; StackCookie
0x18000712e  call    __security_check_cookie
0x180007133  mov     rbx, [rsp+278h+arg_18]
0x18000713b  add     rsp, 250h
0x180007142  pop     r15
0x180007144  pop     r14
0x180007146  pop     rdi
0x180007147  pop     rsi
0x180007148  pop     rbp
0x180007149  retn
```
