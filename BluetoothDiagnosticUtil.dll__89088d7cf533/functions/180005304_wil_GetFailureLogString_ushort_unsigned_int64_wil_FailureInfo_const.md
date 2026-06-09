# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005304`
- end: `0x1800055c7`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002208`
- `0x18000249c`
- `0x180002768`
- `0x180005ee8`
- `0x180008670`
- `0x18000a33b`
- `0x18000a46f`

## callees

- `0x180005304`
- `0x1800061fc`
- `0x180009c5e`
- `0x180009c90`
- `0x18000b010`

## import_xrefs

- `KERNEL32!FormatMessageW` at `0x180005436`
- `KERNEL32!FormatMessageW` at `0x180005436`
- `KERNEL32!GetCurrentThreadId` at `0x1800054bd`
- `KERNEL32!GetCurrentThreadId` at `0x1800054bd`

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
          v7 = (const char *)&byte_18000D1E0;
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
0x180005304  mov     [rsp+arg_18], rbx
0x180005309  push    rbp
0x18000530a  push    rsi
0x18000530b  push    rdi
0x18000530c  push    r14
0x18000530e  push    r15
0x180005310  sub     rsp, 250h
0x180005317  mov     rax, cs:__security_cookie
0x18000531e  xor     rax, rsp
0x180005321  mov     [rsp+278h+var_38], rax
0x180005329  mov     rbx, r8
0x18000532c  mov     rsi, rdx
0x18000532f  mov     r14, rcx
0x180005332  xor     r15d, r15d
0x180005335  test    rdx, rdx
0x180005338  jz      loc_18000559D
0x18000533e  test    rcx, rcx
0x180005341  jz      loc_18000559D
0x180005347  mov     [rcx], r15w
0x18000534b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005352  test    rax, rax
0x180005355  jz      short loc_180005378
0x180005357  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000535e  jz      short loc_180005378
0x180005360  mov     r8, rdx
0x180005363  mov     rdx, rcx
0x180005366  mov     rcx, rbx
0x180005369  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000536e  cmp     [r14], r15w
0x180005372  jnz     loc_18000559D
0x180005378  mov     ecx, [rbx]
0x18000537a  mov     bpl, 8
0x18000537d  test    ecx, ecx
0x18000537f  jz      short loc_1800053CA
0x180005381  sub     ecx, 1
0x180005384  jz      short loc_1800053B2
0x180005386  sub     ecx, 1
0x180005389  jz      short loc_1800053A2
0x18000538b  cmp     ecx, 1
0x18000538e  jz      short loc_180005399
0x180005390  lea     rdi, byte_18000D1E0
0x180005397  jmp     short loc_1800053D1
0x180005399  lea     rdi, aFailfast; "FailFast"
0x1800053a0  jmp     short loc_1800053D1
0x1800053a2  lea     rax, aLoghr; "LogHr"
0x1800053a9  lea     rdi, aLognt; "LogNt"
0x1800053b0  jmp     short loc_1800053C0
0x1800053b2  lea     rax, aReturnhr; "ReturnHr"
0x1800053b9  lea     rdi, aReturnnt; "ReturnNt"
0x1800053c0  test    [rbx+4], bpl
0x1800053c4  cmovz   rdi, rax
0x1800053c8  jmp     short loc_1800053D1
0x1800053ca  lea     rdi, aException; "Exception"
0x1800053d1  xor     edx, edx; Val
0x1800053d3  mov     r8d, 200h; Size
0x1800053d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800053de  call    memset_0
0x1800053e3  test    [rbx+4], bpl
0x1800053e7  jz      short loc_18000540C
0x1800053e9  mov     ebp, [rbx+0Ch]
0x1800053ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800053f3  test    rax, rax
0x1800053f6  jz      short loc_180005442
0x1800053f8  mov     r8d, 100h
0x1800053fe  lea     rdx, [rsp+278h+Buffer]
0x180005403  mov     ecx, ebp
0x180005405  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000540a  jmp     short loc_180005442
0x18000540c  mov     ebp, [rbx+8]
0x18000540f  mov     [rsp+278h+Arguments], r15; Arguments
0x180005414  mov     [rsp+278h+nSize], 100h; nSize
0x18000541c  lea     rax, [rsp+278h+Buffer]
0x180005421  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180005426  mov     r9d, 400h; dwLanguageId
0x18000542c  mov     r8d, ebp; dwMessageId
0x18000542f  xor     edx, edx; lpSource
0x180005431  mov     ecx, 1200h; dwFlags
0x180005436  call    cs:__imp_FormatMessageW
0x18000543d  nop     dword ptr [rax+rax+00h]
0x180005442  lea     rsi, [r14+rsi*2]
0x180005446  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000544a  mov     rax, [rbx+88h]
0x180005451  mov     rcx, [rbx+80h]
0x180005458  mov     rdx, rsi; unsigned __int16 *
0x18000545b  test    r9, r9
0x18000545e  jz      short loc_180005482
0x180005460  mov     [rsp+278h+Arguments], rax
0x180005465  mov     qword ptr [rsp+278h+nSize], rcx
0x18000546a  mov     eax, [rbx+40h]
0x18000546d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005471  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005478  mov     rcx, r14; this
0x18000547b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005480  jmp     short loc_180005499
0x180005482  mov     [rsp+278h+lpBuffer], rax
0x180005487  mov     r9, rcx; unsigned __int16 *
0x18000548a  lea     r8, aHsP; "%hs!%p: "
0x180005491  mov     rcx, r14; this
0x180005494  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005499  mov     r14, rax
0x18000549c  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800054a3  test    r9, r9
0x1800054a6  jz      short loc_1800054BD
0x1800054a8  lea     r8, aCallerP; "(caller: %p) "
0x1800054af  mov     rdx, rsi; unsigned __int16 *
0x1800054b2  mov     rcx, rax; this
0x1800054b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054ba  mov     r14, rax
0x1800054bd  call    cs:__imp_GetCurrentThreadId
0x1800054c4  nop     dword ptr [rax+rax+00h]
0x1800054c9  lea     rcx, [rsp+278h+Buffer]
0x1800054ce  mov     [rsp+278h+var_240], rcx
0x1800054d3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800054d7  mov     [rsp+278h+nSize], eax
0x1800054db  mov     eax, [rbx+44h]
0x1800054de  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800054e2  mov     r9, rdi; unsigned __int16 *
0x1800054e5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800054ec  mov     rdx, rsi; unsigned __int16 *
0x1800054ef  mov     rcx, r14; this
0x1800054f2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054f7  cmp     [rbx+18h], r15
0x1800054fb  jnz     short loc_18000550D
0x1800054fd  cmp     [rbx+48h], r15
0x180005501  jnz     short loc_18000550D
0x180005503  cmp     [rbx+30h], r15
0x180005507  jz      loc_18000559D
0x18000550d  lea     r8, asc_18000CD58; "    "
0x180005514  mov     rdx, rsi; unsigned __int16 *
0x180005517  mov     rcx, rax; this
0x18000551a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000551f  mov     r9, [rbx+18h]; unsigned __int16 *
0x180005523  test    r9, r9
0x180005526  jz      short loc_18000553A
0x180005528  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000552f  mov     rdx, rsi; unsigned __int16 *
0x180005532  mov     rcx, rax; this
0x180005535  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000553a  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000553e  test    r9, r9
0x180005541  jz      short loc_180005555
0x180005543  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000554a  mov     rdx, rsi; unsigned __int16 *
0x18000554d  mov     rcx, rax; this
0x180005550  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005555  mov     rcx, [rbx+28h]
0x180005559  mov     r9, [rbx+30h]; unsigned __int16 *
0x18000555d  mov     rdx, rsi; unsigned __int16 *
0x180005560  test    rcx, rcx
0x180005563  jz      short loc_18000557B
0x180005565  mov     [rsp+278h+lpBuffer], rcx
0x18000556a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005571  mov     rcx, rax; this
0x180005574  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005579  jmp     short loc_18000559D
0x18000557b  mov     rcx, rax; this
0x18000557e  test    r9, r9
0x180005581  jz      short loc_180005591
0x180005583  lea     r8, aHs; "[%hs]\n"
0x18000558a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000558f  jmp     short loc_18000559D
0x180005591  lea     r8, asc_18000CDD0; "\n"
0x180005598  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000559d  xor     eax, eax
0x18000559f  mov     rcx, [rsp+278h+var_38]
0x1800055a7  xor     rcx, rsp; StackCookie
0x1800055aa  call    __security_check_cookie
0x1800055af  mov     rbx, [rsp+278h+arg_18]
0x1800055b7  add     rsp, 250h
0x1800055be  pop     r15
0x1800055c0  pop     r14
0x1800055c2  pop     rdi
0x1800055c3  pop     rsi
0x1800055c4  pop     rbp
0x1800055c5  retn
```
