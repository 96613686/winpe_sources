# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140005000`
- end: `0x140005300`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400046f8`

## callees

- `0x140002470`
- `0x1400030a8`
- `0x140004904`
- `0x140005000`
- `0x140007b34`
- `0x1400082d4`
- `0x14000964c`
- `0x14000c3d0`
- `0x14000c59c`
- `0x14005b770`
- `0x14005d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005121`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005121`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005214`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005214`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000529d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000529d`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<2>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7,
        _WORD *a8,
        int a9,
        int a10)
{
  int v14; // edx
  int v15; // ebx
  int v16; // edx
  int v17; // ebx
  const struct wil::FailureInfo *v18; // rdx
  wil::details::in1diag3 *v19; // rcx
  const struct wil::FailureInfo *v20; // r9
  bool v21; // zf
  wil::details *v22; // [rsp+30h] [rbp-D0h]
  int v23; // [rsp+50h] [rbp-B0h] BYREF
  int v24; // [rsp+54h] [rbp-ACh]
  int v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v27; // [rsp+60h] [rbp-A0h]
  _WORD *v28; // [rsp+68h] [rbp-98h]
  DWORD CurrentThreadId; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+78h] [rbp-88h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int64 v32; // [rsp+88h] [rbp-78h]
  int v33; // [rsp+90h] [rbp-70h]
  int v34; // [rsp+94h] [rbp-6Ch]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int128 v36; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  __int128 v38; // [rsp+B8h] [rbp-48h]
  __int64 v39; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v41; // [rsp+D8h] [rbp-28h]
  __int64 v42; // [rsp+E0h] [rbp-20h]
  char v43[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v23, 0, 0x98u);
  OutputString[0] = 0;
  v43[0] = 0;
  v15 = *a7;
  v25 = v15;
  v26 = a7[1];
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v22) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v22);
    v25 = -2147024228;
    v26 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v16);
  }
  v17 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v23 = 2;
  v24 = a10;
  if ( a7[2] == 1 )
    v24 = a10 | 8;
  v27 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v21 = *a8 == 0, v28 = a8, v21) )
    v28 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v32 = a3;
  v33 = a2;
  v34 = v17;
  v30 = a5;
  v31 = a4;
  v41 = a6;
  v42 = a1;
  v35 = 0;
  v38 = 0;
  v39 = 0;
  v36 = 0;
  v37 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v19);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v23);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v23, v43, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v23);
  if ( wil::details::g_pfnOriginateCallback && (v24 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v23);
  if ( v25 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v19);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v21 = !IsDebuggerPresent())
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v19) == 0),
        v21)
    || (v24 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v23, v20);
    OutputDebugStringW(OutputString);
  }
  if ( ((v24 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v19);
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x140005000  push    rbp
0x140005002  push    rbx
0x140005003  push    rsi
0x140005004  push    rdi
0x140005005  push    r12
0x140005007  push    r13
0x140005009  push    r14
0x14000500b  push    r15
0x14000500d  lea     rbp, [rsp-1408h]
0x140005015  mov     eax, 1508h
0x14000501a  call    _alloca_probe
0x14000501f  sub     rsp, rax
0x140005022  mov     rax, cs:__security_cookie
0x140005029  xor     rax, rsp
0x14000502c  mov     [rbp+1440h+var_50], rax
0x140005033  mov     r12, r9
0x140005036  mov     r15, r8
0x140005039  mov     r14d, edx
0x14000503c  mov     rsi, rcx
0x14000503f  mov     r13, [rbp+1440h+arg_20]
0x140005046  mov     rax, [rbp+1440h+arg_28]
0x14000504d  mov     [rsp+1540h+var_1500], rax
0x140005052  xor     edx, edx; Val
0x140005054  mov     r8d, 98h; Size
0x14000505a  lea     rcx, [rsp+1540h+var_14F0]; void *
0x14000505f  call    memset_0
0x140005064  nop
0x140005065  xor     eax, eax
0x140005067  mov     [rbp+1440h+OutputString], ax
0x14000506e  mov     [rbp+1440h+var_1450], al
0x140005071  mov     rdi, [rbp+1440h+arg_30]
0x140005078  mov     ebx, [rdi]
0x14000507a  mov     [rsp+1540h+var_14E8], ebx
0x14000507e  mov     eax, [rdi+4]
0x140005081  mov     [rsp+1540h+var_14E4], eax
0x140005085  test    ebx, ebx
0x140005087  js      short loc_1400050C9
0x140005089  mov     [rsp+1540h+var_1508], 0
0x140005091  mov     ebx, 8007029Ch
0x140005096  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x14000509a  mov     rax, [rsp+1540h+var_1500]
0x14000509f  mov     [rsp+1540h+var_1518], rax; __int64
0x1400050a4  mov     [rsp+1540h+var_1520], r13; __int64
0x1400050a9  mov     r9, r12; int
0x1400050ac  mov     r8, r15; int
0x1400050af  mov     edx, r14d; int
0x1400050b2  mov     rcx, rsi; int
0x1400050b5  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400050ba  mov     [rsp+1540h+var_14E8], ebx
0x1400050be  mov     ecx, ebx; this
0x1400050c0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400050c5  mov     [rsp+1540h+var_14E4], eax
0x1400050c9  mov     ecx, ebx; this
0x1400050cb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400050d0  mov     ebx, eax
0x1400050d2  mov     dword ptr [rsp+1540h+var_14F0], 2
0x1400050da  mov     ecx, [rbp+1440h+arg_48]
0x1400050e0  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1400050e4  cmp     dword ptr [rdi+8], 1
0x1400050e8  jnz     short loc_1400050F1
0x1400050ea  or      ecx, 8
0x1400050ed  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1400050f1  mov     ecx, 1
0x1400050f6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400050fe  inc     ecx
0x140005100  mov     [rsp+1540h+var_14E0], ecx
0x140005104  mov     rax, [rbp+1440h+arg_38]
0x14000510b  xor     edi, edi
0x14000510d  test    rax, rax
0x140005110  jz      short loc_14000511C
0x140005112  cmp     [rax], di
0x140005115  mov     [rsp+1540h+var_14D8], rax
0x14000511a  jnz     short loc_140005121
0x14000511c  mov     [rsp+1540h+var_14D8], rdi
0x140005121  call    cs:__imp_GetCurrentThreadId
0x140005127  mov     [rsp+1540h+var_14D0], eax
0x14000512b  mov     [rbp+1440h+var_14B8], r15
0x14000512f  mov     [rbp+1440h+var_14B0], r14d
0x140005133  mov     [rbp+1440h+var_14AC], ebx
0x140005136  mov     [rsp+1540h+var_14C8], r13
0x14000513b  mov     [rbp+1440h+var_14C0], r12
0x14000513f  mov     rax, [rsp+1540h+var_1500]
0x140005144  mov     [rbp+1440h+var_1468], rax
0x140005148  mov     [rbp+1440h+var_1460], rsi
0x14000514c  mov     [rbp+1440h+var_14A8], rdi
0x140005150  xorps   xmm0, xmm0
0x140005153  xor     eax, eax
0x140005155  movups  [rbp+1440h+var_1488], xmm0
0x140005159  mov     [rbp+1440h+var_1478], rax
0x14000515d  xorps   xmm1, xmm1
0x140005160  movups  [rbp+1440h+var_14A0], xmm1
0x140005164  mov     [rbp+1440h+var_1490], rax
0x140005168  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000516f  test    rax, rax
0x140005172  jz      short loc_14000517F
0x140005174  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005179  mov     [rbp+1440h+var_1470], rax
0x14000517d  jmp     short loc_140005183
0x14000517f  mov     [rbp+1440h+var_1470], rdi
0x140005183  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000518a  test    rax, rax
0x14000518d  jz      short loc_140005199
0x14000518f  lea     rcx, [rsp+1540h+var_14F0]
0x140005194  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005199  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400051a0  test    rax, rax
0x1400051a3  jz      short loc_1400051B9
0x1400051a5  mov     r8d, 400h
0x1400051ab  lea     rdx, [rbp+1440h+var_1450]
0x1400051af  lea     rcx, [rsp+1540h+var_14F0]
0x1400051b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051b9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400051c0  test    rax, rax
0x1400051c3  jz      short loc_1400051CF
0x1400051c5  lea     rcx, [rsp+1540h+var_14F0]
0x1400051ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400051d6  test    rax, rax
0x1400051d9  jz      short loc_1400051EC
0x1400051db  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1400051e0  jnz     short loc_1400051EC
0x1400051e2  lea     rcx, [rsp+1540h+var_14F0]
0x1400051e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051ec  cmp     [rsp+1540h+var_14E8], edi
0x1400051f0  jge     loc_1400052FA
0x1400051f6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400051fd  jnz     short loc_14000521E
0x1400051ff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005206  test    rax, rax
0x140005209  jz      short loc_140005214
0x14000520b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005210  test    al, al
0x140005212  jmp     short loc_14000521C
0x140005214  call    cs:__imp_IsDebuggerPresent
0x14000521a  test    eax, eax
0x14000521c  jz      short loc_140005225
0x14000521e  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140005223  jz      short loc_14000524B
0x140005225  mov     rax, cs:g_pfnResultLoggingCallback
0x14000522c  test    rax, rax
0x14000522f  jz      short loc_1400052A3
0x140005231  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005238  jnz     short loc_1400052A3
0x14000523a  xor     r8d, r8d
0x14000523d  xor     edx, edx
0x14000523f  lea     rcx, [rsp+1540h+var_14F0]
0x140005244  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005249  jmp     short loc_1400052A3
0x14000524b  mov     ebx, 800h
0x140005250  mov     rax, cs:g_pfnResultLoggingCallback
0x140005257  test    rax, rax
0x14000525a  jz      short loc_140005279
0x14000525c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005263  jnz     short loc_140005279
0x140005265  mov     r8d, ebx
0x140005268  lea     rdx, [rbp+1440h+OutputString]
0x14000526f  lea     rcx, [rsp+1540h+var_14F0]
0x140005274  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005279  cmp     [rbp+1440h+OutputString], di
0x140005280  jnz     short loc_140005296
0x140005282  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x140005287  mov     rdx, rbx; wchar_t *
0x14000528a  lea     rcx, [rbp+1440h+OutputString]; this
0x140005291  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140005296  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x14000529d  call    cs:__imp_OutputDebugStringW
0x1400052a3  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x1400052a8  jnz     short loc_1400052B3
0x1400052aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400052b1  jz      short loc_1400052C5
0x1400052b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400052ba  test    rax, rax
0x1400052bd  jz      short loc_1400052C5
0x1400052bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052c4  nop
0x1400052c5  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x1400052ca  jnz     short loc_1400052EF
0x1400052cc  mov     rcx, [rbp+1440h+var_50]
0x1400052d3  xor     rcx, rsp; StackCookie
0x1400052d6  call    __security_check_cookie
0x1400052db  add     rsp, 1508h
0x1400052e2  pop     r15
0x1400052e4  pop     r14
0x1400052e6  pop     r13
0x1400052e8  pop     r12
0x1400052ea  pop     rdi
0x1400052eb  pop     rsi
0x1400052ec  pop     rbx
0x1400052ed  pop     rbp
0x1400052ee  retn
0x1400052ef  lea     rcx, [rsp+1540h+var_14F0]; this
0x1400052f4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400052fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
