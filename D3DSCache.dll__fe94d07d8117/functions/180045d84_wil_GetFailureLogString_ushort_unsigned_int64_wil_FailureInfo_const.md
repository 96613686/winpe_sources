# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180045d84`
- end: `0x18004603a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180046920`
- `0x180047fac`
- `0x180048214`
- `0x18004b550`

## callees

- `0x1800449f0`
- `0x180045374`
- `0x180045d84`
- `0x180046330`
- `0x1800a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045f37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180045f37`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180045eb6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180045eb6`

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
          v7 = (const char *)&Src;
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
0x180045d84  mov     [rsp+arg_18], rbx
0x180045d89  push    rbp
0x180045d8a  push    rsi
0x180045d8b  push    rdi
0x180045d8c  push    r14
0x180045d8e  push    r15
0x180045d90  sub     rsp, 250h
0x180045d97  mov     rax, cs:__security_cookie
0x180045d9e  xor     rax, rsp
0x180045da1  mov     [rsp+278h+var_38], rax
0x180045da9  mov     rbx, r8
0x180045dac  mov     rsi, rdx
0x180045daf  mov     r14, rcx
0x180045db2  xor     r15d, r15d
0x180045db5  test    rdx, rdx
0x180045db8  jz      loc_180046011
0x180045dbe  test    rcx, rcx
0x180045dc1  jz      loc_180046011
0x180045dc7  mov     [rcx], r15w
0x180045dcb  mov     rax, cs:g_pfnResultLoggingCallback
0x180045dd2  test    rax, rax
0x180045dd5  jz      short loc_180045DF8
0x180045dd7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180045dde  jz      short loc_180045DF8
0x180045de0  mov     r8, rdx
0x180045de3  mov     rdx, rcx
0x180045de6  mov     rcx, rbx
0x180045de9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045dee  cmp     [r14], r15w
0x180045df2  jnz     loc_180046011
0x180045df8  mov     ecx, [rbx]
0x180045dfa  mov     bpl, 8
0x180045dfd  test    ecx, ecx
0x180045dff  jz      short loc_180045E4A
0x180045e01  sub     ecx, 1
0x180045e04  jz      short loc_180045E32
0x180045e06  sub     ecx, 1
0x180045e09  jz      short loc_180045E22
0x180045e0b  cmp     ecx, 1
0x180045e0e  jz      short loc_180045E19
0x180045e10  lea     rdi, Src
0x180045e17  jmp     short loc_180045E51
0x180045e19  lea     rdi, aFailfast; "FailFast"
0x180045e20  jmp     short loc_180045E51
0x180045e22  lea     rax, aLoghr; "LogHr"
0x180045e29  lea     rdi, aLognt; "LogNt"
0x180045e30  jmp     short loc_180045E40
0x180045e32  lea     rax, aReturnhr; "ReturnHr"
0x180045e39  lea     rdi, aReturnnt; "ReturnNt"
0x180045e40  test    [rbx+4], bpl
0x180045e44  cmovz   rdi, rax
0x180045e48  jmp     short loc_180045E51
0x180045e4a  lea     rdi, aException; "Exception"
0x180045e51  xor     edx, edx; Val
0x180045e53  mov     r8d, 200h; Size
0x180045e59  lea     rcx, [rsp+278h+Buffer]; void *
0x180045e5e  call    memset_0
0x180045e63  test    [rbx+4], bpl
0x180045e67  jz      short loc_180045E8C
0x180045e69  mov     ebp, [rbx+0Ch]
0x180045e6c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180045e73  test    rax, rax
0x180045e76  jz      short loc_180045EBC
0x180045e78  mov     r8d, 100h
0x180045e7e  lea     rdx, [rsp+278h+Buffer]
0x180045e83  mov     ecx, ebp
0x180045e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180045e8a  jmp     short loc_180045EBC
0x180045e8c  mov     ebp, [rbx+8]
0x180045e8f  mov     [rsp+278h+Arguments], r15; Arguments
0x180045e94  mov     [rsp+278h+nSize], 100h; nSize
0x180045e9c  lea     rax, [rsp+278h+Buffer]
0x180045ea1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180045ea6  mov     r9d, 400h; dwLanguageId
0x180045eac  mov     r8d, ebp; dwMessageId
0x180045eaf  xor     edx, edx; lpSource
0x180045eb1  mov     ecx, 1200h; dwFlags
0x180045eb6  call    cs:__imp_FormatMessageW
0x180045ebc  lea     rsi, [r14+rsi*2]
0x180045ec0  mov     r9, [rbx+38h]; unsigned __int16 *
0x180045ec4  mov     rax, [rbx+88h]
0x180045ecb  mov     rcx, [rbx+80h]
0x180045ed2  mov     rdx, rsi; unsigned __int16 *
0x180045ed5  test    r9, r9
0x180045ed8  jz      short loc_180045EFC
0x180045eda  mov     [rsp+278h+Arguments], rax
0x180045edf  mov     qword ptr [rsp+278h+nSize], rcx
0x180045ee4  mov     eax, [rbx+40h]
0x180045ee7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180045eeb  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180045ef2  mov     rcx, r14; this
0x180045ef5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045efa  jmp     short loc_180045F13
0x180045efc  mov     [rsp+278h+lpBuffer], rax
0x180045f01  mov     r9, rcx; unsigned __int16 *
0x180045f04  lea     r8, aHsP; "%hs!%p: "
0x180045f0b  mov     rcx, r14; this
0x180045f0e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045f13  mov     r14, rax
0x180045f16  mov     r9, [rbx+90h]; unsigned __int16 *
0x180045f1d  test    r9, r9
0x180045f20  jz      short loc_180045F37
0x180045f22  lea     r8, aCallerP; "(caller: %p) "
0x180045f29  mov     rdx, rsi; unsigned __int16 *
0x180045f2c  mov     rcx, rax; this
0x180045f2f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045f34  mov     r14, rax
0x180045f37  call    cs:__imp_GetCurrentThreadId
0x180045f3d  lea     rcx, [rsp+278h+Buffer]
0x180045f42  mov     [rsp+278h+var_240], rcx
0x180045f47  mov     dword ptr [rsp+278h+Arguments], ebp
0x180045f4b  mov     [rsp+278h+nSize], eax
0x180045f4f  mov     eax, [rbx+44h]
0x180045f52  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180045f56  mov     r9, rdi; unsigned __int16 *
0x180045f59  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180045f60  mov     rdx, rsi; unsigned __int16 *
0x180045f63  mov     rcx, r14; this
0x180045f66  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045f6b  cmp     [rbx+18h], r15
0x180045f6f  jnz     short loc_180045F81
0x180045f71  cmp     [rbx+48h], r15
0x180045f75  jnz     short loc_180045F81
0x180045f77  cmp     [rbx+30h], r15
0x180045f7b  jz      loc_180046011
0x180045f81  lea     r8, asc_1800AE358; "    "
0x180045f88  mov     rdx, rsi; unsigned __int16 *
0x180045f8b  mov     rcx, rax; this
0x180045f8e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045f93  mov     r9, [rbx+18h]; unsigned __int16 *
0x180045f97  test    r9, r9
0x180045f9a  jz      short loc_180045FAE
0x180045f9c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180045fa3  mov     rdx, rsi; unsigned __int16 *
0x180045fa6  mov     rcx, rax; this
0x180045fa9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045fae  mov     r9, [rbx+48h]; unsigned __int16 *
0x180045fb2  test    r9, r9
0x180045fb5  jz      short loc_180045FC9
0x180045fb7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180045fbe  mov     rdx, rsi; unsigned __int16 *
0x180045fc1  mov     rcx, rax; this
0x180045fc4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045fc9  mov     rcx, [rbx+28h]
0x180045fcd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180045fd1  mov     rdx, rsi; unsigned __int16 *
0x180045fd4  test    rcx, rcx
0x180045fd7  jz      short loc_180045FEF
0x180045fd9  mov     [rsp+278h+lpBuffer], rcx
0x180045fde  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180045fe5  mov     rcx, rax; this
0x180045fe8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180045fed  jmp     short loc_180046011
0x180045fef  mov     rcx, rax; this
0x180045ff2  test    r9, r9
0x180045ff5  jz      short loc_180046005
0x180045ff7  lea     r8, aHs; "[%hs]\n"
0x180045ffe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046003  jmp     short loc_180046011
0x180046005  lea     r8, asc_1800AE3D0; "\n"
0x18004600c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180046011  xor     eax, eax
0x180046013  mov     rcx, [rsp+278h+var_38]
0x18004601b  xor     rcx, rsp; StackCookie
0x18004601e  call    __security_check_cookie
0x180046023  mov     rbx, [rsp+278h+arg_18]
0x18004602b  add     rsp, 250h
0x180046032  pop     r15
0x180046034  pop     r14
0x180046036  pop     rdi
0x180046037  pop     rsi
0x180046038  pop     rbp
0x180046039  retn
```
