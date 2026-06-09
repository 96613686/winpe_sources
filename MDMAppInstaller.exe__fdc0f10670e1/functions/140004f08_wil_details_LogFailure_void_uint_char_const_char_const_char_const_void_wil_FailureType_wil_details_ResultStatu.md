# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004f08`
- end: `0x140005201`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003000`
- `0x140003344`

## callees

- `0x140002f40`
- `0x140004564`
- `0x140004d44`
- `0x140004f08`
- `0x140005560`
- `0x140005580`
- `0x140005594`
- `0x1400055b0`
- `0x140006340`
- `0x14001c010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1400051bc`
- `KERNEL32!OutputDebugStringW` at `0x1400051bc`
- `KERNEL32!IsDebuggerPresent` at `0x14000514a`
- `KERNEL32!IsDebuggerPresent` at `0x14000514a`
- `KERNEL32!GetCurrentThreadId` at `0x14000502b`
- `KERNEL32!GetCurrentThreadId` at `0x14000502b`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x140004f08  mov     [rsp+arg_10], rbx
0x140004f0d  mov     [rsp+arg_8], edx
0x140004f11  mov     [rsp+arg_0], rcx
0x140004f16  push    rbp
0x140004f17  push    rsi
0x140004f18  push    rdi
0x140004f19  push    r12
0x140004f1b  push    r13
0x140004f1d  push    r14
0x140004f1f  push    r15
0x140004f21  sub     rsp, 40h
0x140004f25  mov     r12, r9
0x140004f28  mov     r13, r8
0x140004f2b  mov     r10, rcx
0x140004f2e  xor     eax, eax
0x140004f30  mov     rsi, [rsp+78h+lpOutputString]
0x140004f38  mov     [rsi], ax
0x140004f3b  mov     rax, [rsp+78h+arg_60]
0x140004f43  mov     byte ptr [rax], 0
0x140004f46  mov     r14, [rsp+78h+arg_38]
0x140004f4e  mov     edi, [r14]
0x140004f51  mov     rbx, [rsp+78h+arg_78]
0x140004f59  mov     [rbx+8], edi
0x140004f5c  mov     eax, [r14+4]
0x140004f60  mov     [rbx+0Ch], eax
0x140004f63  xor     ebp, ebp
0x140004f65  mov     r15d, [rsp+78h+arg_30]
0x140004f6d  mov     ecx, r15d
0x140004f70  test    r15d, r15d
0x140004f73  jz      short loc_140004FDB
0x140004f75  sub     ecx, 1
0x140004f78  jz      short loc_140004FD2
0x140004f7a  sub     ecx, 1
0x140004f7d  jz      short loc_140004F8D
0x140004f7f  cmp     ecx, 1
0x140004f82  jnz     short loc_140004FE4
0x140004f84  mov     ecx, edi; this
0x140004f86  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004f8b  jmp     short loc_140004FE2
0x140004f8d  test    edi, edi
0x140004f8f  js      short loc_140004FC9
0x140004f91  mov     edi, 8007029Ch
0x140004f96  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004f9a  mov     rax, [rsp+78h+arg_28]
0x140004fa2  mov     [rsp+78h+var_50], rax; __int64
0x140004fa7  mov     rax, [rsp+78h+arg_20]
0x140004faf  mov     [rsp+78h+var_58], rax; __int64
0x140004fb4  mov     rcx, r10; int
0x140004fb7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004fbc  mov     [rbx+8], edi
0x140004fbf  mov     ecx, edi; this
0x140004fc1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004fc6  mov     [rbx+0Ch], eax
0x140004fc9  mov     ecx, edi; this
0x140004fcb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004fd0  jmp     short loc_140004FE2
0x140004fd2  mov     ecx, edi; this
0x140004fd4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004fd9  jmp     short loc_140004FE2
0x140004fdb  mov     ecx, edi; this
0x140004fdd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004fe2  mov     ebp, eax
0x140004fe4  mov     [rbx], r15d
0x140004fe7  mov     eax, [rsp+78h+arg_70]
0x140004fee  mov     [rbx+4], eax
0x140004ff1  cmp     dword ptr [r14+8], 1
0x140004ff6  jnz     short loc_140004FFE
0x140004ff8  or      eax, 8
0x140004ffb  mov     [rbx+4], eax
0x140004ffe  mov     eax, 1
0x140005003  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000500b  inc     eax
0x14000500d  mov     [rbx+10h], eax
0x140005010  mov     rax, [rsp+78h+arg_40]
0x140005018  xor     edi, edi
0x14000501a  test    rax, rax
0x14000501d  jz      short loc_140005024
0x14000501f  cmp     [rax], di
0x140005022  jnz     short loc_140005027
0x140005024  mov     rax, rdi
0x140005027  mov     [rbx+18h], rax
0x14000502b  call    cs:__imp_GetCurrentThreadId
0x140005031  mov     [rbx+20h], eax
0x140005034  mov     [rbx+38h], r13
0x140005038  mov     eax, [rsp+78h+arg_8]
0x14000503f  mov     [rbx+40h], eax
0x140005042  mov     [rbx+44h], ebp
0x140005045  mov     rax, [rsp+78h+arg_20]
0x14000504d  mov     [rbx+28h], rax
0x140005051  mov     [rbx+30h], r12
0x140005055  mov     rax, [rsp+78h+arg_28]
0x14000505d  mov     [rbx+88h], rax
0x140005064  mov     rax, [rsp+78h+arg_0]
0x14000506c  mov     [rbx+90h], rax
0x140005073  mov     [rbx+48h], rdi
0x140005077  xorps   xmm0, xmm0
0x14000507a  xor     eax, eax
0x14000507c  movups  xmmword ptr [rbx+68h], xmm0
0x140005080  mov     [rbx+78h], rax
0x140005084  movups  xmmword ptr [rbx+50h], xmm0
0x140005088  mov     [rbx+60h], rax
0x14000508c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005093  test    rax, rax
0x140005096  jz      short loc_14000509F
0x140005098  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000509d  jmp     short loc_1400050A2
0x14000509f  mov     rax, rdi
0x1400050a2  mov     [rbx+80h], rax
0x1400050a9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400050b0  test    rax, rax
0x1400050b3  jz      short loc_1400050BD
0x1400050b5  mov     rcx, rbx
0x1400050b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050bd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400050c4  test    rax, rax
0x1400050c7  jz      short loc_1400050DF
0x1400050c9  mov     r8d, 400h
0x1400050cf  mov     rdx, [rsp+78h+arg_60]
0x1400050d7  mov     rcx, rbx
0x1400050da  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050df  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400050e6  test    rax, rax
0x1400050e9  jz      short loc_1400050F3
0x1400050eb  mov     rcx, rbx
0x1400050ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400050f3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400050fa  test    rax, rax
0x1400050fd  jz      short loc_14000510D
0x1400050ff  test    byte ptr [rbx+4], 2
0x140005103  jnz     short loc_14000510D
0x140005105  mov     rcx, rbx
0x140005108  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000510d  cmp     [rbx+8], edi
0x140005110  jl      short loc_14000512C
0x140005112  cmp     r15d, 3
0x140005116  jnz     loc_1400051FB
0x14000511c  mov     ecx, 8000FFFFh; this
0x140005121  mov     [rbx+8], ecx
0x140005124  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005129  mov     [rbx+0Ch], eax
0x14000512c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005133  jnz     short loc_140005154
0x140005135  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000513c  test    rax, rax
0x14000513f  jz      short loc_14000514A
0x140005141  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005146  test    al, al
0x140005148  jmp     short loc_140005152
0x14000514a  call    cs:__imp_IsDebuggerPresent
0x140005150  test    eax, eax
0x140005152  jz      short loc_14000515A
0x140005154  test    byte ptr [rbx+4], 2
0x140005158  jz      short loc_14000517E
0x14000515a  mov     rax, cs:g_pfnResultLoggingCallback
0x140005161  test    rax, rax
0x140005164  jz      short loc_1400051C2
0x140005166  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000516d  jnz     short loc_1400051C2
0x14000516f  xor     r8d, r8d
0x140005172  xor     edx, edx
0x140005174  mov     rcx, rbx
0x140005177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000517c  jmp     short loc_1400051C2
0x14000517e  mov     ebp, 800h
0x140005183  mov     rax, cs:g_pfnResultLoggingCallback
0x14000518a  test    rax, rax
0x14000518d  jz      short loc_1400051A6
0x14000518f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005196  jnz     short loc_1400051A6
0x140005198  mov     r8d, ebp
0x14000519b  mov     rdx, rsi
0x14000519e  mov     rcx, rbx
0x1400051a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051a6  cmp     [rsi], di
0x1400051a9  jnz     short loc_1400051B9
0x1400051ab  mov     r8, rbx; unsigned __int64
0x1400051ae  mov     rdx, rbp; unsigned __int16 *
0x1400051b1  mov     rcx, rsi; this
0x1400051b4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400051b9  mov     rcx, rsi; lpOutputString
0x1400051bc  call    cs:__imp_OutputDebugStringW
0x1400051c2  test    byte ptr [rbx+4], 4
0x1400051c6  jnz     short loc_1400051D1
0x1400051c8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400051cf  jz      short loc_1400051E3
0x1400051d1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400051d8  test    rax, rax
0x1400051db  jz      short loc_1400051E3
0x1400051dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400051e2  nop
0x1400051e3  mov     rbx, [rsp+78h+arg_10]
0x1400051eb  add     rsp, 40h
0x1400051ef  pop     r15
0x1400051f1  pop     r14
0x1400051f3  pop     r13
0x1400051f5  pop     r12
0x1400051f7  pop     rdi
0x1400051f8  pop     rsi
0x1400051f9  pop     rbp
0x1400051fa  retn
0x1400051fb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
