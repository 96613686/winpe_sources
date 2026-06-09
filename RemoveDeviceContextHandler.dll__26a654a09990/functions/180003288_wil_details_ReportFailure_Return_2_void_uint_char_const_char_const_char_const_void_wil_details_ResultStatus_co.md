# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003288`
- end: `0x180003586`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `766`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x180002ae0`

## callees

- `0x180002cc4`
- `0x180003288`
- `0x180003f84`
- `0x1800047c0`
- `0x180004be4`
- `0x1800054f0`
- `0x180005678`
- `0x18000c966`
- `0x18000c990`
- `0x18000ca20`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a8`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033a8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000349b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000349b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003524`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003524`

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
  int v16; // eax
  int v17; // edx
  int v18; // eax
  int v19; // ebx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v21; // rdx
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  bool v24; // zf
  wil::details *v25; // [rsp+30h] [rbp-D0h]
  int v26; // [rsp+50h] [rbp-B0h] BYREF
  int v27; // [rsp+54h] [rbp-ACh]
  int v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+5Ch] [rbp-A4h]
  signed __int32 v30; // [rsp+60h] [rbp-A0h]
  _WORD *v31; // [rsp+68h] [rbp-98h]
  DWORD v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int64 v35; // [rsp+88h] [rbp-78h]
  int v36; // [rsp+90h] [rbp-70h]
  int v37; // [rsp+94h] [rbp-6Ch]
  __int64 v38; // [rsp+98h] [rbp-68h]
  __int128 v39; // [rsp+A0h] [rbp-60h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  __int128 v41; // [rsp+B8h] [rbp-48h]
  __int64 v42; // [rsp+C8h] [rbp-38h]
  __int64 ModuleName; // [rsp+D0h] [rbp-30h]
  __int64 v44; // [rsp+D8h] [rbp-28h]
  __int64 v45; // [rsp+E0h] [rbp-20h]
  char v46[1024]; // [rsp+F0h] [rbp-10h] BYREF
  WCHAR OutputString[2048]; // [rsp+4F0h] [rbp+3F0h] BYREF

  memset_0(&v26, 0, 0x98u);
  OutputString[0] = 0;
  v46[0] = 0;
  v15 = *a7;
  v16 = a7[1];
  v28 = v15;
  v29 = v16;
  if ( v15 >= 0 )
  {
    v15 = -2147024228;
    LODWORD(v25) = -2147024228;
    wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v25);
    v28 = -2147024228;
    v29 = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v17);
  }
  v18 = wil::details::RecordLog((wil::details *)(unsigned int)v15, v14);
  v24 = a7[2] == 1;
  v19 = v18;
  v26 = 2;
  v27 = a10;
  if ( v24 )
    v27 = a10 | 8;
  v30 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v31 = a8, !*a8) )
    v31 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v35 = a3;
  v32 = CurrentThreadId;
  v44 = a6;
  v42 = 0;
  v40 = 0;
  v36 = a2;
  v37 = v19;
  v33 = a5;
  v34 = a4;
  v45 = a1;
  v38 = 0;
  v41 = 0;
  v39 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v22);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v26);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v26, v46, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v26);
  if ( wil::details::g_pfnOriginateCallback && (v27 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v26);
  if ( v28 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v24 = !IsDebuggerPresent())
      : (v24 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v24)
    || (v27 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v26, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v26, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v26, v23);
    OutputDebugStringW(OutputString);
  }
  if ( ((v27 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v22);
  if ( (v27 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v26, v21);
}

```

## disassembly

```asm
0x180003288  push    rbp
0x18000328a  push    rbx
0x18000328b  push    rsi
0x18000328c  push    rdi
0x18000328d  push    r12
0x18000328f  push    r13
0x180003291  push    r14
0x180003293  push    r15
0x180003295  lea     rbp, [rsp-1408h]
0x18000329d  mov     eax, 1508h
0x1800032a2  call    _alloca_probe
0x1800032a7  sub     rsp, rax
0x1800032aa  mov     rax, cs:__security_cookie
0x1800032b1  xor     rax, rsp
0x1800032b4  mov     [rbp+1440h+var_50], rax
0x1800032bb  mov     rax, [rbp+1440h+arg_28]
0x1800032c2  mov     r15, r8
0x1800032c5  mov     r13, [rbp+1440h+arg_20]
0x1800032cc  mov     r14d, edx
0x1800032cf  mov     rsi, rcx
0x1800032d2  mov     [rsp+1540h+var_1500], rax
0x1800032d7  xor     edx, edx; Val
0x1800032d9  lea     rcx, [rsp+1540h+var_14F0]; void *
0x1800032de  mov     r8d, 98h; Size
0x1800032e4  mov     r12, r9
0x1800032e7  call    memset_0
0x1800032ec  mov     rdi, [rbp+1440h+arg_30]
0x1800032f3  xor     eax, eax
0x1800032f5  mov     [rbp+1440h+OutputString], ax
0x1800032fc  mov     [rbp+1440h+var_1450], al
0x1800032ff  mov     ebx, [rdi]
0x180003301  mov     eax, [rdi+4]
0x180003304  mov     [rsp+1540h+var_14E8], ebx
0x180003308  mov     [rsp+1540h+var_14E4], eax
0x18000330c  test    ebx, ebx
0x18000330e  js      short loc_180003350
0x180003310  mov     rax, [rsp+1540h+var_1500]
0x180003315  mov     ebx, 8007029Ch
0x18000331a  mov     [rsp+1540h+var_1508], 0
0x180003322  mov     r9, r12; int
0x180003325  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x180003329  mov     r8, r15; int
0x18000332c  mov     [rsp+1540h+var_1518], rax; __int64
0x180003331  mov     edx, r14d; int
0x180003334  mov     rcx, rsi; int
0x180003337  mov     [rsp+1540h+var_1520], r13; __int64
0x18000333c  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180003341  mov     ecx, ebx; this
0x180003343  mov     [rsp+1540h+var_14E8], ebx
0x180003347  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000334c  mov     [rsp+1540h+var_14E4], eax
0x180003350  mov     ecx, ebx; this
0x180003352  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180003357  cmp     dword ptr [rdi+8], 1
0x18000335b  mov     ebx, eax
0x18000335d  mov     ecx, [rbp+1440h+arg_48]
0x180003363  mov     dword ptr [rsp+1540h+var_14F0], 2
0x18000336b  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x18000336f  jnz     short loc_180003378
0x180003371  or      ecx, 8
0x180003374  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x180003378  mov     ecx, 1
0x18000337d  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003385  mov     rax, [rbp+1440h+arg_38]
0x18000338c  inc     ecx
0x18000338e  xor     edi, edi
0x180003390  mov     [rsp+1540h+var_14E0], ecx
0x180003394  test    rax, rax
0x180003397  jz      short loc_1800033A3
0x180003399  mov     [rsp+1540h+var_14D8], rax
0x18000339e  cmp     [rax], di
0x1800033a1  jnz     short loc_1800033A8
0x1800033a3  mov     [rsp+1540h+var_14D8], rdi
0x1800033a8  call    cs:__imp_GetCurrentThreadId
0x1800033ae  xorps   xmm0, xmm0
0x1800033b1  mov     [rbp+1440h+var_14B8], r15
0x1800033b5  mov     [rsp+1540h+var_14D0], eax
0x1800033b9  xorps   xmm1, xmm1
0x1800033bc  mov     rax, [rsp+1540h+var_1500]
0x1800033c1  mov     [rbp+1440h+var_1468], rax
0x1800033c5  xor     eax, eax
0x1800033c7  mov     [rbp+1440h+var_1478], rax
0x1800033cb  mov     [rbp+1440h+var_1490], rax
0x1800033cf  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800033d6  mov     [rbp+1440h+var_14B0], r14d
0x1800033da  mov     [rbp+1440h+var_14AC], ebx
0x1800033dd  mov     [rsp+1540h+var_14C8], r13
0x1800033e2  mov     [rbp+1440h+var_14C0], r12
0x1800033e6  mov     [rbp+1440h+var_1460], rsi
0x1800033ea  mov     [rbp+1440h+var_14A8], rdi
0x1800033ee  movups  [rbp+1440h+var_1488], xmm0
0x1800033f2  movups  [rbp+1440h+var_14A0], xmm1
0x1800033f6  test    rax, rax
0x1800033f9  jz      short loc_180003406
0x1800033fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003400  mov     [rbp+1440h+var_1470], rax
0x180003404  jmp     short loc_18000340A
0x180003406  mov     [rbp+1440h+var_1470], rdi
0x18000340a  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003411  test    rax, rax
0x180003414  jz      short loc_180003420
0x180003416  lea     rcx, [rsp+1540h+var_14F0]
0x18000341b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003420  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003427  test    rax, rax
0x18000342a  jz      short loc_180003440
0x18000342c  mov     r8d, 400h
0x180003432  lea     rdx, [rbp+1440h+var_1450]
0x180003436  lea     rcx, [rsp+1540h+var_14F0]
0x18000343b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003440  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003447  test    rax, rax
0x18000344a  jz      short loc_180003456
0x18000344c  lea     rcx, [rsp+1540h+var_14F0]
0x180003451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003456  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000345d  test    rax, rax
0x180003460  jz      short loc_180003473
0x180003462  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x180003467  jnz     short loc_180003473
0x180003469  lea     rcx, [rsp+1540h+var_14F0]
0x18000346e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003473  cmp     [rsp+1540h+var_14E8], edi
0x180003477  jge     loc_180003575
0x18000347d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180003484  jnz     short loc_1800034A5
0x180003486  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000348d  test    rax, rax
0x180003490  jz      short loc_18000349B
0x180003492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003497  test    al, al
0x180003499  jmp     short loc_1800034A3
0x18000349b  call    cs:__imp_IsDebuggerPresent
0x1800034a1  test    eax, eax
0x1800034a3  jz      short loc_1800034AC
0x1800034a5  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x1800034aa  jz      short loc_1800034D2
0x1800034ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034b3  test    rax, rax
0x1800034b6  jz      short loc_18000352A
0x1800034b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800034bf  jnz     short loc_18000352A
0x1800034c1  xor     r8d, r8d
0x1800034c4  lea     rcx, [rsp+1540h+var_14F0]
0x1800034c9  xor     edx, edx
0x1800034cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d0  jmp     short loc_18000352A
0x1800034d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800034d9  mov     ebx, 800h
0x1800034de  test    rax, rax
0x1800034e1  jz      short loc_180003500
0x1800034e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800034ea  jnz     short loc_180003500
0x1800034ec  mov     r8d, ebx
0x1800034ef  lea     rdx, [rbp+1440h+OutputString]
0x1800034f6  lea     rcx, [rsp+1540h+var_14F0]
0x1800034fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003500  cmp     [rbp+1440h+OutputString], di
0x180003507  jnz     short loc_18000351D
0x180003509  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x18000350e  mov     rdx, rbx; unsigned __int16 *
0x180003511  lea     rcx, [rbp+1440h+OutputString]; this
0x180003518  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000351d  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x180003524  call    cs:__imp_OutputDebugStringW
0x18000352a  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x18000352f  jnz     short loc_18000353A
0x180003531  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180003538  jz      short loc_18000354B
0x18000353a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003541  test    rax, rax
0x180003544  jz      short loc_18000354B
0x180003546  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000354b  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x180003550  jnz     short loc_18000357B
0x180003552  mov     rcx, [rbp+1440h+var_50]
0x180003559  xor     rcx, rsp; StackCookie
0x18000355c  call    __security_check_cookie
0x180003561  add     rsp, 1508h
0x180003568  pop     r15
0x18000356a  pop     r14
0x18000356c  pop     r13
0x18000356e  pop     r12
0x180003570  pop     rdi
0x180003571  pop     rsi
0x180003572  pop     rbx
0x180003573  pop     rbp
0x180003574  retn
0x180003575  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000357b  lea     rcx, [rsp+1540h+var_14F0]; this
0x180003580  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
