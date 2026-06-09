# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000bf64`
- end: `0x18000c210`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000beb8`

## callees

- `0x18000526c`
- `0x180008094`
- `0x180009758`
- `0x18000b378`
- `0x18000ba00`
- `0x18000baf4`
- `0x18000bf64`
- `0x18003e3f0`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c00d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c00d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c108`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c108`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x18000bf64  mov     [rsp-8+arg_18], rbx
0x18000bf69  push    rbp
0x18000bf6a  push    rsi
0x18000bf6b  push    rdi
0x18000bf6c  push    r12
0x18000bf6e  push    r13
0x18000bf70  push    r14
0x18000bf72  push    r15
0x18000bf74  lea     rbp, [rsp-13C0h]
0x18000bf7c  mov     eax, 14C0h
0x18000bf81  call    _alloca_probe
0x18000bf86  sub     rsp, rax
0x18000bf89  mov     r14, r8
0x18000bf8c  mov     esi, edx
0x18000bf8e  mov     r15, rcx
0x18000bf91  mov     rdi, [rbp+13F0h+arg_28]
0x18000bf98  xor     r13d, r13d
0x18000bf9b  cmp     cs:g_pfnThrowPlatformException, r13
0x18000bfa2  setnz   r12b
0x18000bfa6  xor     edx, edx; Val
0x18000bfa8  mov     r8d, 98h; Size
0x18000bfae  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000bfb3  call    memset_0
0x18000bfb8  nop
0x18000bfb9  mov     [rbp+13F0h+OutputString], r13w
0x18000bfc1  mov     [rbp+13F0h+var_1430], r13b
0x18000bfc5  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000bfcc  mov     ecx, [rdx]; this
0x18000bfce  mov     [rsp+14F0h+var_14C8], ecx
0x18000bfd2  mov     eax, [rdx+4]
0x18000bfd5  mov     [rsp+14F0h+var_14C4], eax
0x18000bfd9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000bfde  mov     ebx, eax
0x18000bfe0  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000bfe5  mov     ecx, r13d
0x18000bfe8  lea     eax, [r13+8]
0x18000bfec  cmp     dword ptr [rdx+8], 1
0x18000bff0  cmovz   ecx, eax
0x18000bff3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000bff7  lea     ecx, [rax-7]
0x18000bffa  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c002  inc     ecx
0x18000c004  mov     [rsp+14F0h+var_14C0], ecx
0x18000c008  mov     [rsp+14F0h+var_14B8], r13
0x18000c00d  call    cs:__imp_GetCurrentThreadId
0x18000c013  mov     [rsp+14F0h+var_14B0], eax
0x18000c017  mov     [rsp+14F0h+var_1498], r14
0x18000c01c  mov     [rsp+14F0h+var_1490], esi
0x18000c020  mov     [rsp+14F0h+var_148C], ebx
0x18000c024  mov     [rsp+14F0h+var_14A8], r13
0x18000c029  mov     [rsp+14F0h+var_14A0], r13
0x18000c02e  mov     [rbp+13F0h+var_1448], rdi
0x18000c032  mov     [rbp+13F0h+var_1440], r15
0x18000c036  mov     [rsp+14F0h+var_1488], r13
0x18000c03b  xorps   xmm0, xmm0
0x18000c03e  xor     eax, eax
0x18000c040  movups  [rbp+13F0h+var_1468], xmm0
0x18000c044  mov     [rbp+13F0h+var_1458], rax
0x18000c048  xorps   xmm1, xmm1
0x18000c04b  movups  [rsp+14F0h+var_1480], xmm1
0x18000c050  mov     [rbp+13F0h+var_1470], rax
0x18000c054  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c05b  test    rax, rax
0x18000c05e  jz      short loc_18000C06B
0x18000c060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c065  mov     [rbp+13F0h+var_1450], rax
0x18000c069  jmp     short loc_18000C06F
0x18000c06b  mov     [rbp+13F0h+var_1450], r13
0x18000c06f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c076  test    rax, rax
0x18000c079  jz      short loc_18000C085
0x18000c07b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c080  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c085  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c08c  test    rax, rax
0x18000c08f  jz      short loc_18000C0A5
0x18000c091  mov     r8d, 400h
0x18000c097  lea     rdx, [rbp+13F0h+var_1430]
0x18000c09b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c0a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0a5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c0ac  test    rax, rax
0x18000c0af  jz      short loc_18000C0BB
0x18000c0b1  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c0c2  test    rax, rax
0x18000c0c5  jz      short loc_18000C0DD
0x18000c0c7  test    r12b, r12b
0x18000c0ca  jnz     short loc_18000C0DD
0x18000c0cc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000c0d1  jnz     short loc_18000C0DD
0x18000c0d3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c0d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0dd  cmp     [rsp+14F0h+var_14C8], r13d
0x18000c0e2  jl      short loc_18000C0EA
0x18000c0e4  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c0ea  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000c0f1  jnz     short loc_18000C112
0x18000c0f3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c0fa  test    rax, rax
0x18000c0fd  jz      short loc_18000C108
0x18000c0ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c104  test    al, al
0x18000c106  jmp     short loc_18000C110
0x18000c108  call    cs:__imp_IsDebuggerPresent
0x18000c10e  test    eax, eax
0x18000c110  jz      short loc_18000C11B
0x18000c112  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000c117  mov     bl, 1
0x18000c119  jz      short loc_18000C11E
0x18000c11b  mov     bl, r13b
0x18000c11e  test    r12b, r12b
0x18000c121  jnz     short loc_18000C14D
0x18000c123  test    bl, bl
0x18000c125  jnz     short loc_18000C14D
0x18000c127  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c12e  test    rax, rax
0x18000c131  jz      short loc_18000C1AA
0x18000c133  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000c13a  jnz     short loc_18000C1AA
0x18000c13c  xor     r8d, r8d
0x18000c13f  xor     edx, edx
0x18000c141  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c14b  jmp     short loc_18000C1AA
0x18000c14d  mov     edi, 800h
0x18000c152  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c159  test    rax, rax
0x18000c15c  jz      short loc_18000C17B
0x18000c15e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000c165  jnz     short loc_18000C17B
0x18000c167  mov     r8d, edi
0x18000c16a  lea     rdx, [rbp+13F0h+OutputString]
0x18000c171  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c17b  cmp     [rbp+13F0h+OutputString], r13w
0x18000c183  jnz     short loc_18000C199
0x18000c185  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000c18a  mov     rdx, rdi; unsigned __int16 *
0x18000c18d  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000c194  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c199  test    bl, bl
0x18000c19b  jz      short loc_18000C1AA
0x18000c19d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000c1a4  call    cs:__imp_OutputDebugStringW
0x18000c1aa  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000c1af  jnz     short loc_18000C1BA
0x18000c1b1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000c1b8  jz      short loc_18000C1CC
0x18000c1ba  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c1c1  test    rax, rax
0x18000c1c4  jz      short loc_18000C1CC
0x18000c1c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1cb  nop
0x18000c1cc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000c1d1  jz      short loc_18000C1DE
0x18000c1d3  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c1d8  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c1de  test    r12b, r12b
0x18000c1e1  jz      short loc_18000C1FB
0x18000c1e3  lea     rdx, [rbp+13F0h+OutputString]
0x18000c1ea  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c1ef  mov     rax, cs:g_pfnThrowPlatformException
0x18000c1f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1fb  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c200  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000c205  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c20a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
