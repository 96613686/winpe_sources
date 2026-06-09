# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800236a0`
- end: `0x180023944`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `676`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18001a694`

## callees

- `0x1800236a0`
- `0x180024144`
- `0x180024cb0`
- `0x1800254c8`
- `0x180025674`
- `0x18004c98a`
- `0x18004c9d0`
- `0x18004ca60`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023765`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180023765`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002385a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002385a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800238e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800238e4`

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
  int v11; // eax
  int v12; // eax
  __int64 v13; // rdx
  int v14; // r15d
  int v15; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v17; // rdx
  wil::details::in1diag3 *v18; // rcx
  const struct wil::FailureInfo *v19; // r9
  bool v20; // zf
  int v21; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+24h] [rbp-DCh]
  int v23; // [rsp+28h] [rbp-D8h]
  int v24; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v25; // [rsp+30h] [rbp-D0h]
  _WORD *v26; // [rsp+38h] [rbp-C8h]
  DWORD v27; // [rsp+40h] [rbp-C0h]
  __int64 v28; // [rsp+48h] [rbp-B8h]
  __int64 v29; // [rsp+50h] [rbp-B0h]
  __int64 v30; // [rsp+58h] [rbp-A8h]
  int v31; // [rsp+60h] [rbp-A0h]
  int v32; // [rsp+64h] [rbp-9Ch]
  __int64 v33; // [rsp+68h] [rbp-98h]
  __int128 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+80h] [rbp-80h]
  __int128 v36; // [rsp+88h] [rbp-78h]
  __int64 v37; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v39; // [rsp+A8h] [rbp-58h]
  __int64 v40; // [rsp+B0h] [rbp-50h]
  char v41[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v21, 0, 0x98u);
  OutputString[0] = 0;
  v41[0] = 0;
  v11 = a7[1];
  v23 = *a7;
  v24 = v11;
  v12 = wil::details::RecordReturn((wil::details *)(unsigned int)v23, (int)a7);
  v20 = *(_DWORD *)(v13 + 8) == 1;
  v14 = v12;
  v21 = 1;
  v15 = 0;
  if ( v20 )
    v15 = 8;
  v22 = v15;
  v25 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v26 = a8, !*a8) )
    v26 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v30 = a3;
  v27 = CurrentThreadId;
  v31 = a2;
  v37 = 0;
  v35 = 0;
  v32 = v14;
  v28 = 0;
  v29 = 0;
  v39 = a6;
  v40 = a1;
  v33 = 0;
  v36 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v18);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v21);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v21, v41, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v21);
  if ( wil::details::g_pfnOriginateCallback && (v22 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v21);
  if ( v23 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v18);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v20 = !IsDebuggerPresent())
      : (v20 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v18) == 0),
        v20)
    || (v22 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v21, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v21, v19);
    OutputDebugStringW(OutputString);
  }
  if ( ((v22 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v18);
  if ( (v22 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v21, v17);
}

```

## disassembly

```asm
0x1800236a0  push    rbp
0x1800236a2  push    rbx
0x1800236a3  push    rsi
0x1800236a4  push    rdi
0x1800236a5  push    r12
0x1800236a7  push    r14
0x1800236a9  push    r15
0x1800236ab  lea     rbp, [rsp-13D0h]
0x1800236b3  mov     eax, 14D0h
0x1800236b8  call    _alloca_probe
0x1800236bd  sub     rsp, rax
0x1800236c0  mov     rax, cs:__security_cookie
0x1800236c7  xor     rax, rsp
0x1800236ca  mov     [rbp+1400h+var_40], rax
0x1800236d1  mov     r14, [rbp+1400h+arg_28]
0x1800236d8  mov     rsi, r8
0x1800236db  mov     edi, edx
0x1800236dd  mov     rbx, rcx
0x1800236e0  xor     edx, edx; Val
0x1800236e2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800236e7  mov     r8d, 98h; Size
0x1800236ed  call    memset_0
0x1800236f2  mov     rdx, [rbp+1400h+arg_30]; int
0x1800236f9  xor     r12d, r12d
0x1800236fc  mov     [rbp+1400h+OutputString], r12w
0x180023704  mov     [rbp+1400h+var_1440], r12b
0x180023708  mov     ecx, [rdx]; this
0x18002370a  mov     eax, [rdx+4]
0x18002370d  mov     [rsp+1500h+var_14D8], ecx
0x180023711  mov     [rsp+1500h+var_14D4], eax
0x180023715  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002371a  cmp     dword ptr [rdx+8], 1
0x18002371e  mov     r15d, eax
0x180023721  lea     eax, [r12+8]
0x180023726  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18002372e  mov     ecx, r12d
0x180023731  cmovz   ecx, eax
0x180023734  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180023738  lea     ecx, [rax-7]
0x18002373b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180023743  inc     ecx
0x180023745  mov     [rsp+1500h+var_14D0], ecx
0x180023749  mov     rcx, [rbp+1400h+arg_38]
0x180023750  test    rcx, rcx
0x180023753  jz      short loc_180023760
0x180023755  mov     [rsp+1500h+var_14C8], rcx
0x18002375a  cmp     [rcx], r12w
0x18002375e  jnz     short loc_180023765
0x180023760  mov     [rsp+1500h+var_14C8], r12
0x180023765  call    cs:__imp_GetCurrentThreadId
0x18002376b  xorps   xmm0, xmm0
0x18002376e  mov     [rsp+1500h+var_14A8], rsi
0x180023773  mov     [rsp+1500h+var_14C0], eax
0x180023777  xorps   xmm1, xmm1
0x18002377a  xor     eax, eax
0x18002377c  mov     [rsp+1500h+var_14A0], edi
0x180023780  mov     [rbp+1400h+var_1468], rax
0x180023784  mov     [rbp+1400h+var_1480], rax
0x180023788  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002378f  mov     [rsp+1500h+var_149C], r15d
0x180023794  mov     [rsp+1500h+var_14B8], r12
0x180023799  mov     [rsp+1500h+var_14B0], r12
0x18002379e  mov     [rbp+1400h+var_1458], r14
0x1800237a2  mov     [rbp+1400h+var_1450], rbx
0x1800237a6  mov     [rsp+1500h+var_1498], r12
0x1800237ab  movups  [rbp+1400h+var_1478], xmm0
0x1800237af  movups  [rsp+1500h+var_1490], xmm1
0x1800237b4  test    rax, rax
0x1800237b7  jz      short loc_1800237C4
0x1800237b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237be  mov     [rbp+1400h+var_1460], rax
0x1800237c2  jmp     short loc_1800237C8
0x1800237c4  mov     [rbp+1400h+var_1460], r12
0x1800237c8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800237cf  test    rax, rax
0x1800237d2  jz      short loc_1800237DE
0x1800237d4  lea     rcx, [rsp+1500h+var_14E0]
0x1800237d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237de  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800237e5  test    rax, rax
0x1800237e8  jz      short loc_1800237FE
0x1800237ea  mov     r8d, 400h
0x1800237f0  lea     rdx, [rbp+1400h+var_1440]
0x1800237f4  lea     rcx, [rsp+1500h+var_14E0]
0x1800237f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237fe  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180023805  test    rax, rax
0x180023808  jz      short loc_180023814
0x18002380a  lea     rcx, [rsp+1500h+var_14E0]
0x18002380f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023814  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002381b  test    rax, rax
0x18002381e  jz      short loc_180023831
0x180023820  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180023825  jnz     short loc_180023831
0x180023827  lea     rcx, [rsp+1500h+var_14E0]
0x18002382c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023831  cmp     [rsp+1500h+var_14D8], r12d
0x180023836  jge     loc_180023933
0x18002383c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180023843  jnz     short loc_180023864
0x180023845  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002384c  test    rax, rax
0x18002384f  jz      short loc_18002385A
0x180023851  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023856  test    al, al
0x180023858  jmp     short loc_180023862
0x18002385a  call    cs:__imp_IsDebuggerPresent
0x180023860  test    eax, eax
0x180023862  jz      short loc_18002386B
0x180023864  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180023869  jz      short loc_180023891
0x18002386b  mov     rax, cs:g_pfnResultLoggingCallback
0x180023872  test    rax, rax
0x180023875  jz      short loc_1800238EA
0x180023877  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18002387e  jnz     short loc_1800238EA
0x180023880  xor     r8d, r8d
0x180023883  lea     rcx, [rsp+1500h+var_14E0]
0x180023888  xor     edx, edx
0x18002388a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002388f  jmp     short loc_1800238EA
0x180023891  mov     rax, cs:g_pfnResultLoggingCallback
0x180023898  mov     ebx, 800h
0x18002389d  test    rax, rax
0x1800238a0  jz      short loc_1800238BF
0x1800238a2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800238a9  jnz     short loc_1800238BF
0x1800238ab  mov     r8d, ebx
0x1800238ae  lea     rdx, [rbp+1400h+OutputString]
0x1800238b5  lea     rcx, [rsp+1500h+var_14E0]
0x1800238ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800238bf  cmp     [rbp+1400h+OutputString], r12w
0x1800238c7  jnz     short loc_1800238DD
0x1800238c9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800238ce  mov     rdx, rbx; unsigned __int16 *
0x1800238d1  lea     rcx, [rbp+1400h+OutputString]; this
0x1800238d8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800238dd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800238e4  call    cs:__imp_OutputDebugStringW
0x1800238ea  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800238ef  jnz     short loc_1800238FA
0x1800238f1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800238f8  jz      short loc_18002390B
0x1800238fa  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180023901  test    rax, rax
0x180023904  jz      short loc_18002390B
0x180023906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002390b  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180023910  jnz     short loc_180023939
0x180023912  mov     rcx, [rbp+1400h+var_40]
0x180023919  xor     rcx, rsp; StackCookie
0x18002391c  call    __security_check_cookie
0x180023921  add     rsp, 14D0h
0x180023928  pop     r15
0x18002392a  pop     r14
0x18002392c  pop     r12
0x18002392e  pop     rdi
0x18002392f  pop     rsi
0x180023930  pop     rbx
0x180023931  pop     rbp
0x180023932  retn
0x180023933  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180023939  lea     rcx, [rsp+1500h+var_14E0]; this
0x18002393e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
