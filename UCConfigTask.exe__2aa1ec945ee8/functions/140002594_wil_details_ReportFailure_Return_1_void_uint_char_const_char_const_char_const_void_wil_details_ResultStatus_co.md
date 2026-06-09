# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x140002594`
- end: `0x140002821`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x140002254`

## callees

- `0x1400014c0`
- `0x14000209c`
- `0x140002594`
- `0x140003ea4`
- `0x140005810`
- `0x140006fa8`
- `0x140007160`
- `0x140008750`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002642`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140002642`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002736`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140002736`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400027c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400027c0`

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
0x140002594  push    rbp
0x140002596  push    rbx
0x140002597  push    rsi
0x140002598  push    rdi
0x140002599  push    r12
0x14000259b  push    r14
0x14000259d  push    r15
0x14000259f  lea     rbp, [rsp-13D0h]
0x1400025a7  mov     eax, 14D0h
0x1400025ac  call    _alloca_probe
0x1400025b1  sub     rsp, rax
0x1400025b4  mov     rax, cs:__security_cookie
0x1400025bb  xor     rax, rsp
0x1400025be  mov     [rbp+1400h+var_40], rax
0x1400025c5  mov     r14, r8
0x1400025c8  mov     esi, edx
0x1400025ca  mov     r15, rcx
0x1400025cd  mov     rdi, [rbp+1400h+arg_28]
0x1400025d4  xor     edx, edx; Val
0x1400025d6  mov     r8d, 98h; Size
0x1400025dc  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1400025e1  call    memset_0
0x1400025e6  nop
0x1400025e7  xor     r12d, r12d
0x1400025ea  mov     [rbp+1400h+OutputString], r12w
0x1400025f2  mov     [rbp+1400h+var_1440], r12b
0x1400025f6  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x1400025fd  mov     ecx, [rdx]; this
0x1400025ff  mov     [rsp+1500h+var_14D8], ecx
0x140002603  mov     eax, [rdx+4]
0x140002606  mov     [rsp+1500h+var_14D4], eax
0x14000260a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000260f  mov     ebx, eax
0x140002611  mov     dword ptr [rsp+1500h+var_14E0], 1
0x140002619  mov     ecx, r12d
0x14000261c  lea     eax, [r12+8]
0x140002621  cmp     dword ptr [rdx+8], 1
0x140002625  cmovz   ecx, eax
0x140002628  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x14000262c  lea     ecx, [rax-7]
0x14000262f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140002637  inc     ecx
0x140002639  mov     [rsp+1500h+var_14D0], ecx
0x14000263d  mov     [rsp+1500h+var_14C8], r12
0x140002642  call    cs:__imp_GetCurrentThreadId
0x140002648  mov     [rsp+1500h+var_14C0], eax
0x14000264c  mov     [rsp+1500h+var_14A8], r14
0x140002651  mov     [rsp+1500h+var_14A0], esi
0x140002655  mov     [rsp+1500h+var_149C], ebx
0x140002659  mov     [rsp+1500h+var_14B8], r12
0x14000265e  mov     [rsp+1500h+var_14B0], r12
0x140002663  mov     [rbp+1400h+var_1458], rdi
0x140002667  mov     [rbp+1400h+var_1450], r15
0x14000266b  mov     [rsp+1500h+var_1498], r12
0x140002670  xorps   xmm0, xmm0
0x140002673  xor     eax, eax
0x140002675  movups  [rbp+1400h+var_1478], xmm0
0x140002679  mov     [rbp+1400h+var_1468], rax
0x14000267d  xorps   xmm1, xmm1
0x140002680  movups  [rsp+1500h+var_1490], xmm1
0x140002685  mov     [rbp+1400h+var_1480], rax
0x140002689  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140002690  test    rax, rax
0x140002693  jz      short loc_1400026A0
0x140002695  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000269a  mov     [rbp+1400h+var_1460], rax
0x14000269e  jmp     short loc_1400026A4
0x1400026a0  mov     [rbp+1400h+var_1460], r12
0x1400026a4  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400026ab  test    rax, rax
0x1400026ae  jz      short loc_1400026BA
0x1400026b0  lea     rcx, [rsp+1500h+var_14E0]
0x1400026b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026ba  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400026c1  test    rax, rax
0x1400026c4  jz      short loc_1400026DA
0x1400026c6  mov     r8d, 400h
0x1400026cc  lea     rdx, [rbp+1400h+var_1440]
0x1400026d0  lea     rcx, [rsp+1500h+var_14E0]
0x1400026d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026da  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400026e1  test    rax, rax
0x1400026e4  jz      short loc_1400026F0
0x1400026e6  lea     rcx, [rsp+1500h+var_14E0]
0x1400026eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400026f0  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400026f7  test    rax, rax
0x1400026fa  jz      short loc_14000270D
0x1400026fc  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002701  jnz     short loc_14000270D
0x140002703  lea     rcx, [rsp+1500h+var_14E0]
0x140002708  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000270d  cmp     [rsp+1500h+var_14D8], r12d
0x140002712  jge     loc_14000281B
0x140002718  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x14000271f  jnz     short loc_140002740
0x140002721  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002728  test    rax, rax
0x14000272b  jz      short loc_140002736
0x14000272d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002732  test    al, al
0x140002734  jmp     short loc_14000273E
0x140002736  call    cs:__imp_IsDebuggerPresent
0x14000273c  test    eax, eax
0x14000273e  jz      short loc_140002747
0x140002740  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x140002745  jz      short loc_14000276D
0x140002747  mov     rax, cs:g_pfnResultLoggingCallback
0x14000274e  test    rax, rax
0x140002751  jz      short loc_1400027C6
0x140002753  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x14000275a  jnz     short loc_1400027C6
0x14000275c  xor     r8d, r8d
0x14000275f  xor     edx, edx
0x140002761  lea     rcx, [rsp+1500h+var_14E0]
0x140002766  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000276b  jmp     short loc_1400027C6
0x14000276d  mov     ebx, 800h
0x140002772  mov     rax, cs:g_pfnResultLoggingCallback
0x140002779  test    rax, rax
0x14000277c  jz      short loc_14000279B
0x14000277e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x140002785  jnz     short loc_14000279B
0x140002787  mov     r8d, ebx
0x14000278a  lea     rdx, [rbp+1400h+OutputString]
0x140002791  lea     rcx, [rsp+1500h+var_14E0]
0x140002796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000279b  cmp     [rbp+1400h+OutputString], r12w
0x1400027a3  jnz     short loc_1400027B9
0x1400027a5  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1400027aa  mov     rdx, rbx; unsigned __int16 *
0x1400027ad  lea     rcx, [rbp+1400h+OutputString]; this
0x1400027b4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400027b9  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1400027c0  call    cs:__imp_OutputDebugStringW
0x1400027c6  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1400027cb  jnz     short loc_1400027D6
0x1400027cd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1400027d4  jz      short loc_1400027E8
0x1400027d6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400027dd  test    rax, rax
0x1400027e0  jz      short loc_1400027E8
0x1400027e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400027e7  nop
0x1400027e8  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x1400027ed  jnz     short loc_140002810
0x1400027ef  mov     rcx, [rbp+1400h+var_40]
0x1400027f6  xor     rcx, rsp; StackCookie
0x1400027f9  call    __security_check_cookie
0x1400027fe  add     rsp, 14D0h
0x140002805  pop     r15
0x140002807  pop     r14
0x140002809  pop     r12
0x14000280b  pop     rdi
0x14000280c  pop     rsi
0x14000280d  pop     rbx
0x14000280e  pop     rbp
0x14000280f  retn
0x140002810  lea     rcx, [rsp+1500h+var_14E0]; this
0x140002815  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x14000281b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
