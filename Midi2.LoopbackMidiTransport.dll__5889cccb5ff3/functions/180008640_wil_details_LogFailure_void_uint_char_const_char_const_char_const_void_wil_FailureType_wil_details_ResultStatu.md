# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008640`
- end: `0x180008939`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005a0c`

## callees

- `0x180005438`
- `0x180007b74`
- `0x180008314`
- `0x180008640`
- `0x180008fb8`
- `0x180008fe0`
- `0x180008ff4`
- `0x180009010`
- `0x18000b1c4`
- `0x180032010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008763`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008763`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008882`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008882`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800088f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800088f4`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v24);
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180008640  mov     [rsp+arg_10], rbx
0x180008645  mov     [rsp+arg_8], edx
0x180008649  mov     [rsp+arg_0], rcx
0x18000864e  push    rbp
0x18000864f  push    rsi
0x180008650  push    rdi
0x180008651  push    r12
0x180008653  push    r13
0x180008655  push    r14
0x180008657  push    r15
0x180008659  sub     rsp, 40h
0x18000865d  mov     r12, r9
0x180008660  mov     r13, r8
0x180008663  mov     r10, rcx
0x180008666  xor     eax, eax
0x180008668  mov     rsi, [rsp+78h+lpOutputString]
0x180008670  mov     [rsi], ax
0x180008673  mov     rax, [rsp+78h+arg_60]
0x18000867b  mov     byte ptr [rax], 0
0x18000867e  mov     r14, [rsp+78h+arg_38]
0x180008686  mov     edi, [r14]
0x180008689  mov     rbx, [rsp+78h+arg_78]
0x180008691  mov     [rbx+8], edi
0x180008694  mov     eax, [r14+4]
0x180008698  mov     [rbx+0Ch], eax
0x18000869b  xor     ebp, ebp
0x18000869d  mov     r15d, [rsp+78h+arg_30]
0x1800086a5  mov     ecx, r15d
0x1800086a8  test    r15d, r15d
0x1800086ab  jz      short loc_180008713
0x1800086ad  sub     ecx, 1
0x1800086b0  jz      short loc_18000870A
0x1800086b2  sub     ecx, 1
0x1800086b5  jz      short loc_1800086C5
0x1800086b7  cmp     ecx, 1
0x1800086ba  jnz     short loc_18000871C
0x1800086bc  mov     ecx, edi; this
0x1800086be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800086c3  jmp     short loc_18000871A
0x1800086c5  test    edi, edi
0x1800086c7  js      short loc_180008701
0x1800086c9  mov     edi, 8007029Ch
0x1800086ce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800086d2  mov     rax, [rsp+78h+arg_28]
0x1800086da  mov     [rsp+78h+var_50], rax; __int64
0x1800086df  mov     rax, [rsp+78h+arg_20]
0x1800086e7  mov     [rsp+78h+var_58], rax; __int64
0x1800086ec  mov     rcx, r10; int
0x1800086ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800086f4  mov     [rbx+8], edi
0x1800086f7  mov     ecx, edi; this
0x1800086f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800086fe  mov     [rbx+0Ch], eax
0x180008701  mov     ecx, edi; this
0x180008703  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008708  jmp     short loc_18000871A
0x18000870a  mov     ecx, edi; this
0x18000870c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008711  jmp     short loc_18000871A
0x180008713  mov     ecx, edi; this
0x180008715  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000871a  mov     ebp, eax
0x18000871c  mov     [rbx], r15d
0x18000871f  mov     eax, [rsp+78h+arg_70]
0x180008726  mov     [rbx+4], eax
0x180008729  cmp     dword ptr [r14+8], 1
0x18000872e  jnz     short loc_180008736
0x180008730  or      eax, 8
0x180008733  mov     [rbx+4], eax
0x180008736  mov     eax, 1
0x18000873b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008743  inc     eax
0x180008745  mov     [rbx+10h], eax
0x180008748  mov     rax, [rsp+78h+arg_40]
0x180008750  xor     edi, edi
0x180008752  test    rax, rax
0x180008755  jz      short loc_18000875C
0x180008757  cmp     [rax], di
0x18000875a  jnz     short loc_18000875F
0x18000875c  mov     rax, rdi
0x18000875f  mov     [rbx+18h], rax
0x180008763  call    cs:__imp_GetCurrentThreadId
0x180008769  mov     [rbx+20h], eax
0x18000876c  mov     [rbx+38h], r13
0x180008770  mov     eax, [rsp+78h+arg_8]
0x180008777  mov     [rbx+40h], eax
0x18000877a  mov     [rbx+44h], ebp
0x18000877d  mov     rax, [rsp+78h+arg_20]
0x180008785  mov     [rbx+28h], rax
0x180008789  mov     [rbx+30h], r12
0x18000878d  mov     rax, [rsp+78h+arg_28]
0x180008795  mov     [rbx+88h], rax
0x18000879c  mov     rax, [rsp+78h+arg_0]
0x1800087a4  mov     [rbx+90h], rax
0x1800087ab  mov     [rbx+48h], rdi
0x1800087af  xorps   xmm0, xmm0
0x1800087b2  xor     eax, eax
0x1800087b4  movups  xmmword ptr [rbx+68h], xmm0
0x1800087b8  mov     [rbx+78h], rax
0x1800087bc  movups  xmmword ptr [rbx+50h], xmm0
0x1800087c0  mov     [rbx+60h], rax
0x1800087c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800087cb  test    rax, rax
0x1800087ce  jz      short loc_1800087D7
0x1800087d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087d5  jmp     short loc_1800087DA
0x1800087d7  mov     rax, rdi
0x1800087da  mov     [rbx+80h], rax
0x1800087e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800087e8  test    rax, rax
0x1800087eb  jz      short loc_1800087F5
0x1800087ed  mov     rcx, rbx
0x1800087f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800087fc  test    rax, rax
0x1800087ff  jz      short loc_180008817
0x180008801  mov     r8d, 400h
0x180008807  mov     rdx, [rsp+78h+arg_60]
0x18000880f  mov     rcx, rbx
0x180008812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008817  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000881e  test    rax, rax
0x180008821  jz      short loc_18000882B
0x180008823  mov     rcx, rbx
0x180008826  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000882b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008832  test    rax, rax
0x180008835  jz      short loc_180008845
0x180008837  test    byte ptr [rbx+4], 2
0x18000883b  jnz     short loc_180008845
0x18000883d  mov     rcx, rbx
0x180008840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008845  cmp     [rbx+8], edi
0x180008848  jl      short loc_180008864
0x18000884a  cmp     r15d, 3
0x18000884e  jnz     loc_180008933
0x180008854  mov     ecx, 8000FFFFh; this
0x180008859  mov     [rbx+8], ecx
0x18000885c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008861  mov     [rbx+0Ch], eax
0x180008864  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000886b  jnz     short loc_18000888C
0x18000886d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008874  test    rax, rax
0x180008877  jz      short loc_180008882
0x180008879  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000887e  test    al, al
0x180008880  jmp     short loc_18000888A
0x180008882  call    cs:__imp_IsDebuggerPresent
0x180008888  test    eax, eax
0x18000888a  jz      short loc_180008892
0x18000888c  test    byte ptr [rbx+4], 2
0x180008890  jz      short loc_1800088B6
0x180008892  mov     rax, cs:g_pfnResultLoggingCallback
0x180008899  test    rax, rax
0x18000889c  jz      short loc_1800088FA
0x18000889e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800088a5  jnz     short loc_1800088FA
0x1800088a7  xor     r8d, r8d
0x1800088aa  xor     edx, edx
0x1800088ac  mov     rcx, rbx
0x1800088af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088b4  jmp     short loc_1800088FA
0x1800088b6  mov     ebp, 800h
0x1800088bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800088c2  test    rax, rax
0x1800088c5  jz      short loc_1800088DE
0x1800088c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800088ce  jnz     short loc_1800088DE
0x1800088d0  mov     r8d, ebp
0x1800088d3  mov     rdx, rsi
0x1800088d6  mov     rcx, rbx
0x1800088d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088de  cmp     [rsi], di
0x1800088e1  jnz     short loc_1800088F1
0x1800088e3  mov     r8, rbx; unsigned __int64
0x1800088e6  mov     rdx, rbp; unsigned __int16 *
0x1800088e9  mov     rcx, rsi; this
0x1800088ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800088f1  mov     rcx, rsi; lpOutputString
0x1800088f4  call    cs:__imp_OutputDebugStringW
0x1800088fa  test    byte ptr [rbx+4], 4
0x1800088fe  jnz     short loc_180008909
0x180008900  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008907  jz      short loc_18000891B
0x180008909  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008910  test    rax, rax
0x180008913  jz      short loc_18000891B
0x180008915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000891a  nop
0x18000891b  mov     rbx, [rsp+78h+arg_10]
0x180008923  add     rsp, 40h
0x180008927  pop     r15
0x180008929  pop     r14
0x18000892b  pop     r13
0x18000892d  pop     r12
0x18000892f  pop     rdi
0x180008930  pop     rsi
0x180008931  pop     rbp
0x180008932  retn
0x180008933  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
