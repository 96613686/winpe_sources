# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x180008444`
- end: `0x1800086fa`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *__hidden this, unsigned __int16 *, unsigned __int64, const struct wil::FailureInfo *)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x180007414`
- `0x180008e5c`
- `0x180009310`
- `0x18000a5d0`
- `0x18000bcbc`

## callees

- `0x180003ed0`
- `0x180004a70`
- `0x180008444`
- `0x180009160`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800085f7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008576`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180008576`

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
          v7 = (const char *)&qword_180098990;
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
0x180008444  mov     [rsp+arg_18], rbx
0x180008449  push    rbp
0x18000844a  push    rsi
0x18000844b  push    rdi
0x18000844c  push    r14
0x18000844e  push    r15
0x180008450  sub     rsp, 250h
0x180008457  mov     rax, cs:__security_cookie
0x18000845e  xor     rax, rsp
0x180008461  mov     [rsp+278h+var_38], rax
0x180008469  mov     rbx, r8
0x18000846c  mov     rsi, rdx
0x18000846f  mov     r14, rcx
0x180008472  xor     r15d, r15d
0x180008475  test    rdx, rdx
0x180008478  jz      loc_1800086D1
0x18000847e  test    rcx, rcx
0x180008481  jz      loc_1800086D1
0x180008487  mov     [rcx], r15w
0x18000848b  mov     rax, cs:g_pfnResultLoggingCallback
0x180008492  test    rax, rax
0x180008495  jz      short loc_1800084B8
0x180008497  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000849e  jz      short loc_1800084B8
0x1800084a0  mov     r8, rdx
0x1800084a3  mov     rdx, rcx
0x1800084a6  mov     rcx, rbx
0x1800084a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084ae  cmp     [r14], r15w
0x1800084b2  jnz     loc_1800086D1
0x1800084b8  mov     ecx, [rbx]
0x1800084ba  mov     bpl, 8
0x1800084bd  test    ecx, ecx
0x1800084bf  jz      short loc_18000850A
0x1800084c1  sub     ecx, 1
0x1800084c4  jz      short loc_1800084F2
0x1800084c6  sub     ecx, 1
0x1800084c9  jz      short loc_1800084E2
0x1800084cb  cmp     ecx, 1
0x1800084ce  jz      short loc_1800084D9
0x1800084d0  lea     rdi, qword_180098990
0x1800084d7  jmp     short loc_180008511
0x1800084d9  lea     rdi, aFailfast; "FailFast"
0x1800084e0  jmp     short loc_180008511
0x1800084e2  lea     rax, aLoghr; "LogHr"
0x1800084e9  lea     rdi, aLognt; "LogNt"
0x1800084f0  jmp     short loc_180008500
0x1800084f2  lea     rax, aReturnhr; "ReturnHr"
0x1800084f9  lea     rdi, aReturnnt; "ReturnNt"
0x180008500  test    [rbx+4], bpl
0x180008504  cmovz   rdi, rax
0x180008508  jmp     short loc_180008511
0x18000850a  lea     rdi, aException; "Exception"
0x180008511  xor     edx, edx; Val
0x180008513  mov     r8d, 200h; Size
0x180008519  lea     rcx, [rsp+278h+Buffer]; void *
0x18000851e  call    memset_0
0x180008523  test    [rbx+4], bpl
0x180008527  jz      short loc_18000854C
0x180008529  mov     ebp, [rbx+0Ch]
0x18000852c  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x180008533  test    rax, rax
0x180008536  jz      short loc_18000857C
0x180008538  mov     r8d, 100h
0x18000853e  lea     rdx, [rsp+278h+Buffer]
0x180008543  mov     ecx, ebp
0x180008545  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000854a  jmp     short loc_18000857C
0x18000854c  mov     ebp, [rbx+8]
0x18000854f  mov     [rsp+278h+Arguments], r15; Arguments
0x180008554  mov     [rsp+278h+nSize], 100h; nSize
0x18000855c  lea     rax, [rsp+278h+Buffer]
0x180008561  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180008566  mov     r9d, 400h; dwLanguageId
0x18000856c  mov     r8d, ebp; dwMessageId
0x18000856f  xor     edx, edx; lpSource
0x180008571  mov     ecx, 1200h; dwFlags
0x180008576  call    cs:__imp_FormatMessageW
0x18000857c  lea     rsi, [r14+rsi*2]
0x180008580  mov     r9, [rbx+38h]; unsigned __int16 *
0x180008584  mov     rax, [rbx+88h]
0x18000858b  mov     rcx, [rbx+80h]
0x180008592  mov     rdx, rsi; unsigned __int16 *
0x180008595  test    r9, r9
0x180008598  jz      short loc_1800085BC
0x18000859a  mov     [rsp+278h+Arguments], rax
0x18000859f  mov     qword ptr [rsp+278h+nSize], rcx
0x1800085a4  mov     eax, [rbx+40h]
0x1800085a7  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800085ab  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x1800085b2  mov     rcx, r14; this
0x1800085b5  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800085ba  jmp     short loc_1800085D3
0x1800085bc  mov     [rsp+278h+lpBuffer], rax
0x1800085c1  mov     r9, rcx; unsigned __int16 *
0x1800085c4  lea     r8, aHsP; "%hs!%p: "
0x1800085cb  mov     rcx, r14; this
0x1800085ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800085d3  mov     r14, rax
0x1800085d6  mov     r9, [rbx+90h]; unsigned __int16 *
0x1800085dd  test    r9, r9
0x1800085e0  jz      short loc_1800085F7
0x1800085e2  lea     r8, aCallerP; "(caller: %p) "
0x1800085e9  mov     rdx, rsi; unsigned __int16 *
0x1800085ec  mov     rcx, rax; this
0x1800085ef  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800085f4  mov     r14, rax
0x1800085f7  call    cs:__imp_GetCurrentThreadId
0x1800085fd  lea     rcx, [rsp+278h+Buffer]
0x180008602  mov     [rsp+278h+var_240], rcx
0x180008607  mov     dword ptr [rsp+278h+Arguments], ebp
0x18000860b  mov     [rsp+278h+nSize], eax
0x18000860f  mov     eax, [rbx+44h]
0x180008612  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180008616  mov     r9, rdi; unsigned __int16 *
0x180008619  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x180008620  mov     rdx, rsi; unsigned __int16 *
0x180008623  mov     rcx, r14; this
0x180008626  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000862b  cmp     [rbx+18h], r15
0x18000862f  jnz     short loc_180008641
0x180008631  cmp     [rbx+48h], r15
0x180008635  jnz     short loc_180008641
0x180008637  cmp     [rbx+30h], r15
0x18000863b  jz      loc_1800086D1
0x180008641  lea     r8, asc_180098A98; "    "
0x180008648  mov     rdx, rsi; unsigned __int16 *
0x18000864b  mov     rcx, rax; this
0x18000864e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008653  mov     r9, [rbx+18h]; unsigned __int16 *
0x180008657  test    r9, r9
0x18000865a  jz      short loc_18000866E
0x18000865c  lea     r8, aMsgWs; "Msg:[%ws] "
0x180008663  mov     rdx, rsi; unsigned __int16 *
0x180008666  mov     rcx, rax; this
0x180008669  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000866e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180008672  test    r9, r9
0x180008675  jz      short loc_180008689
0x180008677  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000867e  mov     rdx, rsi; unsigned __int16 *
0x180008681  mov     rcx, rax; this
0x180008684  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180008689  mov     rcx, [rbx+28h]
0x18000868d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180008691  mov     rdx, rsi; unsigned __int16 *
0x180008694  test    rcx, rcx
0x180008697  jz      short loc_1800086AF
0x180008699  mov     [rsp+278h+lpBuffer], rcx
0x18000869e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x1800086a5  mov     rcx, rax; this
0x1800086a8  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800086ad  jmp     short loc_1800086D1
0x1800086af  mov     rcx, rax; this
0x1800086b2  test    r9, r9
0x1800086b5  jz      short loc_1800086C5
0x1800086b7  lea     r8, aHs; "[%hs]\n"
0x1800086be  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800086c3  jmp     short loc_1800086D1
0x1800086c5  lea     r8, asc_180098B10; "\n"
0x1800086cc  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800086d1  xor     eax, eax
0x1800086d3  mov     rcx, [rsp+278h+var_38]
0x1800086db  xor     rcx, rsp; StackCookie
0x1800086de  call    __security_check_cookie
0x1800086e3  mov     rbx, [rsp+278h+arg_18]
0x1800086eb  add     rsp, 250h
0x1800086f2  pop     r15
0x1800086f4  pop     r14
0x1800086f6  pop     rdi
0x1800086f7  pop     rsi
0x1800086f8  pop     rbp
0x1800086f9  retn
```
