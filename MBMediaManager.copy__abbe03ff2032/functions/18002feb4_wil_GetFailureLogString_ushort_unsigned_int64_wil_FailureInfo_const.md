# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18002feb4`
- end: `0x18003016a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x18001cc94`
- `0x1800305a4`
- `0x180031250`

## callees

- `0x18002cd20`
- `0x18002d8c8`
- `0x18002feb4`
- `0x180030424`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030067`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180030067`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002ffe6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18002ffe6`

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
          v7 = (const char *)&qword_180060D60;
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
0x18002feb4  mov     [rsp+arg_18], rbx
0x18002feb9  push    rbp
0x18002feba  push    rsi
0x18002febb  push    rdi
0x18002febc  push    r14
0x18002febe  push    r15
0x18002fec0  sub     rsp, 250h
0x18002fec7  mov     rax, cs:__security_cookie
0x18002fece  xor     rax, rsp
0x18002fed1  mov     [rsp+278h+var_38], rax
0x18002fed9  mov     rbx, r8
0x18002fedc  mov     rsi, rdx
0x18002fedf  mov     r14, rcx
0x18002fee2  xor     r15d, r15d
0x18002fee5  test    rdx, rdx
0x18002fee8  jz      loc_180030141
0x18002feee  test    rcx, rcx
0x18002fef1  jz      loc_180030141
0x18002fef7  mov     [rcx], r15w
0x18002fefb  mov     rax, cs:g_pfnResultLoggingCallback
0x18002ff02  test    rax, rax
0x18002ff05  jz      short loc_18002FF28
0x18002ff07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18002ff0e  jz      short loc_18002FF28
0x18002ff10  mov     r8, rdx
0x18002ff13  mov     rdx, rcx
0x18002ff16  mov     rcx, rbx
0x18002ff19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ff1e  cmp     [r14], r15w
0x18002ff22  jnz     loc_180030141
0x18002ff28  mov     ecx, [rbx]
0x18002ff2a  mov     bpl, 8
0x18002ff2d  test    ecx, ecx
0x18002ff2f  jz      short loc_18002FF7A
0x18002ff31  sub     ecx, 1
0x18002ff34  jz      short loc_18002FF62
0x18002ff36  sub     ecx, 1
0x18002ff39  jz      short loc_18002FF52
0x18002ff3b  cmp     ecx, 1
0x18002ff3e  jz      short loc_18002FF49
0x18002ff40  lea     rdi, qword_180060D60
0x18002ff47  jmp     short loc_18002FF81
0x18002ff49  lea     rdi, aFailfast; "FailFast"
0x18002ff50  jmp     short loc_18002FF81
0x18002ff52  lea     rax, aLoghr; "LogHr"
0x18002ff59  lea     rdi, aLognt; "LogNt"
0x18002ff60  jmp     short loc_18002FF70
0x18002ff62  lea     rax, aReturnhr; "ReturnHr"
0x18002ff69  lea     rdi, aReturnnt; "ReturnNt"
0x18002ff70  test    [rbx+4], bpl
0x18002ff74  cmovz   rdi, rax
0x18002ff78  jmp     short loc_18002FF81
0x18002ff7a  lea     rdi, aException; "Exception"
0x18002ff81  xor     edx, edx; Val
0x18002ff83  mov     r8d, 200h; Size
0x18002ff89  lea     rcx, [rsp+278h+Buffer]; void *
0x18002ff8e  call    memset_0
0x18002ff93  test    [rbx+4], bpl
0x18002ff97  jz      short loc_18002FFBC
0x18002ff99  mov     ebp, [rbx+0Ch]
0x18002ff9c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18002ffa3  test    rax, rax
0x18002ffa6  jz      short loc_18002FFEC
0x18002ffa8  mov     r8d, 100h
0x18002ffae  lea     rdx, [rsp+278h+Buffer]
0x18002ffb3  mov     ecx, ebp
0x18002ffb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002ffba  jmp     short loc_18002FFEC
0x18002ffbc  mov     ebp, [rbx+8]
0x18002ffbf  mov     [rsp+278h+Arguments], r15; Arguments
0x18002ffc4  mov     [rsp+278h+nSize], 100h; nSize
0x18002ffcc  lea     rax, [rsp+278h+Buffer]
0x18002ffd1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18002ffd6  mov     r9d, 400h; dwLanguageId
0x18002ffdc  mov     r8d, ebp; dwMessageId
0x18002ffdf  xor     edx, edx; lpSource
0x18002ffe1  mov     ecx, 1200h; dwFlags
0x18002ffe6  call    cs:__imp_FormatMessageW
0x18002ffec  lea     rsi, [r14+rsi*2]
0x18002fff0  mov     r9, [rbx+38h]; unsigned __int16 *
0x18002fff4  mov     rax, [rbx+88h]
0x18002fffb  mov     rcx, [rbx+80h]
0x180030002  mov     rdx, rsi; unsigned __int16 *
0x180030005  test    r9, r9
0x180030008  jz      short loc_18003002C
0x18003000a  mov     [rsp+278h+Arguments], rax
0x18003000f  mov     qword ptr [rsp+278h+nSize], rcx
0x180030014  mov     eax, [rbx+40h]
0x180030017  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18003001b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180030022  mov     rcx, r14; this
0x180030025  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003002a  jmp     short loc_180030043
0x18003002c  mov     [rsp+278h+lpBuffer], rax
0x180030031  mov     r9, rcx; unsigned __int16 *
0x180030034  lea     r8, aHsP; "%hs!%p: "
0x18003003b  mov     rcx, r14; this
0x18003003e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030043  mov     r14, rax
0x180030046  mov     r9, [rbx+90h]; unsigned __int16 *
0x18003004d  test    r9, r9
0x180030050  jz      short loc_180030067
0x180030052  lea     r8, aCallerP; "(caller: %p) "
0x180030059  mov     rdx, rsi; unsigned __int16 *
0x18003005c  mov     rcx, rax; this
0x18003005f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030064  mov     r14, rax
0x180030067  call    cs:__imp_GetCurrentThreadId
0x18003006d  lea     rcx, [rsp+278h+Buffer]
0x180030072  mov     [rsp+278h+var_240], rcx
0x180030077  mov     dword ptr [rsp+278h+Arguments], ebp
0x18003007b  mov     [rsp+278h+nSize], eax
0x18003007f  mov     eax, [rbx+44h]
0x180030082  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180030086  mov     r9, rdi; unsigned __int16 *
0x180030089  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180030090  mov     rdx, rsi; unsigned __int16 *
0x180030093  mov     rcx, r14; this
0x180030096  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003009b  cmp     [rbx+18h], r15
0x18003009f  jnz     short loc_1800300B1
0x1800300a1  cmp     [rbx+48h], r15
0x1800300a5  jnz     short loc_1800300B1
0x1800300a7  cmp     [rbx+30h], r15
0x1800300ab  jz      loc_180030141
0x1800300b1  lea     r8, asc_180066A08; "    "
0x1800300b8  mov     rdx, rsi; unsigned __int16 *
0x1800300bb  mov     rcx, rax; this
0x1800300be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800300c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800300c7  test    r9, r9
0x1800300ca  jz      short loc_1800300DE
0x1800300cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800300d3  mov     rdx, rsi; unsigned __int16 *
0x1800300d6  mov     rcx, rax; this
0x1800300d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800300de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800300e2  test    r9, r9
0x1800300e5  jz      short loc_1800300F9
0x1800300e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800300ee  mov     rdx, rsi; unsigned __int16 *
0x1800300f1  mov     rcx, rax; this
0x1800300f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800300f9  mov     rcx, [rbx+28h]
0x1800300fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180030101  mov     rdx, rsi; unsigned __int16 *
0x180030104  test    rcx, rcx
0x180030107  jz      short loc_18003011F
0x180030109  mov     [rsp+278h+lpBuffer], rcx
0x18003010e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180030115  mov     rcx, rax; this
0x180030118  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18003011d  jmp     short loc_180030141
0x18003011f  mov     rcx, rax; this
0x180030122  test    r9, r9
0x180030125  jz      short loc_180030135
0x180030127  lea     r8, aHs; "[%hs]\n"
0x18003012e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030133  jmp     short loc_180030141
0x180030135  lea     r8, asc_180066A80; "\n"
0x18003013c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180030141  xor     eax, eax
0x180030143  mov     rcx, [rsp+278h+var_38]
0x18003014b  xor     rcx, rsp; StackCookie
0x18003014e  call    __security_check_cookie
0x180030153  mov     rbx, [rsp+278h+arg_18]
0x18003015b  add     rsp, 250h
0x180030162  pop     r15
0x180030164  pop     r14
0x180030166  pop     rdi
0x180030167  pop     rsi
0x180030168  pop     rbp
0x180030169  retn
```
