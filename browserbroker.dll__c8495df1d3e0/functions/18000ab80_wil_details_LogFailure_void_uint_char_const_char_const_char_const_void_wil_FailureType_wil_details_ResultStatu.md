# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000ab80`
- end: `0x18000ae79`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180006060`
- `0x1800063b4`

## callees

- `0x180005f10`
- `0x18000959c`
- `0x18000a30c`
- `0x18000ab80`
- `0x18000b848`
- `0x18000b870`
- `0x18000b884`
- `0x18000b8a0`
- `0x18000dc48`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000aca3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000adc2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000adc2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ae34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ae34`

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
0x18000ab80  mov     [rsp+arg_10], rbx
0x18000ab85  mov     [rsp+arg_8], edx
0x18000ab89  mov     [rsp+arg_0], rcx
0x18000ab8e  push    rbp
0x18000ab8f  push    rsi
0x18000ab90  push    rdi
0x18000ab91  push    r12
0x18000ab93  push    r13
0x18000ab95  push    r14
0x18000ab97  push    r15
0x18000ab99  sub     rsp, 40h
0x18000ab9d  mov     r12, r9
0x18000aba0  mov     r13, r8
0x18000aba3  mov     r10, rcx
0x18000aba6  xor     eax, eax
0x18000aba8  mov     rsi, [rsp+78h+lpOutputString]
0x18000abb0  mov     [rsi], ax
0x18000abb3  mov     rax, [rsp+78h+arg_60]
0x18000abbb  mov     byte ptr [rax], 0
0x18000abbe  mov     r14, [rsp+78h+arg_38]
0x18000abc6  mov     edi, [r14]
0x18000abc9  mov     rbx, [rsp+78h+arg_78]
0x18000abd1  mov     [rbx+8], edi
0x18000abd4  mov     eax, [r14+4]
0x18000abd8  mov     [rbx+0Ch], eax
0x18000abdb  xor     ebp, ebp
0x18000abdd  mov     r15d, [rsp+78h+arg_30]
0x18000abe5  mov     ecx, r15d
0x18000abe8  test    r15d, r15d
0x18000abeb  jz      short loc_18000AC53
0x18000abed  sub     ecx, 1
0x18000abf0  jz      short loc_18000AC4A
0x18000abf2  sub     ecx, 1
0x18000abf5  jz      short loc_18000AC05
0x18000abf7  cmp     ecx, 1
0x18000abfa  jnz     short loc_18000AC5C
0x18000abfc  mov     ecx, edi; this
0x18000abfe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ac03  jmp     short loc_18000AC5A
0x18000ac05  test    edi, edi
0x18000ac07  js      short loc_18000AC41
0x18000ac09  mov     edi, 8007029Ch
0x18000ac0e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ac12  mov     rax, [rsp+78h+arg_28]
0x18000ac1a  mov     [rsp+78h+var_50], rax; __int64
0x18000ac1f  mov     rax, [rsp+78h+arg_20]
0x18000ac27  mov     [rsp+78h+var_58], rax; __int64
0x18000ac2c  mov     rcx, r10; int
0x18000ac2f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ac34  mov     [rbx+8], edi
0x18000ac37  mov     ecx, edi; this
0x18000ac39  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ac3e  mov     [rbx+0Ch], eax
0x18000ac41  mov     ecx, edi; this
0x18000ac43  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ac48  jmp     short loc_18000AC5A
0x18000ac4a  mov     ecx, edi; this
0x18000ac4c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ac51  jmp     short loc_18000AC5A
0x18000ac53  mov     ecx, edi; this
0x18000ac55  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ac5a  mov     ebp, eax
0x18000ac5c  mov     [rbx], r15d
0x18000ac5f  mov     eax, [rsp+78h+arg_70]
0x18000ac66  mov     [rbx+4], eax
0x18000ac69  cmp     dword ptr [r14+8], 1
0x18000ac6e  jnz     short loc_18000AC76
0x18000ac70  or      eax, 8
0x18000ac73  mov     [rbx+4], eax
0x18000ac76  mov     eax, 1
0x18000ac7b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ac83  inc     eax
0x18000ac85  mov     [rbx+10h], eax
0x18000ac88  mov     rax, [rsp+78h+arg_40]
0x18000ac90  xor     edi, edi
0x18000ac92  test    rax, rax
0x18000ac95  jz      short loc_18000AC9C
0x18000ac97  cmp     [rax], di
0x18000ac9a  jnz     short loc_18000AC9F
0x18000ac9c  mov     rax, rdi
0x18000ac9f  mov     [rbx+18h], rax
0x18000aca3  call    cs:__imp_GetCurrentThreadId
0x18000aca9  mov     [rbx+20h], eax
0x18000acac  mov     [rbx+38h], r13
0x18000acb0  mov     eax, [rsp+78h+arg_8]
0x18000acb7  mov     [rbx+40h], eax
0x18000acba  mov     [rbx+44h], ebp
0x18000acbd  mov     rax, [rsp+78h+arg_20]
0x18000acc5  mov     [rbx+28h], rax
0x18000acc9  mov     [rbx+30h], r12
0x18000accd  mov     rax, [rsp+78h+arg_28]
0x18000acd5  mov     [rbx+88h], rax
0x18000acdc  mov     rax, [rsp+78h+arg_0]
0x18000ace4  mov     [rbx+90h], rax
0x18000aceb  mov     [rbx+48h], rdi
0x18000acef  xorps   xmm0, xmm0
0x18000acf2  xor     eax, eax
0x18000acf4  movups  xmmword ptr [rbx+68h], xmm0
0x18000acf8  mov     [rbx+78h], rax
0x18000acfc  movups  xmmword ptr [rbx+50h], xmm0
0x18000ad00  mov     [rbx+60h], rax
0x18000ad04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ad0b  test    rax, rax
0x18000ad0e  jz      short loc_18000AD17
0x18000ad10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad15  jmp     short loc_18000AD1A
0x18000ad17  mov     rax, rdi
0x18000ad1a  mov     [rbx+80h], rax
0x18000ad21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ad28  test    rax, rax
0x18000ad2b  jz      short loc_18000AD35
0x18000ad2d  mov     rcx, rbx
0x18000ad30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000ad3c  test    rax, rax
0x18000ad3f  jz      short loc_18000AD57
0x18000ad41  mov     r8d, 400h
0x18000ad47  mov     rdx, [rsp+78h+arg_60]
0x18000ad4f  mov     rcx, rbx
0x18000ad52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ad5e  test    rax, rax
0x18000ad61  jz      short loc_18000AD6B
0x18000ad63  mov     rcx, rbx
0x18000ad66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000ad72  test    rax, rax
0x18000ad75  jz      short loc_18000AD85
0x18000ad77  test    byte ptr [rbx+4], 2
0x18000ad7b  jnz     short loc_18000AD85
0x18000ad7d  mov     rcx, rbx
0x18000ad80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ad85  cmp     [rbx+8], edi
0x18000ad88  jl      short loc_18000ADA4
0x18000ad8a  cmp     r15d, 3
0x18000ad8e  jnz     loc_18000AE73
0x18000ad94  mov     ecx, 8000FFFFh; this
0x18000ad99  mov     [rbx+8], ecx
0x18000ad9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ada1  mov     [rbx+0Ch], eax
0x18000ada4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000adab  jnz     short loc_18000ADCC
0x18000adad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000adb4  test    rax, rax
0x18000adb7  jz      short loc_18000ADC2
0x18000adb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adbe  test    al, al
0x18000adc0  jmp     short loc_18000ADCA
0x18000adc2  call    cs:__imp_IsDebuggerPresent
0x18000adc8  test    eax, eax
0x18000adca  jz      short loc_18000ADD2
0x18000adcc  test    byte ptr [rbx+4], 2
0x18000add0  jz      short loc_18000ADF6
0x18000add2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000add9  test    rax, rax
0x18000addc  jz      short loc_18000AE3A
0x18000adde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ade5  jnz     short loc_18000AE3A
0x18000ade7  xor     r8d, r8d
0x18000adea  xor     edx, edx
0x18000adec  mov     rcx, rbx
0x18000adef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adf4  jmp     short loc_18000AE3A
0x18000adf6  mov     ebp, 800h
0x18000adfb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000ae02  test    rax, rax
0x18000ae05  jz      short loc_18000AE1E
0x18000ae07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000ae0e  jnz     short loc_18000AE1E
0x18000ae10  mov     r8d, ebp
0x18000ae13  mov     rdx, rsi
0x18000ae16  mov     rcx, rbx
0x18000ae19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae1e  cmp     [rsi], di
0x18000ae21  jnz     short loc_18000AE31
0x18000ae23  mov     r8, rbx; unsigned __int64
0x18000ae26  mov     rdx, rbp; unsigned __int16 *
0x18000ae29  mov     rcx, rsi; this
0x18000ae2c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ae31  mov     rcx, rsi; lpOutputString
0x18000ae34  call    cs:__imp_OutputDebugStringW
0x18000ae3a  test    byte ptr [rbx+4], 4
0x18000ae3e  jnz     short loc_18000AE49
0x18000ae40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000ae47  jz      short loc_18000AE5B
0x18000ae49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ae50  test    rax, rax
0x18000ae53  jz      short loc_18000AE5B
0x18000ae55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae5a  nop
0x18000ae5b  mov     rbx, [rsp+78h+arg_10]
0x18000ae63  add     rsp, 40h
0x18000ae67  pop     r15
0x18000ae69  pop     r14
0x18000ae6b  pop     r13
0x18000ae6d  pop     r12
0x18000ae6f  pop     rdi
0x18000ae70  pop     rsi
0x18000ae71  pop     rbp
0x18000ae72  retn
0x18000ae73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
