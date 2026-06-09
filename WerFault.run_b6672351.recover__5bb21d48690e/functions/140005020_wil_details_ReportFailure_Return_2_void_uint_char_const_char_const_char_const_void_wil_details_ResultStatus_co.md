# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140005020`
- end: `0x140005333`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `787`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x1400046e8`

## callees

- `0x140002490`
- `0x1400030f8`
- `0x1400048f8`
- `0x140005020`
- `0x140007a24`
- `0x14000822c`
- `0x140009678`
- `0x14000c53c`
- `0x14000c710`
- `0x14005f510`
- `0x140061010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005141`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005141`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000523a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000523a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400052c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400052c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
    ModuleName = wil::details::g_pfnGetModuleName();
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
      : (v21 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
    wil::details::g_pfnDebugBreak();
  if ( (v24 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v23, v18);
}

```

## disassembly

```asm
0x140005020  push    rbp
0x140005022  push    rbx
0x140005023  push    rsi
0x140005024  push    rdi
0x140005025  push    r12
0x140005027  push    r13
0x140005029  push    r14
0x14000502b  push    r15
0x14000502d  lea     rbp, [rsp-1408h]
0x140005035  mov     eax, 1508h
0x14000503a  call    _alloca_probe
0x14000503f  sub     rsp, rax
0x140005042  mov     rax, cs:__security_cookie
0x140005049  xor     rax, rsp
0x14000504c  mov     [rbp+1440h+var_50], rax
0x140005053  mov     r12, r9
0x140005056  mov     r15, r8
0x140005059  mov     r14d, edx
0x14000505c  mov     rsi, rcx
0x14000505f  mov     r13, [rbp+1440h+arg_20]
0x140005066  mov     rax, [rbp+1440h+arg_28]
0x14000506d  mov     [rsp+1540h+var_1500], rax
0x140005072  xor     edx, edx; Val
0x140005074  mov     r8d, 98h; Size
0x14000507a  lea     rcx, [rsp+1540h+var_14F0]; void *
0x14000507f  call    memset_0
0x140005084  nop
0x140005085  xor     eax, eax
0x140005087  mov     [rbp+1440h+OutputString], ax
0x14000508e  mov     [rbp+1440h+var_1450], al
0x140005091  mov     rdi, [rbp+1440h+arg_30]
0x140005098  mov     ebx, [rdi]
0x14000509a  mov     [rsp+1540h+var_14E8], ebx
0x14000509e  mov     eax, [rdi+4]
0x1400050a1  mov     [rsp+1540h+var_14E4], eax
0x1400050a5  test    ebx, ebx
0x1400050a7  js      short loc_1400050E9
0x1400050a9  mov     [rsp+1540h+var_1508], 0
0x1400050b1  mov     ebx, 8007029Ch
0x1400050b6  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x1400050ba  mov     rax, [rsp+1540h+var_1500]
0x1400050bf  mov     [rsp+1540h+var_1518], rax; __int64
0x1400050c4  mov     [rsp+1540h+var_1520], r13; __int64
0x1400050c9  mov     r9, r12; int
0x1400050cc  mov     r8, r15; int
0x1400050cf  mov     edx, r14d; int
0x1400050d2  mov     rcx, rsi; int
0x1400050d5  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400050da  mov     [rsp+1540h+var_14E8], ebx
0x1400050de  mov     ecx, ebx; this
0x1400050e0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400050e5  mov     [rsp+1540h+var_14E4], eax
0x1400050e9  mov     ecx, ebx; this
0x1400050eb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400050f0  mov     ebx, eax
0x1400050f2  mov     dword ptr [rsp+1540h+var_14F0], 2
0x1400050fa  mov     ecx, [rbp+1440h+arg_48]
0x140005100  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140005104  cmp     dword ptr [rdi+8], 1
0x140005108  jnz     short loc_140005111
0x14000510a  or      ecx, 8
0x14000510d  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140005111  mov     ecx, 1
0x140005116  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000511e  inc     ecx
0x140005120  mov     [rsp+1540h+var_14E0], ecx
0x140005124  mov     rax, [rbp+1440h+arg_38]
0x14000512b  xor     edi, edi
0x14000512d  test    rax, rax
0x140005130  jz      short loc_14000513C
0x140005132  cmp     [rax], di
0x140005135  mov     [rsp+1540h+var_14D8], rax
0x14000513a  jnz     short loc_140005141
0x14000513c  mov     [rsp+1540h+var_14D8], rdi
0x140005141  call    cs:__imp_GetCurrentThreadId
0x140005148  nop     dword ptr [rax+rax+00h]
0x14000514d  mov     [rsp+1540h+var_14D0], eax
0x140005151  mov     [rbp+1440h+var_14B8], r15
0x140005155  mov     [rbp+1440h+var_14B0], r14d
0x140005159  mov     [rbp+1440h+var_14AC], ebx
0x14000515c  mov     [rsp+1540h+var_14C8], r13
0x140005161  mov     [rbp+1440h+var_14C0], r12
0x140005165  mov     rax, [rsp+1540h+var_1500]
0x14000516a  mov     [rbp+1440h+var_1468], rax
0x14000516e  mov     [rbp+1440h+var_1460], rsi
0x140005172  mov     [rbp+1440h+var_14A8], rdi
0x140005176  xorps   xmm0, xmm0
0x140005179  xor     eax, eax
0x14000517b  movups  [rbp+1440h+var_1488], xmm0
0x14000517f  mov     [rbp+1440h+var_1478], rax
0x140005183  xorps   xmm1, xmm1
0x140005186  movups  [rbp+1440h+var_14A0], xmm1
0x14000518a  mov     [rbp+1440h+var_1490], rax
0x14000518e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005195  test    rax, rax
0x140005198  jz      short loc_1400051A5
0x14000519a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000519f  mov     [rbp+1440h+var_1470], rax
0x1400051a3  jmp     short loc_1400051A9
0x1400051a5  mov     [rbp+1440h+var_1470], rdi
0x1400051a9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400051b0  test    rax, rax
0x1400051b3  jz      short loc_1400051BF
0x1400051b5  lea     rcx, [rsp+1540h+var_14F0]
0x1400051ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051bf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400051c6  test    rax, rax
0x1400051c9  jz      short loc_1400051DF
0x1400051cb  mov     r8d, 400h
0x1400051d1  lea     rdx, [rbp+1440h+var_1450]
0x1400051d5  lea     rcx, [rsp+1540h+var_14F0]
0x1400051da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400051e6  test    rax, rax
0x1400051e9  jz      short loc_1400051F5
0x1400051eb  lea     rcx, [rsp+1540h+var_14F0]
0x1400051f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051f5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400051fc  test    rax, rax
0x1400051ff  jz      short loc_140005212
0x140005201  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140005206  jnz     short loc_140005212
0x140005208  lea     rcx, [rsp+1540h+var_14F0]
0x14000520d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005212  cmp     [rsp+1540h+var_14E8], edi
0x140005216  jge     loc_14000532D
0x14000521c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005223  jnz     short loc_14000524A
0x140005225  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000522c  test    rax, rax
0x14000522f  jz      short loc_14000523A
0x140005231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005236  test    al, al
0x140005238  jmp     short loc_140005248
0x14000523a  call    cs:__imp_IsDebuggerPresent
0x140005241  nop     dword ptr [rax+rax+00h]
0x140005246  test    eax, eax
0x140005248  jz      short loc_140005251
0x14000524a  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x14000524f  jz      short loc_140005277
0x140005251  mov     rax, cs:g_pfnResultLoggingCallback
0x140005258  test    rax, rax
0x14000525b  jz      short loc_1400052D5
0x14000525d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005264  jnz     short loc_1400052D5
0x140005266  xor     r8d, r8d
0x140005269  xor     edx, edx
0x14000526b  lea     rcx, [rsp+1540h+var_14F0]
0x140005270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005275  jmp     short loc_1400052D5
0x140005277  mov     ebx, 800h
0x14000527c  mov     rax, cs:g_pfnResultLoggingCallback
0x140005283  test    rax, rax
0x140005286  jz      short loc_1400052A5
0x140005288  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000528f  jnz     short loc_1400052A5
0x140005291  mov     r8d, ebx
0x140005294  lea     rdx, [rbp+1440h+OutputString]
0x14000529b  lea     rcx, [rsp+1540h+var_14F0]
0x1400052a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052a5  cmp     [rbp+1440h+OutputString], di
0x1400052ac  jnz     short loc_1400052C2
0x1400052ae  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x1400052b3  mov     rdx, rbx; wchar_t *
0x1400052b6  lea     rcx, [rbp+1440h+OutputString]; this
0x1400052bd  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400052c2  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x1400052c9  call    cs:__imp_OutputDebugStringW
0x1400052d0  nop     dword ptr [rax+rax+00h]
0x1400052d5  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x1400052da  jnz     short loc_1400052E5
0x1400052dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400052e3  jz      short loc_1400052F7
0x1400052e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400052ec  test    rax, rax
0x1400052ef  jz      short loc_1400052F7
0x1400052f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400052f6  nop
0x1400052f7  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x1400052fc  jnz     short loc_140005322
0x1400052fe  mov     rcx, [rbp+1440h+var_50]
0x140005305  xor     rcx, rsp; StackCookie
0x140005308  call    __security_check_cookie
0x14000530d  add     rsp, 1508h
0x140005314  pop     r15
0x140005316  pop     r14
0x140005318  pop     r13
0x14000531a  pop     r12
0x14000531c  pop     rdi
0x14000531d  pop     rsi
0x14000531e  pop     rbx
0x14000531f  pop     rbp
0x140005320  retn
0x140005322  lea     rcx, [rsp+1540h+var_14F0]; this
0x140005327  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000532d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
