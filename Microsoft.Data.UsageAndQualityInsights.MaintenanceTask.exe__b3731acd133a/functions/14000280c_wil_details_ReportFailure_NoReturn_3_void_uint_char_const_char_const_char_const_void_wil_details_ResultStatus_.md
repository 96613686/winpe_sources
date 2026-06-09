# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x14000280c`
- end: `0x140002a6e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1400025b0`

## callees

- `0x14000221c`
- `0x14000280c`
- `0x140004d14`
- `0x1400054b0`
- `0x1400063f0`
- `0x140008920`
- `0x14000b840`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400028ae`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400028ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400029b1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400029b1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002a3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002a3b`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x14000280c  mov     [rsp-8+arg_18], rbx
0x140002811  push    rbp
0x140002812  push    rsi
0x140002813  push    rdi
0x140002814  push    r12
0x140002816  push    r13
0x140002818  push    r14
0x14000281a  push    r15
0x14000281c  lea     rbp, [rsp-13C0h]
0x140002824  mov     eax, 14C0h
0x140002829  call    _alloca_probe
0x14000282e  sub     rsp, rax
0x140002831  mov     r15, r8
0x140002834  mov     r14d, edx
0x140002837  mov     r12, rcx
0x14000283a  mov     rsi, [rbp+13F0h+arg_28]
0x140002841  xor     edx, edx; Val
0x140002843  mov     r8d, 98h; Size
0x140002849  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000284e  call    memset_0
0x140002853  nop
0x140002854  xor     r13d, r13d
0x140002857  mov     [rbp+13F0h+OutputString], r13w
0x14000285f  mov     [rbp+13F0h+var_1430], r13b
0x140002863  mov     rbx, [rbp+13F0h+arg_30]
0x14000286a  mov     ecx, [rbx]; this
0x14000286c  mov     [rsp+14F0h+var_14C8], ecx
0x140002870  mov     eax, [rbx+4]
0x140002873  mov     [rsp+14F0h+var_14C4], eax
0x140002877  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000287c  mov     edi, eax
0x14000287e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140002886  mov     ecx, r13d
0x140002889  lea     eax, [r13+8]
0x14000288d  cmp     dword ptr [rbx+8], 1
0x140002891  cmovz   ecx, eax
0x140002894  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002898  lea     ecx, [rax-7]
0x14000289b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400028a3  inc     ecx
0x1400028a5  mov     [rsp+14F0h+var_14C0], ecx
0x1400028a9  mov     [rsp+14F0h+var_14B8], r13
0x1400028ae  call    cs:__imp_GetCurrentThreadId
0x1400028b4  mov     [rsp+14F0h+var_14B0], eax
0x1400028b8  mov     [rsp+14F0h+var_1498], r15
0x1400028bd  mov     [rsp+14F0h+var_1490], r14d
0x1400028c2  mov     [rsp+14F0h+var_148C], edi
0x1400028c6  mov     [rsp+14F0h+var_14A8], r13
0x1400028cb  mov     [rsp+14F0h+var_14A0], r13
0x1400028d0  mov     [rbp+13F0h+var_1448], rsi
0x1400028d4  mov     [rbp+13F0h+var_1440], r12
0x1400028d8  mov     [rsp+14F0h+var_1488], r13
0x1400028dd  xorps   xmm0, xmm0
0x1400028e0  xor     eax, eax
0x1400028e2  movups  [rbp+13F0h+var_1468], xmm0
0x1400028e6  mov     [rbp+13F0h+var_1458], rax
0x1400028ea  xorps   xmm1, xmm1
0x1400028ed  movups  [rsp+14F0h+var_1480], xmm1
0x1400028f2  mov     [rbp+13F0h+var_1470], rax
0x1400028f6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400028fd  test    rax, rax
0x140002900  jz      short loc_14000290D
0x140002902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002907  mov     [rbp+13F0h+var_1450], rax
0x14000290b  jmp     short loc_140002911
0x14000290d  mov     [rbp+13F0h+var_1450], r13
0x140002911  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140002918  test    rax, rax
0x14000291b  jz      short loc_140002927
0x14000291d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002927  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000292e  test    rax, rax
0x140002931  jz      short loc_140002947
0x140002933  mov     r8d, 400h
0x140002939  lea     rdx, [rbp+13F0h+var_1430]
0x14000293d  lea     rcx, [rsp+14F0h+var_14D0]
0x140002942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002947  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000294e  test    rax, rax
0x140002951  jz      short loc_14000295D
0x140002953  lea     rcx, [rsp+14F0h+var_14D0]
0x140002958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000295d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002964  test    rax, rax
0x140002967  jz      short loc_14000297A
0x140002969  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000296e  jnz     short loc_14000297A
0x140002970  lea     rcx, [rsp+14F0h+var_14D0]
0x140002975  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000297a  cmp     [rsp+14F0h+var_14C8], r13d
0x14000297f  jl      short loc_140002993
0x140002981  mov     ecx, 8000FFFFh; this
0x140002986  mov     [rsp+14F0h+var_14C8], ecx
0x14000298a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000298f  mov     [rsp+14F0h+var_14C4], eax
0x140002993  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000299a  jnz     short loc_1400029BB
0x14000299c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400029a3  test    rax, rax
0x1400029a6  jz      short loc_1400029B1
0x1400029a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029ad  test    al, al
0x1400029af  jmp     short loc_1400029B9
0x1400029b1  call    cs:__imp_IsDebuggerPresent
0x1400029b7  test    eax, eax
0x1400029b9  jz      short loc_1400029C2
0x1400029bb  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400029c0  jz      short loc_1400029E8
0x1400029c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400029c9  test    rax, rax
0x1400029cc  jz      short loc_140002A41
0x1400029ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400029d5  jnz     short loc_140002A41
0x1400029d7  xor     r8d, r8d
0x1400029da  xor     edx, edx
0x1400029dc  lea     rcx, [rsp+14F0h+var_14D0]
0x1400029e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029e6  jmp     short loc_140002A41
0x1400029e8  mov     ebx, 800h
0x1400029ed  mov     rax, cs:g_pfnResultLoggingCallback
0x1400029f4  test    rax, rax
0x1400029f7  jz      short loc_140002A16
0x1400029f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002a00  jnz     short loc_140002A16
0x140002a02  mov     r8d, ebx
0x140002a05  lea     rdx, [rbp+13F0h+OutputString]
0x140002a0c  lea     rcx, [rsp+14F0h+var_14D0]
0x140002a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a16  cmp     [rbp+13F0h+OutputString], r13w
0x140002a1e  jnz     short loc_140002A34
0x140002a20  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140002a25  mov     rdx, rbx; wchar_t *
0x140002a28  lea     rcx, [rbp+13F0h+OutputString]; this
0x140002a2f  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140002a34  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140002a3b  call    cs:__imp_OutputDebugStringW
0x140002a41  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140002a46  jnz     short loc_140002A51
0x140002a48  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140002a4f  jz      short loc_140002A63
0x140002a51  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140002a58  test    rax, rax
0x140002a5b  jz      short loc_140002A63
0x140002a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a62  nop
0x140002a63  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002a68  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
