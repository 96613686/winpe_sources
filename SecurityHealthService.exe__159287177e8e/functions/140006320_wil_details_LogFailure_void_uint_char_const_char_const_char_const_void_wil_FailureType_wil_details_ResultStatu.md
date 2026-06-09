# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006320`
- end: `0x140006619`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140005a0c`

## callees

- `0x140005714`
- `0x140005b60`
- `0x14000615c`
- `0x140006320`
- `0x140006b60`
- `0x140006b80`
- `0x140006b94`
- `0x140006bb0`
- `0x140006e3c`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006443`
- `KERNEL32!GetCurrentThreadId` at `0x140006443`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400065d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400065d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006562`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006562`

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
    ModuleName = wil::details::g_pfnGetModuleName();
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x140006320  mov     [rsp+arg_10], rbx
0x140006325  mov     [rsp+arg_8], edx
0x140006329  mov     [rsp+arg_0], rcx
0x14000632e  push    rbp
0x14000632f  push    rsi
0x140006330  push    rdi
0x140006331  push    r12
0x140006333  push    r13
0x140006335  push    r14
0x140006337  push    r15
0x140006339  sub     rsp, 40h
0x14000633d  mov     r12, r9
0x140006340  mov     r13, r8
0x140006343  mov     r10, rcx
0x140006346  xor     eax, eax
0x140006348  mov     rsi, [rsp+78h+lpOutputString]
0x140006350  mov     [rsi], ax
0x140006353  mov     rax, [rsp+78h+arg_60]
0x14000635b  mov     byte ptr [rax], 0
0x14000635e  mov     r14, [rsp+78h+arg_38]
0x140006366  mov     edi, [r14]
0x140006369  mov     rbx, [rsp+78h+arg_78]
0x140006371  mov     [rbx+8], edi
0x140006374  mov     eax, [r14+4]
0x140006378  mov     [rbx+0Ch], eax
0x14000637b  xor     ebp, ebp
0x14000637d  mov     r15d, [rsp+78h+arg_30]
0x140006385  mov     ecx, r15d
0x140006388  test    r15d, r15d
0x14000638b  jz      short loc_1400063F3
0x14000638d  sub     ecx, 1
0x140006390  jz      short loc_1400063EA
0x140006392  sub     ecx, 1
0x140006395  jz      short loc_1400063A5
0x140006397  cmp     ecx, 1
0x14000639a  jnz     short loc_1400063FC
0x14000639c  mov     ecx, edi; this
0x14000639e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400063a3  jmp     short loc_1400063FA
0x1400063a5  test    edi, edi
0x1400063a7  js      short loc_1400063E1
0x1400063a9  mov     edi, 8007029Ch
0x1400063ae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400063b2  mov     rax, [rsp+78h+arg_28]
0x1400063ba  mov     [rsp+78h+var_50], rax; __int64
0x1400063bf  mov     rax, [rsp+78h+arg_20]
0x1400063c7  mov     [rsp+78h+var_58], rax; __int64
0x1400063cc  mov     rcx, r10; int
0x1400063cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400063d4  mov     [rbx+8], edi
0x1400063d7  mov     ecx, edi; this
0x1400063d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400063de  mov     [rbx+0Ch], eax
0x1400063e1  mov     ecx, edi; this
0x1400063e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400063e8  jmp     short loc_1400063FA
0x1400063ea  mov     ecx, edi; this
0x1400063ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400063f1  jmp     short loc_1400063FA
0x1400063f3  mov     ecx, edi; this
0x1400063f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400063fa  mov     ebp, eax
0x1400063fc  mov     [rbx], r15d
0x1400063ff  mov     eax, [rsp+78h+arg_70]
0x140006406  mov     [rbx+4], eax
0x140006409  cmp     dword ptr [r14+8], 1
0x14000640e  jnz     short loc_140006416
0x140006410  or      eax, 8
0x140006413  mov     [rbx+4], eax
0x140006416  mov     eax, 1
0x14000641b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006423  inc     eax
0x140006425  mov     [rbx+10h], eax
0x140006428  mov     rax, [rsp+78h+arg_40]
0x140006430  xor     edi, edi
0x140006432  test    rax, rax
0x140006435  jz      short loc_14000643C
0x140006437  cmp     [rax], di
0x14000643a  jnz     short loc_14000643F
0x14000643c  mov     rax, rdi
0x14000643f  mov     [rbx+18h], rax
0x140006443  call    cs:__imp_GetCurrentThreadId
0x140006449  mov     [rbx+20h], eax
0x14000644c  mov     [rbx+38h], r13
0x140006450  mov     eax, [rsp+78h+arg_8]
0x140006457  mov     [rbx+40h], eax
0x14000645a  mov     [rbx+44h], ebp
0x14000645d  mov     rax, [rsp+78h+arg_20]
0x140006465  mov     [rbx+28h], rax
0x140006469  mov     [rbx+30h], r12
0x14000646d  mov     rax, [rsp+78h+arg_28]
0x140006475  mov     [rbx+88h], rax
0x14000647c  mov     rax, [rsp+78h+arg_0]
0x140006484  mov     [rbx+90h], rax
0x14000648b  mov     [rbx+48h], rdi
0x14000648f  xorps   xmm0, xmm0
0x140006492  xor     eax, eax
0x140006494  movups  xmmword ptr [rbx+68h], xmm0
0x140006498  mov     [rbx+78h], rax
0x14000649c  movups  xmmword ptr [rbx+50h], xmm0
0x1400064a0  mov     [rbx+60h], rax
0x1400064a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400064ab  test    rax, rax
0x1400064ae  jz      short loc_1400064B7
0x1400064b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064b5  jmp     short loc_1400064BA
0x1400064b7  mov     rax, rdi
0x1400064ba  mov     [rbx+80h], rax
0x1400064c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400064c8  test    rax, rax
0x1400064cb  jz      short loc_1400064D5
0x1400064cd  mov     rcx, rbx
0x1400064d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400064dc  test    rax, rax
0x1400064df  jz      short loc_1400064F7
0x1400064e1  mov     r8d, 400h
0x1400064e7  mov     rdx, [rsp+78h+arg_60]
0x1400064ef  mov     rcx, rbx
0x1400064f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400064fe  test    rax, rax
0x140006501  jz      short loc_14000650B
0x140006503  mov     rcx, rbx
0x140006506  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000650b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006512  test    rax, rax
0x140006515  jz      short loc_140006525
0x140006517  test    byte ptr [rbx+4], 2
0x14000651b  jnz     short loc_140006525
0x14000651d  mov     rcx, rbx
0x140006520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006525  cmp     [rbx+8], edi
0x140006528  jl      short loc_140006544
0x14000652a  cmp     r15d, 3
0x14000652e  jnz     loc_140006613
0x140006534  mov     ecx, 8000FFFFh; this
0x140006539  mov     [rbx+8], ecx
0x14000653c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006541  mov     [rbx+0Ch], eax
0x140006544  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000654b  jnz     short loc_14000656C
0x14000654d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006554  test    rax, rax
0x140006557  jz      short loc_140006562
0x140006559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000655e  test    al, al
0x140006560  jmp     short loc_14000656A
0x140006562  call    cs:__imp_IsDebuggerPresent
0x140006568  test    eax, eax
0x14000656a  jz      short loc_140006572
0x14000656c  test    byte ptr [rbx+4], 2
0x140006570  jz      short loc_140006596
0x140006572  mov     rax, cs:g_pfnResultLoggingCallback
0x140006579  test    rax, rax
0x14000657c  jz      short loc_1400065DA
0x14000657e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006585  jnz     short loc_1400065DA
0x140006587  xor     r8d, r8d
0x14000658a  xor     edx, edx
0x14000658c  mov     rcx, rbx
0x14000658f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006594  jmp     short loc_1400065DA
0x140006596  mov     ebp, 800h
0x14000659b  mov     rax, cs:g_pfnResultLoggingCallback
0x1400065a2  test    rax, rax
0x1400065a5  jz      short loc_1400065BE
0x1400065a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400065ae  jnz     short loc_1400065BE
0x1400065b0  mov     r8d, ebp
0x1400065b3  mov     rdx, rsi
0x1400065b6  mov     rcx, rbx
0x1400065b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065be  cmp     [rsi], di
0x1400065c1  jnz     short loc_1400065D1
0x1400065c3  mov     r8, rbx; unsigned __int64
0x1400065c6  mov     rdx, rbp; unsigned __int16 *
0x1400065c9  mov     rcx, rsi; this
0x1400065cc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400065d1  mov     rcx, rsi; lpOutputString
0x1400065d4  call    cs:__imp_OutputDebugStringW
0x1400065da  test    byte ptr [rbx+4], 4
0x1400065de  jnz     short loc_1400065E9
0x1400065e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400065e7  jz      short loc_1400065FB
0x1400065e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400065f0  test    rax, rax
0x1400065f3  jz      short loc_1400065FB
0x1400065f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065fa  nop
0x1400065fb  mov     rbx, [rsp+78h+arg_10]
0x140006603  add     rsp, 40h
0x140006607  pop     r15
0x140006609  pop     r14
0x14000660b  pop     r13
0x14000660d  pop     r12
0x14000660f  pop     rdi
0x140006610  pop     rsi
0x140006611  pop     rbp
0x140006612  retn
0x140006613  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
