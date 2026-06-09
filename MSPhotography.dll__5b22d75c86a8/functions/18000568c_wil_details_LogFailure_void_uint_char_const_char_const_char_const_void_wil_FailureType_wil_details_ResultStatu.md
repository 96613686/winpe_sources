# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000568c`
- end: `0x180005985`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003da4`
- `0x180004110`

## callees

- `0x180003cdc`
- `0x180004cc4`
- `0x18000549c`
- `0x18000568c`
- `0x180005cec`
- `0x180005d10`
- `0x180005d24`
- `0x180005d40`
- `0x180006a14`
- `0x180142010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057af`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800057af`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800058ce`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800058ce`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005940`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005940`

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
0x18000568c  mov     [rsp+arg_10], rbx
0x180005691  mov     [rsp+arg_8], edx
0x180005695  mov     [rsp+arg_0], rcx
0x18000569a  push    rbp
0x18000569b  push    rsi
0x18000569c  push    rdi
0x18000569d  push    r12
0x18000569f  push    r13
0x1800056a1  push    r14
0x1800056a3  push    r15
0x1800056a5  sub     rsp, 40h
0x1800056a9  mov     r12, r9
0x1800056ac  mov     r13, r8
0x1800056af  mov     r10, rcx
0x1800056b2  xor     eax, eax
0x1800056b4  mov     rsi, [rsp+78h+lpOutputString]
0x1800056bc  mov     [rsi], ax
0x1800056bf  mov     rax, [rsp+78h+arg_60]
0x1800056c7  mov     byte ptr [rax], 0
0x1800056ca  mov     r14, [rsp+78h+arg_38]
0x1800056d2  mov     edi, [r14]
0x1800056d5  mov     rbx, [rsp+78h+arg_78]
0x1800056dd  mov     [rbx+8], edi
0x1800056e0  mov     eax, [r14+4]
0x1800056e4  mov     [rbx+0Ch], eax
0x1800056e7  xor     ebp, ebp
0x1800056e9  mov     r15d, [rsp+78h+arg_30]
0x1800056f1  mov     ecx, r15d
0x1800056f4  test    r15d, r15d
0x1800056f7  jz      short loc_18000575F
0x1800056f9  sub     ecx, 1
0x1800056fc  jz      short loc_180005756
0x1800056fe  sub     ecx, 1
0x180005701  jz      short loc_180005711
0x180005703  cmp     ecx, 1
0x180005706  jnz     short loc_180005768
0x180005708  mov     ecx, edi; this
0x18000570a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000570f  jmp     short loc_180005766
0x180005711  test    edi, edi
0x180005713  js      short loc_18000574D
0x180005715  mov     edi, 8007029Ch
0x18000571a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000571e  mov     rax, [rsp+78h+arg_28]
0x180005726  mov     [rsp+78h+var_50], rax; __int64
0x18000572b  mov     rax, [rsp+78h+arg_20]
0x180005733  mov     [rsp+78h+var_58], rax; __int64
0x180005738  mov     rcx, r10; int
0x18000573b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005740  mov     [rbx+8], edi
0x180005743  mov     ecx, edi; this
0x180005745  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000574a  mov     [rbx+0Ch], eax
0x18000574d  mov     ecx, edi; this
0x18000574f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005754  jmp     short loc_180005766
0x180005756  mov     ecx, edi; this
0x180005758  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000575d  jmp     short loc_180005766
0x18000575f  mov     ecx, edi; this
0x180005761  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005766  mov     ebp, eax
0x180005768  mov     [rbx], r15d
0x18000576b  mov     eax, [rsp+78h+arg_70]
0x180005772  mov     [rbx+4], eax
0x180005775  cmp     dword ptr [r14+8], 1
0x18000577a  jnz     short loc_180005782
0x18000577c  or      eax, 8
0x18000577f  mov     [rbx+4], eax
0x180005782  mov     eax, 1
0x180005787  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000578f  inc     eax
0x180005791  mov     [rbx+10h], eax
0x180005794  mov     rax, [rsp+78h+arg_40]
0x18000579c  xor     edi, edi
0x18000579e  test    rax, rax
0x1800057a1  jz      short loc_1800057A8
0x1800057a3  cmp     [rax], di
0x1800057a6  jnz     short loc_1800057AB
0x1800057a8  mov     rax, rdi
0x1800057ab  mov     [rbx+18h], rax
0x1800057af  call    cs:__imp_GetCurrentThreadId
0x1800057b5  mov     [rbx+20h], eax
0x1800057b8  mov     [rbx+38h], r13
0x1800057bc  mov     eax, [rsp+78h+arg_8]
0x1800057c3  mov     [rbx+40h], eax
0x1800057c6  mov     [rbx+44h], ebp
0x1800057c9  mov     rax, [rsp+78h+arg_20]
0x1800057d1  mov     [rbx+28h], rax
0x1800057d5  mov     [rbx+30h], r12
0x1800057d9  mov     rax, [rsp+78h+arg_28]
0x1800057e1  mov     [rbx+88h], rax
0x1800057e8  mov     rax, [rsp+78h+arg_0]
0x1800057f0  mov     [rbx+90h], rax
0x1800057f7  mov     [rbx+48h], rdi
0x1800057fb  xorps   xmm0, xmm0
0x1800057fe  xor     eax, eax
0x180005800  movups  xmmword ptr [rbx+68h], xmm0
0x180005804  mov     [rbx+78h], rax
0x180005808  movups  xmmword ptr [rbx+50h], xmm0
0x18000580c  mov     [rbx+60h], rax
0x180005810  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005817  test    rax, rax
0x18000581a  jz      short loc_180005823
0x18000581c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005821  jmp     short loc_180005826
0x180005823  mov     rax, rdi
0x180005826  mov     [rbx+80h], rax
0x18000582d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005834  test    rax, rax
0x180005837  jz      short loc_180005841
0x180005839  mov     rcx, rbx
0x18000583c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005841  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005848  test    rax, rax
0x18000584b  jz      short loc_180005863
0x18000584d  mov     r8d, 400h
0x180005853  mov     rdx, [rsp+78h+arg_60]
0x18000585b  mov     rcx, rbx
0x18000585e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005863  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000586a  test    rax, rax
0x18000586d  jz      short loc_180005877
0x18000586f  mov     rcx, rbx
0x180005872  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005877  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000587e  test    rax, rax
0x180005881  jz      short loc_180005891
0x180005883  test    byte ptr [rbx+4], 2
0x180005887  jnz     short loc_180005891
0x180005889  mov     rcx, rbx
0x18000588c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005891  cmp     [rbx+8], edi
0x180005894  jl      short loc_1800058B0
0x180005896  cmp     r15d, 3
0x18000589a  jnz     loc_18000597F
0x1800058a0  mov     ecx, 8000FFFFh; this
0x1800058a5  mov     [rbx+8], ecx
0x1800058a8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800058ad  mov     [rbx+0Ch], eax
0x1800058b0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800058b7  jnz     short loc_1800058D8
0x1800058b9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800058c0  test    rax, rax
0x1800058c3  jz      short loc_1800058CE
0x1800058c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058ca  test    al, al
0x1800058cc  jmp     short loc_1800058D6
0x1800058ce  call    cs:__imp_IsDebuggerPresent
0x1800058d4  test    eax, eax
0x1800058d6  jz      short loc_1800058DE
0x1800058d8  test    byte ptr [rbx+4], 2
0x1800058dc  jz      short loc_180005902
0x1800058de  mov     rax, cs:g_pfnResultLoggingCallback
0x1800058e5  test    rax, rax
0x1800058e8  jz      short loc_180005946
0x1800058ea  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800058f1  jnz     short loc_180005946
0x1800058f3  xor     r8d, r8d
0x1800058f6  xor     edx, edx
0x1800058f8  mov     rcx, rbx
0x1800058fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005900  jmp     short loc_180005946
0x180005902  mov     ebp, 800h
0x180005907  mov     rax, cs:g_pfnResultLoggingCallback
0x18000590e  test    rax, rax
0x180005911  jz      short loc_18000592A
0x180005913  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000591a  jnz     short loc_18000592A
0x18000591c  mov     r8d, ebp
0x18000591f  mov     rdx, rsi
0x180005922  mov     rcx, rbx
0x180005925  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000592a  cmp     [rsi], di
0x18000592d  jnz     short loc_18000593D
0x18000592f  mov     r8, rbx; unsigned __int64
0x180005932  mov     rdx, rbp; unsigned __int16 *
0x180005935  mov     rcx, rsi; this
0x180005938  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000593d  mov     rcx, rsi; lpOutputString
0x180005940  call    cs:__imp_OutputDebugStringW
0x180005946  test    byte ptr [rbx+4], 4
0x18000594a  jnz     short loc_180005955
0x18000594c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005953  jz      short loc_180005967
0x180005955  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000595c  test    rax, rax
0x18000595f  jz      short loc_180005967
0x180005961  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005966  nop
0x180005967  mov     rbx, [rsp+78h+arg_10]
0x18000596f  add     rsp, 40h
0x180005973  pop     r15
0x180005975  pop     r14
0x180005977  pop     r13
0x180005979  pop     r12
0x18000597b  pop     rdi
0x18000597c  pop     rsi
0x18000597d  pop     rbp
0x18000597e  retn
0x18000597f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
