# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004f0c`
- end: `0x14000520d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003590`
- `0x1400038dc`

## callees

- `0x1400034d0`
- `0x140004564`
- `0x140004d48`
- `0x140004f0c`
- `0x140005594`
- `0x1400055b0`
- `0x1400055c4`
- `0x1400055e0`
- `0x1400062a4`
- `0x14002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005037`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005156`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005156`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400051c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400051c8`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
0x140004f0c  mov     rax, rsp
0x140004f0f  mov     [rax+10h], edx
0x140004f12  mov     [rax+8], rcx
0x140004f16  push    rbp
0x140004f17  push    rsi
0x140004f18  push    rdi
0x140004f19  push    r12
0x140004f1b  push    r13
0x140004f1d  push    r14
0x140004f1f  push    r15
0x140004f21  sub     rsp, 50h
0x140004f25  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x140004f2d  mov     [rax+18h], rbx
0x140004f31  mov     r12, r9
0x140004f34  mov     r13, r8
0x140004f37  mov     r10, rcx
0x140004f3a  xor     eax, eax
0x140004f3c  mov     rsi, [rsp+88h+lpOutputString]
0x140004f44  mov     [rsi], ax
0x140004f47  mov     rax, [rsp+88h+arg_60]
0x140004f4f  mov     byte ptr [rax], 0
0x140004f52  mov     r14, [rsp+88h+arg_38]
0x140004f5a  mov     edi, [r14]
0x140004f5d  mov     rbx, [rsp+88h+arg_78]
0x140004f65  mov     [rbx+8], edi
0x140004f68  mov     eax, [r14+4]
0x140004f6c  mov     [rbx+0Ch], eax
0x140004f6f  xor     ebp, ebp
0x140004f71  mov     r15d, [rsp+88h+arg_30]
0x140004f79  mov     ecx, r15d
0x140004f7c  test    r15d, r15d
0x140004f7f  jz      short loc_140004FE7
0x140004f81  sub     ecx, 1
0x140004f84  jz      short loc_140004FDE
0x140004f86  sub     ecx, 1
0x140004f89  jz      short loc_140004F99
0x140004f8b  cmp     ecx, 1
0x140004f8e  jnz     short loc_140004FF0
0x140004f90  mov     ecx, edi; this
0x140004f92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004f97  jmp     short loc_140004FEE
0x140004f99  test    edi, edi
0x140004f9b  js      short loc_140004FD5
0x140004f9d  mov     edi, 8007029Ch
0x140004fa2  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x140004fa6  mov     rax, [rsp+88h+arg_28]
0x140004fae  mov     [rsp+88h+var_60], rax; __int64
0x140004fb3  mov     rax, [rsp+88h+arg_20]
0x140004fbb  mov     [rsp+88h+var_68], rax; __int64
0x140004fc0  mov     rcx, r10; int
0x140004fc3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004fc8  mov     [rbx+8], edi
0x140004fcb  mov     ecx, edi; this
0x140004fcd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004fd2  mov     [rbx+0Ch], eax
0x140004fd5  mov     ecx, edi; this
0x140004fd7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004fdc  jmp     short loc_140004FEE
0x140004fde  mov     ecx, edi; this
0x140004fe0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004fe5  jmp     short loc_140004FEE
0x140004fe7  mov     ecx, edi; this
0x140004fe9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004fee  mov     ebp, eax
0x140004ff0  mov     [rbx], r15d
0x140004ff3  mov     eax, [rsp+88h+arg_70]
0x140004ffa  mov     [rbx+4], eax
0x140004ffd  cmp     dword ptr [r14+8], 1
0x140005002  jnz     short loc_14000500A
0x140005004  or      eax, 8
0x140005007  mov     [rbx+4], eax
0x14000500a  mov     eax, 1
0x14000500f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005017  inc     eax
0x140005019  mov     [rbx+10h], eax
0x14000501c  mov     rax, [rsp+88h+arg_40]
0x140005024  xor     edi, edi
0x140005026  test    rax, rax
0x140005029  jz      short loc_140005030
0x14000502b  cmp     [rax], di
0x14000502e  jnz     short loc_140005033
0x140005030  mov     rax, rdi
0x140005033  mov     [rbx+18h], rax
0x140005037  call    cs:__imp_GetCurrentThreadId
0x14000503d  mov     [rbx+20h], eax
0x140005040  mov     [rbx+38h], r13
0x140005044  mov     eax, [rsp+88h+arg_8]
0x14000504b  mov     [rbx+40h], eax
0x14000504e  mov     [rbx+44h], ebp
0x140005051  mov     rax, [rsp+88h+arg_20]
0x140005059  mov     [rbx+28h], rax
0x14000505d  mov     [rbx+30h], r12
0x140005061  mov     rax, [rsp+88h+arg_28]
0x140005069  mov     [rbx+88h], rax
0x140005070  mov     rax, [rsp+88h+arg_0]
0x140005078  mov     [rbx+90h], rax
0x14000507f  mov     [rbx+48h], rdi
0x140005083  xorps   xmm0, xmm0
0x140005086  xor     eax, eax
0x140005088  movups  xmmword ptr [rbx+68h], xmm0
0x14000508c  mov     [rbx+78h], rax
0x140005090  movups  xmmword ptr [rbx+50h], xmm0
0x140005094  mov     [rbx+60h], rax
0x140005098  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000509f  test    rax, rax
0x1400050a2  jz      short loc_1400050AB
0x1400050a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050a9  jmp     short loc_1400050AE
0x1400050ab  mov     rax, rdi
0x1400050ae  mov     [rbx+80h], rax
0x1400050b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400050bc  test    rax, rax
0x1400050bf  jz      short loc_1400050C9
0x1400050c1  mov     rcx, rbx
0x1400050c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400050d0  test    rax, rax
0x1400050d3  jz      short loc_1400050EB
0x1400050d5  mov     r8d, 400h
0x1400050db  mov     rdx, [rsp+88h+arg_60]
0x1400050e3  mov     rcx, rbx
0x1400050e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400050f2  test    rax, rax
0x1400050f5  jz      short loc_1400050FF
0x1400050f7  mov     rcx, rbx
0x1400050fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005106  test    rax, rax
0x140005109  jz      short loc_140005119
0x14000510b  test    byte ptr [rbx+4], 2
0x14000510f  jnz     short loc_140005119
0x140005111  mov     rcx, rbx
0x140005114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005119  cmp     [rbx+8], edi
0x14000511c  jl      short loc_140005138
0x14000511e  cmp     r15d, 3
0x140005122  jnz     loc_140005207
0x140005128  mov     ecx, 8000FFFFh; this
0x14000512d  mov     [rbx+8], ecx
0x140005130  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005135  mov     [rbx+0Ch], eax
0x140005138  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000513f  jnz     short loc_140005160
0x140005141  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005148  test    rax, rax
0x14000514b  jz      short loc_140005156
0x14000514d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005152  test    al, al
0x140005154  jmp     short loc_14000515E
0x140005156  call    cs:__imp_IsDebuggerPresent
0x14000515c  test    eax, eax
0x14000515e  jz      short loc_140005166
0x140005160  test    byte ptr [rbx+4], 2
0x140005164  jz      short loc_14000518A
0x140005166  mov     rax, cs:g_pfnResultLoggingCallback
0x14000516d  test    rax, rax
0x140005170  jz      short loc_1400051CE
0x140005172  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005179  jnz     short loc_1400051CE
0x14000517b  xor     r8d, r8d
0x14000517e  xor     edx, edx
0x140005180  mov     rcx, rbx
0x140005183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005188  jmp     short loc_1400051CE
0x14000518a  mov     ebp, 800h
0x14000518f  mov     rax, cs:g_pfnResultLoggingCallback
0x140005196  test    rax, rax
0x140005199  jz      short loc_1400051B2
0x14000519b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400051a2  jnz     short loc_1400051B2
0x1400051a4  mov     r8d, ebp
0x1400051a7  mov     rdx, rsi
0x1400051aa  mov     rcx, rbx
0x1400051ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051b2  cmp     [rsi], di
0x1400051b5  jnz     short loc_1400051C5
0x1400051b7  mov     r8, rbx; unsigned __int64
0x1400051ba  mov     rdx, rbp; wchar_t *
0x1400051bd  mov     rcx, rsi; this
0x1400051c0  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400051c5  mov     rcx, rsi; lpOutputString
0x1400051c8  call    cs:__imp_OutputDebugStringW
0x1400051ce  test    byte ptr [rbx+4], 4
0x1400051d2  jnz     short loc_1400051DD
0x1400051d4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400051db  jz      short loc_1400051EF
0x1400051dd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400051e4  test    rax, rax
0x1400051e7  jz      short loc_1400051EF
0x1400051e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051ee  nop
0x1400051ef  mov     rbx, [rsp+88h+arg_10]
0x1400051f7  add     rsp, 50h
0x1400051fb  pop     r15
0x1400051fd  pop     r14
0x1400051ff  pop     r13
0x140005201  pop     r12
0x140005203  pop     rdi
0x140005204  pop     rsi
0x140005205  pop     rbp
0x140005206  retn
0x140005207  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
