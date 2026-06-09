# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180007c24`
- end: `0x180007eda`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006894`
- `0x180008648`
- `0x180009e30`

## callees

- `0x180004c70`
- `0x1800056e0`
- `0x180007c24`
- `0x180008948`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007dd7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007dd7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007d56`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007d56`

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
          v7 = (const char *)&byte_1800168F5;
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
0x180007c24  mov     [rsp+arg_18], rbx
0x180007c29  push    rbp
0x180007c2a  push    rsi
0x180007c2b  push    rdi
0x180007c2c  push    r14
0x180007c2e  push    r15
0x180007c30  sub     rsp, 250h
0x180007c37  mov     rax, cs:__security_cookie
0x180007c3e  xor     rax, rsp
0x180007c41  mov     [rsp+278h+var_38], rax
0x180007c49  mov     rbx, r8
0x180007c4c  mov     rsi, rdx
0x180007c4f  mov     r14, rcx
0x180007c52  xor     r15d, r15d
0x180007c55  test    rdx, rdx
0x180007c58  jz      loc_180007EB1
0x180007c5e  test    rcx, rcx
0x180007c61  jz      loc_180007EB1
0x180007c67  mov     [rcx], r15w
0x180007c6b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007c72  test    rax, rax
0x180007c75  jz      short loc_180007C98
0x180007c77  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007c7e  jz      short loc_180007C98
0x180007c80  mov     r8, rdx
0x180007c83  mov     rdx, rcx
0x180007c86  mov     rcx, rbx
0x180007c89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c8e  cmp     [r14], r15w
0x180007c92  jnz     loc_180007EB1
0x180007c98  mov     ecx, [rbx]
0x180007c9a  mov     bpl, 8
0x180007c9d  test    ecx, ecx
0x180007c9f  jz      short loc_180007CEA
0x180007ca1  sub     ecx, 1
0x180007ca4  jz      short loc_180007CD2
0x180007ca6  sub     ecx, 1
0x180007ca9  jz      short loc_180007CC2
0x180007cab  cmp     ecx, 1
0x180007cae  jz      short loc_180007CB9
0x180007cb0  lea     rdi, byte_1800168F5
0x180007cb7  jmp     short loc_180007CF1
0x180007cb9  lea     rdi, aFailfast; "FailFast"
0x180007cc0  jmp     short loc_180007CF1
0x180007cc2  lea     rax, aLoghr; "LogHr"
0x180007cc9  lea     rdi, aLognt; "LogNt"
0x180007cd0  jmp     short loc_180007CE0
0x180007cd2  lea     rax, aReturnhr; "ReturnHr"
0x180007cd9  lea     rdi, aReturnnt; "ReturnNt"
0x180007ce0  test    [rbx+4], bpl
0x180007ce4  cmovz   rdi, rax
0x180007ce8  jmp     short loc_180007CF1
0x180007cea  lea     rdi, aException; "Exception"
0x180007cf1  xor     edx, edx; Val
0x180007cf3  mov     r8d, 200h; Size
0x180007cf9  lea     rcx, [rsp+278h+Buffer]; void *
0x180007cfe  call    memset_0
0x180007d03  test    [rbx+4], bpl
0x180007d07  jz      short loc_180007D2C
0x180007d09  mov     ebp, [rbx+0Ch]
0x180007d0c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180007d13  test    rax, rax
0x180007d16  jz      short loc_180007D5C
0x180007d18  mov     r8d, 100h
0x180007d1e  lea     rdx, [rsp+278h+Buffer]
0x180007d23  mov     ecx, ebp
0x180007d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d2a  jmp     short loc_180007D5C
0x180007d2c  mov     ebp, [rbx+8]
0x180007d2f  mov     [rsp+278h+Arguments], r15; Arguments
0x180007d34  mov     [rsp+278h+nSize], 100h; nSize
0x180007d3c  lea     rax, [rsp+278h+Buffer]
0x180007d41  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007d46  mov     r9d, 400h; dwLanguageId
0x180007d4c  mov     r8d, ebp; dwMessageId
0x180007d4f  xor     edx, edx; lpSource
0x180007d51  mov     ecx, 1200h; dwFlags
0x180007d56  call    cs:__imp_FormatMessageW
0x180007d5c  lea     rsi, [r14+rsi*2]
0x180007d60  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007d64  mov     rax, [rbx+88h]
0x180007d6b  mov     rcx, [rbx+80h]
0x180007d72  mov     rdx, rsi; unsigned __int16 *
0x180007d75  test    r9, r9
0x180007d78  jz      short loc_180007D9C
0x180007d7a  mov     [rsp+278h+Arguments], rax
0x180007d7f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007d84  mov     eax, [rbx+40h]
0x180007d87  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007d8b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007d92  mov     rcx, r14; this
0x180007d95  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007d9a  jmp     short loc_180007DB3
0x180007d9c  mov     [rsp+278h+lpBuffer], rax
0x180007da1  mov     r9, rcx; unsigned __int16 *
0x180007da4  lea     r8, aHsP; "%hs!%p: "
0x180007dab  mov     rcx, r14; this
0x180007dae  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007db3  mov     r14, rax
0x180007db6  mov     r9, [rbx+90h]; unsigned __int16 *
0x180007dbd  test    r9, r9
0x180007dc0  jz      short loc_180007DD7
0x180007dc2  lea     r8, aCallerP; "(caller: %p) "
0x180007dc9  mov     rdx, rsi; unsigned __int16 *
0x180007dcc  mov     rcx, rax; this
0x180007dcf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007dd4  mov     r14, rax
0x180007dd7  call    cs:__imp_GetCurrentThreadId
0x180007ddd  lea     rcx, [rsp+278h+Buffer]
0x180007de2  mov     [rsp+278h+var_240], rcx
0x180007de7  mov     dword ptr [rsp+278h+Arguments], ebp
0x180007deb  mov     [rsp+278h+nSize], eax
0x180007def  mov     eax, [rbx+44h]
0x180007df2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180007df6  mov     r9, rdi; unsigned __int16 *
0x180007df9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180007e00  mov     rdx, rsi; unsigned __int16 *
0x180007e03  mov     rcx, r14; this
0x180007e06  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e0b  cmp     [rbx+18h], r15
0x180007e0f  jnz     short loc_180007E21
0x180007e11  cmp     [rbx+48h], r15
0x180007e15  jnz     short loc_180007E21
0x180007e17  cmp     [rbx+30h], r15
0x180007e1b  jz      loc_180007EB1
0x180007e21  lea     r8, asc_1800169F8; "    "
0x180007e28  mov     rdx, rsi; unsigned __int16 *
0x180007e2b  mov     rcx, rax; this
0x180007e2e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e33  mov     r9, [rbx+18h]; unsigned __int16 *
0x180007e37  test    r9, r9
0x180007e3a  jz      short loc_180007E4E
0x180007e3c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007e43  mov     rdx, rsi; unsigned __int16 *
0x180007e46  mov     rcx, rax; this
0x180007e49  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e4e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007e52  test    r9, r9
0x180007e55  jz      short loc_180007E69
0x180007e57  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007e5e  mov     rdx, rsi; unsigned __int16 *
0x180007e61  mov     rcx, rax; this
0x180007e64  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e69  mov     rcx, [rbx+28h]
0x180007e6d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007e71  mov     rdx, rsi; unsigned __int16 *
0x180007e74  test    rcx, rcx
0x180007e77  jz      short loc_180007E8F
0x180007e79  mov     [rsp+278h+lpBuffer], rcx
0x180007e7e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007e85  mov     rcx, rax; this
0x180007e88  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007e8d  jmp     short loc_180007EB1
0x180007e8f  mov     rcx, rax; this
0x180007e92  test    r9, r9
0x180007e95  jz      short loc_180007EA5
0x180007e97  lea     r8, aHs; "[%hs]\n"
0x180007e9e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007ea3  jmp     short loc_180007EB1
0x180007ea5  lea     r8, asc_180016A70; "\n"
0x180007eac  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007eb1  xor     eax, eax
0x180007eb3  mov     rcx, [rsp+278h+var_38]
0x180007ebb  xor     rcx, rsp; StackCookie
0x180007ebe  call    __security_check_cookie
0x180007ec3  mov     rbx, [rsp+278h+arg_18]
0x180007ecb  add     rsp, 250h
0x180007ed2  pop     r15
0x180007ed4  pop     r14
0x180007ed6  pop     rdi
0x180007ed7  pop     rsi
0x180007ed8  pop     rbp
0x180007ed9  retn
```
