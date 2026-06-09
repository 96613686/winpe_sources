# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800275e4`
- end: `0x180027871`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800270bc`

## callees

- `0x1800268ef`
- `0x1800275e4`
- `0x18002a784`
- `0x18002c8e8`
- `0x18002f900`
- `0x18002febc`
- `0x1800350e0`
- `0x1800351a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027692`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180027692`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027786`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180027786`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027810`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180027810`

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
0x1800275e4  push    rbp
0x1800275e6  push    rbx
0x1800275e7  push    rsi
0x1800275e8  push    rdi
0x1800275e9  push    r12
0x1800275eb  push    r14
0x1800275ed  push    r15
0x1800275ef  lea     rbp, [rsp-13D0h]
0x1800275f7  mov     eax, 14D0h
0x1800275fc  call    _alloca_probe
0x180027601  sub     rsp, rax
0x180027604  mov     rax, cs:__security_cookie
0x18002760b  xor     rax, rsp
0x18002760e  mov     [rbp+1400h+var_40], rax
0x180027615  mov     r14, r8
0x180027618  mov     esi, edx
0x18002761a  mov     r15, rcx
0x18002761d  mov     rdi, [rbp+1400h+arg_28]
0x180027624  xor     edx, edx; Val
0x180027626  mov     r8d, 98h; Size
0x18002762c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180027631  call    memset_0
0x180027636  nop
0x180027637  xor     r12d, r12d
0x18002763a  mov     [rbp+1400h+OutputString], r12w
0x180027642  mov     [rbp+1400h+var_1440], r12b
0x180027646  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x18002764d  mov     ecx, [rdx]; this
0x18002764f  mov     [rsp+1500h+var_14D8], ecx
0x180027653  mov     eax, [rdx+4]
0x180027656  mov     [rsp+1500h+var_14D4], eax
0x18002765a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002765f  mov     ebx, eax
0x180027661  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180027669  mov     ecx, r12d
0x18002766c  lea     eax, [r12+8]
0x180027671  cmp     dword ptr [rdx+8], 1
0x180027675  cmovz   ecx, eax
0x180027678  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18002767c  lea     ecx, [rax-7]
0x18002767f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027687  inc     ecx
0x180027689  mov     [rsp+1500h+var_14D0], ecx
0x18002768d  mov     [rsp+1500h+var_14C8], r12
0x180027692  call    cs:__imp_GetCurrentThreadId
0x180027698  mov     [rsp+1500h+var_14C0], eax
0x18002769c  mov     [rsp+1500h+var_14A8], r14
0x1800276a1  mov     [rsp+1500h+var_14A0], esi
0x1800276a5  mov     [rsp+1500h+var_149C], ebx
0x1800276a9  mov     [rsp+1500h+var_14B8], r12
0x1800276ae  mov     [rsp+1500h+var_14B0], r12
0x1800276b3  mov     [rbp+1400h+var_1458], rdi
0x1800276b7  mov     [rbp+1400h+var_1450], r15
0x1800276bb  mov     [rsp+1500h+var_1498], r12
0x1800276c0  xorps   xmm0, xmm0
0x1800276c3  xor     eax, eax
0x1800276c5  movups  [rbp+1400h+var_1478], xmm0
0x1800276c9  mov     [rbp+1400h+var_1468], rax
0x1800276cd  xorps   xmm1, xmm1
0x1800276d0  movups  [rsp+1500h+var_1490], xmm1
0x1800276d5  mov     [rbp+1400h+var_1480], rax
0x1800276d9  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800276e0  test    rax, rax
0x1800276e3  jz      short loc_1800276F0
0x1800276e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800276ea  mov     [rbp+1400h+var_1460], rax
0x1800276ee  jmp     short loc_1800276F4
0x1800276f0  mov     [rbp+1400h+var_1460], r12
0x1800276f4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800276fb  test    rax, rax
0x1800276fe  jz      short loc_18002770A
0x180027700  lea     rcx, [rsp+1500h+var_14E0]
0x180027705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002770a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180027711  test    rax, rax
0x180027714  jz      short loc_18002772A
0x180027716  mov     r8d, 400h
0x18002771c  lea     rdx, [rbp+1400h+var_1440]
0x180027720  lea     rcx, [rsp+1500h+var_14E0]
0x180027725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002772a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027731  test    rax, rax
0x180027734  jz      short loc_180027740
0x180027736  lea     rcx, [rsp+1500h+var_14E0]
0x18002773b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027740  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180027747  test    rax, rax
0x18002774a  jz      short loc_18002775D
0x18002774c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180027751  jnz     short loc_18002775D
0x180027753  lea     rcx, [rsp+1500h+var_14E0]
0x180027758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002775d  cmp     [rsp+1500h+var_14D8], r12d
0x180027762  jge     loc_18002786B
0x180027768  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x18002776f  jnz     short loc_180027790
0x180027771  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180027778  test    rax, rax
0x18002777b  jz      short loc_180027786
0x18002777d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027782  test    al, al
0x180027784  jmp     short loc_18002778E
0x180027786  call    cs:__imp_IsDebuggerPresent
0x18002778c  test    eax, eax
0x18002778e  jz      short loc_180027797
0x180027790  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180027795  jz      short loc_1800277BD
0x180027797  mov     rax, cs:g_pfnResultLoggingCallback
0x18002779e  test    rax, rax
0x1800277a1  jz      short loc_180027816
0x1800277a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800277aa  jnz     short loc_180027816
0x1800277ac  xor     r8d, r8d
0x1800277af  xor     edx, edx
0x1800277b1  lea     rcx, [rsp+1500h+var_14E0]
0x1800277b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277bb  jmp     short loc_180027816
0x1800277bd  mov     ebx, 800h
0x1800277c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800277c9  test    rax, rax
0x1800277cc  jz      short loc_1800277EB
0x1800277ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800277d5  jnz     short loc_1800277EB
0x1800277d7  mov     r8d, ebx
0x1800277da  lea     rdx, [rbp+1400h+OutputString]
0x1800277e1  lea     rcx, [rsp+1500h+var_14E0]
0x1800277e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800277eb  cmp     [rbp+1400h+OutputString], r12w
0x1800277f3  jnz     short loc_180027809
0x1800277f5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800277fa  mov     rdx, rbx; unsigned __int16 *
0x1800277fd  lea     rcx, [rbp+1400h+OutputString]; this
0x180027804  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180027809  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180027810  call    cs:__imp_OutputDebugStringW
0x180027816  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18002781b  jnz     short loc_180027826
0x18002781d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180027824  jz      short loc_180027838
0x180027826  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002782d  test    rax, rax
0x180027830  jz      short loc_180027838
0x180027832  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180027837  nop
0x180027838  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x18002783d  jnz     short loc_180027860
0x18002783f  mov     rcx, [rbp+1400h+var_40]
0x180027846  xor     rcx, rsp; StackCookie
0x180027849  call    __security_check_cookie
0x18002784e  add     rsp, 14D0h
0x180027855  pop     r15
0x180027857  pop     r14
0x180027859  pop     r12
0x18002785b  pop     rdi
0x18002785c  pop     rsi
0x18002785d  pop     rbx
0x18002785e  pop     rbp
0x18002785f  retn
0x180027860  lea     rcx, [rsp+1500h+var_14E0]; this
0x180027865  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18002786b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
