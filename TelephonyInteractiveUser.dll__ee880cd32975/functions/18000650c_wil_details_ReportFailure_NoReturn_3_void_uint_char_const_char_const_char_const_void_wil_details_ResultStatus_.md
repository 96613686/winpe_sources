# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000650c`
- end: `0x180006773`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800062b8`

## callees

- `0x1800027c0`
- `0x180005010`
- `0x18000650c`
- `0x18000a70c`
- `0x18000c5fc`
- `0x18000fbf8`
- `0x1800187e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800066b7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800066b7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006741`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006741`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065ad`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800065ad`

## string_xrefs

- `0x1800065c2`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

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
  int v9; // eax
  int v10; // edx
  int v11; // eax
  int v12; // edi
  int v13; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
  bool v18; // zf
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD v25; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
  int v29; // [rsp+60h] [rbp-A0h]
  int v30; // [rsp+64h] [rbp-9Ch]
  __int64 v31; // [rsp+68h] [rbp-98h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  __int128 v34; // [rsp+88h] [rbp-78h]
  __int64 v35; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v37; // [rsp+A8h] [rbp-58h]
  __int64 v38; // [rsp+B0h] [rbp-50h]
  char v39[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v9 = a7[1];
  v21 = *a7;
  v22 = v9;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21, v10);
  v18 = a7[2] == 1;
  v12 = v11;
  v19 = 3;
  v13 = 0;
  if ( v18 )
    v13 = 8;
  v20 = v13;
  v24 = 0;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a2;
  v25 = CurrentThreadId;
  v30 = v12;
  v28 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v35 = 0;
  v33 = 0;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v16);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
  {
    v21 = -2147418113;
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v18 = !IsDebuggerPresent())
      : (v18 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16) == 0),
        v18)
    || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v17);
    OutputDebugStringW(OutputString);
  }
  if ( (v20 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v19, v15);
}

```

## disassembly

```asm
0x18000650c  mov     [rsp-8+arg_10], rbx
0x180006511  mov     [rsp-8+arg_18], rsi
0x180006516  push    rbp
0x180006517  push    rdi
0x180006518  push    r12
0x18000651a  push    r14
0x18000651c  push    r15
0x18000651e  lea     rbp, [rsp-13C0h]
0x180006526  mov     eax, 14C0h
0x18000652b  call    _alloca_probe
0x180006530  sub     rsp, rax
0x180006533  mov     rsi, [rbp+13E0h+arg_28]
0x18000653a  mov     r14d, edx
0x18000653d  mov     r15, rcx
0x180006540  xor     edx, edx; Val
0x180006542  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x180006547  mov     r8d, 98h; Size
0x18000654d  call    memset_0
0x180006552  mov     rbx, [rbp+13E0h+arg_30]
0x180006559  xor     r12d, r12d
0x18000655c  mov     [rbp+13E0h+OutputString], r12w
0x180006564  mov     [rbp+13E0h+var_1420], r12b
0x180006568  mov     ecx, [rbx]; this
0x18000656a  mov     eax, [rbx+4]
0x18000656d  mov     [rsp+14E0h+var_14B8], ecx
0x180006571  mov     [rsp+14E0h+var_14B4], eax
0x180006575  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000657a  cmp     dword ptr [rbx+8], 1
0x18000657e  mov     edi, eax
0x180006580  lea     eax, [r12+8]
0x180006585  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x18000658d  mov     ecx, r12d
0x180006590  cmovz   ecx, eax
0x180006593  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x180006597  lea     ecx, [rax-7]
0x18000659a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800065a2  inc     ecx
0x1800065a4  mov     [rsp+14E0h+var_14A8], r12
0x1800065a9  mov     [rsp+14E0h+var_14B0], ecx
0x1800065ad  call    cs:__imp_GetCurrentThreadId
0x1800065b3  xorps   xmm0, xmm0
0x1800065b6  mov     [rsp+14E0h+var_1480], r14d
0x1800065bb  mov     [rsp+14E0h+var_14A0], eax
0x1800065bf  xorps   xmm1, xmm1
0x1800065c2  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x1800065c9  mov     [rsp+14E0h+var_147C], edi
0x1800065cd  mov     [rsp+14E0h+var_1488], rax
0x1800065d2  xor     eax, eax
0x1800065d4  mov     [rbp+13E0h+var_1448], rax
0x1800065d8  mov     [rbp+13E0h+var_1460], rax
0x1800065dc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800065e3  mov     [rsp+14E0h+var_1498], r12
0x1800065e8  mov     [rsp+14E0h+var_1490], r12
0x1800065ed  mov     [rbp+13E0h+var_1438], rsi
0x1800065f1  mov     [rbp+13E0h+var_1430], r15
0x1800065f5  mov     [rsp+14E0h+var_1478], r12
0x1800065fa  movups  [rbp+13E0h+var_1458], xmm0
0x1800065fe  movups  [rsp+14E0h+var_1470], xmm1
0x180006603  test    rax, rax
0x180006606  jz      short loc_180006613
0x180006608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000660d  mov     [rbp+13E0h+var_1440], rax
0x180006611  jmp     short loc_180006617
0x180006613  mov     [rbp+13E0h+var_1440], r12
0x180006617  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000661e  test    rax, rax
0x180006621  jz      short loc_18000662D
0x180006623  lea     rcx, [rsp+14E0h+var_14C0]
0x180006628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000662d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006634  test    rax, rax
0x180006637  jz      short loc_18000664D
0x180006639  mov     r8d, 400h
0x18000663f  lea     rdx, [rbp+13E0h+var_1420]
0x180006643  lea     rcx, [rsp+14E0h+var_14C0]
0x180006648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000664d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006654  test    rax, rax
0x180006657  jz      short loc_180006663
0x180006659  lea     rcx, [rsp+14E0h+var_14C0]
0x18000665e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006663  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000666a  test    rax, rax
0x18000666d  jz      short loc_180006680
0x18000666f  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180006674  jnz     short loc_180006680
0x180006676  lea     rcx, [rsp+14E0h+var_14C0]
0x18000667b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006680  cmp     [rsp+14E0h+var_14B8], r12d
0x180006685  jl      short loc_180006699
0x180006687  mov     ecx, 8000FFFFh; this
0x18000668c  mov     [rsp+14E0h+var_14B8], ecx
0x180006690  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006695  mov     [rsp+14E0h+var_14B4], eax
0x180006699  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800066a0  jnz     short loc_1800066C1
0x1800066a2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800066a9  test    rax, rax
0x1800066ac  jz      short loc_1800066B7
0x1800066ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b3  test    al, al
0x1800066b5  jmp     short loc_1800066BF
0x1800066b7  call    cs:__imp_IsDebuggerPresent
0x1800066bd  test    eax, eax
0x1800066bf  jz      short loc_1800066C8
0x1800066c1  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800066c6  jz      short loc_1800066EE
0x1800066c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066cf  test    rax, rax
0x1800066d2  jz      short loc_180006747
0x1800066d4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800066db  jnz     short loc_180006747
0x1800066dd  xor     r8d, r8d
0x1800066e0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800066e5  xor     edx, edx
0x1800066e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ec  jmp     short loc_180006747
0x1800066ee  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066f5  mov     ebx, 800h
0x1800066fa  test    rax, rax
0x1800066fd  jz      short loc_18000671C
0x1800066ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180006706  jnz     short loc_18000671C
0x180006708  mov     r8d, ebx
0x18000670b  lea     rdx, [rbp+13E0h+OutputString]
0x180006712  lea     rcx, [rsp+14E0h+var_14C0]
0x180006717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671c  cmp     [rbp+13E0h+OutputString], r12w
0x180006724  jnz     short loc_18000673A
0x180006726  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000672b  mov     rdx, rbx; unsigned __int16 *
0x18000672e  lea     rcx, [rbp+13E0h+OutputString]; this
0x180006735  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000673a  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180006741  call    cs:__imp_OutputDebugStringW
0x180006747  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000674c  jnz     short loc_180006757
0x18000674e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006755  jz      short loc_180006768
0x180006757  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000675e  test    rax, rax
0x180006761  jz      short loc_180006768
0x180006763  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006768  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000676d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
