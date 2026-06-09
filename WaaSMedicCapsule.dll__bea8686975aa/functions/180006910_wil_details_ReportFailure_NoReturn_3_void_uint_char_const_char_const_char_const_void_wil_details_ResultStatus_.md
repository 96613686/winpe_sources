# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180006910`
- end: `0x180006b89`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x180006680`

## callees

- `0x180004708`
- `0x180006910`
- `0x180008254`
- `0x180008b98`
- `0x180009770`
- `0x18000a9b0`
- `0x180060700`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069c9`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800069c9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006b56`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006b56`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006acc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006acc`

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
0x180006910  mov     [rsp-8+arg_18], rbx
0x180006915  push    rbp
0x180006916  push    rsi
0x180006917  push    rdi
0x180006918  push    r12
0x18000691a  push    r13
0x18000691c  push    r14
0x18000691e  push    r15
0x180006920  lea     rbp, [rsp-13C0h]
0x180006928  mov     eax, 14C0h
0x18000692d  call    _alloca_probe
0x180006932  sub     rsp, rax
0x180006935  mov     r14, r8
0x180006938  mov     esi, edx
0x18000693a  mov     rdi, rcx
0x18000693d  mov     r15, [rbp+13F0h+arg_28]
0x180006944  xor     edx, edx; Val
0x180006946  mov     r8d, 98h; Size
0x18000694c  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180006951  call    memset_0
0x180006956  nop
0x180006957  xor     r13d, r13d
0x18000695a  mov     [rbp+13F0h+OutputString], r13w
0x180006962  mov     [rbp+13F0h+var_1430], r13b
0x180006966  mov     rbx, [rbp+13F0h+arg_30]
0x18000696d  mov     ecx, [rbx]; this
0x18000696f  mov     [rsp+14F0h+var_14C8], ecx
0x180006973  mov     eax, [rbx+4]
0x180006976  mov     [rsp+14F0h+var_14C4], eax
0x18000697a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000697f  mov     r12d, eax
0x180006982  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18000698a  mov     ecx, r13d
0x18000698d  lea     eax, [r13+8]
0x180006991  cmp     dword ptr [rbx+8], 1
0x180006995  cmovz   ecx, eax
0x180006998  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000699c  lea     ecx, [rax-7]
0x18000699f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800069a7  inc     ecx
0x1800069a9  mov     [rsp+14F0h+var_14C0], ecx
0x1800069ad  mov     rcx, [rbp+13F0h+arg_38]
0x1800069b4  test    rcx, rcx
0x1800069b7  jz      short loc_1800069C4
0x1800069b9  cmp     [rcx], r13w
0x1800069bd  mov     [rsp+14F0h+var_14B8], rcx
0x1800069c2  jnz     short loc_1800069C9
0x1800069c4  mov     [rsp+14F0h+var_14B8], r13
0x1800069c9  call    cs:__imp_GetCurrentThreadId
0x1800069cf  mov     [rsp+14F0h+var_14B0], eax
0x1800069d3  mov     [rsp+14F0h+var_1498], r14
0x1800069d8  mov     [rsp+14F0h+var_1490], esi
0x1800069dc  mov     [rsp+14F0h+var_148C], r12d
0x1800069e1  mov     [rsp+14F0h+var_14A8], r13
0x1800069e6  mov     [rsp+14F0h+var_14A0], r13
0x1800069eb  mov     [rbp+13F0h+var_1448], r15
0x1800069ef  mov     [rbp+13F0h+var_1440], rdi
0x1800069f3  mov     [rsp+14F0h+var_1488], r13
0x1800069f8  xorps   xmm0, xmm0
0x1800069fb  xor     eax, eax
0x1800069fd  movups  [rbp+13F0h+var_1468], xmm0
0x180006a01  mov     [rbp+13F0h+var_1458], rax
0x180006a05  xorps   xmm1, xmm1
0x180006a08  movups  [rsp+14F0h+var_1480], xmm1
0x180006a0d  mov     [rbp+13F0h+var_1470], rax
0x180006a11  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006a18  test    rax, rax
0x180006a1b  jz      short loc_180006A28
0x180006a1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a22  mov     [rbp+13F0h+var_1450], rax
0x180006a26  jmp     short loc_180006A2C
0x180006a28  mov     [rbp+13F0h+var_1450], r13
0x180006a2c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006a33  test    rax, rax
0x180006a36  jz      short loc_180006A42
0x180006a38  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a42  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006a49  test    rax, rax
0x180006a4c  jz      short loc_180006A62
0x180006a4e  mov     r8d, 400h
0x180006a54  lea     rdx, [rbp+13F0h+var_1430]
0x180006a58  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a62  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a69  test    rax, rax
0x180006a6c  jz      short loc_180006A78
0x180006a6e  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a78  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006a7f  test    rax, rax
0x180006a82  jz      short loc_180006A95
0x180006a84  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006a89  jnz     short loc_180006A95
0x180006a8b  lea     rcx, [rsp+14F0h+var_14D0]
0x180006a90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a95  cmp     [rsp+14F0h+var_14C8], r13d
0x180006a9a  jl      short loc_180006AAE
0x180006a9c  mov     ecx, 8000FFFFh; this
0x180006aa1  mov     [rsp+14F0h+var_14C8], ecx
0x180006aa5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006aaa  mov     [rsp+14F0h+var_14C4], eax
0x180006aae  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180006ab5  jnz     short loc_180006AD6
0x180006ab7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006abe  test    rax, rax
0x180006ac1  jz      short loc_180006ACC
0x180006ac3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac8  test    al, al
0x180006aca  jmp     short loc_180006AD4
0x180006acc  call    cs:__imp_IsDebuggerPresent
0x180006ad2  test    eax, eax
0x180006ad4  jz      short loc_180006ADD
0x180006ad6  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180006adb  jz      short loc_180006B03
0x180006add  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ae4  test    rax, rax
0x180006ae7  jz      short loc_180006B5C
0x180006ae9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006af0  jnz     short loc_180006B5C
0x180006af2  xor     r8d, r8d
0x180006af5  xor     edx, edx
0x180006af7  lea     rcx, [rsp+14F0h+var_14D0]
0x180006afc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b01  jmp     short loc_180006B5C
0x180006b03  mov     ebx, 800h
0x180006b08  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b0f  test    rax, rax
0x180006b12  jz      short loc_180006B31
0x180006b14  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180006b1b  jnz     short loc_180006B31
0x180006b1d  mov     r8d, ebx
0x180006b20  lea     rdx, [rbp+13F0h+OutputString]
0x180006b27  lea     rcx, [rsp+14F0h+var_14D0]
0x180006b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b31  cmp     [rbp+13F0h+OutputString], r13w
0x180006b39  jnz     short loc_180006B4F
0x180006b3b  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180006b40  mov     rdx, rbx; unsigned __int16 *
0x180006b43  lea     rcx, [rbp+13F0h+OutputString]; this
0x180006b4a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006b4f  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180006b56  call    cs:__imp_OutputDebugStringW
0x180006b5c  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180006b61  jnz     short loc_180006B6C
0x180006b63  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180006b6a  jz      short loc_180006B7E
0x180006b6c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006b73  test    rax, rax
0x180006b76  jz      short loc_180006B7E
0x180006b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b7d  nop
0x180006b7e  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180006b83  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
