# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002f64`
- end: `0x1800031c6`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002d08`

## callees

- `0x180002f64`
- `0x18000e76c`
- `0x180010a08`
- `0x180013a60`
- `0x18001daa0`
- `0x1800502c2`
- `0x1800503c0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003006`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003006`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003193`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003193`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003109`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003109`

## pseudocode

```c
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x180002f64  mov     [rsp-8+arg_18], rbx
0x180002f69  push    rbp
0x180002f6a  push    rsi
0x180002f6b  push    rdi
0x180002f6c  push    r12
0x180002f6e  push    r13
0x180002f70  push    r14
0x180002f72  push    r15
0x180002f74  lea     rbp, [rsp-13C0h]
0x180002f7c  mov     eax, 14C0h
0x180002f81  call    _alloca_probe
0x180002f86  sub     rsp, rax
0x180002f89  mov     r15, r8
0x180002f8c  mov     r14d, edx
0x180002f8f  mov     r12, rcx
0x180002f92  mov     rsi, [rbp+13F0h+arg_28]
0x180002f99  xor     edx, edx; Val
0x180002f9b  mov     r8d, 98h; Size
0x180002fa1  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002fa6  call    memset_0
0x180002fab  nop
0x180002fac  xor     r13d, r13d
0x180002faf  mov     [rbp+13F0h+OutputString], r13w
0x180002fb7  mov     [rbp+13F0h+var_1430], r13b
0x180002fbb  mov     rbx, [rbp+13F0h+arg_30]
0x180002fc2  mov     ecx, [rbx]; this
0x180002fc4  mov     [rsp+14F0h+var_14C8], ecx
0x180002fc8  mov     eax, [rbx+4]
0x180002fcb  mov     [rsp+14F0h+var_14C4], eax
0x180002fcf  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002fd4  mov     edi, eax
0x180002fd6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002fde  mov     ecx, r13d
0x180002fe1  lea     eax, [r13+8]
0x180002fe5  cmp     dword ptr [rbx+8], 1
0x180002fe9  cmovz   ecx, eax
0x180002fec  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ff0  lea     ecx, [rax-7]
0x180002ff3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002ffb  inc     ecx
0x180002ffd  mov     [rsp+14F0h+var_14C0], ecx
0x180003001  mov     [rsp+14F0h+var_14B8], r13
0x180003006  call    cs:__imp_GetCurrentThreadId
0x18000300c  mov     [rsp+14F0h+var_14B0], eax
0x180003010  mov     [rsp+14F0h+var_1498], r15
0x180003015  mov     [rsp+14F0h+var_1490], r14d
0x18000301a  mov     [rsp+14F0h+var_148C], edi
0x18000301e  mov     [rsp+14F0h+var_14A8], r13
0x180003023  mov     [rsp+14F0h+var_14A0], r13
0x180003028  mov     [rbp+13F0h+var_1448], rsi
0x18000302c  mov     [rbp+13F0h+var_1440], r12
0x180003030  mov     [rsp+14F0h+var_1488], r13
0x180003035  xorps   xmm0, xmm0
0x180003038  xor     eax, eax
0x18000303a  movups  [rbp+13F0h+var_1468], xmm0
0x18000303e  mov     [rbp+13F0h+var_1458], rax
0x180003042  xorps   xmm1, xmm1
0x180003045  movups  [rsp+14F0h+var_1480], xmm1
0x18000304a  mov     [rbp+13F0h+var_1470], rax
0x18000304e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003055  test    rax, rax
0x180003058  jz      short loc_180003065
0x18000305a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000305f  mov     [rbp+13F0h+var_1450], rax
0x180003063  jmp     short loc_180003069
0x180003065  mov     [rbp+13F0h+var_1450], r13
0x180003069  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003070  test    rax, rax
0x180003073  jz      short loc_18000307F
0x180003075  lea     rcx, [rsp+14F0h+var_14D0]
0x18000307a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000307f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003086  test    rax, rax
0x180003089  jz      short loc_18000309F
0x18000308b  mov     r8d, 400h
0x180003091  lea     rdx, [rbp+13F0h+var_1430]
0x180003095  lea     rcx, [rsp+14F0h+var_14D0]
0x18000309a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000309f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030a6  test    rax, rax
0x1800030a9  jz      short loc_1800030B5
0x1800030ab  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800030bc  test    rax, rax
0x1800030bf  jz      short loc_1800030D2
0x1800030c1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800030c6  jnz     short loc_1800030D2
0x1800030c8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800030cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030d2  cmp     [rsp+14F0h+var_14C8], r13d
0x1800030d7  jl      short loc_1800030EB
0x1800030d9  mov     ecx, 8000FFFFh; this
0x1800030de  mov     [rsp+14F0h+var_14C8], ecx
0x1800030e2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800030e7  mov     [rsp+14F0h+var_14C4], eax
0x1800030eb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800030f2  jnz     short loc_180003113
0x1800030f4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800030fb  test    rax, rax
0x1800030fe  jz      short loc_180003109
0x180003100  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003105  test    al, al
0x180003107  jmp     short loc_180003111
0x180003109  call    cs:__imp_IsDebuggerPresent
0x18000310f  test    eax, eax
0x180003111  jz      short loc_18000311A
0x180003113  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003118  jz      short loc_180003140
0x18000311a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003121  test    rax, rax
0x180003124  jz      short loc_180003199
0x180003126  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000312d  jnz     short loc_180003199
0x18000312f  xor     r8d, r8d
0x180003132  xor     edx, edx
0x180003134  lea     rcx, [rsp+14F0h+var_14D0]
0x180003139  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000313e  jmp     short loc_180003199
0x180003140  mov     ebx, 800h
0x180003145  mov     rax, cs:g_pfnResultLoggingCallback
0x18000314c  test    rax, rax
0x18000314f  jz      short loc_18000316E
0x180003151  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003158  jnz     short loc_18000316E
0x18000315a  mov     r8d, ebx
0x18000315d  lea     rdx, [rbp+13F0h+OutputString]
0x180003164  lea     rcx, [rsp+14F0h+var_14D0]
0x180003169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000316e  cmp     [rbp+13F0h+OutputString], r13w
0x180003176  jnz     short loc_18000318C
0x180003178  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000317d  mov     rdx, rbx; unsigned __int16 *
0x180003180  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003187  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000318c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003193  call    cs:__imp_OutputDebugStringW
0x180003199  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000319e  jnz     short loc_1800031A9
0x1800031a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800031a7  jz      short loc_1800031BB
0x1800031a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800031b0  test    rax, rax
0x1800031b3  jz      short loc_1800031BB
0x1800031b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031ba  nop
0x1800031bb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800031c0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
