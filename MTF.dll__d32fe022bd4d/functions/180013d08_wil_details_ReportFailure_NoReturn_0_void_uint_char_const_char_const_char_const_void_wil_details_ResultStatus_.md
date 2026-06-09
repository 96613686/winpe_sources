# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180013d08`
- end: `0x180013fb4`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180013c80`

## callees

- `0x1800049a4`
- `0x180005a88`
- `0x180006930`
- `0x180006c80`
- `0x180006f00`
- `0x180013d08`
- `0x18002bc62`
- `0x18002bd60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013db1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013db1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013eac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180013eac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013f48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013f48`

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
      g_pfnResultLoggingCallback(&v20, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0, v16);
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
0x180013d08  mov     [rsp-8+arg_18], rbx
0x180013d0d  push    rbp
0x180013d0e  push    rsi
0x180013d0f  push    rdi
0x180013d10  push    r12
0x180013d12  push    r13
0x180013d14  push    r14
0x180013d16  push    r15
0x180013d18  lea     rbp, [rsp-13C0h]
0x180013d20  mov     eax, 14C0h
0x180013d25  call    _alloca_probe
0x180013d2a  sub     rsp, rax
0x180013d2d  mov     r14, r8
0x180013d30  mov     esi, edx
0x180013d32  mov     r15, rcx
0x180013d35  mov     rdi, [rbp+13F0h+arg_28]
0x180013d3c  xor     r13d, r13d
0x180013d3f  cmp     cs:g_pfnThrowPlatformException, r13
0x180013d46  setnz   r12b
0x180013d4a  xor     edx, edx; Val
0x180013d4c  mov     r8d, 98h; Size
0x180013d52  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180013d57  call    memset_0
0x180013d5c  nop
0x180013d5d  mov     [rbp+13F0h+OutputString], r13w
0x180013d65  mov     [rbp+13F0h+var_1430], r13b
0x180013d69  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180013d70  mov     ecx, [rdx]; this
0x180013d72  mov     [rsp+14F0h+var_14C8], ecx
0x180013d76  mov     eax, [rdx+4]
0x180013d79  mov     [rsp+14F0h+var_14C4], eax
0x180013d7d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013d82  mov     ebx, eax
0x180013d84  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180013d89  mov     ecx, r13d
0x180013d8c  lea     eax, [r13+8]
0x180013d90  cmp     dword ptr [rdx+8], 1
0x180013d94  cmovz   ecx, eax
0x180013d97  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180013d9b  lea     ecx, [rax-7]
0x180013d9e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013da6  inc     ecx
0x180013da8  mov     [rsp+14F0h+var_14C0], ecx
0x180013dac  mov     [rsp+14F0h+var_14B8], r13
0x180013db1  call    cs:__imp_GetCurrentThreadId
0x180013db7  mov     [rsp+14F0h+var_14B0], eax
0x180013dbb  mov     [rsp+14F0h+var_1498], r14
0x180013dc0  mov     [rsp+14F0h+var_1490], esi
0x180013dc4  mov     [rsp+14F0h+var_148C], ebx
0x180013dc8  mov     [rsp+14F0h+var_14A8], r13
0x180013dcd  mov     [rsp+14F0h+var_14A0], r13
0x180013dd2  mov     [rbp+13F0h+var_1448], rdi
0x180013dd6  mov     [rbp+13F0h+var_1440], r15
0x180013dda  mov     [rsp+14F0h+var_1488], r13
0x180013ddf  xorps   xmm0, xmm0
0x180013de2  xor     eax, eax
0x180013de4  movups  [rbp+13F0h+var_1468], xmm0
0x180013de8  mov     [rbp+13F0h+var_1458], rax
0x180013dec  xorps   xmm1, xmm1
0x180013def  movups  [rsp+14F0h+var_1480], xmm1
0x180013df4  mov     [rbp+13F0h+var_1470], rax
0x180013df8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013dff  test    rax, rax
0x180013e02  jz      short loc_180013E0F
0x180013e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e09  mov     [rbp+13F0h+var_1450], rax
0x180013e0d  jmp     short loc_180013E13
0x180013e0f  mov     [rbp+13F0h+var_1450], r13
0x180013e13  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013e1a  test    rax, rax
0x180013e1d  jz      short loc_180013E29
0x180013e1f  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e29  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013e30  test    rax, rax
0x180013e33  jz      short loc_180013E49
0x180013e35  mov     r8d, 400h
0x180013e3b  lea     rdx, [rbp+13F0h+var_1430]
0x180013e3f  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e49  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013e50  test    rax, rax
0x180013e53  jz      short loc_180013E5F
0x180013e55  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e5f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013e66  test    rax, rax
0x180013e69  jz      short loc_180013E81
0x180013e6b  test    r12b, r12b
0x180013e6e  jnz     short loc_180013E81
0x180013e70  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013e75  jnz     short loc_180013E81
0x180013e77  lea     rcx, [rsp+14F0h+var_14D0]
0x180013e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013e81  cmp     [rsp+14F0h+var_14C8], r13d
0x180013e86  jl      short loc_180013E8E
0x180013e88  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180013e8e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180013e95  jnz     short loc_180013EB6
0x180013e97  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013e9e  test    rax, rax
0x180013ea1  jz      short loc_180013EAC
0x180013ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ea8  test    al, al
0x180013eaa  jmp     short loc_180013EB4
0x180013eac  call    cs:__imp_IsDebuggerPresent
0x180013eb2  test    eax, eax
0x180013eb4  jz      short loc_180013EBF
0x180013eb6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013ebb  mov     bl, 1
0x180013ebd  jz      short loc_180013EC2
0x180013ebf  mov     bl, r13b
0x180013ec2  test    r12b, r12b
0x180013ec5  jnz     short loc_180013EF1
0x180013ec7  test    bl, bl
0x180013ec9  jnz     short loc_180013EF1
0x180013ecb  mov     rax, cs:g_pfnResultLoggingCallback
0x180013ed2  test    rax, rax
0x180013ed5  jz      short loc_180013F4E
0x180013ed7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180013ede  jnz     short loc_180013F4E
0x180013ee0  xor     r8d, r8d
0x180013ee3  xor     edx, edx
0x180013ee5  lea     rcx, [rsp+14F0h+var_14D0]
0x180013eea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013eef  jmp     short loc_180013F4E
0x180013ef1  mov     edi, 800h
0x180013ef6  mov     rax, cs:g_pfnResultLoggingCallback
0x180013efd  test    rax, rax
0x180013f00  jz      short loc_180013F1F
0x180013f02  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180013f09  jnz     short loc_180013F1F
0x180013f0b  mov     r8d, edi
0x180013f0e  lea     rdx, [rbp+13F0h+OutputString]
0x180013f15  lea     rcx, [rsp+14F0h+var_14D0]
0x180013f1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f1f  cmp     [rbp+13F0h+OutputString], r13w
0x180013f27  jnz     short loc_180013F3D
0x180013f29  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180013f2e  mov     rdx, rdi; unsigned __int16 *
0x180013f31  lea     rcx, [rbp+13F0h+OutputString]; this
0x180013f38  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013f3d  test    bl, bl
0x180013f3f  jz      short loc_180013F4E
0x180013f41  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180013f48  call    cs:__imp_OutputDebugStringW
0x180013f4e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180013f53  jnz     short loc_180013F5E
0x180013f55  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180013f5c  jz      short loc_180013F70
0x180013f5e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013f65  test    rax, rax
0x180013f68  jz      short loc_180013F70
0x180013f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f6f  nop
0x180013f70  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180013f75  jz      short loc_180013F82
0x180013f77  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180013f7c  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180013f82  test    r12b, r12b
0x180013f85  jz      short loc_180013F9F
0x180013f87  lea     rdx, [rbp+13F0h+OutputString]
0x180013f8e  lea     rcx, [rsp+14F0h+var_14D0]
0x180013f93  mov     rax, cs:g_pfnThrowPlatformException
0x180013f9a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013f9f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180013fa4  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180013fa9  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180013fae  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
