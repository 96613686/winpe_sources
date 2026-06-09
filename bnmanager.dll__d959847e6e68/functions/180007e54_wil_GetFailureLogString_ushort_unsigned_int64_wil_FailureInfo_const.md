# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007e54`
- end: `0x18000810a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180002a74`
- `0x180002cdc`
- `0x1800088d8`
- `0x18000c030`

## callees

- `0x1800017c0`
- `0x180002290`
- `0x180007e54`
- `0x180008bd8`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007f86`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007f86`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008007`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008007`

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
          v7 = (const char *)&byte_18000E9B0;
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
0x180007e54  mov     [rsp+arg_18], rbx
0x180007e59  push    rbp
0x180007e5a  push    rsi
0x180007e5b  push    rdi
0x180007e5c  push    r14
0x180007e5e  push    r15
0x180007e60  sub     rsp, 250h
0x180007e67  mov     rax, cs:__security_cookie
0x180007e6e  xor     rax, rsp
0x180007e71  mov     [rsp+278h+var_38], rax
0x180007e79  mov     rbx, r8
0x180007e7c  mov     rsi, rdx
0x180007e7f  mov     r14, rcx
0x180007e82  xor     r15d, r15d
0x180007e85  test    rdx, rdx
0x180007e88  jz      loc_1800080E1
0x180007e8e  test    rcx, rcx
0x180007e91  jz      loc_1800080E1
0x180007e97  mov     [rcx], r15w
0x180007e9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007ea2  test    rax, rax
0x180007ea5  jz      short loc_180007EC8
0x180007ea7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007eae  jz      short loc_180007EC8
0x180007eb0  mov     r8, rdx
0x180007eb3  mov     rdx, rcx
0x180007eb6  mov     rcx, rbx
0x180007eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ebe  cmp     [r14], r15w
0x180007ec2  jnz     loc_1800080E1
0x180007ec8  mov     ecx, [rbx]
0x180007eca  mov     bpl, 8
0x180007ecd  test    ecx, ecx
0x180007ecf  jz      short loc_180007F1A
0x180007ed1  sub     ecx, 1
0x180007ed4  jz      short loc_180007F02
0x180007ed6  sub     ecx, 1
0x180007ed9  jz      short loc_180007EF2
0x180007edb  cmp     ecx, 1
0x180007ede  jz      short loc_180007EE9
0x180007ee0  lea     rdi, byte_18000E9B0
0x180007ee7  jmp     short loc_180007F21
0x180007ee9  lea     rdi, aFailfast; "FailFast"
0x180007ef0  jmp     short loc_180007F21
0x180007ef2  lea     rax, aLoghr; "LogHr"
0x180007ef9  lea     rdi, aLognt; "LogNt"
0x180007f00  jmp     short loc_180007F10
0x180007f02  lea     rax, aReturnhr; "ReturnHr"
0x180007f09  lea     rdi, aReturnnt; "ReturnNt"
0x180007f10  test    [rbx+4], bpl
0x180007f14  cmovz   rdi, rax
0x180007f18  jmp     short loc_180007F21
0x180007f1a  lea     rdi, aException; "Exception"
0x180007f21  xor     edx, edx; Val
0x180007f23  mov     r8d, 200h; Size
0x180007f29  lea     rcx, [rsp+278h+Buffer]; void *
0x180007f2e  call    memset_0
0x180007f33  test    [rbx+4], bpl
0x180007f37  jz      short loc_180007F5C
0x180007f39  mov     ebp, [rbx+0Ch]
0x180007f3c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007f43  test    rax, rax
0x180007f46  jz      short loc_180007F8C
0x180007f48  mov     r8d, 100h
0x180007f4e  lea     rdx, [rsp+278h+Buffer]
0x180007f53  mov     ecx, ebp
0x180007f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f5a  jmp     short loc_180007F8C
0x180007f5c  mov     ebp, [rbx+8]
0x180007f5f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007f64  mov     [rsp+278h+nSize], 100h; nSize
0x180007f6c  lea     rax, [rsp+278h+Buffer]
0x180007f71  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007f76  mov     r9d, 400h; dwLanguageId
0x180007f7c  mov     r8d, ebp; dwMessageId
0x180007f7f  xor     edx, edx; lpSource
0x180007f81  mov     ecx, 1200h; dwFlags
0x180007f86  call    cs:__imp_FormatMessageW
0x180007f8c  lea     rsi, [r14+rsi*2]
0x180007f90  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007f94  mov     rax, [rbx+88h]
0x180007f9b  mov     rcx, [rbx+80h]
0x180007fa2  mov     rdx, rsi; unsigned __int16 *
0x180007fa5  test    r9, r9
0x180007fa8  jz      short loc_180007FCC
0x180007faa  mov     [rsp+278h+Arguments], rax
0x180007faf  mov     qword ptr [rsp+278h+nSize], rcx
0x180007fb4  mov     eax, [rbx+40h]
0x180007fb7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007fbb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007fc2  mov     rcx, r14; this
0x180007fc5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007fca  jmp     short loc_180007FE3
0x180007fcc  mov     [rsp+278h+lpBuffer], rax
0x180007fd1  mov     r9, rcx; unsigned __int16 *
0x180007fd4  lea     r8, aHsP; "%hs!%p: "
0x180007fdb  mov     rcx, r14; this
0x180007fde  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007fe3  mov     r14, rax
0x180007fe6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007fed  test    r9, r9
0x180007ff0  jz      short loc_180008007
0x180007ff2  lea     r8, aCallerP; "(caller: %p) "
0x180007ff9  mov     rdx, rsi; unsigned __int16 *
0x180007ffc  mov     rcx, rax; this
0x180007fff  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008004  mov     r14, rax
0x180008007  call    cs:__imp_GetCurrentThreadId
0x18000800d  lea     rcx, [rsp+278h+Buffer]
0x180008012  mov     [rsp+278h+var_240], rcx
0x180008017  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000801b  mov     [rsp+278h+nSize], eax
0x18000801f  mov     eax, [rbx+44h]
0x180008022  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008026  mov     r9, rdi; unsigned __int16 *
0x180008029  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008030  mov     rdx, rsi; unsigned __int16 *
0x180008033  mov     rcx, r14; this
0x180008036  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000803b  cmp     [rbx+18h], r15
0x18000803f  jnz     short loc_180008051
0x180008041  cmp     [rbx+48h], r15
0x180008045  jnz     short loc_180008051
0x180008047  cmp     [rbx+30h], r15
0x18000804b  jz      loc_1800080E1
0x180008051  lea     r8, asc_18000EAE0; "    "
0x180008058  mov     rdx, rsi; unsigned __int16 *
0x18000805b  mov     rcx, rax; this
0x18000805e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008063  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008067  test    r9, r9
0x18000806a  jz      short loc_18000807E
0x18000806c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008073  mov     rdx, rsi; unsigned __int16 *
0x180008076  mov     rcx, rax; this
0x180008079  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000807e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008082  test    r9, r9
0x180008085  jz      short loc_180008099
0x180008087  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000808e  mov     rdx, rsi; unsigned __int16 *
0x180008091  mov     rcx, rax; this
0x180008094  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008099  mov     rcx, [rbx+28h]
0x18000809d  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800080a1  mov     rdx, rsi; unsigned __int16 *
0x1800080a4  test    rcx, rcx
0x1800080a7  jz      short loc_1800080BF
0x1800080a9  mov     [rsp+278h+lpBuffer], rcx
0x1800080ae  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800080b5  mov     rcx, rax; this
0x1800080b8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800080bd  jmp     short loc_1800080E1
0x1800080bf  mov     rcx, rax; this
0x1800080c2  test    r9, r9
0x1800080c5  jz      short loc_1800080D5
0x1800080c7  lea     r8, aHs; "[%hs]\n"
0x1800080ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800080d3  jmp     short loc_1800080E1
0x1800080d5  lea     r8, asc_18000EB58; "\n"
0x1800080dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800080e1  xor     eax, eax
0x1800080e3  mov     rcx, [rsp+278h+var_38]
0x1800080eb  xor     rcx, rsp; StackCookie
0x1800080ee  call    __security_check_cookie
0x1800080f3  mov     rbx, [rsp+278h+arg_18]
0x1800080fb  add     rsp, 250h
0x180008102  pop     r15
0x180008104  pop     r14
0x180008106  pop     rdi
0x180008107  pop     rsi
0x180008108  pop     rbp
0x180008109  retn
```
