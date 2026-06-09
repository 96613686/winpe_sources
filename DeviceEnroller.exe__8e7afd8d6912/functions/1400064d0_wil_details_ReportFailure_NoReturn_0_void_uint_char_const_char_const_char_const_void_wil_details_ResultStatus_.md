# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1400064d0`
- end: `0x14000677c`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140005f70`

## callees

- `0x140004e28`
- `0x1400064d0`
- `0x140007f74`
- `0x1400091a0`
- `0x14000a188`
- `0x14000a510`
- `0x14000a698`
- `0x140059180`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006579`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006579`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006674`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006674`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006710`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006710`

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
0x1400064d0  mov     [rsp-8+arg_18], rbx
0x1400064d5  push    rbp
0x1400064d6  push    rsi
0x1400064d7  push    rdi
0x1400064d8  push    r12
0x1400064da  push    r13
0x1400064dc  push    r14
0x1400064de  push    r15
0x1400064e0  lea     rbp, [rsp-13C0h]
0x1400064e8  mov     eax, 14C0h
0x1400064ed  call    _alloca_probe
0x1400064f2  sub     rsp, rax
0x1400064f5  mov     r14, r8
0x1400064f8  mov     esi, edx
0x1400064fa  mov     r15, rcx
0x1400064fd  mov     rdi, [rbp+13F0h+arg_28]
0x140006504  xor     r13d, r13d
0x140006507  cmp     cs:g_pfnThrowPlatformException, r13
0x14000650e  setnz   r12b
0x140006512  xor     edx, edx; Val
0x140006514  mov     r8d, 98h; Size
0x14000651a  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x14000651f  call    memset_0
0x140006524  nop
0x140006525  mov     [rbp+13F0h+OutputString], r13w
0x14000652d  mov     [rbp+13F0h+var_1430], r13b
0x140006531  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x140006538  mov     ecx, [rdx]; this
0x14000653a  mov     [rsp+14F0h+var_14C8], ecx
0x14000653e  mov     eax, [rdx+4]
0x140006541  mov     [rsp+14F0h+var_14C4], eax
0x140006545  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000654a  mov     ebx, eax
0x14000654c  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x140006551  mov     ecx, r13d
0x140006554  lea     eax, [r13+8]
0x140006558  cmp     dword ptr [rdx+8], 1
0x14000655c  cmovz   ecx, eax
0x14000655f  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140006563  lea     ecx, [rax-7]
0x140006566  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000656e  inc     ecx
0x140006570  mov     [rsp+14F0h+var_14C0], ecx
0x140006574  mov     [rsp+14F0h+var_14B8], r13
0x140006579  call    cs:__imp_GetCurrentThreadId
0x14000657f  mov     [rsp+14F0h+var_14B0], eax
0x140006583  mov     [rsp+14F0h+var_1498], r14
0x140006588  mov     [rsp+14F0h+var_1490], esi
0x14000658c  mov     [rsp+14F0h+var_148C], ebx
0x140006590  mov     [rsp+14F0h+var_14A8], r13
0x140006595  mov     [rsp+14F0h+var_14A0], r13
0x14000659a  mov     [rbp+13F0h+var_1448], rdi
0x14000659e  mov     [rbp+13F0h+var_1440], r15
0x1400065a2  mov     [rsp+14F0h+var_1488], r13
0x1400065a7  xorps   xmm0, xmm0
0x1400065aa  xor     eax, eax
0x1400065ac  movups  [rbp+13F0h+var_1468], xmm0
0x1400065b0  mov     [rbp+13F0h+var_1458], rax
0x1400065b4  xorps   xmm1, xmm1
0x1400065b7  movups  [rsp+14F0h+var_1480], xmm1
0x1400065bc  mov     [rbp+13F0h+var_1470], rax
0x1400065c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400065c7  test    rax, rax
0x1400065ca  jz      short loc_1400065D7
0x1400065cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065d1  mov     [rbp+13F0h+var_1450], rax
0x1400065d5  jmp     short loc_1400065DB
0x1400065d7  mov     [rbp+13F0h+var_1450], r13
0x1400065db  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400065e2  test    rax, rax
0x1400065e5  jz      short loc_1400065F1
0x1400065e7  lea     rcx, [rsp+14F0h+var_14D0]
0x1400065ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400065f8  test    rax, rax
0x1400065fb  jz      short loc_140006611
0x1400065fd  mov     r8d, 400h
0x140006603  lea     rdx, [rbp+13F0h+var_1430]
0x140006607  lea     rcx, [rsp+14F0h+var_14D0]
0x14000660c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006611  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006618  test    rax, rax
0x14000661b  jz      short loc_140006627
0x14000661d  lea     rcx, [rsp+14F0h+var_14D0]
0x140006622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006627  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000662e  test    rax, rax
0x140006631  jz      short loc_140006649
0x140006633  test    r12b, r12b
0x140006636  jnz     short loc_140006649
0x140006638  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000663d  jnz     short loc_140006649
0x14000663f  lea     rcx, [rsp+14F0h+var_14D0]
0x140006644  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006649  cmp     [rsp+14F0h+var_14C8], r13d
0x14000664e  jl      short loc_140006656
0x140006650  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x140006656  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000665d  jnz     short loc_14000667E
0x14000665f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006666  test    rax, rax
0x140006669  jz      short loc_140006674
0x14000666b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006670  test    al, al
0x140006672  jmp     short loc_14000667C
0x140006674  call    cs:__imp_IsDebuggerPresent
0x14000667a  test    eax, eax
0x14000667c  jz      short loc_140006687
0x14000667e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140006683  mov     bl, 1
0x140006685  jz      short loc_14000668A
0x140006687  mov     bl, r13b
0x14000668a  test    r12b, r12b
0x14000668d  jnz     short loc_1400066B9
0x14000668f  test    bl, bl
0x140006691  jnz     short loc_1400066B9
0x140006693  mov     rax, cs:g_pfnResultLoggingCallback
0x14000669a  test    rax, rax
0x14000669d  jz      short loc_140006716
0x14000669f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400066a6  jnz     short loc_140006716
0x1400066a8  xor     r8d, r8d
0x1400066ab  xor     edx, edx
0x1400066ad  lea     rcx, [rsp+14F0h+var_14D0]
0x1400066b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066b7  jmp     short loc_140006716
0x1400066b9  mov     edi, 800h
0x1400066be  mov     rax, cs:g_pfnResultLoggingCallback
0x1400066c5  test    rax, rax
0x1400066c8  jz      short loc_1400066E7
0x1400066ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400066d1  jnz     short loc_1400066E7
0x1400066d3  mov     r8d, edi
0x1400066d6  lea     rdx, [rbp+13F0h+OutputString]
0x1400066dd  lea     rcx, [rsp+14F0h+var_14D0]
0x1400066e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066e7  cmp     [rbp+13F0h+OutputString], r13w
0x1400066ef  jnz     short loc_140006705
0x1400066f1  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400066f6  mov     rdx, rdi; unsigned __int16 *
0x1400066f9  lea     rcx, [rbp+13F0h+OutputString]; this
0x140006700  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006705  test    bl, bl
0x140006707  jz      short loc_140006716
0x140006709  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140006710  call    cs:__imp_OutputDebugStringW
0x140006716  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000671b  jnz     short loc_140006726
0x14000671d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140006724  jz      short loc_140006738
0x140006726  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000672d  test    rax, rax
0x140006730  jz      short loc_140006738
0x140006732  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006737  nop
0x140006738  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x14000673d  jz      short loc_14000674A
0x14000673f  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006744  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000674a  test    r12b, r12b
0x14000674d  jz      short loc_140006767
0x14000674f  lea     rdx, [rbp+13F0h+OutputString]
0x140006756  lea     rcx, [rsp+14F0h+var_14D0]
0x14000675b  mov     rax, cs:g_pfnThrowPlatformException
0x140006762  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006767  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000676c  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x140006771  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140006776  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
