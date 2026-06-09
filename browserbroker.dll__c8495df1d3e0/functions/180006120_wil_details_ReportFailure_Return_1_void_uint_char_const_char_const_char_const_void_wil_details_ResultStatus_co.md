# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180006120`
- end: `0x1800063ad`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180005d3c`

## callees

- `0x180002ce0`
- `0x1800037ac`
- `0x180006120`
- `0x18000959c`
- `0x18000b8a0`
- `0x18000d858`
- `0x18000dc48`
- `0x18002b4e0`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061ce`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800061ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800062c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800062c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000634c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000634c`

## pseudocode

```c
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
0x180006120  push    rbp
0x180006122  push    rbx
0x180006123  push    rsi
0x180006124  push    rdi
0x180006125  push    r12
0x180006127  push    r14
0x180006129  push    r15
0x18000612b  lea     rbp, [rsp-13D0h]
0x180006133  mov     eax, 14D0h
0x180006138  call    _alloca_probe
0x18000613d  sub     rsp, rax
0x180006140  mov     rax, cs:__security_cookie
0x180006147  xor     rax, rsp
0x18000614a  mov     [rbp+1400h+var_40], rax
0x180006151  mov     r14, r8
0x180006154  mov     esi, edx
0x180006156  mov     r15, rcx
0x180006159  mov     rdi, [rbp+1400h+arg_28]
0x180006160  xor     edx, edx; Val
0x180006162  mov     r8d, 98h; Size
0x180006168  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000616d  call    memset_0
0x180006172  nop
0x180006173  xor     r12d, r12d
0x180006176  mov     [rbp+1400h+OutputString], r12w
0x18000617e  mov     [rbp+1400h+var_1440], r12b
0x180006182  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006189  mov     ecx, [rdx]; this
0x18000618b  mov     [rsp+1500h+var_14D8], ecx
0x18000618f  mov     eax, [rdx+4]
0x180006192  mov     [rsp+1500h+var_14D4], eax
0x180006196  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000619b  mov     ebx, eax
0x18000619d  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800061a5  mov     ecx, r12d
0x1800061a8  lea     eax, [r12+8]
0x1800061ad  cmp     dword ptr [rdx+8], 1
0x1800061b1  cmovz   ecx, eax
0x1800061b4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800061b8  lea     ecx, [rax-7]
0x1800061bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800061c3  inc     ecx
0x1800061c5  mov     [rsp+1500h+var_14D0], ecx
0x1800061c9  mov     [rsp+1500h+var_14C8], r12
0x1800061ce  call    cs:__imp_GetCurrentThreadId
0x1800061d4  mov     [rsp+1500h+var_14C0], eax
0x1800061d8  mov     [rsp+1500h+var_14A8], r14
0x1800061dd  mov     [rsp+1500h+var_14A0], esi
0x1800061e1  mov     [rsp+1500h+var_149C], ebx
0x1800061e5  mov     [rsp+1500h+var_14B8], r12
0x1800061ea  mov     [rsp+1500h+var_14B0], r12
0x1800061ef  mov     [rbp+1400h+var_1458], rdi
0x1800061f3  mov     [rbp+1400h+var_1450], r15
0x1800061f7  mov     [rsp+1500h+var_1498], r12
0x1800061fc  xorps   xmm0, xmm0
0x1800061ff  xor     eax, eax
0x180006201  movups  [rbp+1400h+var_1478], xmm0
0x180006205  mov     [rbp+1400h+var_1468], rax
0x180006209  xorps   xmm1, xmm1
0x18000620c  movups  [rsp+1500h+var_1490], xmm1
0x180006211  mov     [rbp+1400h+var_1480], rax
0x180006215  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000621c  test    rax, rax
0x18000621f  jz      short loc_18000622C
0x180006221  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006226  mov     [rbp+1400h+var_1460], rax
0x18000622a  jmp     short loc_180006230
0x18000622c  mov     [rbp+1400h+var_1460], r12
0x180006230  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006237  test    rax, rax
0x18000623a  jz      short loc_180006246
0x18000623c  lea     rcx, [rsp+1500h+var_14E0]
0x180006241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006246  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000624d  test    rax, rax
0x180006250  jz      short loc_180006266
0x180006252  mov     r8d, 400h
0x180006258  lea     rdx, [rbp+1400h+var_1440]
0x18000625c  lea     rcx, [rsp+1500h+var_14E0]
0x180006261  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006266  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000626d  test    rax, rax
0x180006270  jz      short loc_18000627C
0x180006272  lea     rcx, [rsp+1500h+var_14E0]
0x180006277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000627c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006283  test    rax, rax
0x180006286  jz      short loc_180006299
0x180006288  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000628d  jnz     short loc_180006299
0x18000628f  lea     rcx, [rsp+1500h+var_14E0]
0x180006294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006299  cmp     [rsp+1500h+var_14D8], r12d
0x18000629e  jge     loc_1800063A7
0x1800062a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800062ab  jnz     short loc_1800062CC
0x1800062ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800062b4  test    rax, rax
0x1800062b7  jz      short loc_1800062C2
0x1800062b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062be  test    al, al
0x1800062c0  jmp     short loc_1800062CA
0x1800062c2  call    cs:__imp_IsDebuggerPresent
0x1800062c8  test    eax, eax
0x1800062ca  jz      short loc_1800062D3
0x1800062cc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800062d1  jz      short loc_1800062F9
0x1800062d3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800062da  test    rax, rax
0x1800062dd  jz      short loc_180006352
0x1800062df  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800062e6  jnz     short loc_180006352
0x1800062e8  xor     r8d, r8d
0x1800062eb  xor     edx, edx
0x1800062ed  lea     rcx, [rsp+1500h+var_14E0]
0x1800062f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f7  jmp     short loc_180006352
0x1800062f9  mov     ebx, 800h
0x1800062fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180006305  test    rax, rax
0x180006308  jz      short loc_180006327
0x18000630a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006311  jnz     short loc_180006327
0x180006313  mov     r8d, ebx
0x180006316  lea     rdx, [rbp+1400h+OutputString]
0x18000631d  lea     rcx, [rsp+1500h+var_14E0]
0x180006322  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006327  cmp     [rbp+1400h+OutputString], r12w
0x18000632f  jnz     short loc_180006345
0x180006331  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006336  mov     rdx, rbx; unsigned __int16 *
0x180006339  lea     rcx, [rbp+1400h+OutputString]; this
0x180006340  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006345  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000634c  call    cs:__imp_OutputDebugStringW
0x180006352  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006357  jnz     short loc_180006362
0x180006359  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006360  jz      short loc_180006374
0x180006362  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006369  test    rax, rax
0x18000636c  jz      short loc_180006374
0x18000636e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006373  nop
0x180006374  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006379  jnz     short loc_18000639C
0x18000637b  mov     rcx, [rbp+1400h+var_40]
0x180006382  xor     rcx, rsp; StackCookie
0x180006385  call    __security_check_cookie
0x18000638a  add     rsp, 14D0h
0x180006391  pop     r15
0x180006393  pop     r14
0x180006395  pop     r12
0x180006397  pop     rdi
0x180006398  pop     rsi
0x180006399  pop     rbx
0x18000639a  pop     rbp
0x18000639b  retn
0x18000639c  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800063a1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800063a7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
