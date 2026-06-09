# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140005cbc`
- end: `0x140005f62`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140005154`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140005cbc`
- `0x1400097c4`
- `0x14000bb40`
- `0x14000d9f0`
- `0x14000e394`
- `0x140021f90`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005d82`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005d82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005e77`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005e77`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005f01`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005f01`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140005cbc  push    rbp
0x140005cbe  push    rbx
0x140005cbf  push    rsi
0x140005cc0  push    rdi
0x140005cc1  push    r12
0x140005cc3  push    r14
0x140005cc5  push    r15
0x140005cc7  lea     rbp, [rsp-13D0h]
0x140005ccf  mov     eax, 14D0h
0x140005cd4  call    _alloca_probe
0x140005cd9  sub     rsp, rax
0x140005cdc  mov     rax, cs:__security_cookie
0x140005ce3  xor     rax, rsp
0x140005ce6  mov     [rbp+1400h+var_40], rax
0x140005ced  mov     rsi, r8
0x140005cf0  mov     edi, edx
0x140005cf2  mov     rbx, rcx
0x140005cf5  mov     r14, [rbp+1400h+arg_28]
0x140005cfc  xor     edx, edx; Val
0x140005cfe  mov     r8d, 98h; Size
0x140005d04  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140005d09  call    memset_0
0x140005d0e  nop
0x140005d0f  xor     r12d, r12d
0x140005d12  mov     [rbp+1400h+OutputString], r12w
0x140005d1a  mov     [rbp+1400h+var_1440], r12b
0x140005d1e  mov     rdx, [rbp+1400h+arg_30]; int
0x140005d25  mov     ecx, [rdx]; this
0x140005d27  mov     [rsp+1500h+var_14D8], ecx
0x140005d2b  mov     eax, [rdx+4]
0x140005d2e  mov     [rsp+1500h+var_14D4], eax
0x140005d32  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005d37  mov     r15d, eax
0x140005d3a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140005d42  mov     ecx, r12d
0x140005d45  lea     eax, [r12+8]
0x140005d4a  cmp     dword ptr [rdx+8], 1
0x140005d4e  cmovz   ecx, eax
0x140005d51  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140005d55  lea     ecx, [rax-7]
0x140005d58  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005d60  inc     ecx
0x140005d62  mov     [rsp+1500h+var_14D0], ecx
0x140005d66  mov     rcx, [rbp+1400h+arg_38]
0x140005d6d  test    rcx, rcx
0x140005d70  jz      short loc_140005D7D
0x140005d72  cmp     [rcx], r12w
0x140005d76  mov     [rsp+1500h+var_14C8], rcx
0x140005d7b  jnz     short loc_140005D82
0x140005d7d  mov     [rsp+1500h+var_14C8], r12
0x140005d82  call    cs:__imp_GetCurrentThreadId
0x140005d88  mov     [rsp+1500h+var_14C0], eax
0x140005d8c  mov     [rsp+1500h+var_14A8], rsi
0x140005d91  mov     [rsp+1500h+var_14A0], edi
0x140005d95  mov     [rsp+1500h+var_149C], r15d
0x140005d9a  mov     [rsp+1500h+var_14B8], r12
0x140005d9f  mov     [rsp+1500h+var_14B0], r12
0x140005da4  mov     [rbp+1400h+var_1458], r14
0x140005da8  mov     [rbp+1400h+var_1450], rbx
0x140005dac  mov     [rsp+1500h+var_1498], r12
0x140005db1  xorps   xmm0, xmm0
0x140005db4  xor     eax, eax
0x140005db6  movups  [rbp+1400h+var_1478], xmm0
0x140005dba  mov     [rbp+1400h+var_1468], rax
0x140005dbe  xorps   xmm1, xmm1
0x140005dc1  movups  [rsp+1500h+var_1490], xmm1
0x140005dc6  mov     [rbp+1400h+var_1480], rax
0x140005dca  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005dd1  test    rax, rax
0x140005dd4  jz      short loc_140005DE1
0x140005dd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ddb  mov     [rbp+1400h+var_1460], rax
0x140005ddf  jmp     short loc_140005DE5
0x140005de1  mov     [rbp+1400h+var_1460], r12
0x140005de5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005dec  test    rax, rax
0x140005def  jz      short loc_140005DFB
0x140005df1  lea     rcx, [rsp+1500h+var_14E0]
0x140005df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005dfb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005e02  test    rax, rax
0x140005e05  jz      short loc_140005E1B
0x140005e07  mov     r8d, 400h
0x140005e0d  lea     rdx, [rbp+1400h+var_1440]
0x140005e11  lea     rcx, [rsp+1500h+var_14E0]
0x140005e16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e1b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005e22  test    rax, rax
0x140005e25  jz      short loc_140005E31
0x140005e27  lea     rcx, [rsp+1500h+var_14E0]
0x140005e2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e31  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005e38  test    rax, rax
0x140005e3b  jz      short loc_140005E4E
0x140005e3d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140005e42  jnz     short loc_140005E4E
0x140005e44  lea     rcx, [rsp+1500h+var_14E0]
0x140005e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e4e  cmp     [rsp+1500h+var_14D8], r12d
0x140005e53  jge     loc_140005F5C
0x140005e59  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140005e60  jnz     short loc_140005E81
0x140005e62  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005e69  test    rax, rax
0x140005e6c  jz      short loc_140005E77
0x140005e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005e73  test    al, al
0x140005e75  jmp     short loc_140005E7F
0x140005e77  call    cs:__imp_IsDebuggerPresent
0x140005e7d  test    eax, eax
0x140005e7f  jz      short loc_140005E88
0x140005e81  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140005e86  jz      short loc_140005EAE
0x140005e88  mov     rax, cs:g_pfnResultLoggingCallback
0x140005e8f  test    rax, rax
0x140005e92  jz      short loc_140005F07
0x140005e94  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005e9b  jnz     short loc_140005F07
0x140005e9d  xor     r8d, r8d
0x140005ea0  xor     edx, edx
0x140005ea2  lea     rcx, [rsp+1500h+var_14E0]
0x140005ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005eac  jmp     short loc_140005F07
0x140005eae  mov     ebx, 800h
0x140005eb3  mov     rax, cs:g_pfnResultLoggingCallback
0x140005eba  test    rax, rax
0x140005ebd  jz      short loc_140005EDC
0x140005ebf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140005ec6  jnz     short loc_140005EDC
0x140005ec8  mov     r8d, ebx
0x140005ecb  lea     rdx, [rbp+1400h+OutputString]
0x140005ed2  lea     rcx, [rsp+1500h+var_14E0]
0x140005ed7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005edc  cmp     [rbp+1400h+OutputString], r12w
0x140005ee4  jnz     short loc_140005EFA
0x140005ee6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140005eeb  mov     rdx, rbx; unsigned __int16 *
0x140005eee  lea     rcx, [rbp+1400h+OutputString]; this
0x140005ef5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005efa  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140005f01  call    cs:__imp_OutputDebugStringW
0x140005f07  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140005f0c  jnz     short loc_140005F17
0x140005f0e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140005f15  jz      short loc_140005F29
0x140005f17  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005f1e  test    rax, rax
0x140005f21  jz      short loc_140005F29
0x140005f23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f28  nop
0x140005f29  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x140005f2e  jnz     short loc_140005F51
0x140005f30  mov     rcx, [rbp+1400h+var_40]
0x140005f37  xor     rcx, rsp; StackCookie
0x140005f3a  call    __security_check_cookie
0x140005f3f  add     rsp, 14D0h
0x140005f46  pop     r15
0x140005f48  pop     r14
0x140005f4a  pop     r12
0x140005f4c  pop     rdi
0x140005f4d  pop     rsi
0x140005f4e  pop     rbx
0x140005f4f  pop     rbp
0x140005f50  retn
0x140005f51  lea     rcx, [rsp+1500h+var_14E0]; this
0x140005f56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x140005f5c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
