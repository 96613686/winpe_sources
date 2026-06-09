# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140002798`
- end: `0x140002a11`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140002520`

## callees

- `0x140002456`
- `0x140002798`
- `0x140003b54`
- `0x1400042f0`
- `0x140004a50`
- `0x140005ad0`
- `0x1400114d0`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140002851`
- `KERNEL32!GetCurrentThreadId` at `0x140002851`
- `KERNEL32!OutputDebugStringW` at `0x1400029de`
- `KERNEL32!OutputDebugStringW` at `0x1400029de`
- `KERNEL32!IsDebuggerPresent` at `0x140002954`
- `KERNEL32!IsDebuggerPresent` at `0x140002954`

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
0x140002798  mov     [rsp-8+arg_18], rbx
0x14000279d  push    rbp
0x14000279e  push    rsi
0x14000279f  push    rdi
0x1400027a0  push    r12
0x1400027a2  push    r13
0x1400027a4  push    r14
0x1400027a6  push    r15
0x1400027a8  lea     rbp, [rsp-13C0h]
0x1400027b0  mov     eax, 14C0h
0x1400027b5  call    _alloca_probe
0x1400027ba  sub     rsp, rax
0x1400027bd  mov     r14, r8
0x1400027c0  mov     esi, edx
0x1400027c2  mov     rdi, rcx
0x1400027c5  mov     r15, [rbp+13F0h+arg_28]
0x1400027cc  xor     edx, edx; Val
0x1400027ce  mov     r8d, 98h; Size
0x1400027d4  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x1400027d9  call    memset_0
0x1400027de  nop
0x1400027df  xor     r13d, r13d
0x1400027e2  mov     [rbp+13F0h+OutputString], r13w
0x1400027ea  mov     [rbp+13F0h+var_1430], r13b
0x1400027ee  mov     rbx, [rbp+13F0h+arg_30]
0x1400027f5  mov     ecx, [rbx]; this
0x1400027f7  mov     [rsp+14F0h+var_14C8], ecx
0x1400027fb  mov     eax, [rbx+4]
0x1400027fe  mov     [rsp+14F0h+var_14C4], eax
0x140002802  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140002807  mov     r12d, eax
0x14000280a  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140002812  mov     ecx, r13d
0x140002815  lea     eax, [r13+8]
0x140002819  cmp     dword ptr [rbx+8], 1
0x14000281d  cmovz   ecx, eax
0x140002820  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140002824  lea     ecx, [rax-7]
0x140002827  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000282f  inc     ecx
0x140002831  mov     [rsp+14F0h+var_14C0], ecx
0x140002835  mov     rcx, [rbp+13F0h+arg_38]
0x14000283c  test    rcx, rcx
0x14000283f  jz      short loc_14000284C
0x140002841  cmp     [rcx], r13w
0x140002845  mov     [rsp+14F0h+var_14B8], rcx
0x14000284a  jnz     short loc_140002851
0x14000284c  mov     [rsp+14F0h+var_14B8], r13
0x140002851  call    cs:__imp_GetCurrentThreadId
0x140002857  mov     [rsp+14F0h+var_14B0], eax
0x14000285b  mov     [rsp+14F0h+var_1498], r14
0x140002860  mov     [rsp+14F0h+var_1490], esi
0x140002864  mov     [rsp+14F0h+var_148C], r12d
0x140002869  mov     [rsp+14F0h+var_14A8], r13
0x14000286e  mov     [rsp+14F0h+var_14A0], r13
0x140002873  mov     [rbp+13F0h+var_1448], r15
0x140002877  mov     [rbp+13F0h+var_1440], rdi
0x14000287b  mov     [rsp+14F0h+var_1488], r13
0x140002880  xorps   xmm0, xmm0
0x140002883  xor     eax, eax
0x140002885  movups  [rbp+13F0h+var_1468], xmm0
0x140002889  mov     [rbp+13F0h+var_1458], rax
0x14000288d  xorps   xmm1, xmm1
0x140002890  movups  [rsp+14F0h+var_1480], xmm1
0x140002895  mov     [rbp+13F0h+var_1470], rax
0x140002899  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400028a0  test    rax, rax
0x1400028a3  jz      short loc_1400028B0
0x1400028a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028aa  mov     [rbp+13F0h+var_1450], rax
0x1400028ae  jmp     short loc_1400028B4
0x1400028b0  mov     [rbp+13F0h+var_1450], r13
0x1400028b4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400028bb  test    rax, rax
0x1400028be  jz      short loc_1400028CA
0x1400028c0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028ca  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400028d1  test    rax, rax
0x1400028d4  jz      short loc_1400028EA
0x1400028d6  mov     r8d, 400h
0x1400028dc  lea     rdx, [rbp+13F0h+var_1430]
0x1400028e0  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400028ea  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400028f1  test    rax, rax
0x1400028f4  jz      short loc_140002900
0x1400028f6  lea     rcx, [rsp+14F0h+var_14D0]
0x1400028fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002900  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002907  test    rax, rax
0x14000290a  jz      short loc_14000291D
0x14000290c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002911  jnz     short loc_14000291D
0x140002913  lea     rcx, [rsp+14F0h+var_14D0]
0x140002918  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000291d  cmp     [rsp+14F0h+var_14C8], r13d
0x140002922  jl      short loc_140002936
0x140002924  mov     ecx, 8000FFFFh; this
0x140002929  mov     [rsp+14F0h+var_14C8], ecx
0x14000292d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002932  mov     [rsp+14F0h+var_14C4], eax
0x140002936  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x14000293d  jnz     short loc_14000295E
0x14000293f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002946  test    rax, rax
0x140002949  jz      short loc_140002954
0x14000294b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002950  test    al, al
0x140002952  jmp     short loc_14000295C
0x140002954  call    cs:__imp_IsDebuggerPresent
0x14000295a  test    eax, eax
0x14000295c  jz      short loc_140002965
0x14000295e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140002963  jz      short loc_14000298B
0x140002965  mov     rax, cs:g_pfnResultLoggingCallback
0x14000296c  test    rax, rax
0x14000296f  jz      short loc_1400029E4
0x140002971  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140002978  jnz     short loc_1400029E4
0x14000297a  xor     r8d, r8d
0x14000297d  xor     edx, edx
0x14000297f  lea     rcx, [rsp+14F0h+var_14D0]
0x140002984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002989  jmp     short loc_1400029E4
0x14000298b  mov     ebx, 800h
0x140002990  mov     rax, cs:g_pfnResultLoggingCallback
0x140002997  test    rax, rax
0x14000299a  jz      short loc_1400029B9
0x14000299c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400029a3  jnz     short loc_1400029B9
0x1400029a5  mov     r8d, ebx
0x1400029a8  lea     rdx, [rbp+13F0h+OutputString]
0x1400029af  lea     rcx, [rsp+14F0h+var_14D0]
0x1400029b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400029b9  cmp     [rbp+13F0h+OutputString], r13w
0x1400029c1  jnz     short loc_1400029D7
0x1400029c3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x1400029c8  mov     rdx, rbx; unsigned __int16 *
0x1400029cb  lea     rcx, [rbp+13F0h+OutputString]; this
0x1400029d2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400029d7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1400029de  call    cs:__imp_OutputDebugStringW
0x1400029e4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1400029e9  jnz     short loc_1400029F4
0x1400029eb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x1400029f2  jz      short loc_140002A06
0x1400029f4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400029fb  test    rax, rax
0x1400029fe  jz      short loc_140002A06
0x140002a00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002a05  nop
0x140002a06  lea     rcx, [rsp+14F0h+var_14D0]; this
0x140002a0b  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
