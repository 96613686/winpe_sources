# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005dc8`
- end: `0x18000607e`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800055c0`
- `0x180006248`
- `0x1800065fc`
- `0x180007300`

## callees

- `0x180003980`
- `0x180004344`
- `0x180005dc8`
- `0x180006548`
- `0x180035010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f7b`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005efa`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005efa`

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
          v7 = (const char *)&byte_18003941D;
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
0x180005dc8  mov     [rsp+arg_18], rbx
0x180005dcd  push    rbp
0x180005dce  push    rsi
0x180005dcf  push    rdi
0x180005dd0  push    r14
0x180005dd2  push    r15
0x180005dd4  sub     rsp, 250h
0x180005ddb  mov     rax, cs:__security_cookie
0x180005de2  xor     rax, rsp
0x180005de5  mov     [rsp+278h+var_38], rax
0x180005ded  mov     rbx, r8
0x180005df0  mov     rsi, rdx
0x180005df3  mov     r14, rcx
0x180005df6  xor     r15d, r15d
0x180005df9  test    rdx, rdx
0x180005dfc  jz      loc_180006055
0x180005e02  test    rcx, rcx
0x180005e05  jz      loc_180006055
0x180005e0b  mov     [rcx], r15w
0x180005e0f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e16  test    rax, rax
0x180005e19  jz      short loc_180005E3C
0x180005e1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005e22  jz      short loc_180005E3C
0x180005e24  mov     r8, rdx
0x180005e27  mov     rdx, rcx
0x180005e2a  mov     rcx, rbx
0x180005e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e32  cmp     [r14], r15w
0x180005e36  jnz     loc_180006055
0x180005e3c  mov     ecx, [rbx]
0x180005e3e  mov     bpl, 8
0x180005e41  test    ecx, ecx
0x180005e43  jz      short loc_180005E8E
0x180005e45  sub     ecx, 1
0x180005e48  jz      short loc_180005E76
0x180005e4a  sub     ecx, 1
0x180005e4d  jz      short loc_180005E66
0x180005e4f  cmp     ecx, 1
0x180005e52  jz      short loc_180005E5D
0x180005e54  lea     rdi, byte_18003941D
0x180005e5b  jmp     short loc_180005E95
0x180005e5d  lea     rdi, aFailfast; "FailFast"
0x180005e64  jmp     short loc_180005E95
0x180005e66  lea     rax, aLoghr; "LogHr"
0x180005e6d  lea     rdi, aLognt; "LogNt"
0x180005e74  jmp     short loc_180005E84
0x180005e76  lea     rax, aReturnhr; "ReturnHr"
0x180005e7d  lea     rdi, aReturnnt; "ReturnNt"
0x180005e84  test    [rbx+4], bpl
0x180005e88  cmovz   rdi, rax
0x180005e8c  jmp     short loc_180005E95
0x180005e8e  lea     rdi, aException; "Exception"
0x180005e95  xor     edx, edx; Val
0x180005e97  mov     r8d, 200h; Size
0x180005e9d  lea     rcx, [rsp+278h+Buffer]; void *
0x180005ea2  call    memset_0
0x180005ea7  test    [rbx+4], bpl
0x180005eab  jz      short loc_180005ED0
0x180005ead  mov     ebp, [rbx+0Ch]
0x180005eb0  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005eb7  test    rax, rax
0x180005eba  jz      short loc_180005F00
0x180005ebc  mov     r8d, 100h
0x180005ec2  lea     rdx, [rsp+278h+Buffer]
0x180005ec7  mov     ecx, ebp
0x180005ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ece  jmp     short loc_180005F00
0x180005ed0  mov     ebp, [rbx+8]
0x180005ed3  mov     [rsp+278h+Arguments], r15; Arguments
0x180005ed8  mov     [rsp+278h+nSize], 100h; nSize
0x180005ee0  lea     rax, [rsp+278h+Buffer]
0x180005ee5  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005eea  mov     r9d, 400h; dwLanguageId
0x180005ef0  mov     r8d, ebp; dwMessageId
0x180005ef3  xor     edx, edx; lpSource
0x180005ef5  mov     ecx, 1200h; dwFlags
0x180005efa  call    cs:__imp_FormatMessageW
0x180005f00  lea     rsi, [r14+rsi*2]
0x180005f04  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005f08  mov     rax, [rbx+88h]
0x180005f0f  mov     rcx, [rbx+80h]
0x180005f16  mov     rdx, rsi; unsigned __int16 *
0x180005f19  test    r9, r9
0x180005f1c  jz      short loc_180005F40
0x180005f1e  mov     [rsp+278h+Arguments], rax
0x180005f23  mov     qword ptr [rsp+278h+nSize], rcx
0x180005f28  mov     eax, [rbx+40h]
0x180005f2b  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f2f  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005f36  mov     rcx, r14; this
0x180005f39  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f3e  jmp     short loc_180005F57
0x180005f40  mov     [rsp+278h+lpBuffer], rax
0x180005f45  mov     r9, rcx; unsigned __int16 *
0x180005f48  lea     r8, aHsP; "%hs!%p: "
0x180005f4f  mov     rcx, r14; this
0x180005f52  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f57  mov     r14, rax
0x180005f5a  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005f61  test    r9, r9
0x180005f64  jz      short loc_180005F7B
0x180005f66  lea     r8, aCallerP; "(caller: %p) "
0x180005f6d  mov     rdx, rsi; unsigned __int16 *
0x180005f70  mov     rcx, rax; this
0x180005f73  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f78  mov     r14, rax
0x180005f7b  call    cs:__imp_GetCurrentThreadId
0x180005f81  lea     rcx, [rsp+278h+Buffer]
0x180005f86  mov     [rsp+278h+var_240], rcx
0x180005f8b  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005f8f  mov     [rsp+278h+nSize], eax
0x180005f93  mov     eax, [rbx+44h]
0x180005f96  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f9a  mov     r9, rdi; unsigned __int16 *
0x180005f9d  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005fa4  mov     rdx, rsi; unsigned __int16 *
0x180005fa7  mov     rcx, r14; this
0x180005faa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005faf  cmp     [rbx+18h], r15
0x180005fb3  jnz     short loc_180005FC5
0x180005fb5  cmp     [rbx+48h], r15
0x180005fb9  jnz     short loc_180005FC5
0x180005fbb  cmp     [rbx+30h], r15
0x180005fbf  jz      loc_180006055
0x180005fc5  lea     r8, asc_180039538; "    "
0x180005fcc  mov     rdx, rsi; unsigned __int16 *
0x180005fcf  mov     rcx, rax; this
0x180005fd2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fd7  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005fdb  test    r9, r9
0x180005fde  jz      short loc_180005FF2
0x180005fe0  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005fe7  mov     rdx, rsi; unsigned __int16 *
0x180005fea  mov     rcx, rax; this
0x180005fed  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ff2  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005ff6  test    r9, r9
0x180005ff9  jz      short loc_18000600D
0x180005ffb  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180006002  mov     rdx, rsi; unsigned __int16 *
0x180006005  mov     rcx, rax; this
0x180006008  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000600d  mov     rcx, [rbx+28h]
0x180006011  mov     r9, [rbx+30h]; unsigned __int16 *
0x180006015  mov     rdx, rsi; unsigned __int16 *
0x180006018  test    rcx, rcx
0x18000601b  jz      short loc_180006033
0x18000601d  mov     [rsp+278h+lpBuffer], rcx
0x180006022  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180006029  mov     rcx, rax; this
0x18000602c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006031  jmp     short loc_180006055
0x180006033  mov     rcx, rax; this
0x180006036  test    r9, r9
0x180006039  jz      short loc_180006049
0x18000603b  lea     r8, aHs; "[%hs]\n"
0x180006042  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006047  jmp     short loc_180006055
0x180006049  lea     r8, asc_1800395B0; "\n"
0x180006050  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180006055  xor     eax, eax
0x180006057  mov     rcx, [rsp+278h+var_38]
0x18000605f  xor     rcx, rsp; StackCookie
0x180006062  call    __security_check_cookie
0x180006067  mov     rbx, [rsp+278h+arg_18]
0x18000606f  add     rsp, 250h
0x180006076  pop     r15
0x180006078  pop     r14
0x18000607a  pop     rdi
0x18000607b  pop     rsi
0x18000607c  pop     rbp
0x18000607d  retn
```
