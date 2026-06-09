# wil::details::ReportFailure_NoReturn<3>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x180004a58`
- end: `0x180004cd1`
- name: `??$ReportFailure_NoReturn@$02@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `633`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `8`
- tags: ``

## callers

- `0x1800046c8`

## callees

- `0x180002dc4`
- `0x180003324`
- `0x18000370c`
- `0x180003ab0`
- `0x180004a58`
- `0x180007170`
- `0x1800173e0`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004b11`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004c14`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004c14`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004c9e`

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
0x180004a58  mov     [rsp-8+arg_18], rbx
0x180004a5d  push    rbp
0x180004a5e  push    rsi
0x180004a5f  push    rdi
0x180004a60  push    r12
0x180004a62  push    r13
0x180004a64  push    r14
0x180004a66  push    r15
0x180004a68  lea     rbp, [rsp-13C0h]
0x180004a70  mov     eax, 14C0h
0x180004a75  call    _alloca_probe
0x180004a7a  sub     rsp, rax
0x180004a7d  mov     r14, r8
0x180004a80  mov     esi, edx
0x180004a82  mov     rdi, rcx
0x180004a85  mov     r15, [rbp+13F0h+arg_28]
0x180004a8c  xor     edx, edx; Val
0x180004a8e  mov     r8d, 98h; Size
0x180004a94  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180004a99  call    memset_0
0x180004a9e  nop
0x180004a9f  xor     r13d, r13d
0x180004aa2  mov     [rbp+13F0h+OutputString], r13w
0x180004aaa  mov     [rbp+13F0h+var_1430], r13b
0x180004aae  mov     rbx, [rbp+13F0h+arg_30]
0x180004ab5  mov     ecx, [rbx]; this
0x180004ab7  mov     [rsp+14F0h+var_14C8], ecx
0x180004abb  mov     eax, [rbx+4]
0x180004abe  mov     [rsp+14F0h+var_14C4], eax
0x180004ac2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004ac7  mov     r12d, eax
0x180004aca  mov     dword ptr [rsp+14F0h+var_14D0], 3
0x180004ad2  mov     ecx, r13d
0x180004ad5  lea     eax, [r13+8]
0x180004ad9  cmp     dword ptr [rbx+8], 1
0x180004add  cmovz   ecx, eax
0x180004ae0  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180004ae4  lea     ecx, [rax-7]
0x180004ae7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004aef  inc     ecx
0x180004af1  mov     [rsp+14F0h+var_14C0], ecx
0x180004af5  mov     rcx, [rbp+13F0h+arg_38]
0x180004afc  test    rcx, rcx
0x180004aff  jz      short loc_180004B0C
0x180004b01  cmp     [rcx], r13w
0x180004b05  mov     [rsp+14F0h+var_14B8], rcx
0x180004b0a  jnz     short loc_180004B11
0x180004b0c  mov     [rsp+14F0h+var_14B8], r13
0x180004b11  call    cs:__imp_GetCurrentThreadId
0x180004b17  mov     [rsp+14F0h+var_14B0], eax
0x180004b1b  mov     [rsp+14F0h+var_1498], r14
0x180004b20  mov     [rsp+14F0h+var_1490], esi
0x180004b24  mov     [rsp+14F0h+var_148C], r12d
0x180004b29  mov     [rsp+14F0h+var_14A8], r13
0x180004b2e  mov     [rsp+14F0h+var_14A0], r13
0x180004b33  mov     [rbp+13F0h+var_1448], r15
0x180004b37  mov     [rbp+13F0h+var_1440], rdi
0x180004b3b  mov     [rsp+14F0h+var_1488], r13
0x180004b40  xorps   xmm0, xmm0
0x180004b43  xor     eax, eax
0x180004b45  movups  [rbp+13F0h+var_1468], xmm0
0x180004b49  mov     [rbp+13F0h+var_1458], rax
0x180004b4d  xorps   xmm1, xmm1
0x180004b50  movups  [rsp+14F0h+var_1480], xmm1
0x180004b55  mov     [rbp+13F0h+var_1470], rax
0x180004b59  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004b60  test    rax, rax
0x180004b63  jz      short loc_180004B70
0x180004b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b6a  mov     [rbp+13F0h+var_1450], rax
0x180004b6e  jmp     short loc_180004B74
0x180004b70  mov     [rbp+13F0h+var_1450], r13
0x180004b74  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004b7b  test    rax, rax
0x180004b7e  jz      short loc_180004B8A
0x180004b80  lea     rcx, [rsp+14F0h+var_14D0]
0x180004b85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004b8a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004b91  test    rax, rax
0x180004b94  jz      short loc_180004BAA
0x180004b96  mov     r8d, 400h
0x180004b9c  lea     rdx, [rbp+13F0h+var_1430]
0x180004ba0  lea     rcx, [rsp+14F0h+var_14D0]
0x180004ba5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004baa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004bb1  test    rax, rax
0x180004bb4  jz      short loc_180004BC0
0x180004bb6  lea     rcx, [rsp+14F0h+var_14D0]
0x180004bbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bc0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004bc7  test    rax, rax
0x180004bca  jz      short loc_180004BDD
0x180004bcc  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004bd1  jnz     short loc_180004BDD
0x180004bd3  lea     rcx, [rsp+14F0h+var_14D0]
0x180004bd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004bdd  cmp     [rsp+14F0h+var_14C8], r13d
0x180004be2  jl      short loc_180004BF6
0x180004be4  mov     ecx, 8000FFFFh; this
0x180004be9  mov     [rsp+14F0h+var_14C8], ecx
0x180004bed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004bf2  mov     [rsp+14F0h+var_14C4], eax
0x180004bf6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x180004bfd  jnz     short loc_180004C1E
0x180004bff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004c06  test    rax, rax
0x180004c09  jz      short loc_180004C14
0x180004c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c10  test    al, al
0x180004c12  jmp     short loc_180004C1C
0x180004c14  call    cs:__imp_IsDebuggerPresent
0x180004c1a  test    eax, eax
0x180004c1c  jz      short loc_180004C25
0x180004c1e  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180004c23  jz      short loc_180004C4B
0x180004c25  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c2c  test    rax, rax
0x180004c2f  jz      short loc_180004CA4
0x180004c31  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004c38  jnz     short loc_180004CA4
0x180004c3a  xor     r8d, r8d
0x180004c3d  xor     edx, edx
0x180004c3f  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c49  jmp     short loc_180004CA4
0x180004c4b  mov     ebx, 800h
0x180004c50  mov     rax, cs:g_pfnResultLoggingCallback
0x180004c57  test    rax, rax
0x180004c5a  jz      short loc_180004C79
0x180004c5c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x180004c63  jnz     short loc_180004C79
0x180004c65  mov     r8d, ebx
0x180004c68  lea     rdx, [rbp+13F0h+OutputString]
0x180004c6f  lea     rcx, [rsp+14F0h+var_14D0]
0x180004c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004c79  cmp     [rbp+13F0h+OutputString], r13w
0x180004c81  jnz     short loc_180004C97
0x180004c83  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180004c88  mov     rdx, rbx; unsigned __int16 *
0x180004c8b  lea     rcx, [rbp+13F0h+OutputString]; this
0x180004c92  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004c97  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180004c9e  call    cs:__imp_OutputDebugStringW
0x180004ca4  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180004ca9  jnz     short loc_180004CB4
0x180004cab  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x180004cb2  jz      short loc_180004CC6
0x180004cb4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004cbb  test    rax, rax
0x180004cbe  jz      short loc_180004CC6
0x180004cc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004cc5  nop
0x180004cc6  lea     rcx, [rsp+14F0h+var_14D0]; this
0x180004ccb  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
