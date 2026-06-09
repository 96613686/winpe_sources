# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140006c28`
- end: `0x140006e8a`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140006a78`

## callees

- `0x1400022ec`
- `0x140005d20`
- `0x1400061c4`
- `0x140006700`
- `0x140006810`
- `0x140006c28`
- `0x14000fa20`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006cca`
- `KERNEL32!GetCurrentThreadId` at `0x140006cca`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006e57`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006e57`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006dcd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006dcd`

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
0x140006c28  mov     [rsp-8+arg_18], rbx
0x140006c2d  push    rbp
0x140006c2e  push    rsi
0x140006c2f  push    rdi
0x140006c30  push    r12
0x140006c32  push    r13
0x140006c34  push    r14
0x140006c36  push    r15
0x140006c38  lea     rbp, [rsp-13C0h]
0x140006c40  mov     eax, 14C0h
0x140006c45  call    _alloca_probe
0x140006c4a  sub     rsp, rax
0x140006c4d  mov     r15, r8
0x140006c50  mov     r14d, edx
0x140006c53  mov     r12, rcx
0x140006c56  mov     rsi, [rbp+13F0h+arg_28]
0x140006c5d  xor     edx, edx; Val
0x140006c5f  mov     r8d, 98h; Size
0x140006c65  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140006c6a  call    memset_0
0x140006c6f  nop
0x140006c70  xor     r13d, r13d
0x140006c73  mov     [rbp+13F0h+OutputString], r13w
0x140006c7b  mov     [rbp+13F0h+var_1430], r13b
0x140006c7f  mov     rbx, [rbp+13F0h+arg_30]
0x140006c86  mov     ecx, [rbx]; this
0x140006c88  mov     [rsp+14F0h+var_14C8], ecx
0x140006c8c  mov     eax, [rbx+4]
0x140006c8f  mov     [rsp+14F0h+var_14C4], eax
0x140006c93  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006c98  mov     edi, eax
0x140006c9a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140006ca2  mov     ecx, r13d
0x140006ca5  lea     eax, [r13+8]
0x140006ca9  cmp     dword ptr [rbx+8], 1
0x140006cad  cmovz   ecx, eax
0x140006cb0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140006cb4  lea     ecx, [rax-7]
0x140006cb7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006cbf  inc     ecx
0x140006cc1  mov     [rsp+14F0h+var_14C0], ecx
0x140006cc5  mov     [rsp+14F0h+var_14B8], r13
0x140006cca  call    cs:__imp_GetCurrentThreadId
0x140006cd0  mov     [rsp+14F0h+var_14B0], eax
0x140006cd4  mov     [rsp+14F0h+var_1498], r15
0x140006cd9  mov     [rsp+14F0h+var_1490], r14d
0x140006cde  mov     [rsp+14F0h+var_148C], edi
0x140006ce2  mov     [rsp+14F0h+var_14A8], r13
0x140006ce7  mov     [rsp+14F0h+var_14A0], r13
0x140006cec  mov     [rbp+13F0h+var_1448], rsi
0x140006cf0  mov     [rbp+13F0h+var_1440], r12
0x140006cf4  mov     [rsp+14F0h+var_1488], r13
0x140006cf9  xorps   xmm0, xmm0
0x140006cfc  xor     eax, eax
0x140006cfe  movups  [rbp+13F0h+var_1468], xmm0
0x140006d02  mov     [rbp+13F0h+var_1458], rax
0x140006d06  xorps   xmm1, xmm1
0x140006d09  movups  [rsp+14F0h+var_1480], xmm1
0x140006d0e  mov     [rbp+13F0h+var_1470], rax
0x140006d12  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006d19  test    rax, rax
0x140006d1c  jz      short loc_140006D29
0x140006d1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d23  mov     [rbp+13F0h+var_1450], rax
0x140006d27  jmp     short loc_140006D2D
0x140006d29  mov     [rbp+13F0h+var_1450], r13
0x140006d2d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006d34  test    rax, rax
0x140006d37  jz      short loc_140006D43
0x140006d39  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d43  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006d4a  test    rax, rax
0x140006d4d  jz      short loc_140006D63
0x140006d4f  mov     r8d, 400h
0x140006d55  lea     rdx, [rbp+13F0h+var_1430]
0x140006d59  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d63  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006d6a  test    rax, rax
0x140006d6d  jz      short loc_140006D79
0x140006d6f  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d79  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006d80  test    rax, rax
0x140006d83  jz      short loc_140006D96
0x140006d85  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006d8a  jnz     short loc_140006D96
0x140006d8c  lea     rcx, [rsp+14F0h+var_14D0]
0x140006d91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d96  cmp     [rsp+14F0h+var_14C8], r13d
0x140006d9b  jl      short loc_140006DAF
0x140006d9d  mov     ecx, 8000FFFFh; this
0x140006da2  mov     [rsp+14F0h+var_14C8], ecx
0x140006da6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006dab  mov     [rsp+14F0h+var_14C4], eax
0x140006daf  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140006db6  jnz     short loc_140006DD7
0x140006db8  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006dbf  test    rax, rax
0x140006dc2  jz      short loc_140006DCD
0x140006dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006dc9  test    al, al
0x140006dcb  jmp     short loc_140006DD5
0x140006dcd  call    cs:__imp_IsDebuggerPresent
0x140006dd3  test    eax, eax
0x140006dd5  jz      short loc_140006DDE
0x140006dd7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006ddc  jz      short loc_140006E04
0x140006dde  mov     rax, cs:g_pfnResultLoggingCallback
0x140006de5  test    rax, rax
0x140006de8  jz      short loc_140006E5D
0x140006dea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006df1  jnz     short loc_140006E5D
0x140006df3  xor     r8d, r8d
0x140006df6  xor     edx, edx
0x140006df8  lea     rcx, [rsp+14F0h+var_14D0]
0x140006dfd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e02  jmp     short loc_140006E5D
0x140006e04  mov     ebx, 800h
0x140006e09  mov     rax, cs:g_pfnResultLoggingCallback
0x140006e10  test    rax, rax
0x140006e13  jz      short loc_140006E32
0x140006e15  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140006e1c  jnz     short loc_140006E32
0x140006e1e  mov     r8d, ebx
0x140006e21  lea     rdx, [rbp+13F0h+OutputString]
0x140006e28  lea     rcx, [rsp+14F0h+var_14D0]
0x140006e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e32  cmp     [rbp+13F0h+OutputString], r13w
0x140006e3a  jnz     short loc_140006E50
0x140006e3c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140006e41  mov     rdx, rbx; unsigned __int16 *
0x140006e44  lea     rcx, [rbp+13F0h+OutputString]; this
0x140006e4b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006e50  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006e57  call    cs:__imp_OutputDebugStringW
0x140006e5d  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140006e62  jnz     short loc_140006E6D
0x140006e64  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140006e6b  jz      short loc_140006E7F
0x140006e6d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006e74  test    rax, rax
0x140006e77  jz      short loc_140006E7F
0x140006e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006e7e  nop
0x140006e7f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006e84  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
