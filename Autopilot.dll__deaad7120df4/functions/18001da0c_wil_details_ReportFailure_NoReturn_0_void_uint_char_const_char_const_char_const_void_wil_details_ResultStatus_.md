# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001da0c`
- end: `0x18001dcca`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001d984`

## callees

- `0x1800053c4`
- `0x18000d284`
- `0x18000f190`
- `0x18001173c`
- `0x180011efc`
- `0x180012210`
- `0x18001da0c`
- `0x1800294b0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dab5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001dab5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001dbb6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001dbb6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001dc58`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001dc58`

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
0x18001da0c  mov     [rsp-8+arg_18], rbx
0x18001da11  push    rbp
0x18001da12  push    rsi
0x18001da13  push    rdi
0x18001da14  push    r12
0x18001da16  push    r13
0x18001da18  push    r14
0x18001da1a  push    r15
0x18001da1c  lea     rbp, [rsp-13C0h]
0x18001da24  mov     eax, 14C0h
0x18001da29  call    _alloca_probe
0x18001da2e  sub     rsp, rax
0x18001da31  mov     r14, r8
0x18001da34  mov     esi, edx
0x18001da36  mov     r15, rcx
0x18001da39  mov     rdi, [rbp+13F0h+arg_28]
0x18001da40  xor     r13d, r13d
0x18001da43  cmp     cs:g_pfnThrowPlatformException, r13
0x18001da4a  setnz   r12b
0x18001da4e  xor     edx, edx; Val
0x18001da50  mov     r8d, 98h; Size
0x18001da56  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001da5b  call    memset_0
0x18001da60  nop
0x18001da61  mov     [rbp+13F0h+OutputString], r13w
0x18001da69  mov     [rbp+13F0h+var_1430], r13b
0x18001da6d  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18001da74  mov     ecx, [rdx]; this
0x18001da76  mov     [rsp+14F0h+var_14C8], ecx
0x18001da7a  mov     eax, [rdx+4]
0x18001da7d  mov     [rsp+14F0h+var_14C4], eax
0x18001da81  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001da86  mov     ebx, eax
0x18001da88  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18001da8d  mov     ecx, r13d
0x18001da90  lea     eax, [r13+8]
0x18001da94  cmp     dword ptr [rdx+8], 1
0x18001da98  cmovz   ecx, eax
0x18001da9b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001da9f  lea     ecx, [rax-7]
0x18001daa2  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001daaa  inc     ecx
0x18001daac  mov     [rsp+14F0h+var_14C0], ecx
0x18001dab0  mov     [rsp+14F0h+var_14B8], r13
0x18001dab5  call    cs:__imp_GetCurrentThreadId
0x18001dabc  nop     dword ptr [rax+rax+00h]
0x18001dac1  mov     [rsp+14F0h+var_14B0], eax
0x18001dac5  mov     [rsp+14F0h+var_1498], r14
0x18001daca  mov     [rsp+14F0h+var_1490], esi
0x18001dace  mov     [rsp+14F0h+var_148C], ebx
0x18001dad2  mov     [rsp+14F0h+var_14A8], r13
0x18001dad7  mov     [rsp+14F0h+var_14A0], r13
0x18001dadc  mov     [rbp+13F0h+var_1448], rdi
0x18001dae0  mov     [rbp+13F0h+var_1440], r15
0x18001dae4  mov     [rsp+14F0h+var_1488], r13
0x18001dae9  xorps   xmm0, xmm0
0x18001daec  xor     eax, eax
0x18001daee  movups  [rbp+13F0h+var_1468], xmm0
0x18001daf2  mov     [rbp+13F0h+var_1458], rax
0x18001daf6  xorps   xmm1, xmm1
0x18001daf9  movups  [rsp+14F0h+var_1480], xmm1
0x18001dafe  mov     [rbp+13F0h+var_1470], rax
0x18001db02  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001db09  test    rax, rax
0x18001db0c  jz      short loc_18001DB19
0x18001db0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db13  mov     [rbp+13F0h+var_1450], rax
0x18001db17  jmp     short loc_18001DB1D
0x18001db19  mov     [rbp+13F0h+var_1450], r13
0x18001db1d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001db24  test    rax, rax
0x18001db27  jz      short loc_18001DB33
0x18001db29  lea     rcx, [rsp+14F0h+var_14D0]
0x18001db2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db33  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001db3a  test    rax, rax
0x18001db3d  jz      short loc_18001DB53
0x18001db3f  mov     r8d, 400h
0x18001db45  lea     rdx, [rbp+13F0h+var_1430]
0x18001db49  lea     rcx, [rsp+14F0h+var_14D0]
0x18001db4e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db53  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001db5a  test    rax, rax
0x18001db5d  jz      short loc_18001DB69
0x18001db5f  lea     rcx, [rsp+14F0h+var_14D0]
0x18001db64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db69  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001db70  test    rax, rax
0x18001db73  jz      short loc_18001DB8B
0x18001db75  test    r12b, r12b
0x18001db78  jnz     short loc_18001DB8B
0x18001db7a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001db7f  jnz     short loc_18001DB8B
0x18001db81  lea     rcx, [rsp+14F0h+var_14D0]
0x18001db86  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001db8b  cmp     [rsp+14F0h+var_14C8], r13d
0x18001db90  jl      short loc_18001DB98
0x18001db92  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18001db98  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001db9f  jnz     short loc_18001DBC6
0x18001dba1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001dba8  test    rax, rax
0x18001dbab  jz      short loc_18001DBB6
0x18001dbad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbb2  test    al, al
0x18001dbb4  jmp     short loc_18001DBC4
0x18001dbb6  call    cs:__imp_IsDebuggerPresent
0x18001dbbd  nop     dword ptr [rax+rax+00h]
0x18001dbc2  test    eax, eax
0x18001dbc4  jz      short loc_18001DBCF
0x18001dbc6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001dbcb  mov     bl, 1
0x18001dbcd  jz      short loc_18001DBD2
0x18001dbcf  mov     bl, r13b
0x18001dbd2  test    r12b, r12b
0x18001dbd5  jnz     short loc_18001DC01
0x18001dbd7  test    bl, bl
0x18001dbd9  jnz     short loc_18001DC01
0x18001dbdb  mov     rax, cs:g_pfnResultLoggingCallback
0x18001dbe2  test    rax, rax
0x18001dbe5  jz      short loc_18001DC64
0x18001dbe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001dbee  jnz     short loc_18001DC64
0x18001dbf0  xor     r8d, r8d
0x18001dbf3  xor     edx, edx
0x18001dbf5  lea     rcx, [rsp+14F0h+var_14D0]
0x18001dbfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dbff  jmp     short loc_18001DC64
0x18001dc01  mov     edi, 800h
0x18001dc06  mov     rax, cs:g_pfnResultLoggingCallback
0x18001dc0d  test    rax, rax
0x18001dc10  jz      short loc_18001DC2F
0x18001dc12  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001dc19  jnz     short loc_18001DC2F
0x18001dc1b  mov     r8d, edi
0x18001dc1e  lea     rdx, [rbp+13F0h+OutputString]
0x18001dc25  lea     rcx, [rsp+14F0h+var_14D0]
0x18001dc2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc2f  cmp     [rbp+13F0h+OutputString], r13w
0x18001dc37  jnz     short loc_18001DC4D
0x18001dc39  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001dc3e  mov     rdx, rdi; unsigned __int16 *
0x18001dc41  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001dc48  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001dc4d  test    bl, bl
0x18001dc4f  jz      short loc_18001DC64
0x18001dc51  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001dc58  call    cs:__imp_OutputDebugStringW
0x18001dc5f  nop     dword ptr [rax+rax+00h]
0x18001dc64  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001dc69  jnz     short loc_18001DC74
0x18001dc6b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001dc72  jz      short loc_18001DC86
0x18001dc74  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001dc7b  test    rax, rax
0x18001dc7e  jz      short loc_18001DC86
0x18001dc80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dc85  nop
0x18001dc86  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18001dc8b  jz      short loc_18001DC98
0x18001dc8d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001dc92  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18001dc98  test    r12b, r12b
0x18001dc9b  jz      short loc_18001DCB5
0x18001dc9d  lea     rdx, [rbp+13F0h+OutputString]
0x18001dca4  lea     rcx, [rsp+14F0h+var_14D0]
0x18001dca9  mov     rax, cs:g_pfnThrowPlatformException
0x18001dcb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001dcb5  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001dcba  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001dcbf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001dcc4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
