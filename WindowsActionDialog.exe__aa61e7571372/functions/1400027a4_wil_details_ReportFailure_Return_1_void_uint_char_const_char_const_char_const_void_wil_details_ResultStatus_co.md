# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1400027a4`
- end: `0x140002a3f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `667`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002004`

## callees

- `0x140001460`
- `0x140001f5c`
- `0x1400027a4`
- `0x1400046a4`
- `0x140006070`
- `0x1400074c0`
- `0x1400076dc`
- `0x1400092a0`
- `0x14000a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140002956`
- `KERNEL32!IsDebuggerPresent` at `0x140002956`
- `KERNEL32!OutputDebugStringW` at `0x1400029dd`
- `KERNEL32!OutputDebugStringW` at `0x1400029dd`
- `KERNEL32!GetCurrentThreadId` at `0x140002861`
- `KERNEL32!GetCurrentThreadId` at `0x140002861`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag5 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  __int64 v23; // [rsp+38h] [rbp-C8h]
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
  v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = a5;
  v26 = a4;
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
    wil::details::in1diag5::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x1400027a4  push    rbp
0x1400027a6  push    rbx
0x1400027a7  push    rsi
0x1400027a8  push    rdi
0x1400027a9  push    r12
0x1400027ab  push    r13
0x1400027ad  push    r14
0x1400027af  push    r15
0x1400027b1  lea     rbp, [rsp-13D8h]
0x1400027b9  mov     eax, 14D8h
0x1400027be  call    _alloca_probe
0x1400027c3  sub     rsp, rax
0x1400027c6  mov     rax, cs:__security_cookie
0x1400027cd  xor     rax, rsp
0x1400027d0  mov     [rbp+1410h+var_50], rax
0x1400027d7  mov     r13, r9
0x1400027da  mov     r15, r8
0x1400027dd  mov     r14d, edx
0x1400027e0  mov     r12, rcx
0x1400027e3  mov     rdi, [rbp+1410h+arg_20]
0x1400027ea  mov     rsi, [rbp+1410h+arg_28]
0x1400027f1  xor     edx, edx; Val
0x1400027f3  mov     r8d, 98h; Size
0x1400027f9  lea     rcx, [rsp+1510h+var_14F0]; void *
0x1400027fe  call    memset_0
0x140002803  nop
0x140002804  xor     eax, eax
0x140002806  mov     [rbp+1410h+OutputString], ax
0x14000280d  mov     [rbp+1410h+var_1450], al
0x140002810  mov     rdx, qword ptr [rbp+1410h+arg_30]; int
0x140002817  mov     ecx, [rdx]; this
0x140002819  mov     [rsp+1510h+var_14E8], ecx
0x14000281d  mov     eax, [rdx+4]
0x140002820  mov     [rsp+1510h+var_14E4], eax
0x140002824  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140002829  mov     ebx, eax
0x14000282b  mov     r8d, 1
0x140002831  mov     dword ptr [rsp+1510h+var_14F0], r8d
0x140002836  xor     ecx, ecx
0x140002838  lea     eax, [rcx+8]
0x14000283b  cmp     [rdx+8], r8d
0x14000283f  cmovz   ecx, eax
0x140002842  mov     dword ptr [rsp+1510h+var_14F0+4], ecx
0x140002846  mov     ecx, r8d
0x140002849  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002851  add     ecx, r8d
0x140002854  mov     [rsp+1510h+var_14E0], ecx
0x140002858  mov     [rsp+1510h+var_14D8], 0
0x140002861  call    cs:__imp_GetCurrentThreadId
0x140002867  mov     [rsp+1510h+var_14D0], eax
0x14000286b  mov     [rsp+1510h+var_14B8], r15
0x140002870  mov     [rsp+1510h+var_14B0], r14d
0x140002875  mov     [rsp+1510h+var_14AC], ebx
0x140002879  mov     [rsp+1510h+var_14C8], rdi
0x14000287e  mov     [rsp+1510h+var_14C0], r13
0x140002883  mov     [rbp+1410h+var_1468], rsi
0x140002887  mov     [rbp+1410h+var_1460], r12
0x14000288b  xor     ebx, ebx
0x14000288d  mov     [rsp+1510h+var_14A8], rbx
0x140002892  xorps   xmm0, xmm0
0x140002895  xor     eax, eax
0x140002897  movups  [rbp+1410h+var_1488], xmm0
0x14000289b  mov     [rbp+1410h+var_1478], rax
0x14000289f  xorps   xmm1, xmm1
0x1400028a2  movups  [rsp+1510h+var_14A0], xmm1
0x1400028a7  mov     [rbp+1410h+var_1490], rax
0x1400028ab  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400028b2  test    rax, rax
0x1400028b5  jz      short loc_1400028C2
0x1400028b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028bc  mov     [rbp+1410h+var_1470], rax
0x1400028c0  jmp     short loc_1400028C6
0x1400028c2  mov     [rbp+1410h+var_1470], rbx
0x1400028c6  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400028cd  test    rax, rax
0x1400028d0  jz      short loc_1400028DC
0x1400028d2  lea     rcx, [rsp+1510h+var_14F0]
0x1400028d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028dc  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400028e3  test    rax, rax
0x1400028e6  jz      short loc_1400028FC
0x1400028e8  mov     r8d, 400h
0x1400028ee  lea     rdx, [rbp+1410h+var_1450]
0x1400028f2  lea     rcx, [rsp+1510h+var_14F0]
0x1400028f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028fc  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002903  test    rax, rax
0x140002906  jz      short loc_140002912
0x140002908  lea     rcx, [rsp+1510h+var_14F0]
0x14000290d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002912  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002919  test    rax, rax
0x14000291c  jz      short loc_14000292F
0x14000291e  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140002923  jnz     short loc_14000292F
0x140002925  lea     rcx, [rsp+1510h+var_14F0]
0x14000292a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000292f  cmp     [rsp+1510h+var_14E8], ebx
0x140002933  jge     loc_140002A39
0x140002939  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x14000293f  jnz     short loc_140002960
0x140002941  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002948  test    rax, rax
0x14000294b  jz      short loc_140002956
0x14000294d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002952  test    al, al
0x140002954  jmp     short loc_14000295E
0x140002956  call    cs:__imp_IsDebuggerPresent
0x14000295c  test    eax, eax
0x14000295e  jz      short loc_140002967
0x140002960  test    byte ptr [rsp+1510h+var_14F0+4], 2
0x140002965  jz      short loc_14000298C
0x140002967  mov     rax, cs:g_pfnResultLoggingCallback
0x14000296e  test    rax, rax
0x140002971  jz      short loc_1400029E3
0x140002973  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x140002979  jnz     short loc_1400029E3
0x14000297b  xor     r8d, r8d
0x14000297e  xor     edx, edx
0x140002980  lea     rcx, [rsp+1510h+var_14F0]
0x140002985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000298a  jmp     short loc_1400029E3
0x14000298c  mov     edi, 800h
0x140002991  mov     rax, cs:g_pfnResultLoggingCallback
0x140002998  test    rax, rax
0x14000299b  jz      short loc_1400029B9
0x14000299d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x1400029a3  jnz     short loc_1400029B9
0x1400029a5  mov     r8d, edi
0x1400029a8  lea     rdx, [rbp+1410h+OutputString]
0x1400029af  lea     rcx, [rsp+1510h+var_14F0]
0x1400029b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029b9  cmp     [rbp+1410h+OutputString], bx
0x1400029c0  jnz     short loc_1400029D6
0x1400029c2  lea     r8, [rsp+1510h+var_14F0]; unsigned __int64
0x1400029c7  mov     rdx, rdi; unsigned __int16 *
0x1400029ca  lea     rcx, [rbp+1410h+OutputString]; this
0x1400029d1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400029d6  lea     rcx, [rbp+1410h+OutputString]; lpOutputString
0x1400029dd  call    cs:__imp_OutputDebugStringW
0x1400029e3  test    byte ptr [rsp+1510h+var_14F0+4], 4
0x1400029e8  jnz     short loc_1400029F2
0x1400029ea  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, bl; bool wil::g_fBreakOnFailure
0x1400029f0  jz      short loc_140002A04
0x1400029f2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400029f9  test    rax, rax
0x1400029fc  jz      short loc_140002A04
0x1400029fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a03  nop
0x140002a04  test    byte ptr [rsp+1510h+var_14F0+4], 1
0x140002a09  jnz     short loc_140002A2E
0x140002a0b  mov     rcx, [rbp+1410h+var_50]
0x140002a12  xor     rcx, rsp; StackCookie
0x140002a15  call    __security_check_cookie
0x140002a1a  add     rsp, 14D8h
0x140002a21  pop     r15
0x140002a23  pop     r14
0x140002a25  pop     r13
0x140002a27  pop     r12
0x140002a29  pop     rdi
0x140002a2a  pop     rsi
0x140002a2b  pop     rbx
0x140002a2c  pop     rbp
0x140002a2d  retn
0x140002a2e  lea     rcx, [rsp+1510h+var_14F0]; this
0x140002a33  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140002a39  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
```
