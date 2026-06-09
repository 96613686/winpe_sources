# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180010d84`
- end: `0x18001101a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001088c`

## callees

- `0x180010d84`
- `0x180012644`
- `0x180013fc0`
- `0x180016040`
- `0x1800163fc`
- `0x180020c02`
- `0x180020c30`
- `0x180020cf0`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010e2f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010e2f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010f2a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010f2a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010fb4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010fb4`

## pseudocode

```c
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180010d84  mov     [rsp-8+arg_10], rbx
0x180010d89  push    rbp
0x180010d8a  push    rsi
0x180010d8b  push    rdi
0x180010d8c  push    r14
0x180010d8e  push    r15
0x180010d90  lea     rbp, [rsp-13D0h]
0x180010d98  mov     eax, 14D0h
0x180010d9d  call    _alloca_probe
0x180010da2  sub     rsp, rax
0x180010da5  mov     rax, cs:__security_cookie
0x180010dac  xor     rax, rsp
0x180010daf  mov     [rbp+13F0h+var_30], rax
0x180010db6  mov     esi, edx
0x180010db8  mov     r14, rcx
0x180010dbb  mov     rdi, [rbp+13F0h+arg_28]
0x180010dc2  xor     edx, edx; Val
0x180010dc4  mov     r8d, 98h; Size
0x180010dca  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180010dcf  call    memset_0
0x180010dd4  nop
0x180010dd5  xor     r15d, r15d
0x180010dd8  mov     [rbp+13F0h+OutputString], r15w
0x180010de0  mov     [rbp+13F0h+var_1430], r15b
0x180010de4  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x180010deb  mov     ecx, [rdx]; this
0x180010ded  mov     [rsp+14F0h+var_14C8], ecx
0x180010df1  mov     eax, [rdx+4]
0x180010df4  mov     [rsp+14F0h+var_14C4], eax
0x180010df8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180010dfd  mov     ebx, eax
0x180010dff  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x180010e07  mov     ecx, r15d
0x180010e0a  lea     eax, [r15+8]
0x180010e0e  cmp     dword ptr [rdx+8], 1
0x180010e12  cmovz   ecx, eax
0x180010e15  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x180010e19  lea     ecx, [rax-7]
0x180010e1c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180010e24  inc     ecx
0x180010e26  mov     [rsp+14F0h+var_14C0], ecx
0x180010e2a  mov     [rsp+14F0h+var_14B8], r15
0x180010e2f  call    cs:__imp_GetCurrentThreadId
0x180010e35  mov     [rsp+14F0h+var_14B0], eax
0x180010e39  lea     rax, aWil; "wil"
0x180010e40  mov     [rsp+14F0h+var_1498], rax
0x180010e45  mov     [rsp+14F0h+var_1490], esi
0x180010e49  mov     [rsp+14F0h+var_148C], ebx
0x180010e4d  mov     [rsp+14F0h+var_14A8], r15
0x180010e52  mov     [rsp+14F0h+var_14A0], r15
0x180010e57  mov     [rbp+13F0h+var_1448], rdi
0x180010e5b  mov     [rbp+13F0h+var_1440], r14
0x180010e5f  mov     [rsp+14F0h+var_1488], r15
0x180010e64  xorps   xmm0, xmm0
0x180010e67  xor     eax, eax
0x180010e69  movups  [rbp+13F0h+var_1468], xmm0
0x180010e6d  mov     [rbp+13F0h+var_1458], rax
0x180010e71  xorps   xmm1, xmm1
0x180010e74  movups  [rsp+14F0h+var_1480], xmm1
0x180010e79  mov     [rbp+13F0h+var_1470], rax
0x180010e7d  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010e84  test    rax, rax
0x180010e87  jz      short loc_180010E94
0x180010e89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e8e  mov     [rbp+13F0h+var_1450], rax
0x180010e92  jmp     short loc_180010E98
0x180010e94  mov     [rbp+13F0h+var_1450], r15
0x180010e98  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010e9f  test    rax, rax
0x180010ea2  jz      short loc_180010EAE
0x180010ea4  lea     rcx, [rsp+14F0h+var_14D0]
0x180010ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010eae  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010eb5  test    rax, rax
0x180010eb8  jz      short loc_180010ECE
0x180010eba  mov     r8d, 400h
0x180010ec0  lea     rdx, [rbp+13F0h+var_1430]
0x180010ec4  lea     rcx, [rsp+14F0h+var_14D0]
0x180010ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ece  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010ed5  test    rax, rax
0x180010ed8  jz      short loc_180010EE4
0x180010eda  lea     rcx, [rsp+14F0h+var_14D0]
0x180010edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010ee4  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010eeb  test    rax, rax
0x180010eee  jz      short loc_180010F01
0x180010ef0  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010ef5  jnz     short loc_180010F01
0x180010ef7  lea     rcx, [rsp+14F0h+var_14D0]
0x180010efc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f01  cmp     [rsp+14F0h+var_14C8], r15d
0x180010f06  jge     loc_180011014
0x180010f0c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x180010f13  jnz     short loc_180010F34
0x180010f15  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010f1c  test    rax, rax
0x180010f1f  jz      short loc_180010F2A
0x180010f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f26  test    al, al
0x180010f28  jmp     short loc_180010F32
0x180010f2a  call    cs:__imp_IsDebuggerPresent
0x180010f30  test    eax, eax
0x180010f32  jz      short loc_180010F3B
0x180010f34  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x180010f39  jz      short loc_180010F61
0x180010f3b  mov     rax, cs:g_pfnResultLoggingCallback
0x180010f42  test    rax, rax
0x180010f45  jz      short loc_180010FBA
0x180010f47  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010f4e  jnz     short loc_180010FBA
0x180010f50  xor     r8d, r8d
0x180010f53  xor     edx, edx
0x180010f55  lea     rcx, [rsp+14F0h+var_14D0]
0x180010f5a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f5f  jmp     short loc_180010FBA
0x180010f61  mov     ebx, 800h
0x180010f66  mov     rax, cs:g_pfnResultLoggingCallback
0x180010f6d  test    rax, rax
0x180010f70  jz      short loc_180010F8F
0x180010f72  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180010f79  jnz     short loc_180010F8F
0x180010f7b  mov     r8d, ebx
0x180010f7e  lea     rdx, [rbp+13F0h+OutputString]
0x180010f85  lea     rcx, [rsp+14F0h+var_14D0]
0x180010f8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010f8f  cmp     [rbp+13F0h+OutputString], r15w
0x180010f97  jnz     short loc_180010FAD
0x180010f99  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180010f9e  mov     rdx, rbx; unsigned __int16 *
0x180010fa1  lea     rcx, [rbp+13F0h+OutputString]; this
0x180010fa8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010fad  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180010fb4  call    cs:__imp_OutputDebugStringW
0x180010fba  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180010fbf  jnz     short loc_180010FCA
0x180010fc1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x180010fc8  jz      short loc_180010FDC
0x180010fca  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010fd1  test    rax, rax
0x180010fd4  jz      short loc_180010FDC
0x180010fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010fdb  nop
0x180010fdc  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x180010fe1  jnz     short loc_180011009
0x180010fe3  mov     rcx, [rbp+13F0h+var_30]
0x180010fea  xor     rcx, rsp; StackCookie
0x180010fed  call    __security_check_cookie
0x180010ff2  mov     rbx, [rsp+14F0h+arg_10]
0x180010ffa  add     rsp, 14D0h
0x180011001  pop     r15
0x180011003  pop     r14
0x180011005  pop     rdi
0x180011006  pop     rsi
0x180011007  pop     rbp
0x180011008  retn
0x180011009  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18001100e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180011014  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
