# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x180003548`
- end: `0x1800037de`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `662`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003028`

## callees

- `0x180003548`
- `0x180004874`
- `0x180005770`
- `0x180006490`
- `0x18000669c`
- `0x18000b612`
- `0x18000b640`
- `0x18000b700`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800035f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800036ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003778`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180003778`

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
  int v9; // ebx
  int v10; // ecx
  __int64 v11; // rdx
  const struct wil::FailureInfo *v12; // rdx
  wil::details::in1diag3 *v13; // rcx
  const struct wil::FailureInfo *v14; // r9
  bool v15; // zf
  int v16; // [rsp+20h] [rbp-E0h] BYREF
  int v17; // [rsp+24h] [rbp-DCh]
  int v18; // [rsp+28h] [rbp-D8h]
  int v19; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v20; // [rsp+30h] [rbp-D0h]
  __int64 v21; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v23; // [rsp+48h] [rbp-B8h]
  __int64 v24; // [rsp+50h] [rbp-B0h]
  const char *v25; // [rsp+58h] [rbp-A8h]
  int v26; // [rsp+60h] [rbp-A0h]
  int v27; // [rsp+64h] [rbp-9Ch]
  __int64 v28; // [rsp+68h] [rbp-98h]
  __int128 v29; // [rsp+70h] [rbp-90h]
  __int64 v30; // [rsp+80h] [rbp-80h]
  __int128 v31; // [rsp+88h] [rbp-78h]
  __int64 v32; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v34; // [rsp+A8h] [rbp-58h]
  __int64 v35; // [rsp+B0h] [rbp-50h]
  char v36[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v16, 0, 0x98u);
  OutputString[0] = 0;
  v36[0] = 0;
  v18 = *a7;
  v19 = a7[1];
  v9 = wil::details::RecordReturn((wil::details *)(unsigned int)v18, (int)a7);
  v16 = 1;
  v10 = 0;
  if ( *(_DWORD *)(v11 + 8) == 1 )
    v10 = 8;
  v17 = v10;
  v20 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v25 = "wil";
  v26 = a2;
  v27 = v9;
  v23 = 0;
  v24 = 0;
  v34 = a6;
  v35 = a1;
  v28 = 0;
  v31 = 0;
  v32 = 0;
  v29 = 0;
  v30 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v13);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v16, v36, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v16);
  if ( wil::details::g_pfnOriginateCallback && (v17 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v16);
  if ( v18 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v13);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v15 = !IsDebuggerPresent())
      : (v15 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v13) == 0),
        v15)
    || (v17 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v16, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v16, v14);
    OutputDebugStringW(OutputString);
  }
  if ( ((v17 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v13);
  if ( (v17 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v16, v12);
}

```

## disassembly

```asm
0x180003548  mov     [rsp-8+arg_10], rbx
0x18000354d  push    rbp
0x18000354e  push    rsi
0x18000354f  push    rdi
0x180003550  push    r14
0x180003552  push    r15
0x180003554  lea     rbp, [rsp-13D0h]
0x18000355c  mov     eax, 14D0h
0x180003561  call    _alloca_probe
0x180003566  sub     rsp, rax
0x180003569  mov     rax, cs:__security_cookie
0x180003570  xor     rax, rsp
0x180003573  mov     [rbp+13F0h+var_30], rax
0x18000357a  mov     esi, edx
0x18000357c  mov     r14, rcx
0x18000357f  mov     rdi, [rbp+13F0h+arg_28]
0x180003586  xor     edx, edx; Val
0x180003588  mov     r8d, 98h; Size
0x18000358e  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x180003593  call    memset_0
0x180003598  nop
0x180003599  xor     r15d, r15d
0x18000359c  mov     [rbp+13F0h+OutputString], r15w
0x1800035a4  mov     [rbp+13F0h+var_1430], r15b
0x1800035a8  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x1800035af  mov     ecx, [rdx]; this
0x1800035b1  mov     [rsp+14F0h+var_14C8], ecx
0x1800035b5  mov     eax, [rdx+4]
0x1800035b8  mov     [rsp+14F0h+var_14C4], eax
0x1800035bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800035c1  mov     ebx, eax
0x1800035c3  mov     dword ptr [rsp+14F0h+var_14D0], 1
0x1800035cb  mov     ecx, r15d
0x1800035ce  lea     eax, [r15+8]
0x1800035d2  cmp     dword ptr [rdx+8], 1
0x1800035d6  cmovz   ecx, eax
0x1800035d9  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x1800035dd  lea     ecx, [rax-7]
0x1800035e0  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800035e8  inc     ecx
0x1800035ea  mov     [rsp+14F0h+var_14C0], ecx
0x1800035ee  mov     [rsp+14F0h+var_14B8], r15
0x1800035f3  call    cs:__imp_GetCurrentThreadId
0x1800035f9  mov     [rsp+14F0h+var_14B0], eax
0x1800035fd  lea     rax, aWil; "wil"
0x180003604  mov     [rsp+14F0h+var_1498], rax
0x180003609  mov     [rsp+14F0h+var_1490], esi
0x18000360d  mov     [rsp+14F0h+var_148C], ebx
0x180003611  mov     [rsp+14F0h+var_14A8], r15
0x180003616  mov     [rsp+14F0h+var_14A0], r15
0x18000361b  mov     [rbp+13F0h+var_1448], rdi
0x18000361f  mov     [rbp+13F0h+var_1440], r14
0x180003623  mov     [rsp+14F0h+var_1488], r15
0x180003628  xorps   xmm0, xmm0
0x18000362b  xor     eax, eax
0x18000362d  movups  [rbp+13F0h+var_1468], xmm0
0x180003631  mov     [rbp+13F0h+var_1458], rax
0x180003635  xorps   xmm1, xmm1
0x180003638  movups  [rsp+14F0h+var_1480], xmm1
0x18000363d  mov     [rbp+13F0h+var_1470], rax
0x180003641  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180003648  test    rax, rax
0x18000364b  jz      short loc_180003658
0x18000364d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003652  mov     [rbp+13F0h+var_1450], rax
0x180003656  jmp     short loc_18000365C
0x180003658  mov     [rbp+13F0h+var_1450], r15
0x18000365c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180003663  test    rax, rax
0x180003666  jz      short loc_180003672
0x180003668  lea     rcx, [rsp+14F0h+var_14D0]
0x18000366d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003672  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180003679  test    rax, rax
0x18000367c  jz      short loc_180003692
0x18000367e  mov     r8d, 400h
0x180003684  lea     rdx, [rbp+13F0h+var_1430]
0x180003688  lea     rcx, [rsp+14F0h+var_14D0]
0x18000368d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003692  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180003699  test    rax, rax
0x18000369c  jz      short loc_1800036A8
0x18000369e  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036a8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800036af  test    rax, rax
0x1800036b2  jz      short loc_1800036C5
0x1800036b4  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800036b9  jnz     short loc_1800036C5
0x1800036bb  lea     rcx, [rsp+14F0h+var_14D0]
0x1800036c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036c5  cmp     [rsp+14F0h+var_14C8], r15d
0x1800036ca  jge     loc_1800037D8
0x1800036d0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r15b; bool wil::g_fIsDebuggerPresent
0x1800036d7  jnz     short loc_1800036F8
0x1800036d9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800036e0  test    rax, rax
0x1800036e3  jz      short loc_1800036EE
0x1800036e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800036ea  test    al, al
0x1800036ec  jmp     short loc_1800036F6
0x1800036ee  call    cs:__imp_IsDebuggerPresent
0x1800036f4  test    eax, eax
0x1800036f6  jz      short loc_1800036FF
0x1800036f8  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x1800036fd  jz      short loc_180003725
0x1800036ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180003706  test    rax, rax
0x180003709  jz      short loc_18000377E
0x18000370b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x180003712  jnz     short loc_18000377E
0x180003714  xor     r8d, r8d
0x180003717  xor     edx, edx
0x180003719  lea     rcx, [rsp+14F0h+var_14D0]
0x18000371e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003723  jmp     short loc_18000377E
0x180003725  mov     ebx, 800h
0x18000372a  mov     rax, cs:g_pfnResultLoggingCallback
0x180003731  test    rax, rax
0x180003734  jz      short loc_180003753
0x180003736  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r15b; bool wil::details::g_resultMessageCallbackSet
0x18000373d  jnz     short loc_180003753
0x18000373f  mov     r8d, ebx
0x180003742  lea     rdx, [rbp+13F0h+OutputString]
0x180003749  lea     rcx, [rsp+14F0h+var_14D0]
0x18000374e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003753  cmp     [rbp+13F0h+OutputString], r15w
0x18000375b  jnz     short loc_180003771
0x18000375d  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x180003762  mov     rdx, rbx; unsigned __int16 *
0x180003765  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000376c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180003771  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x180003778  call    cs:__imp_OutputDebugStringW
0x18000377e  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x180003783  jnz     short loc_18000378E
0x180003785  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r15b; bool wil::g_fBreakOnFailure
0x18000378c  jz      short loc_1800037A0
0x18000378e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180003795  test    rax, rax
0x180003798  jz      short loc_1800037A0
0x18000379a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000379f  nop
0x1800037a0  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x1800037a5  jnz     short loc_1800037CD
0x1800037a7  mov     rcx, [rbp+13F0h+var_30]
0x1800037ae  xor     rcx, rsp; StackCookie
0x1800037b1  call    __security_check_cookie
0x1800037b6  mov     rbx, [rsp+14F0h+arg_10]
0x1800037be  add     rsp, 14D0h
0x1800037c5  pop     r15
0x1800037c7  pop     r14
0x1800037c9  pop     rdi
0x1800037ca  pop     rsi
0x1800037cb  pop     rbp
0x1800037cc  retn
0x1800037cd  lea     rcx, [rsp+14F0h+var_14D0]; this
0x1800037d2  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1800037d8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
