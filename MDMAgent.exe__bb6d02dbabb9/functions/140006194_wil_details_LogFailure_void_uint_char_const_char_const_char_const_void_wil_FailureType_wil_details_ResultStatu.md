# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006194`
- end: `0x1400064a0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003df4`
- `0x140004174`

## callees

- `0x140003d2c`
- `0x140005534`
- `0x140005ed4`
- `0x140006194`
- `0x1400068d4`
- `0x140006900`
- `0x140006914`
- `0x140006934`
- `0x140007c78`
- `0x14001a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400062b7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400062b7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400063dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400063dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006454`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006454`

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
0x140006194  mov     [rsp+arg_10], rbx
0x140006199  mov     [rsp+arg_8], edx
0x14000619d  mov     [rsp+arg_0], rcx
0x1400061a2  push    rbp
0x1400061a3  push    rsi
0x1400061a4  push    rdi
0x1400061a5  push    r12
0x1400061a7  push    r13
0x1400061a9  push    r14
0x1400061ab  push    r15
0x1400061ad  sub     rsp, 40h
0x1400061b1  mov     r12, r9
0x1400061b4  mov     r13, r8
0x1400061b7  mov     r10, rcx
0x1400061ba  xor     eax, eax
0x1400061bc  mov     rsi, [rsp+78h+lpOutputString]
0x1400061c4  mov     [rsi], ax
0x1400061c7  mov     rax, [rsp+78h+arg_60]
0x1400061cf  mov     byte ptr [rax], 0
0x1400061d2  mov     r14, [rsp+78h+arg_38]
0x1400061da  mov     edi, [r14]
0x1400061dd  mov     rbx, [rsp+78h+arg_78]
0x1400061e5  mov     [rbx+8], edi
0x1400061e8  mov     eax, [r14+4]
0x1400061ec  mov     [rbx+0Ch], eax
0x1400061ef  xor     ebp, ebp
0x1400061f1  mov     r15d, [rsp+78h+arg_30]
0x1400061f9  mov     ecx, r15d
0x1400061fc  test    r15d, r15d
0x1400061ff  jz      short loc_140006267
0x140006201  sub     ecx, 1
0x140006204  jz      short loc_14000625E
0x140006206  sub     ecx, 1
0x140006209  jz      short loc_140006219
0x14000620b  cmp     ecx, 1
0x14000620e  jnz     short loc_140006270
0x140006210  mov     ecx, edi; this
0x140006212  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006217  jmp     short loc_14000626E
0x140006219  test    edi, edi
0x14000621b  js      short loc_140006255
0x14000621d  mov     edi, 8007029Ch
0x140006222  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006226  mov     rax, [rsp+78h+arg_28]
0x14000622e  mov     [rsp+78h+var_50], rax; __int64
0x140006233  mov     rax, [rsp+78h+arg_20]
0x14000623b  mov     [rsp+78h+var_58], rax; __int64
0x140006240  mov     rcx, r10; int
0x140006243  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006248  mov     [rbx+8], edi
0x14000624b  mov     ecx, edi; this
0x14000624d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006252  mov     [rbx+0Ch], eax
0x140006255  mov     ecx, edi; this
0x140006257  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000625c  jmp     short loc_14000626E
0x14000625e  mov     ecx, edi; this
0x140006260  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006265  jmp     short loc_14000626E
0x140006267  mov     ecx, edi; this
0x140006269  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000626e  mov     ebp, eax
0x140006270  mov     [rbx], r15d
0x140006273  mov     eax, [rsp+78h+arg_70]
0x14000627a  mov     [rbx+4], eax
0x14000627d  cmp     dword ptr [r14+8], 1
0x140006282  jnz     short loc_14000628A
0x140006284  or      eax, 8
0x140006287  mov     [rbx+4], eax
0x14000628a  mov     eax, 1
0x14000628f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006297  inc     eax
0x140006299  mov     [rbx+10h], eax
0x14000629c  mov     rax, [rsp+78h+arg_40]
0x1400062a4  xor     edi, edi
0x1400062a6  test    rax, rax
0x1400062a9  jz      short loc_1400062B0
0x1400062ab  cmp     [rax], di
0x1400062ae  jnz     short loc_1400062B3
0x1400062b0  mov     rax, rdi
0x1400062b3  mov     [rbx+18h], rax
0x1400062b7  call    cs:__imp_GetCurrentThreadId
0x1400062be  nop     dword ptr [rax+rax+00h]
0x1400062c3  mov     [rbx+20h], eax
0x1400062c6  mov     [rbx+38h], r13
0x1400062ca  mov     eax, [rsp+78h+arg_8]
0x1400062d1  mov     [rbx+40h], eax
0x1400062d4  mov     [rbx+44h], ebp
0x1400062d7  mov     rax, [rsp+78h+arg_20]
0x1400062df  mov     [rbx+28h], rax
0x1400062e3  mov     [rbx+30h], r12
0x1400062e7  mov     rax, [rsp+78h+arg_28]
0x1400062ef  mov     [rbx+88h], rax
0x1400062f6  mov     rax, [rsp+78h+arg_0]
0x1400062fe  mov     [rbx+90h], rax
0x140006305  mov     [rbx+48h], rdi
0x140006309  xorps   xmm0, xmm0
0x14000630c  xor     eax, eax
0x14000630e  movups  xmmword ptr [rbx+68h], xmm0
0x140006312  mov     [rbx+78h], rax
0x140006316  movups  xmmword ptr [rbx+50h], xmm0
0x14000631a  mov     [rbx+60h], rax
0x14000631e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006325  test    rax, rax
0x140006328  jz      short loc_140006331
0x14000632a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000632f  jmp     short loc_140006334
0x140006331  mov     rax, rdi
0x140006334  mov     [rbx+80h], rax
0x14000633b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006342  test    rax, rax
0x140006345  jz      short loc_14000634F
0x140006347  mov     rcx, rbx
0x14000634a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000634f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006356  test    rax, rax
0x140006359  jz      short loc_140006371
0x14000635b  mov     r8d, 400h
0x140006361  mov     rdx, [rsp+78h+arg_60]
0x140006369  mov     rcx, rbx
0x14000636c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006371  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006378  test    rax, rax
0x14000637b  jz      short loc_140006385
0x14000637d  mov     rcx, rbx
0x140006380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006385  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000638c  test    rax, rax
0x14000638f  jz      short loc_14000639F
0x140006391  test    byte ptr [rbx+4], 2
0x140006395  jnz     short loc_14000639F
0x140006397  mov     rcx, rbx
0x14000639a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000639f  cmp     [rbx+8], edi
0x1400063a2  jl      short loc_1400063BE
0x1400063a4  cmp     r15d, 3
0x1400063a8  jnz     loc_14000649A
0x1400063ae  mov     ecx, 8000FFFFh; this
0x1400063b3  mov     [rbx+8], ecx
0x1400063b6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400063bb  mov     [rbx+0Ch], eax
0x1400063be  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400063c5  jnz     short loc_1400063EC
0x1400063c7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400063ce  test    rax, rax
0x1400063d1  jz      short loc_1400063DC
0x1400063d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400063d8  test    al, al
0x1400063da  jmp     short loc_1400063EA
0x1400063dc  call    cs:__imp_IsDebuggerPresent
0x1400063e3  nop     dword ptr [rax+rax+00h]
0x1400063e8  test    eax, eax
0x1400063ea  jz      short loc_1400063F2
0x1400063ec  test    byte ptr [rbx+4], 2
0x1400063f0  jz      short loc_140006416
0x1400063f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400063f9  test    rax, rax
0x1400063fc  jz      short loc_140006460
0x1400063fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006405  jnz     short loc_140006460
0x140006407  xor     r8d, r8d
0x14000640a  xor     edx, edx
0x14000640c  mov     rcx, rbx
0x14000640f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006414  jmp     short loc_140006460
0x140006416  mov     ebp, 800h
0x14000641b  mov     rax, cs:g_pfnResultLoggingCallback
0x140006422  test    rax, rax
0x140006425  jz      short loc_14000643E
0x140006427  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000642e  jnz     short loc_14000643E
0x140006430  mov     r8d, ebp
0x140006433  mov     rdx, rsi
0x140006436  mov     rcx, rbx
0x140006439  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000643e  cmp     [rsi], di
0x140006441  jnz     short loc_140006451
0x140006443  mov     r8, rbx; unsigned __int64
0x140006446  mov     rdx, rbp; unsigned __int16 *
0x140006449  mov     rcx, rsi; this
0x14000644c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006451  mov     rcx, rsi; lpOutputString
0x140006454  call    cs:__imp_OutputDebugStringW
0x14000645b  nop     dword ptr [rax+rax+00h]
0x140006460  test    byte ptr [rbx+4], 4
0x140006464  jnz     short loc_14000646F
0x140006466  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000646d  jz      short loc_140006481
0x14000646f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006476  test    rax, rax
0x140006479  jz      short loc_140006481
0x14000647b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006480  nop
0x140006481  mov     rbx, [rsp+78h+arg_10]
0x140006489  add     rsp, 40h
0x14000648d  pop     r15
0x14000648f  pop     r14
0x140006491  pop     r13
0x140006493  pop     r12
0x140006495  pop     rdi
0x140006496  pop     rsi
0x140006497  pop     rbp
0x140006498  retn
0x14000649a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
