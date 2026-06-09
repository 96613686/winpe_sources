# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000ee9c`
- end: `0x18000f194`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d8f4`
- `0x18000dc38`

## callees

- `0x18000d834`
- `0x18000e544`
- `0x18000ecd8`
- `0x18000ee9c`
- `0x18000f334`
- `0x18000f350`
- `0x18000f364`
- `0x18000f380`
- `0x18000fc48`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000efbf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f0de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000f0de`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f150`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000f150`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x18000ee9c  mov     [rsp+arg_10], rbx
0x18000eea1  mov     [rsp+arg_8], edx
0x18000eea5  mov     [rsp+arg_0], rcx
0x18000eeaa  push    rbp
0x18000eeab  push    rsi
0x18000eeac  push    rdi
0x18000eead  push    r12
0x18000eeaf  push    r13
0x18000eeb1  push    r14
0x18000eeb3  push    r15
0x18000eeb5  sub     rsp, 40h
0x18000eeb9  mov     r14, [rsp+78h+arg_38]
0x18000eec1  xor     eax, eax
0x18000eec3  mov     rbx, [rsp+78h+arg_78]
0x18000eecb  xor     ebp, ebp
0x18000eecd  mov     r15d, [rsp+78h+arg_30]
0x18000eed5  mov     r10, rcx
0x18000eed8  mov     rsi, [rsp+78h+lpOutputString]
0x18000eee0  mov     r12, r9
0x18000eee3  mov     r13, r8
0x18000eee6  mov     ecx, r15d
0x18000eee9  mov     [rsi], ax
0x18000eeec  mov     rax, [rsp+78h+arg_60]
0x18000eef4  mov     byte ptr [rax], 0
0x18000eef7  mov     edi, [r14]
0x18000eefa  mov     [rbx+8], edi
0x18000eefd  mov     eax, [r14+4]
0x18000ef01  mov     [rbx+0Ch], eax
0x18000ef04  test    r15d, r15d
0x18000ef07  jz      short loc_18000EF6F
0x18000ef09  sub     ecx, 1
0x18000ef0c  jz      short loc_18000EF66
0x18000ef0e  sub     ecx, 1
0x18000ef11  jz      short loc_18000EF21
0x18000ef13  cmp     ecx, 1
0x18000ef16  jnz     short loc_18000EF78
0x18000ef18  mov     ecx, edi; this
0x18000ef1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ef1f  jmp     short loc_18000EF76
0x18000ef21  test    edi, edi
0x18000ef23  js      short loc_18000EF5D
0x18000ef25  mov     rax, [rsp+78h+arg_28]
0x18000ef2d  mov     edi, 8007029Ch
0x18000ef32  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ef36  mov     rcx, r10; int
0x18000ef39  mov     [rsp+78h+var_50], rax; __int64
0x18000ef3e  mov     rax, [rsp+78h+arg_20]
0x18000ef46  mov     [rsp+78h+var_58], rax; __int64
0x18000ef4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ef50  mov     ecx, edi; this
0x18000ef52  mov     [rbx+8], edi
0x18000ef55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ef5a  mov     [rbx+0Ch], eax
0x18000ef5d  mov     ecx, edi; this
0x18000ef5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ef64  jmp     short loc_18000EF76
0x18000ef66  mov     ecx, edi; this
0x18000ef68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ef6d  jmp     short loc_18000EF76
0x18000ef6f  mov     ecx, edi; this
0x18000ef71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ef76  mov     ebp, eax
0x18000ef78  mov     eax, [rsp+78h+arg_70]
0x18000ef7f  mov     [rbx+4], eax
0x18000ef82  mov     [rbx], r15d
0x18000ef85  cmp     dword ptr [r14+8], 1
0x18000ef8a  jnz     short loc_18000EF92
0x18000ef8c  or      eax, 8
0x18000ef8f  mov     [rbx+4], eax
0x18000ef92  mov     eax, 1
0x18000ef97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ef9f  inc     eax
0x18000efa1  xor     edi, edi
0x18000efa3  mov     [rbx+10h], eax
0x18000efa6  mov     rax, [rsp+78h+arg_40]
0x18000efae  test    rax, rax
0x18000efb1  jz      short loc_18000EFB8
0x18000efb3  cmp     [rax], di
0x18000efb6  jnz     short loc_18000EFBB
0x18000efb8  mov     rax, rdi
0x18000efbb  mov     [rbx+18h], rax
0x18000efbf  call    cs:__imp_GetCurrentThreadId
0x18000efc5  mov     [rbx+38h], r13
0x18000efc9  xorps   xmm0, xmm0
0x18000efcc  mov     [rbx+20h], eax
0x18000efcf  mov     eax, [rsp+78h+arg_8]
0x18000efd6  mov     [rbx+40h], eax
0x18000efd9  mov     rax, [rsp+78h+arg_20]
0x18000efe1  mov     [rbx+28h], rax
0x18000efe5  mov     rax, [rsp+78h+arg_28]
0x18000efed  mov     [rbx+88h], rax
0x18000eff4  mov     rax, [rsp+78h+arg_0]
0x18000effc  mov     [rbx+90h], rax
0x18000f003  xor     eax, eax
0x18000f005  mov     [rbx+44h], ebp
0x18000f008  mov     [rbx+30h], r12
0x18000f00c  mov     [rbx+48h], rdi
0x18000f010  movups  xmmword ptr [rbx+68h], xmm0
0x18000f014  mov     [rbx+78h], rax
0x18000f018  movups  xmmword ptr [rbx+50h], xmm0
0x18000f01c  mov     [rbx+60h], rax
0x18000f020  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000f027  test    rax, rax
0x18000f02a  jz      short loc_18000F033
0x18000f02c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f031  jmp     short loc_18000F036
0x18000f033  mov     rax, rdi
0x18000f036  mov     [rbx+80h], rax
0x18000f03d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000f044  test    rax, rax
0x18000f047  jz      short loc_18000F051
0x18000f049  mov     rcx, rbx
0x18000f04c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f051  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000f058  test    rax, rax
0x18000f05b  jz      short loc_18000F073
0x18000f05d  mov     rdx, [rsp+78h+arg_60]
0x18000f065  mov     r8d, 400h
0x18000f06b  mov     rcx, rbx
0x18000f06e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f073  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f07a  test    rax, rax
0x18000f07d  jz      short loc_18000F087
0x18000f07f  mov     rcx, rbx
0x18000f082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f087  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000f08e  test    rax, rax
0x18000f091  jz      short loc_18000F0A1
0x18000f093  test    byte ptr [rbx+4], 2
0x18000f097  jnz     short loc_18000F0A1
0x18000f099  mov     rcx, rbx
0x18000f09c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0a1  cmp     [rbx+8], edi
0x18000f0a4  jl      short loc_18000F0C0
0x18000f0a6  cmp     r15d, 3
0x18000f0aa  jnz     loc_18000F18E
0x18000f0b0  mov     ecx, 8000FFFFh; this
0x18000f0b5  mov     [rbx+8], ecx
0x18000f0b8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000f0bd  mov     [rbx+0Ch], eax
0x18000f0c0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000f0c7  jnz     short loc_18000F0E8
0x18000f0c9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000f0d0  test    rax, rax
0x18000f0d3  jz      short loc_18000F0DE
0x18000f0d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f0da  test    al, al
0x18000f0dc  jmp     short loc_18000F0E6
0x18000f0de  call    cs:__imp_IsDebuggerPresent
0x18000f0e4  test    eax, eax
0x18000f0e6  jz      short loc_18000F0EE
0x18000f0e8  test    byte ptr [rbx+4], 2
0x18000f0ec  jz      short loc_18000F112
0x18000f0ee  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f0f5  test    rax, rax
0x18000f0f8  jz      short loc_18000F156
0x18000f0fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f101  jnz     short loc_18000F156
0x18000f103  xor     r8d, r8d
0x18000f106  xor     edx, edx
0x18000f108  mov     rcx, rbx
0x18000f10b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f110  jmp     short loc_18000F156
0x18000f112  mov     rax, cs:g_pfnResultLoggingCallback
0x18000f119  mov     ebp, 800h
0x18000f11e  test    rax, rax
0x18000f121  jz      short loc_18000F13A
0x18000f123  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000f12a  jnz     short loc_18000F13A
0x18000f12c  mov     r8d, ebp
0x18000f12f  mov     rdx, rsi
0x18000f132  mov     rcx, rbx
0x18000f135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f13a  cmp     [rsi], di
0x18000f13d  jnz     short loc_18000F14D
0x18000f13f  mov     r8, rbx; unsigned __int64
0x18000f142  mov     rdx, rbp; unsigned __int16 *
0x18000f145  mov     rcx, rsi; this
0x18000f148  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000f14d  mov     rcx, rsi; lpOutputString
0x18000f150  call    cs:__imp_OutputDebugStringW
0x18000f156  test    byte ptr [rbx+4], 4
0x18000f15a  jnz     short loc_18000F165
0x18000f15c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000f163  jz      short loc_18000F176
0x18000f165  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000f16c  test    rax, rax
0x18000f16f  jz      short loc_18000F176
0x18000f171  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f176  mov     rbx, [rsp+78h+arg_10]
0x18000f17e  add     rsp, 40h
0x18000f182  pop     r15
0x18000f184  pop     r14
0x18000f186  pop     r13
0x18000f188  pop     r12
0x18000f18a  pop     rdi
0x18000f18b  pop     rsi
0x18000f18c  pop     rbp
0x18000f18d  retn
0x18000f18e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
