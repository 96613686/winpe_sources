# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800046fc`
- end: `0x180004989`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800043c0`

## callees

- `0x1800036a0`
- `0x180004054`
- `0x1800046fc`
- `0x180005630`
- `0x1800066e0`
- `0x180007148`
- `0x1800072b4`
- `0x18001b3e0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800047aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004928`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004928`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000489e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000489e`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x1800046fc  push    rbp
0x1800046fe  push    rbx
0x1800046ff  push    rsi
0x180004700  push    rdi
0x180004701  push    r12
0x180004703  push    r14
0x180004705  push    r15
0x180004707  lea     rbp, [rsp-13D0h]
0x18000470f  mov     eax, 14D0h
0x180004714  call    _alloca_probe
0x180004719  sub     rsp, rax
0x18000471c  mov     rax, cs:__security_cookie
0x180004723  xor     rax, rsp
0x180004726  mov     [rbp+1400h+var_40], rax
0x18000472d  mov     r14, r8
0x180004730  mov     esi, edx
0x180004732  mov     r15, rcx
0x180004735  mov     rdi, [rbp+1400h+arg_28]
0x18000473c  xor     edx, edx; Val
0x18000473e  mov     r8d, 98h; Size
0x180004744  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004749  call    memset_0
0x18000474e  nop
0x18000474f  xor     r12d, r12d
0x180004752  mov     [rbp+1400h+OutputString], r12w
0x18000475a  mov     [rbp+1400h+var_1440], r12b
0x18000475e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004765  mov     ecx, [rdx]; this
0x180004767  mov     [rsp+1500h+var_14D8], ecx
0x18000476b  mov     eax, [rdx+4]
0x18000476e  mov     [rsp+1500h+var_14D4], eax
0x180004772  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004777  mov     ebx, eax
0x180004779  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004781  mov     ecx, r12d
0x180004784  lea     eax, [r12+8]
0x180004789  cmp     dword ptr [rdx+8], 1
0x18000478d  cmovz   ecx, eax
0x180004790  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004794  lea     ecx, [rax-7]
0x180004797  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000479f  inc     ecx
0x1800047a1  mov     [rsp+1500h+var_14D0], ecx
0x1800047a5  mov     [rsp+1500h+var_14C8], r12
0x1800047aa  call    cs:__imp_GetCurrentThreadId
0x1800047b0  mov     [rsp+1500h+var_14C0], eax
0x1800047b4  mov     [rsp+1500h+var_14A8], r14
0x1800047b9  mov     [rsp+1500h+var_14A0], esi
0x1800047bd  mov     [rsp+1500h+var_149C], ebx
0x1800047c1  mov     [rsp+1500h+var_14B8], r12
0x1800047c6  mov     [rsp+1500h+var_14B0], r12
0x1800047cb  mov     [rbp+1400h+var_1458], rdi
0x1800047cf  mov     [rbp+1400h+var_1450], r15
0x1800047d3  mov     [rsp+1500h+var_1498], r12
0x1800047d8  xorps   xmm0, xmm0
0x1800047db  xor     eax, eax
0x1800047dd  movups  [rbp+1400h+var_1478], xmm0
0x1800047e1  mov     [rbp+1400h+var_1468], rax
0x1800047e5  xorps   xmm1, xmm1
0x1800047e8  movups  [rsp+1500h+var_1490], xmm1
0x1800047ed  mov     [rbp+1400h+var_1480], rax
0x1800047f1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800047f8  test    rax, rax
0x1800047fb  jz      short loc_180004808
0x1800047fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004802  mov     [rbp+1400h+var_1460], rax
0x180004806  jmp     short loc_18000480C
0x180004808  mov     [rbp+1400h+var_1460], r12
0x18000480c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004813  test    rax, rax
0x180004816  jz      short loc_180004822
0x180004818  lea     rcx, [rsp+1500h+var_14E0]
0x18000481d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004822  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004829  test    rax, rax
0x18000482c  jz      short loc_180004842
0x18000482e  mov     r8d, 400h
0x180004834  lea     rdx, [rbp+1400h+var_1440]
0x180004838  lea     rcx, [rsp+1500h+var_14E0]
0x18000483d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004842  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004849  test    rax, rax
0x18000484c  jz      short loc_180004858
0x18000484e  lea     rcx, [rsp+1500h+var_14E0]
0x180004853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004858  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000485f  test    rax, rax
0x180004862  jz      short loc_180004875
0x180004864  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004869  jnz     short loc_180004875
0x18000486b  lea     rcx, [rsp+1500h+var_14E0]
0x180004870  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004875  cmp     [rsp+1500h+var_14D8], r12d
0x18000487a  jge     loc_180004983
0x180004880  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004887  jnz     short loc_1800048A8
0x180004889  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004890  test    rax, rax
0x180004893  jz      short loc_18000489E
0x180004895  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000489a  test    al, al
0x18000489c  jmp     short loc_1800048A6
0x18000489e  call    cs:__imp_IsDebuggerPresent
0x1800048a4  test    eax, eax
0x1800048a6  jz      short loc_1800048AF
0x1800048a8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800048ad  jz      short loc_1800048D5
0x1800048af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048b6  test    rax, rax
0x1800048b9  jz      short loc_18000492E
0x1800048bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800048c2  jnz     short loc_18000492E
0x1800048c4  xor     r8d, r8d
0x1800048c7  xor     edx, edx
0x1800048c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800048ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048d3  jmp     short loc_18000492E
0x1800048d5  mov     ebx, 800h
0x1800048da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800048e1  test    rax, rax
0x1800048e4  jz      short loc_180004903
0x1800048e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800048ed  jnz     short loc_180004903
0x1800048ef  mov     r8d, ebx
0x1800048f2  lea     rdx, [rbp+1400h+OutputString]
0x1800048f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800048fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004903  cmp     [rbp+1400h+OutputString], r12w
0x18000490b  jnz     short loc_180004921
0x18000490d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004912  mov     rdx, rbx; unsigned __int16 *
0x180004915  lea     rcx, [rbp+1400h+OutputString]; this
0x18000491c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004921  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004928  call    cs:__imp_OutputDebugStringW
0x18000492e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004933  jnz     short loc_18000493E
0x180004935  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000493c  jz      short loc_180004950
0x18000493e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004945  test    rax, rax
0x180004948  jz      short loc_180004950
0x18000494a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000494f  nop
0x180004950  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004955  jnz     short loc_180004978
0x180004957  mov     rcx, [rbp+1400h+var_40]
0x18000495e  xor     rcx, rsp; StackCookie
0x180004961  call    __security_check_cookie
0x180004966  add     rsp, 14D0h
0x18000496d  pop     r15
0x18000496f  pop     r14
0x180004971  pop     r12
0x180004973  pop     rdi
0x180004974  pop     rsi
0x180004975  pop     rbx
0x180004976  pop     rbp
0x180004977  retn
0x180004978  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000497d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004983  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
