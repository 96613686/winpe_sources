# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006360`
- end: `0x1800065d9`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800060dc`

## callees

- `0x1800044b8`
- `0x180006360`
- `0x180007bb4`
- `0x180008400`
- `0x1800089d0`
- `0x180009e70`
- `0x1800633f0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006419`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006419`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000651c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000651c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800065a6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800065a6`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180006360  mov     [rsp-8+arg_18], rbx
0x180006365  push    rbp
0x180006366  push    rsi
0x180006367  push    rdi
0x180006368  push    r12
0x18000636a  push    r13
0x18000636c  push    r14
0x18000636e  push    r15
0x180006370  lea     rbp, [rsp-13C0h]
0x180006378  mov     eax, 14C0h
0x18000637d  call    _alloca_probe
0x180006382  sub     rsp, rax
0x180006385  mov     r14, r8
0x180006388  mov     esi, edx
0x18000638a  mov     rdi, rcx
0x18000638d  mov     r15, [rbp+13F0h+arg_28]
0x180006394  xor     edx, edx; Val
0x180006396  mov     r8d, 98h; Size
0x18000639c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800063a1  call    memset_0
0x1800063a6  nop
0x1800063a7  xor     r13d, r13d
0x1800063aa  mov     [rbp+13F0h+OutputString], r13w
0x1800063b2  mov     [rbp+13F0h+var_1430], r13b
0x1800063b6  mov     rbx, [rbp+13F0h+arg_30]
0x1800063bd  mov     ecx, [rbx]; this
0x1800063bf  mov     [rsp+14F0h+var_14C8], ecx
0x1800063c3  mov     eax, [rbx+4]
0x1800063c6  mov     [rsp+14F0h+var_14C4], eax
0x1800063ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800063cf  mov     r12d, eax
0x1800063d2  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800063da  mov     ecx, r13d
0x1800063dd  lea     eax, [r13+8]
0x1800063e1  cmp     dword ptr [rbx+8], 1
0x1800063e5  cmovz   ecx, eax
0x1800063e8  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800063ec  lea     ecx, [rax-7]
0x1800063ef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800063f7  inc     ecx
0x1800063f9  mov     [rsp+14F0h+var_14C0], ecx
0x1800063fd  mov     rcx, [rbp+13F0h+arg_38]
0x180006404  test    rcx, rcx
0x180006407  jz      short loc_180006414
0x180006409  cmp     [rcx], r13w
0x18000640d  mov     [rsp+14F0h+var_14B8], rcx
0x180006412  jnz     short loc_180006419
0x180006414  mov     [rsp+14F0h+var_14B8], r13
0x180006419  call    cs:__imp_GetCurrentThreadId
0x18000641f  mov     [rsp+14F0h+var_14B0], eax
0x180006423  mov     [rsp+14F0h+var_1498], r14
0x180006428  mov     [rsp+14F0h+var_1490], esi
0x18000642c  mov     [rsp+14F0h+var_148C], r12d
0x180006431  mov     [rsp+14F0h+var_14A8], r13
0x180006436  mov     [rsp+14F0h+var_14A0], r13
0x18000643b  mov     [rbp+13F0h+var_1448], r15
0x18000643f  mov     [rbp+13F0h+var_1440], rdi
0x180006443  mov     [rsp+14F0h+var_1488], r13
0x180006448  xorps   xmm0, xmm0
0x18000644b  xor     eax, eax
0x18000644d  movups  [rbp+13F0h+var_1468], xmm0
0x180006451  mov     [rbp+13F0h+var_1458], rax
0x180006455  xorps   xmm1, xmm1
0x180006458  movups  [rsp+14F0h+var_1480], xmm1
0x18000645d  mov     [rbp+13F0h+var_1470], rax
0x180006461  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006468  test    rax, rax
0x18000646b  jz      short loc_180006478
0x18000646d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006472  mov     [rbp+13F0h+var_1450], rax
0x180006476  jmp     short loc_18000647C
0x180006478  mov     [rbp+13F0h+var_1450], r13
0x18000647c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006483  test    rax, rax
0x180006486  jz      short loc_180006492
0x180006488  lea     rcx, [rsp+14F0h+var_14D0]
0x18000648d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006492  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006499  test    rax, rax
0x18000649c  jz      short loc_1800064B2
0x18000649e  mov     r8d, 400h
0x1800064a4  lea     rdx, [rbp+13F0h+var_1430]
0x1800064a8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800064ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064b2  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800064b9  test    rax, rax
0x1800064bc  jz      short loc_1800064C8
0x1800064be  lea     rcx, [rsp+14F0h+var_14D0]
0x1800064c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800064cf  test    rax, rax
0x1800064d2  jz      short loc_1800064E5
0x1800064d4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800064d9  jnz     short loc_1800064E5
0x1800064db  lea     rcx, [rsp+14F0h+var_14D0]
0x1800064e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064e5  cmp     [rsp+14F0h+var_14C8], r13d
0x1800064ea  jl      short loc_1800064FE
0x1800064ec  mov     ecx, 8000FFFFh; this
0x1800064f1  mov     [rsp+14F0h+var_14C8], ecx
0x1800064f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800064fa  mov     [rsp+14F0h+var_14C4], eax
0x1800064fe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006505  jnz     short loc_180006526
0x180006507  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000650e  test    rax, rax
0x180006511  jz      short loc_18000651C
0x180006513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006518  test    al, al
0x18000651a  jmp     short loc_180006524
0x18000651c  call    cs:__imp_IsDebuggerPresent
0x180006522  test    eax, eax
0x180006524  jz      short loc_18000652D
0x180006526  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000652b  jz      short loc_180006553
0x18000652d  mov     rax, cs:g_pfnResultLoggingCallback
0x180006534  test    rax, rax
0x180006537  jz      short loc_1800065AC
0x180006539  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006540  jnz     short loc_1800065AC
0x180006542  xor     r8d, r8d
0x180006545  xor     edx, edx
0x180006547  lea     rcx, [rsp+14F0h+var_14D0]
0x18000654c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006551  jmp     short loc_1800065AC
0x180006553  mov     ebx, 800h
0x180006558  mov     rax, cs:g_pfnResultLoggingCallback
0x18000655f  test    rax, rax
0x180006562  jz      short loc_180006581
0x180006564  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000656b  jnz     short loc_180006581
0x18000656d  mov     r8d, ebx
0x180006570  lea     rdx, [rbp+13F0h+OutputString]
0x180006577  lea     rcx, [rsp+14F0h+var_14D0]
0x18000657c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006581  cmp     [rbp+13F0h+OutputString], r13w
0x180006589  jnz     short loc_18000659F
0x18000658b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006590  mov     rdx, rbx; unsigned __int16 *
0x180006593  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000659a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000659f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800065a6  call    cs:__imp_OutputDebugStringW
0x1800065ac  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800065b1  jnz     short loc_1800065BC
0x1800065b3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1800065ba  jz      short loc_1800065CE
0x1800065bc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800065c3  test    rax, rax
0x1800065c6  jz      short loc_1800065CE
0x1800065c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065cd  nop
0x1800065ce  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800065d3  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
