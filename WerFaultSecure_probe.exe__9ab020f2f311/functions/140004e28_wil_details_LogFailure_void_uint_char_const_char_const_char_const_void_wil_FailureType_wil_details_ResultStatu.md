# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004e28`
- end: `0x140005121`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004c40`

## callees

- `0x1400037e4`
- `0x140003bcc`
- `0x140003f30`
- `0x140004a5c`
- `0x140004e28`
- `0x140005ed8`
- `0x140005ef4`
- `0x140005f10`
- `0x140006008`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004f4b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004f4b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400050dc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400050dc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000506a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000506a`

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
  wil::details::in1diag4 *v24; // rcx
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
      wil::details::in1diag4::_FailFastImmediate_Unexpected(v24);
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x140004e28  mov     [rsp+arg_10], rbx
0x140004e2d  mov     [rsp+arg_8], edx
0x140004e31  mov     [rsp+arg_0], rcx
0x140004e36  push    rbp
0x140004e37  push    rsi
0x140004e38  push    rdi
0x140004e39  push    r12
0x140004e3b  push    r13
0x140004e3d  push    r14
0x140004e3f  push    r15
0x140004e41  sub     rsp, 40h
0x140004e45  mov     r12, r9
0x140004e48  mov     r13, r8
0x140004e4b  mov     r10, rcx
0x140004e4e  xor     eax, eax
0x140004e50  mov     rsi, [rsp+78h+lpOutputString]
0x140004e58  mov     [rsi], ax
0x140004e5b  mov     rax, [rsp+78h+arg_60]
0x140004e63  mov     byte ptr [rax], 0
0x140004e66  mov     r14, [rsp+78h+arg_38]
0x140004e6e  mov     edi, [r14]
0x140004e71  mov     rbx, [rsp+78h+arg_78]
0x140004e79  mov     [rbx+8], edi
0x140004e7c  mov     eax, [r14+4]
0x140004e80  mov     [rbx+0Ch], eax
0x140004e83  xor     ebp, ebp
0x140004e85  mov     r15d, [rsp+78h+arg_30]
0x140004e8d  mov     ecx, r15d
0x140004e90  test    r15d, r15d
0x140004e93  jz      short loc_140004EFB
0x140004e95  sub     ecx, 1
0x140004e98  jz      short loc_140004EF2
0x140004e9a  sub     ecx, 1
0x140004e9d  jz      short loc_140004EAD
0x140004e9f  cmp     ecx, 1
0x140004ea2  jnz     short loc_140004F04
0x140004ea4  mov     ecx, edi; this
0x140004ea6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004eab  jmp     short loc_140004F02
0x140004ead  test    edi, edi
0x140004eaf  js      short loc_140004EE9
0x140004eb1  mov     edi, 8007029Ch
0x140004eb6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004eba  mov     rax, [rsp+78h+arg_28]
0x140004ec2  mov     [rsp+78h+var_50], rax; __int64
0x140004ec7  mov     rax, [rsp+78h+arg_20]
0x140004ecf  mov     [rsp+78h+var_58], rax; __int64
0x140004ed4  mov     rcx, r10; int
0x140004ed7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004edc  mov     [rbx+8], edi
0x140004edf  mov     ecx, edi; this
0x140004ee1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004ee6  mov     [rbx+0Ch], eax
0x140004ee9  mov     ecx, edi; this
0x140004eeb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004ef0  jmp     short loc_140004F02
0x140004ef2  mov     ecx, edi; this
0x140004ef4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004ef9  jmp     short loc_140004F02
0x140004efb  mov     ecx, edi; this
0x140004efd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004f02  mov     ebp, eax
0x140004f04  mov     [rbx], r15d
0x140004f07  mov     eax, [rsp+78h+arg_70]
0x140004f0e  mov     [rbx+4], eax
0x140004f11  cmp     dword ptr [r14+8], 1
0x140004f16  jnz     short loc_140004F1E
0x140004f18  or      eax, 8
0x140004f1b  mov     [rbx+4], eax
0x140004f1e  mov     eax, 1
0x140004f23  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004f2b  inc     eax
0x140004f2d  mov     [rbx+10h], eax
0x140004f30  mov     rax, [rsp+78h+arg_40]
0x140004f38  xor     edi, edi
0x140004f3a  test    rax, rax
0x140004f3d  jz      short loc_140004F44
0x140004f3f  cmp     [rax], di
0x140004f42  jnz     short loc_140004F47
0x140004f44  mov     rax, rdi
0x140004f47  mov     [rbx+18h], rax
0x140004f4b  call    cs:__imp_GetCurrentThreadId
0x140004f51  mov     [rbx+20h], eax
0x140004f54  mov     [rbx+38h], r13
0x140004f58  mov     eax, [rsp+78h+arg_8]
0x140004f5f  mov     [rbx+40h], eax
0x140004f62  mov     [rbx+44h], ebp
0x140004f65  mov     rax, [rsp+78h+arg_20]
0x140004f6d  mov     [rbx+28h], rax
0x140004f71  mov     [rbx+30h], r12
0x140004f75  mov     rax, [rsp+78h+arg_28]
0x140004f7d  mov     [rbx+88h], rax
0x140004f84  mov     rax, [rsp+78h+arg_0]
0x140004f8c  mov     [rbx+90h], rax
0x140004f93  mov     [rbx+48h], rdi
0x140004f97  xorps   xmm0, xmm0
0x140004f9a  xor     eax, eax
0x140004f9c  movups  xmmword ptr [rbx+68h], xmm0
0x140004fa0  mov     [rbx+78h], rax
0x140004fa4  movups  xmmword ptr [rbx+50h], xmm0
0x140004fa8  mov     [rbx+60h], rax
0x140004fac  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004fb3  test    rax, rax
0x140004fb6  jz      short loc_140004FBF
0x140004fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fbd  jmp     short loc_140004FC2
0x140004fbf  mov     rax, rdi
0x140004fc2  mov     [rbx+80h], rax
0x140004fc9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004fd0  test    rax, rax
0x140004fd3  jz      short loc_140004FDD
0x140004fd5  mov     rcx, rbx
0x140004fd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fdd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004fe4  test    rax, rax
0x140004fe7  jz      short loc_140004FFF
0x140004fe9  mov     r8d, 400h
0x140004fef  mov     rdx, [rsp+78h+arg_60]
0x140004ff7  mov     rcx, rbx
0x140004ffa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fff  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005006  test    rax, rax
0x140005009  jz      short loc_140005013
0x14000500b  mov     rcx, rbx
0x14000500e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005013  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000501a  test    rax, rax
0x14000501d  jz      short loc_14000502D
0x14000501f  test    byte ptr [rbx+4], 2
0x140005023  jnz     short loc_14000502D
0x140005025  mov     rcx, rbx
0x140005028  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000502d  cmp     [rbx+8], edi
0x140005030  jl      short loc_14000504C
0x140005032  cmp     r15d, 3
0x140005036  jnz     loc_14000511B
0x14000503c  mov     ecx, 8000FFFFh; this
0x140005041  mov     [rbx+8], ecx
0x140005044  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005049  mov     [rbx+0Ch], eax
0x14000504c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005053  jnz     short loc_140005074
0x140005055  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000505c  test    rax, rax
0x14000505f  jz      short loc_14000506A
0x140005061  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005066  test    al, al
0x140005068  jmp     short loc_140005072
0x14000506a  call    cs:__imp_IsDebuggerPresent
0x140005070  test    eax, eax
0x140005072  jz      short loc_14000507A
0x140005074  test    byte ptr [rbx+4], 2
0x140005078  jz      short loc_14000509E
0x14000507a  mov     rax, cs:g_pfnResultLoggingCallback
0x140005081  test    rax, rax
0x140005084  jz      short loc_1400050E2
0x140005086  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000508d  jnz     short loc_1400050E2
0x14000508f  xor     r8d, r8d
0x140005092  xor     edx, edx
0x140005094  mov     rcx, rbx
0x140005097  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000509c  jmp     short loc_1400050E2
0x14000509e  mov     ebp, 800h
0x1400050a3  mov     rax, cs:g_pfnResultLoggingCallback
0x1400050aa  test    rax, rax
0x1400050ad  jz      short loc_1400050C6
0x1400050af  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400050b6  jnz     short loc_1400050C6
0x1400050b8  mov     r8d, ebp
0x1400050bb  mov     rdx, rsi
0x1400050be  mov     rcx, rbx
0x1400050c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050c6  cmp     [rsi], di
0x1400050c9  jnz     short loc_1400050D9
0x1400050cb  mov     r8, rbx; unsigned __int64
0x1400050ce  mov     rdx, rbp; wchar_t *
0x1400050d1  mov     rcx, rsi; this
0x1400050d4  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400050d9  mov     rcx, rsi; lpOutputString
0x1400050dc  call    cs:__imp_OutputDebugStringW
0x1400050e2  test    byte ptr [rbx+4], 4
0x1400050e6  jnz     short loc_1400050F1
0x1400050e8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400050ef  jz      short loc_140005103
0x1400050f1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400050f8  test    rax, rax
0x1400050fb  jz      short loc_140005103
0x1400050fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005102  nop
0x140005103  mov     rbx, [rsp+78h+arg_10]
0x14000510b  add     rsp, 40h
0x14000510f  pop     r15
0x140005111  pop     r14
0x140005113  pop     r13
0x140005115  pop     r12
0x140005117  pop     rdi
0x140005118  pop     rsi
0x140005119  pop     rbp
0x14000511a  retn
0x14000511b  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
