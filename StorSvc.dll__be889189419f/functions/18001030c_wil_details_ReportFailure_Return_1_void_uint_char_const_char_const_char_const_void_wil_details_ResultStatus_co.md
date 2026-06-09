# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18001030c`
- end: `0x180010591`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `645`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000ff94`

## callees

- `0x18000d030`
- `0x18000ddb0`
- `0x18001030c`
- `0x180011364`
- `0x180011d50`
- `0x180012520`
- `0x180013198`
- `0x180013354`
- `0x18007d490`
- `0x18008a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103d1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800103d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001050b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001050b`

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
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  bool v14; // zf
  int v15; // r15d
  int v16; // ecx
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // rdx
  __int64 v20; // rcx
  const struct wil::FailureInfo *v21; // r9
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh]
  int v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v26; // [rsp+30h] [rbp-D0h]
  _WORD *v27; // [rsp+38h] [rbp-C8h]
  DWORD v28; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+64h] [rbp-9Ch]
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int128 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  char v42[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v22, 0, 0x98u);
  OutputString[0] = 0;
  v42[0] = 0;
  v11 = a7[1];
  v24 = *a7;
  v25 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v24, (int)a7);
  v14 = *(_DWORD *)(v13 + 8) == 1;
  v15 = v12;
  v22 = 1;
  v16 = 0;
  if ( v14 )
    v16 = 8;
  v23 = v16;
  v26 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v27 = a8, !*a8) )
    v27 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v31 = a3;
  v28 = CurrentThreadId;
  v32 = a2;
  v38 = 0;
  v36 = 0;
  v33 = v15;
  v29 = 0;
  v30 = 0;
  v40 = a6;
  v41 = a1;
  v34 = 0;
  v37 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v22);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v22, v42, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v22);
  if ( wil::details::g_pfnOriginateCallback && (v23 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v22);
  if ( v24 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::details::IsDebuggerPresent(v18) || (v23 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v22, v21);
    OutputDebugStringW(OutputString);
  }
  if ( ((v23 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v20);
  if ( (v23 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v22, v19);
}

```

## disassembly

```asm
0x18001030c  push    rbp
0x18001030e  push    rbx
0x18001030f  push    rsi
0x180010310  push    rdi
0x180010311  push    r12
0x180010313  push    r14
0x180010315  push    r15
0x180010317  lea     rbp, [rsp-13D0h]
0x18001031f  mov     eax, 14D0h
0x180010324  call    _alloca_probe
0x180010329  sub     rsp, rax
0x18001032c  mov     rax, cs:__security_cookie
0x180010333  xor     rax, rsp
0x180010336  mov     [rbp+1400h+var_40], rax
0x18001033d  mov     r14, [rbp+1400h+arg_28]
0x180010344  mov     rsi, r8
0x180010347  mov     edi, edx
0x180010349  mov     rbx, rcx
0x18001034c  xor     edx, edx; Val
0x18001034e  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180010353  mov     r8d, 98h; Size
0x180010359  call    memset_0
0x18001035e  mov     rdx, [rbp+1400h+arg_30]; int
0x180010365  xor     r12d, r12d
0x180010368  mov     [rbp+1400h+OutputString], r12w
0x180010370  mov     [rbp+1400h+var_1440], r12b
0x180010374  mov     ecx, [rdx]; this
0x180010376  mov     eax, [rdx+4]
0x180010379  mov     [rsp+1500h+var_14D8], ecx
0x18001037d  mov     [rsp+1500h+var_14D4], eax
0x180010381  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180010386  cmp     dword ptr [rdx+8], 1
0x18001038a  mov     r15d, eax
0x18001038d  lea     eax, [r12+8]
0x180010392  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18001039a  mov     ecx, r12d
0x18001039d  cmovz   ecx, eax
0x1800103a0  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800103a4  lea     ecx, [rax-7]
0x1800103a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800103af  inc     ecx
0x1800103b1  mov     [rsp+1500h+var_14D0], ecx
0x1800103b5  mov     rcx, [rbp+1400h+arg_38]
0x1800103bc  test    rcx, rcx
0x1800103bf  jz      short loc_1800103CC
0x1800103c1  mov     [rsp+1500h+var_14C8], rcx
0x1800103c6  cmp     [rcx], r12w
0x1800103ca  jnz     short loc_1800103D1
0x1800103cc  mov     [rsp+1500h+var_14C8], r12
0x1800103d1  call    cs:__imp_GetCurrentThreadId
0x1800103d7  xorps   xmm0, xmm0
0x1800103da  mov     [rsp+1500h+var_14A8], rsi
0x1800103df  mov     [rsp+1500h+var_14C0], eax
0x1800103e3  xorps   xmm1, xmm1
0x1800103e6  xor     eax, eax
0x1800103e8  mov     [rsp+1500h+var_14A0], edi
0x1800103ec  mov     [rbp+1400h+var_1468], rax
0x1800103f0  mov     [rbp+1400h+var_1480], rax
0x1800103f4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800103fb  mov     [rsp+1500h+var_149C], r15d
0x180010400  mov     [rsp+1500h+var_14B8], r12
0x180010405  mov     [rsp+1500h+var_14B0], r12
0x18001040a  mov     [rbp+1400h+var_1458], r14
0x18001040e  mov     [rbp+1400h+var_1450], rbx
0x180010412  mov     [rsp+1500h+var_1498], r12
0x180010417  movups  [rbp+1400h+var_1478], xmm0
0x18001041b  movups  [rsp+1500h+var_1490], xmm1
0x180010420  test    rax, rax
0x180010423  jz      short loc_180010430
0x180010425  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001042a  mov     [rbp+1400h+var_1460], rax
0x18001042e  jmp     short loc_180010434
0x180010430  mov     [rbp+1400h+var_1460], r12
0x180010434  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001043b  test    rax, rax
0x18001043e  jz      short loc_18001044A
0x180010440  lea     rcx, [rsp+1500h+var_14E0]
0x180010445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001044a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010451  test    rax, rax
0x180010454  jz      short loc_18001046A
0x180010456  mov     r8d, 400h
0x18001045c  lea     rdx, [rbp+1400h+var_1440]
0x180010460  lea     rcx, [rsp+1500h+var_14E0]
0x180010465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001046a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010471  test    rax, rax
0x180010474  jz      short loc_180010480
0x180010476  lea     rcx, [rsp+1500h+var_14E0]
0x18001047b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010480  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010487  test    rax, rax
0x18001048a  jz      short loc_18001049D
0x18001048c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180010491  jnz     short loc_18001049D
0x180010493  lea     rcx, [rsp+1500h+var_14E0]
0x180010498  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001049d  cmp     [rsp+1500h+var_14D8], r12d
0x1800104a2  jge     loc_180010580
0x1800104a8  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x1800104ad  test    al, al
0x1800104af  jz      short loc_180010513
0x1800104b1  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800104b6  jnz     short loc_180010513
0x1800104b8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800104bf  mov     ebx, 800h
0x1800104c4  test    rax, rax
0x1800104c7  jz      short loc_1800104E6
0x1800104c9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800104d0  jnz     short loc_1800104E6
0x1800104d2  mov     r8d, ebx
0x1800104d5  lea     rdx, [rbp+1400h+OutputString]
0x1800104dc  lea     rcx, [rsp+1500h+var_14E0]
0x1800104e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104e6  cmp     [rbp+1400h+OutputString], r12w
0x1800104ee  jnz     short loc_180010504
0x1800104f0  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800104f5  mov     rdx, rbx; unsigned __int16 *
0x1800104f8  lea     rcx, [rbp+1400h+OutputString]; this
0x1800104ff  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010504  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18001050b  call    cs:__imp_OutputDebugStringW
0x180010511  jmp     short loc_180010537
0x180010513  mov     rax, cs:g_pfnResultLoggingCallback
0x18001051a  test    rax, rax
0x18001051d  jz      short loc_180010537
0x18001051f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180010526  jnz     short loc_180010537
0x180010528  xor     r8d, r8d
0x18001052b  lea     rcx, [rsp+1500h+var_14E0]
0x180010530  xor     edx, edx
0x180010532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010537  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18001053c  jnz     short loc_180010547
0x18001053e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180010545  jz      short loc_180010558
0x180010547  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001054e  test    rax, rax
0x180010551  jz      short loc_180010558
0x180010553  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010558  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18001055d  jnz     short loc_180010586
0x18001055f  mov     rcx, [rbp+1400h+var_40]
0x180010566  xor     rcx, rsp; StackCookie
0x180010569  call    __security_check_cookie
0x18001056e  add     rsp, 14D0h
0x180010575  pop     r15
0x180010577  pop     r14
0x180010579  pop     r12
0x18001057b  pop     rdi
0x18001057c  pop     rsi
0x18001057d  pop     rbx
0x18001057e  pop     rbp
0x18001057f  retn
0x180010580  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180010586  lea     rcx, [rsp+1500h+var_14E0]; this
0x18001058b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
