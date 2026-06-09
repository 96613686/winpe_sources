# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002524`
- end: `0x1400027b1`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002000`

## callees

- `0x140001480`
- `0x140001f36`
- `0x140002524`
- `0x140003644`
- `0x140004540`
- `0x140005460`
- `0x14000553c`
- `0x1400064c0`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400025d2`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400025d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002750`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140002750`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400026c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400026c6`

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
0x140002524  push    rbp
0x140002526  push    rbx
0x140002527  push    rsi
0x140002528  push    rdi
0x140002529  push    r12
0x14000252b  push    r14
0x14000252d  push    r15
0x14000252f  lea     rbp, [rsp-13D0h]
0x140002537  mov     eax, 14D0h
0x14000253c  call    _alloca_probe
0x140002541  sub     rsp, rax
0x140002544  mov     rax, cs:__security_cookie
0x14000254b  xor     rax, rsp
0x14000254e  mov     [rbp+1400h+var_40], rax
0x140002555  mov     r14, r8
0x140002558  mov     esi, edx
0x14000255a  mov     r15, rcx
0x14000255d  mov     rdi, [rbp+1400h+arg_28]
0x140002564  xor     edx, edx; Val
0x140002566  mov     r8d, 98h; Size
0x14000256c  lea     rcx, [rsp+1500h+var_14E0]; void *
0x140002571  call    memset_0
0x140002576  nop
0x140002577  xor     r12d, r12d
0x14000257a  mov     [rbp+1400h+OutputString], r12w
0x140002582  mov     [rbp+1400h+var_1440], r12b
0x140002586  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x14000258d  mov     ecx, [rdx]; this
0x14000258f  mov     [rsp+1500h+var_14D8], ecx
0x140002593  mov     eax, [rdx+4]
0x140002596  mov     [rsp+1500h+var_14D4], eax
0x14000259a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000259f  mov     ebx, eax
0x1400025a1  mov     dword ptr [rsp+1500h+var_14E0], 1
0x1400025a9  mov     ecx, r12d
0x1400025ac  lea     eax, [r12+8]
0x1400025b1  cmp     dword ptr [rdx+8], 1
0x1400025b5  cmovz   ecx, eax
0x1400025b8  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x1400025bc  lea     ecx, [rax-7]
0x1400025bf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400025c7  inc     ecx
0x1400025c9  mov     [rsp+1500h+var_14D0], ecx
0x1400025cd  mov     [rsp+1500h+var_14C8], r12
0x1400025d2  call    cs:__imp_GetCurrentThreadId
0x1400025d8  mov     [rsp+1500h+var_14C0], eax
0x1400025dc  mov     [rsp+1500h+var_14A8], r14
0x1400025e1  mov     [rsp+1500h+var_14A0], esi
0x1400025e5  mov     [rsp+1500h+var_149C], ebx
0x1400025e9  mov     [rsp+1500h+var_14B8], r12
0x1400025ee  mov     [rsp+1500h+var_14B0], r12
0x1400025f3  mov     [rbp+1400h+var_1458], rdi
0x1400025f7  mov     [rbp+1400h+var_1450], r15
0x1400025fb  mov     [rsp+1500h+var_1498], r12
0x140002600  xorps   xmm0, xmm0
0x140002603  xor     eax, eax
0x140002605  movups  [rbp+1400h+var_1478], xmm0
0x140002609  mov     [rbp+1400h+var_1468], rax
0x14000260d  xorps   xmm1, xmm1
0x140002610  movups  [rsp+1500h+var_1490], xmm1
0x140002615  mov     [rbp+1400h+var_1480], rax
0x140002619  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002620  test    rax, rax
0x140002623  jz      short loc_140002630
0x140002625  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000262a  mov     [rbp+1400h+var_1460], rax
0x14000262e  jmp     short loc_140002634
0x140002630  mov     [rbp+1400h+var_1460], r12
0x140002634  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000263b  test    rax, rax
0x14000263e  jz      short loc_14000264A
0x140002640  lea     rcx, [rsp+1500h+var_14E0]
0x140002645  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000264a  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140002651  test    rax, rax
0x140002654  jz      short loc_14000266A
0x140002656  mov     r8d, 400h
0x14000265c  lea     rdx, [rbp+1400h+var_1440]
0x140002660  lea     rcx, [rsp+1500h+var_14E0]
0x140002665  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000266a  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002671  test    rax, rax
0x140002674  jz      short loc_140002680
0x140002676  lea     rcx, [rsp+1500h+var_14E0]
0x14000267b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002680  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140002687  test    rax, rax
0x14000268a  jz      short loc_14000269D
0x14000268c  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002691  jnz     short loc_14000269D
0x140002693  lea     rcx, [rsp+1500h+var_14E0]
0x140002698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000269d  cmp     [rsp+1500h+var_14D8], r12d
0x1400026a2  jge     loc_1400027AB
0x1400026a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x1400026af  jnz     short loc_1400026D0
0x1400026b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400026b8  test    rax, rax
0x1400026bb  jz      short loc_1400026C6
0x1400026bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026c2  test    al, al
0x1400026c4  jmp     short loc_1400026CE
0x1400026c6  call    cs:__imp_IsDebuggerPresent
0x1400026cc  test    eax, eax
0x1400026ce  jz      short loc_1400026D7
0x1400026d0  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1400026d5  jz      short loc_1400026FD
0x1400026d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400026de  test    rax, rax
0x1400026e1  jz      short loc_140002756
0x1400026e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1400026ea  jnz     short loc_140002756
0x1400026ec  xor     r8d, r8d
0x1400026ef  xor     edx, edx
0x1400026f1  lea     rcx, [rsp+1500h+var_14E0]
0x1400026f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026fb  jmp     short loc_140002756
0x1400026fd  mov     ebx, 800h
0x140002702  mov     rax, cs:g_pfnResultLoggingCallback
0x140002709  test    rax, rax
0x14000270c  jz      short loc_14000272B
0x14000270e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002715  jnz     short loc_14000272B
0x140002717  mov     r8d, ebx
0x14000271a  lea     rdx, [rbp+1400h+OutputString]
0x140002721  lea     rcx, [rsp+1500h+var_14E0]
0x140002726  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000272b  cmp     [rbp+1400h+OutputString], r12w
0x140002733  jnz     short loc_140002749
0x140002735  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x14000273a  mov     rdx, rbx; unsigned __int16 *
0x14000273d  lea     rcx, [rbp+1400h+OutputString]; this
0x140002744  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140002749  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x140002750  call    cs:__imp_OutputDebugStringW
0x140002756  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x14000275b  jnz     short loc_140002766
0x14000275d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x140002764  jz      short loc_140002778
0x140002766  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000276d  test    rax, rax
0x140002770  jz      short loc_140002778
0x140002772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002777  nop
0x140002778  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x14000277d  jnz     short loc_1400027A0
0x14000277f  mov     rcx, [rbp+1400h+var_40]
0x140002786  xor     rcx, rsp; StackCookie
0x140002789  call    __security_check_cookie
0x14000278e  add     rsp, 14D0h
0x140002795  pop     r15
0x140002797  pop     r14
0x140002799  pop     r12
0x14000279b  pop     rdi
0x14000279c  pop     rsi
0x14000279d  pop     rbx
0x14000279e  pop     rbp
0x14000279f  retn
0x1400027a0  lea     rcx, [rsp+1500h+var_14E0]; this
0x1400027a5  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x1400027ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
