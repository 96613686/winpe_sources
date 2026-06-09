# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004e10`
- end: `0x180005108`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002db8`

## callees

- `0x1800027fc`
- `0x180004334`
- `0x180004b74`
- `0x180004e10`
- `0x180005914`
- `0x180005930`
- `0x180005944`
- `0x180005960`
- `0x1800078e4`
- `0x180009010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004f33`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005052`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005052`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050c4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800050c4`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x180004e10  mov     [rsp+arg_10], rbx
0x180004e15  mov     [rsp+arg_8], edx
0x180004e19  mov     [rsp+arg_0], rcx
0x180004e1e  push    rbp
0x180004e1f  push    rsi
0x180004e20  push    rdi
0x180004e21  push    r12
0x180004e23  push    r13
0x180004e25  push    r14
0x180004e27  push    r15
0x180004e29  sub     rsp, 40h
0x180004e2d  mov     r14, [rsp+78h+arg_38]
0x180004e35  xor     eax, eax
0x180004e37  mov     rbx, [rsp+78h+arg_78]
0x180004e3f  xor     ebp, ebp
0x180004e41  mov     r15d, [rsp+78h+arg_30]
0x180004e49  mov     r10, rcx
0x180004e4c  mov     rsi, [rsp+78h+lpOutputString]
0x180004e54  mov     r12, r9
0x180004e57  mov     r13, r8
0x180004e5a  mov     ecx, r15d
0x180004e5d  mov     [rsi], ax
0x180004e60  mov     rax, [rsp+78h+arg_60]
0x180004e68  mov     byte ptr [rax], 0
0x180004e6b  mov     edi, [r14]
0x180004e6e  mov     [rbx+8], edi
0x180004e71  mov     eax, [r14+4]
0x180004e75  mov     [rbx+0Ch], eax
0x180004e78  test    r15d, r15d
0x180004e7b  jz      short loc_180004EE3
0x180004e7d  sub     ecx, 1
0x180004e80  jz      short loc_180004EDA
0x180004e82  sub     ecx, 1
0x180004e85  jz      short loc_180004E95
0x180004e87  cmp     ecx, 1
0x180004e8a  jnz     short loc_180004EEC
0x180004e8c  mov     ecx, edi; this
0x180004e8e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004e93  jmp     short loc_180004EEA
0x180004e95  test    edi, edi
0x180004e97  js      short loc_180004ED1
0x180004e99  mov     rax, [rsp+78h+arg_28]
0x180004ea1  mov     edi, 8007029Ch
0x180004ea6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004eaa  mov     rcx, r10; int
0x180004ead  mov     [rsp+78h+var_50], rax; __int64
0x180004eb2  mov     rax, [rsp+78h+arg_20]
0x180004eba  mov     [rsp+78h+var_58], rax; __int64
0x180004ebf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004ec4  mov     ecx, edi; this
0x180004ec6  mov     [rbx+8], edi
0x180004ec9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004ece  mov     [rbx+0Ch], eax
0x180004ed1  mov     ecx, edi; this
0x180004ed3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004ed8  jmp     short loc_180004EEA
0x180004eda  mov     ecx, edi; this
0x180004edc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004ee1  jmp     short loc_180004EEA
0x180004ee3  mov     ecx, edi; this
0x180004ee5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004eea  mov     ebp, eax
0x180004eec  mov     eax, [rsp+78h+arg_70]
0x180004ef3  mov     [rbx+4], eax
0x180004ef6  mov     [rbx], r15d
0x180004ef9  cmp     dword ptr [r14+8], 1
0x180004efe  jnz     short loc_180004F06
0x180004f00  or      eax, 8
0x180004f03  mov     [rbx+4], eax
0x180004f06  mov     eax, 1
0x180004f0b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004f13  inc     eax
0x180004f15  xor     edi, edi
0x180004f17  mov     [rbx+10h], eax
0x180004f1a  mov     rax, [rsp+78h+arg_40]
0x180004f22  test    rax, rax
0x180004f25  jz      short loc_180004F2C
0x180004f27  cmp     [rax], di
0x180004f2a  jnz     short loc_180004F2F
0x180004f2c  mov     rax, rdi
0x180004f2f  mov     [rbx+18h], rax
0x180004f33  call    cs:__imp_GetCurrentThreadId
0x180004f39  mov     [rbx+38h], r13
0x180004f3d  xorps   xmm0, xmm0
0x180004f40  mov     [rbx+20h], eax
0x180004f43  mov     eax, [rsp+78h+arg_8]
0x180004f4a  mov     [rbx+40h], eax
0x180004f4d  mov     rax, [rsp+78h+arg_20]
0x180004f55  mov     [rbx+28h], rax
0x180004f59  mov     rax, [rsp+78h+arg_28]
0x180004f61  mov     [rbx+88h], rax
0x180004f68  mov     rax, [rsp+78h+arg_0]
0x180004f70  mov     [rbx+90h], rax
0x180004f77  xor     eax, eax
0x180004f79  mov     [rbx+44h], ebp
0x180004f7c  mov     [rbx+30h], r12
0x180004f80  mov     [rbx+48h], rdi
0x180004f84  movups  xmmword ptr [rbx+68h], xmm0
0x180004f88  mov     [rbx+78h], rax
0x180004f8c  movups  xmmword ptr [rbx+50h], xmm0
0x180004f90  mov     [rbx+60h], rax
0x180004f94  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f9b  test    rax, rax
0x180004f9e  jz      short loc_180004FA7
0x180004fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fa5  jmp     short loc_180004FAA
0x180004fa7  mov     rax, rdi
0x180004faa  mov     [rbx+80h], rax
0x180004fb1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004fb8  test    rax, rax
0x180004fbb  jz      short loc_180004FC5
0x180004fbd  mov     rcx, rbx
0x180004fc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fc5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004fcc  test    rax, rax
0x180004fcf  jz      short loc_180004FE7
0x180004fd1  mov     rdx, [rsp+78h+arg_60]
0x180004fd9  mov     r8d, 400h
0x180004fdf  mov     rcx, rbx
0x180004fe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004fee  test    rax, rax
0x180004ff1  jz      short loc_180004FFB
0x180004ff3  mov     rcx, rbx
0x180004ff6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ffb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005002  test    rax, rax
0x180005005  jz      short loc_180005015
0x180005007  test    byte ptr [rbx+4], 2
0x18000500b  jnz     short loc_180005015
0x18000500d  mov     rcx, rbx
0x180005010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005015  cmp     [rbx+8], edi
0x180005018  jl      short loc_180005034
0x18000501a  cmp     r15d, 3
0x18000501e  jnz     loc_180005102
0x180005024  mov     ecx, 8000FFFFh; this
0x180005029  mov     [rbx+8], ecx
0x18000502c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005031  mov     [rbx+0Ch], eax
0x180005034  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000503b  jnz     short loc_18000505C
0x18000503d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005044  test    rax, rax
0x180005047  jz      short loc_180005052
0x180005049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000504e  test    al, al
0x180005050  jmp     short loc_18000505A
0x180005052  call    cs:__imp_IsDebuggerPresent
0x180005058  test    eax, eax
0x18000505a  jz      short loc_180005062
0x18000505c  test    byte ptr [rbx+4], 2
0x180005060  jz      short loc_180005086
0x180005062  mov     rax, cs:g_pfnResultLoggingCallback
0x180005069  test    rax, rax
0x18000506c  jz      short loc_1800050CA
0x18000506e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005075  jnz     short loc_1800050CA
0x180005077  xor     r8d, r8d
0x18000507a  xor     edx, edx
0x18000507c  mov     rcx, rbx
0x18000507f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005084  jmp     short loc_1800050CA
0x180005086  mov     rax, cs:g_pfnResultLoggingCallback
0x18000508d  mov     ebp, 800h
0x180005092  test    rax, rax
0x180005095  jz      short loc_1800050AE
0x180005097  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000509e  jnz     short loc_1800050AE
0x1800050a0  mov     r8d, ebp
0x1800050a3  mov     rdx, rsi
0x1800050a6  mov     rcx, rbx
0x1800050a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ae  cmp     [rsi], di
0x1800050b1  jnz     short loc_1800050C1
0x1800050b3  mov     r8, rbx; unsigned __int64
0x1800050b6  mov     rdx, rbp; unsigned __int16 *
0x1800050b9  mov     rcx, rsi; this
0x1800050bc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800050c1  mov     rcx, rsi; lpOutputString
0x1800050c4  call    cs:__imp_OutputDebugStringW
0x1800050ca  test    byte ptr [rbx+4], 4
0x1800050ce  jnz     short loc_1800050D9
0x1800050d0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800050d7  jz      short loc_1800050EA
0x1800050d9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800050e0  test    rax, rax
0x1800050e3  jz      short loc_1800050EA
0x1800050e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800050ea  mov     rbx, [rsp+78h+arg_10]
0x1800050f2  add     rsp, 40h
0x1800050f6  pop     r15
0x1800050f8  pop     r14
0x1800050fa  pop     r13
0x1800050fc  pop     r12
0x1800050fe  pop     rdi
0x1800050ff  pop     rsi
0x180005100  pop     rbp
0x180005101  retn
0x180005102  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
