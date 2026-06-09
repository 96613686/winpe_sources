# wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)

- ea: `0x140003704`
- end: `0x1400039ba`
- name: `?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z`
- size: `694`
- prototype: `__int64 __fastcall(wil *this, unsigned __int16 *, __int64, const struct wil::FailureInfo *)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x14000227c`
- `0x1400024e4`
- `0x140004068`
- `0x1400056e0`

## callees

- `0x140001530`
- `0x140001f50`
- `0x140003704`
- `0x140004368`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400038b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400038b7`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003836`
- `api-ms-win-core-localization-l1-2-0!FormatMessageW` at `0x140003836`

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
          v7 = (const char *)&qword_14000A6B0;
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
0x140003704  mov     [rsp+arg_18], rbx
0x140003709  push    rbp
0x14000370a  push    rsi
0x14000370b  push    rdi
0x14000370c  push    r14
0x14000370e  push    r15
0x140003710  sub     rsp, 250h
0x140003717  mov     rax, cs:__security_cookie
0x14000371e  xor     rax, rsp
0x140003721  mov     [rsp+278h+var_38], rax
0x140003729  mov     rbx, r8
0x14000372c  mov     rsi, rdx
0x14000372f  mov     r14, rcx
0x140003732  xor     r15d, r15d
0x140003735  test    rdx, rdx
0x140003738  jz      loc_140003991
0x14000373e  test    rcx, rcx
0x140003741  jz      loc_140003991
0x140003747  mov     [rcx], r15w
0x14000374b  mov     rax, cs:g_pfnResultLoggingCallback
0x140003752  test    rax, rax
0x140003755  jz      short loc_140003778
0x140003757  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x14000375e  jz      short loc_140003778
0x140003760  mov     r8, rdx
0x140003763  mov     rdx, rcx
0x140003766  mov     rcx, rbx
0x140003769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000376e  cmp     [r14], r15w
0x140003772  jnz     loc_140003991
0x140003778  mov     ecx, [rbx]
0x14000377a  mov     bpl, 8
0x14000377d  test    ecx, ecx
0x14000377f  jz      short loc_1400037CA
0x140003781  sub     ecx, 1
0x140003784  jz      short loc_1400037B2
0x140003786  sub     ecx, 1
0x140003789  jz      short loc_1400037A2
0x14000378b  cmp     ecx, 1
0x14000378e  jz      short loc_140003799
0x140003790  lea     rdi, qword_14000A6B0
0x140003797  jmp     short loc_1400037D1
0x140003799  lea     rdi, aFailfast; "FailFast"
0x1400037a0  jmp     short loc_1400037D1
0x1400037a2  lea     rax, aLoghr; "LogHr"
0x1400037a9  lea     rdi, aLognt; "LogNt"
0x1400037b0  jmp     short loc_1400037C0
0x1400037b2  lea     rax, aReturnhr; "ReturnHr"
0x1400037b9  lea     rdi, aReturnnt; "ReturnNt"
0x1400037c0  test    [rbx+4], bpl
0x1400037c4  cmovz   rdi, rax
0x1400037c8  jmp     short loc_1400037D1
0x1400037ca  lea     rdi, aException; "Exception"
0x1400037d1  xor     edx, edx; Val
0x1400037d3  mov     r8d, 200h; Size
0x1400037d9  lea     rcx, [rsp+278h+Buffer]; void *
0x1400037de  call    memset_0
0x1400037e3  test    [rbx+4], bpl
0x1400037e7  jz      short loc_14000380C
0x1400037e9  mov     ebp, [rbx+0Ch]
0x1400037ec  mov     rax, cs:?g_pfnFormatNtStatusMsg@details@wil@@3P6AXJPEAGK@ZEA; void (*wil::details::g_pfnFormatNtStatusMsg)(long,ushort *,ulong)
0x1400037f3  test    rax, rax
0x1400037f6  jz      short loc_14000383C
0x1400037f8  mov     r8d, 100h
0x1400037fe  lea     rdx, [rsp+278h+Buffer]
0x140003803  mov     ecx, ebp
0x140003805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000380a  jmp     short loc_14000383C
0x14000380c  mov     ebp, [rbx+8]
0x14000380f  mov     [rsp+278h+Arguments], r15; Arguments
0x140003814  mov     [rsp+278h+nSize], 100h; nSize
0x14000381c  lea     rax, [rsp+278h+Buffer]
0x140003821  mov     [rsp+278h+lpBuffer], rax; lpBuffer
0x140003826  mov     r9d, 400h; dwLanguageId
0x14000382c  mov     r8d, ebp; dwMessageId
0x14000382f  xor     edx, edx; lpSource
0x140003831  mov     ecx, 1200h; dwFlags
0x140003836  call    cs:__imp_FormatMessageW
0x14000383c  lea     rsi, [r14+rsi*2]
0x140003840  mov     r9, [rbx+38h]; unsigned __int16 *
0x140003844  mov     rax, [rbx+88h]
0x14000384b  mov     rcx, [rbx+80h]
0x140003852  mov     rdx, rsi; unsigned __int16 *
0x140003855  test    r9, r9
0x140003858  jz      short loc_14000387C
0x14000385a  mov     [rsp+278h+Arguments], rax
0x14000385f  mov     qword ptr [rsp+278h+nSize], rcx
0x140003864  mov     eax, [rbx+40h]
0x140003867  mov     dword ptr [rsp+278h+lpBuffer], eax
0x14000386b  lea     r8, aHsUHsP; "%hs(%u)\\%hs!%p: "
0x140003872  mov     rcx, r14; this
0x140003875  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000387a  jmp     short loc_140003893
0x14000387c  mov     [rsp+278h+lpBuffer], rax
0x140003881  mov     r9, rcx; unsigned __int16 *
0x140003884  lea     r8, aHsP; "%hs!%p: "
0x14000388b  mov     rcx, r14; this
0x14000388e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003893  mov     r14, rax
0x140003896  mov     r9, [rbx+90h]; unsigned __int16 *
0x14000389d  test    r9, r9
0x1400038a0  jz      short loc_1400038B7
0x1400038a2  lea     r8, aCallerP; "(caller: %p) "
0x1400038a9  mov     rdx, rsi; unsigned __int16 *
0x1400038ac  mov     rcx, rax; this
0x1400038af  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038b4  mov     r14, rax
0x1400038b7  call    cs:__imp_GetCurrentThreadId
0x1400038bd  lea     rcx, [rsp+278h+Buffer]
0x1400038c2  mov     [rsp+278h+var_240], rcx
0x1400038c7  mov     dword ptr [rsp+278h+Arguments], ebp
0x1400038cb  mov     [rsp+278h+nSize], eax
0x1400038cf  mov     eax, [rbx+44h]
0x1400038d2  mov     dword ptr [rsp+278h+lpBuffer], eax
0x1400038d6  mov     r9, rdi; unsigned __int16 *
0x1400038d9  lea     r8, aHsDTidX08xWs; "%hs(%d) tid(%x) %08X %ws"
0x1400038e0  mov     rdx, rsi; unsigned __int16 *
0x1400038e3  mov     rcx, r14; this
0x1400038e6  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x1400038eb  cmp     [rbx+18h], r15
0x1400038ef  jnz     short loc_140003901
0x1400038f1  cmp     [rbx+48h], r15
0x1400038f5  jnz     short loc_140003901
0x1400038f7  cmp     [rbx+30h], r15
0x1400038fb  jz      loc_140003991
0x140003901  lea     r8, asc_14000A7B8; "    "
0x140003908  mov     rdx, rsi; unsigned __int16 *
0x14000390b  mov     rcx, rax; this
0x14000390e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003913  mov     r9, [rbx+18h]; unsigned __int16 *
0x140003917  test    r9, r9
0x14000391a  jz      short loc_14000392E
0x14000391c  lea     r8, aMsgWs; "Msg:[%ws] "
0x140003923  mov     rdx, rsi; unsigned __int16 *
0x140003926  mov     rcx, rax; this
0x140003929  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000392e  mov     r9, [rbx+48h]; unsigned __int16 *
0x140003932  test    r9, r9
0x140003935  jz      short loc_140003949
0x140003937  lea     r8, aCallcontextHs; "CallContext:[%hs] "
0x14000393e  mov     rdx, rsi; unsigned __int16 *
0x140003941  mov     rcx, rax; this
0x140003944  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003949  mov     rcx, [rbx+28h]
0x14000394d  mov     r9, [rbx+30h]; unsigned __int16 *
0x140003951  mov     rdx, rsi; unsigned __int16 *
0x140003954  test    rcx, rcx
0x140003957  jz      short loc_14000396F
0x140003959  mov     [rsp+278h+lpBuffer], rcx
0x14000395e  lea     r8, aHsHs; "[%hs(%hs)]\n"
0x140003965  mov     rcx, rax; this
0x140003968  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x14000396d  jmp     short loc_140003991
0x14000396f  mov     rcx, rax; this
0x140003972  test    r9, r9
0x140003975  jz      short loc_140003985
0x140003977  lea     r8, aHs; "[%hs]\n"
0x14000397e  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003983  jmp     short loc_140003991
0x140003985  lea     r8, asc_14000A830; "\n"
0x14000398c  call    ?LogStringPrintf@details@wil@@YAPEAGPEAGPEBG1ZZ; wil::details::LogStringPrintf(ushort *,ushort const *,ushort const *,...)
0x140003991  xor     eax, eax
0x140003993  mov     rcx, [rsp+278h+var_38]
0x14000399b  xor     rcx, rsp; StackCookie
0x14000399e  call    __security_check_cookie
0x1400039a3  mov     rbx, [rsp+278h+arg_18]
0x1400039ab  add     rsp, 250h
0x1400039b2  pop     r15
0x1400039b4  pop     r14
0x1400039b6  pop     rdi
0x1400039b7  pop     rsi
0x1400039b8  pop     rbp
0x1400039b9  retn
```
