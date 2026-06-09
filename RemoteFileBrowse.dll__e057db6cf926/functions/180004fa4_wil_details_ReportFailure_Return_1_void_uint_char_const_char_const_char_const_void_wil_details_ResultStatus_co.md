# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180004fa4`
- end: `0x18000524a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004668`

## callees

- `0x180002030`
- `0x180002dc4`
- `0x180003324`
- `0x180004fa4`
- `0x180006f48`
- `0x180007170`
- `0x180007298`
- `0x1800173e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000506a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000506a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000515f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000515f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800051e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800051e9`

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
0x180004fa4  push    rbp
0x180004fa6  push    rbx
0x180004fa7  push    rsi
0x180004fa8  push    rdi
0x180004fa9  push    r12
0x180004fab  push    r14
0x180004fad  push    r15
0x180004faf  lea     rbp, [rsp-13D0h]
0x180004fb7  mov     eax, 14D0h
0x180004fbc  call    _alloca_probe
0x180004fc1  sub     rsp, rax
0x180004fc4  mov     rax, cs:__security_cookie
0x180004fcb  xor     rax, rsp
0x180004fce  mov     [rbp+1400h+var_40], rax
0x180004fd5  mov     rsi, r8
0x180004fd8  mov     edi, edx
0x180004fda  mov     rbx, rcx
0x180004fdd  mov     r14, [rbp+1400h+arg_28]
0x180004fe4  xor     edx, edx; Val
0x180004fe6  mov     r8d, 98h; Size
0x180004fec  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004ff1  call    memset_0
0x180004ff6  nop
0x180004ff7  xor     r12d, r12d
0x180004ffa  mov     [rbp+1400h+OutputString], r12w
0x180005002  mov     [rbp+1400h+var_1440], r12b
0x180005006  mov     rdx, [rbp+1400h+arg_30]; int
0x18000500d  mov     ecx, [rdx]; this
0x18000500f  mov     [rsp+1500h+var_14D8], ecx
0x180005013  mov     eax, [rdx+4]
0x180005016  mov     [rsp+1500h+var_14D4], eax
0x18000501a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000501f  mov     r15d, eax
0x180005022  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000502a  mov     ecx, r12d
0x18000502d  lea     eax, [r12+8]
0x180005032  cmp     dword ptr [rdx+8], 1
0x180005036  cmovz   ecx, eax
0x180005039  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000503d  lea     ecx, [rax-7]
0x180005040  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005048  inc     ecx
0x18000504a  mov     [rsp+1500h+var_14D0], ecx
0x18000504e  mov     rcx, [rbp+1400h+arg_38]
0x180005055  test    rcx, rcx
0x180005058  jz      short loc_180005065
0x18000505a  cmp     [rcx], r12w
0x18000505e  mov     [rsp+1500h+var_14C8], rcx
0x180005063  jnz     short loc_18000506A
0x180005065  mov     [rsp+1500h+var_14C8], r12
0x18000506a  call    cs:__imp_GetCurrentThreadId
0x180005070  mov     [rsp+1500h+var_14C0], eax
0x180005074  mov     [rsp+1500h+var_14A8], rsi
0x180005079  mov     [rsp+1500h+var_14A0], edi
0x18000507d  mov     [rsp+1500h+var_149C], r15d
0x180005082  mov     [rsp+1500h+var_14B8], r12
0x180005087  mov     [rsp+1500h+var_14B0], r12
0x18000508c  mov     [rbp+1400h+var_1458], r14
0x180005090  mov     [rbp+1400h+var_1450], rbx
0x180005094  mov     [rsp+1500h+var_1498], r12
0x180005099  xorps   xmm0, xmm0
0x18000509c  xor     eax, eax
0x18000509e  movups  [rbp+1400h+var_1478], xmm0
0x1800050a2  mov     [rbp+1400h+var_1468], rax
0x1800050a6  xorps   xmm1, xmm1
0x1800050a9  movups  [rsp+1500h+var_1490], xmm1
0x1800050ae  mov     [rbp+1400h+var_1480], rax
0x1800050b2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800050b9  test    rax, rax
0x1800050bc  jz      short loc_1800050C9
0x1800050be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050c3  mov     [rbp+1400h+var_1460], rax
0x1800050c7  jmp     short loc_1800050CD
0x1800050c9  mov     [rbp+1400h+var_1460], r12
0x1800050cd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800050d4  test    rax, rax
0x1800050d7  jz      short loc_1800050E3
0x1800050d9  lea     rcx, [rsp+1500h+var_14E0]
0x1800050de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800050ea  test    rax, rax
0x1800050ed  jz      short loc_180005103
0x1800050ef  mov     r8d, 400h
0x1800050f5  lea     rdx, [rbp+1400h+var_1440]
0x1800050f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800050fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005103  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000510a  test    rax, rax
0x18000510d  jz      short loc_180005119
0x18000510f  lea     rcx, [rsp+1500h+var_14E0]
0x180005114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005119  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005120  test    rax, rax
0x180005123  jz      short loc_180005136
0x180005125  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000512a  jnz     short loc_180005136
0x18000512c  lea     rcx, [rsp+1500h+var_14E0]
0x180005131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005136  cmp     [rsp+1500h+var_14D8], r12d
0x18000513b  jge     loc_180005244
0x180005141  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005148  jnz     short loc_180005169
0x18000514a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005151  test    rax, rax
0x180005154  jz      short loc_18000515F
0x180005156  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000515b  test    al, al
0x18000515d  jmp     short loc_180005167
0x18000515f  call    cs:__imp_IsDebuggerPresent
0x180005165  test    eax, eax
0x180005167  jz      short loc_180005170
0x180005169  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000516e  jz      short loc_180005196
0x180005170  mov     rax, cs:g_pfnResultLoggingCallback
0x180005177  test    rax, rax
0x18000517a  jz      short loc_1800051EF
0x18000517c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180005183  jnz     short loc_1800051EF
0x180005185  xor     r8d, r8d
0x180005188  xor     edx, edx
0x18000518a  lea     rcx, [rsp+1500h+var_14E0]
0x18000518f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005194  jmp     short loc_1800051EF
0x180005196  mov     ebx, 800h
0x18000519b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051a2  test    rax, rax
0x1800051a5  jz      short loc_1800051C4
0x1800051a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800051ae  jnz     short loc_1800051C4
0x1800051b0  mov     r8d, ebx
0x1800051b3  lea     rdx, [rbp+1400h+OutputString]
0x1800051ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800051bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c4  cmp     [rbp+1400h+OutputString], r12w
0x1800051cc  jnz     short loc_1800051E2
0x1800051ce  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800051d3  mov     rdx, rbx; unsigned __int16 *
0x1800051d6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800051dd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800051e2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800051e9  call    cs:__imp_OutputDebugStringW
0x1800051ef  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800051f4  jnz     short loc_1800051FF
0x1800051f6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800051fd  jz      short loc_180005211
0x1800051ff  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005206  test    rax, rax
0x180005209  jz      short loc_180005211
0x18000520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005210  nop
0x180005211  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005216  jnz     short loc_180005239
0x180005218  mov     rcx, [rbp+1400h+var_40]
0x18000521f  xor     rcx, rsp; StackCookie
0x180005222  call    __security_check_cookie
0x180005227  add     rsp, 14D0h
0x18000522e  pop     r15
0x180005230  pop     r14
0x180005232  pop     r12
0x180005234  pop     rdi
0x180005235  pop     rsi
0x180005236  pop     rbx
0x180005237  pop     rbp
0x180005238  retn
0x180005239  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000523e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005244  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
