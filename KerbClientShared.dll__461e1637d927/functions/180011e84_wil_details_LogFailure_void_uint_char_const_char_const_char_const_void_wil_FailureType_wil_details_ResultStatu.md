# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011e84`
- end: `0x18001217c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000fd38`
- `0x18001007c`

## callees

- `0x18000fc78`
- `0x180011174`
- `0x18001197c`
- `0x180011e84`
- `0x180012ae8`
- `0x180012b10`
- `0x180012bcc`
- `0x180012be8`
- `0x1800141d0`
- `0x180029010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011fa7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011fa7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012138`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012138`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800120c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800120c6`

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
        WCHAR *lpOutputString,
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
  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
    OutputDebugStringW(lpOutputString);
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
0x180011e84  mov     [rsp+arg_10], rbx
0x180011e89  mov     [rsp+arg_8], edx
0x180011e8d  mov     [rsp+arg_0], rcx
0x180011e92  push    rbp
0x180011e93  push    rsi
0x180011e94  push    rdi
0x180011e95  push    r12
0x180011e97  push    r13
0x180011e99  push    r14
0x180011e9b  push    r15
0x180011e9d  sub     rsp, 40h
0x180011ea1  mov     r14, [rsp+78h+arg_38]
0x180011ea9  xor     eax, eax
0x180011eab  mov     rbx, [rsp+78h+arg_78]
0x180011eb3  xor     ebp, ebp
0x180011eb5  mov     r15d, [rsp+78h+arg_30]
0x180011ebd  mov     r10, rcx
0x180011ec0  mov     rsi, [rsp+78h+lpOutputString]
0x180011ec8  mov     r12, r9
0x180011ecb  mov     r13, r8
0x180011ece  mov     ecx, r15d
0x180011ed1  mov     [rsi], ax
0x180011ed4  mov     rax, [rsp+78h+arg_60]
0x180011edc  mov     byte ptr [rax], 0
0x180011edf  mov     edi, [r14]
0x180011ee2  mov     [rbx+8], edi
0x180011ee5  mov     eax, [r14+4]
0x180011ee9  mov     [rbx+0Ch], eax
0x180011eec  test    r15d, r15d
0x180011eef  jz      short loc_180011F57
0x180011ef1  sub     ecx, 1
0x180011ef4  jz      short loc_180011F4E
0x180011ef6  sub     ecx, 1
0x180011ef9  jz      short loc_180011F09
0x180011efb  cmp     ecx, 1
0x180011efe  jnz     short loc_180011F60
0x180011f00  mov     ecx, edi; this
0x180011f02  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011f07  jmp     short loc_180011F5E
0x180011f09  test    edi, edi
0x180011f0b  js      short loc_180011F45
0x180011f0d  mov     rax, [rsp+78h+arg_28]
0x180011f15  mov     edi, 8007029Ch
0x180011f1a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011f1e  mov     rcx, r10; int
0x180011f21  mov     [rsp+78h+var_50], rax; __int64
0x180011f26  mov     rax, [rsp+78h+arg_20]
0x180011f2e  mov     [rsp+78h+var_58], rax; __int64
0x180011f33  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011f38  mov     ecx, edi; this
0x180011f3a  mov     [rbx+8], edi
0x180011f3d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011f42  mov     [rbx+0Ch], eax
0x180011f45  mov     ecx, edi; this
0x180011f47  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011f4c  jmp     short loc_180011F5E
0x180011f4e  mov     ecx, edi; this
0x180011f50  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011f55  jmp     short loc_180011F5E
0x180011f57  mov     ecx, edi; this
0x180011f59  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011f5e  mov     ebp, eax
0x180011f60  mov     eax, [rsp+78h+arg_70]
0x180011f67  mov     [rbx+4], eax
0x180011f6a  mov     [rbx], r15d
0x180011f6d  cmp     dword ptr [r14+8], 1
0x180011f72  jnz     short loc_180011F7A
0x180011f74  or      eax, 8
0x180011f77  mov     [rbx+4], eax
0x180011f7a  mov     eax, 1
0x180011f7f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011f87  inc     eax
0x180011f89  xor     edi, edi
0x180011f8b  mov     [rbx+10h], eax
0x180011f8e  mov     rax, [rsp+78h+arg_40]
0x180011f96  test    rax, rax
0x180011f99  jz      short loc_180011FA0
0x180011f9b  cmp     [rax], di
0x180011f9e  jnz     short loc_180011FA3
0x180011fa0  mov     rax, rdi
0x180011fa3  mov     [rbx+18h], rax
0x180011fa7  call    cs:__imp_GetCurrentThreadId
0x180011fad  mov     [rbx+38h], r13
0x180011fb1  xorps   xmm0, xmm0
0x180011fb4  mov     [rbx+20h], eax
0x180011fb7  mov     eax, [rsp+78h+arg_8]
0x180011fbe  mov     [rbx+40h], eax
0x180011fc1  mov     rax, [rsp+78h+arg_20]
0x180011fc9  mov     [rbx+28h], rax
0x180011fcd  mov     rax, [rsp+78h+arg_28]
0x180011fd5  mov     [rbx+88h], rax
0x180011fdc  mov     rax, [rsp+78h+arg_0]
0x180011fe4  mov     [rbx+90h], rax
0x180011feb  xor     eax, eax
0x180011fed  mov     [rbx+44h], ebp
0x180011ff0  mov     [rbx+30h], r12
0x180011ff4  mov     [rbx+48h], rdi
0x180011ff8  movups  xmmword ptr [rbx+68h], xmm0
0x180011ffc  mov     [rbx+78h], rax
0x180012000  movups  xmmword ptr [rbx+50h], xmm0
0x180012004  mov     [rbx+60h], rax
0x180012008  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001200f  test    rax, rax
0x180012012  jz      short loc_18001201B
0x180012014  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012019  jmp     short loc_18001201E
0x18001201b  mov     rax, rdi
0x18001201e  mov     [rbx+80h], rax
0x180012025  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001202c  test    rax, rax
0x18001202f  jz      short loc_180012039
0x180012031  mov     rcx, rbx
0x180012034  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012039  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012040  test    rax, rax
0x180012043  jz      short loc_18001205B
0x180012045  mov     rdx, [rsp+78h+arg_60]
0x18001204d  mov     r8d, 400h
0x180012053  mov     rcx, rbx
0x180012056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001205b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012062  test    rax, rax
0x180012065  jz      short loc_18001206F
0x180012067  mov     rcx, rbx
0x18001206a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001206f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012076  test    rax, rax
0x180012079  jz      short loc_180012089
0x18001207b  test    byte ptr [rbx+4], 2
0x18001207f  jnz     short loc_180012089
0x180012081  mov     rcx, rbx
0x180012084  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012089  cmp     [rbx+8], edi
0x18001208c  jl      short loc_1800120A8
0x18001208e  cmp     r15d, 3
0x180012092  jnz     loc_180012176
0x180012098  mov     ecx, 8000FFFFh; this
0x18001209d  mov     [rbx+8], ecx
0x1800120a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800120a5  mov     [rbx+0Ch], eax
0x1800120a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800120af  jnz     short loc_1800120D0
0x1800120b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800120b8  test    rax, rax
0x1800120bb  jz      short loc_1800120C6
0x1800120bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120c2  test    al, al
0x1800120c4  jmp     short loc_1800120CE
0x1800120c6  call    cs:__imp_IsDebuggerPresent
0x1800120cc  test    eax, eax
0x1800120ce  jz      short loc_1800120D6
0x1800120d0  test    byte ptr [rbx+4], 2
0x1800120d4  jz      short loc_1800120FA
0x1800120d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800120dd  test    rax, rax
0x1800120e0  jz      short loc_18001213E
0x1800120e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800120e9  jnz     short loc_18001213E
0x1800120eb  xor     r8d, r8d
0x1800120ee  xor     edx, edx
0x1800120f0  mov     rcx, rbx
0x1800120f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800120f8  jmp     short loc_18001213E
0x1800120fa  mov     rax, cs:g_pfnResultLoggingCallback
0x180012101  mov     ebp, 800h
0x180012106  test    rax, rax
0x180012109  jz      short loc_180012122
0x18001210b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012112  jnz     short loc_180012122
0x180012114  mov     r8d, ebp
0x180012117  mov     rdx, rsi
0x18001211a  mov     rcx, rbx
0x18001211d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012122  cmp     [rsi], di
0x180012125  jnz     short loc_180012135
0x180012127  mov     r8, rbx; unsigned __int64
0x18001212a  mov     rdx, rbp; unsigned __int16 *
0x18001212d  mov     rcx, rsi; pszDest
0x180012130  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012135  mov     rcx, rsi; lpOutputString
0x180012138  call    cs:__imp_OutputDebugStringW
0x18001213e  test    byte ptr [rbx+4], 4
0x180012142  jnz     short loc_18001214D
0x180012144  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001214b  jz      short loc_18001215E
0x18001214d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012154  test    rax, rax
0x180012157  jz      short loc_18001215E
0x180012159  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001215e  mov     rbx, [rsp+78h+arg_10]
0x180012166  add     rsp, 40h
0x18001216a  pop     r15
0x18001216c  pop     r14
0x18001216e  pop     r13
0x180012170  pop     r12
0x180012172  pop     rdi
0x180012173  pop     rsi
0x180012174  pop     rbp
0x180012175  retn
0x180012176  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
