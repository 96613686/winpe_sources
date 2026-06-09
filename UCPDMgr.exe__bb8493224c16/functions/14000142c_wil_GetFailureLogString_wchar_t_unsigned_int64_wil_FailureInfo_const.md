# wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x14000142c`
- end: `0x1400016e0`
- name: `?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z`
- size: `692`
- prototype: `__int64 __fastcall(wil *this, wchar_t *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140002340`
- `0x1400026e0`
- `0x140004778`
- `0x140004d94`

## callees

- `0x1400013a8`
- `0x14000142c`
- `0x14000a390`
- `0x14000f4d0`
- `0x14000f550`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400015dd`
- `KERNEL32!GetCurrentThreadId` at `0x1400015dd`
- `KERNEL32!FormatMessageW` at `0x14000155c`
- `KERNEL32!FormatMessageW` at `0x14000155c`

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
      g_pfnResultLoggingCallback(a3, this, a2);
      if ( *(_WORD *)this )
        return 0;
    }
  }
  v7 = (const char *)&word_14001169E;
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
0x14000142c  mov     [rsp+arg_18], rbx
0x140001431  push    rbp
0x140001432  push    rsi
0x140001433  push    rdi
0x140001434  push    r14
0x140001436  push    r15
0x140001438  sub     rsp, 250h
0x14000143f  mov     rax, cs:__security_cookie
0x140001446  xor     rax, rsp
0x140001449  mov     [rsp+278h+var_38], rax
0x140001451  mov     rbx, r8
0x140001454  mov     rdi, rdx
0x140001457  mov     r14, rcx
0x14000145a  xor     r15d, r15d
0x14000145d  test    rdx, rdx
0x140001460  jz      loc_1400016B7
0x140001466  test    rcx, rcx
0x140001469  jz      loc_1400016B7
0x14000146f  mov     [rcx], r15w
0x140001473  mov     rax, cs:g_pfnResultLoggingCallback
0x14000147a  test    rax, rax
0x14000147d  jz      short loc_1400014A0
0x14000147f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140001486  jz      short loc_1400014A0
0x140001488  mov     r8, rdx
0x14000148b  mov     rdx, rcx
0x14000148e  mov     rcx, rbx
0x140001491  call    _guard_dispatch_icall
0x140001496  cmp     [r14], r15w
0x14000149a  jnz     loc_1400016B7
0x1400014a0  lea     rsi, word_14001169E
0x1400014a7  mov     ecx, [rbx]
0x1400014a9  mov     bpl, 8
0x1400014ac  test    ecx, ecx
0x1400014ae  jz      short loc_1400014F0
0x1400014b0  sub     ecx, 1
0x1400014b3  jz      short loc_1400014D8
0x1400014b5  sub     ecx, 1
0x1400014b8  jz      short loc_1400014C8
0x1400014ba  cmp     ecx, 1
0x1400014bd  jnz     short loc_1400014F7
0x1400014bf  lea     rsi, aFailfast; "FailFast"
0x1400014c6  jmp     short loc_1400014F7
0x1400014c8  lea     rax, aLoghr; "LogHr"
0x1400014cf  lea     rsi, aLognt; "LogNt"
0x1400014d6  jmp     short loc_1400014E6
0x1400014d8  lea     rax, aReturnhr; "ReturnHr"
0x1400014df  lea     rsi, aReturnnt; "ReturnNt"
0x1400014e6  test    [rbx+4], bpl
0x1400014ea  cmovz   rsi, rax
0x1400014ee  jmp     short loc_1400014F7
0x1400014f0  lea     rsi, aException; "Exception"
0x1400014f7  xor     edx, edx; Val
0x1400014f9  mov     r8d, 200h; Size
0x1400014ff  lea     rcx, [rsp+278h+Buffer]; void *
0x140001504  call    memset
0x140001509  test    [rbx+4], bpl
0x14000150d  jz      short loc_140001532
0x14000150f  mov     ebp, [rbx+0Ch]
0x140001512  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEA_WK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,wchar_t *,ulong)
0x140001519  test    rax, rax
0x14000151c  jz      short loc_140001562
0x14000151e  mov     r8d, 100h
0x140001524  lea     rdx, [rsp+278h+Buffer]
0x140001529  mov     ecx, ebp
0x14000152b  call    _guard_dispatch_icall
0x140001530  jmp     short loc_140001562
0x140001532  mov     ebp, [rbx+8]
0x140001535  mov     [rsp+278h+Arguments], r15; Arguments
0x14000153a  mov     [rsp+278h+nSize], 100h; nSize
0x140001542  lea     rax, [rsp+278h+Buffer]
0x140001547  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x14000154c  mov     r9d, 400h; dwLanguageId
0x140001552  mov     r8d, ebp; dwMessageId
0x140001555  xor     edx, edx; lpSource
0x140001557  mov     ecx, 1200h; dwFlags
0x14000155c  call    cs:__imp_FormatMessageW
0x140001562  lea     rdi, [r14+rdi*2]
0x140001566  mov     r9, [rbx+38h]; wchar_t *
0x14000156a  mov     rax, [rbx+88h]
0x140001571  mov     rcx, [rbx+80h]
0x140001578  mov     rdx, rdi; wchar_t *
0x14000157b  test    r9, r9
0x14000157e  jz      short loc_1400015A2
0x140001580  mov     [rsp+278h+Arguments], rax
0x140001585  mov     qword ptr [rsp+278h+nSize], rcx
0x14000158a  mov     eax, [rbx+40h]
0x14000158d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140001591  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140001598  mov     rcx, r14; this
0x14000159b  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400015a0  jmp     short loc_1400015B9
0x1400015a2  mov     [rsp+278h+lpBuffer], rax
0x1400015a7  mov     r9, rcx; wchar_t *
0x1400015aa  lea     r8, aHsP; "%hs!%p: "
0x1400015b1  mov     rcx, r14; this
0x1400015b4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400015b9  mov     r14, rax
0x1400015bc  mov     r9, [rbx+90h]; wchar_t *
0x1400015c3  test    r9, r9
0x1400015c6  jz      short loc_1400015DD
0x1400015c8  lea     r8, aCallerP; "(caller: %p) "
0x1400015cf  mov     rdx, rdi; wchar_t *
0x1400015d2  mov     rcx, rax; this
0x1400015d5  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400015da  mov     r14, rax
0x1400015dd  call    cs:__imp_GetCurrentThreadId
0x1400015e3  lea     rcx, [rsp+278h+Buffer]
0x1400015e8  mov     [rsp+278h+var_240], rcx
0x1400015ed  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400015f1  mov     [rsp+278h+nSize], eax
0x1400015f5  mov     eax, [rbx+44h]
0x1400015f8  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400015fc  mov     r9, rsi; wchar_t *
0x1400015ff  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x140001606  mov     rdx, rdi; wchar_t *
0x140001609  mov     rcx, r14; this
0x14000160c  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140001611  cmp     [rbx+18h], r15
0x140001615  jnz     short loc_140001627
0x140001617  cmp     [rbx+48h], r15
0x14000161b  jnz     short loc_140001627
0x14000161d  cmp     [rbx+30h], r15
0x140001621  jz      loc_1400016B7
0x140001627  lea     r8, asc_1400117A0; "    "
0x14000162e  mov     rdx, rdi; wchar_t *
0x140001631  mov     rcx, rax; this
0x140001634  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140001639  mov     r9, [rbx+18h]; wchar_t *
0x14000163d  test    r9, r9
0x140001640  jz      short loc_140001654
0x140001642  lea     r8, aMsgWs; "Msg:[%ws] "
0x140001649  mov     rdx, rdi; wchar_t *
0x14000164c  mov     rcx, rax; this
0x14000164f  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140001654  mov     r9, [rbx+48h]; wchar_t *
0x140001658  test    r9, r9
0x14000165b  jz      short loc_14000166F
0x14000165d  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140001664  mov     rdx, rdi; wchar_t *
0x140001667  mov     rcx, rax; this
0x14000166a  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x14000166f  mov     rcx, [rbx+28h]
0x140001673  mov     r9, [rbx+30h]; wchar_t *
0x140001677  mov     rdx, rdi; wchar_t *
0x14000167a  test    rcx, rcx
0x14000167d  jz      short loc_140001695
0x14000167f  mov     [rsp+278h+lpBuffer], rcx
0x140001684  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x14000168b  mov     rcx, rax; this
0x14000168e  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x140001693  jmp     short loc_1400016B7
0x140001695  mov     rcx, rax; this
0x140001698  test    r9, r9
0x14000169b  jz      short loc_1400016AB
0x14000169d  lea     r8, aHs; "[%hs]\n"
0x1400016a4  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400016a9  jmp     short loc_1400016B7
0x1400016ab  lea     r8, asc_140011818; "\n"
0x1400016b2  call    ?LogStringPrintf@details@wil@@YAPEA_WPEA_WPEB_W1ZZ; wil::details::LogStringPrintf(wchar_t *,wchar_t const *,wchar_t const *,...)
0x1400016b7  xor     eax, eax
0x1400016b9  mov     rcx, [rsp+278h+var_38]
0x1400016c1  xor     rcx, rsp; StackCookie
0x1400016c4  call    __security_check_cookie
0x1400016c9  mov     rbx, [rsp+278h+arg_18]
0x1400016d1  add     rsp, 250h
0x1400016d8  pop     r15
0x1400016da  pop     r14
0x1400016dc  pop     rdi
0x1400016dd  pop     rsi
0x1400016de  pop     rbp
0x1400016df  retn
```
