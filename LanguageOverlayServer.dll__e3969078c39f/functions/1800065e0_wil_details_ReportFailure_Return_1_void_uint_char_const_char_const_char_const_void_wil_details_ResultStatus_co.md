# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800065e0`
- end: `0x180006886`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: `void __fastcall(__int64, int, __int64, __int64, int, __int64, int *, _WORD *)`
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000607c`

## callees

- `0x180003a00`
- `0x1800044b8`
- `0x1800065e0`
- `0x180007bb4`
- `0x180008a00`
- `0x180009e70`
- `0x180009ff8`
- `0x1800633f0`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066a6`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800066a6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000679b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000679b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006825`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006825`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details::ReportFailure_Return<1>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7,
        _WORD *a8)
{
  int v11; // r15d
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  int v18; // [rsp+20h] [rbp-E0h] BYREF
  int v19; // [rsp+24h] [rbp-DCh]
  int v20; // [rsp+28h] [rbp-D8h]
  int v21; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v22; // [rsp+30h] [rbp-D0h]
  _WORD *v23; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
  __int64 v25; // [rsp+48h] [rbp-B8h]
  __int64 v26; // [rsp+50h] [rbp-B0h]
  __int64 v27; // [rsp+58h] [rbp-A8h]
  int v28; // [rsp+60h] [rbp-A0h]
  int v29; // [rsp+64h] [rbp-9Ch]
  __int64 v30; // [rsp+68h] [rbp-98h]
  __int128 v31; // [rsp+70h] [rbp-90h]
  __int64 v32; // [rsp+80h] [rbp-80h]
  __int128 v33; // [rsp+88h] [rbp-78h]
  __int64 v34; // [rsp+98h] [rbp-68h]
  __int64 ModuleName; // [rsp+A0h] [rbp-60h]
  __int64 v36; // [rsp+A8h] [rbp-58h]
  __int64 v37; // [rsp+B0h] [rbp-50h]
  char v38[1024]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR OutputString[2048]; // [rsp+4C0h] [rbp+3C0h] BYREF

  memset_0(&v18, 0, 0x98u);
  OutputString[0] = 0;
  v38[0] = 0;
  v20 = *a7;
  v21 = a7[1];
  v11 = wil::details::RecordReturn((wil::details *)(unsigned int)v20, (int)a7);
  v18 = 1;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v19 = v12;
  v22 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  if ( !a8 || (v17 = *a8 == 0, v23 = a8, v17) )
    v23 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v27 = a3;
  v28 = a2;
  v29 = v11;
  v25 = 0;
  v26 = 0;
  v36 = a6;
  v37 = a1;
  v30 = 0;
  v33 = 0;
  v34 = 0;
  v31 = 0;
  v32 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v18);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v18, v38, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v18);
  if ( wil::details::g_pfnOriginateCallback && (v19 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v18);
  if ( v20 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v19 & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v18, v16);
    OutputDebugStringW(OutputString);
  }
  if ( ((v19 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v19 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v18, v14);
}

```

## disassembly

```asm
0x1800065e0  push    rbp
0x1800065e2  push    rbx
0x1800065e3  push    rsi
0x1800065e4  push    rdi
0x1800065e5  push    r12
0x1800065e7  push    r14
0x1800065e9  push    r15
0x1800065eb  lea     rbp, [rsp-13D0h]
0x1800065f3  mov     eax, 14D0h
0x1800065f8  call    _alloca_probe
0x1800065fd  sub     rsp, rax
0x180006600  mov     rax, cs:__security_cookie
0x180006607  xor     rax, rsp
0x18000660a  mov     [rbp+1400h+var_40], rax
0x180006611  mov     rsi, r8
0x180006614  mov     edi, edx
0x180006616  mov     rbx, rcx
0x180006619  mov     r14, [rbp+1400h+arg_28]
0x180006620  xor     edx, edx; Val
0x180006622  mov     r8d, 98h; Size
0x180006628  lea     rcx, [rsp+1500h+var_14E0]; void *
0x18000662d  call    memset_0
0x180006632  nop
0x180006633  xor     r12d, r12d
0x180006636  mov     [rbp+1400h+OutputString], r12w
0x18000663e  mov     [rbp+1400h+var_1440], r12b
0x180006642  mov     rdx, [rbp+1400h+arg_30]; int
0x180006649  mov     ecx, [rdx]; this
0x18000664b  mov     [rsp+1500h+var_14D8], ecx
0x18000664f  mov     eax, [rdx+4]
0x180006652  mov     [rsp+1500h+var_14D4], eax
0x180006656  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000665b  mov     r15d, eax
0x18000665e  mov     dword ptr [rsp+1500h+var_14E0], 1
0x180006666  mov     ecx, r12d
0x180006669  lea     eax, [r12+8]
0x18000666e  cmp     dword ptr [rdx+8], 1
0x180006672  cmovz   ecx, eax
0x180006675  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180006679  lea     ecx, [rax-7]
0x18000667c  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006684  inc     ecx
0x180006686  mov     [rsp+1500h+var_14D0], ecx
0x18000668a  mov     rcx, [rbp+1400h+arg_38]
0x180006691  test    rcx, rcx
0x180006694  jz      short loc_1800066A1
0x180006696  cmp     [rcx], r12w
0x18000669a  mov     [rsp+1500h+var_14C8], rcx
0x18000669f  jnz     short loc_1800066A6
0x1800066a1  mov     [rsp+1500h+var_14C8], r12
0x1800066a6  call    cs:__imp_GetCurrentThreadId
0x1800066ac  mov     [rsp+1500h+var_14C0], eax
0x1800066b0  mov     [rsp+1500h+var_14A8], rsi
0x1800066b5  mov     [rsp+1500h+var_14A0], edi
0x1800066b9  mov     [rsp+1500h+var_149C], r15d
0x1800066be  mov     [rsp+1500h+var_14B8], r12
0x1800066c3  mov     [rsp+1500h+var_14B0], r12
0x1800066c8  mov     [rbp+1400h+var_1458], r14
0x1800066cc  mov     [rbp+1400h+var_1450], rbx
0x1800066d0  mov     [rsp+1500h+var_1498], r12
0x1800066d5  xorps   xmm0, xmm0
0x1800066d8  xor     eax, eax
0x1800066da  movups  [rbp+1400h+var_1478], xmm0
0x1800066de  mov     [rbp+1400h+var_1468], rax
0x1800066e2  xorps   xmm1, xmm1
0x1800066e5  movups  [rsp+1500h+var_1490], xmm1
0x1800066ea  mov     [rbp+1400h+var_1480], rax
0x1800066ee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800066f5  test    rax, rax
0x1800066f8  jz      short loc_180006705
0x1800066fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ff  mov     [rbp+1400h+var_1460], rax
0x180006703  jmp     short loc_180006709
0x180006705  mov     [rbp+1400h+var_1460], r12
0x180006709  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006710  test    rax, rax
0x180006713  jz      short loc_18000671F
0x180006715  lea     rcx, [rsp+1500h+var_14E0]
0x18000671a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000671f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006726  test    rax, rax
0x180006729  jz      short loc_18000673F
0x18000672b  mov     r8d, 400h
0x180006731  lea     rdx, [rbp+1400h+var_1440]
0x180006735  lea     rcx, [rsp+1500h+var_14E0]
0x18000673a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006746  test    rax, rax
0x180006749  jz      short loc_180006755
0x18000674b  lea     rcx, [rsp+1500h+var_14E0]
0x180006750  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006755  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000675c  test    rax, rax
0x18000675f  jz      short loc_180006772
0x180006761  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180006766  jnz     short loc_180006772
0x180006768  lea     rcx, [rsp+1500h+var_14E0]
0x18000676d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006772  cmp     [rsp+1500h+var_14D8], r12d
0x180006777  jge     loc_180006880
0x18000677d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180006784  jnz     short loc_1800067A5
0x180006786  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000678d  test    rax, rax
0x180006790  jz      short loc_18000679B
0x180006792  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006797  test    al, al
0x180006799  jmp     short loc_1800067A3
0x18000679b  call    cs:__imp_IsDebuggerPresent
0x1800067a1  test    eax, eax
0x1800067a3  jz      short loc_1800067AC
0x1800067a5  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x1800067aa  jz      short loc_1800067D2
0x1800067ac  mov     rax, cs:g_pfnResultLoggingCallback
0x1800067b3  test    rax, rax
0x1800067b6  jz      short loc_18000682B
0x1800067b8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800067bf  jnz     short loc_18000682B
0x1800067c1  xor     r8d, r8d
0x1800067c4  xor     edx, edx
0x1800067c6  lea     rcx, [rsp+1500h+var_14E0]
0x1800067cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067d0  jmp     short loc_18000682B
0x1800067d2  mov     ebx, 800h
0x1800067d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800067de  test    rax, rax
0x1800067e1  jz      short loc_180006800
0x1800067e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800067ea  jnz     short loc_180006800
0x1800067ec  mov     r8d, ebx
0x1800067ef  lea     rdx, [rbp+1400h+OutputString]
0x1800067f6  lea     rcx, [rsp+1500h+var_14E0]
0x1800067fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006800  cmp     [rbp+1400h+OutputString], r12w
0x180006808  jnz     short loc_18000681E
0x18000680a  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x18000680f  mov     rdx, rbx; unsigned __int16 *
0x180006812  lea     rcx, [rbp+1400h+OutputString]; this
0x180006819  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000681e  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180006825  call    cs:__imp_OutputDebugStringW
0x18000682b  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x180006830  jnz     short loc_18000683B
0x180006832  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180006839  jz      short loc_18000684D
0x18000683b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006842  test    rax, rax
0x180006845  jz      short loc_18000684D
0x180006847  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000684c  nop
0x18000684d  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180006852  jnz     short loc_180006875
0x180006854  mov     rcx, [rbp+1400h+var_40]
0x18000685b  xor     rcx, rsp; StackCookie
0x18000685e  call    __security_check_cookie
0x180006863  add     rsp, 14D0h
0x18000686a  pop     r15
0x18000686c  pop     r14
0x18000686e  pop     r12
0x180006870  pop     rdi
0x180006871  pop     rsi
0x180006872  pop     rbx
0x180006873  pop     rbp
0x180006874  retn
0x180006875  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000687a  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180006880  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
