# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004fd4`
- end: `0x18000524d`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180004994`

## callees

- `0x180004118`
- `0x180004fd4`
- `0x180007d64`
- `0x1800085cc`
- `0x180008f20`
- `0x18000a0b0`
- `0x180027cb0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000508d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000508d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005190`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005190`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000521a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000521a`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // edx
  int v12; // r12d
  int v13; // ecx
  const struct wil::FailureInfo *v14; // rdx
  __int64 v15; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, v11);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v12;
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
  {
    v20 = -2147418113;
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v14);
  }
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
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v15);
  }
  wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x180004fd4  mov     [rsp-8+arg_18], rbx
0x180004fd9  push    rbp
0x180004fda  push    rsi
0x180004fdb  push    rdi
0x180004fdc  push    r12
0x180004fde  push    r13
0x180004fe0  push    r14
0x180004fe2  push    r15
0x180004fe4  lea     rbp, [rsp-13C0h]
0x180004fec  mov     eax, 14C0h
0x180004ff1  call    _alloca_probe
0x180004ff6  sub     rsp, rax
0x180004ff9  mov     r14, r8
0x180004ffc  mov     esi, edx
0x180004ffe  mov     rdi, rcx
0x180005001  mov     r15, [rbp+13F0h+arg_28]
0x180005008  xor     edx, edx; Val
0x18000500a  mov     r8d, 98h; Size
0x180005010  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180005015  call    memset_0
0x18000501a  nop
0x18000501b  xor     r13d, r13d
0x18000501e  mov     [rbp+13F0h+OutputString], r13w
0x180005026  mov     [rbp+13F0h+var_1430], r13b
0x18000502a  mov     rbx, [rbp+13F0h+arg_30]
0x180005031  mov     ecx, [rbx]; this
0x180005033  mov     [rsp+14F0h+var_14C8], ecx
0x180005037  mov     eax, [rbx+4]
0x18000503a  mov     [rsp+14F0h+var_14C4], eax
0x18000503e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005043  mov     r12d, eax
0x180005046  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000504e  mov     ecx, r13d
0x180005051  lea     eax, [r13+8]
0x180005055  cmp     dword ptr [rbx+8], 1
0x180005059  cmovz   ecx, eax
0x18000505c  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180005060  lea     ecx, [rax-7]
0x180005063  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000506b  inc     ecx
0x18000506d  mov     [rsp+14F0h+var_14C0], ecx
0x180005071  mov     rcx, [rbp+13F0h+arg_38]
0x180005078  test    rcx, rcx
0x18000507b  jz      short loc_180005088
0x18000507d  cmp     [rcx], r13w
0x180005081  mov     [rsp+14F0h+var_14B8], rcx
0x180005086  jnz     short loc_18000508D
0x180005088  mov     [rsp+14F0h+var_14B8], r13
0x18000508d  call    cs:__imp_GetCurrentThreadId
0x180005093  mov     [rsp+14F0h+var_14B0], eax
0x180005097  mov     [rsp+14F0h+var_1498], r14
0x18000509c  mov     [rsp+14F0h+var_1490], esi
0x1800050a0  mov     [rsp+14F0h+var_148C], r12d
0x1800050a5  mov     [rsp+14F0h+var_14A8], r13
0x1800050aa  mov     [rsp+14F0h+var_14A0], r13
0x1800050af  mov     [rbp+13F0h+var_1448], r15
0x1800050b3  mov     [rbp+13F0h+var_1440], rdi
0x1800050b7  mov     [rsp+14F0h+var_1488], r13
0x1800050bc  xorps   xmm0, xmm0
0x1800050bf  xor     eax, eax
0x1800050c1  movups  [rbp+13F0h+var_1468], xmm0
0x1800050c5  mov     [rbp+13F0h+var_1458], rax
0x1800050c9  xorps   xmm1, xmm1
0x1800050cc  movups  [rsp+14F0h+var_1480], xmm1
0x1800050d1  mov     [rbp+13F0h+var_1470], rax
0x1800050d5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800050dc  test    rax, rax
0x1800050df  jz      short loc_1800050EC
0x1800050e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e6  mov     [rbp+13F0h+var_1450], rax
0x1800050ea  jmp     short loc_1800050F0
0x1800050ec  mov     [rbp+13F0h+var_1450], r13
0x1800050f0  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800050f7  test    rax, rax
0x1800050fa  jz      short loc_180005106
0x1800050fc  lea     rcx, [rsp+14F0h+var_14D0]
0x180005101  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005106  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000510d  test    rax, rax
0x180005110  jz      short loc_180005126
0x180005112  mov     r8d, 400h
0x180005118  lea     rdx, [rbp+13F0h+var_1430]
0x18000511c  lea     rcx, [rsp+14F0h+var_14D0]
0x180005121  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005126  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000512d  test    rax, rax
0x180005130  jz      short loc_18000513C
0x180005132  lea     rcx, [rsp+14F0h+var_14D0]
0x180005137  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000513c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005143  test    rax, rax
0x180005146  jz      short loc_180005159
0x180005148  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000514d  jnz     short loc_180005159
0x18000514f  lea     rcx, [rsp+14F0h+var_14D0]
0x180005154  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005159  cmp     [rsp+14F0h+var_14C8], r13d
0x18000515e  jl      short loc_180005172
0x180005160  mov     ecx, 8000FFFFh; this
0x180005165  mov     [rsp+14F0h+var_14C8], ecx
0x180005169  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000516e  mov     [rsp+14F0h+var_14C4], eax
0x180005172  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180005179  jnz     short loc_18000519A
0x18000517b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005182  test    rax, rax
0x180005185  jz      short loc_180005190
0x180005187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518c  test    al, al
0x18000518e  jmp     short loc_180005198
0x180005190  call    cs:__imp_IsDebuggerPresent
0x180005196  test    eax, eax
0x180005198  jz      short loc_1800051A1
0x18000519a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000519f  jz      short loc_1800051C7
0x1800051a1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051a8  test    rax, rax
0x1800051ab  jz      short loc_180005220
0x1800051ad  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800051b4  jnz     short loc_180005220
0x1800051b6  xor     r8d, r8d
0x1800051b9  xor     edx, edx
0x1800051bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800051c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051c5  jmp     short loc_180005220
0x1800051c7  mov     ebx, 800h
0x1800051cc  mov     rax, cs:g_pfnResultLoggingCallback
0x1800051d3  test    rax, rax
0x1800051d6  jz      short loc_1800051F5
0x1800051d8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800051df  jnz     short loc_1800051F5
0x1800051e1  mov     r8d, ebx
0x1800051e4  lea     rdx, [rbp+13F0h+OutputString]
0x1800051eb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800051f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051f5  cmp     [rbp+13F0h+OutputString], r13w
0x1800051fd  jnz     short loc_180005213
0x1800051ff  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180005204  mov     rdx, rbx; unsigned __int16 *
0x180005207  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000520e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005213  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000521a  call    cs:__imp_OutputDebugStringW
0x180005220  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180005225  jnz     short loc_180005230
0x180005227  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000522e  jz      short loc_180005242
0x180005230  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005237  test    rax, rax
0x18000523a  jz      short loc_180005242
0x18000523c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005241  nop
0x180005242  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180005247  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
