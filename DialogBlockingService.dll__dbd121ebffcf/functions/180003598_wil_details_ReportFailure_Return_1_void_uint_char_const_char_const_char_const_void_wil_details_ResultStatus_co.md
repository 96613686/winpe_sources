# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003598`
- end: `0x18000383e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002ed8`

## callees

- `0x180001620`
- `0x1800020d0`
- `0x180003598`
- `0x1800052f4`
- `0x1800063c0`
- `0x180007c30`
- `0x180007d0c`
- `0x18000c790`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000365e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000365e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800037dd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800037dd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003753`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003753`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180003598  push    rbp
0x18000359a  push    rbx
0x18000359b  push    rsi
0x18000359c  push    rdi
0x18000359d  push    r12
0x18000359f  push    r14
0x1800035a1  push    r15
0x1800035a3  lea     rbp, [rsp-13D0h]
0x1800035ab  mov     eax, 14D0h
0x1800035b0  call    _alloca_probe
0x1800035b5  sub     rsp, rax
0x1800035b8  mov     rax, cs:__security_cookie
0x1800035bf  xor     rax, rsp
0x1800035c2  mov     [rbp+1400h+var_40], rax
0x1800035c9  mov     rsi, r8
0x1800035cc  mov     edi, edx
0x1800035ce  mov     rbx, rcx
0x1800035d1  mov     r14, [rbp+1400h+arg_28]
0x1800035d8  xor     edx, edx; Val
0x1800035da  mov     r8d, 98h; Size
0x1800035e0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800035e5  call    memset_0
0x1800035ea  nop
0x1800035eb  xor     r12d, r12d
0x1800035ee  mov     [rbp+1400h+OutputString], r12w
0x1800035f6  mov     [rbp+1400h+var_1440], r12b
0x1800035fa  mov     rdx, [rbp+1400h+arg_30]; int
0x180003601  mov     ecx, [rdx]; this
0x180003603  mov     [rsp+1500h+var_14D8], ecx
0x180003607  mov     eax, [rdx+4]
0x18000360a  mov     [rsp+1500h+var_14D4], eax
0x18000360e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003613  mov     r15d, eax
0x180003616  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000361e  mov     ecx, r12d
0x180003621  lea     eax, [r12+8]
0x180003626  cmp     dword ptr [rdx+8], 1
0x18000362a  cmovz   ecx, eax
0x18000362d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003631  lea     ecx, [rax-7]
0x180003634  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000363c  inc     ecx
0x18000363e  mov     [rsp+1500h+var_14D0], ecx
0x180003642  mov     rcx, [rbp+1400h+arg_38]
0x180003649  test    rcx, rcx
0x18000364c  jz      short loc_180003659
0x18000364e  cmp     [rcx], r12w
0x180003652  mov     [rsp+1500h+var_14C8], rcx
0x180003657  jnz     short loc_18000365E
0x180003659  mov     [rsp+1500h+var_14C8], r12
0x18000365e  call    cs:__imp_GetCurrentThreadId
0x180003664  mov     [rsp+1500h+var_14C0], eax
0x180003668  mov     [rsp+1500h+var_14A8], rsi
0x18000366d  mov     [rsp+1500h+var_14A0], edi
0x180003671  mov     [rsp+1500h+var_149C], r15d
0x180003676  mov     [rsp+1500h+var_14B8], r12
0x18000367b  mov     [rsp+1500h+var_14B0], r12
0x180003680  mov     [rbp+1400h+var_1458], r14
0x180003684  mov     [rbp+1400h+var_1450], rbx
0x180003688  mov     [rsp+1500h+var_1498], r12
0x18000368d  xorps   xmm0, xmm0
0x180003690  xor     eax, eax
0x180003692  movups  [rbp+1400h+var_1478], xmm0
0x180003696  mov     [rbp+1400h+var_1468], rax
0x18000369a  xorps   xmm1, xmm1
0x18000369d  movups  [rsp+1500h+var_1490], xmm1
0x1800036a2  mov     [rbp+1400h+var_1480], rax
0x1800036a6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800036ad  test    rax, rax
0x1800036b0  jz      short loc_1800036BD
0x1800036b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036b7  mov     [rbp+1400h+var_1460], rax
0x1800036bb  jmp     short loc_1800036C1
0x1800036bd  mov     [rbp+1400h+var_1460], r12
0x1800036c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800036c8  test    rax, rax
0x1800036cb  jz      short loc_1800036D7
0x1800036cd  lea     rcx, [rsp+1500h+var_14E0]
0x1800036d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036d7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800036de  test    rax, rax
0x1800036e1  jz      short loc_1800036F7
0x1800036e3  mov     r8d, 400h
0x1800036e9  lea     rdx, [rbp+1400h+var_1440]
0x1800036ed  lea     rcx, [rsp+1500h+var_14E0]
0x1800036f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800036fe  test    rax, rax
0x180003701  jz      short loc_18000370D
0x180003703  lea     rcx, [rsp+1500h+var_14E0]
0x180003708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003714  test    rax, rax
0x180003717  jz      short loc_18000372A
0x180003719  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000371e  jnz     short loc_18000372A
0x180003720  lea     rcx, [rsp+1500h+var_14E0]
0x180003725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372a  cmp     [rsp+1500h+var_14D8], r12d
0x18000372f  jge     loc_180003838
0x180003735  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000373c  jnz     short loc_18000375D
0x18000373e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003745  test    rax, rax
0x180003748  jz      short loc_180003753
0x18000374a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000374f  test    al, al
0x180003751  jmp     short loc_18000375B
0x180003753  call    cs:__imp_IsDebuggerPresent
0x180003759  test    eax, eax
0x18000375b  jz      short loc_180003764
0x18000375d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003762  jz      short loc_18000378A
0x180003764  mov     rax, cs:g_pfnResultLoggingCallback
0x18000376b  test    rax, rax
0x18000376e  jz      short loc_1800037E3
0x180003770  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003777  jnz     short loc_1800037E3
0x180003779  xor     r8d, r8d
0x18000377c  xor     edx, edx
0x18000377e  lea     rcx, [rsp+1500h+var_14E0]
0x180003783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003788  jmp     short loc_1800037E3
0x18000378a  mov     ebx, 800h
0x18000378f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003796  test    rax, rax
0x180003799  jz      short loc_1800037B8
0x18000379b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800037a2  jnz     short loc_1800037B8
0x1800037a4  mov     r8d, ebx
0x1800037a7  lea     rdx, [rbp+1400h+OutputString]
0x1800037ae  lea     rcx, [rsp+1500h+var_14E0]
0x1800037b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b8  cmp     [rbp+1400h+OutputString], r12w
0x1800037c0  jnz     short loc_1800037D6
0x1800037c2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800037c7  mov     rdx, rbx; unsigned __int16 *
0x1800037ca  lea     rcx, [rbp+1400h+OutputString]; this
0x1800037d1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800037d6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800037dd  call    cs:__imp_OutputDebugStringW
0x1800037e3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800037e8  jnz     short loc_1800037F3
0x1800037ea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800037f1  jz      short loc_180003805
0x1800037f3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800037fa  test    rax, rax
0x1800037fd  jz      short loc_180003805
0x1800037ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003804  nop
0x180003805  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000380a  jnz     short loc_18000382D
0x18000380c  mov     rcx, [rbp+1400h+var_40]
0x180003813  xor     rcx, rsp; StackCookie
0x180003816  call    __security_check_cookie
0x18000381b  add     rsp, 14D0h
0x180003822  pop     r15
0x180003824  pop     r14
0x180003826  pop     r12
0x180003828  pop     rdi
0x180003829  pop     rsi
0x18000382a  pop     rbx
0x18000382b  pop     rbp
0x18000382c  retn
0x18000382d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003832  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003838  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
