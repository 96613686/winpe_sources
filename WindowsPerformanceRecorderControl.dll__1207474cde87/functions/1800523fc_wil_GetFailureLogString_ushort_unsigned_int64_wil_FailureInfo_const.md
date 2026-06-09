# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800523fc`
- end: `0x1800526bd`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180053950`
- `0x1800564c0`

## callees

- `0x18004ece0`
- `0x18004f964`
- `0x1800523fc`
- `0x180053c54`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800525ba`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800525ba`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180052539`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180052539`

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
          v7 = &byte_1800986EF;
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
0x1800523fc  mov     rax, rsp
0x1800523ff  push    rbp
0x180052400  push    rsi
0x180052401  push    rdi
0x180052402  push    r14
0x180052404  push    r15
0x180052406  sub     rsp, 260h
0x18005240d  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x180052416  mov     [rax+20h], rbx
0x18005241a  mov     rax, cs:__security_cookie
0x180052421  xor     rax, rsp
0x180052424  mov     [rsp+288h+var_38], rax
0x18005242c  mov     rbx, r8
0x18005242f  mov     rsi, rdx
0x180052432  mov     r14, rcx
0x180052435  xor     r15d, r15d
0x180052438  test    rdx, rdx
0x18005243b  jz      loc_180052694
0x180052441  test    rcx, rcx
0x180052444  jz      loc_180052694
0x18005244a  mov     [rcx], r15w
0x18005244e  mov     rax, cs:g_pfnResultLoggingCallback
0x180052455  test    rax, rax
0x180052458  jz      short loc_18005247B
0x18005245a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180052461  jz      short loc_18005247B
0x180052463  mov     r8, rdx
0x180052466  mov     rdx, rcx
0x180052469  mov     rcx, rbx
0x18005246c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180052471  cmp     [r14], r15w
0x180052475  jnz     loc_180052694
0x18005247b  mov     ecx, [rbx]
0x18005247d  mov     bpl, 8
0x180052480  test    ecx, ecx
0x180052482  jz      short loc_1800524CD
0x180052484  sub     ecx, 1
0x180052487  jz      short loc_1800524B5
0x180052489  sub     ecx, 1
0x18005248c  jz      short loc_1800524A5
0x18005248e  cmp     ecx, 1
0x180052491  jz      short loc_18005249C
0x180052493  lea     rdi, byte_1800986EF
0x18005249a  jmp     short loc_1800524D4
0x18005249c  lea     rdi, aFailfast; "FailFast"
0x1800524a3  jmp     short loc_1800524D4
0x1800524a5  lea     rax, aLoghr; "LogHr"
0x1800524ac  lea     rdi, aLognt; "LogNt"
0x1800524b3  jmp     short loc_1800524C3
0x1800524b5  lea     rax, aReturnhr; "ReturnHr"
0x1800524bc  lea     rdi, aReturnnt; "ReturnNt"
0x1800524c3  test    [rbx+4], bpl
0x1800524c7  cmovz   rdi, rax
0x1800524cb  jmp     short loc_1800524D4
0x1800524cd  lea     rdi, aException; "Exception"
0x1800524d4  xor     edx, edx; Val
0x1800524d6  mov     r8d, 200h; Size
0x1800524dc  lea     rcx, [rsp+288h+Buffer]; void *
0x1800524e1  call    memset_0
0x1800524e6  test    [rbx+4], bpl
0x1800524ea  jz      short loc_18005250F
0x1800524ec  mov     ebp, [rbx+0Ch]
0x1800524ef  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800524f6  test    rax, rax
0x1800524f9  jz      short loc_18005253F
0x1800524fb  mov     r8d, 100h
0x180052501  lea     rdx, [rsp+288h+Buffer]
0x180052506  mov     ecx, ebp
0x180052508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005250d  jmp     short loc_18005253F
0x18005250f  mov     ebp, [rbx+8]
0x180052512  mov     [rsp+288h+Arguments], r15; Arguments
0x180052517  mov     [rsp+288h+nSize], 100h; nSize
0x18005251f  lea     rax, [rsp+288h+Buffer]
0x180052524  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180052529  mov     r9d, 400h; dwLanguageId
0x18005252f  mov     r8d, ebp; dwMessageId
0x180052532  xor     edx, edx; lpSource
0x180052534  mov     ecx, 1200h; dwFlags
0x180052539  call    cs:__imp_FormatMessageW
0x18005253f  lea     rsi, [r14+rsi*2]
0x180052543  mov     r9, [rbx+38h]; unsigned __int16 *
0x180052547  mov     rax, [rbx+88h]
0x18005254e  mov     rcx, [rbx+80h]
0x180052555  mov     rdx, rsi; unsigned __int16 *
0x180052558  test    r9, r9
0x18005255b  jz      short loc_18005257F
0x18005255d  mov     [rsp+288h+Arguments], rax
0x180052562  mov     qword ptr [rsp+288h+nSize], rcx
0x180052567  mov     eax, [rbx+40h]
0x18005256a  mov     dword ptr [rsp+288h+lpBuffer], eax
0x18005256e  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180052575  mov     rcx, r14; this
0x180052578  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005257d  jmp     short loc_180052596
0x18005257f  mov     [rsp+288h+lpBuffer], rax
0x180052584  mov     r9, rcx; unsigned __int16 *
0x180052587  lea     r8, aHsP; "%hs!%p: "
0x18005258e  mov     rcx, r14; this
0x180052591  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052596  mov     r14, rax
0x180052599  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800525a0  test    r9, r9
0x1800525a3  jz      short loc_1800525BA
0x1800525a5  lea     r8, aCallerP; "(caller: %p) "
0x1800525ac  mov     rdx, rsi; unsigned __int16 *
0x1800525af  mov     rcx, rax; this
0x1800525b2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800525b7  mov     r14, rax
0x1800525ba  call    cs:__imp_GetCurrentThreadId
0x1800525c0  lea     rcx, [rsp+288h+Buffer]
0x1800525c5  mov     [rsp+288h+var_250], rcx
0x1800525ca  mov     dword ptr [rsp+288h+Arguments], ebp
0x1800525ce  mov     [rsp+288h+nSize], eax
0x1800525d2  mov     eax, [rbx+44h]
0x1800525d5  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800525d9  mov     r9, rdi; unsigned __int16 *
0x1800525dc  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800525e3  mov     rdx, rsi; unsigned __int16 *
0x1800525e6  mov     rcx, r14; this
0x1800525e9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800525ee  cmp     [rbx+18h], r15
0x1800525f2  jnz     short loc_180052604
0x1800525f4  cmp     [rbx+48h], r15
0x1800525f8  jnz     short loc_180052604
0x1800525fa  cmp     [rbx+30h], r15
0x1800525fe  jz      loc_180052694
0x180052604  lea     r8, asc_18009A528; "    "
0x18005260b  mov     rdx, rsi; unsigned __int16 *
0x18005260e  mov     rcx, rax; this
0x180052611  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052616  mov     r9, [rbx+18h]; unsigned __int16 *
0x18005261a  test    r9, r9
0x18005261d  jz      short loc_180052631
0x18005261f  lea     r8, aMsgWs; "Msg:[%ws] "
0x180052626  mov     rdx, rsi; unsigned __int16 *
0x180052629  mov     rcx, rax; this
0x18005262c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052631  mov     r9, [rbx+48h]; unsigned __int16 *
0x180052635  test    r9, r9
0x180052638  jz      short loc_18005264C
0x18005263a  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180052641  mov     rdx, rsi; unsigned __int16 *
0x180052644  mov     rcx, rax; this
0x180052647  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005264c  mov     rcx, [rbx+28h]
0x180052650  mov     r9, [rbx+30h]; unsigned __int16 *
0x180052654  mov     rdx, rsi; unsigned __int16 *
0x180052657  test    rcx, rcx
0x18005265a  jz      short loc_180052672
0x18005265c  mov     [rsp+288h+lpBuffer], rcx
0x180052661  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180052668  mov     rcx, rax; this
0x18005266b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052670  jmp     short loc_180052694
0x180052672  mov     rcx, rax; this
0x180052675  test    r9, r9
0x180052678  jz      short loc_180052688
0x18005267a  lea     r8, aHs; "[%hs]\n"
0x180052681  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052686  jmp     short loc_180052694
0x180052688  lea     r8, asc_1800996A0; "\n"
0x18005268f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180052694  xor     eax, eax
0x180052696  mov     rcx, [rsp+288h+var_38]
0x18005269e  xor     rcx, rsp; StackCookie
0x1800526a1  call    __security_check_cookie
0x1800526a6  mov     rbx, [rsp+288h+arg_18]
0x1800526ae  add     rsp, 260h
0x1800526b5  pop     r15
0x1800526b7  pop     r14
0x1800526b9  pop     rdi
0x1800526ba  pop     rsi
0x1800526bb  pop     rbp
0x1800526bc  retn
```
