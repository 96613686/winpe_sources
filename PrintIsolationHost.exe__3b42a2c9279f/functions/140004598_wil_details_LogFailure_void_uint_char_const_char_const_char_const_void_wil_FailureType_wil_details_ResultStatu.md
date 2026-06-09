# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004598`
- end: `0x140004890`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002f00`

## callees

- `0x14000293c`
- `0x140003b74`
- `0x14000430c`
- `0x140004598`
- `0x140004b60`
- `0x140004b80`
- `0x140004b94`
- `0x140004bb0`
- `0x14000589c`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400046bb`
- `KERNEL32!GetCurrentThreadId` at `0x1400046bb`
- `KERNEL32!OutputDebugStringW` at `0x14000484c`
- `KERNEL32!OutputDebugStringW` at `0x14000484c`
- `KERNEL32!IsDebuggerPresent` at `0x1400047da`
- `KERNEL32!IsDebuggerPresent` at `0x1400047da`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x140004598  mov     [rsp+arg_10], rbx
0x14000459d  mov     [rsp+arg_8], edx
0x1400045a1  mov     [rsp+arg_0], rcx
0x1400045a6  push    rbp
0x1400045a7  push    rsi
0x1400045a8  push    rdi
0x1400045a9  push    r12
0x1400045ab  push    r13
0x1400045ad  push    r14
0x1400045af  push    r15
0x1400045b1  sub     rsp, 40h
0x1400045b5  mov     r14, [rsp+78h+arg_38]
0x1400045bd  xor     eax, eax
0x1400045bf  mov     rbx, [rsp+78h+arg_78]
0x1400045c7  xor     ebp, ebp
0x1400045c9  mov     r15d, [rsp+78h+arg_30]
0x1400045d1  mov     r10, rcx
0x1400045d4  mov     rsi, [rsp+78h+lpOutputString]
0x1400045dc  mov     r12, r9
0x1400045df  mov     r13, r8
0x1400045e2  mov     ecx, r15d
0x1400045e5  mov     [rsi], ax
0x1400045e8  mov     rax, [rsp+78h+arg_60]
0x1400045f0  mov     byte ptr [rax], 0
0x1400045f3  mov     edi, [r14]
0x1400045f6  mov     [rbx+8], edi
0x1400045f9  mov     eax, [r14+4]
0x1400045fd  mov     [rbx+0Ch], eax
0x140004600  test    r15d, r15d
0x140004603  jz      short loc_14000466B
0x140004605  sub     ecx, 1
0x140004608  jz      short loc_140004662
0x14000460a  sub     ecx, 1
0x14000460d  jz      short loc_14000461D
0x14000460f  cmp     ecx, 1
0x140004612  jnz     short loc_140004674
0x140004614  mov     ecx, edi; this
0x140004616  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000461b  jmp     short loc_140004672
0x14000461d  test    edi, edi
0x14000461f  js      short loc_140004659
0x140004621  mov     rax, [rsp+78h+arg_28]
0x140004629  mov     edi, 8007029Ch
0x14000462e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004632  mov     rcx, r10; int
0x140004635  mov     [rsp+78h+var_50], rax; __int64
0x14000463a  mov     rax, [rsp+78h+arg_20]
0x140004642  mov     [rsp+78h+var_58], rax; __int64
0x140004647  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000464c  mov     ecx, edi; this
0x14000464e  mov     [rbx+8], edi
0x140004651  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004656  mov     [rbx+0Ch], eax
0x140004659  mov     ecx, edi; this
0x14000465b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004660  jmp     short loc_140004672
0x140004662  mov     ecx, edi; this
0x140004664  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004669  jmp     short loc_140004672
0x14000466b  mov     ecx, edi; this
0x14000466d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004672  mov     ebp, eax
0x140004674  mov     eax, [rsp+78h+arg_70]
0x14000467b  mov     [rbx+4], eax
0x14000467e  mov     [rbx], r15d
0x140004681  cmp     dword ptr [r14+8], 1
0x140004686  jnz     short loc_14000468E
0x140004688  or      eax, 8
0x14000468b  mov     [rbx+4], eax
0x14000468e  mov     eax, 1
0x140004693  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000469b  inc     eax
0x14000469d  xor     edi, edi
0x14000469f  mov     [rbx+10h], eax
0x1400046a2  mov     rax, [rsp+78h+arg_40]
0x1400046aa  test    rax, rax
0x1400046ad  jz      short loc_1400046B4
0x1400046af  cmp     [rax], di
0x1400046b2  jnz     short loc_1400046B7
0x1400046b4  mov     rax, rdi
0x1400046b7  mov     [rbx+18h], rax
0x1400046bb  call    cs:__imp_GetCurrentThreadId
0x1400046c1  mov     [rbx+38h], r13
0x1400046c5  xorps   xmm0, xmm0
0x1400046c8  mov     [rbx+20h], eax
0x1400046cb  mov     eax, [rsp+78h+arg_8]
0x1400046d2  mov     [rbx+40h], eax
0x1400046d5  mov     rax, [rsp+78h+arg_20]
0x1400046dd  mov     [rbx+28h], rax
0x1400046e1  mov     rax, [rsp+78h+arg_28]
0x1400046e9  mov     [rbx+88h], rax
0x1400046f0  mov     rax, [rsp+78h+arg_0]
0x1400046f8  mov     [rbx+90h], rax
0x1400046ff  xor     eax, eax
0x140004701  mov     [rbx+44h], ebp
0x140004704  mov     [rbx+30h], r12
0x140004708  mov     [rbx+48h], rdi
0x14000470c  movups  xmmword ptr [rbx+68h], xmm0
0x140004710  mov     [rbx+78h], rax
0x140004714  movups  xmmword ptr [rbx+50h], xmm0
0x140004718  mov     [rbx+60h], rax
0x14000471c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004723  test    rax, rax
0x140004726  jz      short loc_14000472F
0x140004728  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000472d  jmp     short loc_140004732
0x14000472f  mov     rax, rdi
0x140004732  mov     [rbx+80h], rax
0x140004739  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004740  test    rax, rax
0x140004743  jz      short loc_14000474D
0x140004745  mov     rcx, rbx
0x140004748  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000474d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004754  test    rax, rax
0x140004757  jz      short loc_14000476F
0x140004759  mov     rdx, [rsp+78h+arg_60]
0x140004761  mov     r8d, 400h
0x140004767  mov     rcx, rbx
0x14000476a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000476f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004776  test    rax, rax
0x140004779  jz      short loc_140004783
0x14000477b  mov     rcx, rbx
0x14000477e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004783  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000478a  test    rax, rax
0x14000478d  jz      short loc_14000479D
0x14000478f  test    byte ptr [rbx+4], 2
0x140004793  jnz     short loc_14000479D
0x140004795  mov     rcx, rbx
0x140004798  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000479d  cmp     [rbx+8], edi
0x1400047a0  jl      short loc_1400047BC
0x1400047a2  cmp     r15d, 3
0x1400047a6  jnz     loc_14000488A
0x1400047ac  mov     ecx, 8000FFFFh; this
0x1400047b1  mov     [rbx+8], ecx
0x1400047b4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400047b9  mov     [rbx+0Ch], eax
0x1400047bc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400047c3  jnz     short loc_1400047E4
0x1400047c5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400047cc  test    rax, rax
0x1400047cf  jz      short loc_1400047DA
0x1400047d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400047d6  test    al, al
0x1400047d8  jmp     short loc_1400047E2
0x1400047da  call    cs:__imp_IsDebuggerPresent
0x1400047e0  test    eax, eax
0x1400047e2  jz      short loc_1400047EA
0x1400047e4  test    byte ptr [rbx+4], 2
0x1400047e8  jz      short loc_14000480E
0x1400047ea  mov     rax, cs:g_pfnResultLoggingCallback
0x1400047f1  test    rax, rax
0x1400047f4  jz      short loc_140004852
0x1400047f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400047fd  jnz     short loc_140004852
0x1400047ff  xor     r8d, r8d
0x140004802  xor     edx, edx
0x140004804  mov     rcx, rbx
0x140004807  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000480c  jmp     short loc_140004852
0x14000480e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004815  mov     ebp, 800h
0x14000481a  test    rax, rax
0x14000481d  jz      short loc_140004836
0x14000481f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004826  jnz     short loc_140004836
0x140004828  mov     r8d, ebp
0x14000482b  mov     rdx, rsi
0x14000482e  mov     rcx, rbx
0x140004831  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004836  cmp     [rsi], di
0x140004839  jnz     short loc_140004849
0x14000483b  mov     r8, rbx; unsigned __int64
0x14000483e  mov     rdx, rbp; unsigned __int16 *
0x140004841  mov     rcx, rsi; this
0x140004844  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004849  mov     rcx, rsi; lpOutputString
0x14000484c  call    cs:__imp_OutputDebugStringW
0x140004852  test    byte ptr [rbx+4], 4
0x140004856  jnz     short loc_140004861
0x140004858  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000485f  jz      short loc_140004872
0x140004861  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004868  test    rax, rax
0x14000486b  jz      short loc_140004872
0x14000486d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004872  mov     rbx, [rsp+78h+arg_10]
0x14000487a  add     rsp, 40h
0x14000487e  pop     r15
0x140004880  pop     r14
0x140004882  pop     r13
0x140004884  pop     r12
0x140004886  pop     rdi
0x140004887  pop     rsi
0x140004888  pop     rbp
0x140004889  retn
0x14000488a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
