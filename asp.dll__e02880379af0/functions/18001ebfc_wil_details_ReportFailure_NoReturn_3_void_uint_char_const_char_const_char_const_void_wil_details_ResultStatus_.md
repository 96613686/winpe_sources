# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18001ebfc`
- end: `0x18001ee5c`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `608`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x18001e9c8`

## callees

- `0x18001ebfc`
- `0x1800204e4`
- `0x180020d50`
- `0x180021cc0`
- `0x180023350`
- `0x180023d86`
- `0x180023e60`
- `0x180064010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18001ee2a`
- `KERNEL32!OutputDebugStringW` at `0x18001ee2a`
- `KERNEL32!IsDebuggerPresent` at `0x18001eda0`
- `KERNEL32!IsDebuggerPresent` at `0x18001eda0`
- `KERNEL32!GetCurrentThreadId` at `0x18001ec9d`
- `KERNEL32!GetCurrentThreadId` at `0x18001ec9d`

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
0x18001ebfc  mov     [rsp-8+arg_18], rbx
0x18001ec01  push    rbp
0x18001ec02  push    rsi
0x18001ec03  push    rdi
0x18001ec04  push    r12
0x18001ec06  push    r13
0x18001ec08  push    r14
0x18001ec0a  push    r15
0x18001ec0c  lea     rbp, [rsp-13C0h]
0x18001ec14  mov     eax, 14C0h
0x18001ec19  call    _alloca_probe
0x18001ec1e  sub     rsp, rax
0x18001ec21  mov     rsi, [rbp+13F0h+arg_28]
0x18001ec28  mov     r15, r8
0x18001ec2b  mov     r14d, edx
0x18001ec2e  mov     r12, rcx
0x18001ec31  xor     edx, edx; Val
0x18001ec33  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18001ec38  mov     r8d, 98h; Size
0x18001ec3e  call    memset_0
0x18001ec43  mov     rbx, [rbp+13F0h+arg_30]
0x18001ec4a  xor     r13d, r13d
0x18001ec4d  mov     [rbp+13F0h+OutputString], r13w
0x18001ec55  mov     [rbp+13F0h+var_1430], r13b
0x18001ec59  mov     ecx, [rbx]; this
0x18001ec5b  mov     eax, [rbx+4]
0x18001ec5e  mov     [rsp+14F0h+var_14C8], ecx
0x18001ec62  mov     [rsp+14F0h+var_14C4], eax
0x18001ec66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001ec6b  cmp     dword ptr [rbx+8], 1
0x18001ec6f  mov     edi, eax
0x18001ec71  lea     eax, [r13+8]
0x18001ec75  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x18001ec7d  mov     ecx, r13d
0x18001ec80  cmovz   ecx, eax
0x18001ec83  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18001ec87  lea     ecx, [rax-7]
0x18001ec8a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001ec92  inc     ecx
0x18001ec94  mov     [rsp+14F0h+var_14B8], r13
0x18001ec99  mov     [rsp+14F0h+var_14C0], ecx
0x18001ec9d  call    cs:__imp_GetCurrentThreadId
0x18001eca3  xorps   xmm0, xmm0
0x18001eca6  mov     [rsp+14F0h+var_1498], r15
0x18001ecab  mov     [rsp+14F0h+var_14B0], eax
0x18001ecaf  xorps   xmm1, xmm1
0x18001ecb2  xor     eax, eax
0x18001ecb4  mov     [rsp+14F0h+var_1490], r14d
0x18001ecb9  mov     [rbp+13F0h+var_1458], rax
0x18001ecbd  mov     [rbp+13F0h+var_1470], rax
0x18001ecc1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001ecc8  mov     [rsp+14F0h+var_148C], edi
0x18001eccc  mov     [rsp+14F0h+var_14A8], r13
0x18001ecd1  mov     [rsp+14F0h+var_14A0], r13
0x18001ecd6  mov     [rbp+13F0h+var_1448], rsi
0x18001ecda  mov     [rbp+13F0h+var_1440], r12
0x18001ecde  mov     [rsp+14F0h+var_1488], r13
0x18001ece3  movups  [rbp+13F0h+var_1468], xmm0
0x18001ece7  movups  [rsp+14F0h+var_1480], xmm1
0x18001ecec  test    rax, rax
0x18001ecef  jz      short loc_18001ECFC
0x18001ecf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecf6  mov     [rbp+13F0h+var_1450], rax
0x18001ecfa  jmp     short loc_18001ED00
0x18001ecfc  mov     [rbp+13F0h+var_1450], r13
0x18001ed00  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001ed07  test    rax, rax
0x18001ed0a  jz      short loc_18001ED16
0x18001ed0c  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ed11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed16  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ed1d  test    rax, rax
0x18001ed20  jz      short loc_18001ED36
0x18001ed22  mov     r8d, 400h
0x18001ed28  lea     rdx, [rbp+13F0h+var_1430]
0x18001ed2c  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ed31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed36  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ed3d  test    rax, rax
0x18001ed40  jz      short loc_18001ED4C
0x18001ed42  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ed47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed4c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ed53  test    rax, rax
0x18001ed56  jz      short loc_18001ED69
0x18001ed58  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001ed5d  jnz     short loc_18001ED69
0x18001ed5f  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ed64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed69  cmp     [rsp+14F0h+var_14C8], r13d
0x18001ed6e  jl      short loc_18001ED82
0x18001ed70  mov     ecx, 8000FFFFh; this
0x18001ed75  mov     [rsp+14F0h+var_14C8], ecx
0x18001ed79  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ed7e  mov     [rsp+14F0h+var_14C4], eax
0x18001ed82  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18001ed89  jnz     short loc_18001EDAA
0x18001ed8b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001ed92  test    rax, rax
0x18001ed95  jz      short loc_18001EDA0
0x18001ed97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed9c  test    al, al
0x18001ed9e  jmp     short loc_18001EDA8
0x18001eda0  call    cs:__imp_IsDebuggerPresent
0x18001eda6  test    eax, eax
0x18001eda8  jz      short loc_18001EDB1
0x18001edaa  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18001edaf  jz      short loc_18001EDD7
0x18001edb1  mov     rax, cs:g_pfnResultLoggingCallback
0x18001edb8  test    rax, rax
0x18001edbb  jz      short loc_18001EE30
0x18001edbd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001edc4  jnz     short loc_18001EE30
0x18001edc6  xor     r8d, r8d
0x18001edc9  lea     rcx, [rsp+14F0h+var_14D0]
0x18001edce  xor     edx, edx
0x18001edd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edd5  jmp     short loc_18001EE30
0x18001edd7  mov     rax, cs:g_pfnResultLoggingCallback
0x18001edde  mov     ebx, 800h
0x18001ede3  test    rax, rax
0x18001ede6  jz      short loc_18001EE05
0x18001ede8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18001edef  jnz     short loc_18001EE05
0x18001edf1  mov     r8d, ebx
0x18001edf4  lea     rdx, [rbp+13F0h+OutputString]
0x18001edfb  lea     rcx, [rsp+14F0h+var_14D0]
0x18001ee00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee05  cmp     [rbp+13F0h+OutputString], r13w
0x18001ee0d  jnz     short loc_18001EE23
0x18001ee0f  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18001ee14  mov     rdx, rbx; unsigned __int16 *
0x18001ee17  lea     rcx, [rbp+13F0h+OutputString]; this
0x18001ee1e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001ee23  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18001ee2a  call    cs:__imp_OutputDebugStringW
0x18001ee30  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18001ee35  jnz     short loc_18001EE40
0x18001ee37  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18001ee3e  jz      short loc_18001EE51
0x18001ee40  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001ee47  test    rax, rax
0x18001ee4a  jz      short loc_18001EE51
0x18001ee4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee51  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001ee56  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
