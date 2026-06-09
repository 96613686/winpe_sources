# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004e14`
- end: `0x180005089`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `629`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004adc`

## callees

- `0x180004e14`
- `0x180007920`
- `0x1800082e4`
- `0x180009844`
- `0x18000b69c`
- `0x18000b858`
- `0x180043052`
- `0x180043090`
- `0x180043150`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004ffe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004ffe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ebe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ebe`

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
  int v9; // eax
  int v10; // eax
  __int64 v11; // rdx
  bool v12; // zf
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // rdx
  __int64 v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  const char *v29; // [rsp+58h] [rbp-A8h]
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
  v9 = a7[1];
  v22 = *a7;
  v23 = v9;
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v12 = *(_DWORD *)(v11 + 8) == 1;
  v13 = v10;
  v20 = 1;
  v14 = 0;
  if ( v12 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v30 = a2;
  v26 = CurrentThreadId;
  v31 = v13;
  v29 = "wil";
  v36 = 0;
  v34 = 0;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::details::IsDebuggerPresent(v16) || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString(OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v17);
}

```

## disassembly

```asm
0x180004e14  mov     [rsp-8+arg_10], rbx
0x180004e19  push    rbp
0x180004e1a  push    rsi
0x180004e1b  push    rdi
0x180004e1c  push    r14
0x180004e1e  push    r15
0x180004e20  lea     rbp, [rsp-13D0h]
0x180004e28  mov     eax, 14D0h
0x180004e2d  call    _alloca_probe
0x180004e32  sub     rsp, rax
0x180004e35  mov     rax, cs:__security_cookie
0x180004e3c  xor     rax, rsp
0x180004e3f  mov     [rbp+13F0h+var_30], rax
0x180004e46  mov     rdi, [rbp+13F0h+arg_28]
0x180004e4d  mov     esi, edx
0x180004e4f  mov     r14, rcx
0x180004e52  xor     edx, edx; Val
0x180004e54  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004e59  mov     r8d, 98h; Size
0x180004e5f  call    memset_0
0x180004e64  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180004e6b  xor     r15d, r15d
0x180004e6e  mov     [rbp+13F0h+OutputString], r15w
0x180004e76  mov     [rbp+13F0h+var_1430], r15b
0x180004e7a  mov     ecx, [rdx]; this
0x180004e7c  mov     eax, [rdx+4]
0x180004e7f  mov     [rsp+14F0h+var_14C8], ecx
0x180004e83  mov     [rsp+14F0h+var_14C4], eax
0x180004e87  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e8c  cmp     dword ptr [rdx+8], 1
0x180004e90  mov     ebx, eax
0x180004e92  lea     eax, [r15+8]
0x180004e96  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180004e9e  mov     ecx, r15d
0x180004ea1  cmovz   ecx, eax
0x180004ea4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004ea8  lea     ecx, [rax-7]
0x180004eab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004eb3  inc     ecx
0x180004eb5  mov     [rsp+14F0h+var_14B8], r15
0x180004eba  mov     [rsp+14F0h+var_14C0], ecx
0x180004ebe  call    cs:__imp_GetCurrentThreadId
0x180004ec4  xorps   xmm0, xmm0
0x180004ec7  mov     [rsp+14F0h+var_1490], esi
0x180004ecb  mov     [rsp+14F0h+var_14B0], eax
0x180004ecf  xorps   xmm1, xmm1
0x180004ed2  lea     rax, aWil; "wil"
0x180004ed9  mov     [rsp+14F0h+var_148C], ebx
0x180004edd  mov     [rsp+14F0h+var_1498], rax
0x180004ee2  xor     eax, eax
0x180004ee4  mov     [rbp+13F0h+var_1458], rax
0x180004ee8  mov     [rbp+13F0h+var_1470], rax
0x180004eec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004ef3  mov     [rsp+14F0h+var_14A8], r15
0x180004ef8  mov     [rsp+14F0h+var_14A0], r15
0x180004efd  mov     [rbp+13F0h+var_1448], rdi
0x180004f01  mov     [rbp+13F0h+var_1440], r14
0x180004f05  mov     [rsp+14F0h+var_1488], r15
0x180004f0a  movups  [rbp+13F0h+var_1468], xmm0
0x180004f0e  movups  [rsp+14F0h+var_1480], xmm1
0x180004f13  test    rax, rax
0x180004f16  jz      short loc_180004F23
0x180004f18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f1d  mov     [rbp+13F0h+var_1450], rax
0x180004f21  jmp     short loc_180004F27
0x180004f23  mov     [rbp+13F0h+var_1450], r15
0x180004f27  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004f2e  test    rax, rax
0x180004f31  jz      short loc_180004F3D
0x180004f33  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004f44  test    rax, rax
0x180004f47  jz      short loc_180004F5D
0x180004f49  mov     r8d, 400h
0x180004f4f  lea     rdx, [rbp+13F0h+var_1430]
0x180004f53  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f64  test    rax, rax
0x180004f67  jz      short loc_180004F73
0x180004f69  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f73  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f7a  test    rax, rax
0x180004f7d  jz      short loc_180004F90
0x180004f7f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004f84  jnz     short loc_180004F90
0x180004f86  lea     rcx, [rsp+14F0h+var_14D0]
0x180004f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f90  cmp     [rsp+14F0h+var_14C8], r15d
0x180004f95  jge     loc_180005078
0x180004f9b  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180004fa0  test    al, al
0x180004fa2  jz      short loc_180005006
0x180004fa4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004fa9  jnz     short loc_180005006
0x180004fab  mov     rax, cs:g_pfnResultLoggingCallback
0x180004fb2  mov     ebx, 800h
0x180004fb7  test    rax, rax
0x180004fba  jz      short loc_180004FD9
0x180004fbc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180004fc3  jnz     short loc_180004FD9
0x180004fc5  mov     r8d, ebx
0x180004fc8  lea     rdx, [rbp+13F0h+OutputString]
0x180004fcf  lea     rcx, [rsp+14F0h+var_14D0]
0x180004fd4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fd9  cmp     [rbp+13F0h+OutputString], r15w
0x180004fe1  jnz     short loc_180004FF7
0x180004fe3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004fe8  mov     rdx, rbx; unsigned __int16 *
0x180004feb  lea     rcx, [rbp+13F0h+OutputString]; pszDest
0x180004ff2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004ff7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004ffe  call    cs:__imp_OutputDebugStringW
0x180005004  jmp     short loc_18000502A
0x180005006  mov     rax, cs:g_pfnResultLoggingCallback
0x18000500d  test    rax, rax
0x180005010  jz      short loc_18000502A
0x180005012  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180005019  jnz     short loc_18000502A
0x18000501b  xor     r8d, r8d
0x18000501e  lea     rcx, [rsp+14F0h+var_14D0]
0x180005023  xor     edx, edx
0x180005025  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000502a  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000502f  jnz     short loc_18000503A
0x180005031  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180005038  jz      short loc_18000504B
0x18000503a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005041  test    rax, rax
0x180005044  jz      short loc_18000504B
0x180005046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504b  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180005050  jnz     short loc_18000507E
0x180005052  mov     rcx, [rbp+13F0h+var_30]
0x180005059  xor     rcx, rsp; StackCookie
0x18000505c  call    __security_check_cookie
0x180005061  mov     rbx, [rsp+14F0h+arg_10]
0x180005069  add     rsp, 14D0h
0x180005070  pop     r15
0x180005072  pop     r14
0x180005074  pop     rdi
0x180005075  pop     rsi
0x180005076  pop     rbp
0x180005077  retn
0x180005078  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000507e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005083  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
