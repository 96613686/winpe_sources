# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002627c`
- end: `0x180026587`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180023d54`

## callees

- `0x1800235ec`
- `0x18002582c`
- `0x180026038`
- `0x18002627c`
- `0x180026cc8`
- `0x180026cf0`
- `0x180026e38`
- `0x180026e58`
- `0x180028cf0`
- `0x18005f010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800264c4`
- `KERNEL32!IsDebuggerPresent` at `0x1800264c4`
- `KERNEL32!OutputDebugStringW` at `0x18002653c`
- `KERNEL32!OutputDebugStringW` at `0x18002653c`
- `KERNEL32!GetCurrentThreadId` at `0x18002639f`
- `KERNEL32!GetCurrentThreadId` at `0x18002639f`

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
        v20 = wil::details::RecordReturn((wil::details *)v19);
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
        v20 = wil::details::RecordLog((wil::details *)v19);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19);
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
0x18002627c  mov     [rsp+arg_10], rbx
0x180026281  mov     [rsp+arg_8], edx
0x180026285  mov     [rsp+arg_0], rcx
0x18002628a  push    rbp
0x18002628b  push    rsi
0x18002628c  push    rdi
0x18002628d  push    r12
0x18002628f  push    r13
0x180026291  push    r14
0x180026293  push    r15
0x180026295  sub     rsp, 40h
0x180026299  mov     r14, [rsp+78h+arg_38]
0x1800262a1  xor     eax, eax
0x1800262a3  mov     rbx, [rsp+78h+arg_78]
0x1800262ab  xor     ebp, ebp
0x1800262ad  mov     r15d, [rsp+78h+arg_30]
0x1800262b5  mov     r10, rcx
0x1800262b8  mov     rsi, [rsp+78h+lpOutputString]
0x1800262c0  mov     r12, r9
0x1800262c3  mov     r13, r8
0x1800262c6  mov     ecx, r15d
0x1800262c9  mov     [rsi], ax
0x1800262cc  mov     rax, [rsp+78h+arg_60]
0x1800262d4  mov     byte ptr [rax], 0
0x1800262d7  mov     edi, [r14]
0x1800262da  mov     [rbx+8], edi
0x1800262dd  mov     eax, [r14+4]
0x1800262e1  mov     [rbx+0Ch], eax
0x1800262e4  test    r15d, r15d
0x1800262e7  jz      short loc_18002634F
0x1800262e9  sub     ecx, 1
0x1800262ec  jz      short loc_180026346
0x1800262ee  sub     ecx, 1
0x1800262f1  jz      short loc_180026301
0x1800262f3  cmp     ecx, 1
0x1800262f6  jnz     short loc_180026358
0x1800262f8  mov     ecx, edi; this
0x1800262fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800262ff  jmp     short loc_180026356
0x180026301  test    edi, edi
0x180026303  js      short loc_18002633D
0x180026305  mov     rax, [rsp+78h+arg_28]
0x18002630d  mov     edi, 8007029Ch
0x180026312  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180026316  mov     rcx, r10; int
0x180026319  mov     [rsp+78h+var_50], rax; __int64
0x18002631e  mov     rax, [rsp+78h+arg_20]
0x180026326  mov     [rsp+78h+var_58], rax; __int64
0x18002632b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180026330  mov     ecx, edi; this
0x180026332  mov     [rbx+8], edi
0x180026335  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002633a  mov     [rbx+0Ch], eax
0x18002633d  mov     ecx, edi; this
0x18002633f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180026344  jmp     short loc_180026356
0x180026346  mov     ecx, edi; this
0x180026348  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002634d  jmp     short loc_180026356
0x18002634f  mov     ecx, edi; this
0x180026351  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180026356  mov     ebp, eax
0x180026358  mov     eax, [rsp+78h+arg_70]
0x18002635f  mov     [rbx+4], eax
0x180026362  mov     [rbx], r15d
0x180026365  cmp     dword ptr [r14+8], 1
0x18002636a  jnz     short loc_180026372
0x18002636c  or      eax, 8
0x18002636f  mov     [rbx+4], eax
0x180026372  mov     eax, 1
0x180026377  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002637f  inc     eax
0x180026381  xor     edi, edi
0x180026383  mov     [rbx+10h], eax
0x180026386  mov     rax, [rsp+78h+arg_40]
0x18002638e  test    rax, rax
0x180026391  jz      short loc_180026398
0x180026393  cmp     [rax], di
0x180026396  jnz     short loc_18002639B
0x180026398  mov     rax, rdi
0x18002639b  mov     [rbx+18h], rax
0x18002639f  call    cs:__imp_GetCurrentThreadId
0x1800263a6  nop     dword ptr [rax+rax+00h]
0x1800263ab  mov     [rbx+38h], r13
0x1800263af  xorps   xmm0, xmm0
0x1800263b2  mov     [rbx+20h], eax
0x1800263b5  mov     eax, [rsp+78h+arg_8]
0x1800263bc  mov     [rbx+40h], eax
0x1800263bf  mov     rax, [rsp+78h+arg_20]
0x1800263c7  mov     [rbx+28h], rax
0x1800263cb  mov     rax, [rsp+78h+arg_28]
0x1800263d3  mov     [rbx+88h], rax
0x1800263da  mov     rax, [rsp+78h+arg_0]
0x1800263e2  mov     [rbx+90h], rax
0x1800263e9  xor     eax, eax
0x1800263eb  mov     [rbx+44h], ebp
0x1800263ee  mov     [rbx+30h], r12
0x1800263f2  mov     [rbx+48h], rdi
0x1800263f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800263fa  mov     [rbx+78h], rax
0x1800263fe  movups  xmmword ptr [rbx+50h], xmm0
0x180026402  mov     [rbx+60h], rax
0x180026406  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002640d  test    rax, rax
0x180026410  jz      short loc_180026419
0x180026412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026417  jmp     short loc_18002641C
0x180026419  mov     rax, rdi
0x18002641c  mov     [rbx+80h], rax
0x180026423  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002642a  test    rax, rax
0x18002642d  jz      short loc_180026437
0x18002642f  mov     rcx, rbx
0x180026432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026437  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002643e  test    rax, rax
0x180026441  jz      short loc_180026459
0x180026443  mov     rdx, [rsp+78h+arg_60]
0x18002644b  mov     r8d, 400h
0x180026451  mov     rcx, rbx
0x180026454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026459  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026460  test    rax, rax
0x180026463  jz      short loc_18002646D
0x180026465  mov     rcx, rbx
0x180026468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002646d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180026474  test    rax, rax
0x180026477  jz      short loc_180026487
0x180026479  test    byte ptr [rbx+4], 2
0x18002647d  jnz     short loc_180026487
0x18002647f  mov     rcx, rbx
0x180026482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026487  cmp     [rbx+8], edi
0x18002648a  jl      short loc_1800264A6
0x18002648c  cmp     r15d, 3
0x180026490  jnz     loc_180026581
0x180026496  mov     ecx, 8000FFFFh; this
0x18002649b  mov     [rbx+8], ecx
0x18002649e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800264a3  mov     [rbx+0Ch], eax
0x1800264a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800264ad  jnz     short loc_1800264D4
0x1800264af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800264b6  test    rax, rax
0x1800264b9  jz      short loc_1800264C4
0x1800264bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264c0  test    al, al
0x1800264c2  jmp     short loc_1800264D2
0x1800264c4  call    cs:__imp_IsDebuggerPresent
0x1800264cb  nop     dword ptr [rax+rax+00h]
0x1800264d0  test    eax, eax
0x1800264d2  jz      short loc_1800264DA
0x1800264d4  test    byte ptr [rbx+4], 2
0x1800264d8  jz      short loc_1800264FE
0x1800264da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800264e1  test    rax, rax
0x1800264e4  jz      short loc_180026548
0x1800264e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800264ed  jnz     short loc_180026548
0x1800264ef  xor     r8d, r8d
0x1800264f2  xor     edx, edx
0x1800264f4  mov     rcx, rbx
0x1800264f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800264fc  jmp     short loc_180026548
0x1800264fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180026505  mov     ebp, 800h
0x18002650a  test    rax, rax
0x18002650d  jz      short loc_180026526
0x18002650f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180026516  jnz     short loc_180026526
0x180026518  mov     r8d, ebp
0x18002651b  mov     rdx, rsi
0x18002651e  mov     rcx, rbx
0x180026521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026526  cmp     [rsi], di
0x180026529  jnz     short loc_180026539
0x18002652b  mov     r8, rbx; unsigned __int64
0x18002652e  mov     rdx, rbp; unsigned __int16 *
0x180026531  mov     rcx, rsi; this
0x180026534  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180026539  mov     rcx, rsi; lpOutputString
0x18002653c  call    cs:__imp_OutputDebugStringW
0x180026543  nop     dword ptr [rax+rax+00h]
0x180026548  test    byte ptr [rbx+4], 4
0x18002654c  jnz     short loc_180026557
0x18002654e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180026555  jz      short loc_180026568
0x180026557  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002655e  test    rax, rax
0x180026561  jz      short loc_180026568
0x180026563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026568  mov     rbx, [rsp+78h+arg_10]
0x180026570  add     rsp, 40h
0x180026574  pop     r15
0x180026576  pop     r14
0x180026578  pop     r13
0x18002657a  pop     r12
0x18002657c  pop     rdi
0x18002657d  pop     rsi
0x18002657e  pop     rbp
0x18002657f  retn
0x180026581  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
