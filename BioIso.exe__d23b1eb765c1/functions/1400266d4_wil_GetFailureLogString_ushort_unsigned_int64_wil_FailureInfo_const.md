# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1400266d4`
- end: `0x140026997`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `707`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x14000a5b8`
- `0x1400273e8`
- `0x140029920`

## callees

- `0x14001bd40`
- `0x14001cb90`
- `0x1400266d4`
- `0x140027064`
- `0x140085010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002688d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14002688d`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140026806`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140026806`

## pseudocode

```c
// Hidden C++ exception states: #wind=3 #try_helpers=1
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
          v7 = (const char *)&word_14008BBFE;
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
0x1400266d4  mov     [rsp+arg_18], rbx
0x1400266d9  push    rbp
0x1400266da  push    rsi
0x1400266db  push    rdi
0x1400266dc  push    r14
0x1400266de  push    r15
0x1400266e0  sub     rsp, 250h
0x1400266e7  mov     rax, cs:__security_cookie
0x1400266ee  xor     rax, rsp
0x1400266f1  mov     [rsp+278h+var_38], rax
0x1400266f9  mov     rbx, r8
0x1400266fc  mov     rsi, rdx
0x1400266ff  mov     r14, rcx
0x140026702  xor     r15d, r15d
0x140026705  test    rdx, rdx
0x140026708  jz      loc_14002696D
0x14002670e  test    rcx, rcx
0x140026711  jz      loc_14002696D
0x140026717  mov     [rcx], r15w
0x14002671b  mov     rax, cs:g_pfnResultLoggingCallback
0x140026722  test    rax, rax
0x140026725  jz      short loc_140026748
0x140026727  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14002672e  jz      short loc_140026748
0x140026730  mov     r8, rdx
0x140026733  mov     rdx, rcx
0x140026736  mov     rcx, rbx
0x140026739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14002673e  cmp     [r14], r15w
0x140026742  jnz     loc_14002696D
0x140026748  mov     ecx, [rbx]
0x14002674a  mov     bpl, 8
0x14002674d  test    ecx, ecx
0x14002674f  jz      short loc_14002679A
0x140026751  sub     ecx, 1
0x140026754  jz      short loc_140026782
0x140026756  sub     ecx, 1
0x140026759  jz      short loc_140026772
0x14002675b  cmp     ecx, 1
0x14002675e  jz      short loc_140026769
0x140026760  lea     rdi, word_14008BBFE
0x140026767  jmp     short loc_1400267A1
0x140026769  lea     rdi, aFailfast; "FailFast"
0x140026770  jmp     short loc_1400267A1
0x140026772  lea     rax, aLoghr; "LogHr"
0x140026779  lea     rdi, aLognt; "LogNt"
0x140026780  jmp     short loc_140026790
0x140026782  lea     rax, aReturnhr; "ReturnHr"
0x140026789  lea     rdi, aReturnnt; "ReturnNt"
0x140026790  test    [rbx+4], bpl
0x140026794  cmovz   rdi, rax
0x140026798  jmp     short loc_1400267A1
0x14002679a  lea     rdi, aException; "Exception"
0x1400267a1  xor     edx, edx; Val
0x1400267a3  mov     r8d, 200h; Size
0x1400267a9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400267ae  call    memset_0
0x1400267b3  test    [rbx+4], bpl
0x1400267b7  jz      short loc_1400267DC
0x1400267b9  mov     ebp, [rbx+0Ch]
0x1400267bc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400267c3  test    rax, rax
0x1400267c6  jz      short loc_140026812
0x1400267c8  mov     r8d, 100h
0x1400267ce  lea     rdx, [rsp+278h+Buffer]
0x1400267d3  mov     ecx, ebp
0x1400267d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400267da  jmp     short loc_140026812
0x1400267dc  mov     ebp, [rbx+8]
0x1400267df  mov     [rsp+278h+Arguments], r15; Arguments
0x1400267e4  mov     [rsp+278h+nSize], 100h; nSize
0x1400267ec  lea     rax, [rsp+278h+Buffer]
0x1400267f1  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x1400267f6  mov     r9d, 400h; dwLanguageId
0x1400267fc  mov     r8d, ebp; dwMessageId
0x1400267ff  xor     edx, edx; lpSource
0x140026801  mov     ecx, 1200h; dwFlags
0x140026806  call    cs:__imp_FormatMessageW
0x14002680d  nop     dword ptr [rax+rax+00h]
0x140026812  lea     rsi, [r14+rsi*2]
0x140026816  mov     r9, [rbx+38h]; unsigned __int16 *
0x14002681a  mov     rax, [rbx+88h]
0x140026821  mov     rcx, [rbx+80h]
0x140026828  mov     rdx, rsi; unsigned __int16 *
0x14002682b  test    r9, r9
0x14002682e  jz      short loc_140026852
0x140026830  mov     [rsp+278h+Arguments], rax
0x140026835  mov     qword ptr [rsp+278h+nSize], rcx
0x14002683a  mov     eax, [rbx+40h]
0x14002683d  mov     dword ptr [rsp+278h+lpBuffer], eax
0x140026841  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140026848  mov     rcx, r14; this
0x14002684b  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140026850  jmp     short loc_140026869
0x140026852  mov     [rsp+278h+lpBuffer], rax
0x140026857  mov     r9, rcx; unsigned __int16 *
0x14002685a  lea     r8, aHsP; "%hs!%p: "
0x140026861  mov     rcx, r14; this
0x140026864  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140026869  mov     r14, rax
0x14002686c  mov     r9, [rbx+90h]; unsigned __int16 *
0x140026873  test    r9, r9
0x140026876  jz      short loc_14002688D
0x140026878  lea     r8, aCallerP; "(caller: %p) "
0x14002687f  mov     rdx, rsi; unsigned __int16 *
0x140026882  mov     rcx, rax; this
0x140026885  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002688a  mov     r14, rax
0x14002688d  call    cs:__imp_GetCurrentThreadId
0x140026894  nop     dword ptr [rax+rax+00h]
0x140026899  lea     rcx, [rsp+278h+Buffer]
0x14002689e  mov     [rsp+278h+var_240], rcx
0x1400268a3  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400268a7  mov     [rsp+278h+nSize], eax
0x1400268ab  mov     eax, [rbx+44h]
0x1400268ae  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400268b2  mov     r9, rdi; unsigned __int16 *
0x1400268b5  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400268bc  mov     rdx, rsi; unsigned __int16 *
0x1400268bf  mov     rcx, r14; this
0x1400268c2  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400268c7  cmp     [rbx+18h], r15
0x1400268cb  jnz     short loc_1400268DD
0x1400268cd  cmp     [rbx+48h], r15
0x1400268d1  jnz     short loc_1400268DD
0x1400268d3  cmp     [rbx+30h], r15
0x1400268d7  jz      loc_14002696D
0x1400268dd  lea     r8, asc_14008BED8; "    "
0x1400268e4  mov     rdx, rsi; unsigned __int16 *
0x1400268e7  mov     rcx, rax; this
0x1400268ea  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400268ef  mov     r9, [rbx+18h]; unsigned __int16 *
0x1400268f3  test    r9, r9
0x1400268f6  jz      short loc_14002690A
0x1400268f8  lea     r8, aMsgWs; "Msg:[%ws] "
0x1400268ff  mov     rdx, rsi; unsigned __int16 *
0x140026902  mov     rcx, rax; this
0x140026905  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002690a  mov     r9, [rbx+48h]; unsigned __int16 *
0x14002690e  test    r9, r9
0x140026911  jz      short loc_140026925
0x140026913  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14002691a  mov     rdx, rsi; unsigned __int16 *
0x14002691d  mov     rcx, rax; this
0x140026920  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140026925  mov     rcx, [rbx+28h]
0x140026929  mov     r9, [rbx+30h]; unsigned __int16 *
0x14002692d  mov     rdx, rsi; unsigned __int16 *
0x140026930  test    rcx, rcx
0x140026933  jz      short loc_14002694B
0x140026935  mov     [rsp+278h+lpBuffer], rcx
0x14002693a  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140026941  mov     rcx, rax; this
0x140026944  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140026949  jmp     short loc_14002696D
0x14002694b  mov     rcx, rax; this
0x14002694e  test    r9, r9
0x140026951  jz      short loc_140026961
0x140026953  lea     r8, aHs; "[%hs]\n"
0x14002695a  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002695f  jmp     short loc_14002696D
0x140026961  lea     r8, asc_14008BF50; "\n"
0x140026968  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14002696d  xor     eax, eax
0x14002696f  mov     rcx, [rsp+278h+var_38]
0x140026977  xor     rcx, rsp; StackCookie
0x14002697a  call    __security_check_cookie
0x14002697f  mov     rbx, [rsp+278h+arg_18]
0x140026987  add     rsp, 250h
0x14002698e  pop     r15
0x140026990  pop     r14
0x140026992  pop     rdi
0x140026993  pop     rsi
0x140026994  pop     rbp
0x140026995  retn
```
