# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013e58`
- end: `0x180014150`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180011a04`

## callees

- `0x180011440`
- `0x180013414`
- `0x180013bac`
- `0x180013e58`
- `0x1800147a0`
- `0x1800147c0`
- `0x1800148e8`
- `0x180014904`
- `0x1800165b8`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f7b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180013f7b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001409a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001409a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001410c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001410c`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
0x180013e58  mov     [rsp+arg_10], rbx
0x180013e5d  mov     [rsp+arg_8], edx
0x180013e61  mov     [rsp+arg_0], rcx
0x180013e66  push    rbp
0x180013e67  push    rsi
0x180013e68  push    rdi
0x180013e69  push    r12
0x180013e6b  push    r13
0x180013e6d  push    r14
0x180013e6f  push    r15
0x180013e71  sub     rsp, 40h
0x180013e75  mov     r14, [rsp+78h+arg_38]
0x180013e7d  xor     eax, eax
0x180013e7f  mov     rbx, [rsp+78h+arg_78]
0x180013e87  xor     ebp, ebp
0x180013e89  mov     r15d, [rsp+78h+arg_30]
0x180013e91  mov     r10, rcx
0x180013e94  mov     rsi, [rsp+78h+lpOutputString]
0x180013e9c  mov     r12, r9
0x180013e9f  mov     r13, r8
0x180013ea2  mov     ecx, r15d
0x180013ea5  mov     [rsi], ax
0x180013ea8  mov     rax, [rsp+78h+arg_60]
0x180013eb0  mov     byte ptr [rax], 0
0x180013eb3  mov     edi, [r14]
0x180013eb6  mov     [rbx+8], edi
0x180013eb9  mov     eax, [r14+4]
0x180013ebd  mov     [rbx+0Ch], eax
0x180013ec0  test    r15d, r15d
0x180013ec3  jz      short loc_180013F2B
0x180013ec5  sub     ecx, 1
0x180013ec8  jz      short loc_180013F22
0x180013eca  sub     ecx, 1
0x180013ecd  jz      short loc_180013EDD
0x180013ecf  cmp     ecx, 1
0x180013ed2  jnz     short loc_180013F34
0x180013ed4  mov     ecx, edi; this
0x180013ed6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180013edb  jmp     short loc_180013F32
0x180013edd  test    edi, edi
0x180013edf  js      short loc_180013F19
0x180013ee1  mov     rax, [rsp+78h+arg_28]
0x180013ee9  mov     edi, 8007029Ch
0x180013eee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180013ef2  mov     rcx, r10; int
0x180013ef5  mov     [rsp+78h+var_50], rax; __int64
0x180013efa  mov     rax, [rsp+78h+arg_20]
0x180013f02  mov     [rsp+78h+var_58], rax; __int64
0x180013f07  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180013f0c  mov     ecx, edi; this
0x180013f0e  mov     [rbx+8], edi
0x180013f11  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013f16  mov     [rbx+0Ch], eax
0x180013f19  mov     ecx, edi; this
0x180013f1b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013f20  jmp     short loc_180013F32
0x180013f22  mov     ecx, edi; this
0x180013f24  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013f29  jmp     short loc_180013F32
0x180013f2b  mov     ecx, edi; this
0x180013f2d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013f32  mov     ebp, eax
0x180013f34  mov     eax, [rsp+78h+arg_70]
0x180013f3b  mov     [rbx+4], eax
0x180013f3e  mov     [rbx], r15d
0x180013f41  cmp     dword ptr [r14+8], 1
0x180013f46  jnz     short loc_180013F4E
0x180013f48  or      eax, 8
0x180013f4b  mov     [rbx+4], eax
0x180013f4e  mov     eax, 1
0x180013f53  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180013f5b  inc     eax
0x180013f5d  xor     edi, edi
0x180013f5f  mov     [rbx+10h], eax
0x180013f62  mov     rax, [rsp+78h+arg_40]
0x180013f6a  test    rax, rax
0x180013f6d  jz      short loc_180013F74
0x180013f6f  cmp     [rax], di
0x180013f72  jnz     short loc_180013F77
0x180013f74  mov     rax, rdi
0x180013f77  mov     [rbx+18h], rax
0x180013f7b  call    cs:__imp_GetCurrentThreadId
0x180013f81  mov     [rbx+38h], r13
0x180013f85  xorps   xmm0, xmm0
0x180013f88  mov     [rbx+20h], eax
0x180013f8b  mov     eax, [rsp+78h+arg_8]
0x180013f92  mov     [rbx+40h], eax
0x180013f95  mov     rax, [rsp+78h+arg_20]
0x180013f9d  mov     [rbx+28h], rax
0x180013fa1  mov     rax, [rsp+78h+arg_28]
0x180013fa9  mov     [rbx+88h], rax
0x180013fb0  mov     rax, [rsp+78h+arg_0]
0x180013fb8  mov     [rbx+90h], rax
0x180013fbf  xor     eax, eax
0x180013fc1  mov     [rbx+44h], ebp
0x180013fc4  mov     [rbx+30h], r12
0x180013fc8  mov     [rbx+48h], rdi
0x180013fcc  movups  xmmword ptr [rbx+68h], xmm0
0x180013fd0  mov     [rbx+78h], rax
0x180013fd4  movups  xmmword ptr [rbx+50h], xmm0
0x180013fd8  mov     [rbx+60h], rax
0x180013fdc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013fe3  test    rax, rax
0x180013fe6  jz      short loc_180013FEF
0x180013fe8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013fed  jmp     short loc_180013FF2
0x180013fef  mov     rax, rdi
0x180013ff2  mov     [rbx+80h], rax
0x180013ff9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014000  test    rax, rax
0x180014003  jz      short loc_18001400D
0x180014005  mov     rcx, rbx
0x180014008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001400d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180014014  test    rax, rax
0x180014017  jz      short loc_18001402F
0x180014019  mov     rdx, [rsp+78h+arg_60]
0x180014021  mov     r8d, 400h
0x180014027  mov     rcx, rbx
0x18001402a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001402f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180014036  test    rax, rax
0x180014039  jz      short loc_180014043
0x18001403b  mov     rcx, rbx
0x18001403e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014043  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001404a  test    rax, rax
0x18001404d  jz      short loc_18001405D
0x18001404f  test    byte ptr [rbx+4], 2
0x180014053  jnz     short loc_18001405D
0x180014055  mov     rcx, rbx
0x180014058  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001405d  cmp     [rbx+8], edi
0x180014060  jl      short loc_18001407C
0x180014062  cmp     r15d, 3
0x180014066  jnz     loc_18001414A
0x18001406c  mov     ecx, 8000FFFFh; this
0x180014071  mov     [rbx+8], ecx
0x180014074  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180014079  mov     [rbx+0Ch], eax
0x18001407c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180014083  jnz     short loc_1800140A4
0x180014085  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001408c  test    rax, rax
0x18001408f  jz      short loc_18001409A
0x180014091  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014096  test    al, al
0x180014098  jmp     short loc_1800140A2
0x18001409a  call    cs:__imp_IsDebuggerPresent
0x1800140a0  test    eax, eax
0x1800140a2  jz      short loc_1800140AA
0x1800140a4  test    byte ptr [rbx+4], 2
0x1800140a8  jz      short loc_1800140CE
0x1800140aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800140b1  test    rax, rax
0x1800140b4  jz      short loc_180014112
0x1800140b6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800140bd  jnz     short loc_180014112
0x1800140bf  xor     r8d, r8d
0x1800140c2  xor     edx, edx
0x1800140c4  mov     rcx, rbx
0x1800140c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140cc  jmp     short loc_180014112
0x1800140ce  mov     rax, cs:g_pfnResultLoggingCallback
0x1800140d5  mov     ebp, 800h
0x1800140da  test    rax, rax
0x1800140dd  jz      short loc_1800140F6
0x1800140df  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800140e6  jnz     short loc_1800140F6
0x1800140e8  mov     r8d, ebp
0x1800140eb  mov     rdx, rsi
0x1800140ee  mov     rcx, rbx
0x1800140f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140f6  cmp     [rsi], di
0x1800140f9  jnz     short loc_180014109
0x1800140fb  mov     r8, rbx; unsigned __int64
0x1800140fe  mov     rdx, rbp; unsigned __int16 *
0x180014101  mov     rcx, rsi; this
0x180014104  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180014109  mov     rcx, rsi; lpOutputString
0x18001410c  call    cs:__imp_OutputDebugStringW
0x180014112  test    byte ptr [rbx+4], 4
0x180014116  jnz     short loc_180014121
0x180014118  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001411f  jz      short loc_180014132
0x180014121  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180014128  test    rax, rax
0x18001412b  jz      short loc_180014132
0x18001412d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014132  mov     rbx, [rsp+78h+arg_10]
0x18001413a  add     rsp, 40h
0x18001413e  pop     r15
0x180014140  pop     r14
0x180014142  pop     r13
0x180014144  pop     r12
0x180014146  pop     rdi
0x180014147  pop     rsi
0x180014148  pop     rbp
0x180014149  retn
0x18001414a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
