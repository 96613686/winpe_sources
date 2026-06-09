# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800095d4`
- end: `0x18000988a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180007c74`
- `0x18000a138`
- `0x18000a76c`
- `0x18000cf90`

## callees

- `0x1800015f0`
- `0x180002148`
- `0x1800095d4`
- `0x18000a438`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009787`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009787`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009706`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180009706`

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
          v7 = (const char *)&word_180024EF2;
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
0x1800095d4  mov     [rsp+arg_18], rbx
0x1800095d9  push    rbp
0x1800095da  push    rsi
0x1800095db  push    rdi
0x1800095dc  push    r14
0x1800095de  push    r15
0x1800095e0  sub     rsp, 250h
0x1800095e7  mov     rax, cs:__security_cookie
0x1800095ee  xor     rax, rsp
0x1800095f1  mov     [rsp+278h+var_38], rax
0x1800095f9  mov     rbx, r8
0x1800095fc  mov     rsi, rdx
0x1800095ff  mov     r14, rcx
0x180009602  xor     r15d, r15d
0x180009605  test    rdx, rdx
0x180009608  jz      loc_180009861
0x18000960e  test    rcx, rcx
0x180009611  jz      loc_180009861
0x180009617  mov     [rcx], r15w
0x18000961b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009622  test    rax, rax
0x180009625  jz      short loc_180009648
0x180009627  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000962e  jz      short loc_180009648
0x180009630  mov     r8, rdx
0x180009633  mov     rdx, rcx
0x180009636  mov     rcx, rbx
0x180009639  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000963e  cmp     [r14], r15w
0x180009642  jnz     loc_180009861
0x180009648  mov     ecx, [rbx]
0x18000964a  mov     bpl, 8
0x18000964d  test    ecx, ecx
0x18000964f  jz      short loc_18000969A
0x180009651  sub     ecx, 1
0x180009654  jz      short loc_180009682
0x180009656  sub     ecx, 1
0x180009659  jz      short loc_180009672
0x18000965b  cmp     ecx, 1
0x18000965e  jz      short loc_180009669
0x180009660  lea     rdi, word_180024EF2
0x180009667  jmp     short loc_1800096A1
0x180009669  lea     rdi, aFailfast; "FailFast"
0x180009670  jmp     short loc_1800096A1
0x180009672  lea     rax, aLoghr; "LogHr"
0x180009679  lea     rdi, aLognt; "LogNt"
0x180009680  jmp     short loc_180009690
0x180009682  lea     rax, aReturnhr; "ReturnHr"
0x180009689  lea     rdi, aReturnnt; "ReturnNt"
0x180009690  test    [rbx+4], bpl
0x180009694  cmovz   rdi, rax
0x180009698  jmp     short loc_1800096A1
0x18000969a  lea     rdi, aException; "Exception"
0x1800096a1  xor     edx, edx; Val
0x1800096a3  mov     r8d, 200h; Size
0x1800096a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800096ae  call    memset_0
0x1800096b3  test    [rbx+4], bpl
0x1800096b7  jz      short loc_1800096DC
0x1800096b9  mov     ebp, [rbx+0Ch]
0x1800096bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800096c3  test    rax, rax
0x1800096c6  jz      short loc_18000970C
0x1800096c8  mov     r8d, 100h
0x1800096ce  lea     rdx, [rsp+278h+Buffer]
0x1800096d3  mov     ecx, ebp
0x1800096d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096da  jmp     short loc_18000970C
0x1800096dc  mov     ebp, [rbx+8]
0x1800096df  mov     [rsp+278h+Arguments], r15; Arguments
0x1800096e4  mov     [rsp+278h+nSize], 100h; nSize
0x1800096ec  lea     rax, [rsp+278h+Buffer]
0x1800096f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1800096f6  mov     r9d, 400h; dwLanguageId
0x1800096fc  mov     r8d, ebp; dwMessageId
0x1800096ff  xor     edx, edx; lpSource
0x180009701  mov     ecx, 1200h; dwFlags
0x180009706  call    cs:__imp_FormatMessageW
0x18000970c  lea     rsi, [r14+rsi*2]
0x180009710  mov     r9, [rbx+38h]; unsigned __int16 *
0x180009714  mov     rax, [rbx+88h]
0x18000971b  mov     rcx, [rbx+80h]
0x180009722  mov     rdx, rsi; unsigned __int16 *
0x180009725  test    r9, r9
0x180009728  jz      short loc_18000974C
0x18000972a  mov     [rsp+278h+Arguments], rax
0x18000972f  mov     qword ptr [rsp+278h+nSize], rcx
0x180009734  mov     eax, [rbx+40h]
0x180009737  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000973b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180009742  mov     rcx, r14; this
0x180009745  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000974a  jmp     short loc_180009763
0x18000974c  mov     [rsp+278h+lpBuffer], rax
0x180009751  mov     r9, rcx; unsigned __int16 *
0x180009754  lea     r8, aHsP; "%hs!%p: "
0x18000975b  mov     rcx, r14; this
0x18000975e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009763  mov     r14, rax
0x180009766  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000976d  test    r9, r9
0x180009770  jz      short loc_180009787
0x180009772  lea     r8, aCallerP; "(caller: %p) "
0x180009779  mov     rdx, rsi; unsigned __int16 *
0x18000977c  mov     rcx, rax; this
0x18000977f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009784  mov     r14, rax
0x180009787  call    cs:__imp_GetCurrentThreadId
0x18000978d  lea     rcx, [rsp+278h+Buffer]
0x180009792  mov     [rsp+278h+var_240], rcx
0x180009797  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000979b  mov     [rsp+278h+nSize], eax
0x18000979f  mov     eax, [rbx+44h]
0x1800097a2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800097a6  mov     r9, rdi; unsigned __int16 *
0x1800097a9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800097b0  mov     rdx, rsi; unsigned __int16 *
0x1800097b3  mov     rcx, r14; this
0x1800097b6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097bb  cmp     [rbx+18h], r15
0x1800097bf  jnz     short loc_1800097D1
0x1800097c1  cmp     [rbx+48h], r15
0x1800097c5  jnz     short loc_1800097D1
0x1800097c7  cmp     [rbx+30h], r15
0x1800097cb  jz      loc_180009861
0x1800097d1  lea     r8, asc_180024FE0; "    "
0x1800097d8  mov     rdx, rsi; unsigned __int16 *
0x1800097db  mov     rcx, rax; this
0x1800097de  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097e3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800097e7  test    r9, r9
0x1800097ea  jz      short loc_1800097FE
0x1800097ec  lea     r8, aMsgWs; "Msg:[%ws] "
0x1800097f3  mov     rdx, rsi; unsigned __int16 *
0x1800097f6  mov     rcx, rax; this
0x1800097f9  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800097fe  mov     r9, [rbx+48h]; unsigned __int16 *
0x180009802  test    r9, r9
0x180009805  jz      short loc_180009819
0x180009807  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000980e  mov     rdx, rsi; unsigned __int16 *
0x180009811  mov     rcx, rax; this
0x180009814  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009819  mov     rcx, [rbx+28h]
0x18000981d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009821  mov     rdx, rsi; unsigned __int16 *
0x180009824  test    rcx, rcx
0x180009827  jz      short loc_18000983F
0x180009829  mov     [rsp+278h+lpBuffer], rcx
0x18000982e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180009835  mov     rcx, rax; this
0x180009838  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000983d  jmp     short loc_180009861
0x18000983f  mov     rcx, rax; this
0x180009842  test    r9, r9
0x180009845  jz      short loc_180009855
0x180009847  lea     r8, aHs; "[%hs]\n"
0x18000984e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009853  jmp     short loc_180009861
0x180009855  lea     r8, asc_180025058; "\n"
0x18000985c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009861  xor     eax, eax
0x180009863  mov     rcx, [rsp+278h+var_38]
0x18000986b  xor     rcx, rsp; StackCookie
0x18000986e  call    __security_check_cookie
0x180009873  mov     rbx, [rsp+278h+arg_18]
0x18000987b  add     rsp, 250h
0x180009882  pop     r15
0x180009884  pop     r14
0x180009886  pop     rdi
0x180009887  pop     rsi
0x180009888  pop     rbp
0x180009889  retn
```
