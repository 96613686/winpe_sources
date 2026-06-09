# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800047c8`
- end: `0x180004ac8`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `768`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180003fc8`

## callees

- `0x180002590`
- `0x180002f98`
- `0x1800041d4`
- `0x1800047c8`
- `0x180007914`
- `0x180008110`
- `0x1800093cc`
- `0x18000c380`
- `0x18000c5c4`
- `0x1800300f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048e9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800048e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800049dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800049dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a65`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004a65`

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
      g_pfnResultLoggingCallback(&v23, 0, 0, v20);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v23, OutputString, 2048, v20);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v23, v20);
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
0x1800047c8  push    rbp
0x1800047ca  push    rbx
0x1800047cb  push    rsi
0x1800047cc  push    rdi
0x1800047cd  push    r12
0x1800047cf  push    r13
0x1800047d1  push    r14
0x1800047d3  push    r15
0x1800047d5  lea     rbp, [rsp-1408h]
0x1800047dd  mov     eax, 1508h
0x1800047e2  call    _alloca_probe
0x1800047e7  sub     rsp, rax
0x1800047ea  mov     rax, cs:__security_cookie
0x1800047f1  xor     rax, rsp
0x1800047f4  mov     [rbp+1440h+var_50], rax
0x1800047fb  mov     r12, r9
0x1800047fe  mov     r15, r8
0x180004801  mov     r14d, edx
0x180004804  mov     rsi, rcx
0x180004807  mov     r13, [rbp+1440h+arg_20]
0x18000480e  mov     rax, [rbp+1440h+arg_28]
0x180004815  mov     [rsp+1540h+var_1500], rax
0x18000481a  xor     edx, edx; Val
0x18000481c  mov     r8d, 98h; Size
0x180004822  lea     rcx, [rsp+1540h+var_14F0]; void *
0x180004827  call    memset_0
0x18000482c  nop
0x18000482d  xor     eax, eax
0x18000482f  mov     [rbp+1440h+OutputString], ax
0x180004836  mov     [rbp+1440h+var_1450], al
0x180004839  mov     rdi, [rbp+1440h+arg_30]
0x180004840  mov     ebx, [rdi]
0x180004842  mov     [rsp+1540h+var_14E8], ebx
0x180004846  mov     eax, [rdi+4]
0x180004849  mov     [rsp+1540h+var_14E4], eax
0x18000484d  test    ebx, ebx
0x18000484f  js      short loc_180004891
0x180004851  mov     [rsp+1540h+var_1508], 0
0x180004859  mov     ebx, 8007029Ch
0x18000485e  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180004862  mov     rax, [rsp+1540h+var_1500]
0x180004867  mov     [rsp+1540h+var_1518], rax; __int64
0x18000486c  mov     [rsp+1540h+var_1520], r13; __int64
0x180004871  mov     r9, r12; int
0x180004874  mov     r8, r15; int
0x180004877  mov     edx, r14d; int
0x18000487a  mov     rcx, rsi; int
0x18000487d  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004882  mov     [rsp+1540h+var_14E8], ebx
0x180004886  mov     ecx, ebx; this
0x180004888  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000488d  mov     [rsp+1540h+var_14E4], eax
0x180004891  mov     ecx, ebx; this
0x180004893  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004898  mov     ebx, eax
0x18000489a  mov     dword ptr [rsp+1540h+var_14F0], 2
0x1800048a2  mov     ecx, [rbp+1440h+arg_48]
0x1800048a8  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800048ac  cmp     dword ptr [rdi+8], 1
0x1800048b0  jnz     short loc_1800048B9
0x1800048b2  or      ecx, 8
0x1800048b5  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x1800048b9  mov     ecx, 1
0x1800048be  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800048c6  inc     ecx
0x1800048c8  mov     [rsp+1540h+var_14E0], ecx
0x1800048cc  mov     rax, [rbp+1440h+arg_38]
0x1800048d3  xor     edi, edi
0x1800048d5  test    rax, rax
0x1800048d8  jz      short loc_1800048E4
0x1800048da  cmp     [rax], di
0x1800048dd  mov     [rsp+1540h+var_14D8], rax
0x1800048e2  jnz     short loc_1800048E9
0x1800048e4  mov     [rsp+1540h+var_14D8], rdi
0x1800048e9  call    cs:__imp_GetCurrentThreadId
0x1800048ef  mov     [rsp+1540h+var_14D0], eax
0x1800048f3  mov     [rbp+1440h+var_14B8], r15
0x1800048f7  mov     [rbp+1440h+var_14B0], r14d
0x1800048fb  mov     [rbp+1440h+var_14AC], ebx
0x1800048fe  mov     [rsp+1540h+var_14C8], r13
0x180004903  mov     [rbp+1440h+var_14C0], r12
0x180004907  mov     rax, [rsp+1540h+var_1500]
0x18000490c  mov     [rbp+1440h+var_1468], rax
0x180004910  mov     [rbp+1440h+var_1460], rsi
0x180004914  mov     [rbp+1440h+var_14A8], rdi
0x180004918  xorps   xmm0, xmm0
0x18000491b  xor     eax, eax
0x18000491d  movups  [rbp+1440h+var_1488], xmm0
0x180004921  mov     [rbp+1440h+var_1478], rax
0x180004925  xorps   xmm1, xmm1
0x180004928  movups  [rbp+1440h+var_14A0], xmm1
0x18000492c  mov     [rbp+1440h+var_1490], rax
0x180004930  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004937  test    rax, rax
0x18000493a  jz      short loc_180004947
0x18000493c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004941  mov     [rbp+1440h+var_1470], rax
0x180004945  jmp     short loc_18000494B
0x180004947  mov     [rbp+1440h+var_1470], rdi
0x18000494b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004952  test    rax, rax
0x180004955  jz      short loc_180004961
0x180004957  lea     rcx, [rsp+1540h+var_14F0]
0x18000495c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004961  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004968  test    rax, rax
0x18000496b  jz      short loc_180004981
0x18000496d  mov     r8d, 400h
0x180004973  lea     rdx, [rbp+1440h+var_1450]
0x180004977  lea     rcx, [rsp+1540h+var_14F0]
0x18000497c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004981  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004988  test    rax, rax
0x18000498b  jz      short loc_180004997
0x18000498d  lea     rcx, [rsp+1540h+var_14F0]
0x180004992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004997  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000499e  test    rax, rax
0x1800049a1  jz      short loc_1800049B4
0x1800049a3  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800049a8  jnz     short loc_1800049B4
0x1800049aa  lea     rcx, [rsp+1540h+var_14F0]
0x1800049af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049b4  cmp     [rsp+1540h+var_14E8], edi
0x1800049b8  jge     loc_180004AC2
0x1800049be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800049c5  jnz     short loc_1800049E6
0x1800049c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800049ce  test    rax, rax
0x1800049d1  jz      short loc_1800049DC
0x1800049d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049d8  test    al, al
0x1800049da  jmp     short loc_1800049E4
0x1800049dc  call    cs:__imp_IsDebuggerPresent
0x1800049e2  test    eax, eax
0x1800049e4  jz      short loc_1800049ED
0x1800049e6  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800049eb  jz      short loc_180004A13
0x1800049ed  mov     rax, cs:g_pfnResultLoggingCallback
0x1800049f4  test    rax, rax
0x1800049f7  jz      short loc_180004A6B
0x1800049f9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004a00  jnz     short loc_180004A6B
0x180004a02  xor     r8d, r8d
0x180004a05  xor     edx, edx
0x180004a07  lea     rcx, [rsp+1540h+var_14F0]
0x180004a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a11  jmp     short loc_180004A6B
0x180004a13  mov     ebx, 800h
0x180004a18  mov     rax, cs:g_pfnResultLoggingCallback
0x180004a1f  test    rax, rax
0x180004a22  jz      short loc_180004A41
0x180004a24  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004a2b  jnz     short loc_180004A41
0x180004a2d  mov     r8d, ebx
0x180004a30  lea     rdx, [rbp+1440h+OutputString]
0x180004a37  lea     rcx, [rsp+1540h+var_14F0]
0x180004a3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a41  cmp     [rbp+1440h+OutputString], di
0x180004a48  jnz     short loc_180004A5E
0x180004a4a  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x180004a4f  mov     rdx, rbx; unsigned __int16 *
0x180004a52  lea     rcx, [rbp+1440h+OutputString]; this
0x180004a59  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004a5e  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180004a65  call    cs:__imp_OutputDebugStringW
0x180004a6b  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x180004a70  jnz     short loc_180004A7B
0x180004a72  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004a79  jz      short loc_180004A8D
0x180004a7b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004a82  test    rax, rax
0x180004a85  jz      short loc_180004A8D
0x180004a87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004a8c  nop
0x180004a8d  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180004a92  jnz     short loc_180004AB7
0x180004a94  mov     rcx, [rbp+1440h+var_50]
0x180004a9b  xor     rcx, rsp; StackCookie
0x180004a9e  call    __security_check_cookie
0x180004aa3  add     rsp, 1508h
0x180004aaa  pop     r15
0x180004aac  pop     r14
0x180004aae  pop     r13
0x180004ab0  pop     r12
0x180004ab2  pop     rdi
0x180004ab3  pop     rsi
0x180004ab4  pop     rbx
0x180004ab5  pop     rbp
0x180004ab6  retn
0x180004ab7  lea     rcx, [rsp+1540h+var_14F0]; this
0x180004abc  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004ac2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
