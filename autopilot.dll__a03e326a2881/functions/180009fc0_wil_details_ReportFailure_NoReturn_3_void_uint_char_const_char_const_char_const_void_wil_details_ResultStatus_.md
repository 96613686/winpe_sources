# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009fc0`
- end: `0x18000a239`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009d40`

## callees

- `0x180005374`
- `0x180009fc0`
- `0x18000d284`
- `0x18000db8c`
- `0x18000f090`
- `0x180011e10`
- `0x1800281e0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a079`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a079`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a17c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a17c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a206`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a206`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
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
0x180009fc0  mov     [rsp-8+arg_18], rbx
0x180009fc5  push    rbp
0x180009fc6  push    rsi
0x180009fc7  push    rdi
0x180009fc8  push    r12
0x180009fca  push    r13
0x180009fcc  push    r14
0x180009fce  push    r15
0x180009fd0  lea     rbp, [rsp-13C0h]
0x180009fd8  mov     eax, 14C0h
0x180009fdd  call    _alloca_probe
0x180009fe2  sub     rsp, rax
0x180009fe5  mov     r14, r8
0x180009fe8  mov     esi, edx
0x180009fea  mov     rdi, rcx
0x180009fed  mov     r15, [rbp+13F0h+arg_28]
0x180009ff4  xor     edx, edx; Val
0x180009ff6  mov     r8d, 98h; Size
0x180009ffc  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000a001  call    memset_0
0x18000a006  nop
0x18000a007  xor     r13d, r13d
0x18000a00a  mov     [rbp+13F0h+OutputString], r13w
0x18000a012  mov     [rbp+13F0h+var_1430], r13b
0x18000a016  mov     rbx, [rbp+13F0h+arg_30]
0x18000a01d  mov     ecx, [rbx]; this
0x18000a01f  mov     [rsp+14F0h+var_14C8], ecx
0x18000a023  mov     eax, [rbx+4]
0x18000a026  mov     [rsp+14F0h+var_14C4], eax
0x18000a02a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a02f  mov     r12d, eax
0x18000a032  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000a03a  mov     ecx, r13d
0x18000a03d  lea     eax, [r13+8]
0x18000a041  cmp     dword ptr [rbx+8], 1
0x18000a045  cmovz   ecx, eax
0x18000a048  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000a04c  lea     ecx, [rax-7]
0x18000a04f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a057  inc     ecx
0x18000a059  mov     [rsp+14F0h+var_14C0], ecx
0x18000a05d  mov     rcx, [rbp+13F0h+arg_38]
0x18000a064  test    rcx, rcx
0x18000a067  jz      short loc_18000A074
0x18000a069  cmp     [rcx], r13w
0x18000a06d  mov     [rsp+14F0h+var_14B8], rcx
0x18000a072  jnz     short loc_18000A079
0x18000a074  mov     [rsp+14F0h+var_14B8], r13
0x18000a079  call    cs:__imp_GetCurrentThreadId
0x18000a07f  mov     [rsp+14F0h+var_14B0], eax
0x18000a083  mov     [rsp+14F0h+var_1498], r14
0x18000a088  mov     [rsp+14F0h+var_1490], esi
0x18000a08c  mov     [rsp+14F0h+var_148C], r12d
0x18000a091  mov     [rsp+14F0h+var_14A8], r13
0x18000a096  mov     [rsp+14F0h+var_14A0], r13
0x18000a09b  mov     [rbp+13F0h+var_1448], r15
0x18000a09f  mov     [rbp+13F0h+var_1440], rdi
0x18000a0a3  mov     [rsp+14F0h+var_1488], r13
0x18000a0a8  xorps   xmm0, xmm0
0x18000a0ab  xor     eax, eax
0x18000a0ad  movups  [rbp+13F0h+var_1468], xmm0
0x18000a0b1  mov     [rbp+13F0h+var_1458], rax
0x18000a0b5  xorps   xmm1, xmm1
0x18000a0b8  movups  [rsp+14F0h+var_1480], xmm1
0x18000a0bd  mov     [rbp+13F0h+var_1470], rax
0x18000a0c1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a0c8  test    rax, rax
0x18000a0cb  jz      short loc_18000A0D8
0x18000a0cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0d2  mov     [rbp+13F0h+var_1450], rax
0x18000a0d6  jmp     short loc_18000A0DC
0x18000a0d8  mov     [rbp+13F0h+var_1450], r13
0x18000a0dc  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a0e3  test    rax, rax
0x18000a0e6  jz      short loc_18000A0F2
0x18000a0e8  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a0ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0f2  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a0f9  test    rax, rax
0x18000a0fc  jz      short loc_18000A112
0x18000a0fe  mov     r8d, 400h
0x18000a104  lea     rdx, [rbp+13F0h+var_1430]
0x18000a108  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a10d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a112  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a119  test    rax, rax
0x18000a11c  jz      short loc_18000A128
0x18000a11e  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a123  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a128  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a12f  test    rax, rax
0x18000a132  jz      short loc_18000A145
0x18000a134  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a139  jnz     short loc_18000A145
0x18000a13b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a145  cmp     [rsp+14F0h+var_14C8], r13d
0x18000a14a  jl      short loc_18000A15E
0x18000a14c  mov     ecx, 8000FFFFh; this
0x18000a151  mov     [rsp+14F0h+var_14C8], ecx
0x18000a155  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a15a  mov     [rsp+14F0h+var_14C4], eax
0x18000a15e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000a165  jnz     short loc_18000A186
0x18000a167  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a16e  test    rax, rax
0x18000a171  jz      short loc_18000A17C
0x18000a173  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a178  test    al, al
0x18000a17a  jmp     short loc_18000A184
0x18000a17c  call    cs:__imp_IsDebuggerPresent
0x18000a182  test    eax, eax
0x18000a184  jz      short loc_18000A18D
0x18000a186  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a18b  jz      short loc_18000A1B3
0x18000a18d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a194  test    rax, rax
0x18000a197  jz      short loc_18000A20C
0x18000a199  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a1a0  jnz     short loc_18000A20C
0x18000a1a2  xor     r8d, r8d
0x18000a1a5  xor     edx, edx
0x18000a1a7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a1ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b1  jmp     short loc_18000A20C
0x18000a1b3  mov     ebx, 800h
0x18000a1b8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a1bf  test    rax, rax
0x18000a1c2  jz      short loc_18000A1E1
0x18000a1c4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a1cb  jnz     short loc_18000A1E1
0x18000a1cd  mov     r8d, ebx
0x18000a1d0  lea     rdx, [rbp+13F0h+OutputString]
0x18000a1d7  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e1  cmp     [rbp+13F0h+OutputString], r13w
0x18000a1e9  jnz     short loc_18000A1FF
0x18000a1eb  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000a1f0  mov     rdx, rbx; unsigned __int16 *
0x18000a1f3  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000a1fa  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a1ff  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000a206  call    cs:__imp_OutputDebugStringW
0x18000a20c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000a211  jnz     short loc_18000A21C
0x18000a213  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000a21a  jz      short loc_18000A22E
0x18000a21c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a223  test    rax, rax
0x18000a226  jz      short loc_18000A22E
0x18000a228  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a22d  nop
0x18000a22e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a233  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
