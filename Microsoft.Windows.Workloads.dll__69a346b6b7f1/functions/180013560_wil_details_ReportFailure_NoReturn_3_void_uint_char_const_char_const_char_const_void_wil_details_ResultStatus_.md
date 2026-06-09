# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x180013560`
- end: `0x1800137da`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `634`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x1800137e0`

## callees

- `0x180002e30`
- `0x180002f70`
- `0x1800035a0`
- `0x1800039f0`
- `0x180013560`
- `0x180035c10`
- `0x18003bed0`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180013714`
- `KERNEL32!IsDebuggerPresent` at `0x180013714`
- `KERNEL32!GetCurrentThreadId` at `0x180013606`
- `KERNEL32!GetCurrentThreadId` at `0x180013606`
- `KERNEL32!OutputDebugStringW` at `0x1800137a6`
- `KERNEL32!OutputDebugStringW` at `0x1800137a6`

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
  int IsDebuggerPresent; // edi
  int v12; // r13d
  int v13; // ecx
  bool v14; // zf
  const struct wil::FailureInfo *v15; // rdx
  __int64 v16; // rcx
  const struct wil::FailureInfo *v17; // r9
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

  IsDebuggerPresent = 0;
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v12 = wil::details::RecordFailFast((wil::details *)(unsigned int)v20, a2);
  v18 = 3;
  v13 = 0;
  if ( a7[2] == 1 )
    v13 = 8;
  v19 = v13;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v23 = a8, v14) )
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
    ModuleName = wil::details::g_pfnGetModuleName(v16);
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
    v21 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, (int)v15);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v16)),
         IsDebuggerPresent))
    && (v19 & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v17);
    OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  if ( (v19 & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v16);
  }
  wil::details::WilFailFast((wil::details *)&v18, v15);
}

```

## disassembly

```asm
0x180013560  mov     [rsp-8+arg_18], rbx
0x180013565  push    rbp
0x180013566  push    rsi
0x180013567  push    rdi
0x180013568  push    r12
0x18001356a  push    r13
0x18001356c  push    r14
0x18001356e  push    r15
0x180013570  lea     rbp, [rsp-13C0h]
0x180013578  mov     eax, 14C0h
0x18001357d  call    _alloca_probe
0x180013582  sub     rsp, rax
0x180013585  mov     r15, r8
0x180013588  mov     r14d, edx
0x18001358b  mov     rsi, rcx
0x18001358e  mov     r12, [rbp+13F0h+arg_28]
0x180013595  xor     edi, edi
0x180013597  mov     [rbp+13F0h+OutputString], di
0x18001359e  mov     [rbp+13F0h+var_1430], dil
0x1800135a2  mov     rbx, [rbp+13F0h+arg_30]
0x1800135a9  mov     ecx, [rbx]; this
0x1800135ab  mov     [rsp+14F0h+var_14C8], ecx
0x1800135af  mov     eax, [rbx+4]
0x1800135b2  mov     [rsp+14F0h+var_14C4], eax
0x1800135b6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800135bb  mov     r13d, eax
0x1800135be  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800135c6  mov     ecx, edi
0x1800135c8  mov     eax, 8
0x1800135cd  cmp     dword ptr [rbx+8], 1
0x1800135d1  cmovz   ecx, eax
0x1800135d4  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800135d8  mov     ecx, 1
0x1800135dd  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800135e5  inc     ecx
0x1800135e7  mov     [rsp+14F0h+var_14C0], ecx
0x1800135eb  mov     rcx, [rbp+13F0h+arg_38]
0x1800135f2  test    rcx, rcx
0x1800135f5  jz      short loc_180013601
0x1800135f7  cmp     [rcx], di
0x1800135fa  mov     [rsp+14F0h+var_14B8], rcx
0x1800135ff  jnz     short loc_180013606
0x180013601  mov     [rsp+14F0h+var_14B8], rdi
0x180013606  call    cs:__imp_GetCurrentThreadId
0x18001360c  mov     [rsp+14F0h+var_14B0], eax
0x180013610  mov     [rsp+14F0h+var_1498], r15
0x180013615  mov     [rsp+14F0h+var_1490], r14d
0x18001361a  mov     [rsp+14F0h+var_148C], r13d
0x18001361f  mov     [rsp+14F0h+var_14A8], rdi
0x180013624  mov     [rsp+14F0h+var_14A0], rdi
0x180013629  mov     [rbp+13F0h+var_1448], r12
0x18001362d  mov     [rbp+13F0h+var_1440], rsi
0x180013631  mov     [rsp+14F0h+var_1488], rdi
0x180013636  xorps   xmm0, xmm0
0x180013639  xor     eax, eax
0x18001363b  movups  [rbp+13F0h+var_1468], xmm0
0x18001363f  mov     [rbp+13F0h+var_1458], rax
0x180013643  xorps   xmm1, xmm1
0x180013646  movups  [rsp+14F0h+var_1480], xmm1
0x18001364b  mov     [rbp+13F0h+var_1470], rax
0x18001364f  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013656  test    rax, rax
0x180013659  jz      short loc_180013667
0x18001365b  call    cs:__guard_dispatch_icall_fptr
0x180013661  mov     [rbp+13F0h+var_1450], rax
0x180013665  jmp     short loc_18001366B
0x180013667  mov     [rbp+13F0h+var_1450], rdi
0x18001366b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013672  test    rax, rax
0x180013675  jz      short loc_180013682
0x180013677  lea     rcx, [rsp+14F0h+var_14D0]
0x18001367c  call    cs:__guard_dispatch_icall_fptr
0x180013682  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013689  test    rax, rax
0x18001368c  jz      short loc_1800136A3
0x18001368e  mov     r8d, 400h
0x180013694  lea     rdx, [rbp+13F0h+var_1430]
0x180013698  lea     rcx, [rsp+14F0h+var_14D0]
0x18001369d  call    cs:__guard_dispatch_icall_fptr
0x1800136a3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800136aa  test    rax, rax
0x1800136ad  jz      short loc_1800136BA
0x1800136af  lea     rcx, [rsp+14F0h+var_14D0]
0x1800136b4  call    cs:__guard_dispatch_icall_fptr
0x1800136ba  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800136c1  test    rax, rax
0x1800136c4  jz      short loc_1800136D8
0x1800136c6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800136cb  jnz     short loc_1800136D8
0x1800136cd  lea     rcx, [rsp+14F0h+var_14D0]
0x1800136d2  call    cs:__guard_dispatch_icall_fptr
0x1800136d8  cmp     [rsp+14F0h+var_14C8], edi
0x1800136dc  jl      short loc_1800136F4
0x1800136de  mov     [rsp+14F0h+var_14C8], 8000FFFFh
0x1800136e6  mov     ecx, 8000FFFFh; this
0x1800136eb  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800136f0  mov     [rsp+14F0h+var_14C4], eax
0x1800136f4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800136fb  jnz     short loc_180013724
0x1800136fd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180013704  test    rax, rax
0x180013707  jz      short loc_180013714
0x180013709  call    cs:__guard_dispatch_icall_fptr
0x18001370f  movzx   edi, al
0x180013712  jmp     short loc_180013720
0x180013714  call    cs:__imp_IsDebuggerPresent
0x18001371a  test    eax, eax
0x18001371c  setnz   dil
0x180013720  test    edi, edi
0x180013722  jz      short loc_18001372B
0x180013724  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180013729  jz      short loc_180013752
0x18001372b  mov     rax, cs:g_pfnResultLoggingCallback
0x180013732  test    rax, rax
0x180013735  jz      short loc_1800137AC
0x180013737  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18001373e  jnz     short loc_1800137AC
0x180013740  xor     r8d, r8d
0x180013743  xor     edx, edx
0x180013745  lea     rcx, [rsp+14F0h+var_14D0]
0x18001374a  call    cs:__guard_dispatch_icall_fptr
0x180013750  jmp     short loc_1800137AC
0x180013752  mov     rax, cs:g_pfnResultLoggingCallback
0x180013759  test    rax, rax
0x18001375c  jz      short loc_18001377F
0x18001375e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180013765  jnz     short loc_18001377F
0x180013767  mov     r8d, 800h
0x18001376d  lea     rdx, [rbp+13F0h+OutputString]
0x180013774  lea     rcx, [rsp+14F0h+var_14D0]
0x180013779  call    cs:__guard_dispatch_icall_fptr
0x18001377f  cmp     [rbp+13F0h+OutputString], 0
0x180013787  jnz     short loc_18001379F
0x180013789  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001378e  mov     edx, 800h; wchar_t *
0x180013793  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001379a  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18001379f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x1800137a6  call    cs:__imp_OutputDebugStringW
0x1800137ac  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x1800137b1  jnz     short loc_1800137BC
0x1800137b3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1800137ba  jz      short loc_1800137CF
0x1800137bc  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800137c3  test    rax, rax
0x1800137c6  jz      short loc_1800137CF
0x1800137c8  call    cs:__guard_dispatch_icall_fptr
0x1800137ce  nop
0x1800137cf  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800137d4  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
