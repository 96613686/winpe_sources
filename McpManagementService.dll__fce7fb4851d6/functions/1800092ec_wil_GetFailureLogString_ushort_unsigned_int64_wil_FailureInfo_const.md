# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x1800092ec`
- end: `0x1800095a2`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x1800061b0`
- `0x18000a500`
- `0x18000abe0`
- `0x18000e940`

## callees

- `0x180003a60`
- `0x1800045d8`
- `0x1800092ec`
- `0x18000a800`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000949f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000949f`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000941e`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x18000941e`

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
          v7 = (const char *)&byte_18002DF00;
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
0x1800092ec  mov     [rsp+arg_18], rbx
0x1800092f1  push    rbp
0x1800092f2  push    rsi
0x1800092f3  push    rdi
0x1800092f4  push    r14
0x1800092f6  push    r15
0x1800092f8  sub     rsp, 250h
0x1800092ff  mov     rax, cs:__security_cookie
0x180009306  xor     rax, rsp
0x180009309  mov     [rsp+278h+var_38], rax
0x180009311  mov     rbx, r8
0x180009314  mov     rsi, rdx
0x180009317  mov     r14, rcx
0x18000931a  xor     r15d, r15d
0x18000931d  test    rdx, rdx
0x180009320  jz      loc_180009579
0x180009326  test    rcx, rcx
0x180009329  jz      loc_180009579
0x18000932f  mov     [rcx], r15w
0x180009333  mov     rax, cs:g_pfnResultLoggingCallback
0x18000933a  test    rax, rax
0x18000933d  jz      short loc_180009360
0x18000933f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180009346  jz      short loc_180009360
0x180009348  mov     r8, rdx
0x18000934b  mov     rdx, rcx
0x18000934e  mov     rcx, rbx
0x180009351  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009356  cmp     [r14], r15w
0x18000935a  jnz     loc_180009579
0x180009360  mov     ecx, [rbx]
0x180009362  mov     bpl, 8
0x180009365  test    ecx, ecx
0x180009367  jz      short loc_1800093B2
0x180009369  sub     ecx, 1
0x18000936c  jz      short loc_18000939A
0x18000936e  sub     ecx, 1
0x180009371  jz      short loc_18000938A
0x180009373  cmp     ecx, 1
0x180009376  jz      short loc_180009381
0x180009378  lea     rdi, byte_18002DF00
0x18000937f  jmp     short loc_1800093B9
0x180009381  lea     rdi, aFailfast; "FailFast"
0x180009388  jmp     short loc_1800093B9
0x18000938a  lea     rax, aLoghr; "LogHr"
0x180009391  lea     rdi, aLognt; "LogNt"
0x180009398  jmp     short loc_1800093A8
0x18000939a  lea     rax, aReturnhr; "ReturnHr"
0x1800093a1  lea     rdi, aReturnnt; "ReturnNt"
0x1800093a8  test    [rbx+4], bpl
0x1800093ac  cmovz   rdi, rax
0x1800093b0  jmp     short loc_1800093B9
0x1800093b2  lea     rdi, aException; "Exception"
0x1800093b9  xor     edx, edx; Val
0x1800093bb  mov     r8d, 200h; Size
0x1800093c1  lea     rcx, [rsp+278h+Buffer]; void *
0x1800093c6  call    memset_0
0x1800093cb  test    [rbx+4], bpl
0x1800093cf  jz      short loc_1800093F4
0x1800093d1  mov     ebp, [rbx+0Ch]
0x1800093d4  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1800093db  test    rax, rax
0x1800093de  jz      short loc_180009424
0x1800093e0  mov     r8d, 100h
0x1800093e6  lea     rdx, [rsp+278h+Buffer]
0x1800093eb  mov     ecx, ebp
0x1800093ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800093f2  jmp     short loc_180009424
0x1800093f4  mov     ebp, [rbx+8]
0x1800093f7  mov     [rsp+278h+Arguments], r15; Arguments
0x1800093fc  mov     [rsp+278h+nSize], 100h; nSize
0x180009404  lea     rax, [rsp+278h+Buffer]
0x180009409  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x18000940e  mov     r9d, 400h; dwLanguageId
0x180009414  mov     r8d, ebp; dwMessageId
0x180009417  xor     edx, edx; lpSource
0x180009419  mov     ecx, 1200h; dwFlags
0x18000941e  call    cs:__imp_FormatMessageW
0x180009424  lea     rsi, [r14+rsi*2]
0x180009428  mov     r9, [rbx+38h]; unsigned __int16 *
0x18000942c  mov     rax, [rbx+88h]
0x180009433  mov     rcx, [rbx+80h]
0x18000943a  mov     rdx, rsi; unsigned __int16 *
0x18000943d  test    r9, r9
0x180009440  jz      short loc_180009464
0x180009442  mov     [rsp+278h+Arguments], rax
0x180009447  mov     qword ptr [rsp+278h+nSize], rcx
0x18000944c  mov     eax, [rbx+40h]
0x18000944f  mov     dword ptr [rsp+278h+lpBuffer], eax
0x180009453  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x18000945a  mov     rcx, r14; this
0x18000945d  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009462  jmp     short loc_18000947B
0x180009464  mov     [rsp+278h+lpBuffer], rax
0x180009469  mov     r9, rcx; unsigned __int16 *
0x18000946c  lea     r8, aHsP; "%hs!%p: "
0x180009473  mov     rcx, r14; this
0x180009476  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000947b  mov     r14, rax
0x18000947e  mov     r9, [rbx+90h]; unsigned __int16 *
0x180009485  test    r9, r9
0x180009488  jz      short loc_18000949F
0x18000948a  lea     r8, aCallerP; "(caller: %p) "
0x180009491  mov     rdx, rsi; unsigned __int16 *
0x180009494  mov     rcx, rax; this
0x180009497  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000949c  mov     r14, rax
0x18000949f  call    cs:__imp_GetCurrentThreadId
0x1800094a5  lea     rcx, [rsp+278h+Buffer]
0x1800094aa  mov     [rsp+278h+var_240], rcx
0x1800094af  mov     dword ptr [rsp+278h+Arguments], ebp
0x1800094b3  mov     [rsp+278h+nSize], eax
0x1800094b7  mov     eax, [rbx+44h]
0x1800094ba  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1800094be  mov     r9, rdi; unsigned __int16 *
0x1800094c1  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1800094c8  mov     rdx, rsi; unsigned __int16 *
0x1800094cb  mov     rcx, r14; this
0x1800094ce  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094d3  cmp     [rbx+18h], r15
0x1800094d7  jnz     short loc_1800094E9
0x1800094d9  cmp     [rbx+48h], r15
0x1800094dd  jnz     short loc_1800094E9
0x1800094df  cmp     [rbx+30h], r15
0x1800094e3  jz      loc_180009579
0x1800094e9  lea     r8, asc_18002E020; "    "
0x1800094f0  mov     rdx, rsi; unsigned __int16 *
0x1800094f3  mov     rcx, rax; this
0x1800094f6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1800094fb  mov     r9, [rbx+18h]; unsigned __int16 *
0x1800094ff  test    r9, r9
0x180009502  jz      short loc_180009516
0x180009504  lea     r8, aMsgWs; "Msg:[%ws] "
0x18000950b  mov     rdx, rsi; unsigned __int16 *
0x18000950e  mov     rcx, rax; this
0x180009511  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009516  mov     r9, [rbx+48h]; unsigned __int16 *
0x18000951a  test    r9, r9
0x18000951d  jz      short loc_180009531
0x18000951f  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x180009526  mov     rdx, rsi; unsigned __int16 *
0x180009529  mov     rcx, rax; this
0x18000952c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009531  mov     rcx, [rbx+28h]
0x180009535  mov     r9, [rbx+30h]; unsigned __int16 *
0x180009539  mov     rdx, rsi; unsigned __int16 *
0x18000953c  test    rcx, rcx
0x18000953f  jz      short loc_180009557
0x180009541  mov     [rsp+278h+lpBuffer], rcx
0x180009546  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x18000954d  mov     rcx, rax; this
0x180009550  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009555  jmp     short loc_180009579
0x180009557  mov     rcx, rax; this
0x18000955a  test    r9, r9
0x18000955d  jz      short loc_18000956D
0x18000955f  lea     r8, aHs; "[%hs]\n"
0x180009566  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x18000956b  jmp     short loc_180009579
0x18000956d  lea     r8, asc_18002E098; "\n"
0x180009574  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x180009579  xor     eax, eax
0x18000957b  mov     rcx, [rsp+278h+var_38]
0x180009583  xor     rcx, rsp; StackCookie
0x180009586  call    __security_check_cookie
0x18000958b  mov     rbx, [rsp+278h+arg_18]
0x180009593  add     rsp, 250h
0x18000959a  pop     r15
0x18000959c  pop     r14
0x18000959e  pop     rdi
0x18000959f  pop     rsi
0x1800095a0  pop     rbp
0x1800095a1  retn
```
