# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800050b0`
- end: `0x180005356`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004d3c`

## callees

- `0x180003450`
- `0x180003fe4`
- `0x1800050b0`
- `0x180006be4`
- `0x1800088ac`
- `0x18000a398`
- `0x18000a5a4`
- `0x18003fc50`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005176`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005176`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000526b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000526b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800052f5`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800052f5`

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
0x1800050b0  push    rbp
0x1800050b2  push    rbx
0x1800050b3  push    rsi
0x1800050b4  push    rdi
0x1800050b5  push    r12
0x1800050b7  push    r14
0x1800050b9  push    r15
0x1800050bb  lea     rbp, [rsp-13D0h]
0x1800050c3  mov     eax, 14D0h
0x1800050c8  call    _alloca_probe
0x1800050cd  sub     rsp, rax
0x1800050d0  mov     rax, cs:__security_cookie
0x1800050d7  xor     rax, rsp
0x1800050da  mov     [rbp+1400h+var_40], rax
0x1800050e1  mov     rsi, r8
0x1800050e4  mov     edi, edx
0x1800050e6  mov     rbx, rcx
0x1800050e9  mov     r14, [rbp+1400h+arg_28]
0x1800050f0  xor     edx, edx; Val
0x1800050f2  mov     r8d, 98h; Size
0x1800050f8  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800050fd  call    memset_0
0x180005102  nop
0x180005103  xor     r12d, r12d
0x180005106  mov     [rbp+1400h+OutputString], r12w
0x18000510e  mov     [rbp+1400h+var_1440], r12b
0x180005112  mov     rdx, [rbp+1400h+arg_30]; int
0x180005119  mov     ecx, [rdx]; this
0x18000511b  mov     [rsp+1500h+var_14D8], ecx
0x18000511f  mov     eax, [rdx+4]
0x180005122  mov     [rsp+1500h+var_14D4], eax
0x180005126  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000512b  mov     r15d, eax
0x18000512e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180005136  mov     ecx, r12d
0x180005139  lea     eax, [r12+8]
0x18000513e  cmp     dword ptr [rdx+8], 1
0x180005142  cmovz   ecx, eax
0x180005145  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180005149  lea     ecx, [rax-7]
0x18000514c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005154  inc     ecx
0x180005156  mov     [rsp+1500h+var_14D0], ecx
0x18000515a  mov     rcx, [rbp+1400h+arg_38]
0x180005161  test    rcx, rcx
0x180005164  jz      short loc_180005171
0x180005166  cmp     [rcx], r12w
0x18000516a  mov     [rsp+1500h+var_14C8], rcx
0x18000516f  jnz     short loc_180005176
0x180005171  mov     [rsp+1500h+var_14C8], r12
0x180005176  call    cs:__imp_GetCurrentThreadId
0x18000517c  mov     [rsp+1500h+var_14C0], eax
0x180005180  mov     [rsp+1500h+var_14A8], rsi
0x180005185  mov     [rsp+1500h+var_14A0], edi
0x180005189  mov     [rsp+1500h+var_149C], r15d
0x18000518e  mov     [rsp+1500h+var_14B8], r12
0x180005193  mov     [rsp+1500h+var_14B0], r12
0x180005198  mov     [rbp+1400h+var_1458], r14
0x18000519c  mov     [rbp+1400h+var_1450], rbx
0x1800051a0  mov     [rsp+1500h+var_1498], r12
0x1800051a5  xorps   xmm0, xmm0
0x1800051a8  xor     eax, eax
0x1800051aa  movups  [rbp+1400h+var_1478], xmm0
0x1800051ae  mov     [rbp+1400h+var_1468], rax
0x1800051b2  xorps   xmm1, xmm1
0x1800051b5  movups  [rsp+1500h+var_1490], xmm1
0x1800051ba  mov     [rbp+1400h+var_1480], rax
0x1800051be  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800051c5  test    rax, rax
0x1800051c8  jz      short loc_1800051D5
0x1800051ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051cf  mov     [rbp+1400h+var_1460], rax
0x1800051d3  jmp     short loc_1800051D9
0x1800051d5  mov     [rbp+1400h+var_1460], r12
0x1800051d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800051e0  test    rax, rax
0x1800051e3  jz      short loc_1800051EF
0x1800051e5  lea     rcx, [rsp+1500h+var_14E0]
0x1800051ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051ef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800051f6  test    rax, rax
0x1800051f9  jz      short loc_18000520F
0x1800051fb  mov     r8d, 400h
0x180005201  lea     rdx, [rbp+1400h+var_1440]
0x180005205  lea     rcx, [rsp+1500h+var_14E0]
0x18000520a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000520f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005216  test    rax, rax
0x180005219  jz      short loc_180005225
0x18000521b  lea     rcx, [rsp+1500h+var_14E0]
0x180005220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005225  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000522c  test    rax, rax
0x18000522f  jz      short loc_180005242
0x180005231  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180005236  jnz     short loc_180005242
0x180005238  lea     rcx, [rsp+1500h+var_14E0]
0x18000523d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005242  cmp     [rsp+1500h+var_14D8], r12d
0x180005247  jge     loc_180005350
0x18000524d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180005254  jnz     short loc_180005275
0x180005256  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000525d  test    rax, rax
0x180005260  jz      short loc_18000526B
0x180005262  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005267  test    al, al
0x180005269  jmp     short loc_180005273
0x18000526b  call    cs:__imp_IsDebuggerPresent
0x180005271  test    eax, eax
0x180005273  jz      short loc_18000527C
0x180005275  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000527a  jz      short loc_1800052A2
0x18000527c  mov     rax, cs:g_pfnResultLoggingCallback
0x180005283  test    rax, rax
0x180005286  jz      short loc_1800052FB
0x180005288  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000528f  jnz     short loc_1800052FB
0x180005291  xor     r8d, r8d
0x180005294  xor     edx, edx
0x180005296  lea     rcx, [rsp+1500h+var_14E0]
0x18000529b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052a0  jmp     short loc_1800052FB
0x1800052a2  mov     ebx, 800h
0x1800052a7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800052ae  test    rax, rax
0x1800052b1  jz      short loc_1800052D0
0x1800052b3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800052ba  jnz     short loc_1800052D0
0x1800052bc  mov     r8d, ebx
0x1800052bf  lea     rdx, [rbp+1400h+OutputString]
0x1800052c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800052cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800052d0  cmp     [rbp+1400h+OutputString], r12w
0x1800052d8  jnz     short loc_1800052EE
0x1800052da  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800052df  mov     rdx, rbx; unsigned __int16 *
0x1800052e2  lea     rcx, [rbp+1400h+OutputString]; this
0x1800052e9  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800052ee  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800052f5  call    cs:__imp_OutputDebugStringW
0x1800052fb  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180005300  jnz     short loc_18000530B
0x180005302  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180005309  jz      short loc_18000531D
0x18000530b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005312  test    rax, rax
0x180005315  jz      short loc_18000531D
0x180005317  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000531c  nop
0x18000531d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180005322  jnz     short loc_180005345
0x180005324  mov     rcx, [rbp+1400h+var_40]
0x18000532b  xor     rcx, rsp; StackCookie
0x18000532e  call    __security_check_cookie
0x180005333  add     rsp, 14D0h
0x18000533a  pop     r15
0x18000533c  pop     r14
0x18000533e  pop     r12
0x180005340  pop     rdi
0x180005341  pop     rsi
0x180005342  pop     rbx
0x180005343  pop     rbp
0x180005344  retn
0x180005345  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000534a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180005350  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
