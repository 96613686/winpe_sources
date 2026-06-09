# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180004c4c`
- end: `0x180004ed1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `645`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004870`

## callees

- `0x1800042f4`
- `0x180004c4c`
- `0x1800075f4`
- `0x180007f7c`
- `0x180009030`
- `0x18000bcd0`
- `0x180031b80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d12`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004d12`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004e9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004e9e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004e14`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004e14`

## pseudocode

```c
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
  int v18; // [rsp+30h] [rbp-D0h] BYREF
  int v19; // [rsp+34h] [rbp-CCh]
  int v20; // [rsp+38h] [rbp-C8h]
  int v21; // [rsp+3Ch] [rbp-C4h]
  signed __int32 v22; // [rsp+40h] [rbp-C0h]
  _WORD *v23; // [rsp+48h] [rbp-B8h]
  DWORD CurrentThreadId; // [rsp+50h] [rbp-B0h]
  __int64 v25; // [rsp+58h] [rbp-A8h]
  __int64 v26; // [rsp+60h] [rbp-A0h]
  __int64 v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+70h] [rbp-90h]
  int v29; // [rsp+74h] [rbp-8Ch]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int128 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+90h] [rbp-70h]
  __int128 v33; // [rsp+98h] [rbp-68h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 ModuleName; // [rsp+B0h] [rbp-50h]
  __int64 v36; // [rsp+B8h] [rbp-48h]
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

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
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180004c4c  push    rbp
0x180004c4e  push    rsi
0x180004c4f  push    rdi
0x180004c50  push    r12
0x180004c52  push    r13
0x180004c54  push    r14
0x180004c56  push    r15
0x180004c58  lea     rbp, [rsp-13D0h]
0x180004c60  mov     eax, 14D0h
0x180004c65  call    _alloca_probe
0x180004c6a  sub     rsp, rax
0x180004c6d  mov     [rsp+1500h+var_14E0], 0FFFFFFFFFFFFFFFEh
0x180004c76  mov     [rsp+1500h+arg_18], rbx
0x180004c7e  mov     r14, r8
0x180004c81  mov     esi, edx
0x180004c83  mov     rdi, rcx
0x180004c86  mov     r15, [rbp+1400h+arg_28]
0x180004c8d  xor     edx, edx; Val
0x180004c8f  mov     r8d, 98h; Size
0x180004c95  lea     rcx, [rsp+1500h+var_14D0]; void *
0x180004c9a  call    memset_0
0x180004c9f  nop
0x180004ca0  xor     r13d, r13d
0x180004ca3  mov     [rbp+1400h+OutputString], r13w
0x180004cab  mov     [rbp+1400h+var_1430], r13b
0x180004caf  mov     rbx, [rbp+1400h+arg_30]
0x180004cb6  mov     ecx, [rbx]; this
0x180004cb8  mov     [rsp+1500h+var_14C8], ecx
0x180004cbc  mov     eax, [rbx+4]
0x180004cbf  mov     [rsp+1500h+var_14C4], eax
0x180004cc3  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004cc8  mov     r12d, eax
0x180004ccb  mov     dword ptr [rsp+1500h+var_14D0], 3
0x180004cd3  mov     ecx, r13d
0x180004cd6  lea     eax, [r13+8]
0x180004cda  cmp     dword ptr [rbx+8], 1
0x180004cde  cmovz   ecx, eax
0x180004ce1  mov     dword ptr [rsp+1500h+var_14D0+4], ecx
0x180004ce5  lea     ecx, [rax-7]
0x180004ce8  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004cf0  inc     ecx
0x180004cf2  mov     [rsp+1500h+var_14C0], ecx
0x180004cf6  mov     rcx, [rbp+1400h+arg_38]
0x180004cfd  test    rcx, rcx
0x180004d00  jz      short loc_180004D0D
0x180004d02  cmp     [rcx], r13w
0x180004d06  mov     [rsp+1500h+var_14B8], rcx
0x180004d0b  jnz     short loc_180004D12
0x180004d0d  mov     [rsp+1500h+var_14B8], r13
0x180004d12  call    cs:__imp_GetCurrentThreadId
0x180004d18  mov     [rsp+1500h+var_14B0], eax
0x180004d1c  mov     [rsp+1500h+var_1498], r14
0x180004d21  mov     [rsp+1500h+var_1490], esi
0x180004d25  mov     [rsp+1500h+var_148C], r12d
0x180004d2a  mov     [rsp+1500h+var_14A8], r13
0x180004d2f  mov     [rsp+1500h+var_14A0], r13
0x180004d34  mov     [rbp+1400h+var_1448], r15
0x180004d38  mov     [rbp+1400h+var_1440], rdi
0x180004d3c  mov     [rsp+1500h+var_1488], r13
0x180004d41  xorps   xmm0, xmm0
0x180004d44  xor     eax, eax
0x180004d46  movups  [rbp+1400h+var_1468], xmm0
0x180004d4a  mov     [rbp+1400h+var_1458], rax
0x180004d4e  xorps   xmm1, xmm1
0x180004d51  movups  [rbp+1400h+var_1480], xmm1
0x180004d55  mov     [rbp+1400h+var_1470], rax
0x180004d59  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004d60  test    rax, rax
0x180004d63  jz      short loc_180004D70
0x180004d65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d6a  mov     [rbp+1400h+var_1450], rax
0x180004d6e  jmp     short loc_180004D74
0x180004d70  mov     [rbp+1400h+var_1450], r13
0x180004d74  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004d7b  test    rax, rax
0x180004d7e  jz      short loc_180004D8A
0x180004d80  lea     rcx, [rsp+1500h+var_14D0]
0x180004d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004d8a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004d91  test    rax, rax
0x180004d94  jz      short loc_180004DAA
0x180004d96  mov     r8d, 400h
0x180004d9c  lea     rdx, [rbp+1400h+var_1430]
0x180004da0  lea     rcx, [rsp+1500h+var_14D0]
0x180004da5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004daa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004db1  test    rax, rax
0x180004db4  jz      short loc_180004DC0
0x180004db6  lea     rcx, [rsp+1500h+var_14D0]
0x180004dbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004dc0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004dc7  test    rax, rax
0x180004dca  jz      short loc_180004DDD
0x180004dcc  test    byte ptr [rsp+1500h+var_14D0+4], 2
0x180004dd1  jnz     short loc_180004DDD
0x180004dd3  lea     rcx, [rsp+1500h+var_14D0]
0x180004dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ddd  cmp     [rsp+1500h+var_14C8], r13d
0x180004de2  jl      short loc_180004DF6
0x180004de4  mov     ecx, 8000FFFFh; this
0x180004de9  mov     [rsp+1500h+var_14C8], ecx
0x180004ded  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004df2  mov     [rsp+1500h+var_14C4], eax
0x180004df6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004dfd  jnz     short loc_180004E1E
0x180004dff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004e06  test    rax, rax
0x180004e09  jz      short loc_180004E14
0x180004e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e10  test    al, al
0x180004e12  jmp     short loc_180004E1C
0x180004e14  call    cs:__imp_IsDebuggerPresent
0x180004e1a  test    eax, eax
0x180004e1c  jz      short loc_180004E25
0x180004e1e  test    byte ptr [rsp+1500h+var_14D0+4], 2
0x180004e23  jz      short loc_180004E4B
0x180004e25  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e2c  test    rax, rax
0x180004e2f  jz      short loc_180004EA4
0x180004e31  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004e38  jnz     short loc_180004EA4
0x180004e3a  xor     r8d, r8d
0x180004e3d  xor     edx, edx
0x180004e3f  lea     rcx, [rsp+1500h+var_14D0]
0x180004e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e49  jmp     short loc_180004EA4
0x180004e4b  mov     ebx, 800h
0x180004e50  mov     rax, cs:g_pfnResultLoggingCallback
0x180004e57  test    rax, rax
0x180004e5a  jz      short loc_180004E79
0x180004e5c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004e63  jnz     short loc_180004E79
0x180004e65  mov     r8d, ebx
0x180004e68  lea     rdx, [rbp+1400h+OutputString]
0x180004e6f  lea     rcx, [rsp+1500h+var_14D0]
0x180004e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e79  cmp     [rbp+1400h+OutputString], r13w
0x180004e81  jnz     short loc_180004E97
0x180004e83  lea     r8, [rsp+1500h+var_14D0]; unsigned __int64
0x180004e88  mov     rdx, rbx; wchar_t *
0x180004e8b  lea     rcx, [rbp+1400h+OutputString]; this
0x180004e92  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180004e97  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004e9e  call    cs:__imp_OutputDebugStringW
0x180004ea4  test    byte ptr [rsp+1500h+var_14D0+4], 4
0x180004ea9  jnz     short loc_180004EB4
0x180004eab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004eb2  jz      short loc_180004EC6
0x180004eb4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004ebb  test    rax, rax
0x180004ebe  jz      short loc_180004EC6
0x180004ec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ec5  nop
0x180004ec6  lea     rcx, [rsp+1500h+var_14D0]; this
0x180004ecb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
