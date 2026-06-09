# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140004124`
- end: `0x140004386`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `610`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140003ec0`

## callees

- `0x1400030dc`
- `0x140004124`
- `0x140006464`
- `0x140006dc0`
- `0x1400078b0`
- `0x140009260`
- `0x14001bb30`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400041c6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400041c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004353`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004353`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400042c9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400042c9`

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
  int v10; // edx
  int v11; // edi
  int v12; // ecx
  const struct wil::FailureInfo *v13; // rdx
  __int64 v14; // rcx
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v19, v10);
  v17 = 3;
  v12 = 0;
  if ( a7[2] == 1 )
    v12 = 8;
  v18 = v12;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v11;
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
  {
    v19 = -2147418113;
    v20 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v13);
  }
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
  if ( (v18 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v14);
  }
  wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x140004124  mov     [rsp-8+arg_18], rbx
0x140004129  push    rbp
0x14000412a  push    rsi
0x14000412b  push    rdi
0x14000412c  push    r12
0x14000412e  push    r13
0x140004130  push    r14
0x140004132  push    r15
0x140004134  lea     rbp, [rsp-13C0h]
0x14000413c  mov     eax, 14C0h
0x140004141  call    _alloca_probe
0x140004146  sub     rsp, rax
0x140004149  mov     r15, r8
0x14000414c  mov     r14d, edx
0x14000414f  mov     r12, rcx
0x140004152  mov     rsi, [rbp+13F0h+arg_28]
0x140004159  xor     edx, edx; Val
0x14000415b  mov     r8d, 98h; Size
0x140004161  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140004166  call    memset_0
0x14000416b  nop
0x14000416c  xor     r13d, r13d
0x14000416f  mov     [rbp+13F0h+OutputString], r13w
0x140004177  mov     [rbp+13F0h+var_1430], r13b
0x14000417b  mov     rbx, [rbp+13F0h+arg_30]
0x140004182  mov     ecx, [rbx]; this
0x140004184  mov     [rsp+14F0h+var_14C8], ecx
0x140004188  mov     eax, [rbx+4]
0x14000418b  mov     [rsp+14F0h+var_14C4], eax
0x14000418f  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004194  mov     edi, eax
0x140004196  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x14000419e  mov     ecx, r13d
0x1400041a1  lea     eax, [r13+8]
0x1400041a5  cmp     dword ptr [rbx+8], 1
0x1400041a9  cmovz   ecx, eax
0x1400041ac  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1400041b0  lea     ecx, [rax-7]
0x1400041b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400041bb  inc     ecx
0x1400041bd  mov     [rsp+14F0h+var_14C0], ecx
0x1400041c1  mov     [rsp+14F0h+var_14B8], r13
0x1400041c6  call    cs:__imp_GetCurrentThreadId
0x1400041cc  mov     [rsp+14F0h+var_14B0], eax
0x1400041d0  mov     [rsp+14F0h+var_1498], r15
0x1400041d5  mov     [rsp+14F0h+var_1490], r14d
0x1400041da  mov     [rsp+14F0h+var_148C], edi
0x1400041de  mov     [rsp+14F0h+var_14A8], r13
0x1400041e3  mov     [rsp+14F0h+var_14A0], r13
0x1400041e8  mov     [rbp+13F0h+var_1448], rsi
0x1400041ec  mov     [rbp+13F0h+var_1440], r12
0x1400041f0  mov     [rsp+14F0h+var_1488], r13
0x1400041f5  xorps   xmm0, xmm0
0x1400041f8  xor     eax, eax
0x1400041fa  movups  [rbp+13F0h+var_1468], xmm0
0x1400041fe  mov     [rbp+13F0h+var_1458], rax
0x140004202  xorps   xmm1, xmm1
0x140004205  movups  [rsp+14F0h+var_1480], xmm1
0x14000420a  mov     [rbp+13F0h+var_1470], rax
0x14000420e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004215  test    rax, rax
0x140004218  jz      short loc_140004225
0x14000421a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000421f  mov     [rbp+13F0h+var_1450], rax
0x140004223  jmp     short loc_140004229
0x140004225  mov     [rbp+13F0h+var_1450], r13
0x140004229  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004230  test    rax, rax
0x140004233  jz      short loc_14000423F
0x140004235  lea     rcx, [rsp+14F0h+var_14D0]
0x14000423a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000423f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004246  test    rax, rax
0x140004249  jz      short loc_14000425F
0x14000424b  mov     r8d, 400h
0x140004251  lea     rdx, [rbp+13F0h+var_1430]
0x140004255  lea     rcx, [rsp+14F0h+var_14D0]
0x14000425a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000425f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004266  test    rax, rax
0x140004269  jz      short loc_140004275
0x14000426b  lea     rcx, [rsp+14F0h+var_14D0]
0x140004270  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004275  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000427c  test    rax, rax
0x14000427f  jz      short loc_140004292
0x140004281  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140004286  jnz     short loc_140004292
0x140004288  lea     rcx, [rsp+14F0h+var_14D0]
0x14000428d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004292  cmp     [rsp+14F0h+var_14C8], r13d
0x140004297  jl      short loc_1400042AB
0x140004299  mov     ecx, 8000FFFFh; this
0x14000429e  mov     [rsp+14F0h+var_14C8], ecx
0x1400042a2  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400042a7  mov     [rsp+14F0h+var_14C4], eax
0x1400042ab  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400042b2  jnz     short loc_1400042D3
0x1400042b4  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400042bb  test    rax, rax
0x1400042be  jz      short loc_1400042C9
0x1400042c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042c5  test    al, al
0x1400042c7  jmp     short loc_1400042D1
0x1400042c9  call    cs:__imp_IsDebuggerPresent
0x1400042cf  test    eax, eax
0x1400042d1  jz      short loc_1400042DA
0x1400042d3  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400042d8  jz      short loc_140004300
0x1400042da  mov     rax, cs:g_pfnResultLoggingCallback
0x1400042e1  test    rax, rax
0x1400042e4  jz      short loc_140004359
0x1400042e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400042ed  jnz     short loc_140004359
0x1400042ef  xor     r8d, r8d
0x1400042f2  xor     edx, edx
0x1400042f4  lea     rcx, [rsp+14F0h+var_14D0]
0x1400042f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042fe  jmp     short loc_140004359
0x140004300  mov     ebx, 800h
0x140004305  mov     rax, cs:g_pfnResultLoggingCallback
0x14000430c  test    rax, rax
0x14000430f  jz      short loc_14000432E
0x140004311  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140004318  jnz     short loc_14000432E
0x14000431a  mov     r8d, ebx
0x14000431d  lea     rdx, [rbp+13F0h+OutputString]
0x140004324  lea     rcx, [rsp+14F0h+var_14D0]
0x140004329  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000432e  cmp     [rbp+13F0h+OutputString], r13w
0x140004336  jnz     short loc_14000434C
0x140004338  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x14000433d  mov     rdx, rbx; unsigned __int16 *
0x140004340  lea     rcx, [rbp+13F0h+OutputString]; this
0x140004347  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000434c  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x140004353  call    cs:__imp_OutputDebugStringW
0x140004359  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x14000435e  jnz     short loc_140004369
0x140004360  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140004367  jz      short loc_14000437B
0x140004369  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004370  test    rax, rax
0x140004373  jz      short loc_14000437B
0x140004375  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000437a  nop
0x14000437b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140004380  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
