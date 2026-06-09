# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x18000959c`
- end: `0x180009852`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180006120`
- `0x18000ab80`
- `0x18000e190`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x18000959c`
- `0x18000ae80`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800096ce`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800096ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000974f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000974f`

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
          v7 = (const char *)&word_180031792;
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
0x18000959c  mov     [rsp+arg_18], rbx
0x1800095a1  push    rbp
0x1800095a2  push    rsi
0x1800095a3  push    rdi
0x1800095a4  push    r14
0x1800095a6  push    r15
0x1800095a8  sub     rsp, 250h
0x1800095af  mov     rax, cs:__security_cookie
0x1800095b6  xor     rax, rsp
0x1800095b9  mov     [rsp+278h+var_38], rax
0x1800095c1  mov     rbx, r8
0x1800095c4  mov     rsi, rdx
0x1800095c7  mov     r14, rcx
0x1800095ca  xor     r15d, r15d
0x1800095cd  test    rdx, rdx
0x1800095d0  jz      loc_180009829
0x1800095d6  test    rcx, rcx
0x1800095d9  jz      loc_180009829
0x1800095df  mov     [rcx], r15w
0x1800095e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800095ea  test    rax, rax
0x1800095ed  jz      short loc_180009610
0x1800095ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800095f6  jz      short loc_180009610
0x1800095f8  mov     r8, rdx
0x1800095fb  mov     rdx, rcx
0x1800095fe  mov     rcx, rbx
0x180009601  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009606  cmp     [r14], r15w
0x18000960a  jnz     loc_180009829
0x180009610  mov     ecx, [rbx]
0x180009612  mov     bpl, 8
0x180009615  test    ecx, ecx
0x180009617  jz      short loc_180009662
0x180009619  sub     ecx, 1
0x18000961c  jz      short loc_18000964A
0x18000961e  sub     ecx, 1
0x180009621  jz      short loc_18000963A
0x180009623  cmp     ecx, 1
0x180009626  jz      short loc_180009631
0x180009628  lea     rdi, word_180031792
0x18000962f  jmp     short loc_180009669
0x180009631  lea     rdi, aFailfast; "FailFast"
0x180009638  jmp     short loc_180009669
0x18000963a  lea     rax, aLoghr; "LogHr"
0x180009641  lea     rdi, aLognt; "LogNt"
0x180009648  jmp     short loc_180009658
0x18000964a  lea     rax, aReturnhr; "ReturnHr"
0x180009651  lea     rdi, aReturnnt; "ReturnNt"
0x180009658  test    [rbx+4], bpl
0x18000965c  cmovz   rdi, rax
0x180009660  jmp     short loc_180009669
0x180009662  lea     rdi, aException; "Exception"
0x180009669  xor     edx, edx; Val
0x18000966b  mov     r8d, 200h; Size
0x180009671  lea     rcx, [rsp+278h+Buffer]; void *
0x180009676  call    memset_0
0x18000967b  test    [rbx+4], bpl
0x18000967f  jz      short loc_1800096A4
0x180009681  mov     ebp, [rbx+0Ch]
0x180009684  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x18000968b  test    rax, rax
0x18000968e  jz      short loc_1800096D4
0x180009690  mov     r8d, 100h
0x180009696  lea     rdx, [rsp+278h+Buffer]
0x18000969b  mov     ecx, ebp
0x18000969d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a2  jmp     short loc_1800096D4
0x1800096a4  mov     ebp, [rbx+8]
0x1800096a7  mov     [rsp+278h+Arguments], r15; Arguments
0x1800096ac  mov     [rsp+278h+nSize], 100h; nSize
0x1800096b4  lea     rax, [rsp+278h+Buffer]
0x1800096b9  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800096be  mov     r9d, 400h; dwLanguageId
0x1800096c4  mov     r8d, ebp; dwMessageId
0x1800096c7  xor     edx, edx; lpSource
0x1800096c9  mov     ecx, 1200h; dwFlags
0x1800096ce  call    cs:__imp_FormatMessageW
0x1800096d4  lea     rsi, [r14+rsi*2]
0x1800096d8  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800096dc  mov     rax, [rbx+88h]
0x1800096e3  mov     rcx, [rbx+80h]
0x1800096ea  mov     rdx, rsi; unsigned __int16 *
0x1800096ed  test    r9, r9
0x1800096f0  jz      short loc_180009714
0x1800096f2  mov     [rsp+278h+Arguments], rax
0x1800096f7  mov     qword ptr [rsp+278h+nSize], rcx
0x1800096fc  mov     eax, [rbx+40h]
0x1800096ff  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009703  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000970a  mov     rcx, r14; this
0x18000970d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009712  jmp     short loc_18000972B
0x180009714  mov     [rsp+278h+lpBuffer], rax
0x180009719  mov     r9, rcx; unsigned __int16 *
0x18000971c  lea     r8, aHsP; "%hs!%p: "
0x180009723  mov     rcx, r14; this
0x180009726  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000972b  mov     r14, rax
0x18000972e  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009735  test    r9, r9
0x180009738  jz      short loc_18000974F
0x18000973a  lea     r8, aCallerP; "(caller: %p) "
0x180009741  mov     rdx, rsi; unsigned __int16 *
0x180009744  mov     rcx, rax; this
0x180009747  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000974c  mov     r14, rax
0x18000974f  call    cs:__imp_GetCurrentThreadId
0x180009755  lea     rcx, [rsp+278h+Buffer]
0x18000975a  mov     [rsp+278h+var_240], rcx
0x18000975f  mov     dword ptr [rsp+278h+Arguments], ebp
0x180009763  mov     [rsp+278h+nSize], eax
0x180009767  mov     eax, [rbx+44h]
0x18000976a  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000976e  mov     r9, rdi; unsigned __int16 *
0x180009771  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180009778  mov     rdx, rsi; unsigned __int16 *
0x18000977b  mov     rcx, r14; this
0x18000977e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009783  cmp     [rbx+18h], r15
0x180009787  jnz     short loc_180009799
0x180009789  cmp     [rbx+48h], r15
0x18000978d  jnz     short loc_180009799
0x18000978f  cmp     [rbx+30h], r15
0x180009793  jz      loc_180009829
0x180009799  lea     r8, asc_180030968; "    "
0x1800097a0  mov     rdx, rsi; unsigned __int16 *
0x1800097a3  mov     rcx, rax; this
0x1800097a6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097ab  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800097af  test    r9, r9
0x1800097b2  jz      short loc_1800097C6
0x1800097b4  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800097bb  mov     rdx, rsi; unsigned __int16 *
0x1800097be  mov     rcx, rax; this
0x1800097c1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097c6  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800097ca  test    r9, r9
0x1800097cd  jz      short loc_1800097E1
0x1800097cf  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800097d6  mov     rdx, rsi; unsigned __int16 *
0x1800097d9  mov     rcx, rax; this
0x1800097dc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097e1  mov     rcx, [rbx+28h]
0x1800097e5  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800097e9  mov     rdx, rsi; unsigned __int16 *
0x1800097ec  test    rcx, rcx
0x1800097ef  jz      short loc_180009807
0x1800097f1  mov     [rsp+278h+lpBuffer], rcx
0x1800097f6  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800097fd  mov     rcx, rax; this
0x180009800  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009805  jmp     short loc_180009829
0x180009807  mov     rcx, rax; this
0x18000980a  test    r9, r9
0x18000980d  jz      short loc_18000981D
0x18000980f  lea     r8, aHs; "[%hs]\n"
0x180009816  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000981b  jmp     short loc_180009829
0x18000981d  lea     r8, asc_1800309E0; "\n"
0x180009824  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009829  xor     eax, eax
0x18000982b  mov     rcx, [rsp+278h+var_38]
0x180009833  xor     rcx, rsp; StackCookie
0x180009836  call    __security_check_cookie
0x18000983b  mov     rbx, [rsp+278h+arg_18]
0x180009843  add     rsp, 250h
0x18000984a  pop     r15
0x18000984c  pop     r14
0x18000984e  pop     rdi
0x18000984f  pop     rsi
0x180009850  pop     rbp
0x180009851  retn
```
