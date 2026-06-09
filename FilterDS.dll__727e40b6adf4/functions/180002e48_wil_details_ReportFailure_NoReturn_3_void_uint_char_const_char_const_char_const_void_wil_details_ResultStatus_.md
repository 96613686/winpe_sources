# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180002e48`
- end: `0x1800030c1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002bb8`

## callees

- `0x180002e48`
- `0x180004694`
- `0x180004e90`
- `0x1800056c0`
- `0x1800069d0`
- `0x180021822`
- `0x180021910`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f01`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180002f01`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003004`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003004`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000308e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000308e`

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
0x180002e48  mov     [rsp-8+arg_18], rbx
0x180002e4d  push    rbp
0x180002e4e  push    rsi
0x180002e4f  push    rdi
0x180002e50  push    r12
0x180002e52  push    r13
0x180002e54  push    r14
0x180002e56  push    r15
0x180002e58  lea     rbp, [rsp-13C0h]
0x180002e60  mov     eax, 14C0h
0x180002e65  call    _alloca_probe
0x180002e6a  sub     rsp, rax
0x180002e6d  mov     r14, r8
0x180002e70  mov     esi, edx
0x180002e72  mov     rdi, rcx
0x180002e75  mov     r15, [rbp+13F0h+arg_28]
0x180002e7c  xor     edx, edx; Val
0x180002e7e  mov     r8d, 98h; Size
0x180002e84  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180002e89  call    memset_0
0x180002e8e  nop
0x180002e8f  xor     r13d, r13d
0x180002e92  mov     [rbp+13F0h+OutputString], r13w
0x180002e9a  mov     [rbp+13F0h+var_1430], r13b
0x180002e9e  mov     rbx, [rbp+13F0h+arg_30]
0x180002ea5  mov     ecx, [rbx]; this
0x180002ea7  mov     [rsp+14F0h+var_14C8], ecx
0x180002eab  mov     eax, [rbx+4]
0x180002eae  mov     [rsp+14F0h+var_14C4], eax
0x180002eb2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002eb7  mov     r12d, eax
0x180002eba  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002ec2  mov     ecx, r13d
0x180002ec5  lea     eax, [r13+8]
0x180002ec9  cmp     dword ptr [rbx+8], 1
0x180002ecd  cmovz   ecx, eax
0x180002ed0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180002ed4  lea     ecx, [rax-7]
0x180002ed7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002edf  inc     ecx
0x180002ee1  mov     [rsp+14F0h+var_14C0], ecx
0x180002ee5  mov     rcx, [rbp+13F0h+arg_38]
0x180002eec  test    rcx, rcx
0x180002eef  jz      short loc_180002EFC
0x180002ef1  cmp     [rcx], r13w
0x180002ef5  mov     [rsp+14F0h+var_14B8], rcx
0x180002efa  jnz     short loc_180002F01
0x180002efc  mov     [rsp+14F0h+var_14B8], r13
0x180002f01  call    cs:__imp_GetCurrentThreadId
0x180002f07  mov     [rsp+14F0h+var_14B0], eax
0x180002f0b  mov     [rsp+14F0h+var_1498], r14
0x180002f10  mov     [rsp+14F0h+var_1490], esi
0x180002f14  mov     [rsp+14F0h+var_148C], r12d
0x180002f19  mov     [rsp+14F0h+var_14A8], r13
0x180002f1e  mov     [rsp+14F0h+var_14A0], r13
0x180002f23  mov     [rbp+13F0h+var_1448], r15
0x180002f27  mov     [rbp+13F0h+var_1440], rdi
0x180002f2b  mov     [rsp+14F0h+var_1488], r13
0x180002f30  xorps   xmm0, xmm0
0x180002f33  xor     eax, eax
0x180002f35  movups  [rbp+13F0h+var_1468], xmm0
0x180002f39  mov     [rbp+13F0h+var_1458], rax
0x180002f3d  xorps   xmm1, xmm1
0x180002f40  movups  [rsp+14F0h+var_1480], xmm1
0x180002f45  mov     [rbp+13F0h+var_1470], rax
0x180002f49  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002f50  test    rax, rax
0x180002f53  jz      short loc_180002F60
0x180002f55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f5a  mov     [rbp+13F0h+var_1450], rax
0x180002f5e  jmp     short loc_180002F64
0x180002f60  mov     [rbp+13F0h+var_1450], r13
0x180002f64  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002f6b  test    rax, rax
0x180002f6e  jz      short loc_180002F7A
0x180002f70  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f7a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180002f81  test    rax, rax
0x180002f84  jz      short loc_180002F9A
0x180002f86  mov     r8d, 400h
0x180002f8c  lea     rdx, [rbp+13F0h+var_1430]
0x180002f90  lea     rcx, [rsp+14F0h+var_14D0]
0x180002f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002f9a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fa1  test    rax, rax
0x180002fa4  jz      short loc_180002FB0
0x180002fa6  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fb0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002fb7  test    rax, rax
0x180002fba  jz      short loc_180002FCD
0x180002fbc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002fc1  jnz     short loc_180002FCD
0x180002fc3  lea     rcx, [rsp+14F0h+var_14D0]
0x180002fc8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002fcd  cmp     [rsp+14F0h+var_14C8], r13d
0x180002fd2  jl      short loc_180002FE6
0x180002fd4  mov     ecx, 8000FFFFh; this
0x180002fd9  mov     [rsp+14F0h+var_14C8], ecx
0x180002fdd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180002fe2  mov     [rsp+14F0h+var_14C4], eax
0x180002fe6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002fed  jnz     short loc_18000300E
0x180002fef  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002ff6  test    rax, rax
0x180002ff9  jz      short loc_180003004
0x180002ffb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003000  test    al, al
0x180003002  jmp     short loc_18000300C
0x180003004  call    cs:__imp_IsDebuggerPresent
0x18000300a  test    eax, eax
0x18000300c  jz      short loc_180003015
0x18000300e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003013  jz      short loc_18000303B
0x180003015  mov     rax, cs:g_pfnResultLoggingCallback
0x18000301c  test    rax, rax
0x18000301f  jz      short loc_180003094
0x180003021  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003028  jnz     short loc_180003094
0x18000302a  xor     r8d, r8d
0x18000302d  xor     edx, edx
0x18000302f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003039  jmp     short loc_180003094
0x18000303b  mov     ebx, 800h
0x180003040  mov     rax, cs:g_pfnResultLoggingCallback
0x180003047  test    rax, rax
0x18000304a  jz      short loc_180003069
0x18000304c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180003053  jnz     short loc_180003069
0x180003055  mov     r8d, ebx
0x180003058  lea     rdx, [rbp+13F0h+OutputString]
0x18000305f  lea     rcx, [rsp+14F0h+var_14D0]
0x180003064  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003069  cmp     [rbp+13F0h+OutputString], r13w
0x180003071  jnz     short loc_180003087
0x180003073  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003078  mov     rdx, rbx; unsigned __int16 *
0x18000307b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180003082  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003087  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000308e  call    cs:__imp_OutputDebugStringW
0x180003094  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003099  jnz     short loc_1800030A4
0x18000309b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800030a2  jz      short loc_1800030B6
0x1800030a4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800030ab  test    rax, rax
0x1800030ae  jz      short loc_1800030B6
0x1800030b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800030b5  nop
0x1800030b6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800030bb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
