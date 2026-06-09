# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800054b8`
- end: `0x1800057b1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000374c`

## callees

- `0x180003158`
- `0x180004994`
- `0x180005188`
- `0x1800054b8`
- `0x180005b40`
- `0x180005b60`
- `0x180005b74`
- `0x180005b90`
- `0x1800070e4`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000576c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000576c`

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
0x1800054b8  mov     [rsp+arg_10], rbx
0x1800054bd  mov     [rsp+arg_8], edx
0x1800054c1  mov     [rsp+arg_0], rcx
0x1800054c6  push    rbp
0x1800054c7  push    rsi
0x1800054c8  push    rdi
0x1800054c9  push    r12
0x1800054cb  push    r13
0x1800054cd  push    r14
0x1800054cf  push    r15
0x1800054d1  sub     rsp, 40h
0x1800054d5  mov     r12, r9
0x1800054d8  mov     r13, r8
0x1800054db  mov     r10, rcx
0x1800054de  xor     eax, eax
0x1800054e0  mov     rsi, [rsp+78h+lpOutputString]
0x1800054e8  mov     [rsi], ax
0x1800054eb  mov     rax, [rsp+78h+arg_60]
0x1800054f3  mov     byte ptr [rax], 0
0x1800054f6  mov     r14, [rsp+78h+arg_38]
0x1800054fe  mov     edi, [r14]
0x180005501  mov     rbx, [rsp+78h+arg_78]
0x180005509  mov     [rbx+8], edi
0x18000550c  mov     eax, [r14+4]
0x180005510  mov     [rbx+0Ch], eax
0x180005513  xor     ebp, ebp
0x180005515  mov     r15d, [rsp+78h+arg_30]
0x18000551d  mov     ecx, r15d
0x180005520  test    r15d, r15d
0x180005523  jz      short loc_18000558B
0x180005525  sub     ecx, 1
0x180005528  jz      short loc_180005582
0x18000552a  sub     ecx, 1
0x18000552d  jz      short loc_18000553D
0x18000552f  cmp     ecx, 1
0x180005532  jnz     short loc_180005594
0x180005534  mov     ecx, edi; this
0x180005536  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000553b  jmp     short loc_180005592
0x18000553d  test    edi, edi
0x18000553f  js      short loc_180005579
0x180005541  mov     edi, 8007029Ch
0x180005546  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000554a  mov     rax, [rsp+78h+arg_28]
0x180005552  mov     [rsp+78h+var_50], rax; __int64
0x180005557  mov     rax, [rsp+78h+arg_20]
0x18000555f  mov     [rsp+78h+var_58], rax; __int64
0x180005564  mov     rcx, r10; int
0x180005567  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000556c  mov     [rbx+8], edi
0x18000556f  mov     ecx, edi; this
0x180005571  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005576  mov     [rbx+0Ch], eax
0x180005579  mov     ecx, edi; this
0x18000557b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005580  jmp     short loc_180005592
0x180005582  mov     ecx, edi; this
0x180005584  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005589  jmp     short loc_180005592
0x18000558b  mov     ecx, edi; this
0x18000558d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005592  mov     ebp, eax
0x180005594  mov     [rbx], r15d
0x180005597  mov     eax, [rsp+78h+arg_70]
0x18000559e  mov     [rbx+4], eax
0x1800055a1  cmp     dword ptr [r14+8], 1
0x1800055a6  jnz     short loc_1800055AE
0x1800055a8  or      eax, 8
0x1800055ab  mov     [rbx+4], eax
0x1800055ae  mov     eax, 1
0x1800055b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800055bb  inc     eax
0x1800055bd  mov     [rbx+10h], eax
0x1800055c0  mov     rax, [rsp+78h+arg_40]
0x1800055c8  xor     edi, edi
0x1800055ca  test    rax, rax
0x1800055cd  jz      short loc_1800055D4
0x1800055cf  cmp     [rax], di
0x1800055d2  jnz     short loc_1800055D7
0x1800055d4  mov     rax, rdi
0x1800055d7  mov     [rbx+18h], rax
0x1800055db  call    cs:__imp_GetCurrentThreadId
0x1800055e1  mov     [rbx+20h], eax
0x1800055e4  mov     [rbx+38h], r13
0x1800055e8  mov     eax, [rsp+78h+arg_8]
0x1800055ef  mov     [rbx+40h], eax
0x1800055f2  mov     [rbx+44h], ebp
0x1800055f5  mov     rax, [rsp+78h+arg_20]
0x1800055fd  mov     [rbx+28h], rax
0x180005601  mov     [rbx+30h], r12
0x180005605  mov     rax, [rsp+78h+arg_28]
0x18000560d  mov     [rbx+88h], rax
0x180005614  mov     rax, [rsp+78h+arg_0]
0x18000561c  mov     [rbx+90h], rax
0x180005623  mov     [rbx+48h], rdi
0x180005627  xorps   xmm0, xmm0
0x18000562a  xor     eax, eax
0x18000562c  movups  xmmword ptr [rbx+68h], xmm0
0x180005630  mov     [rbx+78h], rax
0x180005634  movups  xmmword ptr [rbx+50h], xmm0
0x180005638  mov     [rbx+60h], rax
0x18000563c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005643  test    rax, rax
0x180005646  jz      short loc_18000564F
0x180005648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000564d  jmp     short loc_180005652
0x18000564f  mov     rax, rdi
0x180005652  mov     [rbx+80h], rax
0x180005659  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005660  test    rax, rax
0x180005663  jz      short loc_18000566D
0x180005665  mov     rcx, rbx
0x180005668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005674  test    rax, rax
0x180005677  jz      short loc_18000568F
0x180005679  mov     r8d, 400h
0x18000567f  mov     rdx, [rsp+78h+arg_60]
0x180005687  mov     rcx, rbx
0x18000568a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000568f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005696  test    rax, rax
0x180005699  jz      short loc_1800056A3
0x18000569b  mov     rcx, rbx
0x18000569e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800056aa  test    rax, rax
0x1800056ad  jz      short loc_1800056BD
0x1800056af  test    byte ptr [rbx+4], 2
0x1800056b3  jnz     short loc_1800056BD
0x1800056b5  mov     rcx, rbx
0x1800056b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056bd  cmp     [rbx+8], edi
0x1800056c0  jl      short loc_1800056DC
0x1800056c2  cmp     r15d, 3
0x1800056c6  jnz     loc_1800057AB
0x1800056cc  mov     ecx, 8000FFFFh; this
0x1800056d1  mov     [rbx+8], ecx
0x1800056d4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800056d9  mov     [rbx+0Ch], eax
0x1800056dc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800056e3  jnz     short loc_180005704
0x1800056e5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800056ec  test    rax, rax
0x1800056ef  jz      short loc_1800056FA
0x1800056f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f6  test    al, al
0x1800056f8  jmp     short loc_180005702
0x1800056fa  call    cs:__imp_IsDebuggerPresent
0x180005700  test    eax, eax
0x180005702  jz      short loc_18000570A
0x180005704  test    byte ptr [rbx+4], 2
0x180005708  jz      short loc_18000572E
0x18000570a  mov     rax, cs:g_pfnResultLoggingCallback
0x180005711  test    rax, rax
0x180005714  jz      short loc_180005772
0x180005716  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000571d  jnz     short loc_180005772
0x18000571f  xor     r8d, r8d
0x180005722  xor     edx, edx
0x180005724  mov     rcx, rbx
0x180005727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000572c  jmp     short loc_180005772
0x18000572e  mov     ebp, 800h
0x180005733  mov     rax, cs:g_pfnResultLoggingCallback
0x18000573a  test    rax, rax
0x18000573d  jz      short loc_180005756
0x18000573f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005746  jnz     short loc_180005756
0x180005748  mov     r8d, ebp
0x18000574b  mov     rdx, rsi
0x18000574e  mov     rcx, rbx
0x180005751  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005756  cmp     [rsi], di
0x180005759  jnz     short loc_180005769
0x18000575b  mov     r8, rbx; unsigned __int64
0x18000575e  mov     rdx, rbp; unsigned __int16 *
0x180005761  mov     rcx, rsi; this
0x180005764  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005769  mov     rcx, rsi; lpOutputString
0x18000576c  call    cs:__imp_OutputDebugStringW
0x180005772  test    byte ptr [rbx+4], 4
0x180005776  jnz     short loc_180005781
0x180005778  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000577f  jz      short loc_180005793
0x180005781  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005788  test    rax, rax
0x18000578b  jz      short loc_180005793
0x18000578d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005792  nop
0x180005793  mov     rbx, [rsp+78h+arg_10]
0x18000579b  add     rsp, 40h
0x18000579f  pop     r15
0x1800057a1  pop     r14
0x1800057a3  pop     r13
0x1800057a5  pop     r12
0x1800057a7  pop     rdi
0x1800057a8  pop     rsi
0x1800057a9  pop     rbp
0x1800057aa  retn
0x1800057ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
