# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800065fc`
- end: `0x180006889`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x1800060dc`

## callees

- `0x180005020`
- `0x180005e9c`
- `0x1800065fc`
- `0x180008c14`
- `0x18000a330`
- `0x18000c580`
- `0x18000c674`
- `0x1800599b0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066aa`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006828`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006828`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000679e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000679e`

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
0x1800065fc  push    rbp
0x1800065fe  push    rbx
0x1800065ff  push    rsi
0x180006600  push    rdi
0x180006601  push    r12
0x180006603  push    r14
0x180006605  push    r15
0x180006607  lea     rbp, [rsp-13D0h]
0x18000660f  mov     eax, 14D0h
0x180006614  call    _alloca_probe
0x180006619  sub     rsp, rax
0x18000661c  mov     rax, cs:__security_cookie
0x180006623  xor     rax, rsp
0x180006626  mov     [rbp+1400h+var_40], rax
0x18000662d  mov     r14, r8
0x180006630  mov     esi, edx
0x180006632  mov     r15, rcx
0x180006635  mov     rdi, [rbp+1400h+arg_28]
0x18000663c  xor     edx, edx; Val
0x18000663e  mov     r8d, 98h; Size
0x180006644  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180006649  call    memset_0
0x18000664e  nop
0x18000664f  xor     r12d, r12d
0x180006652  mov     [rbp+1400h+OutputString], r12w
0x18000665a  mov     [rbp+1400h+var_1440], r12b
0x18000665e  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180006665  mov     ecx, [rdx]; this
0x180006667  mov     [rsp+1500h+var_14D8], ecx
0x18000666b  mov     eax, [rdx+4]
0x18000666e  mov     [rsp+1500h+var_14D4], eax
0x180006672  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006677  mov     ebx, eax
0x180006679  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006681  mov     ecx, r12d
0x180006684  lea     eax, [r12+8]
0x180006689  cmp     dword ptr [rdx+8], 1
0x18000668d  cmovz   ecx, eax
0x180006690  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006694  lea     ecx, [rax-7]
0x180006697  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000669f  inc     ecx
0x1800066a1  mov     [rsp+1500h+var_14D0], ecx
0x1800066a5  mov     [rsp+1500h+var_14C8], r12
0x1800066aa  call    cs:__imp_GetCurrentThreadId
0x1800066b0  mov     [rsp+1500h+var_14C0], eax
0x1800066b4  mov     [rsp+1500h+var_14A8], r14
0x1800066b9  mov     [rsp+1500h+var_14A0], esi
0x1800066bd  mov     [rsp+1500h+var_149C], ebx
0x1800066c1  mov     [rsp+1500h+var_14B8], r12
0x1800066c6  mov     [rsp+1500h+var_14B0], r12
0x1800066cb  mov     [rbp+1400h+var_1458], rdi
0x1800066cf  mov     [rbp+1400h+var_1450], r15
0x1800066d3  mov     [rsp+1500h+var_1498], r12
0x1800066d8  xorps   xmm0, xmm0
0x1800066db  xor     eax, eax
0x1800066dd  movups  [rbp+1400h+var_1478], xmm0
0x1800066e1  mov     [rbp+1400h+var_1468], rax
0x1800066e5  xorps   xmm1, xmm1
0x1800066e8  movups  [rsp+1500h+var_1490], xmm1
0x1800066ed  mov     [rbp+1400h+var_1480], rax
0x1800066f1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800066f8  test    rax, rax
0x1800066fb  jz      short loc_180006708
0x1800066fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006702  mov     [rbp+1400h+var_1460], rax
0x180006706  jmp     short loc_18000670C
0x180006708  mov     [rbp+1400h+var_1460], r12
0x18000670c  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006713  test    rax, rax
0x180006716  jz      short loc_180006722
0x180006718  lea     rcx, [rsp+1500h+var_14E0]
0x18000671d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006722  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006729  test    rax, rax
0x18000672c  jz      short loc_180006742
0x18000672e  mov     r8d, 400h
0x180006734  lea     rdx, [rbp+1400h+var_1440]
0x180006738  lea     rcx, [rsp+1500h+var_14E0]
0x18000673d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006742  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006749  test    rax, rax
0x18000674c  jz      short loc_180006758
0x18000674e  lea     rcx, [rsp+1500h+var_14E0]
0x180006753  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006758  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000675f  test    rax, rax
0x180006762  jz      short loc_180006775
0x180006764  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006769  jnz     short loc_180006775
0x18000676b  lea     rcx, [rsp+1500h+var_14E0]
0x180006770  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006775  cmp     [rsp+1500h+var_14D8], r12d
0x18000677a  jge     loc_180006883
0x180006780  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006787  jnz     short loc_1800067A8
0x180006789  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006790  test    rax, rax
0x180006793  jz      short loc_18000679E
0x180006795  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000679a  test    al, al
0x18000679c  jmp     short loc_1800067A6
0x18000679e  call    cs:__imp_IsDebuggerPresent
0x1800067a4  test    eax, eax
0x1800067a6  jz      short loc_1800067AF
0x1800067a8  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800067ad  jz      short loc_1800067D5
0x1800067af  mov     rax, cs:g_pfnResultLoggingCallback
0x1800067b6  test    rax, rax
0x1800067b9  jz      short loc_18000682E
0x1800067bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800067c2  jnz     short loc_18000682E
0x1800067c4  xor     r8d, r8d
0x1800067c7  xor     edx, edx
0x1800067c9  lea     rcx, [rsp+1500h+var_14E0]
0x1800067ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d3  jmp     short loc_18000682E
0x1800067d5  mov     ebx, 800h
0x1800067da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800067e1  test    rax, rax
0x1800067e4  jz      short loc_180006803
0x1800067e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800067ed  jnz     short loc_180006803
0x1800067ef  mov     r8d, ebx
0x1800067f2  lea     rdx, [rbp+1400h+OutputString]
0x1800067f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800067fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006803  cmp     [rbp+1400h+OutputString], r12w
0x18000680b  jnz     short loc_180006821
0x18000680d  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x180006812  mov     rdx, rbx; unsigned __int16 *
0x180006815  lea     rcx, [rbp+1400h+OutputString]; this
0x18000681c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006821  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006828  call    cs:__imp_OutputDebugStringW
0x18000682e  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006833  jnz     short loc_18000683E
0x180006835  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x18000683c  jz      short loc_180006850
0x18000683e  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006845  test    rax, rax
0x180006848  jz      short loc_180006850
0x18000684a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684f  nop
0x180006850  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006855  jnz     short loc_180006878
0x180006857  mov     rcx, [rbp+1400h+var_40]
0x18000685e  xor     rcx, rsp; StackCookie
0x180006861  call    __security_check_cookie
0x180006866  add     rsp, 14D0h
0x18000686d  pop     r15
0x18000686f  pop     r14
0x180006871  pop     r12
0x180006873  pop     rdi
0x180006874  pop     rsi
0x180006875  pop     rbx
0x180006876  pop     rbp
0x180006877  retn
0x180006878  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000687d  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006883  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
