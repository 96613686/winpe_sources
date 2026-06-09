# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180003680`
- end: `0x180003940`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `704`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003940`

## callees

- `0x180002c70`
- `0x180002e40`
- `0x180002f70`
- `0x180003550`
- `0x1800035a0`
- `0x180003680`
- `0x180035c10`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18000382f`
- `KERNEL32!IsDebuggerPresent` at `0x18000382f`
- `KERNEL32!GetCurrentThreadId` at `0x18000372d`
- `KERNEL32!GetCurrentThreadId` at `0x18000372d`
- `KERNEL32!OutputDebugStringW` at `0x1800038d2`
- `KERNEL32!OutputDebugStringW` at `0x1800038d2`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int IsDebuggerPresent; // ebx
  int v13; // r13d
  int v14; // ecx
  __int64 v15; // rdx
  bool v16; // zf
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // bl
  const struct wil::FailureInfo *v21; // rdx
  int v22; // [rsp+20h] [rbp-E0h] BYREF
  int v23; // [rsp+24h] [rbp-DCh]
  int v24; // [rsp+28h] [rbp-D8h]
  int v25; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v26; // [rsp+30h] [rbp-D0h]
  _WORD *v27; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v29; // [rsp+48h] [rbp-B8h]
  __int64 v30; // [rsp+50h] [rbp-B0h]
  __int64 v31; // [rsp+58h] [rbp-A8h]
  int v32; // [rsp+60h] [rbp-A0h]
  int v33; // [rsp+64h] [rbp-9Ch]
  __int64 v34; // [rsp+68h] [rbp-98h]
  __int128 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+80h] [rbp-80h]
  __int128 v37; // [rsp+88h] [rbp-78h]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+A8h] [rbp-58h]
  __int64 v41; // [rsp+B0h] [rbp-50h]
  char v42[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v42[0] = 0;
  v24 = *a7;
  v25 = a7[1];
  v13 = wil::details::RecordException((wil::details *)(unsigned int)v24, (int)a7);
  v22 = 0;
  v14 = 0;
  if ( *(_DWORD *)(v15 + 8) == 1 )
    v14 = 8;
  v23 = v14;
  v26 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v16 = *a8 == 0, v27 = a8, v16) )
    v27 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v31 = a3;
  v32 = a2;
  v33 = v13;
  v29 = 0;
  v30 = 0;
  v40 = a6;
  v41 = a1;
  v34 = 0;
  v37 = 0;
  v38 = 0;
  v35 = 0;
  v36 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v22);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v22, v42, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v22);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v23 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v22);
  if ( v24 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  v20 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
        : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18)),
          IsDebuggerPresent))
     && (v23 & 2) == 0;
  if ( v11 || v20 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v22, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v22, v19);
    if ( v20 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v22, 0, 0);
  }
  if ( ((v23 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v23 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v22, v17);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v22, OutputString);
  wil::ThrowResultException((wil *)&v22, v17);
  wil::details::WilFailFast((wil::details *)&v22, v21);
}

```

## disassembly

```asm
0x180003680  mov     [rsp-8+arg_18], rbx
0x180003685  push    rbp
0x180003686  push    rsi
0x180003687  push    rdi
0x180003688  push    r12
0x18000368a  push    r13
0x18000368c  push    r14
0x18000368e  push    r15
0x180003690  lea     rbp, [rsp-13C0h]
0x180003698  mov     eax, 14C0h
0x18000369d  call    _alloca_probe
0x1800036a2  sub     rsp, rax
0x1800036a5  mov     r15, r8
0x1800036a8  mov     r14d, edx
0x1800036ab  mov     rsi, rcx
0x1800036ae  mov     r12, [rbp+13F0h+arg_28]
0x1800036b5  cmp     cs:g_pfnThrowPlatformException, 0
0x1800036bd  setnz   dil
0x1800036c1  xor     ebx, ebx
0x1800036c3  mov     [rbp+13F0h+OutputString], bx
0x1800036ca  mov     [rbp+13F0h+var_1430], bl
0x1800036cd  mov     rdx, [rbp+13F0h+arg_30]; int
0x1800036d4  mov     ecx, [rdx]; this
0x1800036d6  mov     [rsp+14F0h+var_14C8], ecx
0x1800036da  mov     eax, [rdx+4]
0x1800036dd  mov     [rsp+14F0h+var_14C4], eax
0x1800036e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800036e6  mov     r13d, eax
0x1800036e9  mov     dword ptr [rsp+14F0h+var_14D0], ebx
0x1800036ed  mov     ecx, ebx
0x1800036ef  mov     eax, 8
0x1800036f4  cmp     dword ptr [rdx+8], 1
0x1800036f8  cmovz   ecx, eax
0x1800036fb  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800036ff  mov     ecx, 1
0x180003704  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000370c  inc     ecx
0x18000370e  mov     [rsp+14F0h+var_14C0], ecx
0x180003712  mov     rcx, [rbp+13F0h+arg_38]
0x180003719  test    rcx, rcx
0x18000371c  jz      short loc_180003728
0x18000371e  cmp     [rcx], bx
0x180003721  mov     [rsp+14F0h+var_14B8], rcx
0x180003726  jnz     short loc_18000372D
0x180003728  mov     [rsp+14F0h+var_14B8], rbx
0x18000372d  call    cs:__imp_GetCurrentThreadId
0x180003733  mov     [rsp+14F0h+var_14B0], eax
0x180003737  mov     [rsp+14F0h+var_1498], r15
0x18000373c  mov     [rsp+14F0h+var_1490], r14d
0x180003741  mov     [rsp+14F0h+var_148C], r13d
0x180003746  mov     [rsp+14F0h+var_14A8], rbx
0x18000374b  mov     [rsp+14F0h+var_14A0], rbx
0x180003750  mov     [rbp+13F0h+var_1448], r12
0x180003754  mov     [rbp+13F0h+var_1440], rsi
0x180003758  mov     [rsp+14F0h+var_1488], rbx
0x18000375d  xorps   xmm0, xmm0
0x180003760  xor     eax, eax
0x180003762  movups  [rbp+13F0h+var_1468], xmm0
0x180003766  mov     [rbp+13F0h+var_1458], rax
0x18000376a  xorps   xmm1, xmm1
0x18000376d  movups  [rsp+14F0h+var_1480], xmm1
0x180003772  mov     [rbp+13F0h+var_1470], rax
0x180003776  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000377d  test    rax, rax
0x180003780  jz      short loc_18000378E
0x180003782  call    cs:__guard_dispatch_icall_fptr
0x180003788  mov     [rbp+13F0h+var_1450], rax
0x18000378c  jmp     short loc_180003792
0x18000378e  mov     [rbp+13F0h+var_1450], rbx
0x180003792  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003799  test    rax, rax
0x18000379c  jz      short loc_1800037A9
0x18000379e  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037a3  call    cs:__guard_dispatch_icall_fptr
0x1800037a9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800037b0  test    rax, rax
0x1800037b3  jz      short loc_1800037CA
0x1800037b5  mov     r8d, 400h
0x1800037bb  lea     rdx, [rbp+13F0h+var_1430]
0x1800037bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037c4  call    cs:__guard_dispatch_icall_fptr
0x1800037ca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037d1  test    rax, rax
0x1800037d4  jz      short loc_1800037E1
0x1800037d6  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037db  call    cs:__guard_dispatch_icall_fptr
0x1800037e1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037e8  test    rax, rax
0x1800037eb  jz      short loc_180003804
0x1800037ed  test    dil, dil
0x1800037f0  jnz     short loc_180003804
0x1800037f2  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800037f7  jnz     short loc_180003804
0x1800037f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800037fe  call    cs:__guard_dispatch_icall_fptr
0x180003804  cmp     [rsp+14F0h+var_14C8], ebx
0x180003808  jl      short loc_180003810
0x18000380a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003810  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, bl; bool wil::g_fIsDebuggerPresent
0x180003816  jnz     short loc_18000383E
0x180003818  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000381f  test    rax, rax
0x180003822  jz      short loc_18000382F
0x180003824  call    cs:__guard_dispatch_icall_fptr
0x18000382a  movzx   ebx, al
0x18000382d  jmp     short loc_18000383A
0x18000382f  call    cs:__imp_IsDebuggerPresent
0x180003835  test    eax, eax
0x180003837  setnz   bl
0x18000383a  test    ebx, ebx
0x18000383c  jz      short loc_180003849
0x18000383e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180003843  jnz     short loc_180003849
0x180003845  mov     bl, 1
0x180003847  jmp     short loc_18000384B
0x180003849  xor     bl, bl
0x18000384b  test    dil, dil
0x18000384e  jnz     short loc_18000387A
0x180003850  test    bl, bl
0x180003852  jnz     short loc_18000387A
0x180003854  mov     rax, cs:g_pfnResultLoggingCallback
0x18000385b  test    rax, rax
0x18000385e  jz      short loc_1800038D8
0x180003860  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, bl; bool wil::details::g_resultMessageCallbackSet
0x180003866  jnz     short loc_1800038D8
0x180003868  xor     r8d, r8d
0x18000386b  xor     edx, edx
0x18000386d  lea     rcx, [rsp+14F0h+var_14D0]
0x180003872  call    cs:__guard_dispatch_icall_fptr
0x180003878  jmp     short loc_1800038D8
0x18000387a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003881  test    rax, rax
0x180003884  jz      short loc_1800038A7
0x180003886  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000388d  jnz     short loc_1800038A7
0x18000388f  mov     r8d, 800h
0x180003895  lea     rdx, [rbp+13F0h+OutputString]
0x18000389c  lea     rcx, [rsp+14F0h+var_14D0]
0x1800038a1  call    cs:__guard_dispatch_icall_fptr
0x1800038a7  cmp     [rbp+13F0h+OutputString], 0
0x1800038af  jnz     short loc_1800038C7
0x1800038b1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800038b6  mov     edx, 800h; wchar_t *
0x1800038bb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800038c2  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800038c7  test    bl, bl
0x1800038c9  jz      short loc_1800038D8
0x1800038cb  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800038d2  call    cs:__imp_OutputDebugStringW
0x1800038d8  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800038dd  jnz     short loc_1800038E8
0x1800038df  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1800038e6  jz      short loc_1800038FB
0x1800038e8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800038ef  test    rax, rax
0x1800038f2  jz      short loc_1800038FB
0x1800038f4  call    cs:__guard_dispatch_icall_fptr
0x1800038fa  nop
0x1800038fb  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180003900  jz      short loc_18000390D
0x180003902  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003907  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000390d  test    dil, dil
0x180003910  jz      short loc_18000392B
0x180003912  lea     rdx, [rbp+13F0h+OutputString]
0x180003919  lea     rcx, [rsp+14F0h+var_14D0]
0x18000391e  mov     rax, cs:g_pfnThrowPlatformException
0x180003925  call    cs:__guard_dispatch_icall_fptr
0x18000392b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180003930  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180003935  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000393a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
