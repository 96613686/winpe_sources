# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800054e0`
- end: `0x1800057d9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000323c`

## callees

- `0x180002c80`
- `0x180004b54`
- `0x1800052f4`
- `0x1800054e0`
- `0x180005b0c`
- `0x180005b30`
- `0x180005b44`
- `0x180005b60`
- `0x180006e34`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005603`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005603`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005722`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005722`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005794`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005794`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x1800054e0  mov     [rsp+arg_10], rbx
0x1800054e5  mov     [rsp+arg_8], edx
0x1800054e9  mov     [rsp+arg_0], rcx
0x1800054ee  push    rbp
0x1800054ef  push    rsi
0x1800054f0  push    rdi
0x1800054f1  push    r12
0x1800054f3  push    r13
0x1800054f5  push    r14
0x1800054f7  push    r15
0x1800054f9  sub     rsp, 40h
0x1800054fd  mov     r12, r9
0x180005500  mov     r13, r8
0x180005503  mov     r10, rcx
0x180005506  xor     eax, eax
0x180005508  mov     rsi, [rsp+78h+lpOutputString]
0x180005510  mov     [rsi], ax
0x180005513  mov     rax, [rsp+78h+arg_60]
0x18000551b  mov     byte ptr [rax], 0
0x18000551e  mov     r14, [rsp+78h+arg_38]
0x180005526  mov     edi, [r14]
0x180005529  mov     rbx, [rsp+78h+arg_78]
0x180005531  mov     [rbx+8], edi
0x180005534  mov     eax, [r14+4]
0x180005538  mov     [rbx+0Ch], eax
0x18000553b  xor     ebp, ebp
0x18000553d  mov     r15d, [rsp+78h+arg_30]
0x180005545  mov     ecx, r15d
0x180005548  test    r15d, r15d
0x18000554b  jz      short loc_1800055B3
0x18000554d  sub     ecx, 1
0x180005550  jz      short loc_1800055AA
0x180005552  sub     ecx, 1
0x180005555  jz      short loc_180005565
0x180005557  cmp     ecx, 1
0x18000555a  jnz     short loc_1800055BC
0x18000555c  mov     ecx, edi; this
0x18000555e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005563  jmp     short loc_1800055BA
0x180005565  test    edi, edi
0x180005567  js      short loc_1800055A1
0x180005569  mov     edi, 8007029Ch
0x18000556e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005572  mov     rax, [rsp+78h+arg_28]
0x18000557a  mov     [rsp+78h+var_50], rax; __int64
0x18000557f  mov     rax, [rsp+78h+arg_20]
0x180005587  mov     [rsp+78h+var_58], rax; __int64
0x18000558c  mov     rcx, r10; int
0x18000558f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005594  mov     [rbx+8], edi
0x180005597  mov     ecx, edi; this
0x180005599  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000559e  mov     [rbx+0Ch], eax
0x1800055a1  mov     ecx, edi; this
0x1800055a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800055a8  jmp     short loc_1800055BA
0x1800055aa  mov     ecx, edi; this
0x1800055ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800055b1  jmp     short loc_1800055BA
0x1800055b3  mov     ecx, edi; this
0x1800055b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800055ba  mov     ebp, eax
0x1800055bc  mov     [rbx], r15d
0x1800055bf  mov     eax, [rsp+78h+arg_70]
0x1800055c6  mov     [rbx+4], eax
0x1800055c9  cmp     dword ptr [r14+8], 1
0x1800055ce  jnz     short loc_1800055D6
0x1800055d0  or      eax, 8
0x1800055d3  mov     [rbx+4], eax
0x1800055d6  mov     eax, 1
0x1800055db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800055e3  inc     eax
0x1800055e5  mov     [rbx+10h], eax
0x1800055e8  mov     rax, [rsp+78h+arg_40]
0x1800055f0  xor     edi, edi
0x1800055f2  test    rax, rax
0x1800055f5  jz      short loc_1800055FC
0x1800055f7  cmp     [rax], di
0x1800055fa  jnz     short loc_1800055FF
0x1800055fc  mov     rax, rdi
0x1800055ff  mov     [rbx+18h], rax
0x180005603  call    cs:__imp_GetCurrentThreadId
0x180005609  mov     [rbx+20h], eax
0x18000560c  mov     [rbx+38h], r13
0x180005610  mov     eax, [rsp+78h+arg_8]
0x180005617  mov     [rbx+40h], eax
0x18000561a  mov     [rbx+44h], ebp
0x18000561d  mov     rax, [rsp+78h+arg_20]
0x180005625  mov     [rbx+28h], rax
0x180005629  mov     [rbx+30h], r12
0x18000562d  mov     rax, [rsp+78h+arg_28]
0x180005635  mov     [rbx+88h], rax
0x18000563c  mov     rax, [rsp+78h+arg_0]
0x180005644  mov     [rbx+90h], rax
0x18000564b  mov     [rbx+48h], rdi
0x18000564f  xorps   xmm0, xmm0
0x180005652  xor     eax, eax
0x180005654  movups  xmmword ptr [rbx+68h], xmm0
0x180005658  mov     [rbx+78h], rax
0x18000565c  movups  xmmword ptr [rbx+50h], xmm0
0x180005660  mov     [rbx+60h], rax
0x180005664  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000566b  test    rax, rax
0x18000566e  jz      short loc_180005677
0x180005670  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005675  jmp     short loc_18000567A
0x180005677  mov     rax, rdi
0x18000567a  mov     [rbx+80h], rax
0x180005681  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005688  test    rax, rax
0x18000568b  jz      short loc_180005695
0x18000568d  mov     rcx, rbx
0x180005690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005695  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000569c  test    rax, rax
0x18000569f  jz      short loc_1800056B7
0x1800056a1  mov     r8d, 400h
0x1800056a7  mov     rdx, [rsp+78h+arg_60]
0x1800056af  mov     rcx, rbx
0x1800056b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056be  test    rax, rax
0x1800056c1  jz      short loc_1800056CB
0x1800056c3  mov     rcx, rbx
0x1800056c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056d2  test    rax, rax
0x1800056d5  jz      short loc_1800056E5
0x1800056d7  test    byte ptr [rbx+4], 2
0x1800056db  jnz     short loc_1800056E5
0x1800056dd  mov     rcx, rbx
0x1800056e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056e5  cmp     [rbx+8], edi
0x1800056e8  jl      short loc_180005704
0x1800056ea  cmp     r15d, 3
0x1800056ee  jnz     loc_1800057D3
0x1800056f4  mov     ecx, 8000FFFFh; this
0x1800056f9  mov     [rbx+8], ecx
0x1800056fc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005701  mov     [rbx+0Ch], eax
0x180005704  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000570b  jnz     short loc_18000572C
0x18000570d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005714  test    rax, rax
0x180005717  jz      short loc_180005722
0x180005719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571e  test    al, al
0x180005720  jmp     short loc_18000572A
0x180005722  call    cs:__imp_IsDebuggerPresent
0x180005728  test    eax, eax
0x18000572a  jz      short loc_180005732
0x18000572c  test    byte ptr [rbx+4], 2
0x180005730  jz      short loc_180005756
0x180005732  mov     rax, cs:g_pfnResultLoggingCallback
0x180005739  test    rax, rax
0x18000573c  jz      short loc_18000579A
0x18000573e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005745  jnz     short loc_18000579A
0x180005747  xor     r8d, r8d
0x18000574a  xor     edx, edx
0x18000574c  mov     rcx, rbx
0x18000574f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005754  jmp     short loc_18000579A
0x180005756  mov     ebp, 800h
0x18000575b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005762  test    rax, rax
0x180005765  jz      short loc_18000577E
0x180005767  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000576e  jnz     short loc_18000577E
0x180005770  mov     r8d, ebp
0x180005773  mov     rdx, rsi
0x180005776  mov     rcx, rbx
0x180005779  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000577e  cmp     [rsi], di
0x180005781  jnz     short loc_180005791
0x180005783  mov     r8, rbx; unsigned __int64
0x180005786  mov     rdx, rbp; unsigned __int16 *
0x180005789  mov     rcx, rsi; this
0x18000578c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005791  mov     rcx, rsi; lpOutputString
0x180005794  call    cs:__imp_OutputDebugStringW
0x18000579a  test    byte ptr [rbx+4], 4
0x18000579e  jnz     short loc_1800057A9
0x1800057a0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800057a7  jz      short loc_1800057BB
0x1800057a9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800057b0  test    rax, rax
0x1800057b3  jz      short loc_1800057BB
0x1800057b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057ba  nop
0x1800057bb  mov     rbx, [rsp+78h+arg_10]
0x1800057c3  add     rsp, 40h
0x1800057c7  pop     r15
0x1800057c9  pop     r14
0x1800057cb  pop     r13
0x1800057cd  pop     r12
0x1800057cf  pop     rdi
0x1800057d0  pop     rsi
0x1800057d1  pop     rbp
0x1800057d2  retn
0x1800057d3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
