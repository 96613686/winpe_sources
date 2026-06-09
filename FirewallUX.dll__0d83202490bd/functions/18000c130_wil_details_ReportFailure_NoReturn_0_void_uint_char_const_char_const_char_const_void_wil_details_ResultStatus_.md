# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000c130`
- end: `0x18000c3dc`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000be74`

## callees

- `0x180002c04`
- `0x1800072bc`
- `0x180008b50`
- `0x18000a3f4`
- `0x18000a7b0`
- `0x18000a938`
- `0x18000c130`
- `0x180029890`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c1d9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c1d9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c2d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c2d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c370`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c370`

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
0x18000c130  mov     [rsp-8+arg_18], rbx
0x18000c135  push    rbp
0x18000c136  push    rsi
0x18000c137  push    rdi
0x18000c138  push    r12
0x18000c13a  push    r13
0x18000c13c  push    r14
0x18000c13e  push    r15
0x18000c140  lea     rbp, [rsp-13C0h]
0x18000c148  mov     eax, 14C0h
0x18000c14d  call    _alloca_probe
0x18000c152  sub     rsp, rax
0x18000c155  mov     r14, r8
0x18000c158  mov     esi, edx
0x18000c15a  mov     r15, rcx
0x18000c15d  mov     rdi, [rbp+13F0h+arg_28]
0x18000c164  xor     r13d, r13d
0x18000c167  cmp     cs:g_pfnThrowPlatformException, r13
0x18000c16e  setnz   r12b
0x18000c172  xor     edx, edx; Val
0x18000c174  mov     r8d, 98h; Size
0x18000c17a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000c17f  call    memset_0
0x18000c184  nop
0x18000c185  mov     [rbp+13F0h+OutputString], r13w
0x18000c18d  mov     [rbp+13F0h+var_1430], r13b
0x18000c191  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000c198  mov     ecx, [rdx]; this
0x18000c19a  mov     [rsp+14F0h+var_14C8], ecx
0x18000c19e  mov     eax, [rdx+4]
0x18000c1a1  mov     [rsp+14F0h+var_14C4], eax
0x18000c1a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c1aa  mov     ebx, eax
0x18000c1ac  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000c1b1  mov     ecx, r13d
0x18000c1b4  lea     eax, [r13+8]
0x18000c1b8  cmp     dword ptr [rdx+8], 1
0x18000c1bc  cmovz   ecx, eax
0x18000c1bf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000c1c3  lea     ecx, [rax-7]
0x18000c1c6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c1ce  inc     ecx
0x18000c1d0  mov     [rsp+14F0h+var_14C0], ecx
0x18000c1d4  mov     [rsp+14F0h+var_14B8], r13
0x18000c1d9  call    cs:__imp_GetCurrentThreadId
0x18000c1df  mov     [rsp+14F0h+var_14B0], eax
0x18000c1e3  mov     [rsp+14F0h+var_1498], r14
0x18000c1e8  mov     [rsp+14F0h+var_1490], esi
0x18000c1ec  mov     [rsp+14F0h+var_148C], ebx
0x18000c1f0  mov     [rsp+14F0h+var_14A8], r13
0x18000c1f5  mov     [rsp+14F0h+var_14A0], r13
0x18000c1fa  mov     [rbp+13F0h+var_1448], rdi
0x18000c1fe  mov     [rbp+13F0h+var_1440], r15
0x18000c202  mov     [rsp+14F0h+var_1488], r13
0x18000c207  xorps   xmm0, xmm0
0x18000c20a  xor     eax, eax
0x18000c20c  movups  [rbp+13F0h+var_1468], xmm0
0x18000c210  mov     [rbp+13F0h+var_1458], rax
0x18000c214  xorps   xmm1, xmm1
0x18000c217  movups  [rsp+14F0h+var_1480], xmm1
0x18000c21c  mov     [rbp+13F0h+var_1470], rax
0x18000c220  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c227  test    rax, rax
0x18000c22a  jz      short loc_18000C237
0x18000c22c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c231  mov     [rbp+13F0h+var_1450], rax
0x18000c235  jmp     short loc_18000C23B
0x18000c237  mov     [rbp+13F0h+var_1450], r13
0x18000c23b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c242  test    rax, rax
0x18000c245  jz      short loc_18000C251
0x18000c247  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c24c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c251  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c258  test    rax, rax
0x18000c25b  jz      short loc_18000C271
0x18000c25d  mov     r8d, 400h
0x18000c263  lea     rdx, [rbp+13F0h+var_1430]
0x18000c267  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c26c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c271  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c278  test    rax, rax
0x18000c27b  jz      short loc_18000C287
0x18000c27d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c282  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c287  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c28e  test    rax, rax
0x18000c291  jz      short loc_18000C2A9
0x18000c293  test    r12b, r12b
0x18000c296  jnz     short loc_18000C2A9
0x18000c298  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000c29d  jnz     short loc_18000C2A9
0x18000c29f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c2a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2a9  cmp     [rsp+14F0h+var_14C8], r13d
0x18000c2ae  jl      short loc_18000C2B6
0x18000c2b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000c2b6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000c2bd  jnz     short loc_18000C2DE
0x18000c2bf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c2c6  test    rax, rax
0x18000c2c9  jz      short loc_18000C2D4
0x18000c2cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c2d0  test    al, al
0x18000c2d2  jmp     short loc_18000C2DC
0x18000c2d4  call    cs:__imp_IsDebuggerPresent
0x18000c2da  test    eax, eax
0x18000c2dc  jz      short loc_18000C2E7
0x18000c2de  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000c2e3  mov     bl, 1
0x18000c2e5  jz      short loc_18000C2EA
0x18000c2e7  mov     bl, r13b
0x18000c2ea  test    r12b, r12b
0x18000c2ed  jnz     short loc_18000C319
0x18000c2ef  test    bl, bl
0x18000c2f1  jnz     short loc_18000C319
0x18000c2f3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c2fa  test    rax, rax
0x18000c2fd  jz      short loc_18000C376
0x18000c2ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000c306  jnz     short loc_18000C376
0x18000c308  xor     r8d, r8d
0x18000c30b  xor     edx, edx
0x18000c30d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c312  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c317  jmp     short loc_18000C376
0x18000c319  mov     edi, 800h
0x18000c31e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c325  test    rax, rax
0x18000c328  jz      short loc_18000C347
0x18000c32a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000c331  jnz     short loc_18000C347
0x18000c333  mov     r8d, edi
0x18000c336  lea     rdx, [rbp+13F0h+OutputString]
0x18000c33d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c342  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c347  cmp     [rbp+13F0h+OutputString], r13w
0x18000c34f  jnz     short loc_18000C365
0x18000c351  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000c356  mov     rdx, rdi; unsigned __int16 *
0x18000c359  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000c360  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c365  test    bl, bl
0x18000c367  jz      short loc_18000C376
0x18000c369  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000c370  call    cs:__imp_OutputDebugStringW
0x18000c376  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000c37b  jnz     short loc_18000C386
0x18000c37d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000c384  jz      short loc_18000C398
0x18000c386  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c38d  test    rax, rax
0x18000c390  jz      short loc_18000C398
0x18000c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c397  nop
0x18000c398  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000c39d  jz      short loc_18000C3AA
0x18000c39f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c3a4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c3aa  test    r12b, r12b
0x18000c3ad  jz      short loc_18000C3C7
0x18000c3af  lea     rdx, [rbp+13F0h+OutputString]
0x18000c3b6  lea     rcx, [rsp+14F0h+var_14D0]
0x18000c3bb  mov     rax, cs:g_pfnThrowPlatformException
0x18000c3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c3cc  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000c3d1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000c3d6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
