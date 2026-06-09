# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800034a0`
- end: `0x180003746`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002f30`

## callees

- `0x1800034a0`
- `0x180004994`
- `0x180005b90`
- `0x180006f10`
- `0x1800070e4`
- `0x18000c4f2`
- `0x18000c530`
- `0x18000c5f0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003566`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003566`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000365b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000365b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800036e5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800036e5`

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
0x1800034a0  push    rbp
0x1800034a2  push    rbx
0x1800034a3  push    rsi
0x1800034a4  push    rdi
0x1800034a5  push    r12
0x1800034a7  push    r14
0x1800034a9  push    r15
0x1800034ab  lea     rbp, [rsp-13D0h]
0x1800034b3  mov     eax, 14D0h
0x1800034b8  call    _alloca_probe
0x1800034bd  sub     rsp, rax
0x1800034c0  mov     rax, cs:__security_cookie
0x1800034c7  xor     rax, rsp
0x1800034ca  mov     [rbp+1400h+var_40], rax
0x1800034d1  mov     rsi, r8
0x1800034d4  mov     edi, edx
0x1800034d6  mov     rbx, rcx
0x1800034d9  mov     r14, [rbp+1400h+arg_28]
0x1800034e0  xor     edx, edx; Val
0x1800034e2  mov     r8d, 98h; Size
0x1800034e8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800034ed  call    memset_0
0x1800034f2  nop
0x1800034f3  xor     r12d, r12d
0x1800034f6  mov     [rbp+1400h+OutputString], r12w
0x1800034fe  mov     [rbp+1400h+var_1440], r12b
0x180003502  mov     rdx, [rbp+1400h+arg_30]; int
0x180003509  mov     ecx, [rdx]; this
0x18000350b  mov     [rsp+1500h+var_14D8], ecx
0x18000350f  mov     eax, [rdx+4]
0x180003512  mov     [rsp+1500h+var_14D4], eax
0x180003516  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000351b  mov     r15d, eax
0x18000351e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003526  mov     ecx, r12d
0x180003529  lea     eax, [r12+8]
0x18000352e  cmp     dword ptr [rdx+8], 1
0x180003532  cmovz   ecx, eax
0x180003535  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003539  lea     ecx, [rax-7]
0x18000353c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003544  inc     ecx
0x180003546  mov     [rsp+1500h+var_14D0], ecx
0x18000354a  mov     rcx, [rbp+1400h+arg_38]
0x180003551  test    rcx, rcx
0x180003554  jz      short loc_180003561
0x180003556  cmp     [rcx], r12w
0x18000355a  mov     [rsp+1500h+var_14C8], rcx
0x18000355f  jnz     short loc_180003566
0x180003561  mov     [rsp+1500h+var_14C8], r12
0x180003566  call    cs:__imp_GetCurrentThreadId
0x18000356c  mov     [rsp+1500h+var_14C0], eax
0x180003570  mov     [rsp+1500h+var_14A8], rsi
0x180003575  mov     [rsp+1500h+var_14A0], edi
0x180003579  mov     [rsp+1500h+var_149C], r15d
0x18000357e  mov     [rsp+1500h+var_14B8], r12
0x180003583  mov     [rsp+1500h+var_14B0], r12
0x180003588  mov     [rbp+1400h+var_1458], r14
0x18000358c  mov     [rbp+1400h+var_1450], rbx
0x180003590  mov     [rsp+1500h+var_1498], r12
0x180003595  xorps   xmm0, xmm0
0x180003598  xor     eax, eax
0x18000359a  movups  [rbp+1400h+var_1478], xmm0
0x18000359e  mov     [rbp+1400h+var_1468], rax
0x1800035a2  xorps   xmm1, xmm1
0x1800035a5  movups  [rsp+1500h+var_1490], xmm1
0x1800035aa  mov     [rbp+1400h+var_1480], rax
0x1800035ae  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800035b5  test    rax, rax
0x1800035b8  jz      short loc_1800035C5
0x1800035ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035bf  mov     [rbp+1400h+var_1460], rax
0x1800035c3  jmp     short loc_1800035C9
0x1800035c5  mov     [rbp+1400h+var_1460], r12
0x1800035c9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800035d0  test    rax, rax
0x1800035d3  jz      short loc_1800035DF
0x1800035d5  lea     rcx, [rsp+1500h+var_14E0]
0x1800035da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035df  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800035e6  test    rax, rax
0x1800035e9  jz      short loc_1800035FF
0x1800035eb  mov     r8d, 400h
0x1800035f1  lea     rdx, [rbp+1400h+var_1440]
0x1800035f5  lea     rcx, [rsp+1500h+var_14E0]
0x1800035fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035ff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003606  test    rax, rax
0x180003609  jz      short loc_180003615
0x18000360b  lea     rcx, [rsp+1500h+var_14E0]
0x180003610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003615  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000361c  test    rax, rax
0x18000361f  jz      short loc_180003632
0x180003621  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003626  jnz     short loc_180003632
0x180003628  lea     rcx, [rsp+1500h+var_14E0]
0x18000362d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003632  cmp     [rsp+1500h+var_14D8], r12d
0x180003637  jge     loc_180003740
0x18000363d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003644  jnz     short loc_180003665
0x180003646  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000364d  test    rax, rax
0x180003650  jz      short loc_18000365B
0x180003652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003657  test    al, al
0x180003659  jmp     short loc_180003663
0x18000365b  call    cs:__imp_IsDebuggerPresent
0x180003661  test    eax, eax
0x180003663  jz      short loc_18000366C
0x180003665  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000366a  jz      short loc_180003692
0x18000366c  mov     rax, cs:g_pfnResultLoggingCallback
0x180003673  test    rax, rax
0x180003676  jz      short loc_1800036EB
0x180003678  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000367f  jnz     short loc_1800036EB
0x180003681  xor     r8d, r8d
0x180003684  xor     edx, edx
0x180003686  lea     rcx, [rsp+1500h+var_14E0]
0x18000368b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003690  jmp     short loc_1800036EB
0x180003692  mov     ebx, 800h
0x180003697  mov     rax, cs:g_pfnResultLoggingCallback
0x18000369e  test    rax, rax
0x1800036a1  jz      short loc_1800036C0
0x1800036a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036aa  jnz     short loc_1800036C0
0x1800036ac  mov     r8d, ebx
0x1800036af  lea     rdx, [rbp+1400h+OutputString]
0x1800036b6  lea     rcx, [rsp+1500h+var_14E0]
0x1800036bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c0  cmp     [rbp+1400h+OutputString], r12w
0x1800036c8  jnz     short loc_1800036DE
0x1800036ca  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800036cf  mov     rdx, rbx; unsigned __int16 *
0x1800036d2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800036d9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800036de  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800036e5  call    cs:__imp_OutputDebugStringW
0x1800036eb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800036f0  jnz     short loc_1800036FB
0x1800036f2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800036f9  jz      short loc_18000370D
0x1800036fb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003702  test    rax, rax
0x180003705  jz      short loc_18000370D
0x180003707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000370c  nop
0x18000370d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003712  jnz     short loc_180003735
0x180003714  mov     rcx, [rbp+1400h+var_40]
0x18000371b  xor     rcx, rsp; StackCookie
0x18000371e  call    __security_check_cookie
0x180003723  add     rsp, 14D0h
0x18000372a  pop     r15
0x18000372c  pop     r14
0x18000372e  pop     r12
0x180003730  pop     rdi
0x180003731  pop     rsi
0x180003732  pop     rbx
0x180003733  pop     rbp
0x180003734  retn
0x180003735  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000373a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180003740  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
