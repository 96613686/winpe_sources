# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800185c8`
- end: `0x180018886`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `702`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180018540`

## callees

- `0x1800035cc`
- `0x18000be84`
- `0x18000d820`
- `0x18000fb24`
- `0x18001027c`
- `0x180010464`
- `0x1800185c8`
- `0x180028a60`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018671`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180018671`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018772`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180018772`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180018814`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180018814`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x1800185c8  mov     [rsp-8+arg_18], rbx
0x1800185cd  push    rbp
0x1800185ce  push    rsi
0x1800185cf  push    rdi
0x1800185d0  push    r12
0x1800185d2  push    r13
0x1800185d4  push    r14
0x1800185d6  push    r15
0x1800185d8  lea     rbp, [rsp-13C0h]
0x1800185e0  mov     eax, 14C0h
0x1800185e5  call    _alloca_probe
0x1800185ea  sub     rsp, rax
0x1800185ed  mov     r14, r8
0x1800185f0  mov     esi, edx
0x1800185f2  mov     r15, rcx
0x1800185f5  mov     rdi, [rbp+13F0h+arg_28]
0x1800185fc  xor     r13d, r13d
0x1800185ff  cmp     cs:g_pfnThrowPlatformException, r13
0x180018606  setnz   r12b
0x18001860a  xor     edx, edx; Val
0x18001860c  mov     r8d, 98h; Size
0x180018612  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180018617  call    memset_0
0x18001861c  nop
0x18001861d  mov     [rbp+13F0h+OutputString], r13w
0x180018625  mov     [rbp+13F0h+var_1430], r13b
0x180018629  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180018630  mov     ecx, [rdx]; this
0x180018632  mov     [rsp+14F0h+var_14C8], ecx
0x180018636  mov     eax, [rdx+4]
0x180018639  mov     [rsp+14F0h+var_14C4], eax
0x18001863d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180018642  mov     ebx, eax
0x180018644  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180018649  mov     ecx, r13d
0x18001864c  lea     eax, [r13+8]
0x180018650  cmp     dword ptr [rdx+8], 1
0x180018654  cmovz   ecx, eax
0x180018657  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001865b  lea     ecx, [rax-7]
0x18001865e  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x180018666  inc     ecx
0x180018668  mov     [rsp+14F0h+var_14C0], ecx
0x18001866c  mov     [rsp+14F0h+var_14B8], r13
0x180018671  call    cs:__imp_GetCurrentThreadId
0x180018678  nop     dword ptr [rax+rax+00h]
0x18001867d  mov     [rsp+14F0h+var_14B0], eax
0x180018681  mov     [rsp+14F0h+var_1498], r14
0x180018686  mov     [rsp+14F0h+var_1490], esi
0x18001868a  mov     [rsp+14F0h+var_148C], ebx
0x18001868e  mov     [rsp+14F0h+var_14A8], r13
0x180018693  mov     [rsp+14F0h+var_14A0], r13
0x180018698  mov     [rbp+13F0h+var_1448], rdi
0x18001869c  mov     [rbp+13F0h+var_1440], r15
0x1800186a0  mov     [rsp+14F0h+var_1488], r13
0x1800186a5  xorps   xmm0, xmm0
0x1800186a8  xor     eax, eax
0x1800186aa  movups  [rbp+13F0h+var_1468], xmm0
0x1800186ae  mov     [rbp+13F0h+var_1458], rax
0x1800186b2  xorps   xmm1, xmm1
0x1800186b5  movups  [rsp+14F0h+var_1480], xmm1
0x1800186ba  mov     [rbp+13F0h+var_1470], rax
0x1800186be  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800186c5  test    rax, rax
0x1800186c8  jz      short loc_1800186D5
0x1800186ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186cf  mov     [rbp+13F0h+var_1450], rax
0x1800186d3  jmp     short loc_1800186D9
0x1800186d5  mov     [rbp+13F0h+var_1450], r13
0x1800186d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800186e0  test    rax, rax
0x1800186e3  jz      short loc_1800186EF
0x1800186e5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800186ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800186ef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800186f6  test    rax, rax
0x1800186f9  jz      short loc_18001870F
0x1800186fb  mov     r8d, 400h
0x180018701  lea     rdx, [rbp+13F0h+var_1430]
0x180018705  lea     rcx, [rsp+14F0h+var_14D0]
0x18001870a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001870f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180018716  test    rax, rax
0x180018719  jz      short loc_180018725
0x18001871b  lea     rcx, [rsp+14F0h+var_14D0]
0x180018720  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018725  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001872c  test    rax, rax
0x18001872f  jz      short loc_180018747
0x180018731  test    r12b, r12b
0x180018734  jnz     short loc_180018747
0x180018736  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001873b  jnz     short loc_180018747
0x18001873d  lea     rcx, [rsp+14F0h+var_14D0]
0x180018742  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018747  cmp     [rsp+14F0h+var_14C8], r13d
0x18001874c  jl      short loc_180018754
0x18001874e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180018754  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001875b  jnz     short loc_180018782
0x18001875d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180018764  test    rax, rax
0x180018767  jz      short loc_180018772
0x180018769  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001876e  test    al, al
0x180018770  jmp     short loc_180018780
0x180018772  call    cs:__imp_IsDebuggerPresent
0x180018779  nop     dword ptr [rax+rax+00h]
0x18001877e  test    eax, eax
0x180018780  jz      short loc_18001878B
0x180018782  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180018787  mov     bl, 1
0x180018789  jz      short loc_18001878E
0x18001878b  mov     bl, r13b
0x18001878e  test    r12b, r12b
0x180018791  jnz     short loc_1800187BD
0x180018793  test    bl, bl
0x180018795  jnz     short loc_1800187BD
0x180018797  mov     rax, cs:g_pfnResultLoggingCallback
0x18001879e  test    rax, rax
0x1800187a1  jz      short loc_180018820
0x1800187a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800187aa  jnz     short loc_180018820
0x1800187ac  xor     r8d, r8d
0x1800187af  xor     edx, edx
0x1800187b1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800187b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187bb  jmp     short loc_180018820
0x1800187bd  mov     edi, 800h
0x1800187c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800187c9  test    rax, rax
0x1800187cc  jz      short loc_1800187EB
0x1800187ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800187d5  jnz     short loc_1800187EB
0x1800187d7  mov     r8d, edi
0x1800187da  lea     rdx, [rbp+13F0h+OutputString]
0x1800187e1  lea     rcx, [rsp+14F0h+var_14D0]
0x1800187e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800187eb  cmp     [rbp+13F0h+OutputString], r13w
0x1800187f3  jnz     short loc_180018809
0x1800187f5  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800187fa  mov     rdx, rdi; unsigned __int16 *
0x1800187fd  lea     rcx, [rbp+13F0h+OutputString]; this
0x180018804  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180018809  test    bl, bl
0x18001880b  jz      short loc_180018820
0x18001880d  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180018814  call    cs:__imp_OutputDebugStringW
0x18001881b  nop     dword ptr [rax+rax+00h]
0x180018820  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180018825  jnz     short loc_180018830
0x180018827  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001882e  jz      short loc_180018842
0x180018830  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180018837  test    rax, rax
0x18001883a  jz      short loc_180018842
0x18001883c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018841  nop
0x180018842  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180018847  jz      short loc_180018854
0x180018849  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001884e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180018854  test    r12b, r12b
0x180018857  jz      short loc_180018871
0x180018859  lea     rdx, [rbp+13F0h+OutputString]
0x180018860  lea     rcx, [rsp+14F0h+var_14D0]
0x180018865  mov     rax, cs:g_pfnThrowPlatformException
0x18001886c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180018871  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180018876  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18001887b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180018880  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
