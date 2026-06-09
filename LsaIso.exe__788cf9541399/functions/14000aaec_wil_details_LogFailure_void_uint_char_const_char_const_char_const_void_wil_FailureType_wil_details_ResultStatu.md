# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000aaec`
- end: `0x14000ade1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1400070cc`
- `0x14000717c`
- `0x14000726c`

## callees

- `0x140007020`
- `0x140009a64`
- `0x14000a26c`
- `0x14000aaec`
- `0x14000b69c`
- `0x14000b6c0`
- `0x14000b77c`
- `0x14000b798`
- `0x14000d3ec`
- `0x14003a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ac0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000ac0f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000ad30`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000ad30`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ada2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ada2`

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
0x14000aaec  mov     [rsp+arg_10], rbx
0x14000aaf1  mov     [rsp+arg_8], edx
0x14000aaf5  mov     [rsp+arg_0], rcx
0x14000aafa  push    rbp
0x14000aafb  push    rsi
0x14000aafc  push    rdi
0x14000aafd  push    r12
0x14000aaff  push    r13
0x14000ab01  push    r14
0x14000ab03  push    r15
0x14000ab05  sub     rsp, 40h
0x14000ab09  mov     r12, r9
0x14000ab0c  mov     r13, r8
0x14000ab0f  mov     r10, rcx
0x14000ab12  xor     eax, eax
0x14000ab14  mov     rsi, [rsp+78h+lpOutputString]
0x14000ab1c  mov     [rsi], ax
0x14000ab1f  mov     rax, [rsp+78h+arg_60]
0x14000ab27  mov     byte ptr [rax], 0
0x14000ab2a  mov     r14, [rsp+78h+arg_38]
0x14000ab32  mov     edi, [r14]
0x14000ab35  mov     rbx, [rsp+78h+arg_78]
0x14000ab3d  mov     [rbx+8], edi
0x14000ab40  mov     eax, [r14+4]
0x14000ab44  mov     [rbx+0Ch], eax
0x14000ab47  xor     ebp, ebp
0x14000ab49  mov     r15d, [rsp+78h+arg_30]
0x14000ab51  mov     ecx, r15d
0x14000ab54  test    r15d, r15d
0x14000ab57  jz      short loc_14000ABBF
0x14000ab59  sub     ecx, 1
0x14000ab5c  jz      short loc_14000ABB6
0x14000ab5e  sub     ecx, 1
0x14000ab61  jz      short loc_14000AB71
0x14000ab63  cmp     ecx, 1
0x14000ab66  jnz     short loc_14000ABC8
0x14000ab68  mov     ecx, edi; this
0x14000ab6a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000ab6f  jmp     short loc_14000ABC6
0x14000ab71  test    edi, edi
0x14000ab73  js      short loc_14000ABAD
0x14000ab75  mov     edi, 8007029Ch
0x14000ab7a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000ab7e  mov     rax, [rsp+78h+arg_28]
0x14000ab86  mov     [rsp+78h+var_50], rax; __int64
0x14000ab8b  mov     rax, [rsp+78h+arg_20]
0x14000ab93  mov     [rsp+78h+var_58], rax; __int64
0x14000ab98  mov     rcx, r10; int
0x14000ab9b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000aba0  mov     [rbx+8], edi
0x14000aba3  mov     ecx, edi; this
0x14000aba5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000abaa  mov     [rbx+0Ch], eax
0x14000abad  mov     ecx, edi; this
0x14000abaf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000abb4  jmp     short loc_14000ABC6
0x14000abb6  mov     ecx, edi; this
0x14000abb8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000abbd  jmp     short loc_14000ABC6
0x14000abbf  mov     ecx, edi; this
0x14000abc1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000abc6  mov     ebp, eax
0x14000abc8  mov     [rbx], r15d
0x14000abcb  mov     eax, [rsp+78h+arg_70]
0x14000abd2  mov     [rbx+4], eax
0x14000abd5  cmp     dword ptr [r14+8], 1
0x14000abda  jnz     short loc_14000ABE2
0x14000abdc  or      eax, 8
0x14000abdf  mov     [rbx+4], eax
0x14000abe2  mov     eax, 1
0x14000abe7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000abef  inc     eax
0x14000abf1  mov     [rbx+10h], eax
0x14000abf4  mov     rax, [rsp+78h+arg_40]
0x14000abfc  xor     edi, edi
0x14000abfe  test    rax, rax
0x14000ac01  jz      short loc_14000AC08
0x14000ac03  cmp     [rax], di
0x14000ac06  jnz     short loc_14000AC0B
0x14000ac08  mov     rax, rdi
0x14000ac0b  mov     [rbx+18h], rax
0x14000ac0f  call    cs:__imp_GetCurrentThreadId
0x14000ac15  mov     [rbx+20h], eax
0x14000ac18  mov     [rbx+38h], r13
0x14000ac1c  mov     eax, [rsp+78h+arg_8]
0x14000ac23  mov     [rbx+40h], eax
0x14000ac26  mov     [rbx+44h], ebp
0x14000ac29  mov     rax, [rsp+78h+arg_20]
0x14000ac31  mov     [rbx+28h], rax
0x14000ac35  mov     [rbx+30h], r12
0x14000ac39  mov     rax, [rsp+78h+arg_28]
0x14000ac41  mov     [rbx+88h], rax
0x14000ac48  mov     rax, [rsp+78h+arg_0]
0x14000ac50  mov     [rbx+90h], rax
0x14000ac57  mov     [rbx+48h], rdi
0x14000ac5b  xorps   xmm0, xmm0
0x14000ac5e  xor     eax, eax
0x14000ac60  movups  xmmword ptr [rbx+68h], xmm0
0x14000ac64  mov     [rbx+78h], rax
0x14000ac68  movups  xmmword ptr [rbx+50h], xmm0
0x14000ac6c  mov     [rbx+60h], rax
0x14000ac70  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000ac77  test    rax, rax
0x14000ac7a  jz      short loc_14000AC83
0x14000ac7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac81  jmp     short loc_14000AC86
0x14000ac83  mov     rax, rdi
0x14000ac86  mov     [rbx+80h], rax
0x14000ac8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000ac94  test    rax, rax
0x14000ac97  jz      short loc_14000ACA1
0x14000ac99  mov     rcx, rbx
0x14000ac9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aca1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000aca8  test    rax, rax
0x14000acab  jz      short loc_14000ACC3
0x14000acad  mov     r8d, 400h
0x14000acb3  mov     rdx, [rsp+78h+arg_60]
0x14000acbb  mov     rcx, rbx
0x14000acbe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acc3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000acca  test    rax, rax
0x14000accd  jz      short loc_14000ACD7
0x14000accf  mov     rcx, rbx
0x14000acd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acd7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000acde  test    rax, rax
0x14000ace1  jz      short loc_14000ACF1
0x14000ace3  test    byte ptr [rbx+4], 2
0x14000ace7  jnz     short loc_14000ACF1
0x14000ace9  mov     rcx, rbx
0x14000acec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000acf1  cmp     [rbx+8], edi
0x14000acf4  jl      short loc_14000AD12
0x14000acf6  cmp     r15d, 3
0x14000acfa  jz      short loc_14000AD02
0x14000acfc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14000ad02  mov     ecx, 8000FFFFh; this
0x14000ad07  mov     [rbx+8], ecx
0x14000ad0a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000ad0f  mov     [rbx+0Ch], eax
0x14000ad12  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000ad19  jnz     short loc_14000AD3A
0x14000ad1b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000ad22  test    rax, rax
0x14000ad25  jz      short loc_14000AD30
0x14000ad27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad2c  test    al, al
0x14000ad2e  jmp     short loc_14000AD38
0x14000ad30  call    cs:__imp_IsDebuggerPresent
0x14000ad36  test    eax, eax
0x14000ad38  jz      short loc_14000AD40
0x14000ad3a  test    byte ptr [rbx+4], 2
0x14000ad3e  jz      short loc_14000AD64
0x14000ad40  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ad47  test    rax, rax
0x14000ad4a  jz      short loc_14000ADA8
0x14000ad4c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000ad53  jnz     short loc_14000ADA8
0x14000ad55  xor     r8d, r8d
0x14000ad58  xor     edx, edx
0x14000ad5a  mov     rcx, rbx
0x14000ad5d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad62  jmp     short loc_14000ADA8
0x14000ad64  mov     ebp, 800h
0x14000ad69  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ad70  test    rax, rax
0x14000ad73  jz      short loc_14000AD8C
0x14000ad75  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000ad7c  jnz     short loc_14000AD8C
0x14000ad7e  mov     r8d, ebp
0x14000ad81  mov     rdx, rsi
0x14000ad84  mov     rcx, rbx
0x14000ad87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad8c  cmp     [rsi], di
0x14000ad8f  jnz     short loc_14000AD9F
0x14000ad91  mov     r8, rbx; unsigned __int64
0x14000ad94  mov     rdx, rbp; unsigned __int16 *
0x14000ad97  mov     rcx, rsi; this
0x14000ad9a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000ad9f  mov     rcx, rsi; lpOutputString
0x14000ada2  call    cs:__imp_OutputDebugStringW
0x14000ada8  test    byte ptr [rbx+4], 4
0x14000adac  jnz     short loc_14000ADB7
0x14000adae  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000adb5  jz      short loc_14000ADC9
0x14000adb7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000adbe  test    rax, rax
0x14000adc1  jz      short loc_14000ADC9
0x14000adc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adc8  nop
0x14000adc9  mov     rbx, [rsp+78h+arg_10]
0x14000add1  add     rsp, 40h
0x14000add5  pop     r15
0x14000add7  pop     r14
0x14000add9  pop     r13
0x14000addb  pop     r12
0x14000addd  pop     rdi
0x14000adde  pop     rsi
0x14000addf  pop     rbp
0x14000ade0  retn
```
