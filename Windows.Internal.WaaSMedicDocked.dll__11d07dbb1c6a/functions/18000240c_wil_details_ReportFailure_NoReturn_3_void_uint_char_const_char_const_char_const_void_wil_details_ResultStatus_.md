# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000240c`
- end: `0x18000266e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002198`

## callees

- `0x180001fde`
- `0x18000240c`
- `0x180003804`
- `0x180003fa4`
- `0x1800046d0`
- `0x180005610`
- `0x18000b550`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800024ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000263b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000263b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800025b1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800025b1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
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
0x18000240c  mov     [rsp-8+arg_18], rbx
0x180002411  push    rbp
0x180002412  push    rsi
0x180002413  push    rdi
0x180002414  push    r12
0x180002416  push    r13
0x180002418  push    r14
0x18000241a  push    r15
0x18000241c  lea     rbp, [rsp-13C0h]
0x180002424  mov     eax, 14C0h
0x180002429  call    _alloca_probe
0x18000242e  sub     rsp, rax
0x180002431  mov     r15, r8
0x180002434  mov     r14d, edx
0x180002437  mov     r12, rcx
0x18000243a  mov     rsi, [rbp+13F0h+arg_28]
0x180002441  xor     edx, edx; Val
0x180002443  mov     r8d, 98h; Size
0x180002449  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000244e  call    memset_0
0x180002453  nop
0x180002454  xor     r13d, r13d
0x180002457  mov     [rbp+13F0h+OutputString], r13w
0x18000245f  mov     [rbp+13F0h+var_1430], r13b
0x180002463  mov     rbx, [rbp+13F0h+arg_30]
0x18000246a  mov     ecx, [rbx]; this
0x18000246c  mov     [rsp+14F0h+var_14C8], ecx
0x180002470  mov     eax, [rbx+4]
0x180002473  mov     [rsp+14F0h+var_14C4], eax
0x180002477  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000247c  mov     edi, eax
0x18000247e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002486  mov     ecx, r13d
0x180002489  lea     eax, [r13+8]
0x18000248d  cmp     dword ptr [rbx+8], 1
0x180002491  cmovz   ecx, eax
0x180002494  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002498  lea     ecx, [rax-7]
0x18000249b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800024a3  inc     ecx
0x1800024a5  mov     [rsp+14F0h+var_14C0], ecx
0x1800024a9  mov     [rsp+14F0h+var_14B8], r13
0x1800024ae  call    cs:__imp_GetCurrentThreadId
0x1800024b4  mov     [rsp+14F0h+var_14B0], eax
0x1800024b8  mov     [rsp+14F0h+var_1498], r15
0x1800024bd  mov     [rsp+14F0h+var_1490], r14d
0x1800024c2  mov     [rsp+14F0h+var_148C], edi
0x1800024c6  mov     [rsp+14F0h+var_14A8], r13
0x1800024cb  mov     [rsp+14F0h+var_14A0], r13
0x1800024d0  mov     [rbp+13F0h+var_1448], rsi
0x1800024d4  mov     [rbp+13F0h+var_1440], r12
0x1800024d8  mov     [rsp+14F0h+var_1488], r13
0x1800024dd  xorps   xmm0, xmm0
0x1800024e0  xor     eax, eax
0x1800024e2  movups  [rbp+13F0h+var_1468], xmm0
0x1800024e6  mov     [rbp+13F0h+var_1458], rax
0x1800024ea  xorps   xmm1, xmm1
0x1800024ed  movups  [rsp+14F0h+var_1480], xmm1
0x1800024f2  mov     [rbp+13F0h+var_1470], rax
0x1800024f6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800024fd  test    rax, rax
0x180002500  jz      short loc_18000250D
0x180002502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002507  mov     [rbp+13F0h+var_1450], rax
0x18000250b  jmp     short loc_180002511
0x18000250d  mov     [rbp+13F0h+var_1450], r13
0x180002511  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002518  test    rax, rax
0x18000251b  jz      short loc_180002527
0x18000251d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002527  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000252e  test    rax, rax
0x180002531  jz      short loc_180002547
0x180002533  mov     r8d, 400h
0x180002539  lea     rdx, [rbp+13F0h+var_1430]
0x18000253d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002542  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002547  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000254e  test    rax, rax
0x180002551  jz      short loc_18000255D
0x180002553  lea     rcx, [rsp+14F0h+var_14D0]
0x180002558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000255d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002564  test    rax, rax
0x180002567  jz      short loc_18000257A
0x180002569  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000256e  jnz     short loc_18000257A
0x180002570  lea     rcx, [rsp+14F0h+var_14D0]
0x180002575  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000257a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000257f  jl      short loc_180002593
0x180002581  mov     ecx, 8000FFFFh; this
0x180002586  mov     [rsp+14F0h+var_14C8], ecx
0x18000258a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000258f  mov     [rsp+14F0h+var_14C4], eax
0x180002593  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000259a  jnz     short loc_1800025BB
0x18000259c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800025a3  test    rax, rax
0x1800025a6  jz      short loc_1800025B1
0x1800025a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025ad  test    al, al
0x1800025af  jmp     short loc_1800025B9
0x1800025b1  call    cs:__imp_IsDebuggerPresent
0x1800025b7  test    eax, eax
0x1800025b9  jz      short loc_1800025C2
0x1800025bb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800025c0  jz      short loc_1800025E8
0x1800025c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800025c9  test    rax, rax
0x1800025cc  jz      short loc_180002641
0x1800025ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800025d5  jnz     short loc_180002641
0x1800025d7  xor     r8d, r8d
0x1800025da  xor     edx, edx
0x1800025dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1800025e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800025e6  jmp     short loc_180002641
0x1800025e8  mov     ebx, 800h
0x1800025ed  mov     rax, cs:g_pfnResultLoggingCallback
0x1800025f4  test    rax, rax
0x1800025f7  jz      short loc_180002616
0x1800025f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002600  jnz     short loc_180002616
0x180002602  mov     r8d, ebx
0x180002605  lea     rdx, [rbp+13F0h+OutputString]
0x18000260c  lea     rcx, [rsp+14F0h+var_14D0]
0x180002611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002616  cmp     [rbp+13F0h+OutputString], r13w
0x18000261e  jnz     short loc_180002634
0x180002620  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180002625  mov     rdx, rbx; unsigned __int16 *
0x180002628  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000262f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002634  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000263b  call    cs:__imp_OutputDebugStringW
0x180002641  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180002646  jnz     short loc_180002651
0x180002648  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000264f  jz      short loc_180002663
0x180002651  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002658  test    rax, rax
0x18000265b  jz      short loc_180002663
0x18000265d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002662  nop
0x180002663  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002668  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
