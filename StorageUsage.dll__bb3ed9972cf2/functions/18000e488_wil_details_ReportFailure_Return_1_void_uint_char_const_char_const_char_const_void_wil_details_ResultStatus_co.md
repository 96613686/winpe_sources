# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000e488`
- end: `0x18000e70f`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `647`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000df94`

## callees

- `0x1800050f0`
- `0x180005c94`
- `0x18000e488`
- `0x180011b64`
- `0x180013b74`
- `0x180014ea0`
- `0x1800161d8`
- `0x1800167a0`
- `0x18002af30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e54e`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e54e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e688`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e688`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
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
  bool v14; // zf
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // rdx
  __int64 v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  _WORD *v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v20 = v12;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v14 = *a8 == 0, v24 = a8, v14) )
    v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = a3;
  v29 = a2;
  v30 = v11;
  v26 = 0;
  v27 = 0;
  v37 = a6;
  v38 = a1;
  v31 = 0;
  v34 = 0;
  v35 = 0;
  v32 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
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
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::details::IsDebuggerPresent(v15) || (v20 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v19, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v16);
}

```

## disassembly

```asm
0x18000e488  push    rbp
0x18000e48a  push    rbx
0x18000e48b  push    rsi
0x18000e48c  push    rdi
0x18000e48d  push    r12
0x18000e48f  push    r14
0x18000e491  push    r15
0x18000e493  lea     rbp, [rsp-13D0h]
0x18000e49b  mov     eax, 14D0h
0x18000e4a0  call    _alloca_probe
0x18000e4a5  sub     rsp, rax
0x18000e4a8  mov     rax, cs:__security_cookie
0x18000e4af  xor     rax, rsp
0x18000e4b2  mov     [rbp+1400h+var_40], rax
0x18000e4b9  mov     rsi, r8
0x18000e4bc  mov     edi, edx
0x18000e4be  mov     rbx, rcx
0x18000e4c1  mov     r14, [rbp+1400h+arg_28]
0x18000e4c8  xor     edx, edx; Val
0x18000e4ca  mov     r8d, 98h; Size
0x18000e4d0  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000e4d5  call    memset_0
0x18000e4da  nop
0x18000e4db  xor     r12d, r12d
0x18000e4de  mov     [rbp+1400h+OutputString], r12w
0x18000e4e6  mov     [rbp+1400h+var_1440], r12b
0x18000e4ea  mov     rdx, [rbp+1400h+arg_30]; int
0x18000e4f1  mov     ecx, [rdx]; this
0x18000e4f3  mov     [rsp+1500h+var_14D8], ecx
0x18000e4f7  mov     eax, [rdx+4]
0x18000e4fa  mov     [rsp+1500h+var_14D4], eax
0x18000e4fe  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e503  mov     r15d, eax
0x18000e506  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000e50e  mov     ecx, r12d
0x18000e511  lea     eax, [r12+8]
0x18000e516  cmp     dword ptr [rdx+8], 1
0x18000e51a  cmovz   ecx, eax
0x18000e51d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000e521  lea     ecx, [rax-7]
0x18000e524  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e52c  inc     ecx
0x18000e52e  mov     [rsp+1500h+var_14D0], ecx
0x18000e532  mov     rcx, [rbp+1400h+arg_38]
0x18000e539  test    rcx, rcx
0x18000e53c  jz      short loc_18000E549
0x18000e53e  cmp     [rcx], r12w
0x18000e542  mov     [rsp+1500h+var_14C8], rcx
0x18000e547  jnz     short loc_18000E54E
0x18000e549  mov     [rsp+1500h+var_14C8], r12
0x18000e54e  call    cs:__imp_GetCurrentThreadId
0x18000e554  mov     [rsp+1500h+var_14C0], eax
0x18000e558  mov     [rsp+1500h+var_14A8], rsi
0x18000e55d  mov     [rsp+1500h+var_14A0], edi
0x18000e561  mov     [rsp+1500h+var_149C], r15d
0x18000e566  mov     [rsp+1500h+var_14B8], r12
0x18000e56b  mov     [rsp+1500h+var_14B0], r12
0x18000e570  mov     [rbp+1400h+var_1458], r14
0x18000e574  mov     [rbp+1400h+var_1450], rbx
0x18000e578  mov     [rsp+1500h+var_1498], r12
0x18000e57d  xorps   xmm0, xmm0
0x18000e580  xor     eax, eax
0x18000e582  movups  [rbp+1400h+var_1478], xmm0
0x18000e586  mov     [rbp+1400h+var_1468], rax
0x18000e58a  xorps   xmm1, xmm1
0x18000e58d  movups  [rsp+1500h+var_1490], xmm1
0x18000e592  mov     [rbp+1400h+var_1480], rax
0x18000e596  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e59d  test    rax, rax
0x18000e5a0  jz      short loc_18000E5AD
0x18000e5a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5a7  mov     [rbp+1400h+var_1460], rax
0x18000e5ab  jmp     short loc_18000E5B1
0x18000e5ad  mov     [rbp+1400h+var_1460], r12
0x18000e5b1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e5b8  test    rax, rax
0x18000e5bb  jz      short loc_18000E5C7
0x18000e5bd  lea     rcx, [rsp+1500h+var_14E0]
0x18000e5c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5c7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e5ce  test    rax, rax
0x18000e5d1  jz      short loc_18000E5E7
0x18000e5d3  mov     r8d, 400h
0x18000e5d9  lea     rdx, [rbp+1400h+var_1440]
0x18000e5dd  lea     rcx, [rsp+1500h+var_14E0]
0x18000e5e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5e7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e5ee  test    rax, rax
0x18000e5f1  jz      short loc_18000E5FD
0x18000e5f3  lea     rcx, [rsp+1500h+var_14E0]
0x18000e5f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5fd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e604  test    rax, rax
0x18000e607  jz      short loc_18000E61A
0x18000e609  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e60e  jnz     short loc_18000E61A
0x18000e610  lea     rcx, [rsp+1500h+var_14E0]
0x18000e615  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e61a  cmp     [rsp+1500h+var_14D8], r12d
0x18000e61f  jge     loc_18000E709
0x18000e625  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x18000e62a  test    al, al
0x18000e62c  jz      short loc_18000E690
0x18000e62e  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000e633  jnz     short loc_18000E690
0x18000e635  mov     ebx, 800h
0x18000e63a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e641  test    rax, rax
0x18000e644  jz      short loc_18000E663
0x18000e646  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e64d  jnz     short loc_18000E663
0x18000e64f  mov     r8d, ebx
0x18000e652  lea     rdx, [rbp+1400h+OutputString]
0x18000e659  lea     rcx, [rsp+1500h+var_14E0]
0x18000e65e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e663  cmp     [rbp+1400h+OutputString], r12w
0x18000e66b  jnz     short loc_18000E681
0x18000e66d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000e672  mov     rdx, rbx; unsigned __int16 *
0x18000e675  lea     rcx, [rbp+1400h+OutputString]; this
0x18000e67c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e681  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000e688  call    cs:__imp_OutputDebugStringW
0x18000e68e  jmp     short loc_18000E6B4
0x18000e690  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e697  test    rax, rax
0x18000e69a  jz      short loc_18000E6B4
0x18000e69c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000e6a3  jnz     short loc_18000E6B4
0x18000e6a5  xor     r8d, r8d
0x18000e6a8  xor     edx, edx
0x18000e6aa  lea     rcx, [rsp+1500h+var_14E0]
0x18000e6af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6b4  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000e6b9  jnz     short loc_18000E6C4
0x18000e6bb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000e6c2  jz      short loc_18000E6D6
0x18000e6c4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e6cb  test    rax, rax
0x18000e6ce  jz      short loc_18000E6D6
0x18000e6d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e6d5  nop
0x18000e6d6  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000e6db  jnz     short loc_18000E6FE
0x18000e6dd  mov     rcx, [rbp+1400h+var_40]
0x18000e6e4  xor     rcx, rsp; StackCookie
0x18000e6e7  call    __security_check_cookie
0x18000e6ec  add     rsp, 14D0h
0x18000e6f3  pop     r15
0x18000e6f5  pop     r14
0x18000e6f7  pop     r12
0x18000e6f9  pop     rdi
0x18000e6fa  pop     rsi
0x18000e6fb  pop     rbx
0x18000e6fc  pop     rbp
0x18000e6fd  retn
0x18000e6fe  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000e703  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000e709  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
