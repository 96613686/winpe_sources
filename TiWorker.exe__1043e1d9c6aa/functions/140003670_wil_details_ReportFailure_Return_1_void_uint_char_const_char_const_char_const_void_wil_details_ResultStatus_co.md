# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003670`
- end: `0x1400038fb`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140003330`

## callees

- `0x140002310`
- `0x140002cf8`
- `0x140003670`
- `0x140004294`
- `0x140005310`
- `0x140005b98`
- `0x140005cc8`
- `0x14002ac80`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000371d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000371d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000389b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000389b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003811`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003811`

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
  int v10; // eax
  int v11; // eax
  __int64 v12; // rdx
  int v13; // ebx
  int v14; // ecx
  DWORD CurrentThreadId; // eax
  const struct wil::FailureInfo *v16; // rdx
  wil::details::in1diag3 *v17; // rcx
  const struct wil::FailureInfo *v18; // r9
  bool v19; // zf
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD v26; // [rsp+40h] [rbp-C0h]
  __int64 v27; // [rsp+48h] [rbp-B8h]
  __int64 v28; // [rsp+50h] [rbp-B0h]
  __int64 v29; // [rsp+58h] [rbp-A8h]
  int v30; // [rsp+60h] [rbp-A0h]
  int v31; // [rsp+64h] [rbp-9Ch]
  __int64 v32; // [rsp+68h] [rbp-98h]
  __int128 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+80h] [rbp-80h]
  __int128 v35; // [rsp+88h] [rbp-78h]
  __int64 v36; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v38; // [rsp+A8h] [rbp-58h]
  __int64 v39; // [rsp+B0h] [rbp-50h]
  char v40[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v10 = a7[1];
  v22 = *a7;
  v23 = v10;
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v22, (int)a7);
  v19 = *(_DWORD *)(v12 + 8) == 1;
  v13 = v11;
  v20 = 1;
  v14 = 0;
  if ( v19 )
    v14 = 8;
  v21 = v14;
  v25 = 0;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v26 = CurrentThreadId;
  v30 = a2;
  v36 = 0;
  v34 = 0;
  v31 = v13;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v33 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v17);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v17);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v19 = !IsDebuggerPresent())
      : (v19 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v17) == 0),
        v19)
    || (v21 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (wchar_t *)0x800, (unsigned __int64)&v20, v18);
    OutputDebugStringW(OutputString);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v17);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v16);
}

```

## disassembly

```asm
0x140003670  push    rbp
0x140003672  push    rbx
0x140003673  push    rsi
0x140003674  push    rdi
0x140003675  push    r12
0x140003677  push    r14
0x140003679  push    r15
0x14000367b  lea     rbp, [rsp-13D0h]
0x140003683  mov     eax, 14D0h
0x140003688  call    _alloca_probe
0x14000368d  sub     rsp, rax
0x140003690  mov     rax, cs:__security_cookie
0x140003697  xor     rax, rsp
0x14000369a  mov     [rbp+1400h+var_40], rax
0x1400036a1  mov     rdi, [rbp+1400h+arg_28]
0x1400036a8  mov     r14, r8
0x1400036ab  mov     esi, edx
0x1400036ad  mov     r15, rcx
0x1400036b0  xor     edx, edx; Val
0x1400036b2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400036b7  mov     r8d, 98h; Size
0x1400036bd  call    memset_0
0x1400036c2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400036c9  xor     r12d, r12d
0x1400036cc  mov     [rbp+1400h+OutputString], r12w
0x1400036d4  mov     [rbp+1400h+var_1440], r12b
0x1400036d8  mov     ecx, [rdx]; this
0x1400036da  mov     eax, [rdx+4]
0x1400036dd  mov     [rsp+1500h+var_14D8], ecx
0x1400036e1  mov     [rsp+1500h+var_14D4], eax
0x1400036e5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400036ea  cmp     dword ptr [rdx+8], 1
0x1400036ee  mov     ebx, eax
0x1400036f0  lea     eax, [r12+8]
0x1400036f5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400036fd  mov     ecx, r12d
0x140003700  cmovz   ecx, eax
0x140003703  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x140003707  lea     ecx, [rax-7]
0x14000370a  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003712  inc     ecx
0x140003714  mov     [rsp+1500h+var_14C8], r12
0x140003719  mov     [rsp+1500h+var_14D0], ecx
0x14000371d  call    cs:__imp_GetCurrentThreadId
0x140003723  xorps   xmm0, xmm0
0x140003726  mov     [rsp+1500h+var_14A8], r14
0x14000372b  mov     [rsp+1500h+var_14C0], eax
0x14000372f  xorps   xmm1, xmm1
0x140003732  xor     eax, eax
0x140003734  mov     [rsp+1500h+var_14A0], esi
0x140003738  mov     [rbp+1400h+var_1468], rax
0x14000373c  mov     [rbp+1400h+var_1480], rax
0x140003740  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003747  mov     [rsp+1500h+var_149C], ebx
0x14000374b  mov     [rsp+1500h+var_14B8], r12
0x140003750  mov     [rsp+1500h+var_14B0], r12
0x140003755  mov     [rbp+1400h+var_1458], rdi
0x140003759  mov     [rbp+1400h+var_1450], r15
0x14000375d  mov     [rsp+1500h+var_1498], r12
0x140003762  movups  [rbp+1400h+var_1478], xmm0
0x140003766  movups  [rsp+1500h+var_1490], xmm1
0x14000376b  test    rax, rax
0x14000376e  jz      short loc_14000377B
0x140003770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003775  mov     [rbp+1400h+var_1460], rax
0x140003779  jmp     short loc_14000377F
0x14000377b  mov     [rbp+1400h+var_1460], r12
0x14000377f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003786  test    rax, rax
0x140003789  jz      short loc_140003795
0x14000378b  lea     rcx, [rsp+1500h+var_14E0]
0x140003790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003795  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000379c  test    rax, rax
0x14000379f  jz      short loc_1400037B5
0x1400037a1  mov     r8d, 400h
0x1400037a7  lea     rdx, [rbp+1400h+var_1440]
0x1400037ab  lea     rcx, [rsp+1500h+var_14E0]
0x1400037b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037b5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400037bc  test    rax, rax
0x1400037bf  jz      short loc_1400037CB
0x1400037c1  lea     rcx, [rsp+1500h+var_14E0]
0x1400037c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400037d2  test    rax, rax
0x1400037d5  jz      short loc_1400037E8
0x1400037d7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400037dc  jnz     short loc_1400037E8
0x1400037de  lea     rcx, [rsp+1500h+var_14E0]
0x1400037e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400037e8  cmp     [rsp+1500h+var_14D8], r12d
0x1400037ed  jge     loc_1400038EA
0x1400037f3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400037fa  jnz     short loc_14000381B
0x1400037fc  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003803  test    rax, rax
0x140003806  jz      short loc_140003811
0x140003808  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000380d  test    al, al
0x14000380f  jmp     short loc_140003819
0x140003811  call    cs:__imp_IsDebuggerPresent
0x140003817  test    eax, eax
0x140003819  jz      short loc_140003822
0x14000381b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003820  jz      short loc_140003848
0x140003822  mov     rax, cs:g_pfnResultLoggingCallback
0x140003829  test    rax, rax
0x14000382c  jz      short loc_1400038A1
0x14000382e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003835  jnz     short loc_1400038A1
0x140003837  xor     r8d, r8d
0x14000383a  lea     rcx, [rsp+1500h+var_14E0]
0x14000383f  xor     edx, edx
0x140003841  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003846  jmp     short loc_1400038A1
0x140003848  mov     rax, cs:g_pfnResultLoggingCallback
0x14000384f  mov     ebx, 800h
0x140003854  test    rax, rax
0x140003857  jz      short loc_140003876
0x140003859  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003860  jnz     short loc_140003876
0x140003862  mov     r8d, ebx
0x140003865  lea     rdx, [rbp+1400h+OutputString]
0x14000386c  lea     rcx, [rsp+1500h+var_14E0]
0x140003871  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003876  cmp     [rbp+1400h+OutputString], r12w
0x14000387e  jnz     short loc_140003894
0x140003880  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003885  mov     rdx, rbx; wchar_t *
0x140003888  lea     rcx, [rbp+1400h+OutputString]; this
0x14000388f  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140003894  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000389b  call    cs:__imp_OutputDebugStringW
0x1400038a1  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400038a6  jnz     short loc_1400038B1
0x1400038a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400038af  jz      short loc_1400038C2
0x1400038b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400038b8  test    rax, rax
0x1400038bb  jz      short loc_1400038C2
0x1400038bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038c2  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400038c7  jnz     short loc_1400038F0
0x1400038c9  mov     rcx, [rbp+1400h+var_40]
0x1400038d0  xor     rcx, rsp; StackCookie
0x1400038d3  call    __security_check_cookie
0x1400038d8  add     rsp, 14D0h
0x1400038df  pop     r15
0x1400038e1  pop     r14
0x1400038e3  pop     r12
0x1400038e5  pop     rdi
0x1400038e6  pop     rsi
0x1400038e7  pop     rbx
0x1400038e8  pop     rbp
0x1400038e9  retn
0x1400038ea  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400038f0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400038f5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
