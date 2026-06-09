# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18007542c`
- end: `0x18007568c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800751f8`

## callees

- `0x18007542c`
- `0x180077204`
- `0x180077ad4`
- `0x180079190`
- `0x18007acd0`
- `0x18009110a`
- `0x1800911d0`
- `0x180092010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1800754cd`
- `KERNEL32!GetCurrentThreadId` at `0x1800754cd`
- `KERNEL32!IsDebuggerPresent` at `0x1800755d0`
- `KERNEL32!IsDebuggerPresent` at `0x1800755d0`
- `KERNEL32!OutputDebugStringW` at `0x18007565a`
- `KERNEL32!OutputDebugStringW` at `0x18007565a`

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
0x18007542c  mov     [rsp-8+arg_18], rbx
0x180075431  push    rbp
0x180075432  push    rsi
0x180075433  push    rdi
0x180075434  push    r12
0x180075436  push    r13
0x180075438  push    r14
0x18007543a  push    r15
0x18007543c  lea     rbp, [rsp-13C0h]
0x180075444  mov     eax, 14C0h
0x180075449  call    _alloca_probe
0x18007544e  sub     rsp, rax
0x180075451  mov     rsi, [rbp+13F0h+arg_28]
0x180075458  mov     r15, r8
0x18007545b  mov     r14d, edx
0x18007545e  mov     r12, rcx
0x180075461  xor     edx, edx; Val
0x180075463  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180075468  mov     r8d, 98h; Size
0x18007546e  call    memset_0
0x180075473  mov     rbx, [rbp+13F0h+arg_30]
0x18007547a  xor     r13d, r13d
0x18007547d  mov     [rbp+13F0h+OutputString], r13w
0x180075485  mov     [rbp+13F0h+var_1430], r13b
0x180075489  mov     ecx, [rbx]; this
0x18007548b  mov     eax, [rbx+4]
0x18007548e  mov     [rsp+14F0h+var_14C8], ecx
0x180075492  mov     [rsp+14F0h+var_14C4], eax
0x180075496  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18007549b  cmp     dword ptr [rbx+8], 1
0x18007549f  mov     edi, eax
0x1800754a1  lea     eax, [r13+8]
0x1800754a5  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x1800754ad  mov     ecx, r13d
0x1800754b0  cmovz   ecx, eax
0x1800754b3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800754b7  lea     ecx, [rax-7]
0x1800754ba  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800754c2  inc     ecx
0x1800754c4  mov     [rsp+14F0h+var_14B8], r13
0x1800754c9  mov     [rsp+14F0h+var_14C0], ecx
0x1800754cd  call    cs:__imp_GetCurrentThreadId
0x1800754d3  xorps   xmm0, xmm0
0x1800754d6  mov     [rsp+14F0h+var_1498], r15
0x1800754db  mov     [rsp+14F0h+var_14B0], eax
0x1800754df  xorps   xmm1, xmm1
0x1800754e2  xor     eax, eax
0x1800754e4  mov     [rsp+14F0h+var_1490], r14d
0x1800754e9  mov     [rbp+13F0h+var_1458], rax
0x1800754ed  mov     [rbp+13F0h+var_1470], rax
0x1800754f1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800754f8  mov     [rsp+14F0h+var_148C], edi
0x1800754fc  mov     [rsp+14F0h+var_14A8], r13
0x180075501  mov     [rsp+14F0h+var_14A0], r13
0x180075506  mov     [rbp+13F0h+var_1448], rsi
0x18007550a  mov     [rbp+13F0h+var_1440], r12
0x18007550e  mov     [rsp+14F0h+var_1488], r13
0x180075513  movups  [rbp+13F0h+var_1468], xmm0
0x180075517  movups  [rsp+14F0h+var_1480], xmm1
0x18007551c  test    rax, rax
0x18007551f  jz      short loc_18007552C
0x180075521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075526  mov     [rbp+13F0h+var_1450], rax
0x18007552a  jmp     short loc_180075530
0x18007552c  mov     [rbp+13F0h+var_1450], r13
0x180075530  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180075537  test    rax, rax
0x18007553a  jz      short loc_180075546
0x18007553c  lea     rcx, [rsp+14F0h+var_14D0]
0x180075541  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075546  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18007554d  test    rax, rax
0x180075550  jz      short loc_180075566
0x180075552  mov     r8d, 400h
0x180075558  lea     rdx, [rbp+13F0h+var_1430]
0x18007555c  lea     rcx, [rsp+14F0h+var_14D0]
0x180075561  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075566  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18007556d  test    rax, rax
0x180075570  jz      short loc_18007557C
0x180075572  lea     rcx, [rsp+14F0h+var_14D0]
0x180075577  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007557c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180075583  test    rax, rax
0x180075586  jz      short loc_180075599
0x180075588  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18007558d  jnz     short loc_180075599
0x18007558f  lea     rcx, [rsp+14F0h+var_14D0]
0x180075594  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075599  cmp     [rsp+14F0h+var_14C8], r13d
0x18007559e  jl      short loc_1800755B2
0x1800755a0  mov     ecx, 8000FFFFh; this
0x1800755a5  mov     [rsp+14F0h+var_14C8], ecx
0x1800755a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800755ae  mov     [rsp+14F0h+var_14C4], eax
0x1800755b2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800755b9  jnz     short loc_1800755DA
0x1800755bb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800755c2  test    rax, rax
0x1800755c5  jz      short loc_1800755D0
0x1800755c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800755cc  test    al, al
0x1800755ce  jmp     short loc_1800755D8
0x1800755d0  call    cs:__imp_IsDebuggerPresent
0x1800755d6  test    eax, eax
0x1800755d8  jz      short loc_1800755E1
0x1800755da  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800755df  jz      short loc_180075607
0x1800755e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800755e8  test    rax, rax
0x1800755eb  jz      short loc_180075660
0x1800755ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800755f4  jnz     short loc_180075660
0x1800755f6  xor     r8d, r8d
0x1800755f9  lea     rcx, [rsp+14F0h+var_14D0]
0x1800755fe  xor     edx, edx
0x180075600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075605  jmp     short loc_180075660
0x180075607  mov     rax, cs:g_pfnResultLoggingCallback
0x18007560e  mov     ebx, 800h
0x180075613  test    rax, rax
0x180075616  jz      short loc_180075635
0x180075618  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18007561f  jnz     short loc_180075635
0x180075621  mov     r8d, ebx
0x180075624  lea     rdx, [rbp+13F0h+OutputString]
0x18007562b  lea     rcx, [rsp+14F0h+var_14D0]
0x180075630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075635  cmp     [rbp+13F0h+OutputString], r13w
0x18007563d  jnz     short loc_180075653
0x18007563f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180075644  mov     rdx, rbx; unsigned __int16 *
0x180075647  lea     rcx, [rbp+13F0h+OutputString]; this
0x18007564e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180075653  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18007565a  call    cs:__imp_OutputDebugStringW
0x180075660  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180075665  jnz     short loc_180075670
0x180075667  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18007566e  jz      short loc_180075681
0x180075670  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180075677  test    rax, rax
0x18007567a  jz      short loc_180075681
0x18007567c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180075681  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180075686  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
