# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000e688`
- end: `0x18000e92e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000e128`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x18000e688`
- `0x18000f984`
- `0x1800108c0`
- `0x180011a10`
- `0x180011aec`
- `0x18004bab0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e74e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e74e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e8cd`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e8cd`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e843`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e843`

## pseudocode

```c
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
0x18000e688  push    rbp
0x18000e68a  push    rbx
0x18000e68b  push    rsi
0x18000e68c  push    rdi
0x18000e68d  push    r12
0x18000e68f  push    r14
0x18000e691  push    r15
0x18000e693  lea     rbp, [rsp-13D0h]
0x18000e69b  mov     eax, 14D0h
0x18000e6a0  call    _alloca_probe
0x18000e6a5  sub     rsp, rax
0x18000e6a8  mov     rax, cs:__security_cookie
0x18000e6af  xor     rax, rsp
0x18000e6b2  mov     [rbp+1400h+var_40], rax
0x18000e6b9  mov     rsi, r8
0x18000e6bc  mov     edi, edx
0x18000e6be  mov     rbx, rcx
0x18000e6c1  mov     r14, [rbp+1400h+arg_28]
0x18000e6c8  xor     edx, edx; Val
0x18000e6ca  mov     r8d, 98h; Size
0x18000e6d0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000e6d5  call    memset_0
0x18000e6da  nop
0x18000e6db  xor     r12d, r12d
0x18000e6de  mov     [rbp+1400h+OutputString], r12w
0x18000e6e6  mov     [rbp+1400h+var_1440], r12b
0x18000e6ea  mov     rdx, [rbp+1400h+arg_30]; int
0x18000e6f1  mov     ecx, [rdx]; this
0x18000e6f3  mov     [rsp+1500h+var_14D8], ecx
0x18000e6f7  mov     eax, [rdx+4]
0x18000e6fa  mov     [rsp+1500h+var_14D4], eax
0x18000e6fe  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e703  mov     r15d, eax
0x18000e706  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000e70e  mov     ecx, r12d
0x18000e711  lea     eax, [r12+8]
0x18000e716  cmp     dword ptr [rdx+8], 1
0x18000e71a  cmovz   ecx, eax
0x18000e71d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000e721  lea     ecx, [rax-7]
0x18000e724  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e72c  inc     ecx
0x18000e72e  mov     [rsp+1500h+var_14D0], ecx
0x18000e732  mov     rcx, [rbp+1400h+arg_38]
0x18000e739  test    rcx, rcx
0x18000e73c  jz      short loc_18000E749
0x18000e73e  cmp     [rcx], r12w
0x18000e742  mov     [rsp+1500h+var_14C8], rcx
0x18000e747  jnz     short loc_18000E74E
0x18000e749  mov     [rsp+1500h+var_14C8], r12
0x18000e74e  call    cs:__imp_GetCurrentThreadId
0x18000e754  mov     [rsp+1500h+var_14C0], eax
0x18000e758  mov     [rsp+1500h+var_14A8], rsi
0x18000e75d  mov     [rsp+1500h+var_14A0], edi
0x18000e761  mov     [rsp+1500h+var_149C], r15d
0x18000e766  mov     [rsp+1500h+var_14B8], r12
0x18000e76b  mov     [rsp+1500h+var_14B0], r12
0x18000e770  mov     [rbp+1400h+var_1458], r14
0x18000e774  mov     [rbp+1400h+var_1450], rbx
0x18000e778  mov     [rsp+1500h+var_1498], r12
0x18000e77d  xorps   xmm0, xmm0
0x18000e780  xor     eax, eax
0x18000e782  movups  [rbp+1400h+var_1478], xmm0
0x18000e786  mov     [rbp+1400h+var_1468], rax
0x18000e78a  xorps   xmm1, xmm1
0x18000e78d  movups  [rsp+1500h+var_1490], xmm1
0x18000e792  mov     [rbp+1400h+var_1480], rax
0x18000e796  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e79d  test    rax, rax
0x18000e7a0  jz      short loc_18000E7AD
0x18000e7a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7a7  mov     [rbp+1400h+var_1460], rax
0x18000e7ab  jmp     short loc_18000E7B1
0x18000e7ad  mov     [rbp+1400h+var_1460], r12
0x18000e7b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e7b8  test    rax, rax
0x18000e7bb  jz      short loc_18000E7C7
0x18000e7bd  lea     rcx, [rsp+1500h+var_14E0]
0x18000e7c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7c7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e7ce  test    rax, rax
0x18000e7d1  jz      short loc_18000E7E7
0x18000e7d3  mov     r8d, 400h
0x18000e7d9  lea     rdx, [rbp+1400h+var_1440]
0x18000e7dd  lea     rcx, [rsp+1500h+var_14E0]
0x18000e7e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e7ee  test    rax, rax
0x18000e7f1  jz      short loc_18000E7FD
0x18000e7f3  lea     rcx, [rsp+1500h+var_14E0]
0x18000e7f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e7fd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e804  test    rax, rax
0x18000e807  jz      short loc_18000E81A
0x18000e809  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e80e  jnz     short loc_18000E81A
0x18000e810  lea     rcx, [rsp+1500h+var_14E0]
0x18000e815  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e81a  cmp     [rsp+1500h+var_14D8], r12d
0x18000e81f  jge     loc_18000E928
0x18000e825  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000e82c  jnz     short loc_18000E84D
0x18000e82e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e835  test    rax, rax
0x18000e838  jz      short loc_18000E843
0x18000e83a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e83f  test    al, al
0x18000e841  jmp     short loc_18000E84B
0x18000e843  call    cs:__imp_IsDebuggerPresent
0x18000e849  test    eax, eax
0x18000e84b  jz      short loc_18000E854
0x18000e84d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e852  jz      short loc_18000E87A
0x18000e854  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e85b  test    rax, rax
0x18000e85e  jz      short loc_18000E8D3
0x18000e860  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e867  jnz     short loc_18000E8D3
0x18000e869  xor     r8d, r8d
0x18000e86c  xor     edx, edx
0x18000e86e  lea     rcx, [rsp+1500h+var_14E0]
0x18000e873  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e878  jmp     short loc_18000E8D3
0x18000e87a  mov     ebx, 800h
0x18000e87f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e886  test    rax, rax
0x18000e889  jz      short loc_18000E8A8
0x18000e88b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e892  jnz     short loc_18000E8A8
0x18000e894  mov     r8d, ebx
0x18000e897  lea     rdx, [rbp+1400h+OutputString]
0x18000e89e  lea     rcx, [rsp+1500h+var_14E0]
0x18000e8a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8a8  cmp     [rbp+1400h+OutputString], r12w
0x18000e8b0  jnz     short loc_18000E8C6
0x18000e8b2  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000e8b7  mov     rdx, rbx; unsigned __int16 *
0x18000e8ba  lea     rcx, [rbp+1400h+OutputString]; this
0x18000e8c1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e8c6  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000e8cd  call    cs:__imp_OutputDebugStringW
0x18000e8d3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000e8d8  jnz     short loc_18000E8E3
0x18000e8da  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000e8e1  jz      short loc_18000E8F5
0x18000e8e3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e8ea  test    rax, rax
0x18000e8ed  jz      short loc_18000E8F5
0x18000e8ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e8f4  nop
0x18000e8f5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000e8fa  jnz     short loc_18000E91D
0x18000e8fc  mov     rcx, [rbp+1400h+var_40]
0x18000e903  xor     rcx, rsp; StackCookie
0x18000e906  call    __security_check_cookie
0x18000e90b  add     rsp, 14D0h
0x18000e912  pop     r15
0x18000e914  pop     r14
0x18000e916  pop     r12
0x18000e918  pop     rdi
0x18000e919  pop     rsi
0x18000e91a  pop     rbx
0x18000e91b  pop     rbp
0x18000e91c  retn
0x18000e91d  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000e922  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e928  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
