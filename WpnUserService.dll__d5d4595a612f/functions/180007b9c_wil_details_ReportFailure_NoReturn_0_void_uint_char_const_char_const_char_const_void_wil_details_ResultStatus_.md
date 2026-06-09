# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007b9c`
- end: `0x180007e4f`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `691`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, service_task`

## callers

- `0x1800077c0`

## callees

- `0x18000354c`
- `0x180004fb4`
- `0x180005f44`
- `0x180006cc0`
- `0x180007010`
- `0x180007198`
- `0x180007b9c`
- `0x180010ba0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007c45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007de3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007de3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007d47`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007d47`

## string_xrefs

- `0x180007c4f`: `onecoreuap\base\diagnosis\platform\notifications\servicehost\userservice\dll\wpnuserservice.cpp`

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
  v28 = "onecoreuap\\base\\diagnosis\\platform\\notifications\\servicehost\\userservice\\dll\\wpnuserservice.cpp";
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v15);
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
0x180007b9c  mov     [rsp-8+arg_10], rbx
0x180007ba1  mov     [rsp-8+arg_18], rsi
0x180007ba6  push    rbp
0x180007ba7  push    rdi
0x180007ba8  push    r12
0x180007baa  push    r14
0x180007bac  push    r15
0x180007bae  lea     rbp, [rsp-13C0h]
0x180007bb6  mov     eax, 14C0h
0x180007bbb  call    _alloca_probe
0x180007bc0  sub     rsp, rax
0x180007bc3  mov     esi, edx
0x180007bc5  mov     r14, rcx
0x180007bc8  mov     rdi, [rbp+13E0h+arg_28]
0x180007bcf  xor     r12d, r12d
0x180007bd2  cmp     cs:g_pfnThrowPlatformException, r12
0x180007bd9  setnz   r15b
0x180007bdd  xor     edx, edx; Val
0x180007bdf  mov     r8d, 98h; Size
0x180007be5  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180007bea  call    memset_0
0x180007bef  nop
0x180007bf0  mov     [rbp+13E0h+OutputString], r12w
0x180007bf8  mov     [rbp+13E0h+var_1420], r12b
0x180007bfc  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x180007c03  mov     ecx, [rdx]; this
0x180007c05  mov     [rsp+14E0h+var_14B8], ecx
0x180007c09  mov     eax, [rdx+4]
0x180007c0c  mov     [rsp+14E0h+var_14B4], eax
0x180007c10  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007c15  mov     ebx, eax
0x180007c17  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x180007c1c  mov     ecx, r12d
0x180007c1f  lea     eax, [r12+8]
0x180007c24  cmp     dword ptr [rdx+8], 1
0x180007c28  cmovz   ecx, eax
0x180007c2b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180007c2f  lea     ecx, [rax-7]
0x180007c32  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007c3a  inc     ecx
0x180007c3c  mov     [rsp+14E0h+var_14B0], ecx
0x180007c40  mov     [rsp+14E0h+var_14A8], r12
0x180007c45  call    cs:__imp_GetCurrentThreadId
0x180007c4b  mov     [rsp+14E0h+var_14A0], eax
0x180007c4f  lea     rax, aOnecoreuapBase; "onecoreuap\\base\\diagnosis\\platform\\"...
0x180007c56  mov     [rsp+14E0h+var_1488], rax
0x180007c5b  mov     [rsp+14E0h+var_1480], esi
0x180007c5f  mov     [rsp+14E0h+var_147C], ebx
0x180007c63  mov     [rsp+14E0h+var_1498], r12
0x180007c68  mov     [rsp+14E0h+var_1490], r12
0x180007c6d  mov     [rbp+13E0h+var_1438], rdi
0x180007c71  mov     [rbp+13E0h+var_1430], r14
0x180007c75  mov     [rsp+14E0h+var_1478], r12
0x180007c7a  xorps   xmm0, xmm0
0x180007c7d  xor     eax, eax
0x180007c7f  movups  [rbp+13E0h+var_1458], xmm0
0x180007c83  mov     [rbp+13E0h+var_1448], rax
0x180007c87  xorps   xmm1, xmm1
0x180007c8a  movups  [rsp+14E0h+var_1470], xmm1
0x180007c8f  mov     [rbp+13E0h+var_1460], rax
0x180007c93  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007c9a  test    rax, rax
0x180007c9d  jz      short loc_180007CAA
0x180007c9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ca4  mov     [rbp+13E0h+var_1440], rax
0x180007ca8  jmp     short loc_180007CAE
0x180007caa  mov     [rbp+13E0h+var_1440], r12
0x180007cae  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007cb5  test    rax, rax
0x180007cb8  jz      short loc_180007CC4
0x180007cba  lea     rcx, [rsp+14E0h+var_14C0]
0x180007cbf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cc4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007ccb  test    rax, rax
0x180007cce  jz      short loc_180007CE4
0x180007cd0  mov     r8d, 400h
0x180007cd6  lea     rdx, [rbp+13E0h+var_1420]
0x180007cda  lea     rcx, [rsp+14E0h+var_14C0]
0x180007cdf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ceb  test    rax, rax
0x180007cee  jz      short loc_180007CFA
0x180007cf0  lea     rcx, [rsp+14E0h+var_14C0]
0x180007cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cfa  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007d01  test    rax, rax
0x180007d04  jz      short loc_180007D1C
0x180007d06  test    r15b, r15b
0x180007d09  jnz     short loc_180007D1C
0x180007d0b  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180007d10  jnz     short loc_180007D1C
0x180007d12  lea     rcx, [rsp+14E0h+var_14C0]
0x180007d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d1c  cmp     [rsp+14E0h+var_14B8], r12d
0x180007d21  jl      short loc_180007D29
0x180007d23  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007d29  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007d30  jnz     short loc_180007D51
0x180007d32  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007d39  test    rax, rax
0x180007d3c  jz      short loc_180007D47
0x180007d3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d43  test    al, al
0x180007d45  jmp     short loc_180007D4F
0x180007d47  call    cs:__imp_IsDebuggerPresent
0x180007d4d  test    eax, eax
0x180007d4f  jz      short loc_180007D5A
0x180007d51  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180007d56  mov     bl, 1
0x180007d58  jz      short loc_180007D5D
0x180007d5a  mov     bl, r12b
0x180007d5d  test    r15b, r15b
0x180007d60  jnz     short loc_180007D8C
0x180007d62  test    bl, bl
0x180007d64  jnz     short loc_180007D8C
0x180007d66  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d6d  test    rax, rax
0x180007d70  jz      short loc_180007DE9
0x180007d72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007d79  jnz     short loc_180007DE9
0x180007d7b  xor     r8d, r8d
0x180007d7e  xor     edx, edx
0x180007d80  lea     rcx, [rsp+14E0h+var_14C0]
0x180007d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d8a  jmp     short loc_180007DE9
0x180007d8c  mov     edi, 800h
0x180007d91  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d98  test    rax, rax
0x180007d9b  jz      short loc_180007DBA
0x180007d9d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007da4  jnz     short loc_180007DBA
0x180007da6  mov     r8d, edi
0x180007da9  lea     rdx, [rbp+13E0h+OutputString]
0x180007db0  lea     rcx, [rsp+14E0h+var_14C0]
0x180007db5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dba  cmp     [rbp+13E0h+OutputString], r12w
0x180007dc2  jnz     short loc_180007DD8
0x180007dc4  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x180007dc9  mov     rdx, rdi; unsigned __int16 *
0x180007dcc  lea     rcx, [rbp+13E0h+OutputString]; this
0x180007dd3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007dd8  test    bl, bl
0x180007dda  jz      short loc_180007DE9
0x180007ddc  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180007de3  call    cs:__imp_OutputDebugStringW
0x180007de9  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x180007dee  jnz     short loc_180007DF9
0x180007df0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180007df7  jz      short loc_180007E0B
0x180007df9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007e00  test    rax, rax
0x180007e03  jz      short loc_180007E0B
0x180007e05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e0a  nop
0x180007e0b  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x180007e10  jz      short loc_180007E1D
0x180007e12  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180007e17  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007e1d  test    r15b, r15b
0x180007e20  jz      short loc_180007E3A
0x180007e22  lea     rdx, [rbp+13E0h+OutputString]
0x180007e29  lea     rcx, [rsp+14E0h+var_14C0]
0x180007e2e  mov     rax, cs:g_pfnThrowPlatformException
0x180007e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e3a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180007e3f  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180007e44  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180007e49  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
