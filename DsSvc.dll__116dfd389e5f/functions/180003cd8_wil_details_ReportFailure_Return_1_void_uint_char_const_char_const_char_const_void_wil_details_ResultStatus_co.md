# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003cd8`
- end: `0x180003f63`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003998`

## callees

- `0x180003cd8`
- `0x180004b24`
- `0x180005cc0`
- `0x1800069c8`
- `0x180006ba4`
- `0x18001b30a`
- `0x18001b340`
- `0x18001b3d0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d85`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003d85`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003e79`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003e79`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f03`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003f03`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x180003cd8  push    rbp
0x180003cda  push    rbx
0x180003cdb  push    rsi
0x180003cdc  push    rdi
0x180003cdd  push    r12
0x180003cdf  push    r14
0x180003ce1  push    r15
0x180003ce3  lea     rbp, [rsp-13D0h]
0x180003ceb  mov     eax, 14D0h
0x180003cf0  call    _alloca_probe
0x180003cf5  sub     rsp, rax
0x180003cf8  mov     rax, cs:__security_cookie
0x180003cff  xor     rax, rsp
0x180003d02  mov     [rbp+1400h+var_40], rax
0x180003d09  mov     rdi, [rbp+1400h+arg_28]
0x180003d10  mov     r14, r8
0x180003d13  mov     esi, edx
0x180003d15  mov     r15, rcx
0x180003d18  xor     edx, edx; Val
0x180003d1a  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003d1f  mov     r8d, 98h; Size
0x180003d25  call    memset_0
0x180003d2a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003d31  xor     r12d, r12d
0x180003d34  mov     [rbp+1400h+OutputString], r12w
0x180003d3c  mov     [rbp+1400h+var_1440], r12b
0x180003d40  mov     ecx, [rdx]; this
0x180003d42  mov     eax, [rdx+4]
0x180003d45  mov     [rsp+1500h+var_14D8], ecx
0x180003d49  mov     [rsp+1500h+var_14D4], eax
0x180003d4d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003d52  cmp     dword ptr [rdx+8], 1
0x180003d56  mov     ebx, eax
0x180003d58  lea     eax, [r12+8]
0x180003d5d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003d65  mov     ecx, r12d
0x180003d68  cmovz   ecx, eax
0x180003d6b  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003d6f  lea     ecx, [rax-7]
0x180003d72  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003d7a  inc     ecx
0x180003d7c  mov     [rsp+1500h+var_14C8], r12
0x180003d81  mov     [rsp+1500h+var_14D0], ecx
0x180003d85  call    cs:__imp_GetCurrentThreadId
0x180003d8b  xorps   xmm0, xmm0
0x180003d8e  mov     [rsp+1500h+var_14A8], r14
0x180003d93  mov     [rsp+1500h+var_14C0], eax
0x180003d97  xorps   xmm1, xmm1
0x180003d9a  xor     eax, eax
0x180003d9c  mov     [rsp+1500h+var_14A0], esi
0x180003da0  mov     [rbp+1400h+var_1468], rax
0x180003da4  mov     [rbp+1400h+var_1480], rax
0x180003da8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003daf  mov     [rsp+1500h+var_149C], ebx
0x180003db3  mov     [rsp+1500h+var_14B8], r12
0x180003db8  mov     [rsp+1500h+var_14B0], r12
0x180003dbd  mov     [rbp+1400h+var_1458], rdi
0x180003dc1  mov     [rbp+1400h+var_1450], r15
0x180003dc5  mov     [rsp+1500h+var_1498], r12
0x180003dca  movups  [rbp+1400h+var_1478], xmm0
0x180003dce  movups  [rsp+1500h+var_1490], xmm1
0x180003dd3  test    rax, rax
0x180003dd6  jz      short loc_180003DE3
0x180003dd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ddd  mov     [rbp+1400h+var_1460], rax
0x180003de1  jmp     short loc_180003DE7
0x180003de3  mov     [rbp+1400h+var_1460], r12
0x180003de7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003dee  test    rax, rax
0x180003df1  jz      short loc_180003DFD
0x180003df3  lea     rcx, [rsp+1500h+var_14E0]
0x180003df8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003dfd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003e04  test    rax, rax
0x180003e07  jz      short loc_180003E1D
0x180003e09  mov     r8d, 400h
0x180003e0f  lea     rdx, [rbp+1400h+var_1440]
0x180003e13  lea     rcx, [rsp+1500h+var_14E0]
0x180003e18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e1d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e24  test    rax, rax
0x180003e27  jz      short loc_180003E33
0x180003e29  lea     rcx, [rsp+1500h+var_14E0]
0x180003e2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003e3a  test    rax, rax
0x180003e3d  jz      short loc_180003E50
0x180003e3f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003e44  jnz     short loc_180003E50
0x180003e46  lea     rcx, [rsp+1500h+var_14E0]
0x180003e4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e50  cmp     [rsp+1500h+var_14D8], r12d
0x180003e55  jge     loc_180003F52
0x180003e5b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003e62  jnz     short loc_180003E83
0x180003e64  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003e6b  test    rax, rax
0x180003e6e  jz      short loc_180003E79
0x180003e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003e75  test    al, al
0x180003e77  jmp     short loc_180003E81
0x180003e79  call    cs:__imp_IsDebuggerPresent
0x180003e7f  test    eax, eax
0x180003e81  jz      short loc_180003E8A
0x180003e83  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003e88  jz      short loc_180003EB0
0x180003e8a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003e91  test    rax, rax
0x180003e94  jz      short loc_180003F09
0x180003e96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003e9d  jnz     short loc_180003F09
0x180003e9f  xor     r8d, r8d
0x180003ea2  lea     rcx, [rsp+1500h+var_14E0]
0x180003ea7  xor     edx, edx
0x180003ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003eae  jmp     short loc_180003F09
0x180003eb0  mov     rax, cs:g_pfnResultLoggingCallback
0x180003eb7  mov     ebx, 800h
0x180003ebc  test    rax, rax
0x180003ebf  jz      short loc_180003EDE
0x180003ec1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003ec8  jnz     short loc_180003EDE
0x180003eca  mov     r8d, ebx
0x180003ecd  lea     rdx, [rbp+1400h+OutputString]
0x180003ed4  lea     rcx, [rsp+1500h+var_14E0]
0x180003ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003ede  cmp     [rbp+1400h+OutputString], r12w
0x180003ee6  jnz     short loc_180003EFC
0x180003ee8  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003eed  mov     rdx, rbx; unsigned __int16 *
0x180003ef0  lea     rcx, [rbp+1400h+OutputString]; this
0x180003ef7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003efc  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003f03  call    cs:__imp_OutputDebugStringW
0x180003f09  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003f0e  jnz     short loc_180003F19
0x180003f10  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003f17  jz      short loc_180003F2A
0x180003f19  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003f20  test    rax, rax
0x180003f23  jz      short loc_180003F2A
0x180003f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f2a  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003f2f  jnz     short loc_180003F58
0x180003f31  mov     rcx, [rbp+1400h+var_40]
0x180003f38  xor     rcx, rsp; StackCookie
0x180003f3b  call    __security_check_cookie
0x180003f40  add     rsp, 14D0h
0x180003f47  pop     r15
0x180003f49  pop     r14
0x180003f4b  pop     r12
0x180003f4d  pop     rdi
0x180003f4e  pop     rsi
0x180003f4f  pop     rbx
0x180003f50  pop     rbp
0x180003f51  retn
0x180003f52  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180003f58  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003f5d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
