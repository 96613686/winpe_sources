# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180057474`
- end: `0x180057739`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `709`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `2`
- callee_count: `5`
- tags: ``

## callers

- `0x180058370`
- `0x18005b75c`

## callees

- `0x18004d320`
- `0x18004dd14`
- `0x180057474`
- `0x180057bd8`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005762f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005762f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800575a8`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x1800575a8`

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
          v7 = (const char *)&qword_1800B52D8;
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
0x180057474  mov     [rsp+arg_18], rbx
0x180057479  push    rbp
0x18005747a  push    rsi
0x18005747b  push    rdi
0x18005747c  push    r14
0x18005747e  push    r15
0x180057480  sub     rsp, 250h
0x180057487  mov     rax, cs:__security_cookie
0x18005748e  xor     rax, rsp
0x180057491  mov     [rsp+278h+var_38], rax
0x180057499  mov     rbx, r8
0x18005749c  mov     rsi, rdx
0x18005749f  mov     r14, rcx
0x1800574a2  xor     r15d, r15d
0x1800574a5  test    rdx, rdx
0x1800574a8  jz      loc_18005770F
0x1800574ae  test    rcx, rcx
0x1800574b1  jz      loc_18005770F
0x1800574b7  mov     [rcx], r15w
0x1800574bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800574c2  test    rax, rax
0x1800574c5  jz      short loc_1800574E9
0x1800574c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x1800574ce  jz      short loc_1800574E9
0x1800574d0  mov     r8, rdx
0x1800574d3  mov     rdx, rcx
0x1800574d6  mov     rcx, rbx
0x1800574d9  call    cs:__guard_dispatch_icall_fptr
0x1800574df  cmp     [r14], r15w
0x1800574e3  jnz     loc_18005770F
0x1800574e9  mov     ecx, [rbx]
0x1800574eb  mov     bpl, 8
0x1800574ee  test    ecx, ecx
0x1800574f0  jz      short loc_18005753B
0x1800574f2  sub     ecx, 1
0x1800574f5  jz      short loc_180057523
0x1800574f7  sub     ecx, 1
0x1800574fa  jz      short loc_180057513
0x1800574fc  cmp     ecx, 1
0x1800574ff  jz      short loc_18005750A
0x180057501  lea     rdi, qword_1800B52D8
0x180057508  jmp     short loc_180057542
0x18005750a  lea     rdi, aFailfast; "FailFast"
0x180057511  jmp     short loc_180057542
0x180057513  lea     rax, aLoghr; "LogHr"
0x18005751a  lea     rdi, aLognt; "LogNt"
0x180057521  jmp     short loc_180057531
0x180057523  lea     rax, aReturnhr; "ReturnHr"
0x18005752a  lea     rdi, aReturnnt; "ReturnNt"
0x180057531  test    [rbx+4], bpl
0x180057535  cmovz   rdi, rax
0x180057539  jmp     short loc_180057542
0x18005753b  lea     rdi, aException; "Exception"
0x180057542  xor     edx, edx; Val
0x180057544  mov     r8d, 200h; Size
0x18005754a  lea     rcx, [rsp+278h+Buffer]; void *
0x18005754f  call    memset_0
0x180057554  test    [rbx+4], bpl
0x180057558  jz      short loc_18005757E
0x18005755a  mov     ebp, [rbx+0Ch]
0x18005755d  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180057564  test    rax, rax
0x180057567  jz      short loc_1800575B4
0x180057569  mov     r8d, 100h
0x18005756f  lea     rdx, [rsp+278h+Buffer]
0x180057574  mov     ecx, ebp
0x180057576  call    cs:__guard_dispatch_icall_fptr
0x18005757c  jmp     short loc_1800575B4
0x18005757e  mov     ebp, [rbx+8]
0x180057581  mov     [rsp+278h+Arguments], r15; Arguments
0x180057586  mov     [rsp+278h+nSize], 100h; nSize
0x18005758e  lea     rax, [rsp+278h+Buffer]
0x180057593  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180057598  mov     r9d, 400h; dwLanguageId
0x18005759e  mov     r8d, ebp; dwMessageId
0x1800575a1  xor     edx, edx; lpSource
0x1800575a3  mov     ecx, 1200h; dwFlags
0x1800575a8  call    cs:__imp_FormatMessageW
0x1800575af  nop     dword ptr [rax+rax+00h]
0x1800575b4  lea     rsi, [r14+rsi*2]
0x1800575b8  mov     r9, [rbx+38h]; unsigned __int16 *
0x1800575bc  mov     rax, [rbx+88h]
0x1800575c3  mov     rcx, [rbx+80h]
0x1800575ca  mov     rdx, rsi; unsigned __int16 *
0x1800575cd  test    r9, r9
0x1800575d0  jz      short loc_1800575F4
0x1800575d2  mov     [rsp+278h+Arguments], rax
0x1800575d7  mov     qword ptr [rsp+278h+nSize], rcx
0x1800575dc  mov     eax, [rbx+40h]
0x1800575df  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800575e3  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800575ea  mov     rcx, r14; this
0x1800575ed  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800575f2  jmp     short loc_18005760B
0x1800575f4  mov     [rsp+278h+lpBuffer], rax
0x1800575f9  mov     r9, rcx; unsigned __int16 *
0x1800575fc  lea     r8, aHsP; "%hs!%p: "
0x180057603  mov     rcx, r14; this
0x180057606  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005760b  mov     r14, rax
0x18005760e  mov     r9, [rbx+90h]; unsigned __int16 *
0x180057615  test    r9, r9
0x180057618  jz      short loc_18005762F
0x18005761a  lea     r8, aCallerP; "(caller: %p) "
0x180057621  mov     rdx, rsi; unsigned __int16 *
0x180057624  mov     rcx, rax; this
0x180057627  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005762c  mov     r14, rax
0x18005762f  call    cs:__imp_GetCurrentThreadId
0x180057636  nop     dword ptr [rax+rax+00h]
0x18005763b  lea     rcx, [rsp+278h+Buffer]
0x180057640  mov     [rsp+278h+var_240], rcx
0x180057645  mov     dword ptr [rsp+278h+Arguments], ebp
0x180057649  mov     [rsp+278h+nSize], eax
0x18005764d  mov     eax, [rbx+44h]
0x180057650  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180057654  mov     r9, rdi; unsigned __int16 *
0x180057657  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x18005765e  mov     rdx, rsi; unsigned __int16 *
0x180057661  mov     rcx, r14; this
0x180057664  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180057669  cmp     [rbx+18h], r15
0x18005766d  jnz     short loc_18005767F
0x18005766f  cmp     [rbx+48h], r15
0x180057673  jnz     short loc_18005767F
0x180057675  cmp     [rbx+30h], r15
0x180057679  jz      loc_18005770F
0x18005767f  lea     r8, asc_1800B53E0; "    "
0x180057686  mov     rdx, rsi; unsigned __int16 *
0x180057689  mov     rcx, rax; this
0x18005768c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180057691  mov     r9, [rbx+18h]; unsigned __int16 *
0x180057695  test    r9, r9
0x180057698  jz      short loc_1800576AC
0x18005769a  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800576a1  mov     rdx, rsi; unsigned __int16 *
0x1800576a4  mov     rcx, rax; this
0x1800576a7  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800576ac  mov     r9, [rbx+48h]; unsigned __int16 *
0x1800576b0  test    r9, r9
0x1800576b3  jz      short loc_1800576C7
0x1800576b5  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x1800576bc  mov     rdx, rsi; unsigned __int16 *
0x1800576bf  mov     rcx, rax; this
0x1800576c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800576c7  mov     rcx, [rbx+28h]
0x1800576cb  mov     r9, [rbx+30h]; unsigned __int16 *
0x1800576cf  mov     rdx, rsi; unsigned __int16 *
0x1800576d2  test    rcx, rcx
0x1800576d5  jz      short loc_1800576ED
0x1800576d7  mov     [rsp+278h+lpBuffer], rcx
0x1800576dc  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800576e3  mov     rcx, rax; this
0x1800576e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800576eb  jmp     short loc_18005770F
0x1800576ed  mov     rcx, rax; this
0x1800576f0  test    r9, r9
0x1800576f3  jz      short loc_180057703
0x1800576f5  lea     r8, aHs; "[%hs]\n"
0x1800576fc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180057701  jmp     short loc_18005770F
0x180057703  lea     r8, asc_1800B5458; "\n"
0x18005770a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18005770f  xor     eax, eax
0x180057711  mov     rcx, [rsp+278h+var_38]
0x180057719  xor     rcx, rsp; StackCookie
0x18005771c  call    __security_check_cookie
0x180057721  mov     rbx, [rsp+278h+arg_18]
0x180057729  add     rsp, 250h
0x180057730  pop     r15
0x180057732  pop     r14
0x180057734  pop     rdi
0x180057735  pop     rsi
0x180057736  pop     rbp
0x180057737  retn
```
