# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800035b4`
- end: `0x180003841`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003094`

## callees

- `0x180002470`
- `0x180002ff8`
- `0x1800035b4`
- `0x180005954`
- `0x180006e00`
- `0x180008f10`
- `0x180009004`
- `0x180014020`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003662`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180003662`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800037e0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800037e0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003756`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180003756`

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
0x1800035b4  push    rbp
0x1800035b6  push    rbx
0x1800035b7  push    rsi
0x1800035b8  push    rdi
0x1800035b9  push    r12
0x1800035bb  push    r14
0x1800035bd  push    r15
0x1800035bf  lea     rbp, [rsp-13D0h]
0x1800035c7  mov     eax, 14D0h
0x1800035cc  call    _alloca_probe
0x1800035d1  sub     rsp, rax
0x1800035d4  mov     rax, cs:__security_cookie
0x1800035db  xor     rax, rsp
0x1800035de  mov     [rbp+1400h+var_40], rax
0x1800035e5  mov     r14, r8
0x1800035e8  mov     esi, edx
0x1800035ea  mov     r15, rcx
0x1800035ed  mov     rdi, [rbp+1400h+arg_28]
0x1800035f4  xor     edx, edx; Val
0x1800035f6  mov     r8d, 98h; Size
0x1800035fc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180003601  call    memset_0
0x180003606  nop
0x180003607  xor     r12d, r12d
0x18000360a  mov     [rbp+1400h+OutputString], r12w
0x180003612  mov     [rbp+1400h+var_1440], r12b
0x180003616  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18000361d  mov     ecx, [rdx]; this
0x18000361f  mov     [rsp+1500h+var_14D8], ecx
0x180003623  mov     eax, [rdx+4]
0x180003626  mov     [rsp+1500h+var_14D4], eax
0x18000362a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000362f  mov     ebx, eax
0x180003631  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180003639  mov     ecx, r12d
0x18000363c  lea     eax, [r12+8]
0x180003641  cmp     dword ptr [rdx+8], 1
0x180003645  cmovz   ecx, eax
0x180003648  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000364c  lea     ecx, [rax-7]
0x18000364f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180003657  inc     ecx
0x180003659  mov     [rsp+1500h+var_14D0], ecx
0x18000365d  mov     [rsp+1500h+var_14C8], r12
0x180003662  call    cs:__imp_GetCurrentThreadId
0x180003668  mov     [rsp+1500h+var_14C0], eax
0x18000366c  mov     [rsp+1500h+var_14A8], r14
0x180003671  mov     [rsp+1500h+var_14A0], esi
0x180003675  mov     [rsp+1500h+var_149C], ebx
0x180003679  mov     [rsp+1500h+var_14B8], r12
0x18000367e  mov     [rsp+1500h+var_14B0], r12
0x180003683  mov     [rbp+1400h+var_1458], rdi
0x180003687  mov     [rbp+1400h+var_1450], r15
0x18000368b  mov     [rsp+1500h+var_1498], r12
0x180003690  xorps   xmm0, xmm0
0x180003693  xor     eax, eax
0x180003695  movups  [rbp+1400h+var_1478], xmm0
0x180003699  mov     [rbp+1400h+var_1468], rax
0x18000369d  xorps   xmm1, xmm1
0x1800036a0  movups  [rsp+1500h+var_1490], xmm1
0x1800036a5  mov     [rbp+1400h+var_1480], rax
0x1800036a9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800036b0  test    rax, rax
0x1800036b3  jz      short loc_1800036C0
0x1800036b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ba  mov     [rbp+1400h+var_1460], rax
0x1800036be  jmp     short loc_1800036C4
0x1800036c0  mov     [rbp+1400h+var_1460], r12
0x1800036c4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800036cb  test    rax, rax
0x1800036ce  jz      short loc_1800036DA
0x1800036d0  lea     rcx, [rsp+1500h+var_14E0]
0x1800036d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036da  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800036e1  test    rax, rax
0x1800036e4  jz      short loc_1800036FA
0x1800036e6  mov     r8d, 400h
0x1800036ec  lea     rdx, [rbp+1400h+var_1440]
0x1800036f0  lea     rcx, [rsp+1500h+var_14E0]
0x1800036f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036fa  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003701  test    rax, rax
0x180003704  jz      short loc_180003710
0x180003706  lea     rcx, [rsp+1500h+var_14E0]
0x18000370b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003710  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003717  test    rax, rax
0x18000371a  jz      short loc_18000372D
0x18000371c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003721  jnz     short loc_18000372D
0x180003723  lea     rcx, [rsp+1500h+var_14E0]
0x180003728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000372d  cmp     [rsp+1500h+var_14D8], r12d
0x180003732  jge     loc_18000383B
0x180003738  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18000373f  jnz     short loc_180003760
0x180003741  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180003748  test    rax, rax
0x18000374b  jz      short loc_180003756
0x18000374d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003752  test    al, al
0x180003754  jmp     short loc_18000375E
0x180003756  call    cs:__imp_IsDebuggerPresent
0x18000375c  test    eax, eax
0x18000375e  jz      short loc_180003767
0x180003760  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180003765  jz      short loc_18000378D
0x180003767  mov     rax, cs:g_pfnResultLoggingCallback
0x18000376e  test    rax, rax
0x180003771  jz      short loc_1800037E6
0x180003773  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000377a  jnz     short loc_1800037E6
0x18000377c  xor     r8d, r8d
0x18000377f  xor     edx, edx
0x180003781  lea     rcx, [rsp+1500h+var_14E0]
0x180003786  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000378b  jmp     short loc_1800037E6
0x18000378d  mov     ebx, 800h
0x180003792  mov     rax, cs:g_pfnResultLoggingCallback
0x180003799  test    rax, rax
0x18000379c  jz      short loc_1800037BB
0x18000379e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800037a5  jnz     short loc_1800037BB
0x1800037a7  mov     r8d, ebx
0x1800037aa  lea     rdx, [rbp+1400h+OutputString]
0x1800037b1  lea     rcx, [rsp+1500h+var_14E0]
0x1800037b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800037bb  cmp     [rbp+1400h+OutputString], r12w
0x1800037c3  jnz     short loc_1800037D9
0x1800037c5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800037ca  mov     rdx, rbx; unsigned __int16 *
0x1800037cd  lea     rcx, [rbp+1400h+OutputString]; this
0x1800037d4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800037d9  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800037e0  call    cs:__imp_OutputDebugStringW
0x1800037e6  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800037eb  jnz     short loc_1800037F6
0x1800037ed  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800037f4  jz      short loc_180003808
0x1800037f6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800037fd  test    rax, rax
0x180003800  jz      short loc_180003808
0x180003802  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003807  nop
0x180003808  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18000380d  jnz     short loc_180003830
0x18000380f  mov     rcx, [rbp+1400h+var_40]
0x180003816  xor     rcx, rsp; StackCookie
0x180003819  call    __security_check_cookie
0x18000381e  add     rsp, 14D0h
0x180003825  pop     r15
0x180003827  pop     r14
0x180003829  pop     r12
0x18000382b  pop     rdi
0x18000382c  pop     rsi
0x18000382d  pop     rbx
0x18000382e  pop     rbp
0x18000382f  retn
0x180003830  lea     rcx, [rsp+1500h+var_14E0]; this
0x180003835  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000383b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
