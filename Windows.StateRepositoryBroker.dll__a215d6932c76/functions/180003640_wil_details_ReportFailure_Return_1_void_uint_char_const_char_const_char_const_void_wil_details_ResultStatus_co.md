# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003640`
- end: `0x1800038cd`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003530`

## callees

- `0x180001d60`
- `0x180002900`
- `0x180003640`
- `0x1800049b4`
- `0x180005b88`
- `0x18000674c`
- `0x180006828`
- `0x18000a810`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036ee`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800036ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000386c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000386c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800037e2`

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
  int v10; // ebx
  int v11; // ecx
  __int64 v12; // rdx
  const struct wil::FailureInfo *v13; // rdx
  wil::details::in1diag3 *v14; // rcx
  const struct wil::FailureInfo *v15; // r9
  bool v16; // zf
  int v17; // [rsp+20h] [rbp-E0h] BYREF
  int v18; // [rsp+24h] [rbp-DCh]
  int v19; // [rsp+28h] [rbp-D8h]
  int v20; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v21; // [rsp+30h] [rbp-D0h]
  __int64 v22; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v24; // [rsp+48h] [rbp-B8h]
  __int64 v25; // [rsp+50h] [rbp-B0h]
  __int64 v26; // [rsp+58h] [rbp-A8h]
  int v27; // [rsp+60h] [rbp-A0h]
  int v28; // [rsp+64h] [rbp-9Ch]
  __int64 v29; // [rsp+68h] [rbp-98h]
  __int128 v30; // [rsp+70h] [rbp-90h]
  __int64 v31; // [rsp+80h] [rbp-80h]
  __int128 v32; // [rsp+88h] [rbp-78h]
  __int64 v33; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v35; // [rsp+A8h] [rbp-58h]
  __int64 v36; // [rsp+B0h] [rbp-50h]
  char v37[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v17, 0, 0x98u);
  OutputString[0] = 0;
  v37[0] = 0;
  v19 = *a7;
  v20 = a7[1];
  v10 = wil::details::RecordReturn((wil::details *)(unsigned int)v19, (int)a7);
  v17 = 1;
  v11 = 0;
  if ( *(_DWORD *)(v12 + 8) == 1 )
    v11 = 8;
  v18 = v11;
  v21 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v26 = a3;
  v27 = a2;
  v28 = v10;
  v24 = 0;
  v25 = 0;
  v35 = a6;
  v36 = a1;
  v29 = 0;
  v32 = 0;
  v33 = 0;
  v30 = 0;
  v31 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v14);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v17);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v17, v37, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v17);
  if ( wil::details::g_pfnOriginateCallback && (v18 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v17);
  if ( v19 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v14);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v16 = !IsDebuggerPresent())
      : (v16 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v14) == 0),
        v16)
    || (v18 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v17, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v17, v15);
    OutputDebugStringW(OutputString);
  }
  if ( ((v18 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v14);
  if ( (v18 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v17, v13);
}

```

## disassembly

```asm
0x180003640  push    rbp
0x180003642  push    rbx
0x180003643  push    rsi
0x180003644  push    rdi
0x180003645  push    r12
0x180003647  push    r14
0x180003649  push    r15
0x18000364b  lea     rbp, [rsp-13D0h]
0x180003653  mov     eax, 14D0h
0x180003658  call    _alloca_probe
0x18000365d  sub     rsp, rax
0x180003660  mov     rax, cs:__security_cookie
0x180003667  xor     rax, rsp
0x18000366a  mov     [rbp+1400h+var_40], rax
0x180003671  mov     r14, r8
0x180003674  mov     esi, edx
0x180003676  mov     r15, rcx
0x180003679  mov     rdi, [rbp+1400h+arg_28]
0x180003680  xor     edx, edx; Val
0x180003682  mov     r8d, 98h; Size
0x180003688  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000368d  call    memset_0
0x180003692  nop
0x180003693  xor     r12d, r12d
0x180003696  mov     [rbp+1400h+OutputString], r12w
0x18000369e  mov     [rbp+1400h+var_1440], r12b
0x1800036a2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1800036a9  mov     ecx, [rdx]; this
0x1800036ab  mov     [rsp+1500h+var_14D8], ecx
0x1800036af  mov     eax, [rdx+4]
0x1800036b2  mov     [rsp+1500h+var_14D4], eax
0x1800036b6  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800036bb  mov     ebx, eax
0x1800036bd  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1800036c5  mov     ecx, r12d
0x1800036c8  lea     eax, [r12+8]
0x1800036cd  cmp     dword ptr [rdx+8], 1
0x1800036d1  cmovz   ecx, eax
0x1800036d4  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1800036d8  lea     ecx, [rax-7]
0x1800036db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800036e3  inc     ecx
0x1800036e5  mov     [rsp+1500h+var_14D0], ecx
0x1800036e9  mov     [rsp+1500h+var_14C8], r12
0x1800036ee  call    cs:__imp_GetCurrentThreadId
0x1800036f4  mov     [rsp+1500h+var_14C0], eax
0x1800036f8  mov     [rsp+1500h+var_14A8], r14
0x1800036fd  mov     [rsp+1500h+var_14A0], esi
0x180003701  mov     [rsp+1500h+var_149C], ebx
0x180003705  mov     [rsp+1500h+var_14B8], r12
0x18000370a  mov     [rsp+1500h+var_14B0], r12
0x18000370f  mov     [rbp+1400h+var_1458], rdi
0x180003713  mov     [rbp+1400h+var_1450], r15
0x180003717  mov     [rsp+1500h+var_1498], r12
0x18000371c  xorps   xmm0, xmm0
0x18000371f  xor     eax, eax
0x180003721  movups  [rbp+1400h+var_1478], xmm0
0x180003725  mov     [rbp+1400h+var_1468], rax
0x180003729  xorps   xmm1, xmm1
0x18000372c  movups  [rsp+1500h+var_1490], xmm1
0x180003731  mov     [rbp+1400h+var_1480], rax
0x180003735  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000373c  test    rax, rax
0x18000373f  jz      short loc_18000374C
0x180003741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003746  mov     [rbp+1400h+var_1460], rax
0x18000374a  jmp     short loc_180003750
0x18000374c  mov     [rbp+1400h+var_1460], r12
0x180003750  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003757  test    rax, rax
0x18000375a  jz      short loc_180003766
0x18000375c  lea     rcx, [rsp+1500h+var_14E0]
0x180003761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003766  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000376d  test    rax, rax
0x180003770  jz      short loc_180003786
0x180003772  mov     r8d, 400h
0x180003778  lea     rdx, [rbp+1400h+var_1440]
0x18000377c  lea     rcx, [rsp+1500h+var_14E0]
0x180003781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003786  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000378d  test    rax, rax
0x180003790  jz      short loc_18000379C
0x180003792  lea     rcx, [rsp+1500h+var_14E0]
0x180003797  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000379c  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800037a3  test    rax, rax
0x1800037a6  jz      short loc_1800037B9
0x1800037a8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800037ad  jnz     short loc_1800037B9
0x1800037af  lea     rcx, [rsp+1500h+var_14E0]
0x1800037b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037b9  cmp     [rsp+1500h+var_14D8], r12d
0x1800037be  jge     loc_1800038C7
0x1800037c4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1800037cb  jnz     short loc_1800037EC
0x1800037cd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800037d4  test    rax, rax
0x1800037d7  jz      short loc_1800037E2
0x1800037d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037de  test    al, al
0x1800037e0  jmp     short loc_1800037EA
0x1800037e2  call    cs:__imp_IsDebuggerPresent
0x1800037e8  test    eax, eax
0x1800037ea  jz      short loc_1800037F3
0x1800037ec  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800037f1  jz      short loc_180003819
0x1800037f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800037fa  test    rax, rax
0x1800037fd  jz      short loc_180003872
0x1800037ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003806  jnz     short loc_180003872
0x180003808  xor     r8d, r8d
0x18000380b  xor     edx, edx
0x18000380d  lea     rcx, [rsp+1500h+var_14E0]
0x180003812  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003817  jmp     short loc_180003872
0x180003819  mov     ebx, 800h
0x18000381e  mov     rax, cs:g_pfnResultLoggingCallback
0x180003825  test    rax, rax
0x180003828  jz      short loc_180003847
0x18000382a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180003831  jnz     short loc_180003847
0x180003833  mov     r8d, ebx
0x180003836  lea     rdx, [rbp+1400h+OutputString]
0x18000383d  lea     rcx, [rsp+1500h+var_14E0]
0x180003842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003847  cmp     [rbp+1400h+OutputString], r12w
0x18000384f  jnz     short loc_180003865
0x180003851  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180003856  mov     rdx, rbx; unsigned __int16 *
0x180003859  lea     rcx, [rbp+1400h+OutputString]; this
0x180003860  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003865  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x18000386c  call    cs:__imp_OutputDebugStringW
0x180003872  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180003877  jnz     short loc_180003882
0x180003879  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180003880  jz      short loc_180003894
0x180003882  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003889  test    rax, rax
0x18000388c  jz      short loc_180003894
0x18000388e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003893  nop
0x180003894  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180003899  jnz     short loc_1800038BC
0x18000389b  mov     rcx, [rbp+1400h+var_40]
0x1800038a2  xor     rcx, rsp; StackCookie
0x1800038a5  call    __security_check_cookie
0x1800038aa  add     rsp, 14D0h
0x1800038b1  pop     r15
0x1800038b3  pop     r14
0x1800038b5  pop     r12
0x1800038b7  pop     rdi
0x1800038b8  pop     rsi
0x1800038b9  pop     rbx
0x1800038ba  pop     rbp
0x1800038bb  retn
0x1800038bc  lea     rcx, [rsp+1500h+var_14E0]; this
0x1800038c1  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800038c7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
