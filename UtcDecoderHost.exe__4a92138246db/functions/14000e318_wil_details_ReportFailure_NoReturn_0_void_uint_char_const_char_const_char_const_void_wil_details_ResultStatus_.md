# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x14000e318`
- end: `0x14000e5c6`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `686`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x14000e1c8`

## callees

- `0x1400090ec`
- `0x14000c0b4`
- `0x14000ceb0`
- `0x14000d200`
- `0x14000d2dc`
- `0x14000e318`
- `0x140010c3c`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e3c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000e3c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000e55a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000e55a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e4c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000e4c3`

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
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  wchar_t *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "onecore\\base\\telemetry\\utc\\include\\StringUtils.h";
  v29 = a2;
  v30 = v10;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, v13, (unsigned __int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, (const struct wil::FailureInfo *)v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, (const struct wil::FailureInfo *)v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x14000e318  mov     [rsp-8+arg_10], rbx
0x14000e31d  mov     [rsp-8+arg_18], rsi
0x14000e322  push    rbp
0x14000e323  push    rdi
0x14000e324  push    r12
0x14000e326  push    r14
0x14000e328  push    r15
0x14000e32a  lea     rbp, [rsp-13C0h]
0x14000e332  mov     eax, 14C0h
0x14000e337  call    _alloca_probe
0x14000e33c  sub     rsp, rax
0x14000e33f  mov     esi, edx
0x14000e341  mov     r14, rcx
0x14000e344  mov     rdi, [rbp+13E0h+arg_28]
0x14000e34b  xor     r12d, r12d
0x14000e34e  cmp     cs:g_pfnThrowPlatformException, r12
0x14000e355  setnz   r15b
0x14000e359  xor     edx, edx; Val
0x14000e35b  mov     r8d, 98h; Size
0x14000e361  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x14000e366  call    memset_0
0x14000e36b  nop
0x14000e36c  mov     [rbp+13E0h+OutputString], r12w
0x14000e374  mov     [rbp+13E0h+var_1420], r12b
0x14000e378  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x14000e37f  mov     ecx, [rdx]; this
0x14000e381  mov     [rsp+14E0h+var_14B8], ecx
0x14000e385  mov     eax, [rdx+4]
0x14000e388  mov     [rsp+14E0h+var_14B4], eax
0x14000e38c  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000e391  mov     ebx, eax
0x14000e393  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x14000e398  mov     ecx, r12d
0x14000e39b  lea     eax, [r12+8]
0x14000e3a0  cmp     dword ptr [rdx+8], 1
0x14000e3a4  cmovz   ecx, eax
0x14000e3a7  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x14000e3ab  lea     ecx, [rax-7]
0x14000e3ae  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000e3b6  inc     ecx
0x14000e3b8  mov     [rsp+14E0h+var_14B0], ecx
0x14000e3bc  mov     [rsp+14E0h+var_14A8], r12
0x14000e3c1  call    cs:__imp_GetCurrentThreadId
0x14000e3c7  mov     [rsp+14E0h+var_14A0], eax
0x14000e3cb  lea     rax, aOnecoreBaseTel_0; "onecore\\base\\telemetry\\utc\\include"...
0x14000e3d2  mov     [rsp+14E0h+var_1488], rax
0x14000e3d7  mov     [rsp+14E0h+var_1480], esi
0x14000e3db  mov     [rsp+14E0h+var_147C], ebx
0x14000e3df  mov     [rsp+14E0h+var_1498], r12
0x14000e3e4  mov     [rsp+14E0h+var_1490], r12
0x14000e3e9  mov     [rbp+13E0h+var_1438], rdi
0x14000e3ed  mov     [rbp+13E0h+var_1430], r14
0x14000e3f1  mov     [rsp+14E0h+var_1478], r12
0x14000e3f6  xorps   xmm0, xmm0
0x14000e3f9  xor     eax, eax
0x14000e3fb  movups  [rbp+13E0h+var_1458], xmm0
0x14000e3ff  mov     [rbp+13E0h+var_1448], rax
0x14000e403  xorps   xmm1, xmm1
0x14000e406  movups  [rsp+14E0h+var_1470], xmm1
0x14000e40b  mov     [rbp+13E0h+var_1460], rax
0x14000e40f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000e416  test    rax, rax
0x14000e419  jz      short loc_14000E426
0x14000e41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e420  mov     [rbp+13E0h+var_1440], rax
0x14000e424  jmp     short loc_14000E42A
0x14000e426  mov     [rbp+13E0h+var_1440], r12
0x14000e42a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000e431  test    rax, rax
0x14000e434  jz      short loc_14000E440
0x14000e436  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e43b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e440  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000e447  test    rax, rax
0x14000e44a  jz      short loc_14000E460
0x14000e44c  mov     r8d, 400h
0x14000e452  lea     rdx, [rbp+13E0h+var_1420]
0x14000e456  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e45b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e460  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e467  test    rax, rax
0x14000e46a  jz      short loc_14000E476
0x14000e46c  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e471  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e476  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000e47d  test    rax, rax
0x14000e480  jz      short loc_14000E498
0x14000e482  test    r15b, r15b
0x14000e485  jnz     short loc_14000E498
0x14000e487  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000e48c  jnz     short loc_14000E498
0x14000e48e  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e498  cmp     [rsp+14E0h+var_14B8], r12d
0x14000e49d  jl      short loc_14000E4A5
0x14000e49f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000e4a5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000e4ac  jnz     short loc_14000E4CD
0x14000e4ae  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000e4b5  test    rax, rax
0x14000e4b8  jz      short loc_14000E4C3
0x14000e4ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e4bf  test    al, al
0x14000e4c1  jmp     short loc_14000E4CB
0x14000e4c3  call    cs:__imp_IsDebuggerPresent
0x14000e4c9  test    eax, eax
0x14000e4cb  jz      short loc_14000E4D6
0x14000e4cd  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x14000e4d2  mov     bl, 1
0x14000e4d4  jz      short loc_14000E4D9
0x14000e4d6  mov     bl, r12b
0x14000e4d9  test    r15b, r15b
0x14000e4dc  jnz     short loc_14000E508
0x14000e4de  test    bl, bl
0x14000e4e0  jnz     short loc_14000E508
0x14000e4e2  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e4e9  test    rax, rax
0x14000e4ec  jz      short loc_14000E560
0x14000e4ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000e4f5  jnz     short loc_14000E560
0x14000e4f7  xor     r8d, r8d
0x14000e4fa  xor     edx, edx
0x14000e4fc  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e501  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e506  jmp     short loc_14000E560
0x14000e508  mov     rax, cs:g_pfnResultLoggingCallback
0x14000e50f  test    rax, rax
0x14000e512  jz      short loc_14000E534
0x14000e514  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000e51b  jnz     short loc_14000E534
0x14000e51d  mov     r8d, 800h
0x14000e523  lea     rdx, [rbp+13E0h+OutputString]
0x14000e52a  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e52f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e534  cmp     [rbp+13E0h+OutputString], r12w
0x14000e53c  jnz     short loc_14000E54F
0x14000e53e  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x14000e543  lea     rcx, [rbp+13E0h+OutputString]; this
0x14000e54a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14000e54f  test    bl, bl
0x14000e551  jz      short loc_14000E560
0x14000e553  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x14000e55a  call    cs:__imp_OutputDebugStringW
0x14000e560  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x14000e565  jnz     short loc_14000E570
0x14000e567  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000e56e  jz      short loc_14000E582
0x14000e570  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000e577  test    rax, rax
0x14000e57a  jz      short loc_14000E582
0x14000e57c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e581  nop
0x14000e582  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x14000e587  jz      short loc_14000E594
0x14000e589  lea     rcx, [rsp+14E0h+var_14C0]; this
0x14000e58e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000e594  test    r15b, r15b
0x14000e597  jz      short loc_14000E5B1
0x14000e599  lea     rdx, [rbp+13E0h+OutputString]
0x14000e5a0  lea     rcx, [rsp+14E0h+var_14C0]
0x14000e5a5  mov     rax, cs:g_pfnThrowPlatformException
0x14000e5ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e5b1  lea     rcx, [rsp+14E0h+var_14C0]; this
0x14000e5b6  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x14000e5bb  lea     rcx, [rsp+14E0h+var_14C0]; this
0x14000e5c0  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
