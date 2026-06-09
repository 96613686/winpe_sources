# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x140007f20`
- end: `0x140008180`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x140007cc4`

## callees

- `0x140007f20`
- `0x140009e34`
- `0x14000a5cc`
- `0x14000b0f0`
- `0x14000cbf0`
- `0x14001094e`
- `0x140010a10`
- `0x140011010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x14000814e`
- `KERNEL32!OutputDebugStringW` at `0x14000814e`
- `KERNEL32!IsDebuggerPresent` at `0x1400080c4`
- `KERNEL32!IsDebuggerPresent` at `0x1400080c4`
- `KERNEL32!GetCurrentThreadId` at `0x140007fc1`
- `KERNEL32!GetCurrentThreadId` at `0x140007fc1`

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
0x140007f20  mov     [rsp-8+arg_18], rbx
0x140007f25  push    rbp
0x140007f26  push    rsi
0x140007f27  push    rdi
0x140007f28  push    r12
0x140007f2a  push    r13
0x140007f2c  push    r14
0x140007f2e  push    r15
0x140007f30  lea     rbp, [rsp-13C0h]
0x140007f38  mov     eax, 14C0h
0x140007f3d  call    _alloca_probe
0x140007f42  sub     rsp, rax
0x140007f45  mov     rsi, [rbp+13F0h+arg_28]
0x140007f4c  mov     r15, r8
0x140007f4f  mov     r14d, edx
0x140007f52  mov     r12, rcx
0x140007f55  xor     edx, edx; Val
0x140007f57  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x140007f5c  mov     r8d, 98h; Size
0x140007f62  call    memset_0
0x140007f67  mov     rbx, [rbp+13F0h+arg_30]
0x140007f6e  xor     r13d, r13d
0x140007f71  mov     [rbp+13F0h+OutputString], r13w
0x140007f79  mov     [rbp+13F0h+var_1430], r13b
0x140007f7d  mov     ecx, [rbx]; this
0x140007f7f  mov     eax, [rbx+4]
0x140007f82  mov     [rsp+14F0h+var_14C8], ecx
0x140007f86  mov     [rsp+14F0h+var_14C4], eax
0x140007f8a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007f8f  cmp     dword ptr [rbx+8], 1
0x140007f93  mov     edi, eax
0x140007f95  lea     eax, [r13+8]
0x140007f99  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x140007fa1  mov     ecx, r13d
0x140007fa4  cmovz   ecx, eax
0x140007fa7  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x140007fab  lea     ecx, [rax-7]
0x140007fae  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007fb6  inc     ecx
0x140007fb8  mov     [rsp+14F0h+var_14B8], r13
0x140007fbd  mov     [rsp+14F0h+var_14C0], ecx
0x140007fc1  call    cs:__imp_GetCurrentThreadId
0x140007fc7  xorps   xmm0, xmm0
0x140007fca  mov     [rsp+14F0h+var_1498], r15
0x140007fcf  mov     [rsp+14F0h+var_14B0], eax
0x140007fd3  xorps   xmm1, xmm1
0x140007fd6  xor     eax, eax
0x140007fd8  mov     [rsp+14F0h+var_1490], r14d
0x140007fdd  mov     [rbp+13F0h+var_1458], rax
0x140007fe1  mov     [rbp+13F0h+var_1470], rax
0x140007fe5  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007fec  mov     [rsp+14F0h+var_148C], edi
0x140007ff0  mov     [rsp+14F0h+var_14A8], r13
0x140007ff5  mov     [rsp+14F0h+var_14A0], r13
0x140007ffa  mov     [rbp+13F0h+var_1448], rsi
0x140007ffe  mov     [rbp+13F0h+var_1440], r12
0x140008002  mov     [rsp+14F0h+var_1488], r13
0x140008007  movups  [rbp+13F0h+var_1468], xmm0
0x14000800b  movups  [rsp+14F0h+var_1480], xmm1
0x140008010  test    rax, rax
0x140008013  jz      short loc_140008020
0x140008015  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000801a  mov     [rbp+13F0h+var_1450], rax
0x14000801e  jmp     short loc_140008024
0x140008020  mov     [rbp+13F0h+var_1450], r13
0x140008024  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000802b  test    rax, rax
0x14000802e  jz      short loc_14000803A
0x140008030  lea     rcx, [rsp+14F0h+var_14D0]
0x140008035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000803a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140008041  test    rax, rax
0x140008044  jz      short loc_14000805A
0x140008046  mov     r8d, 400h
0x14000804c  lea     rdx, [rbp+13F0h+var_1430]
0x140008050  lea     rcx, [rsp+14F0h+var_14D0]
0x140008055  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000805a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140008061  test    rax, rax
0x140008064  jz      short loc_140008070
0x140008066  lea     rcx, [rsp+14F0h+var_14D0]
0x14000806b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008070  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140008077  test    rax, rax
0x14000807a  jz      short loc_14000808D
0x14000807c  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x140008081  jnz     short loc_14000808D
0x140008083  lea     rcx, [rsp+14F0h+var_14D0]
0x140008088  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000808d  cmp     [rsp+14F0h+var_14C8], r13d
0x140008092  jl      short loc_1400080A6
0x140008094  mov     ecx, 8000FFFFh; this
0x140008099  mov     [rsp+14F0h+var_14C8], ecx
0x14000809d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400080a2  mov     [rsp+14F0h+var_14C4], eax
0x1400080a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1400080ad  jnz     short loc_1400080CE
0x1400080af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400080b6  test    rax, rax
0x1400080b9  jz      short loc_1400080C4
0x1400080bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080c0  test    al, al
0x1400080c2  jmp     short loc_1400080CC
0x1400080c4  call    cs:__imp_IsDebuggerPresent
0x1400080ca  test    eax, eax
0x1400080cc  jz      short loc_1400080D5
0x1400080ce  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1400080d3  jz      short loc_1400080FB
0x1400080d5  mov     rax, cs:g_pfnResultLoggingCallback
0x1400080dc  test    rax, rax
0x1400080df  jz      short loc_140008154
0x1400080e1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1400080e8  jnz     short loc_140008154
0x1400080ea  xor     r8d, r8d
0x1400080ed  lea     rcx, [rsp+14F0h+var_14D0]
0x1400080f2  xor     edx, edx
0x1400080f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400080f9  jmp     short loc_140008154
0x1400080fb  mov     rax, cs:g_pfnResultLoggingCallback
0x140008102  mov     ebx, 800h
0x140008107  test    rax, rax
0x14000810a  jz      short loc_140008129
0x14000810c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x140008113  jnz     short loc_140008129
0x140008115  mov     r8d, ebx
0x140008118  lea     rdx, [rbp+13F0h+OutputString]
0x14000811f  lea     rcx, [rsp+14F0h+var_14D0]
0x140008124  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008129  cmp     [rbp+13F0h+OutputString], r13w
0x140008131  jnz     short loc_140008147
0x140008133  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x140008138  mov     rdx, rbx; unsigned __int16 *
0x14000813b  lea     rcx, [rbp+13F0h+OutputString]; this
0x140008142  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140008147  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x14000814e  call    cs:__imp_OutputDebugStringW
0x140008154  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x140008159  jnz     short loc_140008164
0x14000815b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x140008162  jz      short loc_140008175
0x140008164  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000816b  test    rax, rax
0x14000816e  jz      short loc_140008175
0x140008170  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008175  lea     rcx, [rsp+14F0h+var_14D0]; this
0x14000817a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
