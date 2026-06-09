# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800102f0`
- end: `0x1800105e9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000e934`

## callees

- `0x18000e340`
- `0x18000f984`
- `0x18001012c`
- `0x1800102f0`
- `0x180010874`
- `0x180010890`
- `0x1800108a4`
- `0x1800108c0`
- `0x180011aec`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010413`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180010413`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800105a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800105a4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010532`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010532`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        int a2,
        __int64 a3,
        __int64 a4,
        __int64 a5,
        __int64 a6,
        int a7,
        unsigned int *a8,
        _WORD *a9,
        __int64 a10,
        wil *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // zf
  wil::details *v28; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v18 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v19 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v20;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v24);
  else
    ModuleName = 0;
  *(_QWORD *)(a16 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a16);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a16, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a16);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x1800102f0  mov     [rsp+arg_10], rbx
0x1800102f5  mov     [rsp+arg_8], edx
0x1800102f9  mov     [rsp+arg_0], rcx
0x1800102fe  push    rbp
0x1800102ff  push    rsi
0x180010300  push    rdi
0x180010301  push    r12
0x180010303  push    r13
0x180010305  push    r14
0x180010307  push    r15
0x180010309  sub     rsp, 40h
0x18001030d  mov     r12, r9
0x180010310  mov     r13, r8
0x180010313  mov     r10, rcx
0x180010316  xor     eax, eax
0x180010318  mov     rsi, [rsp+78h+lpOutputString]
0x180010320  mov     [rsi], ax
0x180010323  mov     rax, [rsp+78h+arg_60]
0x18001032b  mov     byte ptr [rax], 0
0x18001032e  mov     r14, [rsp+78h+arg_38]
0x180010336  mov     edi, [r14]
0x180010339  mov     rbx, [rsp+78h+arg_78]
0x180010341  mov     [rbx+8], edi
0x180010344  mov     eax, [r14+4]
0x180010348  mov     [rbx+0Ch], eax
0x18001034b  xor     ebp, ebp
0x18001034d  mov     r15d, [rsp+78h+arg_30]
0x180010355  mov     ecx, r15d
0x180010358  test    r15d, r15d
0x18001035b  jz      short loc_1800103C3
0x18001035d  sub     ecx, 1
0x180010360  jz      short loc_1800103BA
0x180010362  sub     ecx, 1
0x180010365  jz      short loc_180010375
0x180010367  cmp     ecx, 1
0x18001036a  jnz     short loc_1800103CC
0x18001036c  mov     ecx, edi; this
0x18001036e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180010373  jmp     short loc_1800103CA
0x180010375  test    edi, edi
0x180010377  js      short loc_1800103B1
0x180010379  mov     edi, 8007029Ch
0x18001037e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180010382  mov     rax, [rsp+78h+arg_28]
0x18001038a  mov     [rsp+78h+var_50], rax; __int64
0x18001038f  mov     rax, [rsp+78h+arg_20]
0x180010397  mov     [rsp+78h+var_58], rax; __int64
0x18001039c  mov     rcx, r10; int
0x18001039f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800103a4  mov     [rbx+8], edi
0x1800103a7  mov     ecx, edi; this
0x1800103a9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800103ae  mov     [rbx+0Ch], eax
0x1800103b1  mov     ecx, edi; this
0x1800103b3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800103b8  jmp     short loc_1800103CA
0x1800103ba  mov     ecx, edi; this
0x1800103bc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800103c1  jmp     short loc_1800103CA
0x1800103c3  mov     ecx, edi; this
0x1800103c5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800103ca  mov     ebp, eax
0x1800103cc  mov     [rbx], r15d
0x1800103cf  mov     eax, [rsp+78h+arg_70]
0x1800103d6  mov     [rbx+4], eax
0x1800103d9  cmp     dword ptr [r14+8], 1
0x1800103de  jnz     short loc_1800103E6
0x1800103e0  or      eax, 8
0x1800103e3  mov     [rbx+4], eax
0x1800103e6  mov     eax, 1
0x1800103eb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800103f3  inc     eax
0x1800103f5  mov     [rbx+10h], eax
0x1800103f8  mov     rax, [rsp+78h+arg_40]
0x180010400  xor     edi, edi
0x180010402  test    rax, rax
0x180010405  jz      short loc_18001040C
0x180010407  cmp     [rax], di
0x18001040a  jnz     short loc_18001040F
0x18001040c  mov     rax, rdi
0x18001040f  mov     [rbx+18h], rax
0x180010413  call    cs:__imp_GetCurrentThreadId
0x180010419  mov     [rbx+20h], eax
0x18001041c  mov     [rbx+38h], r13
0x180010420  mov     eax, [rsp+78h+arg_8]
0x180010427  mov     [rbx+40h], eax
0x18001042a  mov     [rbx+44h], ebp
0x18001042d  mov     rax, [rsp+78h+arg_20]
0x180010435  mov     [rbx+28h], rax
0x180010439  mov     [rbx+30h], r12
0x18001043d  mov     rax, [rsp+78h+arg_28]
0x180010445  mov     [rbx+88h], rax
0x18001044c  mov     rax, [rsp+78h+arg_0]
0x180010454  mov     [rbx+90h], rax
0x18001045b  mov     [rbx+48h], rdi
0x18001045f  xorps   xmm0, xmm0
0x180010462  xor     eax, eax
0x180010464  movups  xmmword ptr [rbx+68h], xmm0
0x180010468  mov     [rbx+78h], rax
0x18001046c  movups  xmmword ptr [rbx+50h], xmm0
0x180010470  mov     [rbx+60h], rax
0x180010474  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001047b  test    rax, rax
0x18001047e  jz      short loc_180010487
0x180010480  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010485  jmp     short loc_18001048A
0x180010487  mov     rax, rdi
0x18001048a  mov     [rbx+80h], rax
0x180010491  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010498  test    rax, rax
0x18001049b  jz      short loc_1800104A5
0x18001049d  mov     rcx, rbx
0x1800104a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104a5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800104ac  test    rax, rax
0x1800104af  jz      short loc_1800104C7
0x1800104b1  mov     r8d, 400h
0x1800104b7  mov     rdx, [rsp+78h+arg_60]
0x1800104bf  mov     rcx, rbx
0x1800104c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104c7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800104ce  test    rax, rax
0x1800104d1  jz      short loc_1800104DB
0x1800104d3  mov     rcx, rbx
0x1800104d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104db  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800104e2  test    rax, rax
0x1800104e5  jz      short loc_1800104F5
0x1800104e7  test    byte ptr [rbx+4], 2
0x1800104eb  jnz     short loc_1800104F5
0x1800104ed  mov     rcx, rbx
0x1800104f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800104f5  cmp     [rbx+8], edi
0x1800104f8  jl      short loc_180010514
0x1800104fa  cmp     r15d, 3
0x1800104fe  jnz     loc_1800105E3
0x180010504  mov     ecx, 8000FFFFh; this
0x180010509  mov     [rbx+8], ecx
0x18001050c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010511  mov     [rbx+0Ch], eax
0x180010514  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001051b  jnz     short loc_18001053C
0x18001051d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010524  test    rax, rax
0x180010527  jz      short loc_180010532
0x180010529  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001052e  test    al, al
0x180010530  jmp     short loc_18001053A
0x180010532  call    cs:__imp_IsDebuggerPresent
0x180010538  test    eax, eax
0x18001053a  jz      short loc_180010542
0x18001053c  test    byte ptr [rbx+4], 2
0x180010540  jz      short loc_180010566
0x180010542  mov     rax, cs:g_pfnResultLoggingCallback
0x180010549  test    rax, rax
0x18001054c  jz      short loc_1800105AA
0x18001054e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010555  jnz     short loc_1800105AA
0x180010557  xor     r8d, r8d
0x18001055a  xor     edx, edx
0x18001055c  mov     rcx, rbx
0x18001055f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010564  jmp     short loc_1800105AA
0x180010566  mov     ebp, 800h
0x18001056b  mov     rax, cs:g_pfnResultLoggingCallback
0x180010572  test    rax, rax
0x180010575  jz      short loc_18001058E
0x180010577  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001057e  jnz     short loc_18001058E
0x180010580  mov     r8d, ebp
0x180010583  mov     rdx, rsi
0x180010586  mov     rcx, rbx
0x180010589  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001058e  cmp     [rsi], di
0x180010591  jnz     short loc_1800105A1
0x180010593  mov     r8, rbx; unsigned __int64
0x180010596  mov     rdx, rbp; unsigned __int16 *
0x180010599  mov     rcx, rsi; this
0x18001059c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800105a1  mov     rcx, rsi; lpOutputString
0x1800105a4  call    cs:__imp_OutputDebugStringW
0x1800105aa  test    byte ptr [rbx+4], 4
0x1800105ae  jnz     short loc_1800105B9
0x1800105b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800105b7  jz      short loc_1800105CB
0x1800105b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800105c0  test    rax, rax
0x1800105c3  jz      short loc_1800105CB
0x1800105c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800105ca  nop
0x1800105cb  mov     rbx, [rsp+78h+arg_10]
0x1800105d3  add     rsp, 40h
0x1800105d7  pop     r15
0x1800105d9  pop     r14
0x1800105db  pop     r13
0x1800105dd  pop     r12
0x1800105df  pop     rdi
0x1800105e0  pop     rsi
0x1800105e1  pop     rbp
0x1800105e2  retn
0x1800105e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
