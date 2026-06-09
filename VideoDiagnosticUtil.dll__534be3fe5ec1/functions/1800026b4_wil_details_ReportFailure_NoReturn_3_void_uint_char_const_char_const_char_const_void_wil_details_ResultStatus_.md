# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x1800026b4`
- end: `0x180002926`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180002450`

## callees

- `0x180001fd0`
- `0x1800026b4`
- `0x1800043bc`
- `0x180004a8c`
- `0x180007698`
- `0x18000967e`
- `0x180009740`
- `0x18000a010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800028ee`
- `KERNEL32!OutputDebugStringW` at `0x1800028ee`
- `KERNEL32!GetCurrentThreadId` at `0x180002755`
- `KERNEL32!GetCurrentThreadId` at `0x180002755`
- `KERNEL32!IsDebuggerPresent` at `0x18000285e`
- `KERNEL32!IsDebuggerPresent` at `0x18000285e`

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
0x1800026b4  mov     [rsp-8+arg_18], rbx
0x1800026b9  push    rbp
0x1800026ba  push    rsi
0x1800026bb  push    rdi
0x1800026bc  push    r12
0x1800026be  push    r13
0x1800026c0  push    r14
0x1800026c2  push    r15
0x1800026c4  lea     rbp, [rsp-13C0h]
0x1800026cc  mov     eax, 14C0h
0x1800026d1  call    _alloca_probe
0x1800026d6  sub     rsp, rax
0x1800026d9  mov     rsi, [rbp+13F0h+arg_28]
0x1800026e0  mov     r15, r8
0x1800026e3  mov     r14d, edx
0x1800026e6  mov     r12, rcx
0x1800026e9  xor     edx, edx; Val
0x1800026eb  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1800026f0  mov     r8d, 98h; Size
0x1800026f6  call    memset_0
0x1800026fb  mov     rbx, [rbp+13F0h+arg_30]
0x180002702  xor     r13d, r13d
0x180002705  mov     [rbp+13F0h+OutputString], r13w
0x18000270d  mov     [rbp+13F0h+var_1430], r13b
0x180002711  mov     ecx, [rbx]; this
0x180002713  mov     eax, [rbx+4]
0x180002716  mov     [rsp+14F0h+var_14C8], ecx
0x18000271a  mov     [rsp+14F0h+var_14C4], eax
0x18000271e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180002723  cmp     dword ptr [rbx+8], 1
0x180002727  mov     edi, eax
0x180002729  lea     eax, [r13+8]
0x18000272d  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180002735  mov     ecx, r13d
0x180002738  cmovz   ecx, eax
0x18000273b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000273f  lea     ecx, [rax-7]
0x180002742  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000274a  inc     ecx
0x18000274c  mov     [rsp+14F0h+var_14B8], r13
0x180002751  mov     [rsp+14F0h+var_14C0], ecx
0x180002755  call    cs:__imp_GetCurrentThreadId
0x18000275c  nop     dword ptr [rax+rax+00h]
0x180002761  xorps   xmm0, xmm0
0x180002764  mov     [rsp+14F0h+var_1498], r15
0x180002769  mov     [rsp+14F0h+var_14B0], eax
0x18000276d  xorps   xmm1, xmm1
0x180002770  xor     eax, eax
0x180002772  mov     [rsp+14F0h+var_1490], r14d
0x180002777  mov     [rbp+13F0h+var_1458], rax
0x18000277b  mov     [rbp+13F0h+var_1470], rax
0x18000277f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180002786  mov     [rsp+14F0h+var_148C], edi
0x18000278a  mov     [rsp+14F0h+var_14A8], r13
0x18000278f  mov     [rsp+14F0h+var_14A0], r13
0x180002794  mov     [rbp+13F0h+var_1448], rsi
0x180002798  mov     [rbp+13F0h+var_1440], r12
0x18000279c  mov     [rsp+14F0h+var_1488], r13
0x1800027a1  movups  [rbp+13F0h+var_1468], xmm0
0x1800027a5  movups  [rsp+14F0h+var_1480], xmm1
0x1800027aa  test    rax, rax
0x1800027ad  jz      short loc_1800027BA
0x1800027af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027b4  mov     [rbp+13F0h+var_1450], rax
0x1800027b8  jmp     short loc_1800027BE
0x1800027ba  mov     [rbp+13F0h+var_1450], r13
0x1800027be  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800027c5  test    rax, rax
0x1800027c8  jz      short loc_1800027D4
0x1800027ca  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027d4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800027db  test    rax, rax
0x1800027de  jz      short loc_1800027F4
0x1800027e0  mov     r8d, 400h
0x1800027e6  lea     rdx, [rbp+13F0h+var_1430]
0x1800027ea  lea     rcx, [rsp+14F0h+var_14D0]
0x1800027ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800027f4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800027fb  test    rax, rax
0x1800027fe  jz      short loc_18000280A
0x180002800  lea     rcx, [rsp+14F0h+var_14D0]
0x180002805  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000280a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180002811  test    rax, rax
0x180002814  jz      short loc_180002827
0x180002816  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000281b  jnz     short loc_180002827
0x18000281d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002827  cmp     [rsp+14F0h+var_14C8], r13d
0x18000282c  jl      short loc_180002840
0x18000282e  mov     ecx, 8000FFFFh; this
0x180002833  mov     [rsp+14F0h+var_14C8], ecx
0x180002837  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000283c  mov     [rsp+14F0h+var_14C4], eax
0x180002840  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180002847  jnz     short loc_18000286E
0x180002849  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180002850  test    rax, rax
0x180002853  jz      short loc_18000285E
0x180002855  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000285a  test    al, al
0x18000285c  jmp     short loc_18000286C
0x18000285e  call    cs:__imp_IsDebuggerPresent
0x180002865  nop     dword ptr [rax+rax+00h]
0x18000286a  test    eax, eax
0x18000286c  jz      short loc_180002875
0x18000286e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180002873  jz      short loc_18000289B
0x180002875  mov     rax, cs:g_pfnResultLoggingCallback
0x18000287c  test    rax, rax
0x18000287f  jz      short loc_1800028FA
0x180002881  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180002888  jnz     short loc_1800028FA
0x18000288a  xor     r8d, r8d
0x18000288d  lea     rcx, [rsp+14F0h+var_14D0]
0x180002892  xor     edx, edx
0x180002894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002899  jmp     short loc_1800028FA
0x18000289b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800028a2  mov     ebx, 800h
0x1800028a7  test    rax, rax
0x1800028aa  jz      short loc_1800028C9
0x1800028ac  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800028b3  jnz     short loc_1800028C9
0x1800028b5  mov     r8d, ebx
0x1800028b8  lea     rdx, [rbp+13F0h+OutputString]
0x1800028bf  lea     rcx, [rsp+14F0h+var_14D0]
0x1800028c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028c9  cmp     [rbp+13F0h+OutputString], r13w
0x1800028d1  jnz     short loc_1800028E7
0x1800028d3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1800028d8  mov     rdx, rbx; unsigned __int16 *
0x1800028db  lea     rcx, [rbp+13F0h+OutputString]; this
0x1800028e2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800028e7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800028ee  call    cs:__imp_OutputDebugStringW
0x1800028f5  nop     dword ptr [rax+rax+00h]
0x1800028fa  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800028ff  jnz     short loc_18000290A
0x180002901  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180002908  jz      short loc_18000291B
0x18000290a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180002911  test    rax, rax
0x180002914  jz      short loc_18000291B
0x180002916  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000291b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180002920  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
