# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180007b40`
- end: `0x180007dec`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007974`

## callees

- `0x180004694`
- `0x180005698`
- `0x180006678`
- `0x1800069d0`
- `0x180006ba4`
- `0x180007b40`
- `0x180021822`
- `0x180021910`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007be9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007be9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007ce4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007ce4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d80`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007d80`

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
0x180007b40  mov     [rsp-8+arg_18], rbx
0x180007b45  push    rbp
0x180007b46  push    rsi
0x180007b47  push    rdi
0x180007b48  push    r12
0x180007b4a  push    r13
0x180007b4c  push    r14
0x180007b4e  push    r15
0x180007b50  lea     rbp, [rsp-13C0h]
0x180007b58  mov     eax, 14C0h
0x180007b5d  call    _alloca_probe
0x180007b62  sub     rsp, rax
0x180007b65  mov     r14, r8
0x180007b68  mov     esi, edx
0x180007b6a  mov     r15, rcx
0x180007b6d  mov     rdi, [rbp+13F0h+arg_28]
0x180007b74  xor     r13d, r13d
0x180007b77  cmp     cs:g_pfnThrowPlatformException, r13
0x180007b7e  setnz   r12b
0x180007b82  xor     edx, edx; Val
0x180007b84  mov     r8d, 98h; Size
0x180007b8a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180007b8f  call    memset_0
0x180007b94  nop
0x180007b95  mov     [rbp+13F0h+OutputString], r13w
0x180007b9d  mov     [rbp+13F0h+var_1430], r13b
0x180007ba1  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180007ba8  mov     ecx, [rdx]; this
0x180007baa  mov     [rsp+14F0h+var_14C8], ecx
0x180007bae  mov     eax, [rdx+4]
0x180007bb1  mov     [rsp+14F0h+var_14C4], eax
0x180007bb5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007bba  mov     ebx, eax
0x180007bbc  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180007bc1  mov     ecx, r13d
0x180007bc4  lea     eax, [r13+8]
0x180007bc8  cmp     dword ptr [rdx+8], 1
0x180007bcc  cmovz   ecx, eax
0x180007bcf  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180007bd3  lea     ecx, [rax-7]
0x180007bd6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007bde  inc     ecx
0x180007be0  mov     [rsp+14F0h+var_14C0], ecx
0x180007be4  mov     [rsp+14F0h+var_14B8], r13
0x180007be9  call    cs:__imp_GetCurrentThreadId
0x180007bef  mov     [rsp+14F0h+var_14B0], eax
0x180007bf3  mov     [rsp+14F0h+var_1498], r14
0x180007bf8  mov     [rsp+14F0h+var_1490], esi
0x180007bfc  mov     [rsp+14F0h+var_148C], ebx
0x180007c00  mov     [rsp+14F0h+var_14A8], r13
0x180007c05  mov     [rsp+14F0h+var_14A0], r13
0x180007c0a  mov     [rbp+13F0h+var_1448], rdi
0x180007c0e  mov     [rbp+13F0h+var_1440], r15
0x180007c12  mov     [rsp+14F0h+var_1488], r13
0x180007c17  xorps   xmm0, xmm0
0x180007c1a  xor     eax, eax
0x180007c1c  movups  [rbp+13F0h+var_1468], xmm0
0x180007c20  mov     [rbp+13F0h+var_1458], rax
0x180007c24  xorps   xmm1, xmm1
0x180007c27  movups  [rsp+14F0h+var_1480], xmm1
0x180007c2c  mov     [rbp+13F0h+var_1470], rax
0x180007c30  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007c37  test    rax, rax
0x180007c3a  jz      short loc_180007C47
0x180007c3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c41  mov     [rbp+13F0h+var_1450], rax
0x180007c45  jmp     short loc_180007C4B
0x180007c47  mov     [rbp+13F0h+var_1450], r13
0x180007c4b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007c52  test    rax, rax
0x180007c55  jz      short loc_180007C61
0x180007c57  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c61  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007c68  test    rax, rax
0x180007c6b  jz      short loc_180007C81
0x180007c6d  mov     r8d, 400h
0x180007c73  lea     rdx, [rbp+13F0h+var_1430]
0x180007c77  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c81  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c88  test    rax, rax
0x180007c8b  jz      short loc_180007C97
0x180007c8d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007c92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007c97  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007c9e  test    rax, rax
0x180007ca1  jz      short loc_180007CB9
0x180007ca3  test    r12b, r12b
0x180007ca6  jnz     short loc_180007CB9
0x180007ca8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007cad  jnz     short loc_180007CB9
0x180007caf  lea     rcx, [rsp+14F0h+var_14D0]
0x180007cb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb9  cmp     [rsp+14F0h+var_14C8], r13d
0x180007cbe  jl      short loc_180007CC6
0x180007cc0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007cc6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180007ccd  jnz     short loc_180007CEE
0x180007ccf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007cd6  test    rax, rax
0x180007cd9  jz      short loc_180007CE4
0x180007cdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ce0  test    al, al
0x180007ce2  jmp     short loc_180007CEC
0x180007ce4  call    cs:__imp_IsDebuggerPresent
0x180007cea  test    eax, eax
0x180007cec  jz      short loc_180007CF7
0x180007cee  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180007cf3  mov     bl, 1
0x180007cf5  jz      short loc_180007CFA
0x180007cf7  mov     bl, r13b
0x180007cfa  test    r12b, r12b
0x180007cfd  jnz     short loc_180007D29
0x180007cff  test    bl, bl
0x180007d01  jnz     short loc_180007D29
0x180007d03  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d0a  test    rax, rax
0x180007d0d  jz      short loc_180007D86
0x180007d0f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007d16  jnz     short loc_180007D86
0x180007d18  xor     r8d, r8d
0x180007d1b  xor     edx, edx
0x180007d1d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d27  jmp     short loc_180007D86
0x180007d29  mov     edi, 800h
0x180007d2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007d35  test    rax, rax
0x180007d38  jz      short loc_180007D57
0x180007d3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180007d41  jnz     short loc_180007D57
0x180007d43  mov     r8d, edi
0x180007d46  lea     rdx, [rbp+13F0h+OutputString]
0x180007d4d  lea     rcx, [rsp+14F0h+var_14D0]
0x180007d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d57  cmp     [rbp+13F0h+OutputString], r13w
0x180007d5f  jnz     short loc_180007D75
0x180007d61  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180007d66  mov     rdx, rdi; unsigned __int16 *
0x180007d69  lea     rcx, [rbp+13F0h+OutputString]; this
0x180007d70  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007d75  test    bl, bl
0x180007d77  jz      short loc_180007D86
0x180007d79  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180007d80  call    cs:__imp_OutputDebugStringW
0x180007d86  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180007d8b  jnz     short loc_180007D96
0x180007d8d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180007d94  jz      short loc_180007DA8
0x180007d96  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007d9d  test    rax, rax
0x180007da0  jz      short loc_180007DA8
0x180007da2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da7  nop
0x180007da8  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180007dad  jz      short loc_180007DBA
0x180007daf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007db4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180007dba  test    r12b, r12b
0x180007dbd  jz      short loc_180007DD7
0x180007dbf  lea     rdx, [rbp+13F0h+OutputString]
0x180007dc6  lea     rcx, [rsp+14F0h+var_14D0]
0x180007dcb  mov     rax, cs:g_pfnThrowPlatformException
0x180007dd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dd7  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007ddc  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180007de1  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180007de6  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
