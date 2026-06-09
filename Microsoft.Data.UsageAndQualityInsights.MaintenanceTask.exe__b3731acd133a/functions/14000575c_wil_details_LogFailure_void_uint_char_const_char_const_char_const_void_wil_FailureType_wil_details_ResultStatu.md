# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000575c`
- end: `0x140005a55`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002d10`

## callees

- `0x14000274c`
- `0x140004d14`
- `0x1400054b0`
- `0x14000575c`
- `0x1400063c8`
- `0x1400063f0`
- `0x14000651c`
- `0x140006538`
- `0x140008aec`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000587f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000587f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000599e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000599e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005a10`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005a10`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
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
0x14000575c  mov     [rsp+arg_10], rbx
0x140005761  mov     [rsp+arg_8], edx
0x140005765  mov     [rsp+arg_0], rcx
0x14000576a  push    rbp
0x14000576b  push    rsi
0x14000576c  push    rdi
0x14000576d  push    r12
0x14000576f  push    r13
0x140005771  push    r14
0x140005773  push    r15
0x140005775  sub     rsp, 40h
0x140005779  mov     r12, r9
0x14000577c  mov     r13, r8
0x14000577f  mov     r10, rcx
0x140005782  xor     eax, eax
0x140005784  mov     rsi, [rsp+78h+lpOutputString]
0x14000578c  mov     [rsi], ax
0x14000578f  mov     rax, [rsp+78h+arg_60]
0x140005797  mov     byte ptr [rax], 0
0x14000579a  mov     r14, [rsp+78h+arg_38]
0x1400057a2  mov     edi, [r14]
0x1400057a5  mov     rbx, [rsp+78h+arg_78]
0x1400057ad  mov     [rbx+8], edi
0x1400057b0  mov     eax, [r14+4]
0x1400057b4  mov     [rbx+0Ch], eax
0x1400057b7  xor     ebp, ebp
0x1400057b9  mov     r15d, [rsp+78h+arg_30]
0x1400057c1  mov     ecx, r15d
0x1400057c4  test    r15d, r15d
0x1400057c7  jz      short loc_14000582F
0x1400057c9  sub     ecx, 1
0x1400057cc  jz      short loc_140005826
0x1400057ce  sub     ecx, 1
0x1400057d1  jz      short loc_1400057E1
0x1400057d3  cmp     ecx, 1
0x1400057d6  jnz     short loc_140005838
0x1400057d8  mov     ecx, edi; this
0x1400057da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400057df  jmp     short loc_140005836
0x1400057e1  test    edi, edi
0x1400057e3  js      short loc_14000581D
0x1400057e5  mov     edi, 8007029Ch
0x1400057ea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400057ee  mov     rax, [rsp+78h+arg_28]
0x1400057f6  mov     [rsp+78h+var_50], rax; __int64
0x1400057fb  mov     rax, [rsp+78h+arg_20]
0x140005803  mov     [rsp+78h+var_58], rax; __int64
0x140005808  mov     rcx, r10; int
0x14000580b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005810  mov     [rbx+8], edi
0x140005813  mov     ecx, edi; this
0x140005815  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000581a  mov     [rbx+0Ch], eax
0x14000581d  mov     ecx, edi; this
0x14000581f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005824  jmp     short loc_140005836
0x140005826  mov     ecx, edi; this
0x140005828  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000582d  jmp     short loc_140005836
0x14000582f  mov     ecx, edi; this
0x140005831  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005836  mov     ebp, eax
0x140005838  mov     [rbx], r15d
0x14000583b  mov     eax, [rsp+78h+arg_70]
0x140005842  mov     [rbx+4], eax
0x140005845  cmp     dword ptr [r14+8], 1
0x14000584a  jnz     short loc_140005852
0x14000584c  or      eax, 8
0x14000584f  mov     [rbx+4], eax
0x140005852  mov     eax, 1
0x140005857  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000585f  inc     eax
0x140005861  mov     [rbx+10h], eax
0x140005864  mov     rax, [rsp+78h+arg_40]
0x14000586c  xor     edi, edi
0x14000586e  test    rax, rax
0x140005871  jz      short loc_140005878
0x140005873  cmp     [rax], di
0x140005876  jnz     short loc_14000587B
0x140005878  mov     rax, rdi
0x14000587b  mov     [rbx+18h], rax
0x14000587f  call    cs:__imp_GetCurrentThreadId
0x140005885  mov     [rbx+20h], eax
0x140005888  mov     [rbx+38h], r13
0x14000588c  mov     eax, [rsp+78h+arg_8]
0x140005893  mov     [rbx+40h], eax
0x140005896  mov     [rbx+44h], ebp
0x140005899  mov     rax, [rsp+78h+arg_20]
0x1400058a1  mov     [rbx+28h], rax
0x1400058a5  mov     [rbx+30h], r12
0x1400058a9  mov     rax, [rsp+78h+arg_28]
0x1400058b1  mov     [rbx+88h], rax
0x1400058b8  mov     rax, [rsp+78h+arg_0]
0x1400058c0  mov     [rbx+90h], rax
0x1400058c7  mov     [rbx+48h], rdi
0x1400058cb  xorps   xmm0, xmm0
0x1400058ce  xor     eax, eax
0x1400058d0  movups  xmmword ptr [rbx+68h], xmm0
0x1400058d4  mov     [rbx+78h], rax
0x1400058d8  movups  xmmword ptr [rbx+50h], xmm0
0x1400058dc  mov     [rbx+60h], rax
0x1400058e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400058e7  test    rax, rax
0x1400058ea  jz      short loc_1400058F3
0x1400058ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058f1  jmp     short loc_1400058F6
0x1400058f3  mov     rax, rdi
0x1400058f6  mov     [rbx+80h], rax
0x1400058fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005904  test    rax, rax
0x140005907  jz      short loc_140005911
0x140005909  mov     rcx, rbx
0x14000590c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005911  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005918  test    rax, rax
0x14000591b  jz      short loc_140005933
0x14000591d  mov     r8d, 400h
0x140005923  mov     rdx, [rsp+78h+arg_60]
0x14000592b  mov     rcx, rbx
0x14000592e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005933  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000593a  test    rax, rax
0x14000593d  jz      short loc_140005947
0x14000593f  mov     rcx, rbx
0x140005942  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005947  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000594e  test    rax, rax
0x140005951  jz      short loc_140005961
0x140005953  test    byte ptr [rbx+4], 2
0x140005957  jnz     short loc_140005961
0x140005959  mov     rcx, rbx
0x14000595c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005961  cmp     [rbx+8], edi
0x140005964  jl      short loc_140005980
0x140005966  cmp     r15d, 3
0x14000596a  jnz     loc_140005A4F
0x140005970  mov     ecx, 8000FFFFh; this
0x140005975  mov     [rbx+8], ecx
0x140005978  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000597d  mov     [rbx+0Ch], eax
0x140005980  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005987  jnz     short loc_1400059A8
0x140005989  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005990  test    rax, rax
0x140005993  jz      short loc_14000599E
0x140005995  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000599a  test    al, al
0x14000599c  jmp     short loc_1400059A6
0x14000599e  call    cs:__imp_IsDebuggerPresent
0x1400059a4  test    eax, eax
0x1400059a6  jz      short loc_1400059AE
0x1400059a8  test    byte ptr [rbx+4], 2
0x1400059ac  jz      short loc_1400059D2
0x1400059ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1400059b5  test    rax, rax
0x1400059b8  jz      short loc_140005A16
0x1400059ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400059c1  jnz     short loc_140005A16
0x1400059c3  xor     r8d, r8d
0x1400059c6  xor     edx, edx
0x1400059c8  mov     rcx, rbx
0x1400059cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059d0  jmp     short loc_140005A16
0x1400059d2  mov     ebp, 800h
0x1400059d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400059de  test    rax, rax
0x1400059e1  jz      short loc_1400059FA
0x1400059e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400059ea  jnz     short loc_1400059FA
0x1400059ec  mov     r8d, ebp
0x1400059ef  mov     rdx, rsi
0x1400059f2  mov     rcx, rbx
0x1400059f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400059fa  cmp     [rsi], di
0x1400059fd  jnz     short loc_140005A0D
0x1400059ff  mov     r8, rbx; unsigned __int64
0x140005a02  mov     rdx, rbp; wchar_t *
0x140005a05  mov     rcx, rsi; this
0x140005a08  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140005a0d  mov     rcx, rsi; lpOutputString
0x140005a10  call    cs:__imp_OutputDebugStringW
0x140005a16  test    byte ptr [rbx+4], 4
0x140005a1a  jnz     short loc_140005A25
0x140005a1c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005a23  jz      short loc_140005A37
0x140005a25  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005a2c  test    rax, rax
0x140005a2f  jz      short loc_140005A37
0x140005a31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005a36  nop
0x140005a37  mov     rbx, [rsp+78h+arg_10]
0x140005a3f  add     rsp, 40h
0x140005a43  pop     r15
0x140005a45  pop     r14
0x140005a47  pop     r13
0x140005a49  pop     r12
0x140005a4b  pop     rdi
0x140005a4c  pop     rsi
0x140005a4d  pop     rbp
0x140005a4e  retn
0x140005a4f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
