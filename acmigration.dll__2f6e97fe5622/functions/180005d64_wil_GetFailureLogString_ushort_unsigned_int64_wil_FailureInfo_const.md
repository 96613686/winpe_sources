# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005d64`
- end: `0x180006025`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `8`
- callee_count: `5`
- tags: ``

## callers

- `0x180003604`
- `0x180003890`
- `0x1800067d0`
- `0x18000a130`
- `0x1800653dd`
- `0x1800654f3`
- `0x18006563e`
- `0x180065a34`

## callees

- `0x180001cf0`
- `0x180002874`
- `0x180005d64`
- `0x180006ad8`
- `0x18006a010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180005ea1`
- `KERNEL32!FormatMessageW` at `0x180005ea1`
- `KERNEL32!GetCurrentThreadId` at `0x180005f22`
- `KERNEL32!GetCurrentThreadId` at `0x180005f22`

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
  LPWSTR lpBuffer; // [rsp+20h] [rbp-268h]
  LPWSTR lpBuffera; // [rsp+20h] [rbp-268h]
  DWORD nSize[2]; // [rsp+28h] [rbp-260h]
  va_list *Arguments; // [rsp+30h] [rbp-258h]
  WCHAR Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( !a2 )
    return 0;
  if ( !this )
    return 0;
  *(_WORD *)this = 0;
  if ( g_pfnResultLoggingCallback )
  {
    if ( wil::details::g_resultMessageCallbackSet )
    {
      g_pfnResultLoggingCallback(a3, this, a2, a4);
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
          v7 = word_18006E07E;
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
                          Buffer,
                          -2);
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
0x180005d64  mov     rax, rsp
0x180005d67  push    rbp
0x180005d68  push    rsi
0x180005d69  push    rdi
0x180005d6a  push    r14
0x180005d6c  push    r15
0x180005d6e  sub     rsp, 260h
0x180005d75  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180005d7e  mov     [rax+20h], rbx
0x180005d82  mov     rax, cs:__security_cookie
0x180005d89  xor     rax, rsp
0x180005d8c  mov     [rsp+288h+var_38], rax
0x180005d94  mov     rbx, r8
0x180005d97  mov     rsi, rdx
0x180005d9a  mov     r14, rcx
0x180005d9d  xor     r15d, r15d
0x180005da0  test    rdx, rdx
0x180005da3  jz      loc_180005FFC
0x180005da9  test    rcx, rcx
0x180005dac  jz      loc_180005FFC
0x180005db2  mov     [rcx], r15w
0x180005db6  mov     rax, cs:g_pfnResultLoggingCallback
0x180005dbd  test    rax, rax
0x180005dc0  jz      short loc_180005DE3
0x180005dc2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005dc9  jz      short loc_180005DE3
0x180005dcb  mov     r8, rdx
0x180005dce  mov     rdx, rcx
0x180005dd1  mov     rcx, rbx
0x180005dd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd9  cmp     [r14], r15w
0x180005ddd  jnz     loc_180005FFC
0x180005de3  mov     ecx, [rbx]
0x180005de5  mov     bpl, 8
0x180005de8  test    ecx, ecx
0x180005dea  jz      short loc_180005E35
0x180005dec  sub     ecx, 1
0x180005def  jz      short loc_180005E1D
0x180005df1  sub     ecx, 1
0x180005df4  jz      short loc_180005E0D
0x180005df6  cmp     ecx, 1
0x180005df9  jz      short loc_180005E04
0x180005dfb  lea     rdi, word_18006E07E
0x180005e02  jmp     short loc_180005E3C
0x180005e04  lea     rdi, aFailfast; "FailFast"
0x180005e0b  jmp     short loc_180005E3C
0x180005e0d  lea     rax, aLoghr; "LogHr"
0x180005e14  lea     rdi, aLognt; "LogNt"
0x180005e1b  jmp     short loc_180005E2B
0x180005e1d  lea     rax, aReturnhr; "ReturnHr"
0x180005e24  lea     rdi, aReturnnt; "ReturnNt"
0x180005e2b  test    [rbx+4], bpl
0x180005e2f  cmovz   rdi, rax
0x180005e33  jmp     short loc_180005E3C
0x180005e35  lea     rdi, aException; "Exception"
0x180005e3c  xor     edx, edx; Val
0x180005e3e  mov     r8d, 200h; Size
0x180005e44  lea     rcx, [rsp+288h+Buffer]; void *
0x180005e49  call    memset_0
0x180005e4e  test    [rbx+4], bpl
0x180005e52  jz      short loc_180005E77
0x180005e54  mov     ebp, [rbx+0Ch]
0x180005e57  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005e5e  test    rax, rax
0x180005e61  jz      short loc_180005EA7
0x180005e63  mov     r8d, 100h
0x180005e69  lea     rdx, [rsp+288h+Buffer]
0x180005e6e  mov     ecx, ebp
0x180005e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e75  jmp     short loc_180005EA7
0x180005e77  mov     ebp, [rbx+8]
0x180005e7a  mov     [rsp+288h+Arguments], r15; Arguments
0x180005e7f  mov     [rsp+288h+nSize], 100h; nSize
0x180005e87  lea     rax, [rsp+288h+Buffer]
0x180005e8c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180005e91  mov     r9d, 400h; dwLanguageId
0x180005e97  mov     r8d, ebp; dwMessageId
0x180005e9a  xor     edx, edx; lpSource
0x180005e9c  mov     ecx, 1200h; dwFlags
0x180005ea1  call    cs:__imp_FormatMessageW
0x180005ea7  lea     rsi, [r14+rsi*2]
0x180005eab  mov     r9, [rbx+38h]; unsigned __int16 *
0x180005eaf  mov     rax, [rbx+88h]
0x180005eb6  mov     rcx, [rbx+80h]
0x180005ebd  mov     rdx, rsi; unsigned __int16 *
0x180005ec0  test    r9, r9
0x180005ec3  jz      short loc_180005EE7
0x180005ec5  mov     [rsp+288h+Arguments], rax
0x180005eca  mov     qword ptr [rsp+288h+nSize], rcx
0x180005ecf  mov     eax, [rbx+40h]
0x180005ed2  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180005ed6  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005edd  mov     rcx, r14; this
0x180005ee0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ee5  jmp     short loc_180005EFE
0x180005ee7  mov     [rsp+288h+lpBuffer], rax
0x180005eec  mov     r9, rcx; unsigned __int16 *
0x180005eef  lea     r8, aHsP; "%hs!%p: "
0x180005ef6  mov     rcx, r14; this
0x180005ef9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005efe  mov     r14, rax
0x180005f01  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005f08  test    r9, r9
0x180005f0b  jz      short loc_180005F22
0x180005f0d  lea     r8, aCallerP; "(caller: %p) "
0x180005f14  mov     rdx, rsi; unsigned __int16 *
0x180005f17  mov     rcx, rax; this
0x180005f1a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f1f  mov     r14, rax
0x180005f22  call    cs:__imp_GetCurrentThreadId
0x180005f28  lea     rcx, [rsp+288h+Buffer]
0x180005f2d  mov     [rsp+288h+var_250], rcx
0x180005f32  mov     dword ptr [rsp+288h+Arguments], ebp
0x180005f36  mov     [rsp+288h+nSize], eax
0x180005f3a  mov     eax, [rbx+44h]
0x180005f3d  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180005f41  mov     r9, rdi; unsigned __int16 *
0x180005f44  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005f4b  mov     rdx, rsi; unsigned __int16 *
0x180005f4e  mov     rcx, r14; this
0x180005f51  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f56  cmp     [rbx+18h], r15
0x180005f5a  jnz     short loc_180005F6C
0x180005f5c  cmp     [rbx+48h], r15
0x180005f60  jnz     short loc_180005F6C
0x180005f62  cmp     [rbx+30h], r15
0x180005f66  jz      loc_180005FFC
0x180005f6c  lea     r8, asc_18006E1B0; "    "
0x180005f73  mov     rdx, rsi; unsigned __int16 *
0x180005f76  mov     rcx, rax; this
0x180005f79  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f7e  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005f82  test    r9, r9
0x180005f85  jz      short loc_180005F99
0x180005f87  lea     r8, aMsgWs; "Msg:[%ws] "
0x180005f8e  mov     rdx, rsi; unsigned __int16 *
0x180005f91  mov     rcx, rax; this
0x180005f94  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005f99  mov     r9, [rbx+48h]; unsigned __int16 *
0x180005f9d  test    r9, r9
0x180005fa0  jz      short loc_180005FB4
0x180005fa2  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180005fa9  mov     rdx, rsi; unsigned __int16 *
0x180005fac  mov     rcx, rax; this
0x180005faf  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fb4  mov     rcx, [rbx+28h]
0x180005fb8  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005fbc  mov     rdx, rsi; unsigned __int16 *
0x180005fbf  test    rcx, rcx
0x180005fc2  jz      short loc_180005FDA
0x180005fc4  mov     [rsp+288h+lpBuffer], rcx
0x180005fc9  lea     r8, aHsHs_0; "[%hs(%hs)]\n"
0x180005fd0  mov     rcx, rax; this
0x180005fd3  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fd8  jmp     short loc_180005FFC
0x180005fda  mov     rcx, rax; this
0x180005fdd  test    r9, r9
0x180005fe0  jz      short loc_180005FF0
0x180005fe2  lea     r8, aHs_0; "[%hs]\n"
0x180005fe9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005fee  jmp     short loc_180005FFC
0x180005ff0  lea     r8, asc_18006E228; "\n"
0x180005ff7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005ffc  xor     eax, eax
0x180005ffe  mov     rcx, [rsp+288h+var_38]
0x180006006  xor     rcx, rsp; StackCookie
0x180006009  call    __security_check_cookie
0x18000600e  mov     rbx, [rsp+288h+arg_18]
0x180006016  add     rsp, 260h
0x18000601d  pop     r15
0x18000601f  pop     r14
0x180006021  pop     rdi
0x180006022  pop     rsi
0x180006023  pop     rbp
0x180006024  retn
```
