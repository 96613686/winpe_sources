# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000c258`
- end: `0x18000c4fe`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000975c`

## callees

- `0x180007160`
- `0x180007b54`
- `0x180009f30`
- `0x18000a8fc`
- `0x18000c258`
- `0x18000d204`
- `0x18000f178`
- `0x1800361f0`
- `0x180038010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c31e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c31e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c413`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c413`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c49d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c49d`

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
0x18000c258  push    rbp
0x18000c25a  push    rbx
0x18000c25b  push    rsi
0x18000c25c  push    rdi
0x18000c25d  push    r12
0x18000c25f  push    r14
0x18000c261  push    r15
0x18000c263  lea     rbp, [rsp-13D0h]
0x18000c26b  mov     eax, 14D0h
0x18000c270  call    _alloca_probe
0x18000c275  sub     rsp, rax
0x18000c278  mov     rax, cs:__security_cookie
0x18000c27f  xor     rax, rsp
0x18000c282  mov     [rbp+1400h+var_40], rax
0x18000c289  mov     rsi, r8
0x18000c28c  mov     edi, edx
0x18000c28e  mov     rbx, rcx
0x18000c291  mov     r14, [rbp+1400h+arg_28]
0x18000c298  xor     edx, edx; Val
0x18000c29a  mov     r8d, 98h; Size
0x18000c2a0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000c2a5  call    memset_0
0x18000c2aa  nop
0x18000c2ab  xor     r12d, r12d
0x18000c2ae  mov     [rbp+1400h+OutputString], r12w
0x18000c2b6  mov     [rbp+1400h+var_1440], r12b
0x18000c2ba  mov     rdx, [rbp+1400h+arg_30]; int
0x18000c2c1  mov     ecx, [rdx]; this
0x18000c2c3  mov     [rsp+1500h+var_14D8], ecx
0x18000c2c7  mov     eax, [rdx+4]
0x18000c2ca  mov     [rsp+1500h+var_14D4], eax
0x18000c2ce  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c2d3  mov     r15d, eax
0x18000c2d6  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000c2de  mov     ecx, r12d
0x18000c2e1  lea     eax, [r12+8]
0x18000c2e6  cmp     dword ptr [rdx+8], 1
0x18000c2ea  cmovz   ecx, eax
0x18000c2ed  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000c2f1  lea     ecx, [rax-7]
0x18000c2f4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c2fc  inc     ecx
0x18000c2fe  mov     [rsp+1500h+var_14D0], ecx
0x18000c302  mov     rcx, [rbp+1400h+arg_38]
0x18000c309  test    rcx, rcx
0x18000c30c  jz      short loc_18000C319
0x18000c30e  cmp     [rcx], r12w
0x18000c312  mov     [rsp+1500h+var_14C8], rcx
0x18000c317  jnz     short loc_18000C31E
0x18000c319  mov     [rsp+1500h+var_14C8], r12
0x18000c31e  call    cs:__imp_GetCurrentThreadId
0x18000c324  mov     [rsp+1500h+var_14C0], eax
0x18000c328  mov     [rsp+1500h+var_14A8], rsi
0x18000c32d  mov     [rsp+1500h+var_14A0], edi
0x18000c331  mov     [rsp+1500h+var_149C], r15d
0x18000c336  mov     [rsp+1500h+var_14B8], r12
0x18000c33b  mov     [rsp+1500h+var_14B0], r12
0x18000c340  mov     [rbp+1400h+var_1458], r14
0x18000c344  mov     [rbp+1400h+var_1450], rbx
0x18000c348  mov     [rsp+1500h+var_1498], r12
0x18000c34d  xorps   xmm0, xmm0
0x18000c350  xor     eax, eax
0x18000c352  movups  [rbp+1400h+var_1478], xmm0
0x18000c356  mov     [rbp+1400h+var_1468], rax
0x18000c35a  xorps   xmm1, xmm1
0x18000c35d  movups  [rsp+1500h+var_1490], xmm1
0x18000c362  mov     [rbp+1400h+var_1480], rax
0x18000c366  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c36d  test    rax, rax
0x18000c370  jz      short loc_18000C37D
0x18000c372  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c377  mov     [rbp+1400h+var_1460], rax
0x18000c37b  jmp     short loc_18000C381
0x18000c37d  mov     [rbp+1400h+var_1460], r12
0x18000c381  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c388  test    rax, rax
0x18000c38b  jz      short loc_18000C397
0x18000c38d  lea     rcx, [rsp+1500h+var_14E0]
0x18000c392  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c397  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c39e  test    rax, rax
0x18000c3a1  jz      short loc_18000C3B7
0x18000c3a3  mov     r8d, 400h
0x18000c3a9  lea     rdx, [rbp+1400h+var_1440]
0x18000c3ad  lea     rcx, [rsp+1500h+var_14E0]
0x18000c3b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c3be  test    rax, rax
0x18000c3c1  jz      short loc_18000C3CD
0x18000c3c3  lea     rcx, [rsp+1500h+var_14E0]
0x18000c3c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3cd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c3d4  test    rax, rax
0x18000c3d7  jz      short loc_18000C3EA
0x18000c3d9  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000c3de  jnz     short loc_18000C3EA
0x18000c3e0  lea     rcx, [rsp+1500h+var_14E0]
0x18000c3e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3ea  cmp     [rsp+1500h+var_14D8], r12d
0x18000c3ef  jge     loc_18000C4F8
0x18000c3f5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000c3fc  jnz     short loc_18000C41D
0x18000c3fe  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c405  test    rax, rax
0x18000c408  jz      short loc_18000C413
0x18000c40a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c40f  test    al, al
0x18000c411  jmp     short loc_18000C41B
0x18000c413  call    cs:__imp_IsDebuggerPresent
0x18000c419  test    eax, eax
0x18000c41b  jz      short loc_18000C424
0x18000c41d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000c422  jz      short loc_18000C44A
0x18000c424  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c42b  test    rax, rax
0x18000c42e  jz      short loc_18000C4A3
0x18000c430  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c437  jnz     short loc_18000C4A3
0x18000c439  xor     r8d, r8d
0x18000c43c  xor     edx, edx
0x18000c43e  lea     rcx, [rsp+1500h+var_14E0]
0x18000c443  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c448  jmp     short loc_18000C4A3
0x18000c44a  mov     ebx, 800h
0x18000c44f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c456  test    rax, rax
0x18000c459  jz      short loc_18000C478
0x18000c45b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000c462  jnz     short loc_18000C478
0x18000c464  mov     r8d, ebx
0x18000c467  lea     rdx, [rbp+1400h+OutputString]
0x18000c46e  lea     rcx, [rsp+1500h+var_14E0]
0x18000c473  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c478  cmp     [rbp+1400h+OutputString], r12w
0x18000c480  jnz     short loc_18000C496
0x18000c482  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000c487  mov     rdx, rbx; unsigned __int16 *
0x18000c48a  lea     rcx, [rbp+1400h+OutputString]; this
0x18000c491  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c496  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000c49d  call    cs:__imp_OutputDebugStringW
0x18000c4a3  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000c4a8  jnz     short loc_18000C4B3
0x18000c4aa  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000c4b1  jz      short loc_18000C4C5
0x18000c4b3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c4ba  test    rax, rax
0x18000c4bd  jz      short loc_18000C4C5
0x18000c4bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4c4  nop
0x18000c4c5  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000c4ca  jnz     short loc_18000C4ED
0x18000c4cc  mov     rcx, [rbp+1400h+var_40]
0x18000c4d3  xor     rcx, rsp; StackCookie
0x18000c4d6  call    __security_check_cookie
0x18000c4db  add     rsp, 14D0h
0x18000c4e2  pop     r15
0x18000c4e4  pop     r14
0x18000c4e6  pop     r12
0x18000c4e8  pop     rdi
0x18000c4e9  pop     rsi
0x18000c4ea  pop     rbx
0x18000c4eb  pop     rbp
0x18000c4ec  retn
0x18000c4ed  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000c4f2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000c4f8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
