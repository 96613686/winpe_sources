# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400022b4`
- end: `0x14000251d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000205c`

## callees

- `0x140001f36`
- `0x1400022b4`
- `0x140003644`
- `0x140003de4`
- `0x140004510`
- `0x140005460`
- `0x1400064c0`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002356`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002356`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400024ea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400024ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002460`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002460`

## string_xrefs

- `0x140002360`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x1400022b4  mov     [rsp-8+arg_10], rbx
0x1400022b9  mov     [rsp-8+arg_18], rsi
0x1400022be  push    rbp
0x1400022bf  push    rdi
0x1400022c0  push    r12
0x1400022c2  push    r14
0x1400022c4  push    r15
0x1400022c6  lea     rbp, [rsp-13C0h]
0x1400022ce  mov     eax, 14C0h
0x1400022d3  call    _alloca_probe
0x1400022d8  sub     rsp, rax
0x1400022db  mov     r14d, edx
0x1400022de  mov     r15, rcx
0x1400022e1  mov     rsi, [rbp+13E0h+arg_28]
0x1400022e8  xor     edx, edx; Val
0x1400022ea  mov     r8d, 98h; Size
0x1400022f0  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1400022f5  call    memset_0
0x1400022fa  nop
0x1400022fb  xor     r12d, r12d
0x1400022fe  mov     [rbp+13E0h+OutputString], r12w
0x140002306  mov     [rbp+13E0h+var_1420], r12b
0x14000230a  mov     rbx, [rbp+13E0h+arg_30]
0x140002311  mov     ecx, [rbx]; this
0x140002313  mov     [rsp+14E0h+var_14B8], ecx
0x140002317  mov     eax, [rbx+4]
0x14000231a  mov     [rsp+14E0h+var_14B4], eax
0x14000231e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002323  mov     edi, eax
0x140002325  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x14000232d  mov     ecx, r12d
0x140002330  lea     eax, [r12+8]
0x140002335  cmp     dword ptr [rbx+8], 1
0x140002339  cmovz   ecx, eax
0x14000233c  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x140002340  lea     ecx, [rax-7]
0x140002343  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000234b  inc     ecx
0x14000234d  mov     [rsp+14E0h+var_14B0], ecx
0x140002351  mov     [rsp+14E0h+var_14A8], r12
0x140002356  call    cs:__imp_GetCurrentThreadId
0x14000235c  mov     [rsp+14E0h+var_14A0], eax
0x140002360  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x140002367  mov     [rsp+14E0h+var_1488], rax
0x14000236c  mov     [rsp+14E0h+var_1480], r14d
0x140002371  mov     [rsp+14E0h+var_147C], edi
0x140002375  mov     [rsp+14E0h+var_1498], r12
0x14000237a  mov     [rsp+14E0h+var_1490], r12
0x14000237f  mov     [rbp+13E0h+var_1438], rsi
0x140002383  mov     [rbp+13E0h+var_1430], r15
0x140002387  mov     [rsp+14E0h+var_1478], r12
0x14000238c  xorps   xmm0, xmm0
0x14000238f  xor     eax, eax
0x140002391  movups  [rbp+13E0h+var_1458], xmm0
0x140002395  mov     [rbp+13E0h+var_1448], rax
0x140002399  xorps   xmm1, xmm1
0x14000239c  movups  [rsp+14E0h+var_1470], xmm1
0x1400023a1  mov     [rbp+13E0h+var_1460], rax
0x1400023a5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400023ac  test    rax, rax
0x1400023af  jz      short loc_1400023BC
0x1400023b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023b6  mov     [rbp+13E0h+var_1440], rax
0x1400023ba  jmp     short loc_1400023C0
0x1400023bc  mov     [rbp+13E0h+var_1440], r12
0x1400023c0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400023c7  test    rax, rax
0x1400023ca  jz      short loc_1400023D6
0x1400023cc  lea     rcx, [rsp+14E0h+var_14C0]
0x1400023d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023d6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400023dd  test    rax, rax
0x1400023e0  jz      short loc_1400023F6
0x1400023e2  mov     r8d, 400h
0x1400023e8  lea     rdx, [rbp+13E0h+var_1420]
0x1400023ec  lea     rcx, [rsp+14E0h+var_14C0]
0x1400023f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400023f6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400023fd  test    rax, rax
0x140002400  jz      short loc_14000240C
0x140002402  lea     rcx, [rsp+14E0h+var_14C0]
0x140002407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000240c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002413  test    rax, rax
0x140002416  jz      short loc_140002429
0x140002418  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000241d  jnz     short loc_140002429
0x14000241f  lea     rcx, [rsp+14E0h+var_14C0]
0x140002424  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002429  cmp     [rsp+14E0h+var_14B8], r12d
0x14000242e  jl      short loc_140002442
0x140002430  mov     ecx, 8000FFFFh; this
0x140002435  mov     [rsp+14E0h+var_14B8], ecx
0x140002439  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000243e  mov     [rsp+14E0h+var_14B4], eax
0x140002442  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140002449  jnz     short loc_14000246A
0x14000244b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002452  test    rax, rax
0x140002455  jz      short loc_140002460
0x140002457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000245c  test    al, al
0x14000245e  jmp     short loc_140002468
0x140002460  call    cs:__imp_IsDebuggerPresent
0x140002466  test    eax, eax
0x140002468  jz      short loc_140002471
0x14000246a  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000246f  jz      short loc_140002497
0x140002471  mov     rax, cs:g_pfnResultLoggingCallback
0x140002478  test    rax, rax
0x14000247b  jz      short loc_1400024F0
0x14000247d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002484  jnz     short loc_1400024F0
0x140002486  xor     r8d, r8d
0x140002489  xor     edx, edx
0x14000248b  lea     rcx, [rsp+14E0h+var_14C0]
0x140002490  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002495  jmp     short loc_1400024F0
0x140002497  mov     ebx, 800h
0x14000249c  mov     rax, cs:g_pfnResultLoggingCallback
0x1400024a3  test    rax, rax
0x1400024a6  jz      short loc_1400024C5
0x1400024a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400024af  jnz     short loc_1400024C5
0x1400024b1  mov     r8d, ebx
0x1400024b4  lea     rdx, [rbp+13E0h+OutputString]
0x1400024bb  lea     rcx, [rsp+14E0h+var_14C0]
0x1400024c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024c5  cmp     [rbp+13E0h+OutputString], r12w
0x1400024cd  jnz     short loc_1400024E3
0x1400024cf  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1400024d4  mov     rdx, rbx; unsigned __int16 *
0x1400024d7  lea     rcx, [rbp+13E0h+OutputString]; this
0x1400024de  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400024e3  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1400024ea  call    cs:__imp_OutputDebugStringW
0x1400024f0  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1400024f5  jnz     short loc_140002500
0x1400024f7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400024fe  jz      short loc_140002512
0x140002500  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002507  test    rax, rax
0x14000250a  jz      short loc_140002512
0x14000250c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002511  nop
0x140002512  lea     rcx, [rsp+14E0h+var_14C0]; this
0x140002517  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
