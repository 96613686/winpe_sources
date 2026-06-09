# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006df0`
- end: `0x1400070e9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002f94`

## callees

- `0x140002690`
- `0x140005204`
- `0x140006940`
- `0x140006df0`
- `0x140007374`
- `0x140007390`
- `0x1400073a4`
- `0x1400073c0`
- `0x1400087f4`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006f13`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007032`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140007032`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400070a4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400070a4`

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
0x140006df0  mov     [rsp+arg_10], rbx
0x140006df5  mov     [rsp+arg_8], edx
0x140006df9  mov     [rsp+arg_0], rcx
0x140006dfe  push    rbp
0x140006dff  push    rsi
0x140006e00  push    rdi
0x140006e01  push    r12
0x140006e03  push    r13
0x140006e05  push    r14
0x140006e07  push    r15
0x140006e09  sub     rsp, 40h
0x140006e0d  mov     r12, r9
0x140006e10  mov     r13, r8
0x140006e13  mov     r10, rcx
0x140006e16  xor     eax, eax
0x140006e18  mov     rsi, [rsp+78h+lpOutputString]
0x140006e20  mov     [rsi], ax
0x140006e23  mov     rax, [rsp+78h+arg_60]
0x140006e2b  mov     byte ptr [rax], 0
0x140006e2e  mov     r14, [rsp+78h+arg_38]
0x140006e36  mov     edi, [r14]
0x140006e39  mov     rbx, [rsp+78h+arg_78]
0x140006e41  mov     [rbx+8], edi
0x140006e44  mov     eax, [r14+4]
0x140006e48  mov     [rbx+0Ch], eax
0x140006e4b  xor     ebp, ebp
0x140006e4d  mov     r15d, [rsp+78h+arg_30]
0x140006e55  mov     ecx, r15d
0x140006e58  test    r15d, r15d
0x140006e5b  jz      short loc_140006EC3
0x140006e5d  sub     ecx, 1
0x140006e60  jz      short loc_140006EBA
0x140006e62  sub     ecx, 1
0x140006e65  jz      short loc_140006E75
0x140006e67  cmp     ecx, 1
0x140006e6a  jnz     short loc_140006ECC
0x140006e6c  mov     ecx, edi; this
0x140006e6e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006e73  jmp     short loc_140006ECA
0x140006e75  test    edi, edi
0x140006e77  js      short loc_140006EB1
0x140006e79  mov     edi, 8007029Ch
0x140006e7e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006e82  mov     rax, [rsp+78h+arg_28]
0x140006e8a  mov     [rsp+78h+var_50], rax; __int64
0x140006e8f  mov     rax, [rsp+78h+arg_20]
0x140006e97  mov     [rsp+78h+var_58], rax; __int64
0x140006e9c  mov     rcx, r10; int
0x140006e9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006ea4  mov     [rbx+8], edi
0x140006ea7  mov     ecx, edi; this
0x140006ea9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006eae  mov     [rbx+0Ch], eax
0x140006eb1  mov     ecx, edi; this
0x140006eb3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006eb8  jmp     short loc_140006ECA
0x140006eba  mov     ecx, edi; this
0x140006ebc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006ec1  jmp     short loc_140006ECA
0x140006ec3  mov     ecx, edi; this
0x140006ec5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006eca  mov     ebp, eax
0x140006ecc  mov     [rbx], r15d
0x140006ecf  mov     eax, [rsp+78h+arg_70]
0x140006ed6  mov     [rbx+4], eax
0x140006ed9  cmp     dword ptr [r14+8], 1
0x140006ede  jnz     short loc_140006EE6
0x140006ee0  or      eax, 8
0x140006ee3  mov     [rbx+4], eax
0x140006ee6  mov     eax, 1
0x140006eeb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006ef3  inc     eax
0x140006ef5  mov     [rbx+10h], eax
0x140006ef8  mov     rax, [rsp+78h+arg_40]
0x140006f00  xor     edi, edi
0x140006f02  test    rax, rax
0x140006f05  jz      short loc_140006F0C
0x140006f07  cmp     [rax], di
0x140006f0a  jnz     short loc_140006F0F
0x140006f0c  mov     rax, rdi
0x140006f0f  mov     [rbx+18h], rax
0x140006f13  call    cs:__imp_GetCurrentThreadId
0x140006f19  mov     [rbx+20h], eax
0x140006f1c  mov     [rbx+38h], r13
0x140006f20  mov     eax, [rsp+78h+arg_8]
0x140006f27  mov     [rbx+40h], eax
0x140006f2a  mov     [rbx+44h], ebp
0x140006f2d  mov     rax, [rsp+78h+arg_20]
0x140006f35  mov     [rbx+28h], rax
0x140006f39  mov     [rbx+30h], r12
0x140006f3d  mov     rax, [rsp+78h+arg_28]
0x140006f45  mov     [rbx+88h], rax
0x140006f4c  mov     rax, [rsp+78h+arg_0]
0x140006f54  mov     [rbx+90h], rax
0x140006f5b  mov     [rbx+48h], rdi
0x140006f5f  xorps   xmm0, xmm0
0x140006f62  xor     eax, eax
0x140006f64  movups  xmmword ptr [rbx+68h], xmm0
0x140006f68  mov     [rbx+78h], rax
0x140006f6c  movups  xmmword ptr [rbx+50h], xmm0
0x140006f70  mov     [rbx+60h], rax
0x140006f74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006f7b  test    rax, rax
0x140006f7e  jz      short loc_140006F87
0x140006f80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f85  jmp     short loc_140006F8A
0x140006f87  mov     rax, rdi
0x140006f8a  mov     [rbx+80h], rax
0x140006f91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006f98  test    rax, rax
0x140006f9b  jz      short loc_140006FA5
0x140006f9d  mov     rcx, rbx
0x140006fa0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fa5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006fac  test    rax, rax
0x140006faf  jz      short loc_140006FC7
0x140006fb1  mov     r8d, 400h
0x140006fb7  mov     rdx, [rsp+78h+arg_60]
0x140006fbf  mov     rcx, rbx
0x140006fc2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fc7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006fce  test    rax, rax
0x140006fd1  jz      short loc_140006FDB
0x140006fd3  mov     rcx, rbx
0x140006fd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006fdb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006fe2  test    rax, rax
0x140006fe5  jz      short loc_140006FF5
0x140006fe7  test    byte ptr [rbx+4], 2
0x140006feb  jnz     short loc_140006FF5
0x140006fed  mov     rcx, rbx
0x140006ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ff5  cmp     [rbx+8], edi
0x140006ff8  jl      short loc_140007014
0x140006ffa  cmp     r15d, 3
0x140006ffe  jnz     loc_1400070E3
0x140007004  mov     ecx, 8000FFFFh; this
0x140007009  mov     [rbx+8], ecx
0x14000700c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007011  mov     [rbx+0Ch], eax
0x140007014  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000701b  jnz     short loc_14000703C
0x14000701d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007024  test    rax, rax
0x140007027  jz      short loc_140007032
0x140007029  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000702e  test    al, al
0x140007030  jmp     short loc_14000703A
0x140007032  call    cs:__imp_IsDebuggerPresent
0x140007038  test    eax, eax
0x14000703a  jz      short loc_140007042
0x14000703c  test    byte ptr [rbx+4], 2
0x140007040  jz      short loc_140007066
0x140007042  mov     rax, cs:g_pfnResultLoggingCallback
0x140007049  test    rax, rax
0x14000704c  jz      short loc_1400070AA
0x14000704e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007055  jnz     short loc_1400070AA
0x140007057  xor     r8d, r8d
0x14000705a  xor     edx, edx
0x14000705c  mov     rcx, rbx
0x14000705f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007064  jmp     short loc_1400070AA
0x140007066  mov     ebp, 800h
0x14000706b  mov     rax, cs:g_pfnResultLoggingCallback
0x140007072  test    rax, rax
0x140007075  jz      short loc_14000708E
0x140007077  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000707e  jnz     short loc_14000708E
0x140007080  mov     r8d, ebp
0x140007083  mov     rdx, rsi
0x140007086  mov     rcx, rbx
0x140007089  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000708e  cmp     [rsi], di
0x140007091  jnz     short loc_1400070A1
0x140007093  mov     r8, rbx; unsigned __int64
0x140007096  mov     rdx, rbp; unsigned __int16 *
0x140007099  mov     rcx, rsi; this
0x14000709c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400070a1  mov     rcx, rsi; lpOutputString
0x1400070a4  call    cs:__imp_OutputDebugStringW
0x1400070aa  test    byte ptr [rbx+4], 4
0x1400070ae  jnz     short loc_1400070B9
0x1400070b0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400070b7  jz      short loc_1400070CB
0x1400070b9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400070c0  test    rax, rax
0x1400070c3  jz      short loc_1400070CB
0x1400070c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070ca  nop
0x1400070cb  mov     rbx, [rsp+78h+arg_10]
0x1400070d3  add     rsp, 40h
0x1400070d7  pop     r15
0x1400070d9  pop     r14
0x1400070db  pop     r13
0x1400070dd  pop     r12
0x1400070df  pop     rdi
0x1400070e0  pop     rsi
0x1400070e1  pop     rbp
0x1400070e2  retn
0x1400070e3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
