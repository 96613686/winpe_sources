# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005d20`
- end: `0x140005fd6`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000581c`
- `0x140006388`
- `0x140006c28`
- `0x14000bc80`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x140005d20`
- `0x140006688`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140005ed3`
- `KERNEL32!GetCurrentThreadId` at `0x140005ed3`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005e52`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005e52`

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
          v7 = (const char *)&word_140013232;
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
0x140005d20  mov     [rsp+arg_18], rbx
0x140005d25  push    rbp
0x140005d26  push    rsi
0x140005d27  push    rdi
0x140005d28  push    r14
0x140005d2a  push    r15
0x140005d2c  sub     rsp, 250h
0x140005d33  mov     rax, cs:__security_cookie
0x140005d3a  xor     rax, rsp
0x140005d3d  mov     [rsp+278h+var_38], rax
0x140005d45  mov     rbx, r8
0x140005d48  mov     rsi, rdx
0x140005d4b  mov     r14, rcx
0x140005d4e  xor     r15d, r15d
0x140005d51  test    rdx, rdx
0x140005d54  jz      loc_140005FAD
0x140005d5a  test    rcx, rcx
0x140005d5d  jz      loc_140005FAD
0x140005d63  mov     [rcx], r15w
0x140005d67  mov     rax, cs:g_pfnResultLoggingCallback
0x140005d6e  test    rax, rax
0x140005d71  jz      short loc_140005D94
0x140005d73  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005d7a  jz      short loc_140005D94
0x140005d7c  mov     r8, rdx
0x140005d7f  mov     rdx, rcx
0x140005d82  mov     rcx, rbx
0x140005d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005d8a  cmp     [r14], r15w
0x140005d8e  jnz     loc_140005FAD
0x140005d94  mov     ecx, [rbx]
0x140005d96  mov     bpl, 8
0x140005d99  test    ecx, ecx
0x140005d9b  jz      short loc_140005DE6
0x140005d9d  sub     ecx, 1
0x140005da0  jz      short loc_140005DCE
0x140005da2  sub     ecx, 1
0x140005da5  jz      short loc_140005DBE
0x140005da7  cmp     ecx, 1
0x140005daa  jz      short loc_140005DB5
0x140005dac  lea     rdi, word_140013232
0x140005db3  jmp     short loc_140005DED
0x140005db5  lea     rdi, aFailfast; "FailFast"
0x140005dbc  jmp     short loc_140005DED
0x140005dbe  lea     rax, aLoghr; "LogHr"
0x140005dc5  lea     rdi, aLognt; "LogNt"
0x140005dcc  jmp     short loc_140005DDC
0x140005dce  lea     rax, aReturnhr; "ReturnHr"
0x140005dd5  lea     rdi, aReturnnt; "ReturnNt"
0x140005ddc  test    [rbx+4], bpl
0x140005de0  cmovz   rdi, rax
0x140005de4  jmp     short loc_140005DED
0x140005de6  lea     rdi, aException; "Exception"
0x140005ded  xor     edx, edx; Val
0x140005def  mov     r8d, 200h; Size
0x140005df5  lea     rcx, [rsp+278h+Buffer]; void *
0x140005dfa  call    memset_0
0x140005dff  test    [rbx+4], bpl
0x140005e03  jz      short loc_140005E28
0x140005e05  mov     ebp, [rbx+0Ch]
0x140005e08  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x140005e0f  test    rax, rax
0x140005e12  jz      short loc_140005E58
0x140005e14  mov     r8d, 100h
0x140005e1a  lea     rdx, [rsp+278h+Buffer]
0x140005e1f  mov     ecx, ebp
0x140005e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e26  jmp     short loc_140005E58
0x140005e28  mov     ebp, [rbx+8]
0x140005e2b  mov     [rsp+278h+Arguments], r15; Arguments
0x140005e30  mov     [rsp+278h+nSize], 100h; nSize
0x140005e38  lea     rax, [rsp+278h+Buffer]
0x140005e3d  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140005e42  mov     r9d, 400h; dwLanguageId
0x140005e48  mov     r8d, ebp; dwMessageId
0x140005e4b  xor     edx, edx; lpSource
0x140005e4d  mov     ecx, 1200h; dwFlags
0x140005e52  call    cs:__imp_FormatMessageW
0x140005e58  lea     rsi, [r14+rsi*2]
0x140005e5c  mov     r9, [rbx+38h]; unsigned __int16 *
0x140005e60  mov     rax, [rbx+88h]
0x140005e67  mov     rcx, [rbx+80h]
0x140005e6e  mov     rdx, rsi; unsigned __int16 *
0x140005e71  test    r9, r9
0x140005e74  jz      short loc_140005E98
0x140005e76  mov     [rsp+278h+Arguments], rax
0x140005e7b  mov     qword ptr [rsp+278h+nSize], rcx
0x140005e80  mov     eax, [rbx+40h]
0x140005e83  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005e87  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140005e8e  mov     rcx, r14; this
0x140005e91  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005e96  jmp     short loc_140005EAF
0x140005e98  mov     [rsp+278h+lpBuffer], rax
0x140005e9d  mov     r9, rcx; unsigned __int16 *
0x140005ea0  lea     r8, aHsP; "%hs!%p: "
0x140005ea7  mov     rcx, r14; this
0x140005eaa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005eaf  mov     r14, rax
0x140005eb2  mov     r9, [rbx+90h]; unsigned __int16 *
0x140005eb9  test    r9, r9
0x140005ebc  jz      short loc_140005ED3
0x140005ebe  lea     r8, aCallerP; "(caller: %p) "
0x140005ec5  mov     rdx, rsi; unsigned __int16 *
0x140005ec8  mov     rcx, rax; this
0x140005ecb  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005ed0  mov     r14, rax
0x140005ed3  call    cs:__imp_GetCurrentThreadId
0x140005ed9  lea     rcx, [rsp+278h+Buffer]
0x140005ede  mov     [rsp+278h+var_240], rcx
0x140005ee3  mov     dword ptr [rsp+278h+Arguments], ebp
0x140005ee7  mov     [rsp+278h+nSize], eax
0x140005eeb  mov     eax, [rbx+44h]
0x140005eee  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140005ef2  mov     r9, rdi; unsigned __int16 *
0x140005ef5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140005efc  mov     rdx, rsi; unsigned __int16 *
0x140005eff  mov     rcx, r14; this
0x140005f02  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005f07  cmp     [rbx+18h], r15
0x140005f0b  jnz     short loc_140005F1D
0x140005f0d  cmp     [rbx+48h], r15
0x140005f11  jnz     short loc_140005F1D
0x140005f13  cmp     [rbx+30h], r15
0x140005f17  jz      loc_140005FAD
0x140005f1d  lea     r8, asc_140013320; "    "
0x140005f24  mov     rdx, rsi; unsigned __int16 *
0x140005f27  mov     rcx, rax; this
0x140005f2a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005f2f  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005f33  test    r9, r9
0x140005f36  jz      short loc_140005F4A
0x140005f38  lea     r8, aMsgWs; "Msg:[%ws] "
0x140005f3f  mov     rdx, rsi; unsigned __int16 *
0x140005f42  mov     rcx, rax; this
0x140005f45  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005f4a  mov     r9, [rbx+48h]; unsigned __int16 *
0x140005f4e  test    r9, r9
0x140005f51  jz      short loc_140005F65
0x140005f53  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140005f5a  mov     rdx, rsi; unsigned __int16 *
0x140005f5d  mov     rcx, rax; this
0x140005f60  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005f65  mov     rcx, [rbx+28h]
0x140005f69  mov     r9, [rbx+30h]; unsigned __int16 *
0x140005f6d  mov     rdx, rsi; unsigned __int16 *
0x140005f70  test    rcx, rcx
0x140005f73  jz      short loc_140005F8B
0x140005f75  mov     [rsp+278h+lpBuffer], rcx
0x140005f7a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005f81  mov     rcx, rax; this
0x140005f84  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005f89  jmp     short loc_140005FAD
0x140005f8b  mov     rcx, rax; this
0x140005f8e  test    r9, r9
0x140005f91  jz      short loc_140005FA1
0x140005f93  lea     r8, aHs; "[%hs]\n"
0x140005f9a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005f9f  jmp     short loc_140005FAD
0x140005fa1  lea     r8, asc_140013398; "\n"
0x140005fa8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005fad  xor     eax, eax
0x140005faf  mov     rcx, [rsp+278h+var_38]
0x140005fb7  xor     rcx, rsp; StackCookie
0x140005fba  call    __security_check_cookie
0x140005fbf  mov     rbx, [rsp+278h+arg_18]
0x140005fc7  add     rsp, 250h
0x140005fce  pop     r15
0x140005fd0  pop     r14
0x140005fd2  pop     rdi
0x140005fd3  pop     rsi
0x140005fd4  pop     rbp
0x140005fd5  retn
```
