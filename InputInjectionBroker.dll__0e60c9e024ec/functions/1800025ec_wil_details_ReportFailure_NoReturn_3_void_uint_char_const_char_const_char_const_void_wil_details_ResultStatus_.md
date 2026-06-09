# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800025ec`
- end: `0x18000284e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002388`

## callees

- `0x1800025ec`
- `0x1800039d4`
- `0x180004174`
- `0x1800048a0`
- `0x180005600`
- `0x18001143a`
- `0x180011520`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000268e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000268e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000281b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000281b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002791`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180002791`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x1800025ec  mov     [rsp-8+arg_18], rbx
0x1800025f1  push    rbp
0x1800025f2  push    rsi
0x1800025f3  push    rdi
0x1800025f4  push    r12
0x1800025f6  push    r13
0x1800025f8  push    r14
0x1800025fa  push    r15
0x1800025fc  lea     rbp, [rsp-13C0h]
0x180002604  mov     eax, 14C0h
0x180002609  call    _alloca_probe
0x18000260e  sub     rsp, rax
0x180002611  mov     r15, r8
0x180002614  mov     r14d, edx
0x180002617  mov     r12, rcx
0x18000261a  mov     rsi, [rbp+13F0h+arg_28]
0x180002621  xor     edx, edx; Val
0x180002623  mov     r8d, 98h; Size
0x180002629  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000262e  call    memset_0
0x180002633  nop
0x180002634  xor     r13d, r13d
0x180002637  mov     [rbp+13F0h+OutputString], r13w
0x18000263f  mov     [rbp+13F0h+var_1430], r13b
0x180002643  mov     rbx, [rbp+13F0h+arg_30]
0x18000264a  mov     ecx, [rbx]; this
0x18000264c  mov     [rsp+14F0h+var_14C8], ecx
0x180002650  mov     eax, [rbx+4]
0x180002653  mov     [rsp+14F0h+var_14C4], eax
0x180002657  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000265c  mov     edi, eax
0x18000265e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002666  mov     ecx, r13d
0x180002669  lea     eax, [r13+8]
0x18000266d  cmp     dword ptr [rbx+8], 1
0x180002671  cmovz   ecx, eax
0x180002674  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002678  lea     ecx, [rax-7]
0x18000267b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002683  inc     ecx
0x180002685  mov     [rsp+14F0h+var_14C0], ecx
0x180002689  mov     [rsp+14F0h+var_14B8], r13
0x18000268e  call    cs:__imp_GetCurrentThreadId
0x180002694  mov     [rsp+14F0h+var_14B0], eax
0x180002698  mov     [rsp+14F0h+var_1498], r15
0x18000269d  mov     [rsp+14F0h+var_1490], r14d
0x1800026a2  mov     [rsp+14F0h+var_148C], edi
0x1800026a6  mov     [rsp+14F0h+var_14A8], r13
0x1800026ab  mov     [rsp+14F0h+var_14A0], r13
0x1800026b0  mov     [rbp+13F0h+var_1448], rsi
0x1800026b4  mov     [rbp+13F0h+var_1440], r12
0x1800026b8  mov     [rsp+14F0h+var_1488], r13
0x1800026bd  xorps   xmm0, xmm0
0x1800026c0  xor     eax, eax
0x1800026c2  movups  [rbp+13F0h+var_1468], xmm0
0x1800026c6  mov     [rbp+13F0h+var_1458], rax
0x1800026ca  xorps   xmm1, xmm1
0x1800026cd  movups  [rsp+14F0h+var_1480], xmm1
0x1800026d2  mov     [rbp+13F0h+var_1470], rax
0x1800026d6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800026dd  test    rax, rax
0x1800026e0  jz      short loc_1800026ED
0x1800026e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800026e7  mov     [rbp+13F0h+var_1450], rax
0x1800026eb  jmp     short loc_1800026F1
0x1800026ed  mov     [rbp+13F0h+var_1450], r13
0x1800026f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800026f8  test    rax, rax
0x1800026fb  jz      short loc_180002707
0x1800026fd  lea     rcx, [rsp+14F0h+var_14D0]
0x180002702  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002707  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000270e  test    rax, rax
0x180002711  jz      short loc_180002727
0x180002713  mov     r8d, 400h
0x180002719  lea     rdx, [rbp+13F0h+var_1430]
0x18000271d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002727  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000272e  test    rax, rax
0x180002731  jz      short loc_18000273D
0x180002733  lea     rcx, [rsp+14F0h+var_14D0]
0x180002738  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000273d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002744  test    rax, rax
0x180002747  jz      short loc_18000275A
0x180002749  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000274e  jnz     short loc_18000275A
0x180002750  lea     rcx, [rsp+14F0h+var_14D0]
0x180002755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000275a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000275f  jl      short loc_180002773
0x180002761  mov     ecx, 8000FFFFh; this
0x180002766  mov     [rsp+14F0h+var_14C8], ecx
0x18000276a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000276f  mov     [rsp+14F0h+var_14C4], eax
0x180002773  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000277a  jnz     short loc_18000279B
0x18000277c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002783  test    rax, rax
0x180002786  jz      short loc_180002791
0x180002788  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000278d  test    al, al
0x18000278f  jmp     short loc_180002799
0x180002791  call    cs:__imp_IsDebuggerPresent
0x180002797  test    eax, eax
0x180002799  jz      short loc_1800027A2
0x18000279b  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800027a0  jz      short loc_1800027C8
0x1800027a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027a9  test    rax, rax
0x1800027ac  jz      short loc_180002821
0x1800027ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800027b5  jnz     short loc_180002821
0x1800027b7  xor     r8d, r8d
0x1800027ba  xor     edx, edx
0x1800027bc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027c6  jmp     short loc_180002821
0x1800027c8  mov     ebx, 800h
0x1800027cd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800027d4  test    rax, rax
0x1800027d7  jz      short loc_1800027F6
0x1800027d9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800027e0  jnz     short loc_1800027F6
0x1800027e2  mov     r8d, ebx
0x1800027e5  lea     rdx, [rbp+13F0h+OutputString]
0x1800027ec  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f6  cmp     [rbp+13F0h+OutputString], r13w
0x1800027fe  jnz     short loc_180002814
0x180002800  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002805  mov     rdx, rbx; unsigned __int16 *
0x180002808  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000280f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002814  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000281b  call    cs:__imp_OutputDebugStringW
0x180002821  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002826  jnz     short loc_180002831
0x180002828  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000282f  jz      short loc_180002843
0x180002831  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002838  test    rax, rax
0x18000283b  jz      short loc_180002843
0x18000283d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002842  nop
0x180002843  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002848  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
