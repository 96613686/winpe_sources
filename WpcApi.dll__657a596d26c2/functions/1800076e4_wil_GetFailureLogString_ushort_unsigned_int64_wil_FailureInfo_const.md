# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800076e4`
- end: `0x18000799a`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `7`
- callee_count: `5`
- tags: ``

## callers

- `0x180005284`
- `0x180005504`
- `0x180008608`
- `0x18000abe0`
- `0x18000e77c`
- `0x1800292ae`
- `0x1800293e2`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x1800076e4`
- `0x180008908`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007897`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007897`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007816`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x180007816`

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
          v7 = (const char *)&dword_1800320C4;
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
0x1800076e4  mov     [rsp+arg_18], rbx
0x1800076e9  push    rbp
0x1800076ea  push    rsi
0x1800076eb  push    rdi
0x1800076ec  push    r14
0x1800076ee  push    r15
0x1800076f0  sub     rsp, 250h
0x1800076f7  mov     rax, cs:__security_cookie
0x1800076fe  xor     rax, rsp
0x180007701  mov     [rsp+278h+var_38], rax
0x180007709  mov     rbx, r8
0x18000770c  mov     rsi, rdx
0x18000770f  mov     r14, rcx
0x180007712  xor     r15d, r15d
0x180007715  test    rdx, rdx
0x180007718  jz      loc_180007971
0x18000771e  test    rcx, rcx
0x180007721  jz      loc_180007971
0x180007727  mov     [rcx], r15w
0x18000772b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007732  test    rax, rax
0x180007735  jz      short loc_180007758
0x180007737  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000773e  jz      short loc_180007758
0x180007740  mov     r8, rdx
0x180007743  mov     rdx, rcx
0x180007746  mov     rcx, rbx
0x180007749  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000774e  cmp     [r14], r15w
0x180007752  jnz     loc_180007971
0x180007758  mov     ecx, [rbx]
0x18000775a  mov     bpl, 8
0x18000775d  test    ecx, ecx
0x18000775f  jz      short loc_1800077AA
0x180007761  sub     ecx, 1
0x180007764  jz      short loc_180007792
0x180007766  sub     ecx, 1
0x180007769  jz      short loc_180007782
0x18000776b  cmp     ecx, 1
0x18000776e  jz      short loc_180007779
0x180007770  lea     rdi, dword_1800320C4
0x180007777  jmp     short loc_1800077B1
0x180007779  lea     rdi, aFailfast; "FailFast"
0x180007780  jmp     short loc_1800077B1
0x180007782  lea     rax, aLoghr; "LogHr"
0x180007789  lea     rdi, aLognt; "LogNt"
0x180007790  jmp     short loc_1800077A0
0x180007792  lea     rax, aReturnhr; "ReturnHr"
0x180007799  lea     rdi, aReturnnt; "ReturnNt"
0x1800077a0  test    [rbx+4], bpl
0x1800077a4  cmovz   rdi, rax
0x1800077a8  jmp     short loc_1800077B1
0x1800077aa  lea     rdi, aException; "Exception"
0x1800077b1  xor     edx, edx; Val
0x1800077b3  mov     r8d, 200h; Size
0x1800077b9  lea     rcx, [rsp+278h+Buffer]; void *
0x1800077be  call    memset_0
0x1800077c3  test    [rbx+4], bpl
0x1800077c7  jz      short loc_1800077EC
0x1800077c9  mov     ebp, [rbx+0Ch]
0x1800077cc  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800077d3  test    rax, rax
0x1800077d6  jz      short loc_18000781C
0x1800077d8  mov     r8d, 100h
0x1800077de  lea     rdx, [rsp+278h+Buffer]
0x1800077e3  mov     ecx, ebp
0x1800077e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800077ea  jmp     short loc_18000781C
0x1800077ec  mov     ebp, [rbx+8]
0x1800077ef  mov     [rsp+278h+Arguments], r15; Arguments
0x1800077f4  mov     [rsp+278h+nSize], 100h; nSize
0x1800077fc  lea     rax, [rsp+278h+Buffer]
0x180007801  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x180007806  mov     r9d, 400h; dwLanguageId
0x18000780c  mov     r8d, ebp; dwMessageId
0x18000780f  xor     edx, edx; lpSource
0x180007811  mov     ecx, 1200h; dwFlags
0x180007816  call    cs:__imp_FormatMessageW
0x18000781c  lea     rsi, [r14+rsi*2]
0x180007820  mov     r9, [rbx+38h]; unsigned __int16 *
0x180007824  mov     rax, [rbx+88h]
0x18000782b  mov     rcx, [rbx+80h]
0x180007832  mov     rdx, rsi; unsigned __int16 *
0x180007835  test    r9, r9
0x180007838  jz      short loc_18000785C
0x18000783a  mov     [rsp+278h+Arguments], rax
0x18000783f  mov     qword ptr [rsp+278h+nSize], rcx
0x180007844  mov     eax, [rbx+40h]
0x180007847  mov     dword ptr [rsp+278h+lpBuffer], eax
0x18000784b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x180007852  mov     rcx, r14; this
0x180007855  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000785a  jmp     short loc_180007873
0x18000785c  mov     [rsp+278h+lpBuffer], rax
0x180007861  mov     r9, rcx; unsigned __int16 *
0x180007864  lea     r8, aHsP; "%hs!%p: "
0x18000786b  mov     rcx, r14; this
0x18000786e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007873  mov     r14, rax
0x180007876  mov     r9, [rbx+90h]; unsigned __int16 *
0x18000787d  test    r9, r9
0x180007880  jz      short loc_180007897
0x180007882  lea     r8, aCallerP; "(caller: %p) "
0x180007889  mov     rdx, rsi; unsigned __int16 *
0x18000788c  mov     rcx, rax; this
0x18000788f  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007894  mov     r14, rax
0x180007897  call    cs:__imp_GetCurrentThreadId
0x18000789d  lea     rcx, [rsp+278h+Buffer]
0x1800078a2  mov     [rsp+278h+var_240], rcx
0x1800078a7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800078ab  mov     [rsp+278h+nSize], eax
0x1800078af  mov     eax, [rbx+44h]
0x1800078b2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800078b6  mov     r9, rdi; unsigned __int16 *
0x1800078b9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800078c0  mov     rdx, rsi; unsigned __int16 *
0x1800078c3  mov     rcx, r14; this
0x1800078c6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800078cb  cmp     [rbx+18h], r15
0x1800078cf  jnz     short loc_1800078E1
0x1800078d1  cmp     [rbx+48h], r15
0x1800078d5  jnz     short loc_1800078E1
0x1800078d7  cmp     [rbx+30h], r15
0x1800078db  jz      loc_180007971
0x1800078e1  lea     r8, asc_1800321B0; "    "
0x1800078e8  mov     rdx, rsi; unsigned __int16 *
0x1800078eb  mov     rcx, rax; this
0x1800078ee  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800078f3  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800078f7  test    r9, r9
0x1800078fa  jz      short loc_18000790E
0x1800078fc  lea     r8, aMsgWs; "Msg:[%ws] "
0x180007903  mov     rdx, rsi; unsigned __int16 *
0x180007906  mov     rcx, rax; this
0x180007909  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000790e  mov     r9, [rbx+48h]; unsigned __int16 *
0x180007912  test    r9, r9
0x180007915  jz      short loc_180007929
0x180007917  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x18000791e  mov     rdx, rsi; unsigned __int16 *
0x180007921  mov     rcx, rax; this
0x180007924  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007929  mov     rcx, [rbx+28h]
0x18000792d  mov     r9, [rbx+30h]; unsigned __int16 *
0x180007931  mov     rdx, rsi; unsigned __int16 *
0x180007934  test    rcx, rcx
0x180007937  jz      short loc_18000794F
0x180007939  mov     [rsp+278h+lpBuffer], rcx
0x18000793e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x180007945  mov     rcx, rax; this
0x180007948  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000794d  jmp     short loc_180007971
0x18000794f  mov     rcx, rax; this
0x180007952  test    r9, r9
0x180007955  jz      short loc_180007965
0x180007957  lea     r8, aHs; "[%hs]\n"
0x18000795e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007963  jmp     short loc_180007971
0x180007965  lea     r8, asc_180032228; "\n"
0x18000796c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180007971  xor     eax, eax
0x180007973  mov     rcx, [rsp+278h+var_38]
0x18000797b  xor     rcx, rsp; StackCookie
0x18000797e  call    __security_check_cookie
0x180007983  mov     rbx, [rsp+278h+arg_18]
0x18000798b  add     rsp, 250h
0x180007992  pop     r15
0x180007994  pop     r14
0x180007996  pop     rdi
0x180007997  pop     rsi
0x180007998  pop     rbp
0x180007999  retn
```
