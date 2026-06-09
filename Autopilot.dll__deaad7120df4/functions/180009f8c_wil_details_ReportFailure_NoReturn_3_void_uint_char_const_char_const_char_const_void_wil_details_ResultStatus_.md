# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180009f8c`
- end: `0x18000a217`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `651`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180009d04`

## callees

- `0x1800053c4`
- `0x180009f8c`
- `0x18000d284`
- `0x18000dbf0`
- `0x18000f1b0`
- `0x180011efc`
- `0x1800294b0`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a045`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a045`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a14e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a14e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a1de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a1de`

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
0x180009f8c  mov     [rsp-8+arg_18], rbx
0x180009f91  push    rbp
0x180009f92  push    rsi
0x180009f93  push    rdi
0x180009f94  push    r12
0x180009f96  push    r13
0x180009f98  push    r14
0x180009f9a  push    r15
0x180009f9c  lea     rbp, [rsp-13C0h]
0x180009fa4  mov     eax, 14C0h
0x180009fa9  call    _alloca_probe
0x180009fae  sub     rsp, rax
0x180009fb1  mov     r14, r8
0x180009fb4  mov     esi, edx
0x180009fb6  mov     rdi, rcx
0x180009fb9  mov     r15, [rbp+13F0h+arg_28]
0x180009fc0  xor     edx, edx; Val
0x180009fc2  mov     r8d, 98h; Size
0x180009fc8  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180009fcd  call    memset_0
0x180009fd2  nop
0x180009fd3  xor     r13d, r13d
0x180009fd6  mov     [rbp+13F0h+OutputString], r13w
0x180009fde  mov     [rbp+13F0h+var_1430], r13b
0x180009fe2  mov     rbx, [rbp+13F0h+arg_30]
0x180009fe9  mov     ecx, [rbx]; this
0x180009feb  mov     [rsp+14F0h+var_14C8], ecx
0x180009fef  mov     eax, [rbx+4]
0x180009ff2  mov     [rsp+14F0h+var_14C4], eax
0x180009ff6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009ffb  mov     r12d, eax
0x180009ffe  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000a006  mov     ecx, r13d
0x18000a009  lea     eax, [r13+8]
0x18000a00d  cmp     dword ptr [rbx+8], 1
0x18000a011  cmovz   ecx, eax
0x18000a014  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000a018  lea     ecx, [rax-7]
0x18000a01b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a023  inc     ecx
0x18000a025  mov     [rsp+14F0h+var_14C0], ecx
0x18000a029  mov     rcx, [rbp+13F0h+arg_38]
0x18000a030  test    rcx, rcx
0x18000a033  jz      short loc_18000A040
0x18000a035  cmp     [rcx], r13w
0x18000a039  mov     [rsp+14F0h+var_14B8], rcx
0x18000a03e  jnz     short loc_18000A045
0x18000a040  mov     [rsp+14F0h+var_14B8], r13
0x18000a045  call    cs:__imp_GetCurrentThreadId
0x18000a04c  nop     dword ptr [rax+rax+00h]
0x18000a051  mov     [rsp+14F0h+var_14B0], eax
0x18000a055  mov     [rsp+14F0h+var_1498], r14
0x18000a05a  mov     [rsp+14F0h+var_1490], esi
0x18000a05e  mov     [rsp+14F0h+var_148C], r12d
0x18000a063  mov     [rsp+14F0h+var_14A8], r13
0x18000a068  mov     [rsp+14F0h+var_14A0], r13
0x18000a06d  mov     [rbp+13F0h+var_1448], r15
0x18000a071  mov     [rbp+13F0h+var_1440], rdi
0x18000a075  mov     [rsp+14F0h+var_1488], r13
0x18000a07a  xorps   xmm0, xmm0
0x18000a07d  xor     eax, eax
0x18000a07f  movups  [rbp+13F0h+var_1468], xmm0
0x18000a083  mov     [rbp+13F0h+var_1458], rax
0x18000a087  xorps   xmm1, xmm1
0x18000a08a  movups  [rsp+14F0h+var_1480], xmm1
0x18000a08f  mov     [rbp+13F0h+var_1470], rax
0x18000a093  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a09a  test    rax, rax
0x18000a09d  jz      short loc_18000A0AA
0x18000a09f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0a4  mov     [rbp+13F0h+var_1450], rax
0x18000a0a8  jmp     short loc_18000A0AE
0x18000a0aa  mov     [rbp+13F0h+var_1450], r13
0x18000a0ae  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a0b5  test    rax, rax
0x18000a0b8  jz      short loc_18000A0C4
0x18000a0ba  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a0bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a0cb  test    rax, rax
0x18000a0ce  jz      short loc_18000A0E4
0x18000a0d0  mov     r8d, 400h
0x18000a0d6  lea     rdx, [rbp+13F0h+var_1430]
0x18000a0da  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a0df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0e4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a0eb  test    rax, rax
0x18000a0ee  jz      short loc_18000A0FA
0x18000a0f0  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a0f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0fa  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a101  test    rax, rax
0x18000a104  jz      short loc_18000A117
0x18000a106  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a10b  jnz     short loc_18000A117
0x18000a10d  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a117  cmp     [rsp+14F0h+var_14C8], r13d
0x18000a11c  jl      short loc_18000A130
0x18000a11e  mov     ecx, 8000FFFFh; this
0x18000a123  mov     [rsp+14F0h+var_14C8], ecx
0x18000a127  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a12c  mov     [rsp+14F0h+var_14C4], eax
0x18000a130  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000a137  jnz     short loc_18000A15E
0x18000a139  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a140  test    rax, rax
0x18000a143  jz      short loc_18000A14E
0x18000a145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a14a  test    al, al
0x18000a14c  jmp     short loc_18000A15C
0x18000a14e  call    cs:__imp_IsDebuggerPresent
0x18000a155  nop     dword ptr [rax+rax+00h]
0x18000a15a  test    eax, eax
0x18000a15c  jz      short loc_18000A165
0x18000a15e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000a163  jz      short loc_18000A18B
0x18000a165  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a16c  test    rax, rax
0x18000a16f  jz      short loc_18000A1EA
0x18000a171  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a178  jnz     short loc_18000A1EA
0x18000a17a  xor     r8d, r8d
0x18000a17d  xor     edx, edx
0x18000a17f  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a189  jmp     short loc_18000A1EA
0x18000a18b  mov     ebx, 800h
0x18000a190  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a197  test    rax, rax
0x18000a19a  jz      short loc_18000A1B9
0x18000a19c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000a1a3  jnz     short loc_18000A1B9
0x18000a1a5  mov     r8d, ebx
0x18000a1a8  lea     rdx, [rbp+13F0h+OutputString]
0x18000a1af  lea     rcx, [rsp+14F0h+var_14D0]
0x18000a1b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1b9  cmp     [rbp+13F0h+OutputString], r13w
0x18000a1c1  jnz     short loc_18000A1D7
0x18000a1c3  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000a1c8  mov     rdx, rbx; unsigned __int16 *
0x18000a1cb  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000a1d2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a1d7  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000a1de  call    cs:__imp_OutputDebugStringW
0x18000a1e5  nop     dword ptr [rax+rax+00h]
0x18000a1ea  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000a1ef  jnz     short loc_18000A1FA
0x18000a1f1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000a1f8  jz      short loc_18000A20C
0x18000a1fa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a201  test    rax, rax
0x18000a204  jz      short loc_18000A20C
0x18000a206  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a20b  nop
0x18000a20c  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000a211  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
