# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006f08`
- end: `0x1800071ae`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180006618`

## callees

- `0x180003ca0`
- `0x18000495c`
- `0x180006f08`
- `0x18000cc28`
- `0x18000fa38`
- `0x1800123f8`
- `0x1800126ec`
- `0x180056f80`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006fce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800070c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800070c3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000714d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000714d`

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
0x180006f08  push    rbp
0x180006f0a  push    rbx
0x180006f0b  push    rsi
0x180006f0c  push    rdi
0x180006f0d  push    r12
0x180006f0f  push    r14
0x180006f11  push    r15
0x180006f13  lea     rbp, [rsp-13D0h]
0x180006f1b  mov     eax, 14D0h
0x180006f20  call    _alloca_probe
0x180006f25  sub     rsp, rax
0x180006f28  mov     rax, cs:__security_cookie
0x180006f2f  xor     rax, rsp
0x180006f32  mov     [rbp+1400h+var_40], rax
0x180006f39  mov     rsi, r8
0x180006f3c  mov     edi, edx
0x180006f3e  mov     rbx, rcx
0x180006f41  mov     r14, [rbp+1400h+arg_28]
0x180006f48  xor     edx, edx; Val
0x180006f4a  mov     r8d, 98h; Size
0x180006f50  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006f55  call    memset_0
0x180006f5a  nop
0x180006f5b  xor     r12d, r12d
0x180006f5e  mov     [rbp+1400h+OutputString], r12w
0x180006f66  mov     [rbp+1400h+var_1440], r12b
0x180006f6a  mov     rdx, [rbp+1400h+arg_30]; int
0x180006f71  mov     ecx, [rdx]; this
0x180006f73  mov     [rsp+1500h+var_14D8], ecx
0x180006f77  mov     eax, [rdx+4]
0x180006f7a  mov     [rsp+1500h+var_14D4], eax
0x180006f7e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006f83  mov     r15d, eax
0x180006f86  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006f8e  mov     ecx, r12d
0x180006f91  lea     eax, [r12+8]
0x180006f96  cmp     dword ptr [rdx+8], 1
0x180006f9a  cmovz   ecx, eax
0x180006f9d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006fa1  lea     ecx, [rax-7]
0x180006fa4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006fac  inc     ecx
0x180006fae  mov     [rsp+1500h+var_14D0], ecx
0x180006fb2  mov     rcx, [rbp+1400h+arg_38]
0x180006fb9  test    rcx, rcx
0x180006fbc  jz      short loc_180006FC9
0x180006fbe  cmp     [rcx], r12w
0x180006fc2  mov     [rsp+1500h+var_14C8], rcx
0x180006fc7  jnz     short loc_180006FCE
0x180006fc9  mov     [rsp+1500h+var_14C8], r12
0x180006fce  call    cs:__imp_GetCurrentThreadId
0x180006fd4  mov     [rsp+1500h+var_14C0], eax
0x180006fd8  mov     [rsp+1500h+var_14A8], rsi
0x180006fdd  mov     [rsp+1500h+var_14A0], edi
0x180006fe1  mov     [rsp+1500h+var_149C], r15d
0x180006fe6  mov     [rsp+1500h+var_14B8], r12
0x180006feb  mov     [rsp+1500h+var_14B0], r12
0x180006ff0  mov     [rbp+1400h+var_1458], r14
0x180006ff4  mov     [rbp+1400h+var_1450], rbx
0x180006ff8  mov     [rsp+1500h+var_1498], r12
0x180006ffd  xorps   xmm0, xmm0
0x180007000  xor     eax, eax
0x180007002  movups  [rbp+1400h+var_1478], xmm0
0x180007006  mov     [rbp+1400h+var_1468], rax
0x18000700a  xorps   xmm1, xmm1
0x18000700d  movups  [rsp+1500h+var_1490], xmm1
0x180007012  mov     [rbp+1400h+var_1480], rax
0x180007016  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000701d  test    rax, rax
0x180007020  jz      short loc_18000702D
0x180007022  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007027  mov     [rbp+1400h+var_1460], rax
0x18000702b  jmp     short loc_180007031
0x18000702d  mov     [rbp+1400h+var_1460], r12
0x180007031  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007038  test    rax, rax
0x18000703b  jz      short loc_180007047
0x18000703d  lea     rcx, [rsp+1500h+var_14E0]
0x180007042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007047  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000704e  test    rax, rax
0x180007051  jz      short loc_180007067
0x180007053  mov     r8d, 400h
0x180007059  lea     rdx, [rbp+1400h+var_1440]
0x18000705d  lea     rcx, [rsp+1500h+var_14E0]
0x180007062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007067  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000706e  test    rax, rax
0x180007071  jz      short loc_18000707D
0x180007073  lea     rcx, [rsp+1500h+var_14E0]
0x180007078  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000707d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007084  test    rax, rax
0x180007087  jz      short loc_18000709A
0x180007089  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000708e  jnz     short loc_18000709A
0x180007090  lea     rcx, [rsp+1500h+var_14E0]
0x180007095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709a  cmp     [rsp+1500h+var_14D8], r12d
0x18000709f  jge     loc_1800071A8
0x1800070a5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800070ac  jnz     short loc_1800070CD
0x1800070ae  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800070b5  test    rax, rax
0x1800070b8  jz      short loc_1800070C3
0x1800070ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070bf  test    al, al
0x1800070c1  jmp     short loc_1800070CB
0x1800070c3  call    cs:__imp_IsDebuggerPresent
0x1800070c9  test    eax, eax
0x1800070cb  jz      short loc_1800070D4
0x1800070cd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800070d2  jz      short loc_1800070FA
0x1800070d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800070db  test    rax, rax
0x1800070de  jz      short loc_180007153
0x1800070e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800070e7  jnz     short loc_180007153
0x1800070e9  xor     r8d, r8d
0x1800070ec  xor     edx, edx
0x1800070ee  lea     rcx, [rsp+1500h+var_14E0]
0x1800070f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f8  jmp     short loc_180007153
0x1800070fa  mov     ebx, 800h
0x1800070ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180007106  test    rax, rax
0x180007109  jz      short loc_180007128
0x18000710b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007112  jnz     short loc_180007128
0x180007114  mov     r8d, ebx
0x180007117  lea     rdx, [rbp+1400h+OutputString]
0x18000711e  lea     rcx, [rsp+1500h+var_14E0]
0x180007123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007128  cmp     [rbp+1400h+OutputString], r12w
0x180007130  jnz     short loc_180007146
0x180007132  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180007137  mov     rdx, rbx; unsigned __int16 *
0x18000713a  lea     rcx, [rbp+1400h+OutputString]; this
0x180007141  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007146  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000714d  call    cs:__imp_OutputDebugStringW
0x180007153  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180007158  jnz     short loc_180007163
0x18000715a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007161  jz      short loc_180007175
0x180007163  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000716a  test    rax, rax
0x18000716d  jz      short loc_180007175
0x18000716f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007174  nop
0x180007175  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000717a  jnz     short loc_18000719D
0x18000717c  mov     rcx, [rbp+1400h+var_40]
0x180007183  xor     rcx, rsp; StackCookie
0x180007186  call    __security_check_cookie
0x18000718b  add     rsp, 14D0h
0x180007192  pop     r15
0x180007194  pop     r14
0x180007196  pop     r12
0x180007198  pop     rdi
0x180007199  pop     rsi
0x18000719a  pop     rbx
0x18000719b  pop     rbp
0x18000719c  retn
0x18000719d  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800071a2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800071a8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
