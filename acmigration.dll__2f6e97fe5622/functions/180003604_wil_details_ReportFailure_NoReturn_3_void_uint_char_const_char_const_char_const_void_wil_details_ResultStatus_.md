# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180003604`
- end: `0x180003889`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `645`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180003228`

## callees

- `0x180002874`
- `0x180003604`
- `0x180005d64`
- `0x180006524`
- `0x180007580`
- `0x180009b00`
- `0x1800650c0`
- `0x18006a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800037cc`
- `KERNEL32!IsDebuggerPresent` at `0x1800037cc`
- `KERNEL32!OutputDebugStringW` at `0x180003856`
- `KERNEL32!OutputDebugStringW` at `0x180003856`
- `KERNEL32!GetCurrentThreadId` at `0x1800036c9`
- `KERNEL32!GetCurrentThreadId` at `0x1800036c9`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
  __int64 v38; // [rsp+C0h] [rbp-40h]
  char v39[1024]; // [rsp+D0h] [rbp-30h] BYREF
  WCHAR OutputString[2072]; // [rsp+4D0h] [rbp+3D0h] BYREF

  v38 = -2;
  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
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
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v39, 1024);
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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x180003604  push    rbp
0x180003606  push    rsi
0x180003607  push    rdi
0x180003608  push    r12
0x18000360a  push    r13
0x18000360c  push    r14
0x18000360e  push    r15
0x180003610  lea     rbp, [rsp-13D0h]
0x180003618  mov     eax, 14D0h
0x18000361d  call    _alloca_probe
0x180003622  sub     rsp, rax
0x180003625  mov     [rbp+1400h+var_1440], 0FFFFFFFFFFFFFFFEh
0x18000362d  mov     [rsp+1500h+arg_18], rbx
0x180003635  mov     r14, r8
0x180003638  mov     esi, edx
0x18000363a  mov     rdi, rcx
0x18000363d  mov     r15, [rbp+1400h+arg_28]
0x180003644  xor     edx, edx; Val
0x180003646  mov     r8d, 98h; Size
0x18000364c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003651  call    memset_0
0x180003656  nop
0x180003657  xor     r13d, r13d
0x18000365a  mov     [rbp+1400h+OutputString], r13w
0x180003662  mov     [rbp+1400h+var_1430], r13b
0x180003666  mov     rbx, [rbp+1400h+arg_30]
0x18000366d  mov     ecx, [rbx]; this
0x18000366f  mov     [rsp+1500h+var_14D8], ecx
0x180003673  mov     eax, [rbx+4]
0x180003676  mov     [rsp+1500h+var_14D4], eax
0x18000367a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000367f  mov     r12d, eax
0x180003682  mov     dword ptr [rsp+1500h+var_14E0], 3
0x18000368a  mov     ecx, r13d
0x18000368d  lea     eax, [r13+8]
0x180003691  cmp     dword ptr [rbx+8], 1
0x180003695  cmovz   ecx, eax
0x180003698  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000369c  lea     ecx, [rax-7]
0x18000369f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800036a7  inc     ecx
0x1800036a9  mov     [rsp+1500h+var_14D0], ecx
0x1800036ad  mov     rcx, [rbp+1400h+arg_38]
0x1800036b4  test    rcx, rcx
0x1800036b7  jz      short loc_1800036C4
0x1800036b9  cmp     [rcx], r13w
0x1800036bd  mov     [rsp+1500h+var_14C8], rcx
0x1800036c2  jnz     short loc_1800036C9
0x1800036c4  mov     [rsp+1500h+var_14C8], r13
0x1800036c9  call    cs:__imp_GetCurrentThreadId
0x1800036cf  mov     [rsp+1500h+var_14C0], eax
0x1800036d3  mov     [rsp+1500h+var_14A8], r14
0x1800036d8  mov     [rsp+1500h+var_14A0], esi
0x1800036dc  mov     [rsp+1500h+var_149C], r12d
0x1800036e1  mov     [rsp+1500h+var_14B8], r13
0x1800036e6  mov     [rsp+1500h+var_14B0], r13
0x1800036eb  mov     [rbp+1400h+var_1458], r15
0x1800036ef  mov     [rbp+1400h+var_1450], rdi
0x1800036f3  mov     [rsp+1500h+var_1498], r13
0x1800036f8  xorps   xmm0, xmm0
0x1800036fb  xor     eax, eax
0x1800036fd  movups  [rbp+1400h+var_1478], xmm0
0x180003701  mov     [rbp+1400h+var_1468], rax
0x180003705  xorps   xmm1, xmm1
0x180003708  movups  [rsp+1500h+var_1490], xmm1
0x18000370d  mov     [rbp+1400h+var_1480], rax
0x180003711  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003718  test    rax, rax
0x18000371b  jz      short loc_180003728
0x18000371d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003722  mov     [rbp+1400h+var_1460], rax
0x180003726  jmp     short loc_18000372C
0x180003728  mov     [rbp+1400h+var_1460], r13
0x18000372c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003733  test    rax, rax
0x180003736  jz      short loc_180003742
0x180003738  lea     rcx, [rsp+1500h+var_14E0]
0x18000373d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003742  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003749  test    rax, rax
0x18000374c  jz      short loc_180003762
0x18000374e  mov     r8d, 400h
0x180003754  lea     rdx, [rbp+1400h+var_1430]
0x180003758  lea     rcx, [rsp+1500h+var_14E0]
0x18000375d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003762  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003769  test    rax, rax
0x18000376c  jz      short loc_180003778
0x18000376e  lea     rcx, [rsp+1500h+var_14E0]
0x180003773  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003778  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000377f  test    rax, rax
0x180003782  jz      short loc_180003795
0x180003784  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003789  jnz     short loc_180003795
0x18000378b  lea     rcx, [rsp+1500h+var_14E0]
0x180003790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003795  cmp     [rsp+1500h+var_14D8], r13d
0x18000379a  jl      short loc_1800037AE
0x18000379c  mov     ecx, 8000FFFFh; this
0x1800037a1  mov     [rsp+1500h+var_14D8], ecx
0x1800037a5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800037aa  mov     [rsp+1500h+var_14D4], eax
0x1800037ae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800037b5  jnz     short loc_1800037D6
0x1800037b7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800037be  test    rax, rax
0x1800037c1  jz      short loc_1800037CC
0x1800037c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037c8  test    al, al
0x1800037ca  jmp     short loc_1800037D4
0x1800037cc  call    cs:__imp_IsDebuggerPresent
0x1800037d2  test    eax, eax
0x1800037d4  jz      short loc_1800037DD
0x1800037d6  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800037db  jz      short loc_180003803
0x1800037dd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037e4  test    rax, rax
0x1800037e7  jz      short loc_18000385C
0x1800037e9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800037f0  jnz     short loc_18000385C
0x1800037f2  xor     r8d, r8d
0x1800037f5  xor     edx, edx
0x1800037f7  lea     rcx, [rsp+1500h+var_14E0]
0x1800037fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003801  jmp     short loc_18000385C
0x180003803  mov     ebx, 800h
0x180003808  mov     rax, cs:g_pfnResultLoggingCallback
0x18000380f  test    rax, rax
0x180003812  jz      short loc_180003831
0x180003814  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000381b  jnz     short loc_180003831
0x18000381d  mov     r8d, ebx
0x180003820  lea     rdx, [rbp+1400h+OutputString]
0x180003827  lea     rcx, [rsp+1500h+var_14E0]
0x18000382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003831  cmp     [rbp+1400h+OutputString], r13w
0x180003839  jnz     short loc_18000384F
0x18000383b  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003840  mov     rdx, rbx; unsigned __int16 *
0x180003843  lea     rcx, [rbp+1400h+OutputString]; this
0x18000384a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000384f  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180003856  call    cs:__imp_OutputDebugStringW
0x18000385c  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003861  jnz     short loc_18000386C
0x180003863  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000386a  jz      short loc_18000387E
0x18000386c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003873  test    rax, rax
0x180003876  jz      short loc_18000387E
0x180003878  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000387d  nop
0x18000387e  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003883  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
