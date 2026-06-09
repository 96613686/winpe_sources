# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140007144`
- end: `0x1400073a6`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140006ee8`

## callees

- `0x1400023f3`
- `0x140007144`
- `0x14000a4a4`
- `0x14000ac7c`
- `0x14000c350`
- `0x14000e790`
- `0x140011ed0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400071e6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400071e6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400072e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400072e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007373`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007373`

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
0x140007144  mov     [rsp-8+arg_18], rbx
0x140007149  push    rbp
0x14000714a  push    rsi
0x14000714b  push    rdi
0x14000714c  push    r12
0x14000714e  push    r13
0x140007150  push    r14
0x140007152  push    r15
0x140007154  lea     rbp, [rsp-13C0h]
0x14000715c  mov     eax, 14C0h
0x140007161  call    _alloca_probe
0x140007166  sub     rsp, rax
0x140007169  mov     r15, r8
0x14000716c  mov     r14d, edx
0x14000716f  mov     r12, rcx
0x140007172  mov     rsi, [rbp+13F0h+arg_28]
0x140007179  xor     edx, edx; Val
0x14000717b  mov     r8d, 98h; Size
0x140007181  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140007186  call    memset_0
0x14000718b  nop
0x14000718c  xor     r13d, r13d
0x14000718f  mov     [rbp+13F0h+OutputString], r13w
0x140007197  mov     [rbp+13F0h+var_1430], r13b
0x14000719b  mov     rbx, [rbp+13F0h+arg_30]
0x1400071a2  mov     ecx, [rbx]; this
0x1400071a4  mov     [rsp+14F0h+var_14C8], ecx
0x1400071a8  mov     eax, [rbx+4]
0x1400071ab  mov     [rsp+14F0h+var_14C4], eax
0x1400071af  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400071b4  mov     edi, eax
0x1400071b6  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400071be  mov     ecx, r13d
0x1400071c1  lea     eax, [r13+8]
0x1400071c5  cmp     dword ptr [rbx+8], 1
0x1400071c9  cmovz   ecx, eax
0x1400071cc  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400071d0  lea     ecx, [rax-7]
0x1400071d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400071db  inc     ecx
0x1400071dd  mov     [rsp+14F0h+var_14C0], ecx
0x1400071e1  mov     [rsp+14F0h+var_14B8], r13
0x1400071e6  call    cs:__imp_GetCurrentThreadId
0x1400071ec  mov     [rsp+14F0h+var_14B0], eax
0x1400071f0  mov     [rsp+14F0h+var_1498], r15
0x1400071f5  mov     [rsp+14F0h+var_1490], r14d
0x1400071fa  mov     [rsp+14F0h+var_148C], edi
0x1400071fe  mov     [rsp+14F0h+var_14A8], r13
0x140007203  mov     [rsp+14F0h+var_14A0], r13
0x140007208  mov     [rbp+13F0h+var_1448], rsi
0x14000720c  mov     [rbp+13F0h+var_1440], r12
0x140007210  mov     [rsp+14F0h+var_1488], r13
0x140007215  xorps   xmm0, xmm0
0x140007218  xor     eax, eax
0x14000721a  movups  [rbp+13F0h+var_1468], xmm0
0x14000721e  mov     [rbp+13F0h+var_1458], rax
0x140007222  xorps   xmm1, xmm1
0x140007225  movups  [rsp+14F0h+var_1480], xmm1
0x14000722a  mov     [rbp+13F0h+var_1470], rax
0x14000722e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007235  test    rax, rax
0x140007238  jz      short loc_140007245
0x14000723a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000723f  mov     [rbp+13F0h+var_1450], rax
0x140007243  jmp     short loc_140007249
0x140007245  mov     [rbp+13F0h+var_1450], r13
0x140007249  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007250  test    rax, rax
0x140007253  jz      short loc_14000725F
0x140007255  lea     rcx, [rsp+14F0h+var_14D0]
0x14000725a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000725f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007266  test    rax, rax
0x140007269  jz      short loc_14000727F
0x14000726b  mov     r8d, 400h
0x140007271  lea     rdx, [rbp+13F0h+var_1430]
0x140007275  lea     rcx, [rsp+14F0h+var_14D0]
0x14000727a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000727f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007286  test    rax, rax
0x140007289  jz      short loc_140007295
0x14000728b  lea     rcx, [rsp+14F0h+var_14D0]
0x140007290  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007295  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000729c  test    rax, rax
0x14000729f  jz      short loc_1400072B2
0x1400072a1  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400072a6  jnz     short loc_1400072B2
0x1400072a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1400072ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072b2  cmp     [rsp+14F0h+var_14C8], r13d
0x1400072b7  jl      short loc_1400072CB
0x1400072b9  mov     ecx, 8000FFFFh; this
0x1400072be  mov     [rsp+14F0h+var_14C8], ecx
0x1400072c2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400072c7  mov     [rsp+14F0h+var_14C4], eax
0x1400072cb  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400072d2  jnz     short loc_1400072F3
0x1400072d4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400072db  test    rax, rax
0x1400072de  jz      short loc_1400072E9
0x1400072e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400072e5  test    al, al
0x1400072e7  jmp     short loc_1400072F1
0x1400072e9  call    cs:__imp_IsDebuggerPresent
0x1400072ef  test    eax, eax
0x1400072f1  jz      short loc_1400072FA
0x1400072f3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400072f8  jz      short loc_140007320
0x1400072fa  mov     rax, cs:g_pfnResultLoggingCallback
0x140007301  test    rax, rax
0x140007304  jz      short loc_140007379
0x140007306  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000730d  jnz     short loc_140007379
0x14000730f  xor     r8d, r8d
0x140007312  xor     edx, edx
0x140007314  lea     rcx, [rsp+14F0h+var_14D0]
0x140007319  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000731e  jmp     short loc_140007379
0x140007320  mov     ebx, 800h
0x140007325  mov     rax, cs:g_pfnResultLoggingCallback
0x14000732c  test    rax, rax
0x14000732f  jz      short loc_14000734E
0x140007331  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140007338  jnz     short loc_14000734E
0x14000733a  mov     r8d, ebx
0x14000733d  lea     rdx, [rbp+13F0h+OutputString]
0x140007344  lea     rcx, [rsp+14F0h+var_14D0]
0x140007349  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000734e  cmp     [rbp+13F0h+OutputString], r13w
0x140007356  jnz     short loc_14000736C
0x140007358  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000735d  mov     rdx, rbx; unsigned __int16 *
0x140007360  lea     rcx, [rbp+13F0h+OutputString]; this
0x140007367  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000736c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140007373  call    cs:__imp_OutputDebugStringW
0x140007379  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000737e  jnz     short loc_140007389
0x140007380  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140007387  jz      short loc_14000739B
0x140007389  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007390  test    rax, rax
0x140007393  jz      short loc_14000739B
0x140007395  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000739a  nop
0x14000739b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1400073a0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
