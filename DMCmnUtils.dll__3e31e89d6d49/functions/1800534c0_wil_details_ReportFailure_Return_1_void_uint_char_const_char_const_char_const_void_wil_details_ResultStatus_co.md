# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800534c0`
- end: `0x180053779`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `697`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180053150`

## callees

- `0x180007270`
- `0x180007c7c`
- `0x1800534c0`
- `0x180055274`
- `0x180057114`
- `0x180059010`
- `0x180059220`
- `0x1800b2630`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053586`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180053586`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180053711`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180053711`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180053681`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180053681`

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
0x1800534c0  push    rbp
0x1800534c2  push    rbx
0x1800534c3  push    rsi
0x1800534c4  push    rdi
0x1800534c5  push    r12
0x1800534c7  push    r14
0x1800534c9  push    r15
0x1800534cb  lea     rbp, [rsp-13D0h]
0x1800534d3  mov     eax, 14D0h
0x1800534d8  call    _alloca_probe
0x1800534dd  sub     rsp, rax
0x1800534e0  mov     rax, cs:__security_cookie
0x1800534e7  xor     rax, rsp
0x1800534ea  mov     [rbp+1400h+var_40], rax
0x1800534f1  mov     rsi, r8
0x1800534f4  mov     edi, edx
0x1800534f6  mov     rbx, rcx
0x1800534f9  mov     r14, [rbp+1400h+arg_28]
0x180053500  xor     edx, edx; Val
0x180053502  mov     r8d, 98h; Size
0x180053508  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18005350d  call    memset_0
0x180053512  nop
0x180053513  xor     r12d, r12d
0x180053516  mov     [rbp+1400h+OutputString], r12w
0x18005351e  mov     [rbp+1400h+var_1440], r12b
0x180053522  mov     rdx, [rbp+1400h+arg_30]; int
0x180053529  mov     ecx, [rdx]; this
0x18005352b  mov     [rsp+1500h+var_14D8], ecx
0x18005352f  mov     eax, [rdx+4]
0x180053532  mov     [rsp+1500h+var_14D4], eax
0x180053536  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005353b  mov     r15d, eax
0x18005353e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180053546  mov     ecx, r12d
0x180053549  lea     eax, [r12+8]
0x18005354e  cmp     dword ptr [rdx+8], 1
0x180053552  cmovz   ecx, eax
0x180053555  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180053559  lea     ecx, [rax-7]
0x18005355c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180053564  inc     ecx
0x180053566  mov     [rsp+1500h+var_14D0], ecx
0x18005356a  mov     rcx, [rbp+1400h+arg_38]
0x180053571  test    rcx, rcx
0x180053574  jz      short loc_180053581
0x180053576  cmp     [rcx], r12w
0x18005357a  mov     [rsp+1500h+var_14C8], rcx
0x18005357f  jnz     short loc_180053586
0x180053581  mov     [rsp+1500h+var_14C8], r12
0x180053586  call    cs:__imp_GetCurrentThreadId
0x18005358d  nop     dword ptr [rax+rax+00h]
0x180053592  mov     [rsp+1500h+var_14C0], eax
0x180053596  mov     [rsp+1500h+var_14A8], rsi
0x18005359b  mov     [rsp+1500h+var_14A0], edi
0x18005359f  mov     [rsp+1500h+var_149C], r15d
0x1800535a4  mov     [rsp+1500h+var_14B8], r12
0x1800535a9  mov     [rsp+1500h+var_14B0], r12
0x1800535ae  mov     [rbp+1400h+var_1458], r14
0x1800535b2  mov     [rbp+1400h+var_1450], rbx
0x1800535b6  mov     [rsp+1500h+var_1498], r12
0x1800535bb  xorps   xmm0, xmm0
0x1800535be  xor     eax, eax
0x1800535c0  movups  [rbp+1400h+var_1478], xmm0
0x1800535c4  mov     [rbp+1400h+var_1468], rax
0x1800535c8  xorps   xmm1, xmm1
0x1800535cb  movups  [rsp+1500h+var_1490], xmm1
0x1800535d0  mov     [rbp+1400h+var_1480], rax
0x1800535d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800535db  test    rax, rax
0x1800535de  jz      short loc_1800535EB
0x1800535e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800535e5  mov     [rbp+1400h+var_1460], rax
0x1800535e9  jmp     short loc_1800535EF
0x1800535eb  mov     [rbp+1400h+var_1460], r12
0x1800535ef  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800535f6  test    rax, rax
0x1800535f9  jz      short loc_180053605
0x1800535fb  lea     rcx, [rsp+1500h+var_14E0]
0x180053600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053605  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005360c  test    rax, rax
0x18005360f  jz      short loc_180053625
0x180053611  mov     r8d, 400h
0x180053617  lea     rdx, [rbp+1400h+var_1440]
0x18005361b  lea     rcx, [rsp+1500h+var_14E0]
0x180053620  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053625  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005362c  test    rax, rax
0x18005362f  jz      short loc_18005363B
0x180053631  lea     rcx, [rsp+1500h+var_14E0]
0x180053636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005363b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180053642  test    rax, rax
0x180053645  jz      short loc_180053658
0x180053647  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18005364c  jnz     short loc_180053658
0x18005364e  lea     rcx, [rsp+1500h+var_14E0]
0x180053653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053658  cmp     [rsp+1500h+var_14D8], r12d
0x18005365d  jge     loc_180053773
0x180053663  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18005366a  jnz     short loc_180053691
0x18005366c  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180053673  test    rax, rax
0x180053676  jz      short loc_180053681
0x180053678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005367d  test    al, al
0x18005367f  jmp     short loc_18005368F
0x180053681  call    cs:__imp_IsDebuggerPresent
0x180053688  nop     dword ptr [rax+rax+00h]
0x18005368d  test    eax, eax
0x18005368f  jz      short loc_180053698
0x180053691  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180053696  jz      short loc_1800536BE
0x180053698  mov     rax, cs:g_pfnResultLoggingCallback
0x18005369f  test    rax, rax
0x1800536a2  jz      short loc_18005371D
0x1800536a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800536ab  jnz     short loc_18005371D
0x1800536ad  xor     r8d, r8d
0x1800536b0  xor     edx, edx
0x1800536b2  lea     rcx, [rsp+1500h+var_14E0]
0x1800536b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536bc  jmp     short loc_18005371D
0x1800536be  mov     ebx, 800h
0x1800536c3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800536ca  test    rax, rax
0x1800536cd  jz      short loc_1800536EC
0x1800536cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800536d6  jnz     short loc_1800536EC
0x1800536d8  mov     r8d, ebx
0x1800536db  lea     rdx, [rbp+1400h+OutputString]
0x1800536e2  lea     rcx, [rsp+1500h+var_14E0]
0x1800536e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800536ec  cmp     [rbp+1400h+OutputString], r12w
0x1800536f4  jnz     short loc_18005370A
0x1800536f6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800536fb  mov     rdx, rbx; unsigned __int16 *
0x1800536fe  lea     rcx, [rbp+1400h+OutputString]; this
0x180053705  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005370a  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180053711  call    cs:__imp_OutputDebugStringW
0x180053718  nop     dword ptr [rax+rax+00h]
0x18005371d  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180053722  jnz     short loc_18005372D
0x180053724  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18005372b  jz      short loc_18005373F
0x18005372d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180053734  test    rax, rax
0x180053737  jz      short loc_18005373F
0x180053739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005373e  nop
0x18005373f  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180053744  jnz     short loc_180053768
0x180053746  mov     rcx, [rbp+1400h+var_40]
0x18005374d  xor     rcx, rsp; StackCookie
0x180053750  call    __security_check_cookie
0x180053755  add     rsp, 14D0h
0x18005375c  pop     r15
0x18005375e  pop     r14
0x180053760  pop     r12
0x180053762  pop     rdi
0x180053763  pop     rsi
0x180053764  pop     rbx
0x180053765  pop     rbp
0x180053766  retn
0x180053768  lea     rcx, [rsp+1500h+var_14E0]; this
0x18005376d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180053773  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
