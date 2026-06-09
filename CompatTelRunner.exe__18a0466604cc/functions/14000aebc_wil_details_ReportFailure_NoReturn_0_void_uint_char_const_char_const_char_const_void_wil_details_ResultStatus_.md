# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000aebc`
- end: `0x14000b168`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000ae10`

## callees

- `0x1400026c0`
- `0x140005e84`
- `0x1400076f8`
- `0x14000981c`
- `0x140009f50`
- `0x14000a11c`
- `0x14000aebc`
- `0x1400a7290`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000af65`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000af65`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000b060`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000b060`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b0fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000b0fc`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x14000aebc  mov     [rsp-8+arg_18], rbx
0x14000aec1  push    rbp
0x14000aec2  push    rsi
0x14000aec3  push    rdi
0x14000aec4  push    r12
0x14000aec6  push    r13
0x14000aec8  push    r14
0x14000aeca  push    r15
0x14000aecc  lea     rbp, [rsp-13C0h]
0x14000aed4  mov     eax, 14C0h
0x14000aed9  call    _alloca_probe
0x14000aede  sub     rsp, rax
0x14000aee1  mov     r14, r8
0x14000aee4  mov     esi, edx
0x14000aee6  mov     r15, rcx
0x14000aee9  mov     rdi, [rbp+13F0h+arg_28]
0x14000aef0  xor     r13d, r13d
0x14000aef3  cmp     cs:g_pfnThrowPlatformException, r13
0x14000aefa  setnz   r12b
0x14000aefe  xor     edx, edx; Val
0x14000af00  mov     r8d, 98h; Size
0x14000af06  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000af0b  call    memset_0
0x14000af10  nop
0x14000af11  mov     [rbp+13F0h+OutputString], r13w
0x14000af19  mov     [rbp+13F0h+var_1430], r13b
0x14000af1d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x14000af24  mov     ecx, [rdx]; this
0x14000af26  mov     [rsp+14F0h+var_14C8], ecx
0x14000af2a  mov     eax, [rdx+4]
0x14000af2d  mov     [rsp+14F0h+var_14C4], eax
0x14000af31  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000af36  mov     ebx, eax
0x14000af38  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x14000af3d  mov     ecx, r13d
0x14000af40  lea     eax, [r13+8]
0x14000af44  cmp     dword ptr [rdx+8], 1
0x14000af48  cmovz   ecx, eax
0x14000af4b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x14000af4f  lea     ecx, [rax-7]
0x14000af52  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000af5a  inc     ecx
0x14000af5c  mov     [rsp+14F0h+var_14C0], ecx
0x14000af60  mov     [rsp+14F0h+var_14B8], r13
0x14000af65  call    cs:__imp_GetCurrentThreadId
0x14000af6b  mov     [rsp+14F0h+var_14B0], eax
0x14000af6f  mov     [rsp+14F0h+var_1498], r14
0x14000af74  mov     [rsp+14F0h+var_1490], esi
0x14000af78  mov     [rsp+14F0h+var_148C], ebx
0x14000af7c  mov     [rsp+14F0h+var_14A8], r13
0x14000af81  mov     [rsp+14F0h+var_14A0], r13
0x14000af86  mov     [rbp+13F0h+var_1448], rdi
0x14000af8a  mov     [rbp+13F0h+var_1440], r15
0x14000af8e  mov     [rsp+14F0h+var_1488], r13
0x14000af93  xorps   xmm0, xmm0
0x14000af96  xor     eax, eax
0x14000af98  movups  [rbp+13F0h+var_1468], xmm0
0x14000af9c  mov     [rbp+13F0h+var_1458], rax
0x14000afa0  xorps   xmm1, xmm1
0x14000afa3  movups  [rsp+14F0h+var_1480], xmm1
0x14000afa8  mov     [rbp+13F0h+var_1470], rax
0x14000afac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000afb3  test    rax, rax
0x14000afb6  jz      short loc_14000AFC3
0x14000afb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afbd  mov     [rbp+13F0h+var_1450], rax
0x14000afc1  jmp     short loc_14000AFC7
0x14000afc3  mov     [rbp+13F0h+var_1450], r13
0x14000afc7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000afce  test    rax, rax
0x14000afd1  jz      short loc_14000AFDD
0x14000afd3  lea     rcx, [rsp+14F0h+var_14D0]
0x14000afd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000afdd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000afe4  test    rax, rax
0x14000afe7  jz      short loc_14000AFFD
0x14000afe9  mov     r8d, 400h
0x14000afef  lea     rdx, [rbp+13F0h+var_1430]
0x14000aff3  lea     rcx, [rsp+14F0h+var_14D0]
0x14000aff8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000affd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b004  test    rax, rax
0x14000b007  jz      short loc_14000B013
0x14000b009  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b00e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b013  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000b01a  test    rax, rax
0x14000b01d  jz      short loc_14000B035
0x14000b01f  test    r12b, r12b
0x14000b022  jnz     short loc_14000B035
0x14000b024  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000b029  jnz     short loc_14000B035
0x14000b02b  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b035  cmp     [rsp+14F0h+var_14C8], r13d
0x14000b03a  jl      short loc_14000B042
0x14000b03c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000b042  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000b049  jnz     short loc_14000B06A
0x14000b04b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000b052  test    rax, rax
0x14000b055  jz      short loc_14000B060
0x14000b057  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b05c  test    al, al
0x14000b05e  jmp     short loc_14000B068
0x14000b060  call    cs:__imp_IsDebuggerPresent
0x14000b066  test    eax, eax
0x14000b068  jz      short loc_14000B073
0x14000b06a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000b06f  mov     bl, 1
0x14000b071  jz      short loc_14000B076
0x14000b073  mov     bl, r13b
0x14000b076  test    r12b, r12b
0x14000b079  jnz     short loc_14000B0A5
0x14000b07b  test    bl, bl
0x14000b07d  jnz     short loc_14000B0A5
0x14000b07f  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b086  test    rax, rax
0x14000b089  jz      short loc_14000B102
0x14000b08b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000b092  jnz     short loc_14000B102
0x14000b094  xor     r8d, r8d
0x14000b097  xor     edx, edx
0x14000b099  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b09e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0a3  jmp     short loc_14000B102
0x14000b0a5  mov     edi, 800h
0x14000b0aa  mov     rax, cs:g_pfnResultLoggingCallback
0x14000b0b1  test    rax, rax
0x14000b0b4  jz      short loc_14000B0D3
0x14000b0b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000b0bd  jnz     short loc_14000B0D3
0x14000b0bf  mov     r8d, edi
0x14000b0c2  lea     rdx, [rbp+13F0h+OutputString]
0x14000b0c9  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b0ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b0d3  cmp     [rbp+13F0h+OutputString], r13w
0x14000b0db  jnz     short loc_14000B0F1
0x14000b0dd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000b0e2  mov     rdx, rdi; unsigned __int16 *
0x14000b0e5  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000b0ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000b0f1  test    bl, bl
0x14000b0f3  jz      short loc_14000B102
0x14000b0f5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000b0fc  call    cs:__imp_OutputDebugStringW
0x14000b102  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000b107  jnz     short loc_14000B112
0x14000b109  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000b110  jz      short loc_14000B124
0x14000b112  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000b119  test    rax, rax
0x14000b11c  jz      short loc_14000B124
0x14000b11e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b123  nop
0x14000b124  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000b129  jz      short loc_14000B136
0x14000b12b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000b130  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000b136  test    r12b, r12b
0x14000b139  jz      short loc_14000B153
0x14000b13b  lea     rdx, [rbp+13F0h+OutputString]
0x14000b142  lea     rcx, [rsp+14F0h+var_14D0]
0x14000b147  mov     rax, cs:g_pfnThrowPlatformException
0x14000b14e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b153  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000b158  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x14000b15d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000b162  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
