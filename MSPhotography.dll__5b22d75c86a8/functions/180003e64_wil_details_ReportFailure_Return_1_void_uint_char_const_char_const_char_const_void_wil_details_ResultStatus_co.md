# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003e64`
- end: `0x18000410a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003ae8`

## callees

- `0x180002420`
- `0x180003088`
- `0x180003e64`
- `0x180004cc4`
- `0x180005d40`
- `0x180006938`
- `0x180006a14`
- `0x18013ecc0`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f2a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003f2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000401f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000401f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800040a9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800040a9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180003e64  push    rbp
0x180003e66  push    rbx
0x180003e67  push    rsi
0x180003e68  push    rdi
0x180003e69  push    r12
0x180003e6b  push    r14
0x180003e6d  push    r15
0x180003e6f  lea     rbp, [rsp-13D0h]
0x180003e77  mov     eax, 14D0h
0x180003e7c  call    _alloca_probe
0x180003e81  sub     rsp, rax
0x180003e84  mov     rax, cs:__security_cookie
0x180003e8b  xor     rax, rsp
0x180003e8e  mov     [rbp+1400h+var_40], rax
0x180003e95  mov     rsi, r8
0x180003e98  mov     edi, edx
0x180003e9a  mov     rbx, rcx
0x180003e9d  mov     r14, [rbp+1400h+arg_28]
0x180003ea4  xor     edx, edx; Val
0x180003ea6  mov     r8d, 98h; Size
0x180003eac  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003eb1  call    memset_0
0x180003eb6  nop
0x180003eb7  xor     r12d, r12d
0x180003eba  mov     [rbp+1400h+OutputString], r12w
0x180003ec2  mov     [rbp+1400h+var_1440], r12b
0x180003ec6  mov     rdx, [rbp+1400h+arg_30]; int
0x180003ecd  mov     ecx, [rdx]; this
0x180003ecf  mov     [rsp+1500h+var_14D8], ecx
0x180003ed3  mov     eax, [rdx+4]
0x180003ed6  mov     [rsp+1500h+var_14D4], eax
0x180003eda  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003edf  mov     r15d, eax
0x180003ee2  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003eea  mov     ecx, r12d
0x180003eed  lea     eax, [r12+8]
0x180003ef2  cmp     dword ptr [rdx+8], 1
0x180003ef6  cmovz   ecx, eax
0x180003ef9  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003efd  lea     ecx, [rax-7]
0x180003f00  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003f08  inc     ecx
0x180003f0a  mov     [rsp+1500h+var_14D0], ecx
0x180003f0e  mov     rcx, [rbp+1400h+arg_38]
0x180003f15  test    rcx, rcx
0x180003f18  jz      short loc_180003F25
0x180003f1a  cmp     [rcx], r12w
0x180003f1e  mov     [rsp+1500h+var_14C8], rcx
0x180003f23  jnz     short loc_180003F2A
0x180003f25  mov     [rsp+1500h+var_14C8], r12
0x180003f2a  call    cs:__imp_GetCurrentThreadId
0x180003f30  mov     [rsp+1500h+var_14C0], eax
0x180003f34  mov     [rsp+1500h+var_14A8], rsi
0x180003f39  mov     [rsp+1500h+var_14A0], edi
0x180003f3d  mov     [rsp+1500h+var_149C], r15d
0x180003f42  mov     [rsp+1500h+var_14B8], r12
0x180003f47  mov     [rsp+1500h+var_14B0], r12
0x180003f4c  mov     [rbp+1400h+var_1458], r14
0x180003f50  mov     [rbp+1400h+var_1450], rbx
0x180003f54  mov     [rsp+1500h+var_1498], r12
0x180003f59  xorps   xmm0, xmm0
0x180003f5c  xor     eax, eax
0x180003f5e  movups  [rbp+1400h+var_1478], xmm0
0x180003f62  mov     [rbp+1400h+var_1468], rax
0x180003f66  xorps   xmm1, xmm1
0x180003f69  movups  [rsp+1500h+var_1490], xmm1
0x180003f6e  mov     [rbp+1400h+var_1480], rax
0x180003f72  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003f79  test    rax, rax
0x180003f7c  jz      short loc_180003F89
0x180003f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f83  mov     [rbp+1400h+var_1460], rax
0x180003f87  jmp     short loc_180003F8D
0x180003f89  mov     [rbp+1400h+var_1460], r12
0x180003f8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003f94  test    rax, rax
0x180003f97  jz      short loc_180003FA3
0x180003f99  lea     rcx, [rsp+1500h+var_14E0]
0x180003f9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fa3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003faa  test    rax, rax
0x180003fad  jz      short loc_180003FC3
0x180003faf  mov     r8d, 400h
0x180003fb5  lea     rdx, [rbp+1400h+var_1440]
0x180003fb9  lea     rcx, [rsp+1500h+var_14E0]
0x180003fbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fc3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fca  test    rax, rax
0x180003fcd  jz      short loc_180003FD9
0x180003fcf  lea     rcx, [rsp+1500h+var_14E0]
0x180003fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003fd9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003fe0  test    rax, rax
0x180003fe3  jz      short loc_180003FF6
0x180003fe5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003fea  jnz     short loc_180003FF6
0x180003fec  lea     rcx, [rsp+1500h+var_14E0]
0x180003ff1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ff6  cmp     [rsp+1500h+var_14D8], r12d
0x180003ffb  jge     loc_180004104
0x180004001  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004008  jnz     short loc_180004029
0x18000400a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004011  test    rax, rax
0x180004014  jz      short loc_18000401F
0x180004016  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000401b  test    al, al
0x18000401d  jmp     short loc_180004027
0x18000401f  call    cs:__imp_IsDebuggerPresent
0x180004025  test    eax, eax
0x180004027  jz      short loc_180004030
0x180004029  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000402e  jz      short loc_180004056
0x180004030  mov     rax, cs:g_pfnResultLoggingCallback
0x180004037  test    rax, rax
0x18000403a  jz      short loc_1800040AF
0x18000403c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004043  jnz     short loc_1800040AF
0x180004045  xor     r8d, r8d
0x180004048  xor     edx, edx
0x18000404a  lea     rcx, [rsp+1500h+var_14E0]
0x18000404f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004054  jmp     short loc_1800040AF
0x180004056  mov     ebx, 800h
0x18000405b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004062  test    rax, rax
0x180004065  jz      short loc_180004084
0x180004067  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000406e  jnz     short loc_180004084
0x180004070  mov     r8d, ebx
0x180004073  lea     rdx, [rbp+1400h+OutputString]
0x18000407a  lea     rcx, [rsp+1500h+var_14E0]
0x18000407f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004084  cmp     [rbp+1400h+OutputString], r12w
0x18000408c  jnz     short loc_1800040A2
0x18000408e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004093  mov     rdx, rbx; unsigned __int16 *
0x180004096  lea     rcx, [rbp+1400h+OutputString]; this
0x18000409d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800040a2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800040a9  call    cs:__imp_OutputDebugStringW
0x1800040af  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800040b4  jnz     short loc_1800040BF
0x1800040b6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800040bd  jz      short loc_1800040D1
0x1800040bf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800040c6  test    rax, rax
0x1800040c9  jz      short loc_1800040D1
0x1800040cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040d0  nop
0x1800040d1  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800040d6  jnz     short loc_1800040F9
0x1800040d8  mov     rcx, [rbp+1400h+var_40]
0x1800040df  xor     rcx, rsp; StackCookie
0x1800040e2  call    __security_check_cookie
0x1800040e7  add     rsp, 14D0h
0x1800040ee  pop     r15
0x1800040f0  pop     r14
0x1800040f2  pop     r12
0x1800040f4  pop     rdi
0x1800040f5  pop     rsi
0x1800040f6  pop     rbx
0x1800040f7  pop     rbp
0x1800040f8  retn
0x1800040f9  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800040fe  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004104  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
