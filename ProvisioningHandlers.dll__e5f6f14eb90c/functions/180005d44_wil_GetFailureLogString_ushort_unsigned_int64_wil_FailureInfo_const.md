# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005d44`
- end: `0x180006007`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180003b04`
- `0x180006ab0`
- `0x18000711c`
- `0x18000a730`

## callees

- `0x180005d44`
- `0x180006dc4`
- `0x180028832`
- `0x180028860`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005efd`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005efd`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005e76`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180005e76`

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
          v7 = (const char *)&dword_1800330E4;
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
0x180005d44  mov     [rsp+arg_18], rbx
0x180005d49  push    rbp
0x180005d4a  push    rsi
0x180005d4b  push    rdi
0x180005d4c  push    r14
0x180005d4e  push    r15
0x180005d50  sub     rsp, 250h
0x180005d57  mov     rax, cs:__security_cookie
0x180005d5e  xor     rax, rsp
0x180005d61  mov     [rsp+278h+var_38], rax
0x180005d69  mov     rbx, r8
0x180005d6c  mov     rsi, rdx
0x180005d6f  mov     r14, rcx
0x180005d72  xor     r15d, r15d
0x180005d75  test    rdx, rdx
0x180005d78  jz      loc_180005FDD
0x180005d7e  test    rcx, rcx
0x180005d81  jz      loc_180005FDD
0x180005d87  mov     [rcx], r15w
0x180005d8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005d92  test    rax, rax
0x180005d95  jz      short loc_180005DB8
0x180005d97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005d9e  jz      short loc_180005DB8
0x180005da0  mov     r8, rdx
0x180005da3  mov     rdx, rcx
0x180005da6  mov     rcx, rbx
0x180005da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dae  cmp     [r14], r15w
0x180005db2  jnz     loc_180005FDD
0x180005db8  mov     ecx, [rbx]
0x180005dba  mov     bpl, 8
0x180005dbd  test    ecx, ecx
0x180005dbf  jz      short loc_180005E0A
0x180005dc1  sub     ecx, 1
0x180005dc4  jz      short loc_180005DF2
0x180005dc6  sub     ecx, 1
0x180005dc9  jz      short loc_180005DE2
0x180005dcb  cmp     ecx, 1
0x180005dce  jz      short loc_180005DD9
0x180005dd0  lea     rdi, dword_1800330E4
0x180005dd7  jmp     short loc_180005E11
0x180005dd9  lea     rdi, aFailfast; "FailFast"
0x180005de0  jmp     short loc_180005E11
0x180005de2  lea     rax, aLoghr; "LogHr"
0x180005de9  lea     rdi, aLognt; "LogNt"
0x180005df0  jmp     short loc_180005E00
0x180005df2  lea     rax, aReturnhr; "ReturnHr"
0x180005df9  lea     rdi, aReturnnt; "ReturnNt"
0x180005e00  test    [rbx+4], bpl
0x180005e04  cmovz   rdi, rax
0x180005e08  jmp     short loc_180005E11
0x180005e0a  lea     rdi, aException; "Exception"
0x180005e11  xor     edx, edx; Val
0x180005e13  mov     r8d, 200h; Size
0x180005e19  lea     rcx, [rsp+278h+Buffer]; void *
0x180005e1e  call    memset_0
0x180005e23  test    [rbx+4], bpl
0x180005e27  jz      short loc_180005E4C
0x180005e29  mov     ebp, [rbx+0Ch]
0x180005e2c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005e33  test    rax, rax
0x180005e36  jz      short loc_180005E82
0x180005e38  mov     r8d, 100h
0x180005e3e  lea     rdx, [rsp+278h+Buffer]
0x180005e43  mov     ecx, ebp
0x180005e45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e4a  jmp     short loc_180005E82
0x180005e4c  mov     ebp, [rbx+8]
0x180005e4f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005e54  mov     [rsp+278h+nSize], 100h; nSize
0x180005e5c  lea     rax, [rsp+278h+Buffer]
0x180005e61  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005e66  mov     r9d, 400h; dwLanguageId
0x180005e6c  mov     r8d, ebp; dwMessageId
0x180005e6f  xor     edx, edx; lpSource
0x180005e71  mov     ecx, 1200h; dwFlags
0x180005e76  call    cs:__imp_FormatMessageW
0x180005e7d  nop     dword ptr [rax+rax+00h]
0x180005e82  lea     rsi, [r14+rsi*2]
0x180005e86  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005e8a  mov     rax, [rbx+88h]
0x180005e91  mov     rcx, [rbx+80h]
0x180005e98  mov     rdx, rsi; unsigned __int16 *
0x180005e9b  test    r9, r9
0x180005e9e  jz      short loc_180005EC2
0x180005ea0  mov     [rsp+278h+Arguments], rax
0x180005ea5  mov     qword ptr [rsp+278h+nSize], rcx
0x180005eaa  mov     eax, [rbx+40h]
0x180005ead  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005eb1  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005eb8  mov     rcx, r14; this
0x180005ebb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ec0  jmp     short loc_180005ED9
0x180005ec2  mov     [rsp+278h+lpBuffer], rax
0x180005ec7  mov     r9, rcx; unsigned __int16 *
0x180005eca  lea     r8, aHsP; "%hs!%p: "
0x180005ed1  mov     rcx, r14; this
0x180005ed4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ed9  mov     r14, rax
0x180005edc  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005ee3  test    r9, r9
0x180005ee6  jz      short loc_180005EFD
0x180005ee8  lea     r8, aCallerP; "(caller: %p) "
0x180005eef  mov     rdx, rsi; unsigned __int16 *
0x180005ef2  mov     rcx, rax; this
0x180005ef5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005efa  mov     r14, rax
0x180005efd  call    cs:__imp_GetCurrentThreadId
0x180005f04  nop     dword ptr [rax+rax+00h]
0x180005f09  lea     rcx, [rsp+278h+Buffer]
0x180005f0e  mov     [rsp+278h+var_240], rcx
0x180005f13  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005f17  mov     [rsp+278h+nSize], eax
0x180005f1b  mov     eax, [rbx+44h]
0x180005f1e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005f22  mov     r9, rdi; unsigned __int16 *
0x180005f25  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005f2c  mov     rdx, rsi; unsigned __int16 *
0x180005f2f  mov     rcx, r14; this
0x180005f32  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f37  cmp     [rbx+18h], r15
0x180005f3b  jnz     short loc_180005F4D
0x180005f3d  cmp     [rbx+48h], r15
0x180005f41  jnz     short loc_180005F4D
0x180005f43  cmp     [rbx+30h], r15
0x180005f47  jz      loc_180005FDD
0x180005f4d  lea     r8, asc_1800331D8; "    "
0x180005f54  mov     rdx, rsi; unsigned __int16 *
0x180005f57  mov     rcx, rax; this
0x180005f5a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f5f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005f63  test    r9, r9
0x180005f66  jz      short loc_180005F7A
0x180005f68  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005f6f  mov     rdx, rsi; unsigned __int16 *
0x180005f72  mov     rcx, rax; this
0x180005f75  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f7a  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005f7e  test    r9, r9
0x180005f81  jz      short loc_180005F95
0x180005f83  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005f8a  mov     rdx, rsi; unsigned __int16 *
0x180005f8d  mov     rcx, rax; this
0x180005f90  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f95  mov     rcx, [rbx+28h]
0x180005f99  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005f9d  mov     rdx, rsi; unsigned __int16 *
0x180005fa0  test    rcx, rcx
0x180005fa3  jz      short loc_180005FBB
0x180005fa5  mov     [rsp+278h+lpBuffer], rcx
0x180005faa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005fb1  mov     rcx, rax; this
0x180005fb4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fb9  jmp     short loc_180005FDD
0x180005fbb  mov     rcx, rax; this
0x180005fbe  test    r9, r9
0x180005fc1  jz      short loc_180005FD1
0x180005fc3  lea     r8, aHs; "[%hs]\n"
0x180005fca  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fcf  jmp     short loc_180005FDD
0x180005fd1  lea     r8, asc_180033250; "\n"
0x180005fd8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fdd  xor     eax, eax
0x180005fdf  mov     rcx, [rsp+278h+var_38]
0x180005fe7  xor     rcx, rsp; StackCookie
0x180005fea  call    __security_check_cookie
0x180005fef  mov     rbx, [rsp+278h+arg_18]
0x180005ff7  add     rsp, 250h
0x180005ffe  pop     r15
0x180006000  pop     r14
0x180006002  pop     rdi
0x180006003  pop     rsi
0x180006004  pop     rbp
0x180006005  retn
```
