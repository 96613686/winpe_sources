# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003528`
- end: `0x1800037ce`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800031a8`

## callees

- `0x180001dd0`
- `0x1800029cc`
- `0x180003528`
- `0x180004fe4`
- `0x180006c9c`
- `0x180008778`
- `0x180008984`
- `0x180057130`
- `0x18005f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036e3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036e3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000376d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000376d`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
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
0x180003528  push    rbp
0x18000352a  push    rbx
0x18000352b  push    rsi
0x18000352c  push    rdi
0x18000352d  push    r12
0x18000352f  push    r14
0x180003531  push    r15
0x180003533  lea     rbp, [rsp-13D0h]
0x18000353b  mov     eax, 14D0h
0x180003540  call    _alloca_probe
0x180003545  sub     rsp, rax
0x180003548  mov     rax, cs:__security_cookie
0x18000354f  xor     rax, rsp
0x180003552  mov     [rbp+1400h+var_40], rax
0x180003559  mov     rsi, r8
0x18000355c  mov     edi, edx
0x18000355e  mov     rbx, rcx
0x180003561  mov     r14, [rbp+1400h+arg_28]
0x180003568  xor     edx, edx; Val
0x18000356a  mov     r8d, 98h; Size
0x180003570  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003575  call    memset_0
0x18000357a  nop
0x18000357b  xor     r12d, r12d
0x18000357e  mov     [rbp+1400h+OutputString], r12w
0x180003586  mov     [rbp+1400h+var_1440], r12b
0x18000358a  mov     rdx, [rbp+1400h+arg_30]; int
0x180003591  mov     ecx, [rdx]; this
0x180003593  mov     [rsp+1500h+var_14D8], ecx
0x180003597  mov     eax, [rdx+4]
0x18000359a  mov     [rsp+1500h+var_14D4], eax
0x18000359e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800035a3  mov     r15d, eax
0x1800035a6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800035ae  mov     ecx, r12d
0x1800035b1  lea     eax, [r12+8]
0x1800035b6  cmp     dword ptr [rdx+8], 1
0x1800035ba  cmovz   ecx, eax
0x1800035bd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800035c1  lea     ecx, [rax-7]
0x1800035c4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800035cc  inc     ecx
0x1800035ce  mov     [rsp+1500h+var_14D0], ecx
0x1800035d2  mov     rcx, [rbp+1400h+arg_38]
0x1800035d9  test    rcx, rcx
0x1800035dc  jz      short loc_1800035E9
0x1800035de  cmp     [rcx], r12w
0x1800035e2  mov     [rsp+1500h+var_14C8], rcx
0x1800035e7  jnz     short loc_1800035EE
0x1800035e9  mov     [rsp+1500h+var_14C8], r12
0x1800035ee  call    cs:__imp_GetCurrentThreadId
0x1800035f4  mov     [rsp+1500h+var_14C0], eax
0x1800035f8  mov     [rsp+1500h+var_14A8], rsi
0x1800035fd  mov     [rsp+1500h+var_14A0], edi
0x180003601  mov     [rsp+1500h+var_149C], r15d
0x180003606  mov     [rsp+1500h+var_14B8], r12
0x18000360b  mov     [rsp+1500h+var_14B0], r12
0x180003610  mov     [rbp+1400h+var_1458], r14
0x180003614  mov     [rbp+1400h+var_1450], rbx
0x180003618  mov     [rsp+1500h+var_1498], r12
0x18000361d  xorps   xmm0, xmm0
0x180003620  xor     eax, eax
0x180003622  movups  [rbp+1400h+var_1478], xmm0
0x180003626  mov     [rbp+1400h+var_1468], rax
0x18000362a  xorps   xmm1, xmm1
0x18000362d  movups  [rsp+1500h+var_1490], xmm1
0x180003632  mov     [rbp+1400h+var_1480], rax
0x180003636  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000363d  test    rax, rax
0x180003640  jz      short loc_18000364D
0x180003642  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003647  mov     [rbp+1400h+var_1460], rax
0x18000364b  jmp     short loc_180003651
0x18000364d  mov     [rbp+1400h+var_1460], r12
0x180003651  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003658  test    rax, rax
0x18000365b  jz      short loc_180003667
0x18000365d  lea     rcx, [rsp+1500h+var_14E0]
0x180003662  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003667  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000366e  test    rax, rax
0x180003671  jz      short loc_180003687
0x180003673  mov     r8d, 400h
0x180003679  lea     rdx, [rbp+1400h+var_1440]
0x18000367d  lea     rcx, [rsp+1500h+var_14E0]
0x180003682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003687  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000368e  test    rax, rax
0x180003691  jz      short loc_18000369D
0x180003693  lea     rcx, [rsp+1500h+var_14E0]
0x180003698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000369d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800036a4  test    rax, rax
0x1800036a7  jz      short loc_1800036BA
0x1800036a9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800036ae  jnz     short loc_1800036BA
0x1800036b0  lea     rcx, [rsp+1500h+var_14E0]
0x1800036b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ba  cmp     [rsp+1500h+var_14D8], r12d
0x1800036bf  jge     loc_1800037C8
0x1800036c5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800036cc  jnz     short loc_1800036ED
0x1800036ce  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800036d5  test    rax, rax
0x1800036d8  jz      short loc_1800036E3
0x1800036da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036df  test    al, al
0x1800036e1  jmp     short loc_1800036EB
0x1800036e3  call    cs:__imp_IsDebuggerPresent
0x1800036e9  test    eax, eax
0x1800036eb  jz      short loc_1800036F4
0x1800036ed  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800036f2  jz      short loc_18000371A
0x1800036f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036fb  test    rax, rax
0x1800036fe  jz      short loc_180003773
0x180003700  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003707  jnz     short loc_180003773
0x180003709  xor     r8d, r8d
0x18000370c  xor     edx, edx
0x18000370e  lea     rcx, [rsp+1500h+var_14E0]
0x180003713  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003718  jmp     short loc_180003773
0x18000371a  mov     ebx, 800h
0x18000371f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003726  test    rax, rax
0x180003729  jz      short loc_180003748
0x18000372b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003732  jnz     short loc_180003748
0x180003734  mov     r8d, ebx
0x180003737  lea     rdx, [rbp+1400h+OutputString]
0x18000373e  lea     rcx, [rsp+1500h+var_14E0]
0x180003743  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003748  cmp     [rbp+1400h+OutputString], r12w
0x180003750  jnz     short loc_180003766
0x180003752  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003757  mov     rdx, rbx; unsigned __int16 *
0x18000375a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003761  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003766  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000376d  call    cs:__imp_OutputDebugStringW
0x180003773  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003778  jnz     short loc_180003783
0x18000377a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003781  jz      short loc_180003795
0x180003783  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000378a  test    rax, rax
0x18000378d  jz      short loc_180003795
0x18000378f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003794  nop
0x180003795  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000379a  jnz     short loc_1800037BD
0x18000379c  mov     rcx, [rbp+1400h+var_40]
0x1800037a3  xor     rcx, rsp; StackCookie
0x1800037a6  call    __security_check_cookie
0x1800037ab  add     rsp, 14D0h
0x1800037b2  pop     r15
0x1800037b4  pop     r14
0x1800037b6  pop     r12
0x1800037b8  pop     rdi
0x1800037b9  pop     rsi
0x1800037ba  pop     rbx
0x1800037bb  pop     rbp
0x1800037bc  retn
0x1800037bd  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800037c2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800037c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
