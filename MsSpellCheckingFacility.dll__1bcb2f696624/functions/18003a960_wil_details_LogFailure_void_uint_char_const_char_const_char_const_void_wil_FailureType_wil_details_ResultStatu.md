# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003a960`
- end: `0x18003ac3a`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `730`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x18003a864`
- `0x180065528`
- `0x1800655e8`
- `0x18006ce5c`

## callees

- `0x18003a960`
- `0x18003efd4`
- `0x180054f9c`
- `0x180065470`
- `0x180066c64`
- `0x180068514`
- `0x180068530`
- `0x1800685ec`
- `0x180068608`
- `0x18006a0b0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003aa87`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003aa87`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003abd7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003abd7`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v26; // r9
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18003a960  mov     [rsp+arg_10], rbx
0x18003a965  mov     [rsp+arg_8], edx
0x18003a969  mov     [rsp+arg_0], rcx
0x18003a96e  push    rbp
0x18003a96f  push    rsi
0x18003a970  push    rdi
0x18003a971  push    r12
0x18003a973  push    r13
0x18003a975  push    r14
0x18003a977  push    r15
0x18003a979  sub     rsp, 40h
0x18003a97d  mov     r12, r9
0x18003a980  mov     r13, r8
0x18003a983  mov     r10, rcx
0x18003a986  xor     eax, eax
0x18003a988  mov     rsi, [rsp+78h+lpOutputString]
0x18003a990  mov     [rsi], ax
0x18003a993  mov     rax, [rsp+78h+arg_60]
0x18003a99b  mov     byte ptr [rax], 0
0x18003a99e  mov     r14, [rsp+78h+arg_38]
0x18003a9a6  mov     edi, [r14]
0x18003a9a9  mov     rbx, [rsp+78h+arg_78]
0x18003a9b1  mov     [rbx+8], edi
0x18003a9b4  mov     eax, [r14+4]
0x18003a9b8  mov     [rbx+0Ch], eax
0x18003a9bb  xor     ebp, ebp
0x18003a9bd  mov     r15d, [rsp+78h+arg_30]
0x18003a9c5  mov     ecx, r15d
0x18003a9c8  test    r15d, r15d
0x18003a9cb  jz      short loc_18003AA37
0x18003a9cd  sub     ecx, 1
0x18003a9d0  jz      short loc_18003AA2E
0x18003a9d2  sub     ecx, 1
0x18003a9d5  jz      short loc_18003A9E5
0x18003a9d7  cmp     ecx, 1
0x18003a9da  jnz     short loc_18003AA40
0x18003a9dc  mov     ecx, edi; this
0x18003a9de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003a9e3  jmp     short loc_18003AA3E
0x18003a9e5  test    edi, edi
0x18003a9e7  js      short loc_18003AA25
0x18003a9e9  mov     [rsp+78h+var_40], ebp
0x18003a9ed  mov     edi, 8007029Ch
0x18003a9f2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003a9f6  mov     rax, [rsp+78h+arg_28]
0x18003a9fe  mov     [rsp+78h+var_50], rax; __int64
0x18003aa03  mov     rax, [rsp+78h+arg_20]
0x18003aa0b  mov     [rsp+78h+var_58], rax; __int64
0x18003aa10  mov     rcx, r10; int
0x18003aa13  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003aa18  mov     [rbx+8], edi
0x18003aa1b  mov     ecx, edi; this
0x18003aa1d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003aa22  mov     [rbx+0Ch], eax
0x18003aa25  mov     ecx, edi; this
0x18003aa27  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003aa2c  jmp     short loc_18003AA3E
0x18003aa2e  mov     ecx, edi; this
0x18003aa30  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003aa35  jmp     short loc_18003AA3E
0x18003aa37  mov     ecx, edi; this
0x18003aa39  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003aa3e  mov     ebp, eax
0x18003aa40  mov     [rbx], r15d
0x18003aa43  mov     eax, [rsp+78h+arg_70]
0x18003aa4a  mov     [rbx+4], eax
0x18003aa4d  cmp     dword ptr [r14+8], 1
0x18003aa52  jnz     short loc_18003AA5A
0x18003aa54  or      eax, 8
0x18003aa57  mov     [rbx+4], eax
0x18003aa5a  mov     eax, 1
0x18003aa5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003aa67  inc     eax
0x18003aa69  mov     [rbx+10h], eax
0x18003aa6c  mov     rax, [rsp+78h+arg_40]
0x18003aa74  xor     edi, edi
0x18003aa76  test    rax, rax
0x18003aa79  jz      short loc_18003AA80
0x18003aa7b  cmp     [rax], di
0x18003aa7e  jnz     short loc_18003AA83
0x18003aa80  mov     rax, rdi
0x18003aa83  mov     [rbx+18h], rax
0x18003aa87  call    cs:__imp_GetCurrentThreadId
0x18003aa8d  mov     [rbx+20h], eax
0x18003aa90  mov     [rbx+38h], r13
0x18003aa94  mov     eax, [rsp+78h+arg_8]
0x18003aa9b  mov     [rbx+40h], eax
0x18003aa9e  mov     [rbx+44h], ebp
0x18003aaa1  mov     rax, [rsp+78h+arg_20]
0x18003aaa9  mov     [rbx+28h], rax
0x18003aaad  mov     [rbx+30h], r12
0x18003aab1  mov     rax, [rsp+78h+arg_28]
0x18003aab9  mov     [rbx+88h], rax
0x18003aac0  mov     rax, [rsp+78h+arg_0]
0x18003aac8  mov     [rbx+90h], rax
0x18003aacf  mov     [rbx+48h], rdi
0x18003aad3  xorps   xmm0, xmm0
0x18003aad6  xor     eax, eax
0x18003aad8  movups  xmmword ptr [rbx+68h], xmm0
0x18003aadc  mov     [rbx+78h], rax
0x18003aae0  movups  xmmword ptr [rbx+50h], xmm0
0x18003aae4  mov     [rbx+60h], rax
0x18003aae8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003aaef  test    rax, rax
0x18003aaf2  jz      short loc_18003AAFB
0x18003aaf4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003aaf9  jmp     short loc_18003AAFE
0x18003aafb  mov     rax, rdi
0x18003aafe  mov     [rbx+80h], rax
0x18003ab05  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003ab0c  test    rax, rax
0x18003ab0f  jz      short loc_18003AB19
0x18003ab11  mov     rcx, rbx
0x18003ab14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab19  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003ab20  test    rax, rax
0x18003ab23  jz      short loc_18003AB3B
0x18003ab25  mov     r8d, 400h
0x18003ab2b  mov     rdx, [rsp+78h+arg_60]
0x18003ab33  mov     rcx, rbx
0x18003ab36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab3b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003ab42  test    rax, rax
0x18003ab45  jz      short loc_18003AB4F
0x18003ab47  mov     rcx, rbx
0x18003ab4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab4f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003ab56  test    rax, rax
0x18003ab59  jz      short loc_18003AB69
0x18003ab5b  test    byte ptr [rbx+4], 2
0x18003ab5f  jnz     short loc_18003AB69
0x18003ab61  mov     rcx, rbx
0x18003ab64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ab69  cmp     [rbx+8], edi
0x18003ab6c  jl      short loc_18003AB8A
0x18003ab6e  cmp     r15d, 3
0x18003ab72  jz      short loc_18003AB7A
0x18003ab74  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x18003ab7a  mov     ecx, 8000FFFFh; this
0x18003ab7f  mov     [rbx+8], ecx
0x18003ab82  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003ab87  mov     [rbx+0Ch], eax
0x18003ab8a  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x18003ab8f  test    al, al
0x18003ab91  jz      short loc_18003ABDF
0x18003ab93  test    byte ptr [rbx+4], 2
0x18003ab97  jnz     short loc_18003ABDF
0x18003ab99  mov     ebp, 800h
0x18003ab9e  mov     rax, cs:g_pfnResultLoggingCallback
0x18003aba5  test    rax, rax
0x18003aba8  jz      short loc_18003ABC1
0x18003abaa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003abb1  jnz     short loc_18003ABC1
0x18003abb3  mov     r8d, ebp
0x18003abb6  mov     rdx, rsi
0x18003abb9  mov     rcx, rbx
0x18003abbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003abc1  cmp     [rsi], di
0x18003abc4  jnz     short loc_18003ABD4
0x18003abc6  mov     r8, rbx; unsigned __int64
0x18003abc9  mov     rdx, rbp; unsigned __int16 *
0x18003abcc  mov     rcx, rsi; this
0x18003abcf  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003abd4  mov     rcx, rsi; lpOutputString
0x18003abd7  call    cs:__imp_OutputDebugStringW
0x18003abdd  jmp     short loc_18003AC01
0x18003abdf  mov     rax, cs:g_pfnResultLoggingCallback
0x18003abe6  test    rax, rax
0x18003abe9  jz      short loc_18003AC01
0x18003abeb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003abf2  jnz     short loc_18003AC01
0x18003abf4  xor     r8d, r8d
0x18003abf7  xor     edx, edx
0x18003abf9  mov     rcx, rbx
0x18003abfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac01  test    byte ptr [rbx+4], 4
0x18003ac05  jnz     short loc_18003AC10
0x18003ac07  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003ac0e  jz      short loc_18003AC22
0x18003ac10  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003ac17  test    rax, rax
0x18003ac1a  jz      short loc_18003AC22
0x18003ac1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ac21  nop
0x18003ac22  mov     rbx, [rsp+78h+arg_10]
0x18003ac2a  add     rsp, 40h
0x18003ac2e  pop     r15
0x18003ac30  pop     r14
0x18003ac32  pop     r13
0x18003ac34  pop     r12
0x18003ac36  pop     rdi
0x18003ac37  pop     rsi
0x18003ac38  pop     rbp
0x18003ac39  retn
```
