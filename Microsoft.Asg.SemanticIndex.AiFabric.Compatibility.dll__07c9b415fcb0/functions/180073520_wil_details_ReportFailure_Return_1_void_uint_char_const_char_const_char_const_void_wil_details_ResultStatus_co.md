# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180073520`
- end: `0x1800737e6`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `710`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800731f0`

## callees

- `0x18000d2d0`
- `0x18000d4b0`
- `0x18000d590`
- `0x18000dbf0`
- `0x180073520`
- `0x1801f7110`
- `0x1801f7d30`
- `0x180242120`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18007375b`
- `KERNEL32!OutputDebugStringW` at `0x18007375b`
- `KERNEL32!GetCurrentThreadId` at `0x1800735e4`
- `KERNEL32!GetCurrentThreadId` at `0x1800735e4`
- `KERNEL32!IsDebuggerPresent` at `0x1800736e7`
- `KERNEL32!IsDebuggerPresent` at `0x1800736e7`

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
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int IsDebuggerPresent; // edi
  bool v15; // zf
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+30h] [rbp-D0h] BYREF
  int v21; // [rsp+34h] [rbp-CCh]
  int v22; // [rsp+38h] [rbp-C8h]
  int v23; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v24; // [rsp+40h] [rbp-C0h]
  _WORD *v25; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  __int64 v28; // [rsp+60h] [rbp-A0h]
  __int64 v29; // [rsp+68h] [rbp-98h]
  int v30; // [rsp+70h] [rbp-90h]
  int v31; // [rsp+74h] [rbp-8Ch]
  __int64 v32; // [rsp+78h] [rbp-88h]
  __int128 v33; // [rsp+80h] [rbp-80h]
  __int64 v34; // [rsp+90h] [rbp-70h]
  __int128 v35; // [rsp+98h] [rbp-68h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C0h] [rbp-40h]
  char v40[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2048]; // [rsp+4D0h] [rbp+3D0h] BYREF

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v19 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, a2);
  v20 = 1;
  v21 = a10;
  if ( a7[2] == 1 )
    v21 = a10 | 8;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v15 = *a8 == 0, v25 = a8, v15) )
    v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v19;
  v27 = a5;
  v28 = a4;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17)),
         IsDebuggerPresent))
    && wil::g_fResultOutputDebugString
    && (v21 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v18);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (wchar_t *)0x800, (__int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v18);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180073520  push    rbp
0x180073522  push    rbx
0x180073523  push    rsi
0x180073524  push    rdi
0x180073525  push    r12
0x180073527  push    r13
0x180073529  push    r14
0x18007352b  push    r15
0x18007352d  lea     rbp, [rsp-13E8h]
0x180073535  mov     eax, 14E8h
0x18007353a  call    _alloca_probe
0x18007353f  sub     rsp, rax
0x180073542  mov     rax, cs:__security_cookie
0x180073549  xor     rax, rsp
0x18007354c  mov     [rbp+1420h+var_50], rax
0x180073553  mov     r12, r9
0x180073556  mov     r15, r8
0x180073559  mov     r14d, edx
0x18007355c  mov     rsi, rcx
0x18007355f  mov     r13, [rbp+1420h+arg_20]
0x180073566  mov     rax, [rbp+1420h+arg_28]
0x18007356d  mov     [rsp+1520h+var_14F8], rax
0x180073572  xor     edi, edi
0x180073574  mov     [rbp+1420h+OutputString], di
0x18007357b  mov     [rbp+1420h+var_1450], dil
0x18007357f  mov     rbx, [rbp+1420h+arg_30]
0x180073586  mov     ecx, [rbx]; this
0x180073588  mov     [rsp+1520h+var_14E8], ecx
0x18007358c  mov     eax, [rbx+4]
0x18007358f  mov     [rsp+1520h+var_14E4], eax
0x180073593  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180073598  mov     [rsp+1520h+var_1500], eax
0x18007359c  mov     ecx, 1
0x1800735a1  mov     dword ptr [rsp+1520h+var_14F0], ecx
0x1800735a5  mov     edx, [rbp+1420h+arg_48]
0x1800735ab  mov     dword ptr [rsp+1520h+var_14F0+4], edx
0x1800735af  cmp     [rbx+8], ecx
0x1800735b2  jnz     short loc_1800735BB
0x1800735b4  or      edx, 8
0x1800735b7  mov     dword ptr [rsp+1520h+var_14F0+4], edx
0x1800735bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800735c3  inc     ecx
0x1800735c5  mov     [rsp+1520h+var_14E0], ecx
0x1800735c9  mov     rax, [rbp+1420h+arg_38]
0x1800735d0  test    rax, rax
0x1800735d3  jz      short loc_1800735DF
0x1800735d5  cmp     [rax], di
0x1800735d8  mov     [rsp+1520h+var_14D8], rax
0x1800735dd  jnz     short loc_1800735E4
0x1800735df  mov     [rsp+1520h+var_14D8], rdi
0x1800735e4  call    cs:__imp_GetCurrentThreadId
0x1800735ea  mov     [rsp+1520h+var_14D0], eax
0x1800735ee  mov     [rsp+1520h+var_14B8], r15
0x1800735f3  mov     [rsp+1520h+var_14B0], r14d
0x1800735f8  mov     eax, [rsp+1520h+var_1500]
0x1800735fc  mov     [rsp+1520h+var_14AC], eax
0x180073600  mov     [rsp+1520h+var_14C8], r13
0x180073605  mov     [rsp+1520h+var_14C0], r12
0x18007360a  mov     rax, [rsp+1520h+var_14F8]
0x18007360f  mov     [rbp+1420h+var_1468], rax
0x180073613  mov     [rbp+1420h+var_1460], rsi
0x180073617  mov     [rsp+1520h+var_14A8], rdi
0x18007361c  xorps   xmm0, xmm0
0x18007361f  xor     eax, eax
0x180073621  movups  [rbp+1420h+var_1488], xmm0
0x180073625  mov     [rbp+1420h+var_1478], rax
0x180073629  xorps   xmm1, xmm1
0x18007362c  movups  [rbp+1420h+var_14A0], xmm1
0x180073630  mov     [rbp+1420h+var_1490], rax
0x180073634  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18007363b  test    rax, rax
0x18007363e  jz      short loc_18007364C
0x180073640  call    cs:__guard_dispatch_icall_fptr
0x180073646  mov     [rbp+1420h+var_1470], rax
0x18007364a  jmp     short loc_180073650
0x18007364c  mov     [rbp+1420h+var_1470], rdi
0x180073650  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180073657  test    rax, rax
0x18007365a  jz      short loc_180073667
0x18007365c  lea     rcx, [rsp+1520h+var_14F0]
0x180073661  call    cs:__guard_dispatch_icall_fptr
0x180073667  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007366e  test    rax, rax
0x180073671  jz      short loc_180073688
0x180073673  mov     r8d, 400h
0x180073679  lea     rdx, [rbp+1420h+var_1450]
0x18007367d  lea     rcx, [rsp+1520h+var_14F0]
0x180073682  call    cs:__guard_dispatch_icall_fptr
0x180073688  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007368f  test    rax, rax
0x180073692  jz      short loc_18007369F
0x180073694  lea     rcx, [rsp+1520h+var_14F0]
0x180073699  call    cs:__guard_dispatch_icall_fptr
0x18007369f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800736a6  test    rax, rax
0x1800736a9  jz      short loc_1800736BD
0x1800736ab  test    byte ptr [rsp+1520h+var_14F0+4], 2
0x1800736b0  jnz     short loc_1800736BD
0x1800736b2  lea     rcx, [rsp+1520h+var_14F0]
0x1800736b7  call    cs:__guard_dispatch_icall_fptr
0x1800736bd  cmp     [rsp+1520h+var_14E8], edi
0x1800736c1  jge     loc_1800737E0
0x1800736c7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800736ce  jnz     short loc_1800736F7
0x1800736d0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800736d7  test    rax, rax
0x1800736da  jz      short loc_1800736E7
0x1800736dc  call    cs:__guard_dispatch_icall_fptr
0x1800736e2  movzx   edi, al
0x1800736e5  jmp     short loc_1800736F3
0x1800736e7  call    cs:__imp_IsDebuggerPresent
0x1800736ed  test    eax, eax
0x1800736ef  setnz   dil
0x1800736f3  test    edi, edi
0x1800736f5  jz      short loc_180073763
0x1800736f7  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x1800736fe  jz      short loc_180073763
0x180073700  test    byte ptr [rsp+1520h+var_14F0+4], 2
0x180073705  jnz     short loc_180073763
0x180073707  mov     rax, cs:g_pfnResultLoggingCallback
0x18007370e  test    rax, rax
0x180073711  jz      short loc_180073734
0x180073713  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18007371a  jnz     short loc_180073734
0x18007371c  mov     r8d, 800h
0x180073722  lea     rdx, [rbp+1420h+OutputString]
0x180073729  lea     rcx, [rsp+1520h+var_14F0]
0x18007372e  call    cs:__guard_dispatch_icall_fptr
0x180073734  cmp     [rbp+1420h+OutputString], 0
0x18007373c  jnz     short loc_180073754
0x18007373e  lea     r8, [rsp+1520h+var_14F0]; unsigned __int64
0x180073743  mov     edx, 800h; wchar_t *
0x180073748  lea     rcx, [rbp+1420h+OutputString]; Buffer
0x18007374f  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180073754  lea     rcx, [rbp+1420h+OutputString]; lpOutputString
0x18007375b  call    cs:__imp_OutputDebugStringW
0x180073761  jmp     short loc_180073788
0x180073763  mov     rax, cs:g_pfnResultLoggingCallback
0x18007376a  test    rax, rax
0x18007376d  jz      short loc_180073788
0x18007376f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180073776  jnz     short loc_180073788
0x180073778  xor     r8d, r8d
0x18007377b  xor     edx, edx
0x18007377d  lea     rcx, [rsp+1520h+var_14F0]
0x180073782  call    cs:__guard_dispatch_icall_fptr
0x180073788  test    byte ptr [rsp+1520h+var_14F0+4], 4
0x18007378d  jnz     short loc_180073798
0x18007378f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x180073796  jz      short loc_1800737AB
0x180073798  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18007379f  test    rax, rax
0x1800737a2  jz      short loc_1800737AB
0x1800737a4  call    cs:__guard_dispatch_icall_fptr
0x1800737aa  nop
0x1800737ab  test    byte ptr [rsp+1520h+var_14F0+4], 1
0x1800737b0  jnz     short loc_1800737D5
0x1800737b2  mov     rcx, [rbp+1420h+var_50]
0x1800737b9  xor     rcx, rsp; StackCookie
0x1800737bc  call    __security_check_cookie
0x1800737c1  add     rsp, 14E8h
0x1800737c8  pop     r15
0x1800737ca  pop     r14
0x1800737cc  pop     r13
0x1800737ce  pop     r12
0x1800737d0  pop     rdi
0x1800737d1  pop     rsi
0x1800737d2  pop     rbx
0x1800737d3  pop     rbp
0x1800737d4  retn
0x1800737d5  lea     rcx, [rsp+1520h+var_14F0]; this
0x1800737da  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800737e0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
