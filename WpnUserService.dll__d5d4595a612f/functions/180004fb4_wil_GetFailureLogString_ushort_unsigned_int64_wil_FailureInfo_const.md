# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180004fb4`
- end: `0x18000526a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180003ae8`
- `0x180003d68`
- `0x1800059c4`
- `0x180007290`
- `0x180007b9c`
- `0x180010dbf`
- `0x180010ef3`

## callees

- `0x180002bc0`
- `0x18000354c`
- `0x180004fb4`
- `0x180005cc4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005167`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005167`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800050e6`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800050e6`

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
          v7 = (const char *)&byte_180013B63;
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
0x180004fb4  mov     [rsp+arg_18], rbx
0x180004fb9  push    rbp
0x180004fba  push    rsi
0x180004fbb  push    rdi
0x180004fbc  push    r14
0x180004fbe  push    r15
0x180004fc0  sub     rsp, 250h
0x180004fc7  mov     rax, cs:__security_cookie
0x180004fce  xor     rax, rsp
0x180004fd1  mov     [rsp+278h+var_38], rax
0x180004fd9  mov     rbx, r8
0x180004fdc  mov     rsi, rdx
0x180004fdf  mov     r14, rcx
0x180004fe2  xor     r15d, r15d
0x180004fe5  test    rdx, rdx
0x180004fe8  jz      loc_180005241
0x180004fee  test    rcx, rcx
0x180004ff1  jz      loc_180005241
0x180004ff7  mov     [rcx], r15w
0x180004ffb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005002  test    rax, rax
0x180005005  jz      short loc_180005028
0x180005007  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000500e  jz      short loc_180005028
0x180005010  mov     r8, rdx
0x180005013  mov     rdx, rcx
0x180005016  mov     rcx, rbx
0x180005019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501e  cmp     [r14], r15w
0x180005022  jnz     loc_180005241
0x180005028  mov     ecx, [rbx]
0x18000502a  mov     bpl, 8
0x18000502d  test    ecx, ecx
0x18000502f  jz      short loc_18000507A
0x180005031  sub     ecx, 1
0x180005034  jz      short loc_180005062
0x180005036  sub     ecx, 1
0x180005039  jz      short loc_180005052
0x18000503b  cmp     ecx, 1
0x18000503e  jz      short loc_180005049
0x180005040  lea     rdi, byte_180013B63
0x180005047  jmp     short loc_180005081
0x180005049  lea     rdi, aFailfast; "FailFast"
0x180005050  jmp     short loc_180005081
0x180005052  lea     rax, aLoghr; "LogHr"
0x180005059  lea     rdi, aLognt; "LogNt"
0x180005060  jmp     short loc_180005070
0x180005062  lea     rax, aReturnhr; "ReturnHr"
0x180005069  lea     rdi, aReturnnt; "ReturnNt"
0x180005070  test    [rbx+4], bpl
0x180005074  cmovz   rdi, rax
0x180005078  jmp     short loc_180005081
0x18000507a  lea     rdi, aException; "Exception"
0x180005081  xor     edx, edx; Val
0x180005083  mov     r8d, 200h; Size
0x180005089  lea     rcx, [rsp+278h+Buffer]; void *
0x18000508e  call    memset_0
0x180005093  test    [rbx+4], bpl
0x180005097  jz      short loc_1800050BC
0x180005099  mov     ebp, [rbx+0Ch]
0x18000509c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800050a3  test    rax, rax
0x1800050a6  jz      short loc_1800050EC
0x1800050a8  mov     r8d, 100h
0x1800050ae  lea     rdx, [rsp+278h+Buffer]
0x1800050b3  mov     ecx, ebp
0x1800050b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ba  jmp     short loc_1800050EC
0x1800050bc  mov     ebp, [rbx+8]
0x1800050bf  mov     [rsp+278h+Arguments], r15; Arguments
0x1800050c4  mov     [rsp+278h+nSize], 100h; nSize
0x1800050cc  lea     rax, [rsp+278h+Buffer]
0x1800050d1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800050d6  mov     r9d, 400h; dwLanguageId
0x1800050dc  mov     r8d, ebp; dwMessageId
0x1800050df  xor     edx, edx; lpSource
0x1800050e1  mov     ecx, 1200h; dwFlags
0x1800050e6  call    cs:__imp_FormatMessageW
0x1800050ec  lea     rsi, [r14+rsi*2]
0x1800050f0  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800050f4  mov     rax, [rbx+88h]
0x1800050fb  mov     rcx, [rbx+80h]
0x180005102  mov     rdx, rsi; unsigned __int16 *
0x180005105  test    r9, r9
0x180005108  jz      short loc_18000512C
0x18000510a  mov     [rsp+278h+Arguments], rax
0x18000510f  mov     qword ptr [rsp+278h+nSize], rcx
0x180005114  mov     eax, [rbx+40h]
0x180005117  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000511b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005122  mov     rcx, r14; this
0x180005125  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000512a  jmp     short loc_180005143
0x18000512c  mov     [rsp+278h+lpBuffer], rax
0x180005131  mov     r9, rcx; unsigned __int16 *
0x180005134  lea     r8, aHsP; "%hs!%p: "
0x18000513b  mov     rcx, r14; this
0x18000513e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005143  mov     r14, rax
0x180005146  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000514d  test    r9, r9
0x180005150  jz      short loc_180005167
0x180005152  lea     r8, aCallerP; "(caller: %p) "
0x180005159  mov     rdx, rsi; unsigned __int16 *
0x18000515c  mov     rcx, rax; this
0x18000515f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005164  mov     r14, rax
0x180005167  call    cs:__imp_GetCurrentThreadId
0x18000516d  lea     rcx, [rsp+278h+Buffer]
0x180005172  mov     [rsp+278h+var_240], rcx
0x180005177  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000517b  mov     [rsp+278h+nSize], eax
0x18000517f  mov     eax, [rbx+44h]
0x180005182  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005186  mov     r9, rdi; unsigned __int16 *
0x180005189  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180005190  mov     rdx, rsi; unsigned __int16 *
0x180005193  mov     rcx, r14; this
0x180005196  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000519b  cmp     [rbx+18h], r15
0x18000519f  jnz     short loc_1800051B1
0x1800051a1  cmp     [rbx+48h], r15
0x1800051a5  jnz     short loc_1800051B1
0x1800051a7  cmp     [rbx+30h], r15
0x1800051ab  jz      loc_180005241
0x1800051b1  lea     r8, asc_180013C68; "    "
0x1800051b8  mov     rdx, rsi; unsigned __int16 *
0x1800051bb  mov     rcx, rax; this
0x1800051be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051c3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800051c7  test    r9, r9
0x1800051ca  jz      short loc_1800051DE
0x1800051cc  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800051d3  mov     rdx, rsi; unsigned __int16 *
0x1800051d6  mov     rcx, rax; this
0x1800051d9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051de  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800051e2  test    r9, r9
0x1800051e5  jz      short loc_1800051F9
0x1800051e7  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800051ee  mov     rdx, rsi; unsigned __int16 *
0x1800051f1  mov     rcx, rax; this
0x1800051f4  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800051f9  mov     rcx, [rbx+28h]
0x1800051fd  mov     r9, [rbx+30h]; unsigned __int16 *
0x180005201  mov     rdx, rsi; unsigned __int16 *
0x180005204  test    rcx, rcx
0x180005207  jz      short loc_18000521F
0x180005209  mov     [rsp+278h+lpBuffer], rcx
0x18000520e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005215  mov     rcx, rax; this
0x180005218  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000521d  jmp     short loc_180005241
0x18000521f  mov     rcx, rax; this
0x180005222  test    r9, r9
0x180005225  jz      short loc_180005235
0x180005227  lea     r8, aHs; "[%hs]\n"
0x18000522e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005233  jmp     short loc_180005241
0x180005235  lea     r8, asc_180013CE0; "\n"
0x18000523c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005241  xor     eax, eax
0x180005243  mov     rcx, [rsp+278h+var_38]
0x18000524b  xor     rcx, rsp; StackCookie
0x18000524e  call    __security_check_cookie
0x180005253  mov     rbx, [rsp+278h+arg_18]
0x18000525b  add     rsp, 250h
0x180005262  pop     r15
0x180005264  pop     r14
0x180005266  pop     rdi
0x180005267  pop     rsi
0x180005268  pop     rbp
0x180005269  retn
```
