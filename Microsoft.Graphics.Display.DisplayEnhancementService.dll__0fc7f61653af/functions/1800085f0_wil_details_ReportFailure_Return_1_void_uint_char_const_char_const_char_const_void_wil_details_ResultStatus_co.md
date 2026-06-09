# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800085f0`
- end: `0x180008896`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180007dd0`

## callees

- `0x180005860`
- `0x180006440`
- `0x1800085f0`
- `0x18000b0f4`
- `0x18000d62c`
- `0x18000f3e8`
- `0x18000f8a0`
- `0x1800dd610`
- `0x1800ed010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086b6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800086b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008835`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008835`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800087ab`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800087ab`

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
0x1800085f0  push    rbp
0x1800085f2  push    rbx
0x1800085f3  push    rsi
0x1800085f4  push    rdi
0x1800085f5  push    r12
0x1800085f7  push    r14
0x1800085f9  push    r15
0x1800085fb  lea     rbp, [rsp-13D0h]
0x180008603  mov     eax, 14D0h
0x180008608  call    _alloca_probe
0x18000860d  sub     rsp, rax
0x180008610  mov     rax, cs:__security_cookie
0x180008617  xor     rax, rsp
0x18000861a  mov     [rbp+1400h+var_40], rax
0x180008621  mov     rsi, r8
0x180008624  mov     edi, edx
0x180008626  mov     rbx, rcx
0x180008629  mov     r14, [rbp+1400h+arg_28]
0x180008630  xor     edx, edx; Val
0x180008632  mov     r8d, 98h; Size
0x180008638  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000863d  call    memset_0
0x180008642  nop
0x180008643  xor     r12d, r12d
0x180008646  mov     [rbp+1400h+OutputString], r12w
0x18000864e  mov     [rbp+1400h+var_1440], r12b
0x180008652  mov     rdx, [rbp+1400h+arg_30]; int
0x180008659  mov     ecx, [rdx]; this
0x18000865b  mov     [rsp+1500h+var_14D8], ecx
0x18000865f  mov     eax, [rdx+4]
0x180008662  mov     [rsp+1500h+var_14D4], eax
0x180008666  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000866b  mov     r15d, eax
0x18000866e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180008676  mov     ecx, r12d
0x180008679  lea     eax, [r12+8]
0x18000867e  cmp     dword ptr [rdx+8], 1
0x180008682  cmovz   ecx, eax
0x180008685  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180008689  lea     ecx, [rax-7]
0x18000868c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008694  inc     ecx
0x180008696  mov     [rsp+1500h+var_14D0], ecx
0x18000869a  mov     rcx, [rbp+1400h+arg_38]
0x1800086a1  test    rcx, rcx
0x1800086a4  jz      short loc_1800086B1
0x1800086a6  cmp     [rcx], r12w
0x1800086aa  mov     [rsp+1500h+var_14C8], rcx
0x1800086af  jnz     short loc_1800086B6
0x1800086b1  mov     [rsp+1500h+var_14C8], r12
0x1800086b6  call    cs:__imp_GetCurrentThreadId
0x1800086bc  mov     [rsp+1500h+var_14C0], eax
0x1800086c0  mov     [rsp+1500h+var_14A8], rsi
0x1800086c5  mov     [rsp+1500h+var_14A0], edi
0x1800086c9  mov     [rsp+1500h+var_149C], r15d
0x1800086ce  mov     [rsp+1500h+var_14B8], r12
0x1800086d3  mov     [rsp+1500h+var_14B0], r12
0x1800086d8  mov     [rbp+1400h+var_1458], r14
0x1800086dc  mov     [rbp+1400h+var_1450], rbx
0x1800086e0  mov     [rsp+1500h+var_1498], r12
0x1800086e5  xorps   xmm0, xmm0
0x1800086e8  xor     eax, eax
0x1800086ea  movups  [rbp+1400h+var_1478], xmm0
0x1800086ee  mov     [rbp+1400h+var_1468], rax
0x1800086f2  xorps   xmm1, xmm1
0x1800086f5  movups  [rsp+1500h+var_1490], xmm1
0x1800086fa  mov     [rbp+1400h+var_1480], rax
0x1800086fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008705  test    rax, rax
0x180008708  jz      short loc_180008715
0x18000870a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870f  mov     [rbp+1400h+var_1460], rax
0x180008713  jmp     short loc_180008719
0x180008715  mov     [rbp+1400h+var_1460], r12
0x180008719  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008720  test    rax, rax
0x180008723  jz      short loc_18000872F
0x180008725  lea     rcx, [rsp+1500h+var_14E0]
0x18000872a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000872f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008736  test    rax, rax
0x180008739  jz      short loc_18000874F
0x18000873b  mov     r8d, 400h
0x180008741  lea     rdx, [rbp+1400h+var_1440]
0x180008745  lea     rcx, [rsp+1500h+var_14E0]
0x18000874a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000874f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008756  test    rax, rax
0x180008759  jz      short loc_180008765
0x18000875b  lea     rcx, [rsp+1500h+var_14E0]
0x180008760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008765  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000876c  test    rax, rax
0x18000876f  jz      short loc_180008782
0x180008771  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180008776  jnz     short loc_180008782
0x180008778  lea     rcx, [rsp+1500h+var_14E0]
0x18000877d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008782  cmp     [rsp+1500h+var_14D8], r12d
0x180008787  jge     loc_180008890
0x18000878d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180008794  jnz     short loc_1800087B5
0x180008796  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000879d  test    rax, rax
0x1800087a0  jz      short loc_1800087AB
0x1800087a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087a7  test    al, al
0x1800087a9  jmp     short loc_1800087B3
0x1800087ab  call    cs:__imp_IsDebuggerPresent
0x1800087b1  test    eax, eax
0x1800087b3  jz      short loc_1800087BC
0x1800087b5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800087ba  jz      short loc_1800087E2
0x1800087bc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800087c3  test    rax, rax
0x1800087c6  jz      short loc_18000883B
0x1800087c8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800087cf  jnz     short loc_18000883B
0x1800087d1  xor     r8d, r8d
0x1800087d4  xor     edx, edx
0x1800087d6  lea     rcx, [rsp+1500h+var_14E0]
0x1800087db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800087e0  jmp     short loc_18000883B
0x1800087e2  mov     ebx, 800h
0x1800087e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800087ee  test    rax, rax
0x1800087f1  jz      short loc_180008810
0x1800087f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800087fa  jnz     short loc_180008810
0x1800087fc  mov     r8d, ebx
0x1800087ff  lea     rdx, [rbp+1400h+OutputString]
0x180008806  lea     rcx, [rsp+1500h+var_14E0]
0x18000880b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008810  cmp     [rbp+1400h+OutputString], r12w
0x180008818  jnz     short loc_18000882E
0x18000881a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000881f  mov     rdx, rbx; unsigned __int16 *
0x180008822  lea     rcx, [rbp+1400h+OutputString]; this
0x180008829  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000882e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180008835  call    cs:__imp_OutputDebugStringW
0x18000883b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180008840  jnz     short loc_18000884B
0x180008842  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180008849  jz      short loc_18000885D
0x18000884b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008852  test    rax, rax
0x180008855  jz      short loc_18000885D
0x180008857  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000885c  nop
0x18000885d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180008862  jnz     short loc_180008885
0x180008864  mov     rcx, [rbp+1400h+var_40]
0x18000886b  xor     rcx, rsp; StackCookie
0x18000886e  call    __security_check_cookie
0x180008873  add     rsp, 14D0h
0x18000887a  pop     r15
0x18000887c  pop     r14
0x18000887e  pop     r12
0x180008880  pop     rdi
0x180008881  pop     rsi
0x180008882  pop     rbx
0x180008883  pop     rbp
0x180008884  retn
0x180008885  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000888a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180008890  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
