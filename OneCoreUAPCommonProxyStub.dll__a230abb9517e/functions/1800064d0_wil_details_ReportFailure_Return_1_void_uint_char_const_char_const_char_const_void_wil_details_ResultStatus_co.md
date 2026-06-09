# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800064d0`
- end: `0x180006776`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005f1c`

## callees

- `0x18000363c`
- `0x180003c80`
- `0x1800045ba`
- `0x1800064d0`
- `0x180007cc4`
- `0x180008c00`
- `0x180009bb8`
- `0x18000b120`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006596`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006596`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006715`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006715`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000668b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000668b`

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
0x1800064d0  push    rbp
0x1800064d2  push    rbx
0x1800064d3  push    rsi
0x1800064d4  push    rdi
0x1800064d5  push    r12
0x1800064d7  push    r14
0x1800064d9  push    r15
0x1800064db  lea     rbp, [rsp-13D0h]
0x1800064e3  mov     eax, 14D0h
0x1800064e8  call    _alloca_probe
0x1800064ed  sub     rsp, rax
0x1800064f0  mov     rax, cs:__security_cookie
0x1800064f7  xor     rax, rsp
0x1800064fa  mov     [rbp+1400h+var_40], rax
0x180006501  mov     rsi, r8
0x180006504  mov     edi, edx
0x180006506  mov     rbx, rcx
0x180006509  mov     r14, [rbp+1400h+arg_28]
0x180006510  xor     edx, edx; Val
0x180006512  mov     r8d, 98h; Size
0x180006518  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000651d  call    memset_0
0x180006522  nop
0x180006523  xor     r12d, r12d
0x180006526  mov     [rbp+1400h+OutputString], r12w
0x18000652e  mov     [rbp+1400h+var_1440], r12b
0x180006532  mov     rdx, [rbp+1400h+arg_30]; int
0x180006539  mov     ecx, [rdx]; this
0x18000653b  mov     [rsp+1500h+var_14D8], ecx
0x18000653f  mov     eax, [rdx+4]
0x180006542  mov     [rsp+1500h+var_14D4], eax
0x180006546  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000654b  mov     r15d, eax
0x18000654e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006556  mov     ecx, r12d
0x180006559  lea     eax, [r12+8]
0x18000655e  cmp     dword ptr [rdx+8], 1
0x180006562  cmovz   ecx, eax
0x180006565  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006569  lea     ecx, [rax-7]
0x18000656c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006574  inc     ecx
0x180006576  mov     [rsp+1500h+var_14D0], ecx
0x18000657a  mov     rcx, [rbp+1400h+arg_38]
0x180006581  test    rcx, rcx
0x180006584  jz      short loc_180006591
0x180006586  cmp     [rcx], r12w
0x18000658a  mov     [rsp+1500h+var_14C8], rcx
0x18000658f  jnz     short loc_180006596
0x180006591  mov     [rsp+1500h+var_14C8], r12
0x180006596  call    cs:__imp_GetCurrentThreadId
0x18000659c  mov     [rsp+1500h+var_14C0], eax
0x1800065a0  mov     [rsp+1500h+var_14A8], rsi
0x1800065a5  mov     [rsp+1500h+var_14A0], edi
0x1800065a9  mov     [rsp+1500h+var_149C], r15d
0x1800065ae  mov     [rsp+1500h+var_14B8], r12
0x1800065b3  mov     [rsp+1500h+var_14B0], r12
0x1800065b8  mov     [rbp+1400h+var_1458], r14
0x1800065bc  mov     [rbp+1400h+var_1450], rbx
0x1800065c0  mov     [rsp+1500h+var_1498], r12
0x1800065c5  xorps   xmm0, xmm0
0x1800065c8  xor     eax, eax
0x1800065ca  movups  [rbp+1400h+var_1478], xmm0
0x1800065ce  mov     [rbp+1400h+var_1468], rax
0x1800065d2  xorps   xmm1, xmm1
0x1800065d5  movups  [rsp+1500h+var_1490], xmm1
0x1800065da  mov     [rbp+1400h+var_1480], rax
0x1800065de  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800065e5  test    rax, rax
0x1800065e8  jz      short loc_1800065F5
0x1800065ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ef  mov     [rbp+1400h+var_1460], rax
0x1800065f3  jmp     short loc_1800065F9
0x1800065f5  mov     [rbp+1400h+var_1460], r12
0x1800065f9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006600  test    rax, rax
0x180006603  jz      short loc_18000660F
0x180006605  lea     rcx, [rsp+1500h+var_14E0]
0x18000660a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006616  test    rax, rax
0x180006619  jz      short loc_18000662F
0x18000661b  mov     r8d, 400h
0x180006621  lea     rdx, [rbp+1400h+var_1440]
0x180006625  lea     rcx, [rsp+1500h+var_14E0]
0x18000662a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000662f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006636  test    rax, rax
0x180006639  jz      short loc_180006645
0x18000663b  lea     rcx, [rsp+1500h+var_14E0]
0x180006640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006645  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000664c  test    rax, rax
0x18000664f  jz      short loc_180006662
0x180006651  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006656  jnz     short loc_180006662
0x180006658  lea     rcx, [rsp+1500h+var_14E0]
0x18000665d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006662  cmp     [rsp+1500h+var_14D8], r12d
0x180006667  jge     loc_180006770
0x18000666d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006674  jnz     short loc_180006695
0x180006676  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000667d  test    rax, rax
0x180006680  jz      short loc_18000668B
0x180006682  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006687  test    al, al
0x180006689  jmp     short loc_180006693
0x18000668b  call    cs:__imp_IsDebuggerPresent
0x180006691  test    eax, eax
0x180006693  jz      short loc_18000669C
0x180006695  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000669a  jz      short loc_1800066C2
0x18000669c  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066a3  test    rax, rax
0x1800066a6  jz      short loc_18000671B
0x1800066a8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800066af  jnz     short loc_18000671B
0x1800066b1  xor     r8d, r8d
0x1800066b4  xor     edx, edx
0x1800066b6  lea     rcx, [rsp+1500h+var_14E0]
0x1800066bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066c0  jmp     short loc_18000671B
0x1800066c2  mov     ebx, 800h
0x1800066c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066ce  test    rax, rax
0x1800066d1  jz      short loc_1800066F0
0x1800066d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800066da  jnz     short loc_1800066F0
0x1800066dc  mov     r8d, ebx
0x1800066df  lea     rdx, [rbp+1400h+OutputString]
0x1800066e6  lea     rcx, [rsp+1500h+var_14E0]
0x1800066eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f0  cmp     [rbp+1400h+OutputString], r12w
0x1800066f8  jnz     short loc_18000670E
0x1800066fa  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800066ff  mov     rdx, rbx; unsigned __int16 *
0x180006702  lea     rcx, [rbp+1400h+OutputString]; this
0x180006709  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000670e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006715  call    cs:__imp_OutputDebugStringW
0x18000671b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006720  jnz     short loc_18000672B
0x180006722  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006729  jz      short loc_18000673D
0x18000672b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006732  test    rax, rax
0x180006735  jz      short loc_18000673D
0x180006737  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673c  nop
0x18000673d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006742  jnz     short loc_180006765
0x180006744  mov     rcx, [rbp+1400h+var_40]
0x18000674b  xor     rcx, rsp; StackCookie
0x18000674e  call    __security_check_cookie
0x180006753  add     rsp, 14D0h
0x18000675a  pop     r15
0x18000675c  pop     r14
0x18000675e  pop     r12
0x180006760  pop     rdi
0x180006761  pop     rsi
0x180006762  pop     rbx
0x180006763  pop     rbp
0x180006764  retn
0x180006765  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000676a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006770  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
