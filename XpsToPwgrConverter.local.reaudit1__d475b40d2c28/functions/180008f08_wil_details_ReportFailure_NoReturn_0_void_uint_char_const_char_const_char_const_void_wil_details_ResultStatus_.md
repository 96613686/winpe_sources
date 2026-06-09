# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180008f08`
- end: `0x1800091cd`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `709`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008e6c`

## callees

- `0x180002194`
- `0x1800049e4`
- `0x180005d94`
- `0x180007bd0`
- `0x180008230`
- `0x1800083fc`
- `0x180008f08`
- `0x18000f4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fc9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008fc9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800090c5`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800090c5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009161`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009161`

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
        int *a7,
        _WORD *a8)
{
  bool v11; // di
  int v12; // r12d
  int v13; // ecx
  __int64 v14; // rdx
  const struct wil::FailureInfo *v15; // rdx
  wil::details::in1diag3 *v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  char v19; // bl
  const struct wil::FailureInfo *v20; // rdx
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v11 = g_pfnThrowPlatformException != 0;
  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v23 = *a7;
  v24 = a7[1];
  v12 = wil::details::RecordException((wil::details *)(unsigned int)v23, (int)a7);
  v21 = 0;
  v13 = 0;
  if ( *(_DWORD *)(v14 + 8) == 1 )
    v13 = 8;
  v22 = v13;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v18 = *a8 == 0, v26 = a8, v18) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v31 = a2;
  v32 = v12;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v37 = 0;
  v34 = 0;
  v35 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && !v11 && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v16);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v19 = 1, (v22 & 2) != 0) )
  {
    v19 = 0;
  }
  if ( v11 || v19 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048, v17);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v21, v17);
    if ( v19 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v21, 0, 0, v17);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v16);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v15);
  if ( v11 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v21, OutputString);
  wil::ThrowResultException((wil *)&v21, v15);
  wil::details::WilFailFast((wil::details *)&v21, v20);
}

```

## disassembly

```asm
0x180008f08  mov     [rsp-8+arg_18], rbx
0x180008f0d  push    rbp
0x180008f0e  push    rsi
0x180008f0f  push    rdi
0x180008f10  push    r12
0x180008f12  push    r13
0x180008f14  push    r14
0x180008f16  push    r15
0x180008f18  lea     rbp, [rsp-13C0h]
0x180008f20  mov     eax, 14C0h
0x180008f25  call    _alloca_probe
0x180008f2a  sub     rsp, rax
0x180008f2d  mov     r14, r8
0x180008f30  mov     esi, edx
0x180008f32  mov     rbx, rcx
0x180008f35  mov     r15, [rbp+13F0h+arg_28]
0x180008f3c  xor     r13d, r13d
0x180008f3f  cmp     cs:g_pfnThrowPlatformException, r13
0x180008f46  setnz   dil
0x180008f4a  xor     edx, edx; Val
0x180008f4c  mov     r8d, 98h; Size
0x180008f52  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180008f57  call    memset_0
0x180008f5c  nop
0x180008f5d  mov     [rbp+13F0h+OutputString], r13w
0x180008f65  mov     [rbp+13F0h+var_1430], r13b
0x180008f69  mov     rdx, [rbp+13F0h+arg_30]; int
0x180008f70  mov     ecx, [rdx]; this
0x180008f72  mov     [rsp+14F0h+var_14C8], ecx
0x180008f76  mov     eax, [rdx+4]
0x180008f79  mov     [rsp+14F0h+var_14C4], eax
0x180008f7d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008f82  mov     r12d, eax
0x180008f85  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x180008f8a  mov     ecx, r13d
0x180008f8d  lea     eax, [r13+8]
0x180008f91  cmp     dword ptr [rdx+8], 1
0x180008f95  cmovz   ecx, eax
0x180008f98  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180008f9c  lea     ecx, [rax-7]
0x180008f9f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008fa7  inc     ecx
0x180008fa9  mov     [rsp+14F0h+var_14C0], ecx
0x180008fad  mov     rcx, [rbp+13F0h+arg_38]
0x180008fb4  test    rcx, rcx
0x180008fb7  jz      short loc_180008FC4
0x180008fb9  cmp     [rcx], r13w
0x180008fbd  mov     [rsp+14F0h+var_14B8], rcx
0x180008fc2  jnz     short loc_180008FC9
0x180008fc4  mov     [rsp+14F0h+var_14B8], r13
0x180008fc9  call    cs:__imp_GetCurrentThreadId
0x180008fcf  mov     [rsp+14F0h+var_14B0], eax
0x180008fd3  mov     [rsp+14F0h+var_1498], r14
0x180008fd8  mov     [rsp+14F0h+var_1490], esi
0x180008fdc  mov     [rsp+14F0h+var_148C], r12d
0x180008fe1  mov     [rsp+14F0h+var_14A8], r13
0x180008fe6  mov     [rsp+14F0h+var_14A0], r13
0x180008feb  mov     [rbp+13F0h+var_1448], r15
0x180008fef  mov     [rbp+13F0h+var_1440], rbx
0x180008ff3  mov     [rsp+14F0h+var_1488], r13
0x180008ff8  xorps   xmm0, xmm0
0x180008ffb  xor     eax, eax
0x180008ffd  movups  [rbp+13F0h+var_1468], xmm0
0x180009001  mov     [rbp+13F0h+var_1458], rax
0x180009005  xorps   xmm1, xmm1
0x180009008  movups  [rsp+14F0h+var_1480], xmm1
0x18000900d  mov     [rbp+13F0h+var_1470], rax
0x180009011  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009018  test    rax, rax
0x18000901b  jz      short loc_180009028
0x18000901d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009022  mov     [rbp+13F0h+var_1450], rax
0x180009026  jmp     short loc_18000902C
0x180009028  mov     [rbp+13F0h+var_1450], r13
0x18000902c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009033  test    rax, rax
0x180009036  jz      short loc_180009042
0x180009038  lea     rcx, [rsp+14F0h+var_14D0]
0x18000903d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009042  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009049  test    rax, rax
0x18000904c  jz      short loc_180009062
0x18000904e  mov     r8d, 400h
0x180009054  lea     rdx, [rbp+13F0h+var_1430]
0x180009058  lea     rcx, [rsp+14F0h+var_14D0]
0x18000905d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009062  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009069  test    rax, rax
0x18000906c  jz      short loc_180009078
0x18000906e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009073  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009078  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000907f  test    rax, rax
0x180009082  jz      short loc_18000909A
0x180009084  test    dil, dil
0x180009087  jnz     short loc_18000909A
0x180009089  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000908e  jnz     short loc_18000909A
0x180009090  lea     rcx, [rsp+14F0h+var_14D0]
0x180009095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909a  cmp     [rsp+14F0h+var_14C8], r13d
0x18000909f  jl      short loc_1800090A7
0x1800090a1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800090a7  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800090ae  jnz     short loc_1800090CF
0x1800090b0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800090b7  test    rax, rax
0x1800090ba  jz      short loc_1800090C5
0x1800090bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090c1  test    al, al
0x1800090c3  jmp     short loc_1800090CD
0x1800090c5  call    cs:__imp_IsDebuggerPresent
0x1800090cb  test    eax, eax
0x1800090cd  jz      short loc_1800090D8
0x1800090cf  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800090d4  mov     bl, 1
0x1800090d6  jz      short loc_1800090DB
0x1800090d8  mov     bl, r13b
0x1800090db  test    dil, dil
0x1800090de  jnz     short loc_18000910A
0x1800090e0  test    bl, bl
0x1800090e2  jnz     short loc_18000910A
0x1800090e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090eb  test    rax, rax
0x1800090ee  jz      short loc_180009167
0x1800090f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800090f7  jnz     short loc_180009167
0x1800090f9  xor     r8d, r8d
0x1800090fc  xor     edx, edx
0x1800090fe  lea     rcx, [rsp+14F0h+var_14D0]
0x180009103  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009108  jmp     short loc_180009167
0x18000910a  mov     esi, 800h
0x18000910f  mov     rax, cs:g_pfnResultLoggingCallback
0x180009116  test    rax, rax
0x180009119  jz      short loc_180009138
0x18000911b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180009122  jnz     short loc_180009138
0x180009124  mov     r8d, esi
0x180009127  lea     rdx, [rbp+13F0h+OutputString]
0x18000912e  lea     rcx, [rsp+14F0h+var_14D0]
0x180009133  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009138  cmp     [rbp+13F0h+OutputString], r13w
0x180009140  jnz     short loc_180009156
0x180009142  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180009147  mov     rdx, rsi; unsigned __int16 *
0x18000914a  lea     rcx, [rbp+13F0h+OutputString]; this
0x180009151  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009156  test    bl, bl
0x180009158  jz      short loc_180009167
0x18000915a  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180009161  call    cs:__imp_OutputDebugStringW
0x180009167  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000916c  jnz     short loc_180009177
0x18000916e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180009175  jz      short loc_180009189
0x180009177  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000917e  test    rax, rax
0x180009181  jz      short loc_180009189
0x180009183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009188  nop
0x180009189  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000918e  jz      short loc_18000919B
0x180009190  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180009195  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000919b  test    dil, dil
0x18000919e  jz      short loc_1800091B8
0x1800091a0  lea     rdx, [rbp+13F0h+OutputString]
0x1800091a7  lea     rcx, [rsp+14F0h+var_14D0]
0x1800091ac  mov     rax, cs:g_pfnThrowPlatformException
0x1800091b3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091b8  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800091bd  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x1800091c2  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800091c7  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
