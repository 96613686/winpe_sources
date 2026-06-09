# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180009508`
- end: `0x1800097c1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180009028`

## callees

- `0x180001520`
- `0x180001fd4`
- `0x180009508`
- `0x180009a4c`
- `0x18000ac84`
- `0x18000acc4`
- `0x18000ada0`
- `0x18001db90`
- `0x18001f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800095ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800095ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009759`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009759`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800096c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800096c9`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180009508  push    rbp
0x18000950a  push    rbx
0x18000950b  push    rsi
0x18000950c  push    rdi
0x18000950d  push    r12
0x18000950f  push    r14
0x180009511  push    r15
0x180009513  lea     rbp, [rsp-13D0h]
0x18000951b  mov     eax, 14D0h
0x180009520  call    _alloca_probe
0x180009525  sub     rsp, rax
0x180009528  mov     rax, cs:__security_cookie
0x18000952f  xor     rax, rsp
0x180009532  mov     [rbp+1400h+var_40], rax
0x180009539  mov     rsi, r8
0x18000953c  mov     edi, edx
0x18000953e  mov     rbx, rcx
0x180009541  mov     r14, [rbp+1400h+arg_28]
0x180009548  xor     edx, edx; Val
0x18000954a  mov     r8d, 98h; Size
0x180009550  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180009555  call    memset_0
0x18000955a  nop
0x18000955b  xor     r12d, r12d
0x18000955e  mov     [rbp+1400h+OutputString], r12w
0x180009566  mov     [rbp+1400h+var_1440], r12b
0x18000956a  mov     rdx, [rbp+1400h+arg_30]; int
0x180009571  mov     ecx, [rdx]; this
0x180009573  mov     [rsp+1500h+var_14D8], ecx
0x180009577  mov     eax, [rdx+4]
0x18000957a  mov     [rsp+1500h+var_14D4], eax
0x18000957e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009583  mov     r15d, eax
0x180009586  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000958e  mov     ecx, r12d
0x180009591  lea     eax, [r12+8]
0x180009596  cmp     dword ptr [rdx+8], 1
0x18000959a  cmovz   ecx, eax
0x18000959d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800095a1  lea     ecx, [rax-7]
0x1800095a4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800095ac  inc     ecx
0x1800095ae  mov     [rsp+1500h+var_14D0], ecx
0x1800095b2  mov     rcx, [rbp+1400h+arg_38]
0x1800095b9  test    rcx, rcx
0x1800095bc  jz      short loc_1800095C9
0x1800095be  cmp     [rcx], r12w
0x1800095c2  mov     [rsp+1500h+var_14C8], rcx
0x1800095c7  jnz     short loc_1800095CE
0x1800095c9  mov     [rsp+1500h+var_14C8], r12
0x1800095ce  call    cs:__imp_GetCurrentThreadId
0x1800095d5  nop     dword ptr [rax+rax+00h]
0x1800095da  mov     [rsp+1500h+var_14C0], eax
0x1800095de  mov     [rsp+1500h+var_14A8], rsi
0x1800095e3  mov     [rsp+1500h+var_14A0], edi
0x1800095e7  mov     [rsp+1500h+var_149C], r15d
0x1800095ec  mov     [rsp+1500h+var_14B8], r12
0x1800095f1  mov     [rsp+1500h+var_14B0], r12
0x1800095f6  mov     [rbp+1400h+var_1458], r14
0x1800095fa  mov     [rbp+1400h+var_1450], rbx
0x1800095fe  mov     [rsp+1500h+var_1498], r12
0x180009603  xorps   xmm0, xmm0
0x180009606  xor     eax, eax
0x180009608  movups  [rbp+1400h+var_1478], xmm0
0x18000960c  mov     [rbp+1400h+var_1468], rax
0x180009610  xorps   xmm1, xmm1
0x180009613  movups  [rsp+1500h+var_1490], xmm1
0x180009618  mov     [rbp+1400h+var_1480], rax
0x18000961c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009623  test    rax, rax
0x180009626  jz      short loc_180009633
0x180009628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000962d  mov     [rbp+1400h+var_1460], rax
0x180009631  jmp     short loc_180009637
0x180009633  mov     [rbp+1400h+var_1460], r12
0x180009637  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000963e  test    rax, rax
0x180009641  jz      short loc_18000964D
0x180009643  lea     rcx, [rsp+1500h+var_14E0]
0x180009648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009654  test    rax, rax
0x180009657  jz      short loc_18000966D
0x180009659  mov     r8d, 400h
0x18000965f  lea     rdx, [rbp+1400h+var_1440]
0x180009663  lea     rcx, [rsp+1500h+var_14E0]
0x180009668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000966d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009674  test    rax, rax
0x180009677  jz      short loc_180009683
0x180009679  lea     rcx, [rsp+1500h+var_14E0]
0x18000967e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009683  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000968a  test    rax, rax
0x18000968d  jz      short loc_1800096A0
0x18000968f  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180009694  jnz     short loc_1800096A0
0x180009696  lea     rcx, [rsp+1500h+var_14E0]
0x18000969b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096a0  cmp     [rsp+1500h+var_14D8], r12d
0x1800096a5  jge     loc_1800097BB
0x1800096ab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800096b2  jnz     short loc_1800096D9
0x1800096b4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800096bb  test    rax, rax
0x1800096be  jz      short loc_1800096C9
0x1800096c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c5  test    al, al
0x1800096c7  jmp     short loc_1800096D7
0x1800096c9  call    cs:__imp_IsDebuggerPresent
0x1800096d0  nop     dword ptr [rax+rax+00h]
0x1800096d5  test    eax, eax
0x1800096d7  jz      short loc_1800096E0
0x1800096d9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800096de  jz      short loc_180009706
0x1800096e0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800096e7  test    rax, rax
0x1800096ea  jz      short loc_180009765
0x1800096ec  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800096f3  jnz     short loc_180009765
0x1800096f5  xor     r8d, r8d
0x1800096f8  xor     edx, edx
0x1800096fa  lea     rcx, [rsp+1500h+var_14E0]
0x1800096ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009704  jmp     short loc_180009765
0x180009706  mov     ebx, 800h
0x18000970b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009712  test    rax, rax
0x180009715  jz      short loc_180009734
0x180009717  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000971e  jnz     short loc_180009734
0x180009720  mov     r8d, ebx
0x180009723  lea     rdx, [rbp+1400h+OutputString]
0x18000972a  lea     rcx, [rsp+1500h+var_14E0]
0x18000972f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009734  cmp     [rbp+1400h+OutputString], r12w
0x18000973c  jnz     short loc_180009752
0x18000973e  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180009743  mov     rdx, rbx; unsigned __int16 *
0x180009746  lea     rcx, [rbp+1400h+OutputString]; this
0x18000974d  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009752  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180009759  call    cs:__imp_OutputDebugStringW
0x180009760  nop     dword ptr [rax+rax+00h]
0x180009765  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000976a  jnz     short loc_180009775
0x18000976c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180009773  jz      short loc_180009787
0x180009775  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000977c  test    rax, rax
0x18000977f  jz      short loc_180009787
0x180009781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009786  nop
0x180009787  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000978c  jnz     short loc_1800097B0
0x18000978e  mov     rcx, [rbp+1400h+var_40]
0x180009795  xor     rcx, rsp; StackCookie
0x180009798  call    __security_check_cookie
0x18000979d  add     rsp, 14D0h
0x1800097a4  pop     r15
0x1800097a6  pop     r14
0x1800097a8  pop     r12
0x1800097aa  pop     rdi
0x1800097ab  pop     rsi
0x1800097ac  pop     rbx
0x1800097ad  pop     rbp
0x1800097ae  retn
0x1800097b0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800097b5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800097bb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
