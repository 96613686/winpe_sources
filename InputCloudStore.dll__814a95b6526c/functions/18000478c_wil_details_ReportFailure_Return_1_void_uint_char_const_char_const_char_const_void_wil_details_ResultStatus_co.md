# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x18000478c`
- end: `0x180004a32`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180004410`

## callees

- `0x180003560`
- `0x180003fd4`
- `0x18000478c`
- `0x1800056d4`
- `0x1800068e0`
- `0x1800074d8`
- `0x180007694`
- `0x18002e660`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004852`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004852`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004947`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004947`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800049d1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800049d1`

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
    wil::details::in1diag3::FailFastImmediate_Unexpected(v15);
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
0x18000478c  push    rbp
0x18000478e  push    rbx
0x18000478f  push    rsi
0x180004790  push    rdi
0x180004791  push    r12
0x180004793  push    r14
0x180004795  push    r15
0x180004797  lea     rbp, [rsp-13D0h]
0x18000479f  mov     eax, 14D0h
0x1800047a4  call    _alloca_probe
0x1800047a9  sub     rsp, rax
0x1800047ac  mov     rax, cs:__security_cookie
0x1800047b3  xor     rax, rsp
0x1800047b6  mov     [rbp+1400h+var_40], rax
0x1800047bd  mov     rsi, r8
0x1800047c0  mov     edi, edx
0x1800047c2  mov     rbx, rcx
0x1800047c5  mov     r14, [rbp+1400h+arg_28]
0x1800047cc  xor     edx, edx; Val
0x1800047ce  mov     r8d, 98h; Size
0x1800047d4  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800047d9  call    memset_0
0x1800047de  nop
0x1800047df  xor     r12d, r12d
0x1800047e2  mov     [rbp+1400h+OutputString], r12w
0x1800047ea  mov     [rbp+1400h+var_1440], r12b
0x1800047ee  mov     rdx, [rbp+1400h+arg_30]; int
0x1800047f5  mov     ecx, [rdx]; this
0x1800047f7  mov     [rsp+1500h+var_14D8], ecx
0x1800047fb  mov     eax, [rdx+4]
0x1800047fe  mov     [rsp+1500h+var_14D4], eax
0x180004802  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004807  mov     r15d, eax
0x18000480a  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180004812  mov     ecx, r12d
0x180004815  lea     eax, [r12+8]
0x18000481a  cmp     dword ptr [rdx+8], 1
0x18000481e  cmovz   ecx, eax
0x180004821  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004825  lea     ecx, [rax-7]
0x180004828  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004830  inc     ecx
0x180004832  mov     [rsp+1500h+var_14D0], ecx
0x180004836  mov     rcx, [rbp+1400h+arg_38]
0x18000483d  test    rcx, rcx
0x180004840  jz      short loc_18000484D
0x180004842  cmp     [rcx], r12w
0x180004846  mov     [rsp+1500h+var_14C8], rcx
0x18000484b  jnz     short loc_180004852
0x18000484d  mov     [rsp+1500h+var_14C8], r12
0x180004852  call    cs:__imp_GetCurrentThreadId
0x180004858  mov     [rsp+1500h+var_14C0], eax
0x18000485c  mov     [rsp+1500h+var_14A8], rsi
0x180004861  mov     [rsp+1500h+var_14A0], edi
0x180004865  mov     [rsp+1500h+var_149C], r15d
0x18000486a  mov     [rsp+1500h+var_14B8], r12
0x18000486f  mov     [rsp+1500h+var_14B0], r12
0x180004874  mov     [rbp+1400h+var_1458], r14
0x180004878  mov     [rbp+1400h+var_1450], rbx
0x18000487c  mov     [rsp+1500h+var_1498], r12
0x180004881  xorps   xmm0, xmm0
0x180004884  xor     eax, eax
0x180004886  movups  [rbp+1400h+var_1478], xmm0
0x18000488a  mov     [rbp+1400h+var_1468], rax
0x18000488e  xorps   xmm1, xmm1
0x180004891  movups  [rsp+1500h+var_1490], xmm1
0x180004896  mov     [rbp+1400h+var_1480], rax
0x18000489a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800048a1  test    rax, rax
0x1800048a4  jz      short loc_1800048B1
0x1800048a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048ab  mov     [rbp+1400h+var_1460], rax
0x1800048af  jmp     short loc_1800048B5
0x1800048b1  mov     [rbp+1400h+var_1460], r12
0x1800048b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800048bc  test    rax, rax
0x1800048bf  jz      short loc_1800048CB
0x1800048c1  lea     rcx, [rsp+1500h+var_14E0]
0x1800048c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048cb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800048d2  test    rax, rax
0x1800048d5  jz      short loc_1800048EB
0x1800048d7  mov     r8d, 400h
0x1800048dd  lea     rdx, [rbp+1400h+var_1440]
0x1800048e1  lea     rcx, [rsp+1500h+var_14E0]
0x1800048e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800048eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800048f2  test    rax, rax
0x1800048f5  jz      short loc_180004901
0x1800048f7  lea     rcx, [rsp+1500h+var_14E0]
0x1800048fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004901  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004908  test    rax, rax
0x18000490b  jz      short loc_18000491E
0x18000490d  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004912  jnz     short loc_18000491E
0x180004914  lea     rcx, [rsp+1500h+var_14E0]
0x180004919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000491e  cmp     [rsp+1500h+var_14D8], r12d
0x180004923  jge     loc_180004A2C
0x180004929  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004930  jnz     short loc_180004951
0x180004932  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004939  test    rax, rax
0x18000493c  jz      short loc_180004947
0x18000493e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004943  test    al, al
0x180004945  jmp     short loc_18000494F
0x180004947  call    cs:__imp_IsDebuggerPresent
0x18000494d  test    eax, eax
0x18000494f  jz      short loc_180004958
0x180004951  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004956  jz      short loc_18000497E
0x180004958  mov     rax, cs:g_pfnResultLoggingCallback
0x18000495f  test    rax, rax
0x180004962  jz      short loc_1800049D7
0x180004964  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000496b  jnz     short loc_1800049D7
0x18000496d  xor     r8d, r8d
0x180004970  xor     edx, edx
0x180004972  lea     rcx, [rsp+1500h+var_14E0]
0x180004977  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000497c  jmp     short loc_1800049D7
0x18000497e  mov     ebx, 800h
0x180004983  mov     rax, cs:g_pfnResultLoggingCallback
0x18000498a  test    rax, rax
0x18000498d  jz      short loc_1800049AC
0x18000498f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180004996  jnz     short loc_1800049AC
0x180004998  mov     r8d, ebx
0x18000499b  lea     rdx, [rbp+1400h+OutputString]
0x1800049a2  lea     rcx, [rsp+1500h+var_14E0]
0x1800049a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049ac  cmp     [rbp+1400h+OutputString], r12w
0x1800049b4  jnz     short loc_1800049CA
0x1800049b6  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800049bb  mov     rdx, rbx; wchar_t *
0x1800049be  lea     rcx, [rbp+1400h+OutputString]; this
0x1800049c5  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800049ca  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800049d1  call    cs:__imp_OutputDebugStringW
0x1800049d7  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800049dc  jnz     short loc_1800049E7
0x1800049de  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800049e5  jz      short loc_1800049F9
0x1800049e7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800049ee  test    rax, rax
0x1800049f1  jz      short loc_1800049F9
0x1800049f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800049f8  nop
0x1800049f9  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1800049fe  jnz     short loc_180004A21
0x180004a00  mov     rcx, [rbp+1400h+var_40]
0x180004a07  xor     rcx, rsp; StackCookie
0x180004a0a  call    __security_check_cookie
0x180004a0f  add     rsp, 14D0h
0x180004a16  pop     r15
0x180004a18  pop     r14
0x180004a1a  pop     r12
0x180004a1c  pop     rdi
0x180004a1d  pop     rsi
0x180004a1e  pop     rbx
0x180004a1f  pop     rbp
0x180004a20  retn
0x180004a21  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004a26  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180004a2c  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
