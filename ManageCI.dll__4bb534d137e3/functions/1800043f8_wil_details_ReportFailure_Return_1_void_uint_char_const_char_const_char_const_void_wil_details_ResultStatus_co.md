# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800043f8`
- end: `0x18000469e`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003c90`

## callees

- `0x180002a90`
- `0x180003888`
- `0x1800043f8`
- `0x180005f24`
- `0x180007140`
- `0x180008028`
- `0x18000822c`
- `0x180029780`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800044be`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000463d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000463d`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800045b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800045b3`

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
0x1800043f8  push    rbp
0x1800043fa  push    rbx
0x1800043fb  push    rsi
0x1800043fc  push    rdi
0x1800043fd  push    r12
0x1800043ff  push    r14
0x180004401  push    r15
0x180004403  lea     rbp, [rsp-13D0h]
0x18000440b  mov     eax, 14D0h
0x180004410  call    _alloca_probe
0x180004415  sub     rsp, rax
0x180004418  mov     rax, cs:__security_cookie
0x18000441f  xor     rax, rsp
0x180004422  mov     [rbp+1400h+var_40], rax
0x180004429  mov     rsi, r8
0x18000442c  mov     edi, edx
0x18000442e  mov     rbx, rcx
0x180004431  mov     r14, [rbp+1400h+arg_28]
0x180004438  xor     edx, edx; Val
0x18000443a  mov     r8d, 98h; Size
0x180004440  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004445  call    memset_0
0x18000444a  nop
0x18000444b  xor     r12d, r12d
0x18000444e  mov     [rbp+1400h+OutputString], r12w
0x180004456  mov     [rbp+1400h+var_1440], r12b
0x18000445a  mov     rdx, [rbp+1400h+arg_30]; int
0x180004461  mov     ecx, [rdx]; this
0x180004463  mov     [rsp+1500h+var_14D8], ecx
0x180004467  mov     eax, [rdx+4]
0x18000446a  mov     [rsp+1500h+var_14D4], eax
0x18000446e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004473  mov     r15d, eax
0x180004476  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000447e  mov     ecx, r12d
0x180004481  lea     eax, [r12+8]
0x180004486  cmp     dword ptr [rdx+8], 1
0x18000448a  cmovz   ecx, eax
0x18000448d  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004491  lea     ecx, [rax-7]
0x180004494  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000449c  inc     ecx
0x18000449e  mov     [rsp+1500h+var_14D0], ecx
0x1800044a2  mov     rcx, [rbp+1400h+arg_38]
0x1800044a9  test    rcx, rcx
0x1800044ac  jz      short loc_1800044B9
0x1800044ae  cmp     [rcx], r12w
0x1800044b2  mov     [rsp+1500h+var_14C8], rcx
0x1800044b7  jnz     short loc_1800044BE
0x1800044b9  mov     [rsp+1500h+var_14C8], r12
0x1800044be  call    cs:__imp_GetCurrentThreadId
0x1800044c4  mov     [rsp+1500h+var_14C0], eax
0x1800044c8  mov     [rsp+1500h+var_14A8], rsi
0x1800044cd  mov     [rsp+1500h+var_14A0], edi
0x1800044d1  mov     [rsp+1500h+var_149C], r15d
0x1800044d6  mov     [rsp+1500h+var_14B8], r12
0x1800044db  mov     [rsp+1500h+var_14B0], r12
0x1800044e0  mov     [rbp+1400h+var_1458], r14
0x1800044e4  mov     [rbp+1400h+var_1450], rbx
0x1800044e8  mov     [rsp+1500h+var_1498], r12
0x1800044ed  xorps   xmm0, xmm0
0x1800044f0  xor     eax, eax
0x1800044f2  movups  [rbp+1400h+var_1478], xmm0
0x1800044f6  mov     [rbp+1400h+var_1468], rax
0x1800044fa  xorps   xmm1, xmm1
0x1800044fd  movups  [rsp+1500h+var_1490], xmm1
0x180004502  mov     [rbp+1400h+var_1480], rax
0x180004506  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000450d  test    rax, rax
0x180004510  jz      short loc_18000451D
0x180004512  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004517  mov     [rbp+1400h+var_1460], rax
0x18000451b  jmp     short loc_180004521
0x18000451d  mov     [rbp+1400h+var_1460], r12
0x180004521  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004528  test    rax, rax
0x18000452b  jz      short loc_180004537
0x18000452d  lea     rcx, [rsp+1500h+var_14E0]
0x180004532  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004537  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000453e  test    rax, rax
0x180004541  jz      short loc_180004557
0x180004543  mov     r8d, 400h
0x180004549  lea     rdx, [rbp+1400h+var_1440]
0x18000454d  lea     rcx, [rsp+1500h+var_14E0]
0x180004552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004557  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000455e  test    rax, rax
0x180004561  jz      short loc_18000456D
0x180004563  lea     rcx, [rsp+1500h+var_14E0]
0x180004568  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000456d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004574  test    rax, rax
0x180004577  jz      short loc_18000458A
0x180004579  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000457e  jnz     short loc_18000458A
0x180004580  lea     rcx, [rsp+1500h+var_14E0]
0x180004585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000458a  cmp     [rsp+1500h+var_14D8], r12d
0x18000458f  jge     loc_180004698
0x180004595  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000459c  jnz     short loc_1800045BD
0x18000459e  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800045a5  test    rax, rax
0x1800045a8  jz      short loc_1800045B3
0x1800045aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045af  test    al, al
0x1800045b1  jmp     short loc_1800045BB
0x1800045b3  call    cs:__imp_IsDebuggerPresent
0x1800045b9  test    eax, eax
0x1800045bb  jz      short loc_1800045C4
0x1800045bd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800045c2  jz      short loc_1800045EA
0x1800045c4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800045cb  test    rax, rax
0x1800045ce  jz      short loc_180004643
0x1800045d0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800045d7  jnz     short loc_180004643
0x1800045d9  xor     r8d, r8d
0x1800045dc  xor     edx, edx
0x1800045de  lea     rcx, [rsp+1500h+var_14E0]
0x1800045e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e8  jmp     short loc_180004643
0x1800045ea  mov     ebx, 800h
0x1800045ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800045f6  test    rax, rax
0x1800045f9  jz      short loc_180004618
0x1800045fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004602  jnz     short loc_180004618
0x180004604  mov     r8d, ebx
0x180004607  lea     rdx, [rbp+1400h+OutputString]
0x18000460e  lea     rcx, [rsp+1500h+var_14E0]
0x180004613  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004618  cmp     [rbp+1400h+OutputString], r12w
0x180004620  jnz     short loc_180004636
0x180004622  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180004627  mov     rdx, rbx; unsigned __int16 *
0x18000462a  lea     rcx, [rbp+1400h+OutputString]; this
0x180004631  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004636  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000463d  call    cs:__imp_OutputDebugStringW
0x180004643  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180004648  jnz     short loc_180004653
0x18000464a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004651  jz      short loc_180004665
0x180004653  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000465a  test    rax, rax
0x18000465d  jz      short loc_180004665
0x18000465f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004664  nop
0x180004665  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000466a  jnz     short loc_18000468D
0x18000466c  mov     rcx, [rbp+1400h+var_40]
0x180004673  xor     rcx, rsp; StackCookie
0x180004676  call    __security_check_cookie
0x18000467b  add     rsp, 14D0h
0x180004682  pop     r15
0x180004684  pop     r14
0x180004686  pop     r12
0x180004688  pop     rdi
0x180004689  pop     rsi
0x18000468a  pop     rbx
0x18000468b  pop     rbp
0x18000468c  retn
0x18000468d  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004692  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004698  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
