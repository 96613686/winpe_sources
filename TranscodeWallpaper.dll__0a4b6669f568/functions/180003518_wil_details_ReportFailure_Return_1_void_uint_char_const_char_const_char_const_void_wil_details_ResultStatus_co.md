# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003518`
- end: `0x1800037be`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180002e68`

## callees

- `0x180002170`
- `0x180002cb4`
- `0x180003518`
- `0x180004874`
- `0x1800057b0`
- `0x1800068a0`
- `0x18000697c`
- `0x18000dd00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035de`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000375d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000375d`

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
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v18, v16);
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
0x180003518  push    rbp
0x18000351a  push    rbx
0x18000351b  push    rsi
0x18000351c  push    rdi
0x18000351d  push    r12
0x18000351f  push    r14
0x180003521  push    r15
0x180003523  lea     rbp, [rsp-13D0h]
0x18000352b  mov     eax, 14D0h
0x180003530  call    _alloca_probe
0x180003535  sub     rsp, rax
0x180003538  mov     rax, cs:__security_cookie
0x18000353f  xor     rax, rsp
0x180003542  mov     [rbp+1400h+var_40], rax
0x180003549  mov     rsi, r8
0x18000354c  mov     edi, edx
0x18000354e  mov     rbx, rcx
0x180003551  mov     r14, [rbp+1400h+arg_28]
0x180003558  xor     edx, edx; Val
0x18000355a  mov     r8d, 98h; Size
0x180003560  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003565  call    memset_0
0x18000356a  nop
0x18000356b  xor     r12d, r12d
0x18000356e  mov     [rbp+1400h+OutputString], r12w
0x180003576  mov     [rbp+1400h+var_1440], r12b
0x18000357a  mov     rdx, [rbp+1400h+arg_30]; int
0x180003581  mov     ecx, [rdx]; this
0x180003583  mov     [rsp+1500h+var_14D8], ecx
0x180003587  mov     eax, [rdx+4]
0x18000358a  mov     [rsp+1500h+var_14D4], eax
0x18000358e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180003593  mov     r15d, eax
0x180003596  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000359e  mov     ecx, r12d
0x1800035a1  lea     eax, [r12+8]
0x1800035a6  cmp     dword ptr [rdx+8], 1
0x1800035aa  cmovz   ecx, eax
0x1800035ad  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800035b1  lea     ecx, [rax-7]
0x1800035b4  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800035bc  inc     ecx
0x1800035be  mov     [rsp+1500h+var_14D0], ecx
0x1800035c2  mov     rcx, [rbp+1400h+arg_38]
0x1800035c9  test    rcx, rcx
0x1800035cc  jz      short loc_1800035D9
0x1800035ce  cmp     [rcx], r12w
0x1800035d2  mov     [rsp+1500h+var_14C8], rcx
0x1800035d7  jnz     short loc_1800035DE
0x1800035d9  mov     [rsp+1500h+var_14C8], r12
0x1800035de  call    cs:__imp_GetCurrentThreadId
0x1800035e4  mov     [rsp+1500h+var_14C0], eax
0x1800035e8  mov     [rsp+1500h+var_14A8], rsi
0x1800035ed  mov     [rsp+1500h+var_14A0], edi
0x1800035f1  mov     [rsp+1500h+var_149C], r15d
0x1800035f6  mov     [rsp+1500h+var_14B8], r12
0x1800035fb  mov     [rsp+1500h+var_14B0], r12
0x180003600  mov     [rbp+1400h+var_1458], r14
0x180003604  mov     [rbp+1400h+var_1450], rbx
0x180003608  mov     [rsp+1500h+var_1498], r12
0x18000360d  xorps   xmm0, xmm0
0x180003610  xor     eax, eax
0x180003612  movups  [rbp+1400h+var_1478], xmm0
0x180003616  mov     [rbp+1400h+var_1468], rax
0x18000361a  xorps   xmm1, xmm1
0x18000361d  movups  [rsp+1500h+var_1490], xmm1
0x180003622  mov     [rbp+1400h+var_1480], rax
0x180003626  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000362d  test    rax, rax
0x180003630  jz      short loc_18000363D
0x180003632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003637  mov     [rbp+1400h+var_1460], rax
0x18000363b  jmp     short loc_180003641
0x18000363d  mov     [rbp+1400h+var_1460], r12
0x180003641  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003648  test    rax, rax
0x18000364b  jz      short loc_180003657
0x18000364d  lea     rcx, [rsp+1500h+var_14E0]
0x180003652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003657  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000365e  test    rax, rax
0x180003661  jz      short loc_180003677
0x180003663  mov     r8d, 400h
0x180003669  lea     rdx, [rbp+1400h+var_1440]
0x18000366d  lea     rcx, [rsp+1500h+var_14E0]
0x180003672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003677  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000367e  test    rax, rax
0x180003681  jz      short loc_18000368D
0x180003683  lea     rcx, [rsp+1500h+var_14E0]
0x180003688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000368d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003694  test    rax, rax
0x180003697  jz      short loc_1800036AA
0x180003699  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000369e  jnz     short loc_1800036AA
0x1800036a0  lea     rcx, [rsp+1500h+var_14E0]
0x1800036a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036aa  cmp     [rsp+1500h+var_14D8], r12d
0x1800036af  jge     loc_1800037B8
0x1800036b5  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800036bc  jnz     short loc_1800036DD
0x1800036be  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800036c5  test    rax, rax
0x1800036c8  jz      short loc_1800036D3
0x1800036ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036cf  test    al, al
0x1800036d1  jmp     short loc_1800036DB
0x1800036d3  call    cs:__imp_IsDebuggerPresent
0x1800036d9  test    eax, eax
0x1800036db  jz      short loc_1800036E4
0x1800036dd  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800036e2  jz      short loc_18000370A
0x1800036e4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800036eb  test    rax, rax
0x1800036ee  jz      short loc_180003763
0x1800036f0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800036f7  jnz     short loc_180003763
0x1800036f9  xor     r8d, r8d
0x1800036fc  xor     edx, edx
0x1800036fe  lea     rcx, [rsp+1500h+var_14E0]
0x180003703  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003708  jmp     short loc_180003763
0x18000370a  mov     ebx, 800h
0x18000370f  mov     rax, cs:g_pfnResultLoggingCallback
0x180003716  test    rax, rax
0x180003719  jz      short loc_180003738
0x18000371b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003722  jnz     short loc_180003738
0x180003724  mov     r8d, ebx
0x180003727  lea     rdx, [rbp+1400h+OutputString]
0x18000372e  lea     rcx, [rsp+1500h+var_14E0]
0x180003733  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003738  cmp     [rbp+1400h+OutputString], r12w
0x180003740  jnz     short loc_180003756
0x180003742  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003747  mov     rdx, rbx; wchar_t *
0x18000374a  lea     rcx, [rbp+1400h+OutputString]; this
0x180003751  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180003756  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000375d  call    cs:__imp_OutputDebugStringW
0x180003763  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003768  jnz     short loc_180003773
0x18000376a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003771  jz      short loc_180003785
0x180003773  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000377a  test    rax, rax
0x18000377d  jz      short loc_180003785
0x18000377f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003784  nop
0x180003785  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000378a  jnz     short loc_1800037AD
0x18000378c  mov     rcx, [rbp+1400h+var_40]
0x180003793  xor     rcx, rsp; StackCookie
0x180003796  call    __security_check_cookie
0x18000379b  add     rsp, 14D0h
0x1800037a2  pop     r15
0x1800037a4  pop     r14
0x1800037a6  pop     r12
0x1800037a8  pop     rdi
0x1800037a9  pop     rsi
0x1800037aa  pop     rbx
0x1800037ab  pop     rbp
0x1800037ac  retn
0x1800037ad  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800037b2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800037b8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
