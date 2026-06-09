# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140005304`
- end: `0x1400055c5`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `705`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x140003bc8`
- `0x140003e3c`
- `0x140005d34`
- `0x1400074f0`

## callees

- `0x140002a30`
- `0x14000369c`
- `0x140005304`
- `0x14000603c`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400054c2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400054c2`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005441`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140005441`

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
          v7 = (const char *)&qword_1400150C8;
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
0x140005304  mov     rax, rsp
0x140005307  push    rbp
0x140005308  push    rsi
0x140005309  push    rdi
0x14000530a  push    r14
0x14000530c  push    r15
0x14000530e  sub     rsp, 260h
0x140005315  mov     [rsp+288h+var_248], 0FFFFFFFFFFFFFFFEh
0x14000531e  mov     [rax+20h], rbx
0x140005322  mov     rax, cs:__security_cookie
0x140005329  xor     rax, rsp
0x14000532c  mov     [rsp+288h+var_38], rax
0x140005334  mov     rbx, r8
0x140005337  mov     rsi, rdx
0x14000533a  mov     r14, rcx
0x14000533d  xor     r15d, r15d
0x140005340  test    rdx, rdx
0x140005343  jz      loc_14000559C
0x140005349  test    rcx, rcx
0x14000534c  jz      loc_14000559C
0x140005352  mov     [rcx], r15w
0x140005356  mov     rax, cs:g_pfnResultLoggingCallback
0x14000535d  test    rax, rax
0x140005360  jz      short loc_140005383
0x140005362  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x140005369  jz      short loc_140005383
0x14000536b  mov     r8, rdx
0x14000536e  mov     rdx, rcx
0x140005371  mov     rcx, rbx
0x140005374  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005379  cmp     [r14], r15w
0x14000537d  jnz     loc_14000559C
0x140005383  mov     ecx, [rbx]
0x140005385  mov     bpl, 8
0x140005388  test    ecx, ecx
0x14000538a  jz      short loc_1400053D5
0x14000538c  sub     ecx, 1
0x14000538f  jz      short loc_1400053BD
0x140005391  sub     ecx, 1
0x140005394  jz      short loc_1400053AD
0x140005396  cmp     ecx, 1
0x140005399  jz      short loc_1400053A4
0x14000539b  lea     rdi, qword_1400150C8
0x1400053a2  jmp     short loc_1400053DC
0x1400053a4  lea     rdi, aFailfast; "FailFast"
0x1400053ab  jmp     short loc_1400053DC
0x1400053ad  lea     rax, aLoghr; "LogHr"
0x1400053b4  lea     rdi, aLognt; "LogNt"
0x1400053bb  jmp     short loc_1400053CB
0x1400053bd  lea     rax, aReturnhr; "ReturnHr"
0x1400053c4  lea     rdi, aReturnnt; "ReturnNt"
0x1400053cb  test    [rbx+4], bpl
0x1400053cf  cmovz   rdi, rax
0x1400053d3  jmp     short loc_1400053DC
0x1400053d5  lea     rdi, aException; "Exception"
0x1400053dc  xor     edx, edx; Val
0x1400053de  mov     r8d, 200h; Size
0x1400053e4  lea     rcx, [rsp+288h+Buffer]; void *
0x1400053e9  call    memset_0
0x1400053ee  test    [rbx+4], bpl
0x1400053f2  jz      short loc_140005417
0x1400053f4  mov     ebp, [rbx+0Ch]
0x1400053f7  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400053fe  test    rax, rax
0x140005401  jz      short loc_140005447
0x140005403  mov     r8d, 100h
0x140005409  lea     rdx, [rsp+288h+Buffer]
0x14000540e  mov     ecx, ebp
0x140005410  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005415  jmp     short loc_140005447
0x140005417  mov     ebp, [rbx+8]
0x14000541a  mov     [rsp+288h+Arguments], r15; Arguments
0x14000541f  mov     [rsp+288h+nSize], 100h; nSize
0x140005427  lea     rax, [rsp+288h+Buffer]
0x14000542c  mov     [rsp+288h+lpBuffer], rax; lpBuffer
0x140005431  mov     r9d, 400h; dwLanguageId
0x140005437  mov     r8d, ebp; dwMessageId
0x14000543a  xor     edx, edx; lpSource
0x14000543c  mov     ecx, 1200h; dwFlags
0x140005441  call    cs:__imp_FormatMessageW
0x140005447  lea     rsi, [r14+rsi*2]
0x14000544b  mov     r9, [rbx+38h]; unsigned __int16 *
0x14000544f  mov     rax, [rbx+88h]
0x140005456  mov     rcx, [rbx+80h]
0x14000545d  mov     rdx, rsi; unsigned __int16 *
0x140005460  test    r9, r9
0x140005463  jz      short loc_140005487
0x140005465  mov     [rsp+288h+Arguments], rax
0x14000546a  mov     qword ptr [rsp+288h+nSize], rcx
0x14000546f  mov     eax, [rbx+40h]
0x140005472  mov     dword ptr [rsp+288h+lpBuffer], eax
0x140005476  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x14000547d  mov     rcx, r14; this
0x140005480  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005485  jmp     short loc_14000549E
0x140005487  mov     [rsp+288h+lpBuffer], rax
0x14000548c  mov     r9, rcx; unsigned __int16 *
0x14000548f  lea     r8, aHsP; "%hs!%p: "
0x140005496  mov     rcx, r14; this
0x140005499  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000549e  mov     r14, rax
0x1400054a1  mov     r9, [rbx+90h]; unsigned __int16 *
0x1400054a8  test    r9, r9
0x1400054ab  jz      short loc_1400054C2
0x1400054ad  lea     r8, aCallerP; "(caller: %p) "
0x1400054b4  mov     rdx, rsi; unsigned __int16 *
0x1400054b7  mov     rcx, rax; this
0x1400054ba  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400054bf  mov     r14, rax
0x1400054c2  call    cs:__imp_GetCurrentThreadId
0x1400054c8  lea     rcx, [rsp+288h+Buffer]
0x1400054cd  mov     [rsp+288h+var_250], rcx
0x1400054d2  mov     dword ptr [rsp+288h+Arguments], ebp
0x1400054d6  mov     [rsp+288h+nSize], eax
0x1400054da  mov     eax, [rbx+44h]
0x1400054dd  mov     dword ptr [rsp+288h+lpBuffer], eax
0x1400054e1  mov     r9, rdi; unsigned __int16 *
0x1400054e4  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400054eb  mov     rdx, rsi; unsigned __int16 *
0x1400054ee  mov     rcx, r14; this
0x1400054f1  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400054f6  cmp     [rbx+18h], r15
0x1400054fa  jnz     short loc_14000550C
0x1400054fc  cmp     [rbx+48h], r15
0x140005500  jnz     short loc_14000550C
0x140005502  cmp     [rbx+30h], r15
0x140005506  jz      loc_14000559C
0x14000550c  lea     r8, asc_1400151F8; "    "
0x140005513  mov     rdx, rsi; unsigned __int16 *
0x140005516  mov     rcx, rax; this
0x140005519  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000551e  mov     r9, [rbx+18h]; unsigned __int16 *
0x140005522  test    r9, r9
0x140005525  jz      short loc_140005539
0x140005527  lea     r8, aMsgWs; "Msg:[%ws] "
0x14000552e  mov     rdx, rsi; unsigned __int16 *
0x140005531  mov     rcx, rax; this
0x140005534  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005539  mov     r9, [rbx+48h]; unsigned __int16 *
0x14000553d  test    r9, r9
0x140005540  jz      short loc_140005554
0x140005542  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x140005549  mov     rdx, rsi; unsigned __int16 *
0x14000554c  mov     rcx, rax; this
0x14000554f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005554  mov     rcx, [rbx+28h]
0x140005558  mov     r9, [rbx+30h]; unsigned __int16 *
0x14000555c  mov     rdx, rsi; unsigned __int16 *
0x14000555f  test    rcx, rcx
0x140005562  jz      short loc_14000557A
0x140005564  mov     [rsp+288h+lpBuffer], rcx
0x140005569  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140005570  mov     rcx, rax; this
0x140005573  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140005578  jmp     short loc_14000559C
0x14000557a  mov     rcx, rax; this
0x14000557d  test    r9, r9
0x140005580  jz      short loc_140005590
0x140005582  lea     r8, aHs; "[%hs]\n"
0x140005589  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000558e  jmp     short loc_14000559C
0x140005590  lea     r8, asc_140015270; "\n"
0x140005597  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000559c  xor     eax, eax
0x14000559e  mov     rcx, [rsp+288h+var_38]
0x1400055a6  xor     rcx, rsp; StackCookie
0x1400055a9  call    __security_check_cookie
0x1400055ae  mov     rbx, [rsp+288h+arg_18]
0x1400055b6  add     rsp, 260h
0x1400055bd  pop     r15
0x1400055bf  pop     r14
0x1400055c1  pop     rdi
0x1400055c2  pop     rsi
0x1400055c3  pop     rbp
0x1400055c4  retn
```
