# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions)

- ea: `0x18000728c`
- end: `0x18000753f`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@@Z`
- size: `691`
- prototype: `void __fastcall __noreturn(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting`

## callers

- `0x180007208`

## callees

- `0x180002cb4`
- `0x180004874`
- `0x180005764`
- `0x180006550`
- `0x1800068a0`
- `0x18000697c`
- `0x18000728c`
- `0x18000dd00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007335`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007335`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007437`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007437`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800074d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800074d3`

## string_xrefs

- `0x18000733f`: `shell\themes\wallpapertranscodecontainer\dll\transcodewallpaper.cpp`

## pseudocode

```c
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v9; // r15
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  char v17; // bl
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h] BYREF
  int v20; // [rsp+24h] [rbp-DCh]
  int v21; // [rsp+28h] [rbp-D8h]
  int v22; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v23; // [rsp+30h] [rbp-D0h]
  __int64 v24; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v26; // [rsp+48h] [rbp-B8h]
  __int64 v27; // [rsp+50h] [rbp-B0h]
  const char *v28; // [rsp+58h] [rbp-A8h]
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
  WCHAR OutputString[2064]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v9 = g_pfnThrowPlatformException != 0;
  memset_0(&v19, 0, 0x98u);
  OutputString[0] = 0;
  v39[0] = 0;
  v21 = *a7;
  v22 = a7[1];
  v10 = wil::details::RecordException((wil::details *)(unsigned int)v21, (int)a7);
  v19 = 0;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v20 = v11;
  v23 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v24 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v28 = "shell\\themes\\wallpapertranscodecontainer\\dll\\transcodewallpaper.cpp";
  v29 = a2;
  v30 = v10;
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
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v19);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v19, v39, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v19);
  if ( wil::details::g_pfnOriginateCallback && !v9 && (v20 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v19);
  if ( v21 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v17 = 1, (v20 & 2) != 0) )
  {
    v17 = 0;
  }
  if ( v9 || v17 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v19, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v19, v15);
    if ( v17 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v19, 0, 0);
  }
  if ( ((v20 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v20 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v19, v13);
  if ( v9 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v19, OutputString);
  wil::ThrowResultException((wil *)&v19, v13);
  wil::details::WilFailFast((wil::details *)&v19, v18);
}

```

## disassembly

```asm
0x18000728c  mov     [rsp-8+arg_10], rbx
0x180007291  mov     [rsp-8+arg_18], rsi
0x180007296  push    rbp
0x180007297  push    rdi
0x180007298  push    r12
0x18000729a  push    r14
0x18000729c  push    r15
0x18000729e  lea     rbp, [rsp-13C0h]
0x1800072a6  mov     eax, 14C0h
0x1800072ab  call    _alloca_probe
0x1800072b0  sub     rsp, rax
0x1800072b3  mov     esi, edx
0x1800072b5  mov     r14, rcx
0x1800072b8  mov     rdi, [rbp+13E0h+arg_28]
0x1800072bf  xor     r12d, r12d
0x1800072c2  cmp     cs:g_pfnThrowPlatformException, r12
0x1800072c9  setnz   r15b
0x1800072cd  xor     edx, edx; Val
0x1800072cf  mov     r8d, 98h; Size
0x1800072d5  lea     rcx, [rsp+14E0h+var_14C0]; void *
0x1800072da  call    memset_0
0x1800072df  nop
0x1800072e0  mov     [rbp+13E0h+OutputString], r12w
0x1800072e8  mov     [rbp+13E0h+var_1420], r12b
0x1800072ec  mov     rdx, qword ptr [rbp+13E0h+arg_30]; int
0x1800072f3  mov     ecx, [rdx]; this
0x1800072f5  mov     [rsp+14E0h+var_14B8], ecx
0x1800072f9  mov     eax, [rdx+4]
0x1800072fc  mov     [rsp+14E0h+var_14B4], eax
0x180007300  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007305  mov     ebx, eax
0x180007307  mov     dword ptr [rsp+14E0h+var_14C0], r12d
0x18000730c  mov     ecx, r12d
0x18000730f  lea     eax, [r12+8]
0x180007314  cmp     dword ptr [rdx+8], 1
0x180007318  cmovz   ecx, eax
0x18000731b  mov     dword ptr [rsp+14E0h+var_14C0+4], ecx
0x18000731f  lea     ecx, [rax-7]
0x180007322  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000732a  inc     ecx
0x18000732c  mov     [rsp+14E0h+var_14B0], ecx
0x180007330  mov     [rsp+14E0h+var_14A8], r12
0x180007335  call    cs:__imp_GetCurrentThreadId
0x18000733b  mov     [rsp+14E0h+var_14A0], eax
0x18000733f  lea     rax, aShellThemesWal; "shell\\themes\\wallpapertranscodecontai"...
0x180007346  mov     [rsp+14E0h+var_1488], rax
0x18000734b  mov     [rsp+14E0h+var_1480], esi
0x18000734f  mov     [rsp+14E0h+var_147C], ebx
0x180007353  mov     [rsp+14E0h+var_1498], r12
0x180007358  mov     [rsp+14E0h+var_1490], r12
0x18000735d  mov     [rbp+13E0h+var_1438], rdi
0x180007361  mov     [rbp+13E0h+var_1430], r14
0x180007365  mov     [rsp+14E0h+var_1478], r12
0x18000736a  xorps   xmm0, xmm0
0x18000736d  xor     eax, eax
0x18000736f  movups  [rbp+13E0h+var_1458], xmm0
0x180007373  mov     [rbp+13E0h+var_1448], rax
0x180007377  xorps   xmm1, xmm1
0x18000737a  movups  [rsp+14E0h+var_1470], xmm1
0x18000737f  mov     [rbp+13E0h+var_1460], rax
0x180007383  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000738a  test    rax, rax
0x18000738d  jz      short loc_18000739A
0x18000738f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007394  mov     [rbp+13E0h+var_1440], rax
0x180007398  jmp     short loc_18000739E
0x18000739a  mov     [rbp+13E0h+var_1440], r12
0x18000739e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800073a5  test    rax, rax
0x1800073a8  jz      short loc_1800073B4
0x1800073aa  lea     rcx, [rsp+14E0h+var_14C0]
0x1800073af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073b4  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800073bb  test    rax, rax
0x1800073be  jz      short loc_1800073D4
0x1800073c0  mov     r8d, 400h
0x1800073c6  lea     rdx, [rbp+13E0h+var_1420]
0x1800073ca  lea     rcx, [rsp+14E0h+var_14C0]
0x1800073cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073d4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800073db  test    rax, rax
0x1800073de  jz      short loc_1800073EA
0x1800073e0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800073e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073ea  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800073f1  test    rax, rax
0x1800073f4  jz      short loc_18000740C
0x1800073f6  test    r15b, r15b
0x1800073f9  jnz     short loc_18000740C
0x1800073fb  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180007400  jnz     short loc_18000740C
0x180007402  lea     rcx, [rsp+14E0h+var_14C0]
0x180007407  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000740c  cmp     [rsp+14E0h+var_14B8], r12d
0x180007411  jl      short loc_180007419
0x180007413  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180007419  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180007420  jnz     short loc_180007441
0x180007422  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007429  test    rax, rax
0x18000742c  jz      short loc_180007437
0x18000742e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007433  test    al, al
0x180007435  jmp     short loc_18000743F
0x180007437  call    cs:__imp_IsDebuggerPresent
0x18000743d  test    eax, eax
0x18000743f  jz      short loc_18000744A
0x180007441  test    byte ptr [rsp+14E0h+var_14C0+4], 2
0x180007446  mov     bl, 1
0x180007448  jz      short loc_18000744D
0x18000744a  mov     bl, r12b
0x18000744d  test    r15b, r15b
0x180007450  jnz     short loc_18000747C
0x180007452  test    bl, bl
0x180007454  jnz     short loc_18000747C
0x180007456  mov     rax, cs:g_pfnResultLoggingCallback
0x18000745d  test    rax, rax
0x180007460  jz      short loc_1800074D9
0x180007462  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007469  jnz     short loc_1800074D9
0x18000746b  xor     r8d, r8d
0x18000746e  xor     edx, edx
0x180007470  lea     rcx, [rsp+14E0h+var_14C0]
0x180007475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000747a  jmp     short loc_1800074D9
0x18000747c  mov     edi, 800h
0x180007481  mov     rax, cs:g_pfnResultLoggingCallback
0x180007488  test    rax, rax
0x18000748b  jz      short loc_1800074AA
0x18000748d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180007494  jnz     short loc_1800074AA
0x180007496  mov     r8d, edi
0x180007499  lea     rdx, [rbp+13E0h+OutputString]
0x1800074a0  lea     rcx, [rsp+14E0h+var_14C0]
0x1800074a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074aa  cmp     [rbp+13E0h+OutputString], r12w
0x1800074b2  jnz     short loc_1800074C8
0x1800074b4  lea     r8, [rsp+14E0h+var_14C0]; unsigned __int64
0x1800074b9  mov     rdx, rdi; wchar_t *
0x1800074bc  lea     rcx, [rbp+13E0h+OutputString]; this
0x1800074c3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800074c8  test    bl, bl
0x1800074ca  jz      short loc_1800074D9
0x1800074cc  lea     rcx, [rbp+13E0h+OutputString]; lpOutputString
0x1800074d3  call    cs:__imp_OutputDebugStringW
0x1800074d9  test    byte ptr [rsp+14E0h+var_14C0+4], 4
0x1800074de  jnz     short loc_1800074E9
0x1800074e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800074e7  jz      short loc_1800074FB
0x1800074e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800074f0  test    rax, rax
0x1800074f3  jz      short loc_1800074FB
0x1800074f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074fa  nop
0x1800074fb  test    byte ptr [rsp+14E0h+var_14C0+4], 1
0x180007500  jz      short loc_18000750D
0x180007502  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180007507  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000750d  test    r15b, r15b
0x180007510  jz      short loc_18000752A
0x180007512  lea     rdx, [rbp+13E0h+OutputString]
0x180007519  lea     rcx, [rsp+14E0h+var_14C0]
0x18000751e  mov     rax, cs:g_pfnThrowPlatformException
0x180007525  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000752a  lea     rcx, [rsp+14E0h+var_14C0]; this
0x18000752f  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x180007534  lea     rcx, [rsp+14E0h+var_14C0]; this
0x180007539  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
