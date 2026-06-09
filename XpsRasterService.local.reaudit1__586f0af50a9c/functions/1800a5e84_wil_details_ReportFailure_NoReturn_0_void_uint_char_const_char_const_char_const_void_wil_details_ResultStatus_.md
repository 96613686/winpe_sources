# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x1800a5e84`
- end: `0x1800a6137`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `691`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800a5c8c`

## callees

- `0x180003cc4`
- `0x1800a0280`
- `0x1800a3be4`
- `0x1800a4988`
- `0x1800a4ff0`
- `0x1800a50c8`
- `0x1800a52d0`
- `0x1800a5e84`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5f2d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a5f2d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a60cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a60cb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a602f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a602f`

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
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
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
  v28 = "onecoreuap\\printscan\\dox\\render\\xpsras\\lib\\passthroughrasterverfierimpl.cpp";
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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v19, v15);
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
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x1800a5e84  mov     [rsp-8+arg_10], rbx
0x1800a5e89  mov     [rsp-8+arg_18], rsi
0x1800a5e8e  push    rbp
0x1800a5e8f  push    rdi
0x1800a5e90  push    r12
0x1800a5e92  push    r14
0x1800a5e94  push    r15
0x1800a5e96  lea     rbp, [rsp-13C0h]
0x1800a5e9e  mov     eax, 14C0h
0x1800a5ea3  call    _alloca_probe
0x1800a5ea8  sub     rsp, rax
0x1800a5eab  mov     esi, edx
0x1800a5ead  mov     r14, rcx
0x1800a5eb0  mov     rdi, [rbp+13E0h+arg_28]
0x1800a5eb7  xor     r12d, r12d
0x1800a5eba  cmp     cs:g_pfnThrowPlatformException, r12
0x1800a5ec1  setnz   r15b
0x1800a5ec5  xor     edx, edx; Val
0x1800a5ec7  mov     r8d, 98h; Size
0x1800a5ecd  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800a5ed2  call    memset_0
0x1800a5ed7  nop
0x1800a5ed8  mov     [rbp+13E0h+OutputString], r12w
0x1800a5ee0  mov     [rbp+13E0h+var_1420], r12b
0x1800a5ee4  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x1800a5eeb  mov     ecx, [rdx]; this
0x1800a5eed  mov     [rsp+14E0h+var_14B8], ecx
0x1800a5ef1  mov     eax, [rdx+4]
0x1800a5ef4  mov     [rsp+14E0h+var_14B4], eax
0x1800a5ef8  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800a5efd  mov     ebx, eax
0x1800a5eff  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x1800a5f04  mov     ecx, r12d
0x1800a5f07  lea     eax, [r12+8]
0x1800a5f0c  cmp     dword ptr [rdx+8], 1
0x1800a5f10  cmovz   ecx, eax
0x1800a5f13  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800a5f17  lea     ecx, [rax-7]
0x1800a5f1a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a5f22  inc     ecx
0x1800a5f24  mov     [rsp+14E0h+var_14B0], ecx
0x1800a5f28  mov     [rsp+14E0h+var_14A8], r12
0x1800a5f2d  call    cs:__imp_GetCurrentThreadId
0x1800a5f33  mov     [rsp+14E0h+var_14A0], eax
0x1800a5f37  lea     rax, aOnecoreuapPrin; "onecoreuap\\printscan\\dox\\render\\xps"...
0x1800a5f3e  mov     [rsp+14E0h+var_1488], rax
0x1800a5f43  mov     [rsp+14E0h+var_1480], esi
0x1800a5f47  mov     [rsp+14E0h+var_147C], ebx
0x1800a5f4b  mov     [rsp+14E0h+var_1498], r12
0x1800a5f50  mov     [rsp+14E0h+var_1490], r12
0x1800a5f55  mov     [rbp+13E0h+var_1438], rdi
0x1800a5f59  mov     [rbp+13E0h+var_1430], r14
0x1800a5f5d  mov     [rsp+14E0h+var_1478], r12
0x1800a5f62  xorps   xmm0, xmm0
0x1800a5f65  xor     eax, eax
0x1800a5f67  movups  [rbp+13E0h+var_1458], xmm0
0x1800a5f6b  mov     [rbp+13E0h+var_1448], rax
0x1800a5f6f  xorps   xmm1, xmm1
0x1800a5f72  movups  [rsp+14E0h+var_1470], xmm1
0x1800a5f77  mov     [rbp+13E0h+var_1460], rax
0x1800a5f7b  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a5f82  test    rax, rax
0x1800a5f85  jz      short loc_1800A5F92
0x1800a5f87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5f8c  mov     [rbp+13E0h+var_1440], rax
0x1800a5f90  jmp     short loc_1800A5F96
0x1800a5f92  mov     [rbp+13E0h+var_1440], r12
0x1800a5f96  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a5f9d  test    rax, rax
0x1800a5fa0  jz      short loc_1800A5FAC
0x1800a5fa2  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a5fa7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5fac  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a5fb3  test    rax, rax
0x1800a5fb6  jz      short loc_1800A5FCC
0x1800a5fb8  mov     r8d, 400h
0x1800a5fbe  lea     rdx, [rbp+13E0h+var_1420]
0x1800a5fc2  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a5fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5fcc  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a5fd3  test    rax, rax
0x1800a5fd6  jz      short loc_1800A5FE2
0x1800a5fd8  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a5fdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a5fe2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a5fe9  test    rax, rax
0x1800a5fec  jz      short loc_1800A6004
0x1800a5fee  test    r15b, r15b
0x1800a5ff1  jnz     short loc_1800A6004
0x1800a5ff3  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800a5ff8  jnz     short loc_1800A6004
0x1800a5ffa  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a5fff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6004  cmp     [rsp+14E0h+var_14B8], r12d
0x1800a6009  jl      short loc_1800A6011
0x1800a600b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800a6011  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800a6018  jnz     short loc_1800A6039
0x1800a601a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a6021  test    rax, rax
0x1800a6024  jz      short loc_1800A602F
0x1800a6026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a602b  test    al, al
0x1800a602d  jmp     short loc_1800A6037
0x1800a602f  call    cs:__imp_IsDebuggerPresent
0x1800a6035  test    eax, eax
0x1800a6037  jz      short loc_1800A6042
0x1800a6039  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800a603e  mov     bl, 1
0x1800a6040  jz      short loc_1800A6045
0x1800a6042  mov     bl, r12b
0x1800a6045  test    r15b, r15b
0x1800a6048  jnz     short loc_1800A6074
0x1800a604a  test    bl, bl
0x1800a604c  jnz     short loc_1800A6074
0x1800a604e  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a6055  test    rax, rax
0x1800a6058  jz      short loc_1800A60D1
0x1800a605a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800a6061  jnz     short loc_1800A60D1
0x1800a6063  xor     r8d, r8d
0x1800a6066  xor     edx, edx
0x1800a6068  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a606d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6072  jmp     short loc_1800A60D1
0x1800a6074  mov     edi, 800h
0x1800a6079  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a6080  test    rax, rax
0x1800a6083  jz      short loc_1800A60A2
0x1800a6085  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800a608c  jnz     short loc_1800A60A2
0x1800a608e  mov     r8d, edi
0x1800a6091  lea     rdx, [rbp+13E0h+OutputString]
0x1800a6098  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a609d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a60a2  cmp     [rbp+13E0h+OutputString], r12w
0x1800a60aa  jnz     short loc_1800A60C0
0x1800a60ac  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800a60b1  mov     rdx, rdi; wchar_t *
0x1800a60b4  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800a60bb  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800a60c0  test    bl, bl
0x1800a60c2  jz      short loc_1800A60D1
0x1800a60c4  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800a60cb  call    cs:__imp_OutputDebugStringW
0x1800a60d1  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800a60d6  jnz     short loc_1800A60E1
0x1800a60d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800a60df  jz      short loc_1800A60F3
0x1800a60e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a60e8  test    rax, rax
0x1800a60eb  jz      short loc_1800A60F3
0x1800a60ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a60f2  nop
0x1800a60f3  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x1800a60f8  jz      short loc_1800A6105
0x1800a60fa  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800a60ff  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800a6105  test    r15b, r15b
0x1800a6108  jz      short loc_1800A6122
0x1800a610a  lea     rdx, [rbp+13E0h+OutputString]
0x1800a6111  lea     rcx, [rsp+14E0h+var_14C0]
0x1800a6116  mov     rax, cs:g_pfnThrowPlatformException
0x1800a611d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a6122  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800a6127  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800a612c  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800a6131  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
