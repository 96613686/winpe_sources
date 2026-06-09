# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180047568`
- end: `0x18004780e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800409c4`

## callees

- `0x180036918`
- `0x180039630`
- `0x180043c30`
- `0x1800446fc`
- `0x180047568`
- `0x18004871c`
- `0x18004a154`
- `0x18006f010`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004762e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004762e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180047723`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180047723`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800477ad`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800477ad`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180047568  push    rbp
0x18004756a  push    rbx
0x18004756b  push    rsi
0x18004756c  push    rdi
0x18004756d  push    r12
0x18004756f  push    r14
0x180047571  push    r15
0x180047573  lea     rbp, [rsp-13D0h]
0x18004757b  mov     eax, 14D0h
0x180047580  call    _alloca_probe
0x180047585  sub     rsp, rax
0x180047588  mov     rax, cs:__security_cookie
0x18004758f  xor     rax, rsp
0x180047592  mov     [rbp+1400h+var_40], rax
0x180047599  mov     rsi, r8
0x18004759c  mov     edi, edx
0x18004759e  mov     rbx, rcx
0x1800475a1  mov     r14, [rbp+1400h+arg_28]
0x1800475a8  xor     edx, edx; Val
0x1800475aa  mov     r8d, 98h; Size
0x1800475b0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800475b5  call    memset_0
0x1800475ba  nop
0x1800475bb  xor     r12d, r12d
0x1800475be  mov     [rbp+1400h+OutputString], r12w
0x1800475c6  mov     [rbp+1400h+var_1440], r12b
0x1800475ca  mov     rdx, [rbp+1400h+arg_30]; int
0x1800475d1  mov     ecx, [rdx]; this
0x1800475d3  mov     [rsp+1500h+var_14D8], ecx
0x1800475d7  mov     eax, [rdx+4]
0x1800475da  mov     [rsp+1500h+var_14D4], eax
0x1800475de  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800475e3  mov     r15d, eax
0x1800475e6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800475ee  mov     ecx, r12d
0x1800475f1  lea     eax, [r12+8]
0x1800475f6  cmp     dword ptr [rdx+8], 1
0x1800475fa  cmovz   ecx, eax
0x1800475fd  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180047601  lea     ecx, [rax-7]
0x180047604  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004760c  inc     ecx
0x18004760e  mov     [rsp+1500h+var_14D0], ecx
0x180047612  mov     rcx, [rbp+1400h+arg_38]
0x180047619  test    rcx, rcx
0x18004761c  jz      short loc_180047629
0x18004761e  cmp     [rcx], r12w
0x180047622  mov     [rsp+1500h+var_14C8], rcx
0x180047627  jnz     short loc_18004762E
0x180047629  mov     [rsp+1500h+var_14C8], r12
0x18004762e  call    cs:__imp_GetCurrentThreadId
0x180047634  mov     [rsp+1500h+var_14C0], eax
0x180047638  mov     [rsp+1500h+var_14A8], rsi
0x18004763d  mov     [rsp+1500h+var_14A0], edi
0x180047641  mov     [rsp+1500h+var_149C], r15d
0x180047646  mov     [rsp+1500h+var_14B8], r12
0x18004764b  mov     [rsp+1500h+var_14B0], r12
0x180047650  mov     [rbp+1400h+var_1458], r14
0x180047654  mov     [rbp+1400h+var_1450], rbx
0x180047658  mov     [rsp+1500h+var_1498], r12
0x18004765d  xorps   xmm0, xmm0
0x180047660  xor     eax, eax
0x180047662  movups  [rbp+1400h+var_1478], xmm0
0x180047666  mov     [rbp+1400h+var_1468], rax
0x18004766a  xorps   xmm1, xmm1
0x18004766d  movups  [rsp+1500h+var_1490], xmm1
0x180047672  mov     [rbp+1400h+var_1480], rax
0x180047676  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004767d  test    rax, rax
0x180047680  jz      short loc_18004768D
0x180047682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047687  mov     [rbp+1400h+var_1460], rax
0x18004768b  jmp     short loc_180047691
0x18004768d  mov     [rbp+1400h+var_1460], r12
0x180047691  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180047698  test    rax, rax
0x18004769b  jz      short loc_1800476A7
0x18004769d  lea     rcx, [rsp+1500h+var_14E0]
0x1800476a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476a7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800476ae  test    rax, rax
0x1800476b1  jz      short loc_1800476C7
0x1800476b3  mov     r8d, 400h
0x1800476b9  lea     rdx, [rbp+1400h+var_1440]
0x1800476bd  lea     rcx, [rsp+1500h+var_14E0]
0x1800476c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800476ce  test    rax, rax
0x1800476d1  jz      short loc_1800476DD
0x1800476d3  lea     rcx, [rsp+1500h+var_14E0]
0x1800476d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476dd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800476e4  test    rax, rax
0x1800476e7  jz      short loc_1800476FA
0x1800476e9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800476ee  jnz     short loc_1800476FA
0x1800476f0  lea     rcx, [rsp+1500h+var_14E0]
0x1800476f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800476fa  cmp     [rsp+1500h+var_14D8], r12d
0x1800476ff  jge     loc_180047808
0x180047705  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18004770c  jnz     short loc_18004772D
0x18004770e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180047715  test    rax, rax
0x180047718  jz      short loc_180047723
0x18004771a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004771f  test    al, al
0x180047721  jmp     short loc_18004772B
0x180047723  call    cs:__imp_IsDebuggerPresent
0x180047729  test    eax, eax
0x18004772b  jz      short loc_180047734
0x18004772d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180047732  jz      short loc_18004775A
0x180047734  mov     rax, cs:g_pfnResultLoggingCallback
0x18004773b  test    rax, rax
0x18004773e  jz      short loc_1800477B3
0x180047740  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180047747  jnz     short loc_1800477B3
0x180047749  xor     r8d, r8d
0x18004774c  xor     edx, edx
0x18004774e  lea     rcx, [rsp+1500h+var_14E0]
0x180047753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047758  jmp     short loc_1800477B3
0x18004775a  mov     ebx, 800h
0x18004775f  mov     rax, cs:g_pfnResultLoggingCallback
0x180047766  test    rax, rax
0x180047769  jz      short loc_180047788
0x18004776b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180047772  jnz     short loc_180047788
0x180047774  mov     r8d, ebx
0x180047777  lea     rdx, [rbp+1400h+OutputString]
0x18004777e  lea     rcx, [rsp+1500h+var_14E0]
0x180047783  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180047788  cmp     [rbp+1400h+OutputString], r12w
0x180047790  jnz     short loc_1800477A6
0x180047792  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180047797  mov     rdx, rbx; unsigned __int16 *
0x18004779a  lea     rcx, [rbp+1400h+OutputString]; this
0x1800477a1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800477a6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800477ad  call    cs:__imp_OutputDebugStringW
0x1800477b3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800477b8  jnz     short loc_1800477C3
0x1800477ba  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800477c1  jz      short loc_1800477D5
0x1800477c3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800477ca  test    rax, rax
0x1800477cd  jz      short loc_1800477D5
0x1800477cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800477d4  nop
0x1800477d5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800477da  jnz     short loc_1800477FD
0x1800477dc  mov     rcx, [rbp+1400h+var_40]
0x1800477e3  xor     rcx, rsp; StackCookie
0x1800477e6  call    __security_check_cookie
0x1800477eb  add     rsp, 14D0h
0x1800477f2  pop     r15
0x1800477f4  pop     r14
0x1800477f6  pop     r12
0x1800477f8  pop     rdi
0x1800477f9  pop     rsi
0x1800477fa  pop     rbx
0x1800477fb  pop     rbp
0x1800477fc  retn
0x1800477fd  lea     rcx, [rsp+1500h+var_14E0]; this
0x180047802  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180047808  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
