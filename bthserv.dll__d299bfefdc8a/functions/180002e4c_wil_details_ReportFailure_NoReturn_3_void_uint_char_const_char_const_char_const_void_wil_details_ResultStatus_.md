# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002e4c`
- end: `0x1800030c5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002bbc`

## callees

- `0x1800024ac`
- `0x180002e4c`
- `0x180005464`
- `0x180005c0c`
- `0x180006b90`
- `0x180009270`
- `0x180032bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f05`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f05`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003092`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003092`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003008`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003008`

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
0x180002e4c  mov     [rsp-8+arg_18], rbx
0x180002e51  push    rbp
0x180002e52  push    rsi
0x180002e53  push    rdi
0x180002e54  push    r12
0x180002e56  push    r13
0x180002e58  push    r14
0x180002e5a  push    r15
0x180002e5c  lea     rbp, [rsp-13C0h]
0x180002e64  mov     eax, 14C0h
0x180002e69  call    _alloca_probe
0x180002e6e  sub     rsp, rax
0x180002e71  mov     r14, r8
0x180002e74  mov     esi, edx
0x180002e76  mov     rdi, rcx
0x180002e79  mov     r15, [rbp+13F0h+arg_28]
0x180002e80  xor     edx, edx; Val
0x180002e82  mov     r8d, 98h; Size
0x180002e88  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002e8d  call    memset_0
0x180002e92  nop
0x180002e93  xor     r13d, r13d
0x180002e96  mov     [rbp+13F0h+OutputString], r13w
0x180002e9e  mov     [rbp+13F0h+var_1430], r13b
0x180002ea2  mov     rbx, [rbp+13F0h+arg_30]
0x180002ea9  mov     ecx, [rbx]; this
0x180002eab  mov     [rsp+14F0h+var_14C8], ecx
0x180002eaf  mov     eax, [rbx+4]
0x180002eb2  mov     [rsp+14F0h+var_14C4], eax
0x180002eb6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002ebb  mov     r12d, eax
0x180002ebe  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002ec6  mov     ecx, r13d
0x180002ec9  lea     eax, [r13+8]
0x180002ecd  cmp     dword ptr [rbx+8], 1
0x180002ed1  cmovz   ecx, eax
0x180002ed4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ed8  lea     ecx, [rax-7]
0x180002edb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002ee3  inc     ecx
0x180002ee5  mov     [rsp+14F0h+var_14C0], ecx
0x180002ee9  mov     rcx, [rbp+13F0h+arg_38]
0x180002ef0  test    rcx, rcx
0x180002ef3  jz      short loc_180002F00
0x180002ef5  cmp     [rcx], r13w
0x180002ef9  mov     [rsp+14F0h+var_14B8], rcx
0x180002efe  jnz     short loc_180002F05
0x180002f00  mov     [rsp+14F0h+var_14B8], r13
0x180002f05  call    cs:__imp_GetCurrentThreadId
0x180002f0b  mov     [rsp+14F0h+var_14B0], eax
0x180002f0f  mov     [rsp+14F0h+var_1498], r14
0x180002f14  mov     [rsp+14F0h+var_1490], esi
0x180002f18  mov     [rsp+14F0h+var_148C], r12d
0x180002f1d  mov     [rsp+14F0h+var_14A8], r13
0x180002f22  mov     [rsp+14F0h+var_14A0], r13
0x180002f27  mov     [rbp+13F0h+var_1448], r15
0x180002f2b  mov     [rbp+13F0h+var_1440], rdi
0x180002f2f  mov     [rsp+14F0h+var_1488], r13
0x180002f34  xorps   xmm0, xmm0
0x180002f37  xor     eax, eax
0x180002f39  movups  [rbp+13F0h+var_1468], xmm0
0x180002f3d  mov     [rbp+13F0h+var_1458], rax
0x180002f41  xorps   xmm1, xmm1
0x180002f44  movups  [rsp+14F0h+var_1480], xmm1
0x180002f49  mov     [rbp+13F0h+var_1470], rax
0x180002f4d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002f54  test    rax, rax
0x180002f57  jz      short loc_180002F64
0x180002f59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5e  mov     [rbp+13F0h+var_1450], rax
0x180002f62  jmp     short loc_180002F68
0x180002f64  mov     [rbp+13F0h+var_1450], r13
0x180002f68  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002f6f  test    rax, rax
0x180002f72  jz      short loc_180002F7E
0x180002f74  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002f85  test    rax, rax
0x180002f88  jz      short loc_180002F9E
0x180002f8a  mov     r8d, 400h
0x180002f90  lea     rdx, [rbp+13F0h+var_1430]
0x180002f94  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f9e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fa5  test    rax, rax
0x180002fa8  jz      short loc_180002FB4
0x180002faa  lea     rcx, [rsp+14F0h+var_14D0]
0x180002faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fbb  test    rax, rax
0x180002fbe  jz      short loc_180002FD1
0x180002fc0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002fc5  jnz     short loc_180002FD1
0x180002fc7  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fd1  cmp     [rsp+14F0h+var_14C8], r13d
0x180002fd6  jl      short loc_180002FEA
0x180002fd8  mov     ecx, 8000FFFFh; this
0x180002fdd  mov     [rsp+14F0h+var_14C8], ecx
0x180002fe1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002fe6  mov     [rsp+14F0h+var_14C4], eax
0x180002fea  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002ff1  jnz     short loc_180003012
0x180002ff3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ffa  test    rax, rax
0x180002ffd  jz      short loc_180003008
0x180002fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003004  test    al, al
0x180003006  jmp     short loc_180003010
0x180003008  call    cs:__imp_IsDebuggerPresent
0x18000300e  test    eax, eax
0x180003010  jz      short loc_180003019
0x180003012  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003017  jz      short loc_18000303F
0x180003019  mov     rax, cs:g_pfnResultLoggingCallback
0x180003020  test    rax, rax
0x180003023  jz      short loc_180003098
0x180003025  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000302c  jnz     short loc_180003098
0x18000302e  xor     r8d, r8d
0x180003031  xor     edx, edx
0x180003033  lea     rcx, [rsp+14F0h+var_14D0]
0x180003038  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000303d  jmp     short loc_180003098
0x18000303f  mov     ebx, 800h
0x180003044  mov     rax, cs:g_pfnResultLoggingCallback
0x18000304b  test    rax, rax
0x18000304e  jz      short loc_18000306D
0x180003050  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003057  jnz     short loc_18000306D
0x180003059  mov     r8d, ebx
0x18000305c  lea     rdx, [rbp+13F0h+OutputString]
0x180003063  lea     rcx, [rsp+14F0h+var_14D0]
0x180003068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000306d  cmp     [rbp+13F0h+OutputString], r13w
0x180003075  jnz     short loc_18000308B
0x180003077  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000307c  mov     rdx, rbx; unsigned __int16 *
0x18000307f  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003086  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000308b  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003092  call    cs:__imp_OutputDebugStringW
0x180003098  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000309d  jnz     short loc_1800030A8
0x18000309f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800030a6  jz      short loc_1800030BA
0x1800030a8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800030af  test    rax, rax
0x1800030b2  jz      short loc_1800030BA
0x1800030b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b9  nop
0x1800030ba  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800030bf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
