# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800025bc`
- end: `0x180002870`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *__hidden this, wchar_t *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180002878`
- `0x180002c60`
- `0x180004750`
- `0x180005a78`
- `0x18001b8c8`
- `0x180069add`
- `0x180069c16`

## callees

- `0x180002550`
- `0x1800025bc`
- `0x180061960`
- `0x180068ea0`
- `0x180068f20`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000276d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000276d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800026ec`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800026ec`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rsi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rdi
  const wchar_t *v11; // r9
  __int64 v12; // rax
  const wchar_t *v13; // rcx
  wchar_t *v14; // rax
  wil::details *v15; // r14
  const wchar_t *v16; // r9
  wil::details *v17; // rax
  const wchar_t *v18; // r9
  wchar_t *v19; // rax
  const wchar_t *v20; // r9
  const wchar_t *v21; // r9
  const wchar_t *v22; // r9
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
  v7 = (const char *)&pszCabPath;
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
        goto LABEL_17;
      }
      v8 = "LogHr";
      v7 = "LogNt";
    }
    if ( (*(_BYTE *)(a3 + 4) & 8) == 0 )
      v7 = v8;
    goto LABEL_17;
  }
  v7 = "Exception";
LABEL_17:
  memset(Buffer, 0, sizeof(Buffer));
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
  v10 = (wchar_t *)((char *)this + 2 * (_QWORD)a2);
  v11 = *(const wchar_t **)(a3 + 56);
  v12 = *(_QWORD *)(a3 + 136);
  v13 = *(const wchar_t **)(a3 + 128);
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
  v16 = *(const wchar_t **)(a3 + 144);
  if ( v16 )
    v15 = (wil::details *)wil::details::LogStringPrintf((wil::details *)v14, v10, L"(caller: %p) ", v16);
  LODWORD(Arguments) = v9;
  nSize[0] = GetCurrentThreadId();
  LODWORD(lpBuffera) = *(_DWORD *)(a3 + 68);
  v17 = (wil::details *)wil::details::LogStringPrintf(
                          v15,
                          v10,
                          L"%hs(%d) tid(%x) %08X %ws",
                          (const wchar_t *)v7,
                          lpBuffera,
                          *(_QWORD *)nSize,
                          Arguments,
                          Buffer);
  if ( *(_QWORD *)(a3 + 24) || *(_QWORD *)(a3 + 72) || *(_QWORD *)(a3 + 48) )
  {
    v19 = wil::details::LogStringPrintf(v17, v10, L"    ", v18);
    v20 = *(const wchar_t **)(a3 + 24);
    if ( v20 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"Msg:[%ws] ", v20);
    v21 = *(const wchar_t **)(a3 + 72);
    if ( v21 )
      v19 = wil::details::LogStringPrintf((wil::details *)v19, v10, L"CallContext:[%hs] ", v21);
    v22 = *(const wchar_t **)(a3 + 48);
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
0x1800025bc  mov     [rsp+arg_18], rbx
0x1800025c1  push    rbp
0x1800025c2  push    rsi
0x1800025c3  push    rdi
0x1800025c4  push    r14
0x1800025c6  push    r15
0x1800025c8  sub     rsp, 250h
0x1800025cf  mov     rax, cs:__security_cookie
0x1800025d6  xor     rax, rsp
0x1800025d9  mov     [rsp+278h+var_38], rax
0x1800025e1  mov     rbx, r8
0x1800025e4  mov     rdi, rdx
0x1800025e7  mov     r14, rcx
0x1800025ea  xor     r15d, r15d
0x1800025ed  test    rdx, rdx
0x1800025f0  jz      loc_180002847
0x1800025f6  test    rcx, rcx
0x1800025f9  jz      loc_180002847
0x1800025ff  mov     [rcx], r15w
0x180002603  mov     rax, cs:g_pfnResultLoggingCallback
0x18000260a  test    rax, rax
0x18000260d  jz      short loc_180002630
0x18000260f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180002616  jz      short loc_180002630
0x180002618  mov     r8, rdx
0x18000261b  mov     rdx, rcx
0x18000261e  mov     rcx, rbx
0x180002621  call    _guard_dispatch_icall
0x180002626  cmp     [r14], r15w
0x18000262a  jnz     loc_180002847
0x180002630  lea     rsi, pszCabPath
0x180002637  mov     ecx, [rbx]
0x180002639  mov     bpl, 8
0x18000263c  test    ecx, ecx
0x18000263e  jz      short loc_180002680
0x180002640  sub     ecx, 1
0x180002643  jz      short loc_180002668
0x180002645  sub     ecx, 1
0x180002648  jz      short loc_180002658
0x18000264a  cmp     ecx, 1
0x18000264d  jnz     short loc_180002687
0x18000264f  lea     rsi, aFailfast; "FailFast"
0x180002656  jmp     short loc_180002687
0x180002658  lea     rax, aLoghr; "LogHr"
0x18000265f  lea     rsi, aLognt; "LogNt"
0x180002666  jmp     short loc_180002676
0x180002668  lea     rax, aReturnhr; "ReturnHr"
0x18000266f  lea     rsi, aReturnnt; "ReturnNt"
0x180002676  test    [rbx+4], bpl
0x18000267a  cmovz   rsi, rax
0x18000267e  jmp     short loc_180002687
0x180002680  lea     rsi, aException; "Exception"
0x180002687  xor     edx, edx; Val
0x180002689  mov     r8d, 200h; Size
0x18000268f  lea     rcx, [rsp+278h+Buffer]; void *
0x180002694  call    memset
0x180002699  test    [rbx+4], bpl
0x18000269d  jz      short loc_1800026C2
0x18000269f  mov     ebp, [rbx+0Ch]
0x1800026a2  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800026a9  test    rax, rax
0x1800026ac  jz      short loc_1800026F2
0x1800026ae  mov     r8d, 100h
0x1800026b4  lea     rdx, [rsp+278h+Buffer]
0x1800026b9  mov     ecx, ebp
0x1800026bb  call    _guard_dispatch_icall
0x1800026c0  jmp     short loc_1800026F2
0x1800026c2  mov     ebp, [rbx+8]
0x1800026c5  mov     [rsp+278h+Arguments], r15; Arguments
0x1800026ca  mov     [rsp+278h+nSize], 100h; nSize
0x1800026d2  lea     rax, [rsp+278h+Buffer]
0x1800026d7  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800026dc  mov     r9d, 400h; dwLanguageId
0x1800026e2  mov     r8d, ebp; dwMessageId
0x1800026e5  xor     edx, edx; lpSource
0x1800026e7  mov     ecx, 1200h; dwFlags
0x1800026ec  call    cs:__imp_FormatMessageW
0x1800026f2  lea     rdi, [r14+rdi*2]
0x1800026f6  mov     r9, [rbx+38h]; wchar_t *
0x1800026fa  mov     rax, [rbx+88h]
0x180002701  mov     rcx, [rbx+80h]
0x180002708  mov     rdx, rdi; wchar_t *
0x18000270b  test    r9, r9
0x18000270e  jz      short loc_180002732
0x180002710  mov     [rsp+278h+Arguments], rax
0x180002715  mov     qword ptr [rsp+278h+nSize], rcx
0x18000271a  mov     eax, [rbx+40h]
0x18000271d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180002721  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180002728  mov     rcx, r14; this
0x18000272b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002730  jmp     short loc_180002749
0x180002732  mov     [rsp+278h+lpBuffer], rax
0x180002737  mov     r9, rcx; wchar_t *
0x18000273a  lea     r8, aHsP; "%hs!%p: "
0x180002741  mov     rcx, r14; this
0x180002744  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002749  mov     r14, rax
0x18000274c  mov     r9, [rbx+90h]; wchar_t *
0x180002753  test    r9, r9
0x180002756  jz      short loc_18000276D
0x180002758  lea     r8, aCallerP; "(caller: %p) "
0x18000275f  mov     rdx, rdi; wchar_t *
0x180002762  mov     rcx, rax; this
0x180002765  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000276a  mov     r14, rax
0x18000276d  call    cs:__imp_GetCurrentThreadId
0x180002773  lea     rcx, [rsp+278h+Buffer]
0x180002778  mov     [rsp+278h+var_240], rcx
0x18000277d  mov     dword ptr [rsp+278h+Arguments], ebp
0x180002781  mov     [rsp+278h+nSize], eax
0x180002785  mov     eax, [rbx+44h]
0x180002788  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000278c  mov     r9, rsi; wchar_t *
0x18000278f  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180002796  mov     rdx, rdi; wchar_t *
0x180002799  mov     rcx, r14; this
0x18000279c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800027a1  cmp     [rbx+18h], r15
0x1800027a5  jnz     short loc_1800027B7
0x1800027a7  cmp     [rbx+48h], r15
0x1800027ab  jnz     short loc_1800027B7
0x1800027ad  cmp     [rbx+30h], r15
0x1800027b1  jz      loc_180002847
0x1800027b7  lea     r8, asc_18006EBE0; "    "
0x1800027be  mov     rdx, rdi; wchar_t *
0x1800027c1  mov     rcx, rax; this
0x1800027c4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800027c9  mov     r9, [rbx+18h]; wchar_t *
0x1800027cd  test    r9, r9
0x1800027d0  jz      short loc_1800027E4
0x1800027d2  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800027d9  mov     rdx, rdi; wchar_t *
0x1800027dc  mov     rcx, rax; this
0x1800027df  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800027e4  mov     r9, [rbx+48h]; wchar_t *
0x1800027e8  test    r9, r9
0x1800027eb  jz      short loc_1800027FF
0x1800027ed  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800027f4  mov     rdx, rdi; wchar_t *
0x1800027f7  mov     rcx, rax; this
0x1800027fa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800027ff  mov     rcx, [rbx+28h]
0x180002803  mov     r9, [rbx+30h]; wchar_t *
0x180002807  mov     rdx, rdi; wchar_t *
0x18000280a  test    rcx, rcx
0x18000280d  jz      short loc_180002825
0x18000280f  mov     [rsp+278h+lpBuffer], rcx
0x180002814  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000281b  mov     rcx, rax; this
0x18000281e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002823  jmp     short loc_180002847
0x180002825  mov     rcx, rax; this
0x180002828  test    r9, r9
0x18000282b  jz      short loc_18000283B
0x18000282d  lea     r8, aHs; "[%hs]\n"
0x180002834  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002839  jmp     short loc_180002847
0x18000283b  lea     r8, asc_18006EC58; "\n"
0x180002842  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180002847  xor     eax, eax
0x180002849  mov     rcx, [rsp+278h+var_38]
0x180002851  xor     rcx, rsp; StackCookie
0x180002854  call    __security_check_cookie
0x180002859  mov     rbx, [rsp+278h+arg_18]
0x180002861  add     rsp, 250h
0x180002868  pop     r15
0x18000286a  pop     r14
0x18000286c  pop     rdi
0x18000286d  pop     rsi
0x18000286e  pop     rbp
0x18000286f  retn
```
