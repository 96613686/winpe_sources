# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800075f4`
- end: `0x1800078b5`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `6`
- callee_count: `5`
- tags: ``

## callers

- `0x180004c4c`
- `0x180004ed8`
- `0x18000823c`
- `0x18000c1b0`
- `0x180031e27`
- `0x180031f3d`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x1800075f4`
- `0x180008544`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077b2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800077b2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007731`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007731`

## pseudocode

```c
__int64 __fastcall wil::GetFailureLogString(wil *this, wchar_t *a2, __int64 a3, const struct wil::FailureInfo *a4)
{
  const char *v7; // rdi
  const char *v8; // rax
  DWORD v9; // ebp
  wchar_t *v10; // rsi
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
          v7 = (const char *)&qword_180036878;
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
                          Buffer,
                          -2);
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
0x1800075f4  mov     rax, rsp
0x1800075f7  push    rbp
0x1800075f8  push    rsi
0x1800075f9  push    rdi
0x1800075fa  push    r14
0x1800075fc  push    r15
0x1800075fe  sub     rsp, 260h
0x180007605  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x18000760e  mov     [rax+20h], rbx
0x180007612  mov     rax, cs:__security_cookie
0x180007619  xor     rax, rsp
0x18000761c  mov     [rsp+288h+var_38], rax
0x180007624  mov     rbx, r8
0x180007627  mov     rsi, rdx
0x18000762a  mov     r14, rcx
0x18000762d  xor     r15d, r15d
0x180007630  test    rdx, rdx
0x180007633  jz      loc_18000788C
0x180007639  test    rcx, rcx
0x18000763c  jz      loc_18000788C
0x180007642  mov     [rcx], r15w
0x180007646  mov     rax, cs:g_pfnResultLoggingCallback
0x18000764d  test    rax, rax
0x180007650  jz      short loc_180007673
0x180007652  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180007659  jz      short loc_180007673
0x18000765b  mov     r8, rdx
0x18000765e  mov     rdx, rcx
0x180007661  mov     rcx, rbx
0x180007664  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007669  cmp     [r14], r15w
0x18000766d  jnz     loc_18000788C
0x180007673  mov     ecx, [rbx]
0x180007675  mov     bpl, 8
0x180007678  test    ecx, ecx
0x18000767a  jz      short loc_1800076C5
0x18000767c  sub     ecx, 1
0x18000767f  jz      short loc_1800076AD
0x180007681  sub     ecx, 1
0x180007684  jz      short loc_18000769D
0x180007686  cmp     ecx, 1
0x180007689  jz      short loc_180007694
0x18000768b  lea     rdi, qword_180036878
0x180007692  jmp     short loc_1800076CC
0x180007694  lea     rdi, aFailfast; "FailFast"
0x18000769b  jmp     short loc_1800076CC
0x18000769d  lea     rax, aLoghr; "LogHr"
0x1800076a4  lea     rdi, aLognt; "LogNt"
0x1800076ab  jmp     short loc_1800076BB
0x1800076ad  lea     rax, aReturnhr; "ReturnHr"
0x1800076b4  lea     rdi, aReturnnt; "ReturnNt"
0x1800076bb  test    [rbx+4], bpl
0x1800076bf  cmovz   rdi, rax
0x1800076c3  jmp     short loc_1800076CC
0x1800076c5  lea     rdi, aException; "Exception"
0x1800076cc  xor     edx, edx; Val
0x1800076ce  mov     r8d, 200h; Size
0x1800076d4  lea     rcx, [rsp+288h+Buffer]; void *
0x1800076d9  call    memset_0
0x1800076de  test    [rbx+4], bpl
0x1800076e2  jz      short loc_180007707
0x1800076e4  mov     ebp, [rbx+0Ch]
0x1800076e7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x1800076ee  test    rax, rax
0x1800076f1  jz      short loc_180007737
0x1800076f3  mov     r8d, 100h
0x1800076f9  lea     rdx, [rsp+288h+Buffer]
0x1800076fe  mov     ecx, ebp
0x180007700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007705  jmp     short loc_180007737
0x180007707  mov     ebp, [rbx+8]
0x18000770a  mov     [rsp+288h+Arguments], r15; Arguments
0x18000770f  mov     [rsp+288h+nSize], 100h; nSize
0x180007717  lea     rax, [rsp+288h+Buffer]
0x18000771c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x180007721  mov     r9d, 400h; dwLanguageId
0x180007727  mov     r8d, ebp; dwMessageId
0x18000772a  xor     edx, edx; lpSource
0x18000772c  mov     ecx, 1200h; dwFlags
0x180007731  call    cs:__imp_FormatMessageW
0x180007737  lea     rsi, [r14+rsi*2]
0x18000773b  mov     r9, [rbx+38h]; wchar_t *
0x18000773f  mov     rax, [rbx+88h]
0x180007746  mov     rcx, [rbx+80h]
0x18000774d  mov     rdx, rsi; wchar_t *
0x180007750  test    r9, r9
0x180007753  jz      short loc_180007777
0x180007755  mov     [rsp+288h+Arguments], rax
0x18000775a  mov     qword ptr [rsp+288h+nSize], rcx
0x18000775f  mov     eax, [rbx+40h]
0x180007762  mov     dword ptr [rsp+288h+lpBuffer], eax
0x180007766  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000776d  mov     rcx, r14; this
0x180007770  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007775  jmp     short loc_18000778E
0x180007777  mov     [rsp+288h+lpBuffer], rax
0x18000777c  mov     r9, rcx; wchar_t *
0x18000777f  lea     r8, aHsP; "%hs!%p: "
0x180007786  mov     rcx, r14; this
0x180007789  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000778e  mov     r14, rax
0x180007791  mov     r9, [rbx+90h]; wchar_t *
0x180007798  test    r9, r9
0x18000779b  jz      short loc_1800077B2
0x18000779d  lea     r8, aCallerP; "(caller: %p) "
0x1800077a4  mov     rdx, rsi; wchar_t *
0x1800077a7  mov     rcx, rax; this
0x1800077aa  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800077af  mov     r14, rax
0x1800077b2  call    cs:__imp_GetCurrentThreadId
0x1800077b8  lea     rcx, [rsp+288h+Buffer]
0x1800077bd  mov     [rsp+288h+var_250], rcx
0x1800077c2  mov     dword ptr [rsp+288h+Arguments], ebp
0x1800077c6  mov     [rsp+288h+nSize], eax
0x1800077ca  mov     eax, [rbx+44h]
0x1800077cd  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1800077d1  mov     r9, rdi; wchar_t *
0x1800077d4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800077db  mov     rdx, rsi; wchar_t *
0x1800077de  mov     rcx, r14; this
0x1800077e1  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1800077e6  cmp     [rbx+18h], r15
0x1800077ea  jnz     short loc_1800077FC
0x1800077ec  cmp     [rbx+48h], r15
0x1800077f0  jnz     short loc_1800077FC
0x1800077f2  cmp     [rbx+30h], r15
0x1800077f6  jz      loc_18000788C
0x1800077fc  lea     r8, asc_180036A60; "    "
0x180007803  mov     rdx, rsi; wchar_t *
0x180007806  mov     rcx, rax; this
0x180007809  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000780e  mov     r9, [rbx+18h]; wchar_t *
0x180007812  test    r9, r9
0x180007815  jz      short loc_180007829
0x180007817  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000781e  mov     rdx, rsi; wchar_t *
0x180007821  mov     rcx, rax; this
0x180007824  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007829  mov     r9, [rbx+48h]; wchar_t *
0x18000782d  test    r9, r9
0x180007830  jz      short loc_180007844
0x180007832  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180007839  mov     rdx, rsi; wchar_t *
0x18000783c  mov     rcx, rax; this
0x18000783f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007844  mov     rcx, [rbx+28h]
0x180007848  mov     r9, [rbx+30h]; wchar_t *
0x18000784c  mov     rdx, rsi; wchar_t *
0x18000784f  test    rcx, rcx
0x180007852  jz      short loc_18000786A
0x180007854  mov     [rsp+288h+lpBuffer], rcx
0x180007859  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007860  mov     rcx, rax; this
0x180007863  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x180007868  jmp     short loc_18000788C
0x18000786a  mov     rcx, rax; this
0x18000786d  test    r9, r9
0x180007870  jz      short loc_180007880
0x180007872  lea     r8, aHs; "[%hs]\n"
0x180007879  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000787e  jmp     short loc_18000788C
0x180007880  lea     r8, asc_180036AD8; "\n"
0x180007887  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x18000788c  xor     eax, eax
0x18000788e  mov     rcx, [rsp+288h+var_38]
0x180007896  xor     rcx, rsp; StackCookie
0x180007899  call    __security_check_cookie
0x18000789e  mov     rbx, [rsp+288h+arg_18]
0x1800078a6  add     rsp, 260h
0x1800078ad  pop     r15
0x1800078af  pop     r14
0x1800078b1  pop     rdi
0x1800078b2  pop     rsi
0x1800078b3  pop     rbp
0x1800078b4  retn
```
