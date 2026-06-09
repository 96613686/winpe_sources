# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800e5638`
- end: `0x1800e58b1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800e53a8`

## callees

- `0x180003a40`
- `0x1800e4d20`
- `0x1800e5638`
- `0x1800e7f74`
- `0x1800e8820`
- `0x1800e97d0`
- `0x1800ec390`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e56f1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800e56f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e587e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800e587e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e57f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800e57f4`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800e5638  mov     [rsp-8+arg_18], rbx
0x1800e563d  push    rbp
0x1800e563e  push    rsi
0x1800e563f  push    rdi
0x1800e5640  push    r12
0x1800e5642  push    r13
0x1800e5644  push    r14
0x1800e5646  push    r15
0x1800e5648  lea     rbp, [rsp-13C0h]
0x1800e5650  mov     eax, 14C0h
0x1800e5655  call    _alloca_probe
0x1800e565a  sub     rsp, rax
0x1800e565d  mov     r14, r8
0x1800e5660  mov     esi, edx
0x1800e5662  mov     rdi, rcx
0x1800e5665  mov     r15, [rbp+13F0h+arg_28]
0x1800e566c  xor     edx, edx; Val
0x1800e566e  mov     r8d, 98h; Size
0x1800e5674  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800e5679  call    memset_0
0x1800e567e  nop
0x1800e567f  xor     r13d, r13d
0x1800e5682  mov     [rbp+13F0h+OutputString], r13w
0x1800e568a  mov     [rbp+13F0h+var_1430], r13b
0x1800e568e  mov     rbx, [rbp+13F0h+arg_30]
0x1800e5695  mov     ecx, [rbx]; this
0x1800e5697  mov     [rsp+14F0h+var_14C8], ecx
0x1800e569b  mov     eax, [rbx+4]
0x1800e569e  mov     [rsp+14F0h+var_14C4], eax
0x1800e56a2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800e56a7  mov     r12d, eax
0x1800e56aa  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800e56b2  mov     ecx, r13d
0x1800e56b5  lea     eax, [r13+8]
0x1800e56b9  cmp     dword ptr [rbx+8], 1
0x1800e56bd  cmovz   ecx, eax
0x1800e56c0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800e56c4  lea     ecx, [rax-7]
0x1800e56c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800e56cf  inc     ecx
0x1800e56d1  mov     [rsp+14F0h+var_14C0], ecx
0x1800e56d5  mov     rcx, [rbp+13F0h+arg_38]
0x1800e56dc  test    rcx, rcx
0x1800e56df  jz      short loc_1800E56EC
0x1800e56e1  cmp     [rcx], r13w
0x1800e56e5  mov     [rsp+14F0h+var_14B8], rcx
0x1800e56ea  jnz     short loc_1800E56F1
0x1800e56ec  mov     [rsp+14F0h+var_14B8], r13
0x1800e56f1  call    cs:__imp_GetCurrentThreadId
0x1800e56f7  mov     [rsp+14F0h+var_14B0], eax
0x1800e56fb  mov     [rsp+14F0h+var_1498], r14
0x1800e5700  mov     [rsp+14F0h+var_1490], esi
0x1800e5704  mov     [rsp+14F0h+var_148C], r12d
0x1800e5709  mov     [rsp+14F0h+var_14A8], r13
0x1800e570e  mov     [rsp+14F0h+var_14A0], r13
0x1800e5713  mov     [rbp+13F0h+var_1448], r15
0x1800e5717  mov     [rbp+13F0h+var_1440], rdi
0x1800e571b  mov     [rsp+14F0h+var_1488], r13
0x1800e5720  xorps   xmm0, xmm0
0x1800e5723  xor     eax, eax
0x1800e5725  movups  [rbp+13F0h+var_1468], xmm0
0x1800e5729  mov     [rbp+13F0h+var_1458], rax
0x1800e572d  xorps   xmm1, xmm1
0x1800e5730  movups  [rsp+14F0h+var_1480], xmm1
0x1800e5735  mov     [rbp+13F0h+var_1470], rax
0x1800e5739  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800e5740  test    rax, rax
0x1800e5743  jz      short loc_1800E5750
0x1800e5745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e574a  mov     [rbp+13F0h+var_1450], rax
0x1800e574e  jmp     short loc_1800E5754
0x1800e5750  mov     [rbp+13F0h+var_1450], r13
0x1800e5754  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800e575b  test    rax, rax
0x1800e575e  jz      short loc_1800E576A
0x1800e5760  lea     rcx, [rsp+14F0h+var_14D0]
0x1800e5765  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e576a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800e5771  test    rax, rax
0x1800e5774  jz      short loc_1800E578A
0x1800e5776  mov     r8d, 400h
0x1800e577c  lea     rdx, [rbp+13F0h+var_1430]
0x1800e5780  lea     rcx, [rsp+14F0h+var_14D0]
0x1800e5785  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e578a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e5791  test    rax, rax
0x1800e5794  jz      short loc_1800E57A0
0x1800e5796  lea     rcx, [rsp+14F0h+var_14D0]
0x1800e579b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e57a0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800e57a7  test    rax, rax
0x1800e57aa  jz      short loc_1800E57BD
0x1800e57ac  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800e57b1  jnz     short loc_1800E57BD
0x1800e57b3  lea     rcx, [rsp+14F0h+var_14D0]
0x1800e57b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e57bd  cmp     [rsp+14F0h+var_14C8], r13d
0x1800e57c2  jl      short loc_1800E57D6
0x1800e57c4  mov     ecx, 8000FFFFh; this
0x1800e57c9  mov     [rsp+14F0h+var_14C8], ecx
0x1800e57cd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800e57d2  mov     [rsp+14F0h+var_14C4], eax
0x1800e57d6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800e57dd  jnz     short loc_1800E57FE
0x1800e57df  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800e57e6  test    rax, rax
0x1800e57e9  jz      short loc_1800E57F4
0x1800e57eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e57f0  test    al, al
0x1800e57f2  jmp     short loc_1800E57FC
0x1800e57f4  call    cs:__imp_IsDebuggerPresent
0x1800e57fa  test    eax, eax
0x1800e57fc  jz      short loc_1800E5805
0x1800e57fe  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800e5803  jz      short loc_1800E582B
0x1800e5805  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e580c  test    rax, rax
0x1800e580f  jz      short loc_1800E5884
0x1800e5811  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800e5818  jnz     short loc_1800E5884
0x1800e581a  xor     r8d, r8d
0x1800e581d  xor     edx, edx
0x1800e581f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800e5824  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5829  jmp     short loc_1800E5884
0x1800e582b  mov     ebx, 800h
0x1800e5830  mov     rax, cs:g_pfnResultLoggingCallback
0x1800e5837  test    rax, rax
0x1800e583a  jz      short loc_1800E5859
0x1800e583c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800e5843  jnz     short loc_1800E5859
0x1800e5845  mov     r8d, ebx
0x1800e5848  lea     rdx, [rbp+13F0h+OutputString]
0x1800e584f  lea     rcx, [rsp+14F0h+var_14D0]
0x1800e5854  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5859  cmp     [rbp+13F0h+OutputString], r13w
0x1800e5861  jnz     short loc_1800E5877
0x1800e5863  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800e5868  mov     rdx, rbx; unsigned __int16 *
0x1800e586b  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800e5872  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800e5877  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800e587e  call    cs:__imp_OutputDebugStringW
0x1800e5884  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800e5889  jnz     short loc_1800E5894
0x1800e588b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800e5892  jz      short loc_1800E58A6
0x1800e5894  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800e589b  test    rax, rax
0x1800e589e  jz      short loc_1800E58A6
0x1800e58a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e58a5  nop
0x1800e58a6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800e58ab  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
