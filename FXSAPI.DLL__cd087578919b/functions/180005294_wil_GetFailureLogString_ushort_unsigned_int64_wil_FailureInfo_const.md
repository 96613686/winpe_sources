# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180005294`
- end: `0x180005557`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800024bc`
- `0x180002738`
- `0x180005c64`
- `0x1800098a0`

## callees

- `0x180005294`
- `0x180005f78`
- `0x18003d4ca`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x18000544d`
- `KERNEL32!GetCurrentThreadId` at `0x18000544d`
- `KERNEL32!FormatMessageW` at `0x1800053c6`
- `KERNEL32!FormatMessageW` at `0x1800053c6`

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
          v7 = (const char *)&qword_1800434C0;
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
0x180005294  mov     [rsp+arg_18], rbx
0x180005299  push    rbp
0x18000529a  push    rsi
0x18000529b  push    rdi
0x18000529c  push    r14
0x18000529e  push    r15
0x1800052a0  sub     rsp, 250h
0x1800052a7  mov     rax, cs:__security_cookie
0x1800052ae  xor     rax, rsp
0x1800052b1  mov     [rsp+278h+var_38], rax
0x1800052b9  mov     rbx, r8
0x1800052bc  mov     rsi, rdx
0x1800052bf  mov     r14, rcx
0x1800052c2  xor     r15d, r15d
0x1800052c5  test    rdx, rdx
0x1800052c8  jz      loc_18000552D
0x1800052ce  test    rcx, rcx
0x1800052d1  jz      loc_18000552D
0x1800052d7  mov     [rcx], r15w
0x1800052db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052e2  test    rax, rax
0x1800052e5  jz      short loc_180005308
0x1800052e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800052ee  jz      short loc_180005308
0x1800052f0  mov     r8, rdx
0x1800052f3  mov     rdx, rcx
0x1800052f6  mov     rcx, rbx
0x1800052f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052fe  cmp     [r14], r15w
0x180005302  jnz     loc_18000552D
0x180005308  mov     ecx, [rbx]
0x18000530a  mov     bpl, 8
0x18000530d  test    ecx, ecx
0x18000530f  jz      short loc_18000535A
0x180005311  sub     ecx, 1
0x180005314  jz      short loc_180005342
0x180005316  sub     ecx, 1
0x180005319  jz      short loc_180005332
0x18000531b  cmp     ecx, 1
0x18000531e  jz      short loc_180005329
0x180005320  lea     rdi, qword_1800434C0
0x180005327  jmp     short loc_180005361
0x180005329  lea     rdi, aFailfast; "FailFast"
0x180005330  jmp     short loc_180005361
0x180005332  lea     rax, aLoghr; "LogHr"
0x180005339  lea     rdi, aLognt; "LogNt"
0x180005340  jmp     short loc_180005350
0x180005342  lea     rax, aReturnhr; "ReturnHr"
0x180005349  lea     rdi, aReturnnt; "ReturnNt"
0x180005350  test    [rbx+4], bpl
0x180005354  cmovz   rdi, rax
0x180005358  jmp     short loc_180005361
0x18000535a  lea     rdi, aException; "Exception"
0x180005361  xor     edx, edx; Val
0x180005363  mov     r8d, 200h; Size
0x180005369  lea     rcx, [rsp+278h+Buffer]; void *
0x18000536e  call    memset_0
0x180005373  test    [rbx+4], bpl
0x180005377  jz      short loc_18000539C
0x180005379  mov     ebp, [rbx+0Ch]
0x18000537c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180005383  test    rax, rax
0x180005386  jz      short loc_1800053D2
0x180005388  mov     r8d, 100h
0x18000538e  lea     rdx, [rsp+278h+Buffer]
0x180005393  mov     ecx, ebp
0x180005395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000539a  jmp     short loc_1800053D2
0x18000539c  mov     ebp, [rbx+8]
0x18000539f  mov     [rsp+278h+Arguments], r15; Arguments
0x1800053a4  mov     [rsp+278h+nSize], 100h; nSize
0x1800053ac  lea     rax, [rsp+278h+Buffer]
0x1800053b1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800053b6  mov     r9d, 400h; dwLanguageId
0x1800053bc  mov     r8d, ebp; dwMessageId
0x1800053bf  xor     edx, edx; lpSource
0x1800053c1  mov     ecx, 1200h; dwFlags
0x1800053c6  call    cs:__imp_FormatMessageW
0x1800053cd  nop     dword ptr [rax+rax+00h]
0x1800053d2  lea     rsi, [r14+rsi*2]
0x1800053d6  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800053da  mov     rax, [rbx+88h]
0x1800053e1  mov     rcx, [rbx+80h]
0x1800053e8  mov     rdx, rsi; unsigned __int16 *
0x1800053eb  test    r9, r9
0x1800053ee  jz      short loc_180005412
0x1800053f0  mov     [rsp+278h+Arguments], rax
0x1800053f5  mov     qword ptr [rsp+278h+nSize], rcx
0x1800053fa  mov     eax, [rbx+40h]
0x1800053fd  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005401  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180005408  mov     rcx, r14; this
0x18000540b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005410  jmp     short loc_180005429
0x180005412  mov     [rsp+278h+lpBuffer], rax
0x180005417  mov     r9, rcx; unsigned __int16 *
0x18000541a  lea     r8, aHsP; "%hs!%p: "
0x180005421  mov     rcx, r14; this
0x180005424  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005429  mov     r14, rax
0x18000542c  mov     r9, [rbx+90h]; unsigned __int16 *
0x180005433  test    r9, r9
0x180005436  jz      short loc_18000544D
0x180005438  lea     r8, aCallerP; "(caller: %p) "
0x18000543f  mov     rdx, rsi; unsigned __int16 *
0x180005442  mov     rcx, rax; this
0x180005445  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000544a  mov     r14, rax
0x18000544d  call    cs:__imp_GetCurrentThreadId
0x180005454  nop     dword ptr [rax+rax+00h]
0x180005459  lea     rcx, [rsp+278h+Buffer]
0x18000545e  mov     [rsp+278h+var_240], rcx
0x180005463  mov     dword ptr [rsp+278h+Arguments], ebp
0x180005467  mov     [rsp+278h+nSize], eax
0x18000546b  mov     eax, [rbx+44h]
0x18000546e  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180005472  mov     r9, rdi; unsigned __int16 *
0x180005475  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18000547c  mov     rdx, rsi; unsigned __int16 *
0x18000547f  mov     rcx, r14; this
0x180005482  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005487  cmp     [rbx+18h], r15
0x18000548b  jnz     short loc_18000549D
0x18000548d  cmp     [rbx+48h], r15
0x180005491  jnz     short loc_18000549D
0x180005493  cmp     [rbx+30h], r15
0x180005497  jz      loc_18000552D
0x18000549d  lea     r8, asc_180043018; "    "
0x1800054a4  mov     rdx, rsi; unsigned __int16 *
0x1800054a7  mov     rcx, rax; this
0x1800054aa  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054af  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800054b3  test    r9, r9
0x1800054b6  jz      short loc_1800054CA
0x1800054b8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800054bf  mov     rdx, rsi; unsigned __int16 *
0x1800054c2  mov     rcx, rax; this
0x1800054c5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054ca  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800054ce  test    r9, r9
0x1800054d1  jz      short loc_1800054E5
0x1800054d3  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800054da  mov     rdx, rsi; unsigned __int16 *
0x1800054dd  mov     rcx, rax; this
0x1800054e0  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800054e5  mov     rcx, [rbx+28h]
0x1800054e9  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800054ed  mov     rdx, rsi; unsigned __int16 *
0x1800054f0  test    rcx, rcx
0x1800054f3  jz      short loc_18000550B
0x1800054f5  mov     [rsp+278h+lpBuffer], rcx
0x1800054fa  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180005501  mov     rcx, rax; this
0x180005504  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180005509  jmp     short loc_18000552D
0x18000550b  mov     rcx, rax; this
0x18000550e  test    r9, r9
0x180005511  jz      short loc_180005521
0x180005513  lea     r8, aHs; "[%hs]\n"
0x18000551a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000551f  jmp     short loc_18000552D
0x180005521  lea     r8, asc_180043090; "\n"
0x180005528  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000552d  xor     eax, eax
0x18000552f  mov     rcx, [rsp+278h+var_38]
0x180005537  xor     rcx, rsp; StackCookie
0x18000553a  call    __security_check_cookie
0x18000553f  mov     rbx, [rsp+278h+arg_18]
0x180005547  add     rsp, 250h
0x18000554e  pop     r15
0x180005550  pop     r14
0x180005552  pop     rdi
0x180005553  pop     rsi
0x180005554  pop     rbp
0x180005555  retn
```
