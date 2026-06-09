# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18003ab80`
- end: `0x18003ae13`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `659`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18003a790`

## callees

- `0x18002c570`
- `0x18003ab80`
- `0x18003c51c`
- `0x18003d120`
- `0x18003dea8`
- `0x18003e05c`
- `0x18005d0f0`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ac33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003ac33`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003ad28`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003ad28`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003adb2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003adb2`

## pseudocode

```c
// Hidden C++ exception states: #wind=8
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
0x18003ab80  push    rbp
0x18003ab82  push    rbx
0x18003ab83  push    rsi
0x18003ab84  push    rdi
0x18003ab85  push    r12
0x18003ab87  push    r14
0x18003ab89  push    r15
0x18003ab8b  lea     rbp, [rsp-13D0h]
0x18003ab93  mov     eax, 14D0h
0x18003ab98  call    _alloca_probe
0x18003ab9d  sub     rsp, rax
0x18003aba0  mov     rax, cs:__security_cookie
0x18003aba7  xor     rax, rsp
0x18003abaa  mov     [rbp+1400h+var_40], rax
0x18003abb1  mov     rsi, r8
0x18003abb4  mov     edi, edx
0x18003abb6  mov     rbx, rcx
0x18003abb9  mov     r14, [rbp+1400h+arg_28]
0x18003abc0  xor     r12d, r12d
0x18003abc3  mov     [rbp+1400h+OutputString], r12w
0x18003abcb  mov     [rbp+1400h+var_1440], r12b
0x18003abcf  mov     rdx, [rbp+1400h+arg_30]; int
0x18003abd6  mov     ecx, [rdx]; this
0x18003abd8  mov     [rsp+1500h+var_14D8], ecx
0x18003abdc  mov     eax, [rdx+4]
0x18003abdf  mov     [rsp+1500h+var_14D4], eax
0x18003abe3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003abe8  mov     r15d, eax
0x18003abeb  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18003abf3  mov     ecx, r12d
0x18003abf6  lea     eax, [r12+8]
0x18003abfb  cmp     dword ptr [rdx+8], 1
0x18003abff  cmovz   ecx, eax
0x18003ac02  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18003ac06  lea     ecx, [rax-7]
0x18003ac09  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003ac11  inc     ecx
0x18003ac13  mov     [rsp+1500h+var_14D0], ecx
0x18003ac17  mov     rcx, [rbp+1400h+arg_38]
0x18003ac1e  test    rcx, rcx
0x18003ac21  jz      short loc_18003AC2E
0x18003ac23  cmp     [rcx], r12w
0x18003ac27  mov     [rsp+1500h+var_14C8], rcx
0x18003ac2c  jnz     short loc_18003AC33
0x18003ac2e  mov     [rsp+1500h+var_14C8], r12
0x18003ac33  call    cs:__imp_GetCurrentThreadId
0x18003ac39  mov     [rsp+1500h+var_14C0], eax
0x18003ac3d  mov     [rsp+1500h+var_14A8], rsi
0x18003ac42  mov     [rsp+1500h+var_14A0], edi
0x18003ac46  mov     [rsp+1500h+var_149C], r15d
0x18003ac4b  mov     [rsp+1500h+var_14B8], r12
0x18003ac50  mov     [rsp+1500h+var_14B0], r12
0x18003ac55  mov     [rbp+1400h+var_1458], r14
0x18003ac59  mov     [rbp+1400h+var_1450], rbx
0x18003ac5d  mov     [rsp+1500h+var_1498], r12
0x18003ac62  xorps   xmm0, xmm0
0x18003ac65  xor     eax, eax
0x18003ac67  movups  [rbp+1400h+var_1478], xmm0
0x18003ac6b  mov     [rbp+1400h+var_1468], rax
0x18003ac6f  xorps   xmm1, xmm1
0x18003ac72  movups  [rsp+1500h+var_1490], xmm1
0x18003ac77  mov     [rbp+1400h+var_1480], rax
0x18003ac7b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003ac82  test    rax, rax
0x18003ac85  jz      short loc_18003AC92
0x18003ac87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac8c  mov     [rbp+1400h+var_1460], rax
0x18003ac90  jmp     short loc_18003AC96
0x18003ac92  mov     [rbp+1400h+var_1460], r12
0x18003ac96  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003ac9d  test    rax, rax
0x18003aca0  jz      short loc_18003ACAC
0x18003aca2  lea     rcx, [rsp+1500h+var_14E0]
0x18003aca7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acac  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003acb3  test    rax, rax
0x18003acb6  jz      short loc_18003ACCC
0x18003acb8  mov     r8d, 400h
0x18003acbe  lea     rdx, [rbp+1400h+var_1440]
0x18003acc2  lea     rcx, [rsp+1500h+var_14E0]
0x18003acc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003accc  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003acd3  test    rax, rax
0x18003acd6  jz      short loc_18003ACE2
0x18003acd8  lea     rcx, [rsp+1500h+var_14E0]
0x18003acdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ace2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003ace9  test    rax, rax
0x18003acec  jz      short loc_18003ACFF
0x18003acee  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18003acf3  jnz     short loc_18003ACFF
0x18003acf5  lea     rcx, [rsp+1500h+var_14E0]
0x18003acfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003acff  cmp     [rsp+1500h+var_14D8], r12d
0x18003ad04  jge     loc_18003AE0D
0x18003ad0a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18003ad11  jnz     short loc_18003AD32
0x18003ad13  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003ad1a  test    rax, rax
0x18003ad1d  jz      short loc_18003AD28
0x18003ad1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad24  test    al, al
0x18003ad26  jmp     short loc_18003AD30
0x18003ad28  call    cs:__imp_IsDebuggerPresent
0x18003ad2e  test    eax, eax
0x18003ad30  jz      short loc_18003AD39
0x18003ad32  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18003ad37  jz      short loc_18003AD5F
0x18003ad39  mov     rax, cs:g_pfnResultLoggingCallback
0x18003ad40  test    rax, rax
0x18003ad43  jz      short loc_18003ADB8
0x18003ad45  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18003ad4c  jnz     short loc_18003ADB8
0x18003ad4e  xor     r8d, r8d
0x18003ad51  xor     edx, edx
0x18003ad53  lea     rcx, [rsp+1500h+var_14E0]
0x18003ad58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad5d  jmp     short loc_18003ADB8
0x18003ad5f  mov     ebx, 800h
0x18003ad64  mov     rax, cs:g_pfnResultLoggingCallback
0x18003ad6b  test    rax, rax
0x18003ad6e  jz      short loc_18003AD8D
0x18003ad70  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18003ad77  jnz     short loc_18003AD8D
0x18003ad79  mov     r8d, ebx
0x18003ad7c  lea     rdx, [rbp+1400h+OutputString]
0x18003ad83  lea     rcx, [rsp+1500h+var_14E0]
0x18003ad88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ad8d  cmp     [rbp+1400h+OutputString], r12w
0x18003ad95  jnz     short loc_18003ADAB
0x18003ad97  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18003ad9c  mov     rdx, rbx; unsigned __int16 *
0x18003ad9f  lea     rcx, [rbp+1400h+OutputString]; this
0x18003ada6  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003adab  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18003adb2  call    cs:__imp_OutputDebugStringW
0x18003adb8  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18003adbd  jnz     short loc_18003ADC8
0x18003adbf  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18003adc6  jz      short loc_18003ADDA
0x18003adc8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003adcf  test    rax, rax
0x18003add2  jz      short loc_18003ADDA
0x18003add4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003add9  nop
0x18003adda  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18003addf  jnz     short loc_18003AE02
0x18003ade1  mov     rcx, [rbp+1400h+var_40]
0x18003ade8  xor     rcx, rsp; StackCookie
0x18003adeb  call    __security_check_cookie
0x18003adf0  add     rsp, 14D0h
0x18003adf7  pop     r15
0x18003adf9  pop     r14
0x18003adfb  pop     r12
0x18003adfd  pop     rdi
0x18003adfe  pop     rsi
0x18003adff  pop     rbx
0x18003ae00  pop     rbp
0x18003ae01  retn
0x18003ae02  lea     rcx, [rsp+1500h+var_14E0]; this
0x18003ae07  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18003ae0d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
