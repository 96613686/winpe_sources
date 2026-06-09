# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18002381c`
- end: `0x180023a8e`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `626`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, __int64, __int64, int *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180023430`

## callees

- `0x180002938`
- `0x18002381c`
- `0x18002582c`
- `0x180026038`
- `0x180026cf0`
- `0x180028b1c`
- `0x18005e040`
- `0x18005f010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800239c6`
- `KERNEL32!IsDebuggerPresent` at `0x1800239c6`
- `KERNEL32!OutputDebugStringW` at `0x180023a56`
- `KERNEL32!OutputDebugStringW` at `0x180023a56`
- `KERNEL32!GetCurrentThreadId` at `0x1800238bd`
- `KERNEL32!GetCurrentThreadId` at `0x1800238bd`

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
  int v10; // eax
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
  __int64 v28; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v10 = a7[1];
  v21 = *a7;
  v22 = v10;
  v11 = wil::details::RecordFailFast((wil::details *)(unsigned int)v21);
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
  v28 = a3;
  v25 = CurrentThreadId;
  v29 = a2;
  v35 = 0;
  v33 = 0;
  v30 = v12;
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
    v22 = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
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
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v19, v17);
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
0x18002381c  mov     [rsp-8+arg_18], rbx
0x180023821  push    rbp
0x180023822  push    rsi
0x180023823  push    rdi
0x180023824  push    r12
0x180023826  push    r13
0x180023828  push    r14
0x18002382a  push    r15
0x18002382c  lea     rbp, [rsp-13C0h]
0x180023834  mov     eax, 14C0h
0x180023839  call    _alloca_probe
0x18002383e  sub     rsp, rax
0x180023841  mov     rsi, [rbp+13F0h+arg_28]
0x180023848  mov     r15, r8
0x18002384b  mov     r14d, edx
0x18002384e  mov     r12, rcx
0x180023851  xor     edx, edx; Val
0x180023853  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180023858  mov     r8d, 98h; Size
0x18002385e  call    memset_0
0x180023863  mov     rbx, [rbp+13F0h+arg_30]
0x18002386a  xor     r13d, r13d
0x18002386d  mov     [rbp+13F0h+OutputString], r13w
0x180023875  mov     [rbp+13F0h+var_1430], r13b
0x180023879  mov     ecx, [rbx]; this
0x18002387b  mov     eax, [rbx+4]
0x18002387e  mov     [rsp+14F0h+var_14C8], ecx
0x180023882  mov     [rsp+14F0h+var_14C4], eax
0x180023886  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002388b  cmp     dword ptr [rbx+8], 1
0x18002388f  mov     edi, eax
0x180023891  lea     eax, [r13+8]
0x180023895  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18002389d  mov     ecx, r13d
0x1800238a0  cmovz   ecx, eax
0x1800238a3  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800238a7  lea     ecx, [rax-7]
0x1800238aa  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800238b2  inc     ecx
0x1800238b4  mov     [rsp+14F0h+var_14B8], r13
0x1800238b9  mov     [rsp+14F0h+var_14C0], ecx
0x1800238bd  call    cs:__imp_GetCurrentThreadId
0x1800238c4  nop     dword ptr [rax+rax+00h]
0x1800238c9  xorps   xmm0, xmm0
0x1800238cc  mov     [rsp+14F0h+var_1498], r15
0x1800238d1  mov     [rsp+14F0h+var_14B0], eax
0x1800238d5  xorps   xmm1, xmm1
0x1800238d8  xor     eax, eax
0x1800238da  mov     [rsp+14F0h+var_1490], r14d
0x1800238df  mov     [rbp+13F0h+var_1458], rax
0x1800238e3  mov     [rbp+13F0h+var_1470], rax
0x1800238e7  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800238ee  mov     [rsp+14F0h+var_148C], edi
0x1800238f2  mov     [rsp+14F0h+var_14A8], r13
0x1800238f7  mov     [rsp+14F0h+var_14A0], r13
0x1800238fc  mov     [rbp+13F0h+var_1448], rsi
0x180023900  mov     [rbp+13F0h+var_1440], r12
0x180023904  mov     [rsp+14F0h+var_1488], r13
0x180023909  movups  [rbp+13F0h+var_1468], xmm0
0x18002390d  movups  [rsp+14F0h+var_1480], xmm1
0x180023912  test    rax, rax
0x180023915  jz      short loc_180023922
0x180023917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002391c  mov     [rbp+13F0h+var_1450], rax
0x180023920  jmp     short loc_180023926
0x180023922  mov     [rbp+13F0h+var_1450], r13
0x180023926  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002392d  test    rax, rax
0x180023930  jz      short loc_18002393C
0x180023932  lea     rcx, [rsp+14F0h+var_14D0]
0x180023937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002393c  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180023943  test    rax, rax
0x180023946  jz      short loc_18002395C
0x180023948  mov     r8d, 400h
0x18002394e  lea     rdx, [rbp+13F0h+var_1430]
0x180023952  lea     rcx, [rsp+14F0h+var_14D0]
0x180023957  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002395c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023963  test    rax, rax
0x180023966  jz      short loc_180023972
0x180023968  lea     rcx, [rsp+14F0h+var_14D0]
0x18002396d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023972  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023979  test    rax, rax
0x18002397c  jz      short loc_18002398F
0x18002397e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180023983  jnz     short loc_18002398F
0x180023985  lea     rcx, [rsp+14F0h+var_14D0]
0x18002398a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002398f  cmp     [rsp+14F0h+var_14C8], r13d
0x180023994  jl      short loc_1800239A8
0x180023996  mov     ecx, 8000FFFFh; this
0x18002399b  mov     [rsp+14F0h+var_14C8], ecx
0x18002399f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800239a4  mov     [rsp+14F0h+var_14C4], eax
0x1800239a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x1800239af  jnz     short loc_1800239D6
0x1800239b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800239b8  test    rax, rax
0x1800239bb  jz      short loc_1800239C6
0x1800239bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800239c2  test    al, al
0x1800239c4  jmp     short loc_1800239D4
0x1800239c6  call    cs:__imp_IsDebuggerPresent
0x1800239cd  nop     dword ptr [rax+rax+00h]
0x1800239d2  test    eax, eax
0x1800239d4  jz      short loc_1800239DD
0x1800239d6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800239db  jz      short loc_180023A03
0x1800239dd  mov     rax, cs:g_pfnResultLoggingCallback
0x1800239e4  test    rax, rax
0x1800239e7  jz      short loc_180023A62
0x1800239e9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x1800239f0  jnz     short loc_180023A62
0x1800239f2  xor     r8d, r8d
0x1800239f5  lea     rcx, [rsp+14F0h+var_14D0]
0x1800239fa  xor     edx, edx
0x1800239fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a01  jmp     short loc_180023A62
0x180023a03  mov     rax, cs:g_pfnResultLoggingCallback
0x180023a0a  mov     ebx, 800h
0x180023a0f  test    rax, rax
0x180023a12  jz      short loc_180023A31
0x180023a14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180023a1b  jnz     short loc_180023A31
0x180023a1d  mov     r8d, ebx
0x180023a20  lea     rdx, [rbp+13F0h+OutputString]
0x180023a27  lea     rcx, [rsp+14F0h+var_14D0]
0x180023a2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a31  cmp     [rbp+13F0h+OutputString], r13w
0x180023a39  jnz     short loc_180023A4F
0x180023a3b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180023a40  mov     rdx, rbx; unsigned __int16 *
0x180023a43  lea     rcx, [rbp+13F0h+OutputString]; this
0x180023a4a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180023a4f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180023a56  call    cs:__imp_OutputDebugStringW
0x180023a5d  nop     dword ptr [rax+rax+00h]
0x180023a62  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180023a67  jnz     short loc_180023A72
0x180023a69  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180023a70  jz      short loc_180023A83
0x180023a72  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180023a79  test    rax, rax
0x180023a7c  jz      short loc_180023A83
0x180023a7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023a83  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180023a88  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
