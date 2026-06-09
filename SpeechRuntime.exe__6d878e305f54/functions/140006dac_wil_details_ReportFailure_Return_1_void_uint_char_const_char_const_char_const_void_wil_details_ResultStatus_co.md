# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140006dac`
- end: `0x140007052`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140006a30`

## callees

- `0x140002d30`
- `0x140003848`
- `0x140006dac`
- `0x14000b6f4`
- `0x14000d6b0`
- `0x140010cd8`
- `0x140010e94`
- `0x14002f370`
- `0x140031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e72`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006e72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006f67`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006f67`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006ff1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006ff1`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
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
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x140006dac  push    rbp
0x140006dae  push    rbx
0x140006daf  push    rsi
0x140006db0  push    rdi
0x140006db1  push    r12
0x140006db3  push    r14
0x140006db5  push    r15
0x140006db7  lea     rbp, [rsp-13D0h]
0x140006dbf  mov     eax, 14D0h
0x140006dc4  call    _alloca_probe
0x140006dc9  sub     rsp, rax
0x140006dcc  mov     rax, cs:__security_cookie
0x140006dd3  xor     rax, rsp
0x140006dd6  mov     [rbp+1400h+var_40], rax
0x140006ddd  mov     rsi, r8
0x140006de0  mov     edi, edx
0x140006de2  mov     rbx, rcx
0x140006de5  mov     r14, [rbp+1400h+arg_28]
0x140006dec  xor     edx, edx; Val
0x140006dee  mov     r8d, 98h; Size
0x140006df4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140006df9  call    memset_0
0x140006dfe  nop
0x140006dff  xor     r12d, r12d
0x140006e02  mov     [rbp+1400h+OutputString], r12w
0x140006e0a  mov     [rbp+1400h+var_1440], r12b
0x140006e0e  mov     rdx, [rbp+1400h+arg_30]; int
0x140006e15  mov     ecx, [rdx]; this
0x140006e17  mov     [rsp+1500h+var_14D8], ecx
0x140006e1b  mov     eax, [rdx+4]
0x140006e1e  mov     [rsp+1500h+var_14D4], eax
0x140006e22  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006e27  mov     r15d, eax
0x140006e2a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140006e32  mov     ecx, r12d
0x140006e35  lea     eax, [r12+8]
0x140006e3a  cmp     dword ptr [rdx+8], 1
0x140006e3e  cmovz   ecx, eax
0x140006e41  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140006e45  lea     ecx, [rax-7]
0x140006e48  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006e50  inc     ecx
0x140006e52  mov     [rsp+1500h+var_14D0], ecx
0x140006e56  mov     rcx, [rbp+1400h+arg_38]
0x140006e5d  test    rcx, rcx
0x140006e60  jz      short loc_140006E6D
0x140006e62  cmp     [rcx], r12w
0x140006e66  mov     [rsp+1500h+var_14C8], rcx
0x140006e6b  jnz     short loc_140006E72
0x140006e6d  mov     [rsp+1500h+var_14C8], r12
0x140006e72  call    cs:__imp_GetCurrentThreadId
0x140006e78  mov     [rsp+1500h+var_14C0], eax
0x140006e7c  mov     [rsp+1500h+var_14A8], rsi
0x140006e81  mov     [rsp+1500h+var_14A0], edi
0x140006e85  mov     [rsp+1500h+var_149C], r15d
0x140006e8a  mov     [rsp+1500h+var_14B8], r12
0x140006e8f  mov     [rsp+1500h+var_14B0], r12
0x140006e94  mov     [rbp+1400h+var_1458], r14
0x140006e98  mov     [rbp+1400h+var_1450], rbx
0x140006e9c  mov     [rsp+1500h+var_1498], r12
0x140006ea1  xorps   xmm0, xmm0
0x140006ea4  xor     eax, eax
0x140006ea6  movups  [rbp+1400h+var_1478], xmm0
0x140006eaa  mov     [rbp+1400h+var_1468], rax
0x140006eae  xorps   xmm1, xmm1
0x140006eb1  movups  [rsp+1500h+var_1490], xmm1
0x140006eb6  mov     [rbp+1400h+var_1480], rax
0x140006eba  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006ec1  test    rax, rax
0x140006ec4  jz      short loc_140006ED1
0x140006ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ecb  mov     [rbp+1400h+var_1460], rax
0x140006ecf  jmp     short loc_140006ED5
0x140006ed1  mov     [rbp+1400h+var_1460], r12
0x140006ed5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006edc  test    rax, rax
0x140006edf  jz      short loc_140006EEB
0x140006ee1  lea     rcx, [rsp+1500h+var_14E0]
0x140006ee6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006eeb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006ef2  test    rax, rax
0x140006ef5  jz      short loc_140006F0B
0x140006ef7  mov     r8d, 400h
0x140006efd  lea     rdx, [rbp+1400h+var_1440]
0x140006f01  lea     rcx, [rsp+1500h+var_14E0]
0x140006f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f0b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006f12  test    rax, rax
0x140006f15  jz      short loc_140006F21
0x140006f17  lea     rcx, [rsp+1500h+var_14E0]
0x140006f1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f21  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006f28  test    rax, rax
0x140006f2b  jz      short loc_140006F3E
0x140006f2d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006f32  jnz     short loc_140006F3E
0x140006f34  lea     rcx, [rsp+1500h+var_14E0]
0x140006f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f3e  cmp     [rsp+1500h+var_14D8], r12d
0x140006f43  jge     loc_14000704C
0x140006f49  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x140006f50  jnz     short loc_140006F71
0x140006f52  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006f59  test    rax, rax
0x140006f5c  jz      short loc_140006F67
0x140006f5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f63  test    al, al
0x140006f65  jmp     short loc_140006F6F
0x140006f67  call    cs:__imp_IsDebuggerPresent
0x140006f6d  test    eax, eax
0x140006f6f  jz      short loc_140006F78
0x140006f71  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140006f76  jz      short loc_140006F9E
0x140006f78  mov     rax, cs:g_pfnResultLoggingCallback
0x140006f7f  test    rax, rax
0x140006f82  jz      short loc_140006FF7
0x140006f84  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006f8b  jnz     short loc_140006FF7
0x140006f8d  xor     r8d, r8d
0x140006f90  xor     edx, edx
0x140006f92  lea     rcx, [rsp+1500h+var_14E0]
0x140006f97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f9c  jmp     short loc_140006FF7
0x140006f9e  mov     ebx, 800h
0x140006fa3  mov     rax, cs:g_pfnResultLoggingCallback
0x140006faa  test    rax, rax
0x140006fad  jz      short loc_140006FCC
0x140006faf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140006fb6  jnz     short loc_140006FCC
0x140006fb8  mov     r8d, ebx
0x140006fbb  lea     rdx, [rbp+1400h+OutputString]
0x140006fc2  lea     rcx, [rsp+1500h+var_14E0]
0x140006fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fcc  cmp     [rbp+1400h+OutputString], r12w
0x140006fd4  jnz     short loc_140006FEA
0x140006fd6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140006fdb  mov     rdx, rbx; unsigned __int16 *
0x140006fde  lea     rcx, [rbp+1400h+OutputString]; this
0x140006fe5  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006fea  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140006ff1  call    cs:__imp_OutputDebugStringW
0x140006ff7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140006ffc  jnz     short loc_140007007
0x140006ffe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140007005  jz      short loc_140007019
0x140007007  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000700e  test    rax, rax
0x140007011  jz      short loc_140007019
0x140007013  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007018  nop
0x140007019  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000701e  jnz     short loc_140007041
0x140007020  mov     rcx, [rbp+1400h+var_40]
0x140007027  xor     rcx, rsp; StackCookie
0x14000702a  call    __security_check_cookie
0x14000702f  add     rsp, 14D0h
0x140007036  pop     r15
0x140007038  pop     r14
0x14000703a  pop     r12
0x14000703c  pop     rdi
0x14000703d  pop     rsi
0x14000703e  pop     rbx
0x14000703f  pop     rbp
0x140007040  retn
0x140007041  lea     rcx, [rsp+1500h+var_14E0]; this
0x140007046  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000704c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
