# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800094a4`
- end: `0x18000974a`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `678`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180008f34`

## callees

- `0x1800050a0`
- `0x180005bbc`
- `0x1800094a4`
- `0x18000a944`
- `0x18000b920`
- `0x18000ca20`
- `0x18000cba8`
- `0x18006b240`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000956a`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000956a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800096e9`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800096e9`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000965f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000965f`

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
      g_pfnResultLoggingCallback(&v18, 0, 0, v16);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v18, OutputString, 2048, v16);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (__int64)&v18, v16);
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
0x1800094a4  push    rbp
0x1800094a6  push    rbx
0x1800094a7  push    rsi
0x1800094a8  push    rdi
0x1800094a9  push    r12
0x1800094ab  push    r14
0x1800094ad  push    r15
0x1800094af  lea     rbp, [rsp-13D0h]
0x1800094b7  mov     eax, 14D0h
0x1800094bc  call    _alloca_probe
0x1800094c1  sub     rsp, rax
0x1800094c4  mov     rax, cs:__security_cookie
0x1800094cb  xor     rax, rsp
0x1800094ce  mov     [rbp+1400h+var_40], rax
0x1800094d5  mov     rsi, r8
0x1800094d8  mov     edi, edx
0x1800094da  mov     rbx, rcx
0x1800094dd  mov     r14, [rbp+1400h+arg_28]
0x1800094e4  xor     edx, edx; Val
0x1800094e6  mov     r8d, 98h; Size
0x1800094ec  lea     rcx, [rsp+1500h+var_14E0]; void *
0x1800094f1  call    memset_0
0x1800094f6  nop
0x1800094f7  xor     r12d, r12d
0x1800094fa  mov     [rbp+1400h+OutputString], r12w
0x180009502  mov     [rbp+1400h+var_1440], r12b
0x180009506  mov     rdx, [rbp+1400h+arg_30]; int
0x18000950d  mov     ecx, [rdx]; this
0x18000950f  mov     [rsp+1500h+var_14D8], ecx
0x180009513  mov     eax, [rdx+4]
0x180009516  mov     [rsp+1500h+var_14D4], eax
0x18000951a  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000951f  mov     r15d, eax
0x180009522  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000952a  mov     ecx, r12d
0x18000952d  lea     eax, [r12+8]
0x180009532  cmp     dword ptr [rdx+8], 1
0x180009536  cmovz   ecx, eax
0x180009539  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x18000953d  lea     ecx, [rax-7]
0x180009540  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009548  inc     ecx
0x18000954a  mov     [rsp+1500h+var_14D0], ecx
0x18000954e  mov     rcx, [rbp+1400h+arg_38]
0x180009555  test    rcx, rcx
0x180009558  jz      short loc_180009565
0x18000955a  cmp     [rcx], r12w
0x18000955e  mov     [rsp+1500h+var_14C8], rcx
0x180009563  jnz     short loc_18000956A
0x180009565  mov     [rsp+1500h+var_14C8], r12
0x18000956a  call    cs:__imp_GetCurrentThreadId
0x180009570  mov     [rsp+1500h+var_14C0], eax
0x180009574  mov     [rsp+1500h+var_14A8], rsi
0x180009579  mov     [rsp+1500h+var_14A0], edi
0x18000957d  mov     [rsp+1500h+var_149C], r15d
0x180009582  mov     [rsp+1500h+var_14B8], r12
0x180009587  mov     [rsp+1500h+var_14B0], r12
0x18000958c  mov     [rbp+1400h+var_1458], r14
0x180009590  mov     [rbp+1400h+var_1450], rbx
0x180009594  mov     [rsp+1500h+var_1498], r12
0x180009599  xorps   xmm0, xmm0
0x18000959c  xor     eax, eax
0x18000959e  movups  [rbp+1400h+var_1478], xmm0
0x1800095a2  mov     [rbp+1400h+var_1468], rax
0x1800095a6  xorps   xmm1, xmm1
0x1800095a9  movups  [rsp+1500h+var_1490], xmm1
0x1800095ae  mov     [rbp+1400h+var_1480], rax
0x1800095b2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800095b9  test    rax, rax
0x1800095bc  jz      short loc_1800095C9
0x1800095be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095c3  mov     [rbp+1400h+var_1460], rax
0x1800095c7  jmp     short loc_1800095CD
0x1800095c9  mov     [rbp+1400h+var_1460], r12
0x1800095cd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800095d4  test    rax, rax
0x1800095d7  jz      short loc_1800095E3
0x1800095d9  lea     rcx, [rsp+1500h+var_14E0]
0x1800095de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800095e3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800095ea  test    rax, rax
0x1800095ed  jz      short loc_180009603
0x1800095ef  mov     r8d, 400h
0x1800095f5  lea     rdx, [rbp+1400h+var_1440]
0x1800095f9  lea     rcx, [rsp+1500h+var_14E0]
0x1800095fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009603  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000960a  test    rax, rax
0x18000960d  jz      short loc_180009619
0x18000960f  lea     rcx, [rsp+1500h+var_14E0]
0x180009614  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009619  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009620  test    rax, rax
0x180009623  jz      short loc_180009636
0x180009625  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000962a  jnz     short loc_180009636
0x18000962c  lea     rcx, [rsp+1500h+var_14E0]
0x180009631  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009636  cmp     [rsp+1500h+var_14D8], r12d
0x18000963b  jge     loc_180009744
0x180009641  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180009648  jnz     short loc_180009669
0x18000964a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009651  test    rax, rax
0x180009654  jz      short loc_18000965F
0x180009656  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000965b  test    al, al
0x18000965d  jmp     short loc_180009667
0x18000965f  call    cs:__imp_IsDebuggerPresent
0x180009665  test    eax, eax
0x180009667  jz      short loc_180009670
0x180009669  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x18000966e  jz      short loc_180009696
0x180009670  mov     rax, cs:g_pfnResultLoggingCallback
0x180009677  test    rax, rax
0x18000967a  jz      short loc_1800096EF
0x18000967c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x180009683  jnz     short loc_1800096EF
0x180009685  xor     r8d, r8d
0x180009688  xor     edx, edx
0x18000968a  lea     rcx, [rsp+1500h+var_14E0]
0x18000968f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009694  jmp     short loc_1800096EF
0x180009696  mov     ebx, 800h
0x18000969b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800096a2  test    rax, rax
0x1800096a5  jz      short loc_1800096C4
0x1800096a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800096ae  jnz     short loc_1800096C4
0x1800096b0  mov     r8d, ebx
0x1800096b3  lea     rdx, [rbp+1400h+OutputString]
0x1800096ba  lea     rcx, [rsp+1500h+var_14E0]
0x1800096bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800096c4  cmp     [rbp+1400h+OutputString], r12w
0x1800096cc  jnz     short loc_1800096E2
0x1800096ce  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800096d3  mov     rdx, rbx; unsigned __int16 *
0x1800096d6  lea     rcx, [rbp+1400h+OutputString]; this
0x1800096dd  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800096e2  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x1800096e9  call    cs:__imp_OutputDebugStringW
0x1800096ef  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x1800096f4  jnz     short loc_1800096FF
0x1800096f6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x1800096fd  jz      short loc_180009711
0x1800096ff  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009706  test    rax, rax
0x180009709  jz      short loc_180009711
0x18000970b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009710  nop
0x180009711  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180009716  jnz     short loc_180009739
0x180009718  mov     rcx, [rbp+1400h+var_40]
0x18000971f  xor     rcx, rsp; StackCookie
0x180009722  call    __security_check_cookie
0x180009727  add     rsp, 14D0h
0x18000972e  pop     r15
0x180009730  pop     r14
0x180009732  pop     r12
0x180009734  pop     rdi
0x180009735  pop     rsi
0x180009736  pop     rbx
0x180009737  pop     rbp
0x180009738  retn
0x180009739  lea     rcx, [rsp+1500h+var_14E0]; this
0x18000973e  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x180009744  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
