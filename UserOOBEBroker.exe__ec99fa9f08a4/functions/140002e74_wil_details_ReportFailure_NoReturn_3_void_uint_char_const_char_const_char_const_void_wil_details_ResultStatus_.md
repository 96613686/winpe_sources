# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002e74`
- end: `0x1400030ed`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002be4`

## callees

- `0x14000295f`
- `0x140002e74`
- `0x140004284`
- `0x140004a24`
- `0x140005190`
- `0x140006060`
- `0x14000e280`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002f2d`
- `KERNEL32!GetCurrentThreadId` at `0x140002f2d`
- `KERNEL32!OutputDebugStringW` at `0x1400030ba`
- `KERNEL32!OutputDebugStringW` at `0x1400030ba`
- `KERNEL32!IsDebuggerPresent` at `0x140003030`
- `KERNEL32!IsDebuggerPresent` at `0x140003030`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x140002e74  mov     [rsp-8+arg_18], rbx
0x140002e79  push    rbp
0x140002e7a  push    rsi
0x140002e7b  push    rdi
0x140002e7c  push    r12
0x140002e7e  push    r13
0x140002e80  push    r14
0x140002e82  push    r15
0x140002e84  lea     rbp, [rsp-13C0h]
0x140002e8c  mov     eax, 14C0h
0x140002e91  call    _alloca_probe
0x140002e96  sub     rsp, rax
0x140002e99  mov     r14, r8
0x140002e9c  mov     esi, edx
0x140002e9e  mov     rdi, rcx
0x140002ea1  mov     r15, [rbp+13F0h+arg_28]
0x140002ea8  xor     edx, edx; Val
0x140002eaa  mov     r8d, 98h; Size
0x140002eb0  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140002eb5  call    memset_0
0x140002eba  nop
0x140002ebb  xor     r13d, r13d
0x140002ebe  mov     [rbp+13F0h+OutputString], r13w
0x140002ec6  mov     [rbp+13F0h+var_1430], r13b
0x140002eca  mov     rbx, [rbp+13F0h+arg_30]
0x140002ed1  mov     ecx, [rbx]; this
0x140002ed3  mov     [rsp+14F0h+var_14C8], ecx
0x140002ed7  mov     eax, [rbx+4]
0x140002eda  mov     [rsp+14F0h+var_14C4], eax
0x140002ede  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002ee3  mov     r12d, eax
0x140002ee6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140002eee  mov     ecx, r13d
0x140002ef1  lea     eax, [r13+8]
0x140002ef5  cmp     dword ptr [rbx+8], 1
0x140002ef9  cmovz   ecx, eax
0x140002efc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002f00  lea     ecx, [rax-7]
0x140002f03  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002f0b  inc     ecx
0x140002f0d  mov     [rsp+14F0h+var_14C0], ecx
0x140002f11  mov     rcx, [rbp+13F0h+arg_38]
0x140002f18  test    rcx, rcx
0x140002f1b  jz      short loc_140002F28
0x140002f1d  cmp     [rcx], r13w
0x140002f21  mov     [rsp+14F0h+var_14B8], rcx
0x140002f26  jnz     short loc_140002F2D
0x140002f28  mov     [rsp+14F0h+var_14B8], r13
0x140002f2d  call    cs:__imp_GetCurrentThreadId
0x140002f33  mov     [rsp+14F0h+var_14B0], eax
0x140002f37  mov     [rsp+14F0h+var_1498], r14
0x140002f3c  mov     [rsp+14F0h+var_1490], esi
0x140002f40  mov     [rsp+14F0h+var_148C], r12d
0x140002f45  mov     [rsp+14F0h+var_14A8], r13
0x140002f4a  mov     [rsp+14F0h+var_14A0], r13
0x140002f4f  mov     [rbp+13F0h+var_1448], r15
0x140002f53  mov     [rbp+13F0h+var_1440], rdi
0x140002f57  mov     [rsp+14F0h+var_1488], r13
0x140002f5c  xorps   xmm0, xmm0
0x140002f5f  xor     eax, eax
0x140002f61  movups  [rbp+13F0h+var_1468], xmm0
0x140002f65  mov     [rbp+13F0h+var_1458], rax
0x140002f69  xorps   xmm1, xmm1
0x140002f6c  movups  [rsp+14F0h+var_1480], xmm1
0x140002f71  mov     [rbp+13F0h+var_1470], rax
0x140002f75  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002f7c  test    rax, rax
0x140002f7f  jz      short loc_140002F8C
0x140002f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002f86  mov     [rbp+13F0h+var_1450], rax
0x140002f8a  jmp     short loc_140002F90
0x140002f8c  mov     [rbp+13F0h+var_1450], r13
0x140002f90  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002f97  test    rax, rax
0x140002f9a  jz      short loc_140002FA6
0x140002f9c  lea     rcx, [rsp+14F0h+var_14D0]
0x140002fa1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fa6  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002fad  test    rax, rax
0x140002fb0  jz      short loc_140002FC6
0x140002fb2  mov     r8d, 400h
0x140002fb8  lea     rdx, [rbp+13F0h+var_1430]
0x140002fbc  lea     rcx, [rsp+14F0h+var_14D0]
0x140002fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fc6  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002fcd  test    rax, rax
0x140002fd0  jz      short loc_140002FDC
0x140002fd2  lea     rcx, [rsp+14F0h+var_14D0]
0x140002fd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fdc  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002fe3  test    rax, rax
0x140002fe6  jz      short loc_140002FF9
0x140002fe8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002fed  jnz     short loc_140002FF9
0x140002fef  lea     rcx, [rsp+14F0h+var_14D0]
0x140002ff4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002ff9  cmp     [rsp+14F0h+var_14C8], r13d
0x140002ffe  jl      short loc_140003012
0x140003000  mov     ecx, 8000FFFFh; this
0x140003005  mov     [rsp+14F0h+var_14C8], ecx
0x140003009  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000300e  mov     [rsp+14F0h+var_14C4], eax
0x140003012  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003019  jnz     short loc_14000303A
0x14000301b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003022  test    rax, rax
0x140003025  jz      short loc_140003030
0x140003027  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000302c  test    al, al
0x14000302e  jmp     short loc_140003038
0x140003030  call    cs:__imp_IsDebuggerPresent
0x140003036  test    eax, eax
0x140003038  jz      short loc_140003041
0x14000303a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000303f  jz      short loc_140003067
0x140003041  mov     rax, cs:g_pfnResultLoggingCallback
0x140003048  test    rax, rax
0x14000304b  jz      short loc_1400030C0
0x14000304d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003054  jnz     short loc_1400030C0
0x140003056  xor     r8d, r8d
0x140003059  xor     edx, edx
0x14000305b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003065  jmp     short loc_1400030C0
0x140003067  mov     ebx, 800h
0x14000306c  mov     rax, cs:g_pfnResultLoggingCallback
0x140003073  test    rax, rax
0x140003076  jz      short loc_140003095
0x140003078  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000307f  jnz     short loc_140003095
0x140003081  mov     r8d, ebx
0x140003084  lea     rdx, [rbp+13F0h+OutputString]
0x14000308b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003095  cmp     [rbp+13F0h+OutputString], r13w
0x14000309d  jnz     short loc_1400030B3
0x14000309f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400030a4  mov     rdx, rbx; unsigned __int16 *
0x1400030a7  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400030ae  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400030b3  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400030ba  call    cs:__imp_OutputDebugStringW
0x1400030c0  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400030c5  jnz     short loc_1400030D0
0x1400030c7  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400030ce  jz      short loc_1400030E2
0x1400030d0  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400030d7  test    rax, rax
0x1400030da  jz      short loc_1400030E2
0x1400030dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400030e1  nop
0x1400030e2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400030e7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
