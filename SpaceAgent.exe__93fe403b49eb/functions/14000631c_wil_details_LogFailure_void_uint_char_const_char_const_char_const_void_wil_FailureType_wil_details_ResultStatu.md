# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000631c`
- end: `0x140006614`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003b2c`
- `0x140003e78`

## callees

- `0x140003a6c`
- `0x140005734`
- `0x140005f3c`
- `0x14000631c`
- `0x140007144`
- `0x140007160`
- `0x1400072e4`
- `0x140007300`
- `0x140009294`
- `0x140020010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14000655e`
- `KERNEL32!IsDebuggerPresent` at `0x14000655e`
- `KERNEL32!GetCurrentThreadId` at `0x14000643f`
- `KERNEL32!GetCurrentThreadId` at `0x14000643f`
- `KERNEL32!OutputDebugStringW` at `0x1400065d0`
- `KERNEL32!OutputDebugStringW` at `0x1400065d0`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x14000631c  mov     [rsp+arg_10], rbx
0x140006321  mov     [rsp+arg_8], edx
0x140006325  mov     [rsp+arg_0], rcx
0x14000632a  push    rbp
0x14000632b  push    rsi
0x14000632c  push    rdi
0x14000632d  push    r12
0x14000632f  push    r13
0x140006331  push    r14
0x140006333  push    r15
0x140006335  sub     rsp, 40h
0x140006339  mov     r14, [rsp+78h+arg_38]
0x140006341  xor     eax, eax
0x140006343  mov     rbx, [rsp+78h+arg_78]
0x14000634b  xor     ebp, ebp
0x14000634d  mov     r15d, [rsp+78h+arg_30]
0x140006355  mov     r10, rcx
0x140006358  mov     rsi, [rsp+78h+lpOutputString]
0x140006360  mov     r12, r9
0x140006363  mov     r13, r8
0x140006366  mov     ecx, r15d
0x140006369  mov     [rsi], ax
0x14000636c  mov     rax, [rsp+78h+arg_60]
0x140006374  mov     byte ptr [rax], 0
0x140006377  mov     edi, [r14]
0x14000637a  mov     [rbx+8], edi
0x14000637d  mov     eax, [r14+4]
0x140006381  mov     [rbx+0Ch], eax
0x140006384  test    r15d, r15d
0x140006387  jz      short loc_1400063EF
0x140006389  sub     ecx, 1
0x14000638c  jz      short loc_1400063E6
0x14000638e  sub     ecx, 1
0x140006391  jz      short loc_1400063A1
0x140006393  cmp     ecx, 1
0x140006396  jnz     short loc_1400063F8
0x140006398  mov     ecx, edi; this
0x14000639a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000639f  jmp     short loc_1400063F6
0x1400063a1  test    edi, edi
0x1400063a3  js      short loc_1400063DD
0x1400063a5  mov     rax, [rsp+78h+arg_28]
0x1400063ad  mov     edi, 8007029Ch
0x1400063b2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400063b6  mov     rcx, r10; int
0x1400063b9  mov     [rsp+78h+var_50], rax; __int64
0x1400063be  mov     rax, [rsp+78h+arg_20]
0x1400063c6  mov     [rsp+78h+var_58], rax; __int64
0x1400063cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400063d0  mov     ecx, edi; this
0x1400063d2  mov     [rbx+8], edi
0x1400063d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400063da  mov     [rbx+0Ch], eax
0x1400063dd  mov     ecx, edi; this
0x1400063df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400063e4  jmp     short loc_1400063F6
0x1400063e6  mov     ecx, edi; this
0x1400063e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400063ed  jmp     short loc_1400063F6
0x1400063ef  mov     ecx, edi; this
0x1400063f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400063f6  mov     ebp, eax
0x1400063f8  mov     eax, [rsp+78h+arg_70]
0x1400063ff  mov     [rbx+4], eax
0x140006402  mov     [rbx], r15d
0x140006405  cmp     dword ptr [r14+8], 1
0x14000640a  jnz     short loc_140006412
0x14000640c  or      eax, 8
0x14000640f  mov     [rbx+4], eax
0x140006412  mov     eax, 1
0x140006417  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000641f  inc     eax
0x140006421  xor     edi, edi
0x140006423  mov     [rbx+10h], eax
0x140006426  mov     rax, [rsp+78h+arg_40]
0x14000642e  test    rax, rax
0x140006431  jz      short loc_140006438
0x140006433  cmp     [rax], di
0x140006436  jnz     short loc_14000643B
0x140006438  mov     rax, rdi
0x14000643b  mov     [rbx+18h], rax
0x14000643f  call    cs:__imp_GetCurrentThreadId
0x140006445  mov     [rbx+38h], r13
0x140006449  xorps   xmm0, xmm0
0x14000644c  mov     [rbx+20h], eax
0x14000644f  mov     eax, [rsp+78h+arg_8]
0x140006456  mov     [rbx+40h], eax
0x140006459  mov     rax, [rsp+78h+arg_20]
0x140006461  mov     [rbx+28h], rax
0x140006465  mov     rax, [rsp+78h+arg_28]
0x14000646d  mov     [rbx+88h], rax
0x140006474  mov     rax, [rsp+78h+arg_0]
0x14000647c  mov     [rbx+90h], rax
0x140006483  xor     eax, eax
0x140006485  mov     [rbx+44h], ebp
0x140006488  mov     [rbx+30h], r12
0x14000648c  mov     [rbx+48h], rdi
0x140006490  movups  xmmword ptr [rbx+68h], xmm0
0x140006494  mov     [rbx+78h], rax
0x140006498  movups  xmmword ptr [rbx+50h], xmm0
0x14000649c  mov     [rbx+60h], rax
0x1400064a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400064a7  test    rax, rax
0x1400064aa  jz      short loc_1400064B3
0x1400064ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064b1  jmp     short loc_1400064B6
0x1400064b3  mov     rax, rdi
0x1400064b6  mov     [rbx+80h], rax
0x1400064bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400064c4  test    rax, rax
0x1400064c7  jz      short loc_1400064D1
0x1400064c9  mov     rcx, rbx
0x1400064cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400064d8  test    rax, rax
0x1400064db  jz      short loc_1400064F3
0x1400064dd  mov     rdx, [rsp+78h+arg_60]
0x1400064e5  mov     r8d, 400h
0x1400064eb  mov     rcx, rbx
0x1400064ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400064f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400064fa  test    rax, rax
0x1400064fd  jz      short loc_140006507
0x1400064ff  mov     rcx, rbx
0x140006502  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006507  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000650e  test    rax, rax
0x140006511  jz      short loc_140006521
0x140006513  test    byte ptr [rbx+4], 2
0x140006517  jnz     short loc_140006521
0x140006519  mov     rcx, rbx
0x14000651c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006521  cmp     [rbx+8], edi
0x140006524  jl      short loc_140006540
0x140006526  cmp     r15d, 3
0x14000652a  jnz     loc_14000660E
0x140006530  mov     ecx, 8000FFFFh; this
0x140006535  mov     [rbx+8], ecx
0x140006538  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000653d  mov     [rbx+0Ch], eax
0x140006540  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006547  jnz     short loc_140006568
0x140006549  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006550  test    rax, rax
0x140006553  jz      short loc_14000655E
0x140006555  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000655a  test    al, al
0x14000655c  jmp     short loc_140006566
0x14000655e  call    cs:__imp_IsDebuggerPresent
0x140006564  test    eax, eax
0x140006566  jz      short loc_14000656E
0x140006568  test    byte ptr [rbx+4], 2
0x14000656c  jz      short loc_140006592
0x14000656e  mov     rax, cs:g_pfnResultLoggingCallback
0x140006575  test    rax, rax
0x140006578  jz      short loc_1400065D6
0x14000657a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006581  jnz     short loc_1400065D6
0x140006583  xor     r8d, r8d
0x140006586  xor     edx, edx
0x140006588  mov     rcx, rbx
0x14000658b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006590  jmp     short loc_1400065D6
0x140006592  mov     rax, cs:g_pfnResultLoggingCallback
0x140006599  mov     ebp, 800h
0x14000659e  test    rax, rax
0x1400065a1  jz      short loc_1400065BA
0x1400065a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400065aa  jnz     short loc_1400065BA
0x1400065ac  mov     r8d, ebp
0x1400065af  mov     rdx, rsi
0x1400065b2  mov     rcx, rbx
0x1400065b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065ba  cmp     [rsi], di
0x1400065bd  jnz     short loc_1400065CD
0x1400065bf  mov     r8, rbx; unsigned __int64
0x1400065c2  mov     rdx, rbp; unsigned __int16 *
0x1400065c5  mov     rcx, rsi; this
0x1400065c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400065cd  mov     rcx, rsi; lpOutputString
0x1400065d0  call    cs:__imp_OutputDebugStringW
0x1400065d6  test    byte ptr [rbx+4], 4
0x1400065da  jnz     short loc_1400065E5
0x1400065dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400065e3  jz      short loc_1400065F6
0x1400065e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400065ec  test    rax, rax
0x1400065ef  jz      short loc_1400065F6
0x1400065f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065f6  mov     rbx, [rsp+78h+arg_10]
0x1400065fe  add     rsp, 40h
0x140006602  pop     r15
0x140006604  pop     r14
0x140006606  pop     r13
0x140006608  pop     r12
0x14000660a  pop     rdi
0x14000660b  pop     rsi
0x14000660c  pop     rbp
0x14000660d  retn
0x14000660e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
