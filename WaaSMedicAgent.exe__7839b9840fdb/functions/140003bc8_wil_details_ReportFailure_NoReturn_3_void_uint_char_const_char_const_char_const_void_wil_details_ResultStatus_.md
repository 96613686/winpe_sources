# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140003bc8`
- end: `0x140003e36`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `622`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x14000394c`

## callees

- `0x14000369c`
- `0x140003bc8`
- `0x140005304`
- `0x140005b70`
- `0x1400062b0`
- `0x140007220`
- `0x140011fc0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003c76`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003c76`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003e03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003e03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003d79`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003d79`

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
  __int64 v37; // [rsp+C0h] [rbp-40h]
  char v38[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v37 = -2;
  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v38, 1024);
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
0x140003bc8  push    rbp
0x140003bca  push    rsi
0x140003bcb  push    rdi
0x140003bcc  push    r12
0x140003bce  push    r13
0x140003bd0  push    r14
0x140003bd2  push    r15
0x140003bd4  lea     rbp, [rsp-13D0h]
0x140003bdc  mov     eax, 14D0h
0x140003be1  call    _alloca_probe
0x140003be6  sub     rsp, rax
0x140003be9  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x140003bf1  mov     [rsp+1500h+arg_18], rbx
0x140003bf9  mov     r15, r8
0x140003bfc  mov     r14d, edx
0x140003bff  mov     r12, rcx
0x140003c02  mov     rsi, [rbp+1400h+arg_28]
0x140003c09  xor     edx, edx; Val
0x140003c0b  mov     r8d, 98h; Size
0x140003c11  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140003c16  call    memset_0
0x140003c1b  nop
0x140003c1c  xor     r13d, r13d
0x140003c1f  mov     [rbp+1400h+OutputString], r13w
0x140003c27  mov     [rbp+1400h+var_1430], r13b
0x140003c2b  mov     rbx, [rbp+1400h+arg_30]
0x140003c32  mov     ecx, [rbx]; this
0x140003c34  mov     [rsp+1500h+var_14D8], ecx
0x140003c38  mov     eax, [rbx+4]
0x140003c3b  mov     [rsp+1500h+var_14D4], eax
0x140003c3f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140003c44  mov     edi, eax
0x140003c46  mov     dword ptr [rsp+1500h+var_14E0], 3
0x140003c4e  mov     ecx, r13d
0x140003c51  lea     eax, [r13+8]
0x140003c55  cmp     dword ptr [rbx+8], 1
0x140003c59  cmovz   ecx, eax
0x140003c5c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003c60  lea     ecx, [rax-7]
0x140003c63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003c6b  inc     ecx
0x140003c6d  mov     [rsp+1500h+var_14D0], ecx
0x140003c71  mov     [rsp+1500h+var_14C8], r13
0x140003c76  call    cs:__imp_GetCurrentThreadId
0x140003c7c  mov     [rsp+1500h+var_14C0], eax
0x140003c80  mov     [rsp+1500h+var_14A8], r15
0x140003c85  mov     [rsp+1500h+var_14A0], r14d
0x140003c8a  mov     [rsp+1500h+var_149C], edi
0x140003c8e  mov     [rsp+1500h+var_14B8], r13
0x140003c93  mov     [rsp+1500h+var_14B0], r13
0x140003c98  mov     [rbp+1400h+var_1458], rsi
0x140003c9c  mov     [rbp+1400h+var_1450], r12
0x140003ca0  mov     [rsp+1500h+var_1498], r13
0x140003ca5  xorps   xmm0, xmm0
0x140003ca8  xor     eax, eax
0x140003caa  movups  [rbp+1400h+var_1478], xmm0
0x140003cae  mov     [rbp+1400h+var_1468], rax
0x140003cb2  xorps   xmm1, xmm1
0x140003cb5  movups  [rsp+1500h+var_1490], xmm1
0x140003cba  mov     [rbp+1400h+var_1480], rax
0x140003cbe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003cc5  test    rax, rax
0x140003cc8  jz      short loc_140003CD5
0x140003cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003ccf  mov     [rbp+1400h+var_1460], rax
0x140003cd3  jmp     short loc_140003CD9
0x140003cd5  mov     [rbp+1400h+var_1460], r13
0x140003cd9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003ce0  test    rax, rax
0x140003ce3  jz      short loc_140003CEF
0x140003ce5  lea     rcx, [rsp+1500h+var_14E0]
0x140003cea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003cef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003cf6  test    rax, rax
0x140003cf9  jz      short loc_140003D0F
0x140003cfb  mov     r8d, 400h
0x140003d01  lea     rdx, [rbp+1400h+var_1430]
0x140003d05  lea     rcx, [rsp+1500h+var_14E0]
0x140003d0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d0f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d16  test    rax, rax
0x140003d19  jz      short loc_140003D25
0x140003d1b  lea     rcx, [rsp+1500h+var_14E0]
0x140003d20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d25  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003d2c  test    rax, rax
0x140003d2f  jz      short loc_140003D42
0x140003d31  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003d36  jnz     short loc_140003D42
0x140003d38  lea     rcx, [rsp+1500h+var_14E0]
0x140003d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d42  cmp     [rsp+1500h+var_14D8], r13d
0x140003d47  jl      short loc_140003D5B
0x140003d49  mov     ecx, 8000FFFFh; this
0x140003d4e  mov     [rsp+1500h+var_14D8], ecx
0x140003d52  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003d57  mov     [rsp+1500h+var_14D4], eax
0x140003d5b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x140003d62  jnz     short loc_140003D83
0x140003d64  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003d6b  test    rax, rax
0x140003d6e  jz      short loc_140003D79
0x140003d70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003d75  test    al, al
0x140003d77  jmp     short loc_140003D81
0x140003d79  call    cs:__imp_IsDebuggerPresent
0x140003d7f  test    eax, eax
0x140003d81  jz      short loc_140003D8A
0x140003d83  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003d88  jz      short loc_140003DB0
0x140003d8a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003d91  test    rax, rax
0x140003d94  jz      short loc_140003E09
0x140003d96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003d9d  jnz     short loc_140003E09
0x140003d9f  xor     r8d, r8d
0x140003da2  xor     edx, edx
0x140003da4  lea     rcx, [rsp+1500h+var_14E0]
0x140003da9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dae  jmp     short loc_140003E09
0x140003db0  mov     ebx, 800h
0x140003db5  mov     rax, cs:g_pfnResultLoggingCallback
0x140003dbc  test    rax, rax
0x140003dbf  jz      short loc_140003DDE
0x140003dc1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003dc8  jnz     short loc_140003DDE
0x140003dca  mov     r8d, ebx
0x140003dcd  lea     rdx, [rbp+1400h+OutputString]
0x140003dd4  lea     rcx, [rsp+1500h+var_14E0]
0x140003dd9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003dde  cmp     [rbp+1400h+OutputString], r13w
0x140003de6  jnz     short loc_140003DFC
0x140003de8  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003ded  mov     rdx, rbx; unsigned __int16 *
0x140003df0  lea     rcx, [rbp+1400h+OutputString]; this
0x140003df7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003dfc  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140003e03  call    cs:__imp_OutputDebugStringW
0x140003e09  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003e0e  jnz     short loc_140003E19
0x140003e10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140003e17  jz      short loc_140003E2B
0x140003e19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003e20  test    rax, rax
0x140003e23  jz      short loc_140003E2B
0x140003e25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003e2a  nop
0x140003e2b  lea     rcx, [rsp+1500h+var_14E0]; this
0x140003e30  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
