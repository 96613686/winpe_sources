# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,wchar_t const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140003760`
- end: `0x1400039eb`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEB_WW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `651`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1400033f4`

## callees

- `0x1400023e0`
- `0x140002de4`
- `0x140003760`
- `0x140004384`
- `0x140005400`
- `0x140005c98`
- `0x140005dc8`
- `0x14002a8e0`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000380d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000380d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000398b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000398b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003901`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003901`

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
0x140003760  push    rbp
0x140003762  push    rbx
0x140003763  push    rsi
0x140003764  push    rdi
0x140003765  push    r12
0x140003767  push    r14
0x140003769  push    r15
0x14000376b  lea     rbp, [rsp-13D0h]
0x140003773  mov     eax, 14D0h
0x140003778  call    _alloca_probe
0x14000377d  sub     rsp, rax
0x140003780  mov     rax, cs:__security_cookie
0x140003787  xor     rax, rsp
0x14000378a  mov     [rbp+1400h+var_40], rax
0x140003791  mov     rdi, [rbp+1400h+arg_28]
0x140003798  mov     r14, r8
0x14000379b  mov     esi, edx
0x14000379d  mov     r15, rcx
0x1400037a0  xor     edx, edx; Val
0x1400037a2  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400037a7  mov     r8d, 98h; Size
0x1400037ad  call    memset_0
0x1400037b2  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400037b9  xor     r12d, r12d
0x1400037bc  mov     [rbp+1400h+OutputString], r12w
0x1400037c4  mov     [rbp+1400h+var_1440], r12b
0x1400037c8  mov     ecx, [rdx]; this
0x1400037ca  mov     eax, [rdx+4]
0x1400037cd  mov     [rsp+1500h+var_14D8], ecx
0x1400037d1  mov     [rsp+1500h+var_14D4], eax
0x1400037d5  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400037da  cmp     dword ptr [rdx+8], 1
0x1400037de  mov     ebx, eax
0x1400037e0  lea     eax, [r12+8]
0x1400037e5  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400037ed  mov     ecx, r12d
0x1400037f0  cmovz   ecx, eax
0x1400037f3  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400037f7  lea     ecx, [rax-7]
0x1400037fa  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003802  inc     ecx
0x140003804  mov     [rsp+1500h+var_14C8], r12
0x140003809  mov     [rsp+1500h+var_14D0], ecx
0x14000380d  call    cs:__imp_GetCurrentThreadId
0x140003813  xorps   xmm0, xmm0
0x140003816  mov     [rsp+1500h+var_14A8], r14
0x14000381b  mov     [rsp+1500h+var_14C0], eax
0x14000381f  xorps   xmm1, xmm1
0x140003822  xor     eax, eax
0x140003824  mov     [rsp+1500h+var_14A0], esi
0x140003828  mov     [rbp+1400h+var_1468], rax
0x14000382c  mov     [rbp+1400h+var_1480], rax
0x140003830  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003837  mov     [rsp+1500h+var_149C], ebx
0x14000383b  mov     [rsp+1500h+var_14B8], r12
0x140003840  mov     [rsp+1500h+var_14B0], r12
0x140003845  mov     [rbp+1400h+var_1458], rdi
0x140003849  mov     [rbp+1400h+var_1450], r15
0x14000384d  mov     [rsp+1500h+var_1498], r12
0x140003852  movups  [rbp+1400h+var_1478], xmm0
0x140003856  movups  [rsp+1500h+var_1490], xmm1
0x14000385b  test    rax, rax
0x14000385e  jz      short loc_14000386B
0x140003860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003865  mov     [rbp+1400h+var_1460], rax
0x140003869  jmp     short loc_14000386F
0x14000386b  mov     [rbp+1400h+var_1460], r12
0x14000386f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003876  test    rax, rax
0x140003879  jz      short loc_140003885
0x14000387b  lea     rcx, [rsp+1500h+var_14E0]
0x140003880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003885  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000388c  test    rax, rax
0x14000388f  jz      short loc_1400038A5
0x140003891  mov     r8d, 400h
0x140003897  lea     rdx, [rbp+1400h+var_1440]
0x14000389b  lea     rcx, [rsp+1500h+var_14E0]
0x1400038a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038a5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400038ac  test    rax, rax
0x1400038af  jz      short loc_1400038BB
0x1400038b1  lea     rcx, [rsp+1500h+var_14E0]
0x1400038b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400038c2  test    rax, rax
0x1400038c5  jz      short loc_1400038D8
0x1400038c7  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400038cc  jnz     short loc_1400038D8
0x1400038ce  lea     rcx, [rsp+1500h+var_14E0]
0x1400038d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038d8  cmp     [rsp+1500h+var_14D8], r12d
0x1400038dd  jge     loc_1400039DA
0x1400038e3  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400038ea  jnz     short loc_14000390B
0x1400038ec  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400038f3  test    rax, rax
0x1400038f6  jz      short loc_140003901
0x1400038f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038fd  test    al, al
0x1400038ff  jmp     short loc_140003909
0x140003901  call    cs:__imp_IsDebuggerPresent
0x140003907  test    eax, eax
0x140003909  jz      short loc_140003912
0x14000390b  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140003910  jz      short loc_140003938
0x140003912  mov     rax, cs:g_pfnResultLoggingCallback
0x140003919  test    rax, rax
0x14000391c  jz      short loc_140003991
0x14000391e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003925  jnz     short loc_140003991
0x140003927  xor     r8d, r8d
0x14000392a  lea     rcx, [rsp+1500h+var_14E0]
0x14000392f  xor     edx, edx
0x140003931  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003936  jmp     short loc_140003991
0x140003938  mov     rax, cs:g_pfnResultLoggingCallback
0x14000393f  mov     ebx, 800h
0x140003944  test    rax, rax
0x140003947  jz      short loc_140003966
0x140003949  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140003950  jnz     short loc_140003966
0x140003952  mov     r8d, ebx
0x140003955  lea     rdx, [rbp+1400h+OutputString]
0x14000395c  lea     rcx, [rsp+1500h+var_14E0]
0x140003961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003966  cmp     [rbp+1400h+OutputString], r12w
0x14000396e  jnz     short loc_140003984
0x140003970  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x140003975  mov     rdx, rbx; wchar_t *
0x140003978  lea     rcx, [rbp+1400h+OutputString]; this
0x14000397f  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140003984  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x14000398b  call    cs:__imp_OutputDebugStringW
0x140003991  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x140003996  jnz     short loc_1400039A1
0x140003998  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x14000399f  jz      short loc_1400039B2
0x1400039a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400039a8  test    rax, rax
0x1400039ab  jz      short loc_1400039B2
0x1400039ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039b2  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400039b7  jnz     short loc_1400039E0
0x1400039b9  mov     rcx, [rbp+1400h+var_40]
0x1400039c0  xor     rcx, rsp; StackCookie
0x1400039c3  call    __security_check_cookie
0x1400039c8  add     rsp, 14D0h
0x1400039cf  pop     r15
0x1400039d1  pop     r14
0x1400039d3  pop     r12
0x1400039d5  pop     rdi
0x1400039d6  pop     rsi
0x1400039d7  pop     rbx
0x1400039d8  pop     rbp
0x1400039d9  retn
0x1400039da  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1400039e0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400039e5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
