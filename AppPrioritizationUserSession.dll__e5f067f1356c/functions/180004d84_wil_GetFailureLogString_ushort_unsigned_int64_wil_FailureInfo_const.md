# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004d84`
- end: `0x18000503a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003788`
- `0x180003a08`
- `0x180005778`
- `0x180007270`
- `0x180007e0c`
- `0x18000c195`
- `0x18000c2c9`

## callees

- `0x180002650`
- `0x1800032a4`
- `0x180004d84`
- `0x180005a78`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004eb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180004eb6`

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
          v7 = (const char *)&byte_18000EE30;
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
0x180004d84  mov     [rsp+arg_18], rbx
0x180004d89  push    rbp
0x180004d8a  push    rsi
0x180004d8b  push    rdi
0x180004d8c  push    r14
0x180004d8e  push    r15
0x180004d90  sub     rsp, 250h
0x180004d97  mov     rax, cs:__security_cookie
0x180004d9e  xor     rax, rsp
0x180004da1  mov     [rsp+278h+var_38], rax
0x180004da9  mov     rbx, r8
0x180004dac  mov     rsi, rdx
0x180004daf  mov     r14, rcx
0x180004db2  xor     r15d, r15d
0x180004db5  test    rdx, rdx
0x180004db8  jz      loc_180005011
0x180004dbe  test    rcx, rcx
0x180004dc1  jz      loc_180005011
0x180004dc7  mov     [rcx], r15w
0x180004dcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180004dd2  test    rax, rax
0x180004dd5  jz      short loc_180004DF8
0x180004dd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004dde  jz      short loc_180004DF8
0x180004de0  mov     r8, rdx
0x180004de3  mov     rdx, rcx
0x180004de6  mov     rcx, rbx
0x180004de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dee  cmp     [r14], r15w
0x180004df2  jnz     loc_180005011
0x180004df8  mov     ecx, [rbx]
0x180004dfa  mov     bpl, 8
0x180004dfd  test    ecx, ecx
0x180004dff  jz      short loc_180004E4A
0x180004e01  sub     ecx, 1
0x180004e04  jz      short loc_180004E32
0x180004e06  sub     ecx, 1
0x180004e09  jz      short loc_180004E22
0x180004e0b  cmp     ecx, 1
0x180004e0e  jz      short loc_180004E19
0x180004e10  lea     rdi, byte_18000EE30
0x180004e17  jmp     short loc_180004E51
0x180004e19  lea     rdi, aFailfast; "FailFast"
0x180004e20  jmp     short loc_180004E51
0x180004e22  lea     rax, aLoghr; "LogHr"
0x180004e29  lea     rdi, aLognt; "LogNt"
0x180004e30  jmp     short loc_180004E40
0x180004e32  lea     rax, aReturnhr; "ReturnHr"
0x180004e39  lea     rdi, aReturnnt; "ReturnNt"
0x180004e40  test    [rbx+4], bpl
0x180004e44  cmovz   rdi, rax
0x180004e48  jmp     short loc_180004E51
0x180004e4a  lea     rdi, aException; "Exception"
0x180004e51  xor     edx, edx; Val
0x180004e53  mov     r8d, 200h; Size
0x180004e59  lea     rcx, [rsp+278h+Buffer]; void *
0x180004e5e  call    memset_0
0x180004e63  test    [rbx+4], bpl
0x180004e67  jz      short loc_180004E8C
0x180004e69  mov     ebp, [rbx+0Ch]
0x180004e6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180004e73  test    rax, rax
0x180004e76  jz      short loc_180004EBC
0x180004e78  mov     r8d, 100h
0x180004e7e  lea     rdx, [rsp+278h+Buffer]
0x180004e83  mov     ecx, ebp
0x180004e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e8a  jmp     short loc_180004EBC
0x180004e8c  mov     ebp, [rbx+8]
0x180004e8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180004e94  mov     [rsp+278h+nSize], 100h; nSize
0x180004e9c  lea     rax, [rsp+278h+Buffer]
0x180004ea1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180004ea6  mov     r9d, 400h; dwLanguageId
0x180004eac  mov     r8d, ebp; dwMessageId
0x180004eaf  xor     edx, edx; lpSource
0x180004eb1  mov     ecx, 1200h; dwFlags
0x180004eb6  call    cs:__imp_FormatMessageW
0x180004ebc  lea     rsi, [r14+rsi*2]
0x180004ec0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180004ec4  mov     rax, [rbx+88h]
0x180004ecb  mov     rcx, [rbx+80h]
0x180004ed2  mov     rdx, rsi; unsigned __int16 *
0x180004ed5  test    r9, r9
0x180004ed8  jz      short loc_180004EFC
0x180004eda  mov     [rsp+278h+Arguments], rax
0x180004edf  mov     qword ptr [rsp+278h+nSize], rcx
0x180004ee4  mov     eax, [rbx+40h]
0x180004ee7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004eeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180004ef2  mov     rcx, r14; this
0x180004ef5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004efa  jmp     short loc_180004F13
0x180004efc  mov     [rsp+278h+lpBuffer], rax
0x180004f01  mov     r9, rcx; unsigned __int16 *
0x180004f04  lea     r8, aHsP; "%hs!%p: "
0x180004f0b  mov     rcx, r14; this
0x180004f0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f13  mov     r14, rax
0x180004f16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180004f1d  test    r9, r9
0x180004f20  jz      short loc_180004F37
0x180004f22  lea     r8, aCallerP; "(caller: %p) "
0x180004f29  mov     rdx, rsi; unsigned __int16 *
0x180004f2c  mov     rcx, rax; this
0x180004f2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f34  mov     r14, rax
0x180004f37  call    cs:__imp_GetCurrentThreadId
0x180004f3d  lea     rcx, [rsp+278h+Buffer]
0x180004f42  mov     [rsp+278h+var_240], rcx
0x180004f47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180004f4b  mov     [rsp+278h+nSize], eax
0x180004f4f  mov     eax, [rbx+44h]
0x180004f52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180004f56  mov     r9, rdi; unsigned __int16 *
0x180004f59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180004f60  mov     rdx, rsi; unsigned __int16 *
0x180004f63  mov     rcx, r14; this
0x180004f66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f6b  cmp     [rbx+18h], r15
0x180004f6f  jnz     short loc_180004F81
0x180004f71  cmp     [rbx+48h], r15
0x180004f75  jnz     short loc_180004F81
0x180004f77  cmp     [rbx+30h], r15
0x180004f7b  jz      loc_180005011
0x180004f81  lea     r8, asc_18000EF38; "    "
0x180004f88  mov     rdx, rsi; unsigned __int16 *
0x180004f8b  mov     rcx, rax; this
0x180004f8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004f93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180004f97  test    r9, r9
0x180004f9a  jz      short loc_180004FAE
0x180004f9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180004fa3  mov     rdx, rsi; unsigned __int16 *
0x180004fa6  mov     rcx, rax; this
0x180004fa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180004fb2  test    r9, r9
0x180004fb5  jz      short loc_180004FC9
0x180004fb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180004fbe  mov     rdx, rsi; unsigned __int16 *
0x180004fc1  mov     rcx, rax; this
0x180004fc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fc9  mov     rcx, [rbx+28h]
0x180004fcd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180004fd1  mov     rdx, rsi; unsigned __int16 *
0x180004fd4  test    rcx, rcx
0x180004fd7  jz      short loc_180004FEF
0x180004fd9  mov     [rsp+278h+lpBuffer], rcx
0x180004fde  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180004fe5  mov     rcx, rax; this
0x180004fe8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180004fed  jmp     short loc_180005011
0x180004fef  mov     rcx, rax; this
0x180004ff2  test    r9, r9
0x180004ff5  jz      short loc_180005005
0x180004ff7  lea     r8, aHs; "[%hs]\n"
0x180004ffe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005003  jmp     short loc_180005011
0x180005005  lea     r8, asc_18000EFB0; "\n"
0x18000500c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005011  xor     eax, eax
0x180005013  mov     rcx, [rsp+278h+var_38]
0x18000501b  xor     rcx, rsp; StackCookie
0x18000501e  call    __security_check_cookie
0x180005023  mov     rbx, [rsp+278h+arg_18]
0x18000502b  add     rsp, 250h
0x180005032  pop     r15
0x180005034  pop     r14
0x180005036  pop     rdi
0x180005037  pop     rsi
0x180005038  pop     rbp
0x180005039  retn
```
