# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001040c`
- end: `0x180010680`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `628`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800101a8`

## callees

- `0x18001040c`
- `0x1800127e4`
- `0x180012ff0`
- `0x180014010`
- `0x180016460`
- `0x18001899e`
- `0x180018a60`
- `0x180019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800105b7`
- `KERNEL32!IsDebuggerPresent` at `0x1800105b7`
- `KERNEL32!OutputDebugStringW` at `0x180010647`
- `KERNEL32!OutputDebugStringW` at `0x180010647`
- `KERNEL32!GetCurrentThreadId` at `0x1800104ae`
- `KERNEL32!GetCurrentThreadId` at `0x1800104ae`

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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v17, v15);
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
0x18001040c  mov     [rsp-8+arg_18], rbx
0x180010411  push    rbp
0x180010412  push    rsi
0x180010413  push    rdi
0x180010414  push    r12
0x180010416  push    r13
0x180010418  push    r14
0x18001041a  push    r15
0x18001041c  lea     rbp, [rsp-13C0h]
0x180010424  mov     eax, 14C0h
0x180010429  call    _alloca_probe
0x18001042e  sub     rsp, rax
0x180010431  mov     r15, r8
0x180010434  mov     r14d, edx
0x180010437  mov     r12, rcx
0x18001043a  mov     rsi, [rbp+13F0h+arg_28]
0x180010441  xor     edx, edx; Val
0x180010443  mov     r8d, 98h; Size
0x180010449  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001044e  call    memset_0
0x180010453  nop
0x180010454  xor     r13d, r13d
0x180010457  mov     [rbp+13F0h+OutputString], r13w
0x18001045f  mov     [rbp+13F0h+var_1430], r13b
0x180010463  mov     rbx, [rbp+13F0h+arg_30]
0x18001046a  mov     ecx, [rbx]; this
0x18001046c  mov     [rsp+14F0h+var_14C8], ecx
0x180010470  mov     eax, [rbx+4]
0x180010473  mov     [rsp+14F0h+var_14C4], eax
0x180010477  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001047c  mov     edi, eax
0x18001047e  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180010486  mov     ecx, r13d
0x180010489  lea     eax, [r13+8]
0x18001048d  cmp     dword ptr [rbx+8], 1
0x180010491  cmovz   ecx, eax
0x180010494  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180010498  lea     ecx, [rax-7]
0x18001049b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800104a3  inc     ecx
0x1800104a5  mov     [rsp+14F0h+var_14C0], ecx
0x1800104a9  mov     [rsp+14F0h+var_14B8], r13
0x1800104ae  call    cs:__imp_GetCurrentThreadId
0x1800104b5  nop     dword ptr [rax+rax+00h]
0x1800104ba  mov     [rsp+14F0h+var_14B0], eax
0x1800104be  mov     [rsp+14F0h+var_1498], r15
0x1800104c3  mov     [rsp+14F0h+var_1490], r14d
0x1800104c8  mov     [rsp+14F0h+var_148C], edi
0x1800104cc  mov     [rsp+14F0h+var_14A8], r13
0x1800104d1  mov     [rsp+14F0h+var_14A0], r13
0x1800104d6  mov     [rbp+13F0h+var_1448], rsi
0x1800104da  mov     [rbp+13F0h+var_1440], r12
0x1800104de  mov     [rsp+14F0h+var_1488], r13
0x1800104e3  xorps   xmm0, xmm0
0x1800104e6  xor     eax, eax
0x1800104e8  movups  [rbp+13F0h+var_1468], xmm0
0x1800104ec  mov     [rbp+13F0h+var_1458], rax
0x1800104f0  xorps   xmm1, xmm1
0x1800104f3  movups  [rsp+14F0h+var_1480], xmm1
0x1800104f8  mov     [rbp+13F0h+var_1470], rax
0x1800104fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010503  test    rax, rax
0x180010506  jz      short loc_180010513
0x180010508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001050d  mov     [rbp+13F0h+var_1450], rax
0x180010511  jmp     short loc_180010517
0x180010513  mov     [rbp+13F0h+var_1450], r13
0x180010517  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001051e  test    rax, rax
0x180010521  jz      short loc_18001052D
0x180010523  lea     rcx, [rsp+14F0h+var_14D0]
0x180010528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001052d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010534  test    rax, rax
0x180010537  jz      short loc_18001054D
0x180010539  mov     r8d, 400h
0x18001053f  lea     rdx, [rbp+13F0h+var_1430]
0x180010543  lea     rcx, [rsp+14F0h+var_14D0]
0x180010548  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001054d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010554  test    rax, rax
0x180010557  jz      short loc_180010563
0x180010559  lea     rcx, [rsp+14F0h+var_14D0]
0x18001055e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010563  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001056a  test    rax, rax
0x18001056d  jz      short loc_180010580
0x18001056f  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010574  jnz     short loc_180010580
0x180010576  lea     rcx, [rsp+14F0h+var_14D0]
0x18001057b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010580  cmp     [rsp+14F0h+var_14C8], r13d
0x180010585  jl      short loc_180010599
0x180010587  mov     ecx, 8000FFFFh; this
0x18001058c  mov     [rsp+14F0h+var_14C8], ecx
0x180010590  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010595  mov     [rsp+14F0h+var_14C4], eax
0x180010599  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800105a0  jnz     short loc_1800105C7
0x1800105a2  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800105a9  test    rax, rax
0x1800105ac  jz      short loc_1800105B7
0x1800105ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105b3  test    al, al
0x1800105b5  jmp     short loc_1800105C5
0x1800105b7  call    cs:__imp_IsDebuggerPresent
0x1800105be  nop     dword ptr [rax+rax+00h]
0x1800105c3  test    eax, eax
0x1800105c5  jz      short loc_1800105CE
0x1800105c7  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800105cc  jz      short loc_1800105F4
0x1800105ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800105d5  test    rax, rax
0x1800105d8  jz      short loc_180010653
0x1800105da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800105e1  jnz     short loc_180010653
0x1800105e3  xor     r8d, r8d
0x1800105e6  xor     edx, edx
0x1800105e8  lea     rcx, [rsp+14F0h+var_14D0]
0x1800105ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105f2  jmp     short loc_180010653
0x1800105f4  mov     ebx, 800h
0x1800105f9  mov     rax, cs:g_pfnResultLoggingCallback
0x180010600  test    rax, rax
0x180010603  jz      short loc_180010622
0x180010605  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001060c  jnz     short loc_180010622
0x18001060e  mov     r8d, ebx
0x180010611  lea     rdx, [rbp+13F0h+OutputString]
0x180010618  lea     rcx, [rsp+14F0h+var_14D0]
0x18001061d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010622  cmp     [rbp+13F0h+OutputString], r13w
0x18001062a  jnz     short loc_180010640
0x18001062c  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180010631  mov     rdx, rbx; unsigned __int16 *
0x180010634  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001063b  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010640  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180010647  call    cs:__imp_OutputDebugStringW
0x18001064e  nop     dword ptr [rax+rax+00h]
0x180010653  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180010658  jnz     short loc_180010663
0x18001065a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180010661  jz      short loc_180010675
0x180010663  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001066a  test    rax, rax
0x18001066d  jz      short loc_180010675
0x18001066f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010674  nop
0x180010675  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001067a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
