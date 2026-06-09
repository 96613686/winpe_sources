# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000fdf4`
- end: `0x1800100aa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x18000a620`
- `0x180012b50`

## callees

- `0x18000c5a0`
- `0x18000fdf4`
- `0x18001a342`
- `0x18001a380`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ffa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ffa7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ff26`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000ff26`

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
          v7 = (const char *)&dword_18001E424;
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
0x18000fdf4  mov     [rsp+arg_18], rbx
0x18000fdf9  push    rbp
0x18000fdfa  push    rsi
0x18000fdfb  push    rdi
0x18000fdfc  push    r14
0x18000fdfe  push    r15
0x18000fe00  sub     rsp, 250h
0x18000fe07  mov     rax, cs:__security_cookie
0x18000fe0e  xor     rax, rsp
0x18000fe11  mov     [rsp+278h+var_38], rax
0x18000fe19  mov     rbx, r8
0x18000fe1c  mov     rsi, rdx
0x18000fe1f  mov     r14, rcx
0x18000fe22  xor     r15d, r15d
0x18000fe25  test    rdx, rdx
0x18000fe28  jz      loc_180010081
0x18000fe2e  test    rcx, rcx
0x18000fe31  jz      loc_180010081
0x18000fe37  mov     [rcx], r15w
0x18000fe3b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000fe42  test    rax, rax
0x18000fe45  jz      short loc_18000FE68
0x18000fe47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000fe4e  jz      short loc_18000FE68
0x18000fe50  mov     r8, rdx
0x18000fe53  mov     rdx, rcx
0x18000fe56  mov     rcx, rbx
0x18000fe59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fe5e  cmp     [r14], r15w
0x18000fe62  jnz     loc_180010081
0x18000fe68  mov     ecx, [rbx]
0x18000fe6a  mov     bpl, 8
0x18000fe6d  test    ecx, ecx
0x18000fe6f  jz      short loc_18000FEBA
0x18000fe71  sub     ecx, 1
0x18000fe74  jz      short loc_18000FEA2
0x18000fe76  sub     ecx, 1
0x18000fe79  jz      short loc_18000FE92
0x18000fe7b  cmp     ecx, 1
0x18000fe7e  jz      short loc_18000FE89
0x18000fe80  lea     rdi, dword_18001E424
0x18000fe87  jmp     short loc_18000FEC1
0x18000fe89  lea     rdi, aFailfast; "FailFast"
0x18000fe90  jmp     short loc_18000FEC1
0x18000fe92  lea     rax, aLoghr; "LogHr"
0x18000fe99  lea     rdi, aLognt; "LogNt"
0x18000fea0  jmp     short loc_18000FEB0
0x18000fea2  lea     rax, aReturnhr; "ReturnHr"
0x18000fea9  lea     rdi, aReturnnt; "ReturnNt"
0x18000feb0  test    [rbx+4], bpl
0x18000feb4  cmovz   rdi, rax
0x18000feb8  jmp     short loc_18000FEC1
0x18000feba  lea     rdi, aException; "Exception"
0x18000fec1  xor     edx, edx; Val
0x18000fec3  mov     r8d, 200h; Size
0x18000fec9  lea     rcx, [rsp+278h+Buffer]; void *
0x18000fece  call    memset_0
0x18000fed3  test    [rbx+4], bpl
0x18000fed7  jz      short loc_18000FEFC
0x18000fed9  mov     ebp, [rbx+0Ch]
0x18000fedc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000fee3  test    rax, rax
0x18000fee6  jz      short loc_18000FF2C
0x18000fee8  mov     r8d, 100h
0x18000feee  lea     rdx, [rsp+278h+Buffer]
0x18000fef3  mov     ecx, ebp
0x18000fef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fefa  jmp     short loc_18000FF2C
0x18000fefc  mov     ebp, [rbx+8]
0x18000feff  mov     [rsp+278h+Arguments], r15; Arguments
0x18000ff04  mov     [rsp+278h+nSize], 100h; nSize
0x18000ff0c  lea     rax, [rsp+278h+Buffer]
0x18000ff11  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000ff16  mov     r9d, 400h; dwLanguageId
0x18000ff1c  mov     r8d, ebp; dwMessageId
0x18000ff1f  xor     edx, edx; lpSource
0x18000ff21  mov     ecx, 1200h; dwFlags
0x18000ff26  call    cs:__imp_FormatMessageW
0x18000ff2c  lea     rsi, [r14+rsi*2]
0x18000ff30  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000ff34  mov     rax, [rbx+88h]
0x18000ff3b  mov     rcx, [rbx+80h]
0x18000ff42  mov     rdx, rsi; unsigned __int16 *
0x18000ff45  test    r9, r9
0x18000ff48  jz      short loc_18000FF6C
0x18000ff4a  mov     [rsp+278h+Arguments], rax
0x18000ff4f  mov     qword ptr [rsp+278h+nSize], rcx
0x18000ff54  mov     eax, [rbx+40h]
0x18000ff57  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ff5b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000ff62  mov     rcx, r14; this
0x18000ff65  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ff6a  jmp     short loc_18000FF83
0x18000ff6c  mov     [rsp+278h+lpBuffer], rax
0x18000ff71  mov     r9, rcx; unsigned __int16 *
0x18000ff74  lea     r8, aHsP; "%hs!%p: "
0x18000ff7b  mov     rcx, r14; this
0x18000ff7e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ff83  mov     r14, rax
0x18000ff86  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000ff8d  test    r9, r9
0x18000ff90  jz      short loc_18000FFA7
0x18000ff92  lea     r8, aCallerP; "(caller: %p) "
0x18000ff99  mov     rdx, rsi; unsigned __int16 *
0x18000ff9c  mov     rcx, rax; this
0x18000ff9f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ffa4  mov     r14, rax
0x18000ffa7  call    cs:__imp_GetCurrentThreadId
0x18000ffad  lea     rcx, [rsp+278h+Buffer]
0x18000ffb2  mov     [rsp+278h+var_240], rcx
0x18000ffb7  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000ffbb  mov     [rsp+278h+nSize], eax
0x18000ffbf  mov     eax, [rbx+44h]
0x18000ffc2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000ffc6  mov     r9, rdi; unsigned __int16 *
0x18000ffc9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000ffd0  mov     rdx, rsi; unsigned __int16 *
0x18000ffd3  mov     rcx, r14; this
0x18000ffd6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000ffdb  cmp     [rbx+18h], r15
0x18000ffdf  jnz     short loc_18000FFF1
0x18000ffe1  cmp     [rbx+48h], r15
0x18000ffe5  jnz     short loc_18000FFF1
0x18000ffe7  cmp     [rbx+30h], r15
0x18000ffeb  jz      loc_180010081
0x18000fff1  lea     r8, asc_18001FA10; "    "
0x18000fff8  mov     rdx, rsi; unsigned __int16 *
0x18000fffb  mov     rcx, rax; this
0x18000fffe  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010003  mov     r9, [rbx+18h]; unsigned __int16 *
0x180010007  test    r9, r9
0x18001000a  jz      short loc_18001001E
0x18001000c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180010013  mov     rdx, rsi; unsigned __int16 *
0x180010016  mov     rcx, rax; this
0x180010019  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001001e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180010022  test    r9, r9
0x180010025  jz      short loc_180010039
0x180010027  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18001002e  mov     rdx, rsi; unsigned __int16 *
0x180010031  mov     rcx, rax; this
0x180010034  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010039  mov     rcx, [rbx+28h]
0x18001003d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180010041  mov     rdx, rsi; unsigned __int16 *
0x180010044  test    rcx, rcx
0x180010047  jz      short loc_18001005F
0x180010049  mov     [rsp+278h+lpBuffer], rcx
0x18001004e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180010055  mov     rcx, rax; this
0x180010058  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18001005d  jmp     short loc_180010081
0x18001005f  mov     rcx, rax; this
0x180010062  test    r9, r9
0x180010065  jz      short loc_180010075
0x180010067  lea     r8, aHs; "[%hs]\n"
0x18001006e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010073  jmp     short loc_180010081
0x180010075  lea     r8, asc_18001FA88; "\n"
0x18001007c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180010081  xor     eax, eax
0x180010083  mov     rcx, [rsp+278h+var_38]
0x18001008b  xor     rcx, rsp; StackCookie
0x18001008e  call    __security_check_cookie
0x180010093  mov     rbx, [rsp+278h+arg_18]
0x18001009b  add     rsp, 250h
0x1800100a2  pop     r15
0x1800100a4  pop     r14
0x1800100a6  pop     rdi
0x1800100a7  pop     rsi
0x1800100a8  pop     rbp
0x1800100a9  retn
```
