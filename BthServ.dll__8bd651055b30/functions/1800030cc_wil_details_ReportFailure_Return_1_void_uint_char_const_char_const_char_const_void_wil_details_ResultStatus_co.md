# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800030cc`
- end: `0x180003372`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002b5c`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800030cc`
- `0x180005464`
- `0x180006cd8`
- `0x180009270`
- `0x18000943c`
- `0x180032bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003192`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003192`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003311`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003311`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003287`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003287`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
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
0x1800030cc  push    rbp
0x1800030ce  push    rbx
0x1800030cf  push    rsi
0x1800030d0  push    rdi
0x1800030d1  push    r12
0x1800030d3  push    r14
0x1800030d5  push    r15
0x1800030d7  lea     rbp, [rsp-13D0h]
0x1800030df  mov     eax, 14D0h
0x1800030e4  call    _alloca_probe
0x1800030e9  sub     rsp, rax
0x1800030ec  mov     rax, cs:__security_cookie
0x1800030f3  xor     rax, rsp
0x1800030f6  mov     [rbp+1400h+var_40], rax
0x1800030fd  mov     rsi, r8
0x180003100  mov     edi, edx
0x180003102  mov     rbx, rcx
0x180003105  mov     r14, [rbp+1400h+arg_28]
0x18000310c  xor     edx, edx; Val
0x18000310e  mov     r8d, 98h; Size
0x180003114  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003119  call    memset_0
0x18000311e  nop
0x18000311f  xor     r12d, r12d
0x180003122  mov     [rbp+1400h+OutputString], r12w
0x18000312a  mov     [rbp+1400h+var_1440], r12b
0x18000312e  mov     rdx, [rbp+1400h+arg_30]; int
0x180003135  mov     ecx, [rdx]; this
0x180003137  mov     [rsp+1500h+var_14D8], ecx
0x18000313b  mov     eax, [rdx+4]
0x18000313e  mov     [rsp+1500h+var_14D4], eax
0x180003142  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003147  mov     r15d, eax
0x18000314a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003152  mov     ecx, r12d
0x180003155  lea     eax, [r12+8]
0x18000315a  cmp     dword ptr [rdx+8], 1
0x18000315e  cmovz   ecx, eax
0x180003161  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003165  lea     ecx, [rax-7]
0x180003168  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003170  inc     ecx
0x180003172  mov     [rsp+1500h+var_14D0], ecx
0x180003176  mov     rcx, [rbp+1400h+arg_38]
0x18000317d  test    rcx, rcx
0x180003180  jz      short loc_18000318D
0x180003182  cmp     [rcx], r12w
0x180003186  mov     [rsp+1500h+var_14C8], rcx
0x18000318b  jnz     short loc_180003192
0x18000318d  mov     [rsp+1500h+var_14C8], r12
0x180003192  call    cs:__imp_GetCurrentThreadId
0x180003198  mov     [rsp+1500h+var_14C0], eax
0x18000319c  mov     [rsp+1500h+var_14A8], rsi
0x1800031a1  mov     [rsp+1500h+var_14A0], edi
0x1800031a5  mov     [rsp+1500h+var_149C], r15d
0x1800031aa  mov     [rsp+1500h+var_14B8], r12
0x1800031af  mov     [rsp+1500h+var_14B0], r12
0x1800031b4  mov     [rbp+1400h+var_1458], r14
0x1800031b8  mov     [rbp+1400h+var_1450], rbx
0x1800031bc  mov     [rsp+1500h+var_1498], r12
0x1800031c1  xorps   xmm0, xmm0
0x1800031c4  xor     eax, eax
0x1800031c6  movups  [rbp+1400h+var_1478], xmm0
0x1800031ca  mov     [rbp+1400h+var_1468], rax
0x1800031ce  xorps   xmm1, xmm1
0x1800031d1  movups  [rsp+1500h+var_1490], xmm1
0x1800031d6  mov     [rbp+1400h+var_1480], rax
0x1800031da  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800031e1  test    rax, rax
0x1800031e4  jz      short loc_1800031F1
0x1800031e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800031eb  mov     [rbp+1400h+var_1460], rax
0x1800031ef  jmp     short loc_1800031F5
0x1800031f1  mov     [rbp+1400h+var_1460], r12
0x1800031f5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800031fc  test    rax, rax
0x1800031ff  jz      short loc_18000320B
0x180003201  lea     rcx, [rsp+1500h+var_14E0]
0x180003206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000320b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003212  test    rax, rax
0x180003215  jz      short loc_18000322B
0x180003217  mov     r8d, 400h
0x18000321d  lea     rdx, [rbp+1400h+var_1440]
0x180003221  lea     rcx, [rsp+1500h+var_14E0]
0x180003226  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000322b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003232  test    rax, rax
0x180003235  jz      short loc_180003241
0x180003237  lea     rcx, [rsp+1500h+var_14E0]
0x18000323c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003241  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003248  test    rax, rax
0x18000324b  jz      short loc_18000325E
0x18000324d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003252  jnz     short loc_18000325E
0x180003254  lea     rcx, [rsp+1500h+var_14E0]
0x180003259  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000325e  cmp     [rsp+1500h+var_14D8], r12d
0x180003263  jge     loc_18000336C
0x180003269  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180003270  jnz     short loc_180003291
0x180003272  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003279  test    rax, rax
0x18000327c  jz      short loc_180003287
0x18000327e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003283  test    al, al
0x180003285  jmp     short loc_18000328F
0x180003287  call    cs:__imp_IsDebuggerPresent
0x18000328d  test    eax, eax
0x18000328f  jz      short loc_180003298
0x180003291  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003296  jz      short loc_1800032BE
0x180003298  mov     rax, cs:g_pfnResultLoggingCallback
0x18000329f  test    rax, rax
0x1800032a2  jz      short loc_180003317
0x1800032a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800032ab  jnz     short loc_180003317
0x1800032ad  xor     r8d, r8d
0x1800032b0  xor     edx, edx
0x1800032b2  lea     rcx, [rsp+1500h+var_14E0]
0x1800032b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032bc  jmp     short loc_180003317
0x1800032be  mov     ebx, 800h
0x1800032c3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800032ca  test    rax, rax
0x1800032cd  jz      short loc_1800032EC
0x1800032cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800032d6  jnz     short loc_1800032EC
0x1800032d8  mov     r8d, ebx
0x1800032db  lea     rdx, [rbp+1400h+OutputString]
0x1800032e2  lea     rcx, [rsp+1500h+var_14E0]
0x1800032e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800032ec  cmp     [rbp+1400h+OutputString], r12w
0x1800032f4  jnz     short loc_18000330A
0x1800032f6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800032fb  mov     rdx, rbx; unsigned __int16 *
0x1800032fe  lea     rcx, [rbp+1400h+OutputString]; this
0x180003305  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000330a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003311  call    cs:__imp_OutputDebugStringW
0x180003317  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000331c  jnz     short loc_180003327
0x18000331e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003325  jz      short loc_180003339
0x180003327  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000332e  test    rax, rax
0x180003331  jz      short loc_180003339
0x180003333  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003338  nop
0x180003339  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000333e  jnz     short loc_180003361
0x180003340  mov     rcx, [rbp+1400h+var_40]
0x180003347  xor     rcx, rsp; StackCookie
0x18000334a  call    __security_check_cookie
0x18000334f  add     rsp, 14D0h
0x180003356  pop     r15
0x180003358  pop     r14
0x18000335a  pop     r12
0x18000335c  pop     rdi
0x18000335d  pop     rsi
0x18000335e  pop     rbx
0x18000335f  pop     rbp
0x180003360  retn
0x180003361  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003366  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000336c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
