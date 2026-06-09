# wil::details::ReportFailure_Return<1>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions,wil::FailureFlags)

- ea: `0x1800040d8`
- end: `0x180004365`
- name: `??$ReportFailure_Return@$00@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@W4FailureFlags@1@@Z`
- size: `653`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x180003bb8`

## callees

- `0x180002e70`
- `0x180003a20`
- `0x1800040d8`
- `0x180006474`
- `0x180007910`
- `0x1800099d0`
- `0x180009ac4`
- `0x180012080`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004186`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004186`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000427a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000427a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004304`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004304`

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
0x1800040d8  push    rbp
0x1800040da  push    rbx
0x1800040db  push    rsi
0x1800040dc  push    rdi
0x1800040dd  push    r12
0x1800040df  push    r14
0x1800040e1  push    r15
0x1800040e3  lea     rbp, [rsp-13D0h]
0x1800040eb  mov     eax, 14D0h
0x1800040f0  call    _alloca_probe
0x1800040f5  sub     rsp, rax
0x1800040f8  mov     rax, cs:__security_cookie
0x1800040ff  xor     rax, rsp
0x180004102  mov     [rbp+1400h+var_40], rax
0x180004109  mov     r14, r8
0x18000410c  mov     esi, edx
0x18000410e  mov     r15, rcx
0x180004111  mov     rdi, [rbp+1400h+arg_28]
0x180004118  xor     edx, edx; Val
0x18000411a  mov     r8d, 98h; Size
0x180004120  lea     rcx, [rsp+1500h+var_14E0]; void *
0x180004125  call    memset_0
0x18000412a  nop
0x18000412b  xor     r12d, r12d
0x18000412e  mov     [rbp+1400h+OutputString], r12w
0x180004136  mov     [rbp+1400h+var_1440], r12b
0x18000413a  mov     rdx, qword ptr [rbp+1400h+arg_30]; int
0x180004141  mov     ecx, [rdx]; this
0x180004143  mov     [rsp+1500h+var_14D8], ecx
0x180004147  mov     eax, [rdx+4]
0x18000414a  mov     [rsp+1500h+var_14D4], eax
0x18000414e  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004153  mov     ebx, eax
0x180004155  mov     dword ptr [rsp+1500h+var_14E0], 1
0x18000415d  mov     ecx, r12d
0x180004160  lea     eax, [r12+8]
0x180004165  cmp     dword ptr [rdx+8], 1
0x180004169  cmovz   ecx, eax
0x18000416c  mov     dword ptr [rsp+1500h+var_14E0+4], ecx
0x180004170  lea     ecx, [rax-7]
0x180004173  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000417b  inc     ecx
0x18000417d  mov     [rsp+1500h+var_14D0], ecx
0x180004181  mov     [rsp+1500h+var_14C8], r12
0x180004186  call    cs:__imp_GetCurrentThreadId
0x18000418c  mov     [rsp+1500h+var_14C0], eax
0x180004190  mov     [rsp+1500h+var_14A8], r14
0x180004195  mov     [rsp+1500h+var_14A0], esi
0x180004199  mov     [rsp+1500h+var_149C], ebx
0x18000419d  mov     [rsp+1500h+var_14B8], r12
0x1800041a2  mov     [rsp+1500h+var_14B0], r12
0x1800041a7  mov     [rbp+1400h+var_1458], rdi
0x1800041ab  mov     [rbp+1400h+var_1450], r15
0x1800041af  mov     [rsp+1500h+var_1498], r12
0x1800041b4  xorps   xmm0, xmm0
0x1800041b7  xor     eax, eax
0x1800041b9  movups  [rbp+1400h+var_1478], xmm0
0x1800041bd  mov     [rbp+1400h+var_1468], rax
0x1800041c1  xorps   xmm1, xmm1
0x1800041c4  movups  [rsp+1500h+var_1490], xmm1
0x1800041c9  mov     [rbp+1400h+var_1480], rax
0x1800041cd  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800041d4  test    rax, rax
0x1800041d7  jz      short loc_1800041E4
0x1800041d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041de  mov     [rbp+1400h+var_1460], rax
0x1800041e2  jmp     short loc_1800041E8
0x1800041e4  mov     [rbp+1400h+var_1460], r12
0x1800041e8  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800041ef  test    rax, rax
0x1800041f2  jz      short loc_1800041FE
0x1800041f4  lea     rcx, [rsp+1500h+var_14E0]
0x1800041f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041fe  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004205  test    rax, rax
0x180004208  jz      short loc_18000421E
0x18000420a  mov     r8d, 400h
0x180004210  lea     rdx, [rbp+1400h+var_1440]
0x180004214  lea     rcx, [rsp+1500h+var_14E0]
0x180004219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000421e  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004225  test    rax, rax
0x180004228  jz      short loc_180004234
0x18000422a  lea     rcx, [rsp+1500h+var_14E0]
0x18000422f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004234  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000423b  test    rax, rax
0x18000423e  jz      short loc_180004251
0x180004240  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004245  jnz     short loc_180004251
0x180004247  lea     rcx, [rsp+1500h+var_14E0]
0x18000424c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004251  cmp     [rsp+1500h+var_14D8], r12d
0x180004256  jge     loc_18000435F
0x18000425c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r12b; bool wil::g_fIsDebuggerPresent
0x180004263  jnz     short loc_180004284
0x180004265  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000426c  test    rax, rax
0x18000426f  jz      short loc_18000427A
0x180004271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004276  test    al, al
0x180004278  jmp     short loc_180004282
0x18000427a  call    cs:__imp_IsDebuggerPresent
0x180004280  test    eax, eax
0x180004282  jz      short loc_18000428B
0x180004284  test    byte ptr [rsp+1500h+var_14E0+4], 2
0x180004289  jz      short loc_1800042B1
0x18000428b  mov     rax, cs:g_pfnResultLoggingCallback
0x180004292  test    rax, rax
0x180004295  jz      short loc_18000430A
0x180004297  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x18000429e  jnz     short loc_18000430A
0x1800042a0  xor     r8d, r8d
0x1800042a3  xor     edx, edx
0x1800042a5  lea     rcx, [rsp+1500h+var_14E0]
0x1800042aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042af  jmp     short loc_18000430A
0x1800042b1  mov     ebx, 800h
0x1800042b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042bd  test    rax, rax
0x1800042c0  jz      short loc_1800042DF
0x1800042c2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r12b; bool wil::details::g_resultMessageCallbackSet
0x1800042c9  jnz     short loc_1800042DF
0x1800042cb  mov     r8d, ebx
0x1800042ce  lea     rdx, [rbp+1400h+OutputString]
0x1800042d5  lea     rcx, [rsp+1500h+var_14E0]
0x1800042da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042df  cmp     [rbp+1400h+OutputString], r12w
0x1800042e7  jnz     short loc_1800042FD
0x1800042e9  lea     r8, [rsp+1500h+var_14E0]; unsigned __int64
0x1800042ee  mov     rdx, rbx; unsigned __int16 *
0x1800042f1  lea     rcx, [rbp+1400h+OutputString]; this
0x1800042f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800042fd  lea     rcx, [rbp+1400h+OutputString]; lpOutputString
0x180004304  call    cs:__imp_OutputDebugStringW
0x18000430a  test    byte ptr [rsp+1500h+var_14E0+4], 4
0x18000430f  jnz     short loc_18000431A
0x180004311  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r12b; bool wil::g_fBreakOnFailure
0x180004318  jz      short loc_18000432C
0x18000431a  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004321  test    rax, rax
0x180004324  jz      short loc_18000432C
0x180004326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000432b  nop
0x18000432c  test    byte ptr [rsp+1500h+var_14E0+4], 1
0x180004331  jnz     short loc_180004354
0x180004333  mov     rcx, [rbp+1400h+var_40]
0x18000433a  xor     rcx, rsp; StackCookie
0x18000433d  call    __security_check_cookie
0x180004342  add     rsp, 14D0h
0x180004349  pop     r15
0x18000434b  pop     r14
0x18000434d  pop     r12
0x18000434f  pop     rdi
0x180004350  pop     rsi
0x180004351  pop     rbx
0x180004352  pop     rbp
0x180004353  retn
0x180004354  lea     rcx, [rsp+1500h+var_14E0]; this
0x180004359  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000435f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
