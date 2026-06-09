# wil::details::ReportFailure_NoReturn<0>(void *,uint,char const *,char const *,char const *,void *,wil::details::ResultStatus const &,ushort const *,wil::details::ReportFailureOptions)

- ea: `0x18000cb9c`
- end: `0x18000ce48`
- name: `??$ReportFailure_NoReturn@$0A@@details@wil@@YAXPEAXIPEBD110AEBUResultStatus@01@PEBGW4ReportFailureOptions@01@@Z`
- size: `684`
- prototype: ``
- caller_count: `1`
- callee_count: `9`
- tags: ``

## callers

- `0x18000caf0`

## callees

- `0x180005e9c`
- `0x180008c14`
- `0x18000a2d8`
- `0x18000bef8`
- `0x18000c580`
- `0x18000c674`
- `0x18000cb9c`
- `0x1800599b0`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc45`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cc45`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cddc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cddc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cd40`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cd40`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
void __fastcall __noreturn wil::details::ReportFailure_NoReturn<0>(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        int a5,
        __int64 a6,
        int *a7)
{
  bool v10; // r12
  int v11; // ebx
  int v12; // ecx
  __int64 v13; // rdx
  const struct wil::FailureInfo *v14; // rdx
  wil::details::in1diag3 *v15; // rcx
  const struct wil::FailureInfo *v16; // r9
  bool v17; // zf
  char v18; // bl
  const struct wil::FailureInfo *v19; // rdx
  int v20; // [rsp+20h] [rbp-E0h] BYREF
  int v21; // [rsp+24h] [rbp-DCh]
  int v22; // [rsp+28h] [rbp-D8h]
  int v23; // [rsp+2Ch] [rbp-D4h]
  signed __int32 v24; // [rsp+30h] [rbp-D0h]
  __int64 v25; // [rsp+38h] [rbp-C8h]
  DWORD CurrentThreadId; // [rsp+40h] [rbp-C0h]
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
  WCHAR OutputString[2072]; // [rsp+4C0h] [rbp+3C0h] BYREF

  v10 = g_pfnThrowPlatformException != 0;
  memset_0(&v20, 0, 0x98u);
  OutputString[0] = 0;
  v40[0] = 0;
  v22 = *a7;
  v23 = a7[1];
  v11 = wil::details::RecordException((wil::details *)(unsigned int)v22, (int)a7);
  v20 = 0;
  v12 = 0;
  if ( *(_DWORD *)(v13 + 8) == 1 )
    v12 = 8;
  v21 = v12;
  v24 = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v25 = 0;
  CurrentThreadId = GetCurrentThreadId();
  v29 = a3;
  v30 = a2;
  v31 = v11;
  v27 = 0;
  v28 = 0;
  v38 = a6;
  v39 = a1;
  v32 = 0;
  v35 = 0;
  v36 = 0;
  v33 = 0;
  v34 = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v15);
  else
    ModuleName = 0;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(&v20);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(&v20, v40, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(&v20);
  if ( wil::details::g_pfnOriginateCallback && !v10 && (v21 & 2) == 0 )
    wil::details::g_pfnOriginateCallback(&v20);
  if ( v22 >= 0 )
    wil::details::in1diag3::_FailFastImmediate_Unexpected(v15);
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v17 = !IsDebuggerPresent())
      : (v17 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v15) == 0),
        v17)
    || (v18 = 1, (v21 & 2) != 0) )
  {
    v18 = 0;
  }
  if ( v10 || v18 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(&v20, OutputString, 2048);
    if ( !OutputString[0] )
      wil::GetFailureLogString((wil *)OutputString, (unsigned __int16 *)0x800, (unsigned __int64)&v20, v16);
    if ( v18 )
      OutputDebugStringW(OutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(&v20, 0, 0);
  }
  if ( ((v21 & 4) != 0 || wil::g_fBreakOnFailure) && wil::details::g_pfnDebugBreak )
    wil::details::g_pfnDebugBreak(v15);
  if ( (v21 & 1) != 0 )
    wil::details::WilFailFast((wil::details *)&v20, v14);
  if ( v10 )
    ((void (__fastcall *)(int *, WCHAR *))g_pfnThrowPlatformException)(&v20, OutputString);
  wil::ThrowResultException((wil *)&v20, v14);
  wil::details::WilFailFast((wil::details *)&v20, v19);
}

```

## disassembly

```asm
0x18000cb9c  mov     [rsp-8+arg_18], rbx
0x18000cba1  push    rbp
0x18000cba2  push    rsi
0x18000cba3  push    rdi
0x18000cba4  push    r12
0x18000cba6  push    r13
0x18000cba8  push    r14
0x18000cbaa  push    r15
0x18000cbac  lea     rbp, [rsp-13C0h]
0x18000cbb4  mov     eax, 14C0h
0x18000cbb9  call    _alloca_probe
0x18000cbbe  sub     rsp, rax
0x18000cbc1  mov     r14, r8
0x18000cbc4  mov     esi, edx
0x18000cbc6  mov     r15, rcx
0x18000cbc9  mov     rdi, [rbp+13F0h+arg_28]
0x18000cbd0  xor     r13d, r13d
0x18000cbd3  cmp     cs:g_pfnThrowPlatformException, r13
0x18000cbda  setnz   r12b
0x18000cbde  xor     edx, edx; Val
0x18000cbe0  mov     r8d, 98h; Size
0x18000cbe6  lea     rcx, [rsp+14F0h+var_14D0]; void *
0x18000cbeb  call    memset_0
0x18000cbf0  nop
0x18000cbf1  mov     [rbp+13F0h+OutputString], r13w
0x18000cbf9  mov     [rbp+13F0h+var_1430], r13b
0x18000cbfd  mov     rdx, qword ptr [rbp+13F0h+arg_30]; int
0x18000cc04  mov     ecx, [rdx]; this
0x18000cc06  mov     [rsp+14F0h+var_14C8], ecx
0x18000cc0a  mov     eax, [rdx+4]
0x18000cc0d  mov     [rsp+14F0h+var_14C4], eax
0x18000cc11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000cc16  mov     ebx, eax
0x18000cc18  mov     dword ptr [rsp+14F0h+var_14D0], r13d
0x18000cc1d  mov     ecx, r13d
0x18000cc20  lea     eax, [r13+8]
0x18000cc24  cmp     dword ptr [rdx+8], 1
0x18000cc28  cmovz   ecx, eax
0x18000cc2b  mov     dword ptr [rsp+14F0h+var_14D0+4], ecx
0x18000cc2f  lea     ecx, [rax-7]
0x18000cc32  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, ecx; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000cc3a  inc     ecx
0x18000cc3c  mov     [rsp+14F0h+var_14C0], ecx
0x18000cc40  mov     [rsp+14F0h+var_14B8], r13
0x18000cc45  call    cs:__imp_GetCurrentThreadId
0x18000cc4b  mov     [rsp+14F0h+var_14B0], eax
0x18000cc4f  mov     [rsp+14F0h+var_1498], r14
0x18000cc54  mov     [rsp+14F0h+var_1490], esi
0x18000cc58  mov     [rsp+14F0h+var_148C], ebx
0x18000cc5c  mov     [rsp+14F0h+var_14A8], r13
0x18000cc61  mov     [rsp+14F0h+var_14A0], r13
0x18000cc66  mov     [rbp+13F0h+var_1448], rdi
0x18000cc6a  mov     [rbp+13F0h+var_1440], r15
0x18000cc6e  mov     [rsp+14F0h+var_1488], r13
0x18000cc73  xorps   xmm0, xmm0
0x18000cc76  xor     eax, eax
0x18000cc78  movups  [rbp+13F0h+var_1468], xmm0
0x18000cc7c  mov     [rbp+13F0h+var_1458], rax
0x18000cc80  xorps   xmm1, xmm1
0x18000cc83  movups  [rsp+14F0h+var_1480], xmm1
0x18000cc88  mov     [rbp+13F0h+var_1470], rax
0x18000cc8c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cc93  test    rax, rax
0x18000cc96  jz      short loc_18000CCA3
0x18000cc98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc9d  mov     [rbp+13F0h+var_1450], rax
0x18000cca1  jmp     short loc_18000CCA7
0x18000cca3  mov     [rbp+13F0h+var_1450], r13
0x18000cca7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ccae  test    rax, rax
0x18000ccb1  jz      short loc_18000CCBD
0x18000ccb3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ccb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccbd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ccc4  test    rax, rax
0x18000ccc7  jz      short loc_18000CCDD
0x18000ccc9  mov     r8d, 400h
0x18000cccf  lea     rdx, [rbp+13F0h+var_1430]
0x18000ccd3  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ccd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccdd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cce4  test    rax, rax
0x18000cce7  jz      short loc_18000CCF3
0x18000cce9  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ccee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccf3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ccfa  test    rax, rax
0x18000ccfd  jz      short loc_18000CD15
0x18000ccff  test    r12b, r12b
0x18000cd02  jnz     short loc_18000CD15
0x18000cd04  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cd09  jnz     short loc_18000CD15
0x18000cd0b  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cd10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd15  cmp     [rsp+14F0h+var_14C8], r13d
0x18000cd1a  jl      short loc_18000CD22
0x18000cd1c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000cd22  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, r13b; bool wil::g_fIsDebuggerPresent
0x18000cd29  jnz     short loc_18000CD4A
0x18000cd2b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cd32  test    rax, rax
0x18000cd35  jz      short loc_18000CD40
0x18000cd37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd3c  test    al, al
0x18000cd3e  jmp     short loc_18000CD48
0x18000cd40  call    cs:__imp_IsDebuggerPresent
0x18000cd46  test    eax, eax
0x18000cd48  jz      short loc_18000CD53
0x18000cd4a  test    byte ptr [rsp+14F0h+var_14D0+4], 2
0x18000cd4f  mov     bl, 1
0x18000cd51  jz      short loc_18000CD56
0x18000cd53  mov     bl, r13b
0x18000cd56  test    r12b, r12b
0x18000cd59  jnz     short loc_18000CD85
0x18000cd5b  test    bl, bl
0x18000cd5d  jnz     short loc_18000CD85
0x18000cd5f  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cd66  test    rax, rax
0x18000cd69  jz      short loc_18000CDE2
0x18000cd6b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000cd72  jnz     short loc_18000CDE2
0x18000cd74  xor     r8d, r8d
0x18000cd77  xor     edx, edx
0x18000cd79  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cd7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cd83  jmp     short loc_18000CDE2
0x18000cd85  mov     edi, 800h
0x18000cd8a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cd91  test    rax, rax
0x18000cd94  jz      short loc_18000CDB3
0x18000cd96  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, r13b; bool wil::details::g_resultMessageCallbackSet
0x18000cd9d  jnz     short loc_18000CDB3
0x18000cd9f  mov     r8d, edi
0x18000cda2  lea     rdx, [rbp+13F0h+OutputString]
0x18000cda9  lea     rcx, [rsp+14F0h+var_14D0]
0x18000cdae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdb3  cmp     [rbp+13F0h+OutputString], r13w
0x18000cdbb  jnz     short loc_18000CDD1
0x18000cdbd  lea     r8, [rsp+14F0h+var_14D0]; unsigned __int64
0x18000cdc2  mov     rdx, rdi; unsigned __int16 *
0x18000cdc5  lea     rcx, [rbp+13F0h+OutputString]; this
0x18000cdcc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cdd1  test    bl, bl
0x18000cdd3  jz      short loc_18000CDE2
0x18000cdd5  lea     rcx, [rbp+13F0h+OutputString]; lpOutputString
0x18000cddc  call    cs:__imp_OutputDebugStringW
0x18000cde2  test    byte ptr [rsp+14F0h+var_14D0+4], 4
0x18000cde7  jnz     short loc_18000CDF2
0x18000cde9  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, r13b; bool wil::g_fBreakOnFailure
0x18000cdf0  jz      short loc_18000CE04
0x18000cdf2  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cdf9  test    rax, rax
0x18000cdfc  jz      short loc_18000CE04
0x18000cdfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce03  nop
0x18000ce04  test    byte ptr [rsp+14F0h+var_14D0+4], 1
0x18000ce09  jz      short loc_18000CE16
0x18000ce0b  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ce10  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
0x18000ce16  test    r12b, r12b
0x18000ce19  jz      short loc_18000CE33
0x18000ce1b  lea     rdx, [rbp+13F0h+OutputString]
0x18000ce22  lea     rcx, [rsp+14F0h+var_14D0]
0x18000ce27  mov     rax, cs:g_pfnThrowPlatformException
0x18000ce2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ce33  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ce38  call    ?ThrowResultException@wil@@YAXAEBUFailureInfo@1@@Z; wil::ThrowResultException(wil::FailureInfo const &)
0x18000ce3d  lea     rcx, [rsp+14F0h+var_14D0]; this
0x18000ce42  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
