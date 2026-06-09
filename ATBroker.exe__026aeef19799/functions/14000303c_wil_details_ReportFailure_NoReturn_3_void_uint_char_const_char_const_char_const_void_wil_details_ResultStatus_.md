# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x14000303c`
- end: `0x14000329c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002dd8`

## callees

- `0x14000303c`
- `0x140005c44`
- `0x140006608`
- `0x140007f00`
- `0x14000a590`
- `0x140015ac2`
- `0x140015b90`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400030dd`
- `KERNEL32!GetCurrentThreadId` at `0x1400030dd`
- `KERNEL32!OutputDebugStringW` at `0x14000326a`
- `KERNEL32!OutputDebugStringW` at `0x14000326a`
- `KERNEL32!IsDebuggerPresent` at `0x1400031e0`
- `KERNEL32!IsDebuggerPresent` at `0x1400031e0`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v10; // eax
  int v11; // edx
  int v12; // eax
  int v13; // edi
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v22, v11);
  v19 = a7[2] == 1;
  v13 = v12;
  v20 = 3;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
  {
    v22 = -2147418113;
    v23 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v16);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( (v21 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v17);
  }
  wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x14000303c  mov     [rsp-8+arg_18], rbx
0x140003041  push    rbp
0x140003042  push    rsi
0x140003043  push    rdi
0x140003044  push    r12
0x140003046  push    r13
0x140003048  push    r14
0x14000304a  push    r15
0x14000304c  lea     rbp, [rsp-13C0h]
0x140003054  mov     eax, 14C0h
0x140003059  call    _alloca_probe
0x14000305e  sub     rsp, rax
0x140003061  mov     rsi, [rbp+13F0h+arg_28]
0x140003068  mov     r15, r8
0x14000306b  mov     r14d, edx
0x14000306e  mov     r12, rcx
0x140003071  xor     edx, edx; Val
0x140003073  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140003078  mov     r8d, 98h; Size
0x14000307e  call    memset_0
0x140003083  mov     rbx, [rbp+13F0h+arg_30]
0x14000308a  xor     r13d, r13d
0x14000308d  mov     [rbp+13F0h+OutputString], r13w
0x140003095  mov     [rbp+13F0h+var_1430], r13b
0x140003099  mov     ecx, [rbx]; this
0x14000309b  mov     eax, [rbx+4]
0x14000309e  mov     [rsp+14F0h+var_14C8], ecx
0x1400030a2  mov     [rsp+14F0h+var_14C4], eax
0x1400030a6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400030ab  cmp     dword ptr [rbx+8], 1
0x1400030af  mov     edi, eax
0x1400030b1  lea     eax, [r13+8]
0x1400030b5  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1400030bd  mov     ecx, r13d
0x1400030c0  cmovz   ecx, eax
0x1400030c3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400030c7  lea     ecx, [rax-7]
0x1400030ca  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400030d2  inc     ecx
0x1400030d4  mov     [rsp+14F0h+var_14B8], r13
0x1400030d9  mov     [rsp+14F0h+var_14C0], ecx
0x1400030dd  call    cs:__imp_GetCurrentThreadId
0x1400030e3  xorps   xmm0, xmm0
0x1400030e6  mov     [rsp+14F0h+var_1498], r15
0x1400030eb  mov     [rsp+14F0h+var_14B0], eax
0x1400030ef  xorps   xmm1, xmm1
0x1400030f2  xor     eax, eax
0x1400030f4  mov     [rsp+14F0h+var_1490], r14d
0x1400030f9  mov     [rbp+13F0h+var_1458], rax
0x1400030fd  mov     [rbp+13F0h+var_1470], rax
0x140003101  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003108  mov     [rsp+14F0h+var_148C], edi
0x14000310c  mov     [rsp+14F0h+var_14A8], r13
0x140003111  mov     [rsp+14F0h+var_14A0], r13
0x140003116  mov     [rbp+13F0h+var_1448], rsi
0x14000311a  mov     [rbp+13F0h+var_1440], r12
0x14000311e  mov     [rsp+14F0h+var_1488], r13
0x140003123  movups  [rbp+13F0h+var_1468], xmm0
0x140003127  movups  [rsp+14F0h+var_1480], xmm1
0x14000312c  test    rax, rax
0x14000312f  jz      short loc_14000313C
0x140003131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003136  mov     [rbp+13F0h+var_1450], rax
0x14000313a  jmp     short loc_140003140
0x14000313c  mov     [rbp+13F0h+var_1450], r13
0x140003140  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003147  test    rax, rax
0x14000314a  jz      short loc_140003156
0x14000314c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003156  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000315d  test    rax, rax
0x140003160  jz      short loc_140003176
0x140003162  mov     r8d, 400h
0x140003168  lea     rdx, [rbp+13F0h+var_1430]
0x14000316c  lea     rcx, [rsp+14F0h+var_14D0]
0x140003171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003176  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000317d  test    rax, rax
0x140003180  jz      short loc_14000318C
0x140003182  lea     rcx, [rsp+14F0h+var_14D0]
0x140003187  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000318c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003193  test    rax, rax
0x140003196  jz      short loc_1400031A9
0x140003198  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x14000319d  jnz     short loc_1400031A9
0x14000319f  lea     rcx, [rsp+14F0h+var_14D0]
0x1400031a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031a9  cmp     [rsp+14F0h+var_14C8], r13d
0x1400031ae  jl      short loc_1400031C2
0x1400031b0  mov     ecx, 8000FFFFh; this
0x1400031b5  mov     [rsp+14F0h+var_14C8], ecx
0x1400031b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400031be  mov     [rsp+14F0h+var_14C4], eax
0x1400031c2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400031c9  jnz     short loc_1400031EA
0x1400031cb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400031d2  test    rax, rax
0x1400031d5  jz      short loc_1400031E0
0x1400031d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400031dc  test    al, al
0x1400031de  jmp     short loc_1400031E8
0x1400031e0  call    cs:__imp_IsDebuggerPresent
0x1400031e6  test    eax, eax
0x1400031e8  jz      short loc_1400031F1
0x1400031ea  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400031ef  jz      short loc_140003217
0x1400031f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1400031f8  test    rax, rax
0x1400031fb  jz      short loc_140003270
0x1400031fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140003204  jnz     short loc_140003270
0x140003206  xor     r8d, r8d
0x140003209  lea     rcx, [rsp+14F0h+var_14D0]
0x14000320e  xor     edx, edx
0x140003210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003215  jmp     short loc_140003270
0x140003217  mov     rax, cs:g_pfnResultLoggingCallback
0x14000321e  mov     ebx, 800h
0x140003223  test    rax, rax
0x140003226  jz      short loc_140003245
0x140003228  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x14000322f  jnz     short loc_140003245
0x140003231  mov     r8d, ebx
0x140003234  lea     rdx, [rbp+13F0h+OutputString]
0x14000323b  lea     rcx, [rsp+14F0h+var_14D0]
0x140003240  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003245  cmp     [rbp+13F0h+OutputString], r13w
0x14000324d  jnz     short loc_140003263
0x14000324f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140003254  mov     rdx, rbx; unsigned __int16 *
0x140003257  lea     rcx, [rbp+13F0h+OutputString]; this
0x14000325e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003263  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000326a  call    cs:__imp_OutputDebugStringW
0x140003270  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140003275  jnz     short loc_140003280
0x140003277  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x14000327e  jz      short loc_140003291
0x140003280  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003287  test    rax, rax
0x14000328a  jz      short loc_140003291
0x14000328c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003291  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140003296  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
