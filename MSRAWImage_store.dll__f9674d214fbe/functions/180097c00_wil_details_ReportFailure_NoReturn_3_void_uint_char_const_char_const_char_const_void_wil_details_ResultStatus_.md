# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180097c00`
- end: `0x180097e97`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `663`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800979b4`

## callees

- `0x180095170`
- `0x180097c00`
- `0x18009a62c`
- `0x18009bf50`
- `0x18009d0f0`
- `0x18009e2d4`
- `0x1800b0b00`
- `0x1800b4010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097cc5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180097cc5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180097dce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180097dce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180097e5e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180097e5e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        unsigned __int64 a1,
        unsigned int a2,
        unsigned __int64 a3,
        __int64 a4,
        int a5,
        unsigned __int64 a6,
        __int64 a7,
        _WORD *a8)
{
  int v11; // edx
  unsigned int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  unsigned __int64 v18[22]; // [rsp+20h] [rbp-E0h] BYREF
  _BYTE v19[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v18[20] = -2;
  memset(v18, 0, 0x98u);
  OutputString[0] = 0;
  v19[0] = 0;
  v18[1] = *(_QWORD *)a7;
  v12 = wil::details::RecordFailFast((wil::details *)LODWORD(v18[1]), v11);
  LODWORD(v18[0]) = 3;
  v13 = 0;
  if ( *(_DWORD *)(a7 + 8) == 1 )
    v13 = 8;
  HIDWORD(v18[0]) = v13;
  LODWORD(v18[2]) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v18[3] = (unsigned __int64)a8, v17) )
    v18[3] = 0;
  LODWORD(v18[4]) = GetCurrentThreadId();
  v18[7] = a3;
  v18[8] = __PAIR64__(v12, a2);
  v18[5] = 0;
  v18[6] = 0;
  v18[17] = a6;
  v18[18] = a1;
  memset(&v18[9], 0, 56);
  if ( wil::details::g_pfnGetModuleName )
    v18[16] = wil::details::g_pfnGetModuleName(v15);
  else
    v18[16] = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(v18, v19, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(v18);
  if ( wil::details::g_pfnOriginateCallback && (v18[0] & 0x200000000LL) == 0 )
    wil::details::g_pfnOriginateCallback(v18);
  if ( SLODWORD(v18[1]) >= 0 )
  {
    LODWORD(v18[1]) = -2147418113;
    HIDWORD(v18[1]) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18[0] & 0x200000000LL) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( (v18[0] & 0x400000000LL) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)v18, v14);
}

```

## disassembly

```asm
0x180097c00  push    rbp
0x180097c02  push    rsi
0x180097c03  push    rdi
0x180097c04  push    r12
0x180097c06  push    r13
0x180097c08  push    r14
0x180097c0a  push    r15
0x180097c0c  lea     rbp, [rsp-13D0h]
0x180097c14  mov     eax, 14D0h
0x180097c19  call    _alloca_probe
0x180097c1e  sub     rsp, rax
0x180097c21  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x180097c29  mov     [rsp+1500h+arg_18], rbx
0x180097c31  mov     r14, r8
0x180097c34  mov     esi, edx
0x180097c36  mov     rdi, rcx
0x180097c39  mov     r15, [rbp+1400h+arg_28]
0x180097c40  xor     edx, edx; Val
0x180097c42  mov     r8d, 98h; Size
0x180097c48  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180097c4d  call    memset
0x180097c52  nop
0x180097c53  xor     r13d, r13d
0x180097c56  mov     [rbp+1400h+OutputString], r13w
0x180097c5e  mov     [rbp+1400h+var_1430], r13b
0x180097c62  mov     rbx, [rbp+1400h+arg_30]
0x180097c69  mov     ecx, [rbx]; this
0x180097c6b  mov     [rsp+1500h+var_14D8], ecx
0x180097c6f  mov     eax, [rbx+4]
0x180097c72  mov     [rsp+1500h+var_14D4], eax
0x180097c76  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180097c7b  mov     r12d, eax
0x180097c7e  mov     dword ptr [rsp+1500h+var_14E0], 3
0x180097c86  mov     ecx, r13d
0x180097c89  lea     eax, [r13+8]
0x180097c8d  cmp     dword ptr [rbx+8], 1
0x180097c91  cmovz   ecx, eax
0x180097c94  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180097c98  lea     ecx, [rax-7]
0x180097c9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180097ca3  inc     ecx
0x180097ca5  mov     [rsp+1500h+var_14D0], ecx
0x180097ca9  mov     rcx, [rbp+1400h+arg_38]
0x180097cb0  test    rcx, rcx
0x180097cb3  jz      short loc_180097CC0
0x180097cb5  cmp     [rcx], r13w
0x180097cb9  mov     [rsp+1500h+var_14C8], rcx
0x180097cbe  jnz     short loc_180097CC5
0x180097cc0  mov     [rsp+1500h+var_14C8], r13
0x180097cc5  call    cs:__imp_GetCurrentThreadId
0x180097ccc  nop     dword ptr [rax+rax+00h]
0x180097cd1  mov     [rsp+1500h+var_14C0], eax
0x180097cd5  mov     [rsp+1500h+var_14A8], r14
0x180097cda  mov     [rsp+1500h+var_14A0], esi
0x180097cde  mov     [rsp+1500h+var_149C], r12d
0x180097ce3  mov     [rsp+1500h+var_14B8], r13
0x180097ce8  mov     [rsp+1500h+var_14B0], r13
0x180097ced  mov     [rbp+1400h+var_1458], r15
0x180097cf1  mov     [rbp+1400h+var_1450], rdi
0x180097cf5  mov     [rsp+1500h+var_1498], r13
0x180097cfa  xorps   xmm0, xmm0
0x180097cfd  xor     eax, eax
0x180097cff  movups  [rbp+1400h+var_1478], xmm0
0x180097d03  mov     [rbp+1400h+var_1468], rax
0x180097d07  xorps   xmm1, xmm1
0x180097d0a  movups  [rsp+1500h+var_1490], xmm1
0x180097d0f  mov     [rbp+1400h+var_1480], rax
0x180097d13  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180097d1a  test    rax, rax
0x180097d1d  jz      short loc_180097D2A
0x180097d1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d24  mov     [rbp+1400h+var_1460], rax
0x180097d28  jmp     short loc_180097D2E
0x180097d2a  mov     [rbp+1400h+var_1460], r13
0x180097d2e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180097d35  test    rax, rax
0x180097d38  jz      short loc_180097D44
0x180097d3a  lea     rcx, [rsp+1500h+var_14E0]
0x180097d3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d44  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180097d4b  test    rax, rax
0x180097d4e  jz      short loc_180097D64
0x180097d50  mov     r8d, 400h
0x180097d56  lea     rdx, [rbp+1400h+var_1430]
0x180097d5a  lea     rcx, [rsp+1500h+var_14E0]
0x180097d5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d64  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180097d6b  test    rax, rax
0x180097d6e  jz      short loc_180097D7A
0x180097d70  lea     rcx, [rsp+1500h+var_14E0]
0x180097d75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d7a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180097d81  test    rax, rax
0x180097d84  jz      short loc_180097D97
0x180097d86  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180097d8b  jnz     short loc_180097D97
0x180097d8d  lea     rcx, [rsp+1500h+var_14E0]
0x180097d92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097d97  cmp     [rsp+1500h+var_14D8], r13d
0x180097d9c  jl      short loc_180097DB0
0x180097d9e  mov     ecx, 8000FFFFh; this
0x180097da3  mov     [rsp+1500h+var_14D8], ecx
0x180097da7  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180097dac  mov     [rsp+1500h+var_14D4], eax
0x180097db0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180097db7  jnz     short loc_180097DDE
0x180097db9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180097dc0  test    rax, rax
0x180097dc3  jz      short loc_180097DCE
0x180097dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097dca  test    al, al
0x180097dcc  jmp     short loc_180097DDC
0x180097dce  call    cs:__imp_IsDebuggerPresent
0x180097dd5  nop     dword ptr [rax+rax+00h]
0x180097dda  test    eax, eax
0x180097ddc  jz      short loc_180097DE5
0x180097dde  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180097de3  jz      short loc_180097E0B
0x180097de5  mov     rax, cs:g_pfnResultLoggingCallback
0x180097dec  test    rax, rax
0x180097def  jz      short loc_180097E6A
0x180097df1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180097df8  jnz     short loc_180097E6A
0x180097dfa  xor     r8d, r8d
0x180097dfd  xor     edx, edx
0x180097dff  lea     rcx, [rsp+1500h+var_14E0]
0x180097e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e09  jmp     short loc_180097E6A
0x180097e0b  mov     ebx, 800h
0x180097e10  mov     rax, cs:g_pfnResultLoggingCallback
0x180097e17  test    rax, rax
0x180097e1a  jz      short loc_180097E39
0x180097e1c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180097e23  jnz     short loc_180097E39
0x180097e25  mov     r8d, ebx
0x180097e28  lea     rdx, [rbp+1400h+OutputString]
0x180097e2f  lea     rcx, [rsp+1500h+var_14E0]
0x180097e34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e39  cmp     [rbp+1400h+OutputString], r13w
0x180097e41  jnz     short loc_180097E57
0x180097e43  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180097e48  mov     rdx, rbx; unsigned __int16 *
0x180097e4b  lea     rcx, [rbp+1400h+OutputString]; this
0x180097e52  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180097e57  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180097e5e  call    cs:__imp_OutputDebugStringW
0x180097e65  nop     dword ptr [rax+rax+00h]
0x180097e6a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180097e6f  jnz     short loc_180097E7A
0x180097e71  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180097e78  jz      short loc_180097E8C
0x180097e7a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180097e81  test    rax, rax
0x180097e84  jz      short loc_180097E8C
0x180097e86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180097e8b  nop
0x180097e8c  lea     rcx, [rsp+1500h+var_14E0]; this
0x180097e91  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
