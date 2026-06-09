# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004e74`
- end: `0x18000516d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003680`

## callees

- `0x1800030bc`
- `0x180004514`
- `0x180004cb0`
- `0x180004e74`
- `0x1800053f4`
- `0x180005410`
- `0x180005424`
- `0x180005440`
- `0x18000656c`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800050b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800050b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005128`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005128`

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
0x180004e74  mov     [rsp+arg_10], rbx
0x180004e79  mov     [rsp+arg_8], edx
0x180004e7d  mov     [rsp+arg_0], rcx
0x180004e82  push    rbp
0x180004e83  push    rsi
0x180004e84  push    rdi
0x180004e85  push    r12
0x180004e87  push    r13
0x180004e89  push    r14
0x180004e8b  push    r15
0x180004e8d  sub     rsp, 40h
0x180004e91  mov     r12, r9
0x180004e94  mov     r13, r8
0x180004e97  mov     r10, rcx
0x180004e9a  xor     eax, eax
0x180004e9c  mov     rsi, [rsp+78h+lpOutputString]
0x180004ea4  mov     [rsi], ax
0x180004ea7  mov     rax, [rsp+78h+arg_60]
0x180004eaf  mov     byte ptr [rax], 0
0x180004eb2  mov     r14, [rsp+78h+arg_38]
0x180004eba  mov     edi, [r14]
0x180004ebd  mov     rbx, [rsp+78h+arg_78]
0x180004ec5  mov     [rbx+8], edi
0x180004ec8  mov     eax, [r14+4]
0x180004ecc  mov     [rbx+0Ch], eax
0x180004ecf  xor     ebp, ebp
0x180004ed1  mov     r15d, [rsp+78h+arg_30]
0x180004ed9  mov     ecx, r15d
0x180004edc  test    r15d, r15d
0x180004edf  jz      short loc_180004F47
0x180004ee1  sub     ecx, 1
0x180004ee4  jz      short loc_180004F3E
0x180004ee6  sub     ecx, 1
0x180004ee9  jz      short loc_180004EF9
0x180004eeb  cmp     ecx, 1
0x180004eee  jnz     short loc_180004F50
0x180004ef0  mov     ecx, edi; this
0x180004ef2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004ef7  jmp     short loc_180004F4E
0x180004ef9  test    edi, edi
0x180004efb  js      short loc_180004F35
0x180004efd  mov     edi, 8007029Ch
0x180004f02  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004f06  mov     rax, [rsp+78h+arg_28]
0x180004f0e  mov     [rsp+78h+var_50], rax; __int64
0x180004f13  mov     rax, [rsp+78h+arg_20]
0x180004f1b  mov     [rsp+78h+var_58], rax; __int64
0x180004f20  mov     rcx, r10; int
0x180004f23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004f28  mov     [rbx+8], edi
0x180004f2b  mov     ecx, edi; this
0x180004f2d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004f32  mov     [rbx+0Ch], eax
0x180004f35  mov     ecx, edi; this
0x180004f37  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004f3c  jmp     short loc_180004F4E
0x180004f3e  mov     ecx, edi; this
0x180004f40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004f45  jmp     short loc_180004F4E
0x180004f47  mov     ecx, edi; this
0x180004f49  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004f4e  mov     ebp, eax
0x180004f50  mov     [rbx], r15d
0x180004f53  mov     eax, [rsp+78h+arg_70]
0x180004f5a  mov     [rbx+4], eax
0x180004f5d  cmp     dword ptr [r14+8], 1
0x180004f62  jnz     short loc_180004F6A
0x180004f64  or      eax, 8
0x180004f67  mov     [rbx+4], eax
0x180004f6a  mov     eax, 1
0x180004f6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f77  inc     eax
0x180004f79  mov     [rbx+10h], eax
0x180004f7c  mov     rax, [rsp+78h+arg_40]
0x180004f84  xor     edi, edi
0x180004f86  test    rax, rax
0x180004f89  jz      short loc_180004F90
0x180004f8b  cmp     [rax], di
0x180004f8e  jnz     short loc_180004F93
0x180004f90  mov     rax, rdi
0x180004f93  mov     [rbx+18h], rax
0x180004f97  call    cs:__imp_GetCurrentThreadId
0x180004f9d  mov     [rbx+20h], eax
0x180004fa0  mov     [rbx+38h], r13
0x180004fa4  mov     eax, [rsp+78h+arg_8]
0x180004fab  mov     [rbx+40h], eax
0x180004fae  mov     [rbx+44h], ebp
0x180004fb1  mov     rax, [rsp+78h+arg_20]
0x180004fb9  mov     [rbx+28h], rax
0x180004fbd  mov     [rbx+30h], r12
0x180004fc1  mov     rax, [rsp+78h+arg_28]
0x180004fc9  mov     [rbx+88h], rax
0x180004fd0  mov     rax, [rsp+78h+arg_0]
0x180004fd8  mov     [rbx+90h], rax
0x180004fdf  mov     [rbx+48h], rdi
0x180004fe3  xorps   xmm0, xmm0
0x180004fe6  xor     eax, eax
0x180004fe8  movups  xmmword ptr [rbx+68h], xmm0
0x180004fec  mov     [rbx+78h], rax
0x180004ff0  movups  xmmword ptr [rbx+50h], xmm0
0x180004ff4  mov     [rbx+60h], rax
0x180004ff8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004fff  test    rax, rax
0x180005002  jz      short loc_18000500B
0x180005004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005009  jmp     short loc_18000500E
0x18000500b  mov     rax, rdi
0x18000500e  mov     [rbx+80h], rax
0x180005015  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000501c  test    rax, rax
0x18000501f  jz      short loc_180005029
0x180005021  mov     rcx, rbx
0x180005024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005029  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005030  test    rax, rax
0x180005033  jz      short loc_18000504B
0x180005035  mov     r8d, 400h
0x18000503b  mov     rdx, [rsp+78h+arg_60]
0x180005043  mov     rcx, rbx
0x180005046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005052  test    rax, rax
0x180005055  jz      short loc_18000505F
0x180005057  mov     rcx, rbx
0x18000505a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000505f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005066  test    rax, rax
0x180005069  jz      short loc_180005079
0x18000506b  test    byte ptr [rbx+4], 2
0x18000506f  jnz     short loc_180005079
0x180005071  mov     rcx, rbx
0x180005074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005079  cmp     [rbx+8], edi
0x18000507c  jl      short loc_180005098
0x18000507e  cmp     r15d, 3
0x180005082  jnz     loc_180005167
0x180005088  mov     ecx, 8000FFFFh; this
0x18000508d  mov     [rbx+8], ecx
0x180005090  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005095  mov     [rbx+0Ch], eax
0x180005098  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000509f  jnz     short loc_1800050C0
0x1800050a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800050a8  test    rax, rax
0x1800050ab  jz      short loc_1800050B6
0x1800050ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050b2  test    al, al
0x1800050b4  jmp     short loc_1800050BE
0x1800050b6  call    cs:__imp_IsDebuggerPresent
0x1800050bc  test    eax, eax
0x1800050be  jz      short loc_1800050C6
0x1800050c0  test    byte ptr [rbx+4], 2
0x1800050c4  jz      short loc_1800050EA
0x1800050c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050cd  test    rax, rax
0x1800050d0  jz      short loc_18000512E
0x1800050d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800050d9  jnz     short loc_18000512E
0x1800050db  xor     r8d, r8d
0x1800050de  xor     edx, edx
0x1800050e0  mov     rcx, rbx
0x1800050e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050e8  jmp     short loc_18000512E
0x1800050ea  mov     ebp, 800h
0x1800050ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800050f6  test    rax, rax
0x1800050f9  jz      short loc_180005112
0x1800050fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005102  jnz     short loc_180005112
0x180005104  mov     r8d, ebp
0x180005107  mov     rdx, rsi
0x18000510a  mov     rcx, rbx
0x18000510d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005112  cmp     [rsi], di
0x180005115  jnz     short loc_180005125
0x180005117  mov     r8, rbx; unsigned __int64
0x18000511a  mov     rdx, rbp; unsigned __int16 *
0x18000511d  mov     rcx, rsi; this
0x180005120  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005125  mov     rcx, rsi; lpOutputString
0x180005128  call    cs:__imp_OutputDebugStringW
0x18000512e  test    byte ptr [rbx+4], 4
0x180005132  jnz     short loc_18000513D
0x180005134  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000513b  jz      short loc_18000514F
0x18000513d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005144  test    rax, rax
0x180005147  jz      short loc_18000514F
0x180005149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000514e  nop
0x18000514f  mov     rbx, [rsp+78h+arg_10]
0x180005157  add     rsp, 40h
0x18000515b  pop     r15
0x18000515d  pop     r14
0x18000515f  pop     r13
0x180005161  pop     r12
0x180005163  pop     rdi
0x180005164  pop     rsi
0x180005165  pop     rbp
0x180005166  retn
0x180005167  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
