# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006c68`
- end: `0x180006eca`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006b70`

## callees

- `0x180002158`
- `0x180005088`
- `0x180005794`
- `0x180005fd0`
- `0x18000687c`
- `0x180006c68`
- `0x180011440`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d0a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006d0a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e97`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006e0d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006e0d`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
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
0x180006c68  mov     [rsp-8+arg_18], rbx
0x180006c6d  push    rbp
0x180006c6e  push    rsi
0x180006c6f  push    rdi
0x180006c70  push    r12
0x180006c72  push    r13
0x180006c74  push    r14
0x180006c76  push    r15
0x180006c78  lea     rbp, [rsp-13C0h]
0x180006c80  mov     eax, 14C0h
0x180006c85  call    _alloca_probe
0x180006c8a  sub     rsp, rax
0x180006c8d  mov     r15, r8
0x180006c90  mov     r14d, edx
0x180006c93  mov     r12, rcx
0x180006c96  mov     rsi, [rbp+13F0h+arg_28]
0x180006c9d  xor     edx, edx; Val
0x180006c9f  mov     r8d, 98h; Size
0x180006ca5  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006caa  call    memset_0
0x180006caf  nop
0x180006cb0  xor     r13d, r13d
0x180006cb3  mov     [rbp+13F0h+OutputString], r13w
0x180006cbb  mov     [rbp+13F0h+var_1430], r13b
0x180006cbf  mov     rbx, [rbp+13F0h+arg_30]
0x180006cc6  mov     ecx, [rbx]; this
0x180006cc8  mov     [rsp+14F0h+var_14C8], ecx
0x180006ccc  mov     eax, [rbx+4]
0x180006ccf  mov     [rsp+14F0h+var_14C4], eax
0x180006cd3  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006cd8  mov     edi, eax
0x180006cda  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180006ce2  mov     ecx, r13d
0x180006ce5  lea     eax, [r13+8]
0x180006ce9  cmp     dword ptr [rbx+8], 1
0x180006ced  cmovz   ecx, eax
0x180006cf0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180006cf4  lea     ecx, [rax-7]
0x180006cf7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006cff  inc     ecx
0x180006d01  mov     [rsp+14F0h+var_14C0], ecx
0x180006d05  mov     [rsp+14F0h+var_14B8], r13
0x180006d0a  call    cs:__imp_GetCurrentThreadId
0x180006d10  mov     [rsp+14F0h+var_14B0], eax
0x180006d14  mov     [rsp+14F0h+var_1498], r15
0x180006d19  mov     [rsp+14F0h+var_1490], r14d
0x180006d1e  mov     [rsp+14F0h+var_148C], edi
0x180006d22  mov     [rsp+14F0h+var_14A8], r13
0x180006d27  mov     [rsp+14F0h+var_14A0], r13
0x180006d2c  mov     [rbp+13F0h+var_1448], rsi
0x180006d30  mov     [rbp+13F0h+var_1440], r12
0x180006d34  mov     [rsp+14F0h+var_1488], r13
0x180006d39  xorps   xmm0, xmm0
0x180006d3c  xor     eax, eax
0x180006d3e  movups  [rbp+13F0h+var_1468], xmm0
0x180006d42  mov     [rbp+13F0h+var_1458], rax
0x180006d46  xorps   xmm1, xmm1
0x180006d49  movups  [rsp+14F0h+var_1480], xmm1
0x180006d4e  mov     [rbp+13F0h+var_1470], rax
0x180006d52  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006d59  test    rax, rax
0x180006d5c  jz      short loc_180006D69
0x180006d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d63  mov     [rbp+13F0h+var_1450], rax
0x180006d67  jmp     short loc_180006D6D
0x180006d69  mov     [rbp+13F0h+var_1450], r13
0x180006d6d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006d74  test    rax, rax
0x180006d77  jz      short loc_180006D83
0x180006d79  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d83  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006d8a  test    rax, rax
0x180006d8d  jz      short loc_180006DA3
0x180006d8f  mov     r8d, 400h
0x180006d95  lea     rdx, [rbp+13F0h+var_1430]
0x180006d99  lea     rcx, [rsp+14F0h+var_14D0]
0x180006d9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006da3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006daa  test    rax, rax
0x180006dad  jz      short loc_180006DB9
0x180006daf  lea     rcx, [rsp+14F0h+var_14D0]
0x180006db4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006db9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006dc0  test    rax, rax
0x180006dc3  jz      short loc_180006DD6
0x180006dc5  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006dca  jnz     short loc_180006DD6
0x180006dcc  lea     rcx, [rsp+14F0h+var_14D0]
0x180006dd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd6  cmp     [rsp+14F0h+var_14C8], r13d
0x180006ddb  jl      short loc_180006DEF
0x180006ddd  mov     ecx, 8000FFFFh; this
0x180006de2  mov     [rsp+14F0h+var_14C8], ecx
0x180006de6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006deb  mov     [rsp+14F0h+var_14C4], eax
0x180006def  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006df6  jnz     short loc_180006E17
0x180006df8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006dff  test    rax, rax
0x180006e02  jz      short loc_180006E0D
0x180006e04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e09  test    al, al
0x180006e0b  jmp     short loc_180006E15
0x180006e0d  call    cs:__imp_IsDebuggerPresent
0x180006e13  test    eax, eax
0x180006e15  jz      short loc_180006E1E
0x180006e17  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006e1c  jz      short loc_180006E44
0x180006e1e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006e25  test    rax, rax
0x180006e28  jz      short loc_180006E9D
0x180006e2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006e31  jnz     short loc_180006E9D
0x180006e33  xor     r8d, r8d
0x180006e36  xor     edx, edx
0x180006e38  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e42  jmp     short loc_180006E9D
0x180006e44  mov     ebx, 800h
0x180006e49  mov     rax, cs:g_pfnResultLoggingCallback
0x180006e50  test    rax, rax
0x180006e53  jz      short loc_180006E72
0x180006e55  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006e5c  jnz     short loc_180006E72
0x180006e5e  mov     r8d, ebx
0x180006e61  lea     rdx, [rbp+13F0h+OutputString]
0x180006e68  lea     rcx, [rsp+14F0h+var_14D0]
0x180006e6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e72  cmp     [rbp+13F0h+OutputString], r13w
0x180006e7a  jnz     short loc_180006E90
0x180006e7c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006e81  mov     rdx, rbx; unsigned __int16 *
0x180006e84  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006e8b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006e90  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006e97  call    cs:__imp_OutputDebugStringW
0x180006e9d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006ea2  jnz     short loc_180006EAD
0x180006ea4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006eab  jz      short loc_180006EBF
0x180006ead  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006eb4  test    rax, rax
0x180006eb7  jz      short loc_180006EBF
0x180006eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ebe  nop
0x180006ebf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006ec4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
