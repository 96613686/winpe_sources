# wil::details::ReportFailure_Return<2>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140006f5c`
- end: `0x140007254`
- name: `??$ReportFailure_Return@$01@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int *, _WORD *, int, int)`
- caller_count: `1`
- callee_count: `11`
- tags: ``

## callers

- `0x140006418`

## callees

- `0x1400054c0`
- `0x1400060f8`
- `0x1400067e0`
- `0x140006f5c`
- `0x140008e14`
- `0x140009674`
- `0x140009e04`
- `0x14000c470`
- `0x14000c54c`
- `0x1400562f0`
- `0x14005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007075`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140007075`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400071f1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400071f1`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007168`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007168`

## pseudocode

```c
// Hidden C++ exception states: #wind=10
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v23, v20);
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
0x140006f5c  push    rbp
0x140006f5e  push    rbx
0x140006f5f  push    rsi
0x140006f60  push    rdi
0x140006f61  push    r12
0x140006f63  push    r13
0x140006f65  push    r14
0x140006f67  push    r15
0x140006f69  lea     rbp, [rsp-1408h]
0x140006f71  mov     eax, 1508h
0x140006f76  call    _alloca_probe
0x140006f7b  sub     rsp, rax
0x140006f7e  mov     rax, cs:__security_cookie
0x140006f85  xor     rax, rsp
0x140006f88  mov     [rbp+1440h+var_50], rax
0x140006f8f  mov     r12, r9
0x140006f92  mov     r15, r8
0x140006f95  mov     r14d, edx
0x140006f98  mov     rsi, rcx
0x140006f9b  mov     r13, [rbp+1440h+arg_20]
0x140006fa2  mov     rax, [rbp+1440h+arg_28]
0x140006fa9  mov     [rsp+1540h+var_1500], rax
0x140006fae  xor     edx, edx; Val
0x140006fb0  mov     r8d, 98h; Size
0x140006fb6  lea     rcx, [rsp+1540h+var_14F0]; void *
0x140006fbb  call    memset_0
0x140006fc0  nop
0x140006fc1  xor     eax, eax
0x140006fc3  mov     [rbp+1440h+OutputString], ax
0x140006fca  mov     [rbp+1440h+var_1450], al
0x140006fcd  mov     rdi, [rbp+1440h+arg_30]
0x140006fd4  mov     ebx, [rdi]
0x140006fd6  mov     [rsp+1540h+var_14E8], ebx
0x140006fda  mov     eax, [rdi+4]
0x140006fdd  mov     [rsp+1540h+var_14E4], eax
0x140006fe1  test    ebx, ebx
0x140006fe3  js      short loc_14000701D
0x140006fe5  mov     ebx, 8007029Ch
0x140006fea  mov     dword ptr [rsp+1540h+var_1510], ebx; wil::details *
0x140006fee  mov     rax, [rsp+1540h+var_1500]
0x140006ff3  mov     [rsp+1540h+var_1518], rax; __int64
0x140006ff8  mov     [rsp+1540h+var_1520], r13; __int64
0x140006ffd  mov     r9, r12; int
0x140007000  mov     r8, r15; int
0x140007003  mov     edx, r14d; int
0x140007006  mov     rcx, rsi; int
0x140007009  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000700e  mov     [rsp+1540h+var_14E8], ebx
0x140007012  mov     ecx, ebx; this
0x140007014  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007019  mov     [rsp+1540h+var_14E4], eax
0x14000701d  mov     ecx, ebx; this
0x14000701f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007024  mov     ebx, eax
0x140007026  mov     dword ptr [rsp+1540h+var_14F0], 2
0x14000702e  mov     ecx, [rbp+1440h+arg_48]
0x140007034  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140007038  cmp     dword ptr [rdi+8], 1
0x14000703c  jnz     short loc_140007045
0x14000703e  or      ecx, 8
0x140007041  mov     dword ptr [rsp+1540h+var_14F0+4], ecx
0x140007045  mov     ecx, 1
0x14000704a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007052  inc     ecx
0x140007054  mov     [rsp+1540h+var_14E0], ecx
0x140007058  mov     rax, [rbp+1440h+arg_38]
0x14000705f  xor     edi, edi
0x140007061  test    rax, rax
0x140007064  jz      short loc_140007070
0x140007066  cmp     [rax], di
0x140007069  mov     [rsp+1540h+var_14D8], rax
0x14000706e  jnz     short loc_140007075
0x140007070  mov     [rsp+1540h+var_14D8], rdi
0x140007075  call    cs:__imp_GetCurrentThreadId
0x14000707b  mov     [rsp+1540h+var_14D0], eax
0x14000707f  mov     [rbp+1440h+var_14B8], r15
0x140007083  mov     [rbp+1440h+var_14B0], r14d
0x140007087  mov     [rbp+1440h+var_14AC], ebx
0x14000708a  mov     [rsp+1540h+var_14C8], r13
0x14000708f  mov     [rbp+1440h+var_14C0], r12
0x140007093  mov     rax, [rsp+1540h+var_1500]
0x140007098  mov     [rbp+1440h+var_1468], rax
0x14000709c  mov     [rbp+1440h+var_1460], rsi
0x1400070a0  mov     [rbp+1440h+var_14A8], rdi
0x1400070a4  xorps   xmm0, xmm0
0x1400070a7  xor     eax, eax
0x1400070a9  movups  [rbp+1440h+var_1488], xmm0
0x1400070ad  mov     [rbp+1440h+var_1478], rax
0x1400070b1  xorps   xmm1, xmm1
0x1400070b4  movups  [rbp+1440h+var_14A0], xmm1
0x1400070b8  mov     [rbp+1440h+var_1490], rax
0x1400070bc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400070c3  test    rax, rax
0x1400070c6  jz      short loc_1400070D3
0x1400070c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070cd  mov     [rbp+1440h+var_1470], rax
0x1400070d1  jmp     short loc_1400070D7
0x1400070d3  mov     [rbp+1440h+var_1470], rdi
0x1400070d7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400070de  test    rax, rax
0x1400070e1  jz      short loc_1400070ED
0x1400070e3  lea     rcx, [rsp+1540h+var_14F0]
0x1400070e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400070f4  test    rax, rax
0x1400070f7  jz      short loc_14000710D
0x1400070f9  mov     r8d, 400h
0x1400070ff  lea     rdx, [rbp+1440h+var_1450]
0x140007103  lea     rcx, [rsp+1540h+var_14F0]
0x140007108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000710d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007114  test    rax, rax
0x140007117  jz      short loc_140007123
0x140007119  lea     rcx, [rsp+1540h+var_14F0]
0x14000711e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007123  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000712a  test    rax, rax
0x14000712d  jz      short loc_140007140
0x14000712f  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140007134  jnz     short loc_140007140
0x140007136  lea     rcx, [rsp+1540h+var_14F0]
0x14000713b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007140  cmp     [rsp+1540h+var_14E8], edi
0x140007144  jge     loc_14000724E
0x14000714a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007151  jnz     short loc_140007172
0x140007153  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000715a  test    rax, rax
0x14000715d  jz      short loc_140007168
0x14000715f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007164  test    al, al
0x140007166  jmp     short loc_140007170
0x140007168  call    cs:__imp_IsDebuggerPresent
0x14000716e  test    eax, eax
0x140007170  jz      short loc_140007179
0x140007172  test    byte ptr [rsp+1540h+var_14F0+4], 2
0x140007177  jz      short loc_14000719F
0x140007179  mov     rax, cs:g_pfnResultLoggingCallback
0x140007180  test    rax, rax
0x140007183  jz      short loc_1400071F7
0x140007185  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000718c  jnz     short loc_1400071F7
0x14000718e  xor     r8d, r8d
0x140007191  xor     edx, edx
0x140007193  lea     rcx, [rsp+1540h+var_14F0]
0x140007198  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000719d  jmp     short loc_1400071F7
0x14000719f  mov     ebx, 800h
0x1400071a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1400071ab  test    rax, rax
0x1400071ae  jz      short loc_1400071CD
0x1400071b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400071b7  jnz     short loc_1400071CD
0x1400071b9  mov     r8d, ebx
0x1400071bc  lea     rdx, [rbp+1440h+OutputString]
0x1400071c3  lea     rcx, [rsp+1540h+var_14F0]
0x1400071c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071cd  cmp     [rbp+1440h+OutputString], di
0x1400071d4  jnz     short loc_1400071EA
0x1400071d6  lea     r8, [rsp+1540h+var_14F0]; unsigned __int64
0x1400071db  mov     rdx, rbx; unsigned __int16 *
0x1400071de  lea     rcx, [rbp+1440h+OutputString]; this
0x1400071e5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400071ea  lea     rcx, [rbp+1440h+OutputString]; lpOutputString
0x1400071f1  call    cs:__imp_OutputDebugStringW
0x1400071f7  test    byte ptr [rsp+1540h+var_14F0+4], 4
0x1400071fc  jnz     short loc_140007207
0x1400071fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007205  jz      short loc_140007219
0x140007207  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000720e  test    rax, rax
0x140007211  jz      short loc_140007219
0x140007213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007218  nop
0x140007219  test    byte ptr [rsp+1540h+var_14F0+4], 1
0x14000721e  jnz     short loc_140007243
0x140007220  mov     rcx, [rbp+1440h+var_50]
0x140007227  xor     rcx, rsp; StackCookie
0x14000722a  call    __security_check_cookie
0x14000722f  add     rsp, 1508h
0x140007236  pop     r15
0x140007238  pop     r14
0x14000723a  pop     r13
0x14000723c  pop     r12
0x14000723e  pop     rdi
0x14000723f  pop     rsi
0x140007240  pop     rbx
0x140007241  pop     rbp
0x140007242  retn
0x140007243  lea     rcx, [rsp+1540h+var_14F0]; this
0x140007248  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000724e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
