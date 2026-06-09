# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003f18`
- end: `0x1800041a5`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003d60`

## callees

- `0x1800016c0`
- `0x180002158`
- `0x180003f18`
- `0x180005088`
- `0x180006000`
- `0x18000687c`
- `0x180006958`
- `0x180011440`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fc6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003fc6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004144`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004144`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800040ba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800040ba`

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
0x180003f18  push    rbp
0x180003f1a  push    rbx
0x180003f1b  push    rsi
0x180003f1c  push    rdi
0x180003f1d  push    r12
0x180003f1f  push    r14
0x180003f21  push    r15
0x180003f23  lea     rbp, [rsp-13D0h]
0x180003f2b  mov     eax, 14D0h
0x180003f30  call    _alloca_probe
0x180003f35  sub     rsp, rax
0x180003f38  mov     rax, cs:__security_cookie
0x180003f3f  xor     rax, rsp
0x180003f42  mov     [rbp+1400h+var_40], rax
0x180003f49  mov     r14, r8
0x180003f4c  mov     esi, edx
0x180003f4e  mov     r15, rcx
0x180003f51  mov     rdi, [rbp+1400h+arg_28]
0x180003f58  xor     edx, edx; Val
0x180003f5a  mov     r8d, 98h; Size
0x180003f60  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003f65  call    memset_0
0x180003f6a  nop
0x180003f6b  xor     r12d, r12d
0x180003f6e  mov     [rbp+1400h+OutputString], r12w
0x180003f76  mov     [rbp+1400h+var_1440], r12b
0x180003f7a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180003f81  mov     ecx, [rdx]; this
0x180003f83  mov     [rsp+1500h+var_14D8], ecx
0x180003f87  mov     eax, [rdx+4]
0x180003f8a  mov     [rsp+1500h+var_14D4], eax
0x180003f8e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003f93  mov     ebx, eax
0x180003f95  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003f9d  mov     ecx, r12d
0x180003fa0  lea     eax, [r12+8]
0x180003fa5  cmp     dword ptr [rdx+8], 1
0x180003fa9  cmovz   ecx, eax
0x180003fac  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180003fb0  lea     ecx, [rax-7]
0x180003fb3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003fbb  inc     ecx
0x180003fbd  mov     [rsp+1500h+var_14D0], ecx
0x180003fc1  mov     [rsp+1500h+var_14C8], r12
0x180003fc6  call    cs:__imp_GetCurrentThreadId
0x180003fcc  mov     [rsp+1500h+var_14C0], eax
0x180003fd0  mov     [rsp+1500h+var_14A8], r14
0x180003fd5  mov     [rsp+1500h+var_14A0], esi
0x180003fd9  mov     [rsp+1500h+var_149C], ebx
0x180003fdd  mov     [rsp+1500h+var_14B8], r12
0x180003fe2  mov     [rsp+1500h+var_14B0], r12
0x180003fe7  mov     [rbp+1400h+var_1458], rdi
0x180003feb  mov     [rbp+1400h+var_1450], r15
0x180003fef  mov     [rsp+1500h+var_1498], r12
0x180003ff4  xorps   xmm0, xmm0
0x180003ff7  xor     eax, eax
0x180003ff9  movups  [rbp+1400h+var_1478], xmm0
0x180003ffd  mov     [rbp+1400h+var_1468], rax
0x180004001  xorps   xmm1, xmm1
0x180004004  movups  [rsp+1500h+var_1490], xmm1
0x180004009  mov     [rbp+1400h+var_1480], rax
0x18000400d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004014  test    rax, rax
0x180004017  jz      short loc_180004024
0x180004019  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000401e  mov     [rbp+1400h+var_1460], rax
0x180004022  jmp     short loc_180004028
0x180004024  mov     [rbp+1400h+var_1460], r12
0x180004028  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000402f  test    rax, rax
0x180004032  jz      short loc_18000403E
0x180004034  lea     rcx, [rsp+1500h+var_14E0]
0x180004039  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000403e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004045  test    rax, rax
0x180004048  jz      short loc_18000405E
0x18000404a  mov     r8d, 400h
0x180004050  lea     rdx, [rbp+1400h+var_1440]
0x180004054  lea     rcx, [rsp+1500h+var_14E0]
0x180004059  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000405e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004065  test    rax, rax
0x180004068  jz      short loc_180004074
0x18000406a  lea     rcx, [rsp+1500h+var_14E0]
0x18000406f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004074  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000407b  test    rax, rax
0x18000407e  jz      short loc_180004091
0x180004080  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004085  jnz     short loc_180004091
0x180004087  lea     rcx, [rsp+1500h+var_14E0]
0x18000408c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004091  cmp     [rsp+1500h+var_14D8], r12d
0x180004096  jge     loc_18000419F
0x18000409c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800040a3  jnz     short loc_1800040C4
0x1800040a5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800040ac  test    rax, rax
0x1800040af  jz      short loc_1800040BA
0x1800040b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040b6  test    al, al
0x1800040b8  jmp     short loc_1800040C2
0x1800040ba  call    cs:__imp_IsDebuggerPresent
0x1800040c0  test    eax, eax
0x1800040c2  jz      short loc_1800040CB
0x1800040c4  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800040c9  jz      short loc_1800040F1
0x1800040cb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800040d2  test    rax, rax
0x1800040d5  jz      short loc_18000414A
0x1800040d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800040de  jnz     short loc_18000414A
0x1800040e0  xor     r8d, r8d
0x1800040e3  xor     edx, edx
0x1800040e5  lea     rcx, [rsp+1500h+var_14E0]
0x1800040ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800040ef  jmp     short loc_18000414A
0x1800040f1  mov     ebx, 800h
0x1800040f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800040fd  test    rax, rax
0x180004100  jz      short loc_18000411F
0x180004102  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004109  jnz     short loc_18000411F
0x18000410b  mov     r8d, ebx
0x18000410e  lea     rdx, [rbp+1400h+OutputString]
0x180004115  lea     rcx, [rsp+1500h+var_14E0]
0x18000411a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000411f  cmp     [rbp+1400h+OutputString], r12w
0x180004127  jnz     short loc_18000413D
0x180004129  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000412e  mov     rdx, rbx; unsigned __int16 *
0x180004131  lea     rcx, [rbp+1400h+OutputString]; this
0x180004138  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000413d  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004144  call    cs:__imp_OutputDebugStringW
0x18000414a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000414f  jnz     short loc_18000415A
0x180004151  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004158  jz      short loc_18000416C
0x18000415a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004161  test    rax, rax
0x180004164  jz      short loc_18000416C
0x180004166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000416b  nop
0x18000416c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004171  jnz     short loc_180004194
0x180004173  mov     rcx, [rbp+1400h+var_40]
0x18000417a  xor     rcx, rsp; StackCookie
0x18000417d  call    __security_check_cookie
0x180004182  add     rsp, 14D0h
0x180004189  pop     r15
0x18000418b  pop     r14
0x18000418d  pop     r12
0x18000418f  pop     rdi
0x180004190  pop     rsi
0x180004191  pop     rbx
0x180004192  pop     rbp
0x180004193  retn
0x180004194  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004199  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000419f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
