# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000335c`
- end: `0x1800035c5`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `617`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003110`

## callees

- `0x1800028f0`
- `0x18000335c`
- `0x1800048e4`
- `0x180005080`
- `0x180005900`
- `0x180006e20`
- `0x180008b80`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033fe`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800033fe`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003592`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003592`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003508`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003508`

## string_xrefs

- `0x180003408`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<3>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int *a7)
{
  int v9; // edx
  int v10; // edi
  int v11; // ecx
  const struct wil::FailureInfo *v12; // rdx
  __int64 v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v10 = wil::details::RecordFailFast((wil::details *)(unsigned int)v18, v9);
  v16 = 3;
  v11 = 0;
  if ( a7[2] == 1 )
    v11 = 8;
  v17 = v11;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h";
  v26 = a2;
  v27 = v10;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
  {
    v18 = -2147418113;
    v19 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v12);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( (v17 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v13);
  }
  wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x18000335c  mov     [rsp-8+arg_10], rbx
0x180003361  mov     [rsp-8+arg_18], rsi
0x180003366  push    rbp
0x180003367  push    rdi
0x180003368  push    r12
0x18000336a  push    r14
0x18000336c  push    r15
0x18000336e  lea     rbp, [rsp-13C0h]
0x180003376  mov     eax, 14C0h
0x18000337b  call    _alloca_probe
0x180003380  sub     rsp, rax
0x180003383  mov     r14d, edx
0x180003386  mov     r15, rcx
0x180003389  mov     rsi, [rbp+13E0h+arg_28]
0x180003390  xor     edx, edx; Val
0x180003392  mov     r8d, 98h; Size
0x180003398  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x18000339d  call    memset_0
0x1800033a2  nop
0x1800033a3  xor     r12d, r12d
0x1800033a6  mov     [rbp+13E0h+OutputString], r12w
0x1800033ae  mov     [rbp+13E0h+var_1420], r12b
0x1800033b2  mov     rbx, [rbp+13E0h+arg_30]
0x1800033b9  mov     ecx, [rbx]; this
0x1800033bb  mov     [rsp+14E0h+var_14B8], ecx
0x1800033bf  mov     eax, [rbx+4]
0x1800033c2  mov     [rsp+14E0h+var_14B4], eax
0x1800033c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800033cb  mov     edi, eax
0x1800033cd  mov     dword ptr [rsp+14E0h+var_14C0], 3
0x1800033d5  mov     ecx, r12d
0x1800033d8  lea     eax, [r12+8]
0x1800033dd  cmp     dword ptr [rbx+8], 1
0x1800033e1  cmovz   ecx, eax
0x1800033e4  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x1800033e8  lea     ecx, [rax-7]
0x1800033eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800033f3  inc     ecx
0x1800033f5  mov     [rsp+14E0h+var_14B0], ecx
0x1800033f9  mov     [rsp+14E0h+var_14A8], r12
0x1800033fe  call    cs:__imp_GetCurrentThreadId
0x180003404  mov     [rsp+14E0h+var_14A0], eax
0x180003408  lea     rax, aOnecoreInterna; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18000340f  mov     [rsp+14E0h+var_1488], rax
0x180003414  mov     [rsp+14E0h+var_1480], r14d
0x180003419  mov     [rsp+14E0h+var_147C], edi
0x18000341d  mov     [rsp+14E0h+var_1498], r12
0x180003422  mov     [rsp+14E0h+var_1490], r12
0x180003427  mov     [rbp+13E0h+var_1438], rsi
0x18000342b  mov     [rbp+13E0h+var_1430], r15
0x18000342f  mov     [rsp+14E0h+var_1478], r12
0x180003434  xorps   xmm0, xmm0
0x180003437  xor     eax, eax
0x180003439  movups  [rbp+13E0h+var_1458], xmm0
0x18000343d  mov     [rbp+13E0h+var_1448], rax
0x180003441  xorps   xmm1, xmm1
0x180003444  movups  [rsp+14E0h+var_1470], xmm1
0x180003449  mov     [rbp+13E0h+var_1460], rax
0x18000344d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003454  test    rax, rax
0x180003457  jz      short loc_180003464
0x180003459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000345e  mov     [rbp+13E0h+var_1440], rax
0x180003462  jmp     short loc_180003468
0x180003464  mov     [rbp+13E0h+var_1440], r12
0x180003468  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000346f  test    rax, rax
0x180003472  jz      short loc_18000347E
0x180003474  lea     rcx, [rsp+14E0h+var_14C0]
0x180003479  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000347e  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003485  test    rax, rax
0x180003488  jz      short loc_18000349E
0x18000348a  mov     r8d, 400h
0x180003490  lea     rdx, [rbp+13E0h+var_1420]
0x180003494  lea     rcx, [rsp+14E0h+var_14C0]
0x180003499  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000349e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034a5  test    rax, rax
0x1800034a8  jz      short loc_1800034B4
0x1800034aa  lea     rcx, [rsp+14E0h+var_14C0]
0x1800034af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034b4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800034bb  test    rax, rax
0x1800034be  jz      short loc_1800034D1
0x1800034c0  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x1800034c5  jnz     short loc_1800034D1
0x1800034c7  lea     rcx, [rsp+14E0h+var_14C0]
0x1800034cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800034d1  cmp     [rsp+14E0h+var_14B8], r12d
0x1800034d6  jl      short loc_1800034EA
0x1800034d8  mov     ecx, 8000FFFFh; this
0x1800034dd  mov     [rsp+14E0h+var_14B8], ecx
0x1800034e1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800034e6  mov     [rsp+14E0h+var_14B4], eax
0x1800034ea  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800034f1  jnz     short loc_180003512
0x1800034f3  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800034fa  test    rax, rax
0x1800034fd  jz      short loc_180003508
0x1800034ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003504  test    al, al
0x180003506  jmp     short loc_180003510
0x180003508  call    cs:__imp_IsDebuggerPresent
0x18000350e  test    eax, eax
0x180003510  jz      short loc_180003519
0x180003512  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180003517  jz      short loc_18000353F
0x180003519  mov     rax, cs:g_pfnResultLoggingCallback
0x180003520  test    rax, rax
0x180003523  jz      short loc_180003598
0x180003525  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000352c  jnz     short loc_180003598
0x18000352e  xor     r8d, r8d
0x180003531  xor     edx, edx
0x180003533  lea     rcx, [rsp+14E0h+var_14C0]
0x180003538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000353d  jmp     short loc_180003598
0x18000353f  mov     ebx, 800h
0x180003544  mov     rax, cs:g_pfnResultLoggingCallback
0x18000354b  test    rax, rax
0x18000354e  jz      short loc_18000356D
0x180003550  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003557  jnz     short loc_18000356D
0x180003559  mov     r8d, ebx
0x18000355c  lea     rdx, [rbp+13E0h+OutputString]
0x180003563  lea     rcx, [rsp+14E0h+var_14C0]
0x180003568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000356d  cmp     [rbp+13E0h+OutputString], r12w
0x180003575  jnz     short loc_18000358B
0x180003577  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x18000357c  mov     rdx, rbx; unsigned __int16 *
0x18000357f  lea     rcx, [rbp+13E0h+OutputString]; this
0x180003586  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000358b  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x180003592  call    cs:__imp_OutputDebugStringW
0x180003598  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x18000359d  jnz     short loc_1800035A8
0x18000359f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800035a6  jz      short loc_1800035BA
0x1800035a8  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800035af  test    rax, rax
0x1800035b2  jz      short loc_1800035BA
0x1800035b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800035b9  nop
0x1800035ba  lea     rcx, [rsp+14E0h+var_14C0]; this
0x1800035bf  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
