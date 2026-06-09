# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000e0a8`
- end: `0x18000e333`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000dd78`

## callees

- `0x18000e0a8`
- `0x18000f474`
- `0x180010860`
- `0x180011808`
- `0x1800118e4`
- `0x18002120a`
- `0x180021240`
- `0x1800212d0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e155`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e155`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e2d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e2d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e249`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e249`

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
0x18000e0a8  push    rbp
0x18000e0aa  push    rbx
0x18000e0ab  push    rsi
0x18000e0ac  push    rdi
0x18000e0ad  push    r12
0x18000e0af  push    r14
0x18000e0b1  push    r15
0x18000e0b3  lea     rbp, [rsp-13D0h]
0x18000e0bb  mov     eax, 14D0h
0x18000e0c0  call    _alloca_probe
0x18000e0c5  sub     rsp, rax
0x18000e0c8  mov     rax, cs:__security_cookie
0x18000e0cf  xor     rax, rsp
0x18000e0d2  mov     [rbp+1400h+var_40], rax
0x18000e0d9  mov     rdi, [rbp+1400h+arg_28]
0x18000e0e0  mov     r14, r8
0x18000e0e3  mov     esi, edx
0x18000e0e5  mov     r15, rcx
0x18000e0e8  xor     edx, edx; Val
0x18000e0ea  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000e0ef  mov     r8d, 98h; Size
0x18000e0f5  call    memset_0
0x18000e0fa  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000e101  xor     r12d, r12d
0x18000e104  mov     [rbp+1400h+OutputString], r12w
0x18000e10c  mov     [rbp+1400h+var_1440], r12b
0x18000e110  mov     ecx, [rdx]; this
0x18000e112  mov     eax, [rdx+4]
0x18000e115  mov     [rsp+1500h+var_14D8], ecx
0x18000e119  mov     [rsp+1500h+var_14D4], eax
0x18000e11d  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e122  cmp     dword ptr [rdx+8], 1
0x18000e126  mov     ebx, eax
0x18000e128  lea     eax, [r12+8]
0x18000e12d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000e135  mov     ecx, r12d
0x18000e138  cmovz   ecx, eax
0x18000e13b  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000e13f  lea     ecx, [rax-7]
0x18000e142  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e14a  inc     ecx
0x18000e14c  mov     [rsp+1500h+var_14C8], r12
0x18000e151  mov     [rsp+1500h+var_14D0], ecx
0x18000e155  call    cs:__imp_GetCurrentThreadId
0x18000e15b  xorps   xmm0, xmm0
0x18000e15e  mov     [rsp+1500h+var_14A8], r14
0x18000e163  mov     [rsp+1500h+var_14C0], eax
0x18000e167  xorps   xmm1, xmm1
0x18000e16a  xor     eax, eax
0x18000e16c  mov     [rsp+1500h+var_14A0], esi
0x18000e170  mov     [rbp+1400h+var_1468], rax
0x18000e174  mov     [rbp+1400h+var_1480], rax
0x18000e178  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e17f  mov     [rsp+1500h+var_149C], ebx
0x18000e183  mov     [rsp+1500h+var_14B8], r12
0x18000e188  mov     [rsp+1500h+var_14B0], r12
0x18000e18d  mov     [rbp+1400h+var_1458], rdi
0x18000e191  mov     [rbp+1400h+var_1450], r15
0x18000e195  mov     [rsp+1500h+var_1498], r12
0x18000e19a  movups  [rbp+1400h+var_1478], xmm0
0x18000e19e  movups  [rsp+1500h+var_1490], xmm1
0x18000e1a3  test    rax, rax
0x18000e1a6  jz      short loc_18000E1B3
0x18000e1a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ad  mov     [rbp+1400h+var_1460], rax
0x18000e1b1  jmp     short loc_18000E1B7
0x18000e1b3  mov     [rbp+1400h+var_1460], r12
0x18000e1b7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e1be  test    rax, rax
0x18000e1c1  jz      short loc_18000E1CD
0x18000e1c3  lea     rcx, [rsp+1500h+var_14E0]
0x18000e1c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e1d4  test    rax, rax
0x18000e1d7  jz      short loc_18000E1ED
0x18000e1d9  mov     r8d, 400h
0x18000e1df  lea     rdx, [rbp+1400h+var_1440]
0x18000e1e3  lea     rcx, [rsp+1500h+var_14E0]
0x18000e1e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ed  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e1f4  test    rax, rax
0x18000e1f7  jz      short loc_18000E203
0x18000e1f9  lea     rcx, [rsp+1500h+var_14E0]
0x18000e1fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e203  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e20a  test    rax, rax
0x18000e20d  jz      short loc_18000E220
0x18000e20f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e214  jnz     short loc_18000E220
0x18000e216  lea     rcx, [rsp+1500h+var_14E0]
0x18000e21b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e220  cmp     [rsp+1500h+var_14D8], r12d
0x18000e225  jge     loc_18000E322
0x18000e22b  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000e232  jnz     short loc_18000E253
0x18000e234  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e23b  test    rax, rax
0x18000e23e  jz      short loc_18000E249
0x18000e240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e245  test    al, al
0x18000e247  jmp     short loc_18000E251
0x18000e249  call    cs:__imp_IsDebuggerPresent
0x18000e24f  test    eax, eax
0x18000e251  jz      short loc_18000E25A
0x18000e253  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e258  jz      short loc_18000E280
0x18000e25a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e261  test    rax, rax
0x18000e264  jz      short loc_18000E2D9
0x18000e266  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e26d  jnz     short loc_18000E2D9
0x18000e26f  xor     r8d, r8d
0x18000e272  lea     rcx, [rsp+1500h+var_14E0]
0x18000e277  xor     edx, edx
0x18000e279  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e27e  jmp     short loc_18000E2D9
0x18000e280  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e287  mov     ebx, 800h
0x18000e28c  test    rax, rax
0x18000e28f  jz      short loc_18000E2AE
0x18000e291  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e298  jnz     short loc_18000E2AE
0x18000e29a  mov     r8d, ebx
0x18000e29d  lea     rdx, [rbp+1400h+OutputString]
0x18000e2a4  lea     rcx, [rsp+1500h+var_14E0]
0x18000e2a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2ae  cmp     [rbp+1400h+OutputString], r12w
0x18000e2b6  jnz     short loc_18000E2CC
0x18000e2b8  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000e2bd  mov     rdx, rbx; unsigned __int16 *
0x18000e2c0  lea     rcx, [rbp+1400h+OutputString]; this
0x18000e2c7  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e2cc  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000e2d3  call    cs:__imp_OutputDebugStringW
0x18000e2d9  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000e2de  jnz     short loc_18000E2E9
0x18000e2e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000e2e7  jz      short loc_18000E2FA
0x18000e2e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e2f0  test    rax, rax
0x18000e2f3  jz      short loc_18000E2FA
0x18000e2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e2fa  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000e2ff  jnz     short loc_18000E328
0x18000e301  mov     rcx, [rbp+1400h+var_40]
0x18000e308  xor     rcx, rsp; StackCookie
0x18000e30b  call    __security_check_cookie
0x18000e310  add     rsp, 14D0h
0x18000e317  pop     r15
0x18000e319  pop     r14
0x18000e31b  pop     r12
0x18000e31d  pop     rdi
0x18000e31e  pop     rsi
0x18000e31f  pop     rbx
0x18000e320  pop     rbp
0x18000e321  retn
0x18000e322  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000e328  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000e32d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
