# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800027d4`
- end: `0x180002a7a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002268`

## callees

- `0x1800016a0`
- `0x180002058`
- `0x1800027d4`
- `0x180003954`
- `0x180004890`
- `0x1800058f0`
- `0x1800059cc`
- `0x180009f20`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000289a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000289a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000298f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000298f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a19`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180002a19`

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
0x1800027d4  push    rbp
0x1800027d6  push    rbx
0x1800027d7  push    rsi
0x1800027d8  push    rdi
0x1800027d9  push    r12
0x1800027db  push    r14
0x1800027dd  push    r15
0x1800027df  lea     rbp, [rsp-13D0h]
0x1800027e7  mov     eax, 14D0h
0x1800027ec  call    _alloca_probe
0x1800027f1  sub     rsp, rax
0x1800027f4  mov     rax, cs:__security_cookie
0x1800027fb  xor     rax, rsp
0x1800027fe  mov     [rbp+1400h+var_40], rax
0x180002805  mov     rsi, r8
0x180002808  mov     edi, edx
0x18000280a  mov     rbx, rcx
0x18000280d  mov     r14, [rbp+1400h+arg_28]
0x180002814  xor     edx, edx; Val
0x180002816  mov     r8d, 98h; Size
0x18000281c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180002821  call    memset_0
0x180002826  nop
0x180002827  xor     r12d, r12d
0x18000282a  mov     [rbp+1400h+OutputString], r12w
0x180002832  mov     [rbp+1400h+var_1440], r12b
0x180002836  mov     rdx, [rbp+1400h+arg_30]; int
0x18000283d  mov     ecx, [rdx]; this
0x18000283f  mov     [rsp+1500h+var_14D8], ecx
0x180002843  mov     eax, [rdx+4]
0x180002846  mov     [rsp+1500h+var_14D4], eax
0x18000284a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000284f  mov     r15d, eax
0x180002852  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000285a  mov     ecx, r12d
0x18000285d  lea     eax, [r12+8]
0x180002862  cmp     dword ptr [rdx+8], 1
0x180002866  cmovz   ecx, eax
0x180002869  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000286d  lea     ecx, [rax-7]
0x180002870  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180002878  inc     ecx
0x18000287a  mov     [rsp+1500h+var_14D0], ecx
0x18000287e  mov     rcx, [rbp+1400h+arg_38]
0x180002885  test    rcx, rcx
0x180002888  jz      short loc_180002895
0x18000288a  cmp     [rcx], r12w
0x18000288e  mov     [rsp+1500h+var_14C8], rcx
0x180002893  jnz     short loc_18000289A
0x180002895  mov     [rsp+1500h+var_14C8], r12
0x18000289a  call    cs:__imp_GetCurrentThreadId
0x1800028a0  mov     [rsp+1500h+var_14C0], eax
0x1800028a4  mov     [rsp+1500h+var_14A8], rsi
0x1800028a9  mov     [rsp+1500h+var_14A0], edi
0x1800028ad  mov     [rsp+1500h+var_149C], r15d
0x1800028b2  mov     [rsp+1500h+var_14B8], r12
0x1800028b7  mov     [rsp+1500h+var_14B0], r12
0x1800028bc  mov     [rbp+1400h+var_1458], r14
0x1800028c0  mov     [rbp+1400h+var_1450], rbx
0x1800028c4  mov     [rsp+1500h+var_1498], r12
0x1800028c9  xorps   xmm0, xmm0
0x1800028cc  xor     eax, eax
0x1800028ce  movups  [rbp+1400h+var_1478], xmm0
0x1800028d2  mov     [rbp+1400h+var_1468], rax
0x1800028d6  xorps   xmm1, xmm1
0x1800028d9  movups  [rsp+1500h+var_1490], xmm1
0x1800028de  mov     [rbp+1400h+var_1480], rax
0x1800028e2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800028e9  test    rax, rax
0x1800028ec  jz      short loc_1800028F9
0x1800028ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f3  mov     [rbp+1400h+var_1460], rax
0x1800028f7  jmp     short loc_1800028FD
0x1800028f9  mov     [rbp+1400h+var_1460], r12
0x1800028fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180002904  test    rax, rax
0x180002907  jz      short loc_180002913
0x180002909  lea     rcx, [rsp+1500h+var_14E0]
0x18000290e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002913  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000291a  test    rax, rax
0x18000291d  jz      short loc_180002933
0x18000291f  mov     r8d, 400h
0x180002925  lea     rdx, [rbp+1400h+var_1440]
0x180002929  lea     rcx, [rsp+1500h+var_14E0]
0x18000292e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002933  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000293a  test    rax, rax
0x18000293d  jz      short loc_180002949
0x18000293f  lea     rcx, [rsp+1500h+var_14E0]
0x180002944  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002949  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002950  test    rax, rax
0x180002953  jz      short loc_180002966
0x180002955  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000295a  jnz     short loc_180002966
0x18000295c  lea     rcx, [rsp+1500h+var_14E0]
0x180002961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002966  cmp     [rsp+1500h+var_14D8], r12d
0x18000296b  jge     loc_180002A74
0x180002971  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180002978  jnz     short loc_180002999
0x18000297a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002981  test    rax, rax
0x180002984  jz      short loc_18000298F
0x180002986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000298b  test    al, al
0x18000298d  jmp     short loc_180002997
0x18000298f  call    cs:__imp_IsDebuggerPresent
0x180002995  test    eax, eax
0x180002997  jz      short loc_1800029A0
0x180002999  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000299e  jz      short loc_1800029C6
0x1800029a0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029a7  test    rax, rax
0x1800029aa  jz      short loc_180002A1F
0x1800029ac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800029b3  jnz     short loc_180002A1F
0x1800029b5  xor     r8d, r8d
0x1800029b8  xor     edx, edx
0x1800029ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800029bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029c4  jmp     short loc_180002A1F
0x1800029c6  mov     ebx, 800h
0x1800029cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800029d2  test    rax, rax
0x1800029d5  jz      short loc_1800029F4
0x1800029d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800029de  jnz     short loc_1800029F4
0x1800029e0  mov     r8d, ebx
0x1800029e3  lea     rdx, [rbp+1400h+OutputString]
0x1800029ea  lea     rcx, [rsp+1500h+var_14E0]
0x1800029ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800029f4  cmp     [rbp+1400h+OutputString], r12w
0x1800029fc  jnz     short loc_180002A12
0x1800029fe  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180002a03  mov     rdx, rbx; unsigned __int16 *
0x180002a06  lea     rcx, [rbp+1400h+OutputString]; this
0x180002a0d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180002a12  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180002a19  call    cs:__imp_OutputDebugStringW
0x180002a1f  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180002a24  jnz     short loc_180002A2F
0x180002a26  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180002a2d  jz      short loc_180002A41
0x180002a2f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002a36  test    rax, rax
0x180002a39  jz      short loc_180002A41
0x180002a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002a40  nop
0x180002a41  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180002a46  jnz     short loc_180002A69
0x180002a48  mov     rcx, [rbp+1400h+var_40]
0x180002a4f  xor     rcx, rsp; StackCookie
0x180002a52  call    __security_check_cookie
0x180002a57  add     rsp, 14D0h
0x180002a5e  pop     r15
0x180002a60  pop     r14
0x180002a62  pop     r12
0x180002a64  pop     rdi
0x180002a65  pop     rsi
0x180002a66  pop     rbx
0x180002a67  pop     rbp
0x180002a68  retn
0x180002a69  lea     rcx, [rsp+1500h+var_14E0]; this
0x180002a6e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180002a74  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
