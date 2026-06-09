# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006048`
- end: `0x180006341`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000464c`
- `0x180004990`

## callees

- `0x18000458c`
- `0x180005630`
- `0x180005e58`
- `0x180006048`
- `0x180006690`
- `0x1800066b0`
- `0x1800066c4`
- `0x1800066e0`
- `0x1800072b4`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000616b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000616b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800062fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800062fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000628a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000628a`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x180006048  mov     [rsp+arg_10], rbx
0x18000604d  mov     [rsp+arg_8], edx
0x180006051  mov     [rsp+arg_0], rcx
0x180006056  push    rbp
0x180006057  push    rsi
0x180006058  push    rdi
0x180006059  push    r12
0x18000605b  push    r13
0x18000605d  push    r14
0x18000605f  push    r15
0x180006061  sub     rsp, 40h
0x180006065  mov     r12, r9
0x180006068  mov     r13, r8
0x18000606b  mov     r10, rcx
0x18000606e  xor     eax, eax
0x180006070  mov     rsi, [rsp+78h+lpOutputString]
0x180006078  mov     [rsi], ax
0x18000607b  mov     rax, [rsp+78h+arg_60]
0x180006083  mov     byte ptr [rax], 0
0x180006086  mov     r14, [rsp+78h+arg_38]
0x18000608e  mov     edi, [r14]
0x180006091  mov     rbx, [rsp+78h+arg_78]
0x180006099  mov     [rbx+8], edi
0x18000609c  mov     eax, [r14+4]
0x1800060a0  mov     [rbx+0Ch], eax
0x1800060a3  xor     ebp, ebp
0x1800060a5  mov     r15d, [rsp+78h+arg_30]
0x1800060ad  mov     ecx, r15d
0x1800060b0  test    r15d, r15d
0x1800060b3  jz      short loc_18000611B
0x1800060b5  sub     ecx, 1
0x1800060b8  jz      short loc_180006112
0x1800060ba  sub     ecx, 1
0x1800060bd  jz      short loc_1800060CD
0x1800060bf  cmp     ecx, 1
0x1800060c2  jnz     short loc_180006124
0x1800060c4  mov     ecx, edi; this
0x1800060c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800060cb  jmp     short loc_180006122
0x1800060cd  test    edi, edi
0x1800060cf  js      short loc_180006109
0x1800060d1  mov     edi, 8007029Ch
0x1800060d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800060da  mov     rax, [rsp+78h+arg_28]
0x1800060e2  mov     [rsp+78h+var_50], rax; __int64
0x1800060e7  mov     rax, [rsp+78h+arg_20]
0x1800060ef  mov     [rsp+78h+var_58], rax; __int64
0x1800060f4  mov     rcx, r10; int
0x1800060f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800060fc  mov     [rbx+8], edi
0x1800060ff  mov     ecx, edi; this
0x180006101  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006106  mov     [rbx+0Ch], eax
0x180006109  mov     ecx, edi; this
0x18000610b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006110  jmp     short loc_180006122
0x180006112  mov     ecx, edi; this
0x180006114  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006119  jmp     short loc_180006122
0x18000611b  mov     ecx, edi; this
0x18000611d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006122  mov     ebp, eax
0x180006124  mov     [rbx], r15d
0x180006127  mov     eax, [rsp+78h+arg_70]
0x18000612e  mov     [rbx+4], eax
0x180006131  cmp     dword ptr [r14+8], 1
0x180006136  jnz     short loc_18000613E
0x180006138  or      eax, 8
0x18000613b  mov     [rbx+4], eax
0x18000613e  mov     eax, 1
0x180006143  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000614b  inc     eax
0x18000614d  mov     [rbx+10h], eax
0x180006150  mov     rax, [rsp+78h+arg_40]
0x180006158  xor     edi, edi
0x18000615a  test    rax, rax
0x18000615d  jz      short loc_180006164
0x18000615f  cmp     [rax], di
0x180006162  jnz     short loc_180006167
0x180006164  mov     rax, rdi
0x180006167  mov     [rbx+18h], rax
0x18000616b  call    cs:__imp_GetCurrentThreadId
0x180006171  mov     [rbx+20h], eax
0x180006174  mov     [rbx+38h], r13
0x180006178  mov     eax, [rsp+78h+arg_8]
0x18000617f  mov     [rbx+40h], eax
0x180006182  mov     [rbx+44h], ebp
0x180006185  mov     rax, [rsp+78h+arg_20]
0x18000618d  mov     [rbx+28h], rax
0x180006191  mov     [rbx+30h], r12
0x180006195  mov     rax, [rsp+78h+arg_28]
0x18000619d  mov     [rbx+88h], rax
0x1800061a4  mov     rax, [rsp+78h+arg_0]
0x1800061ac  mov     [rbx+90h], rax
0x1800061b3  mov     [rbx+48h], rdi
0x1800061b7  xorps   xmm0, xmm0
0x1800061ba  xor     eax, eax
0x1800061bc  movups  xmmword ptr [rbx+68h], xmm0
0x1800061c0  mov     [rbx+78h], rax
0x1800061c4  movups  xmmword ptr [rbx+50h], xmm0
0x1800061c8  mov     [rbx+60h], rax
0x1800061cc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800061d3  test    rax, rax
0x1800061d6  jz      short loc_1800061DF
0x1800061d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061dd  jmp     short loc_1800061E2
0x1800061df  mov     rax, rdi
0x1800061e2  mov     [rbx+80h], rax
0x1800061e9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800061f0  test    rax, rax
0x1800061f3  jz      short loc_1800061FD
0x1800061f5  mov     rcx, rbx
0x1800061f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061fd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006204  test    rax, rax
0x180006207  jz      short loc_18000621F
0x180006209  mov     r8d, 400h
0x18000620f  mov     rdx, [rsp+78h+arg_60]
0x180006217  mov     rcx, rbx
0x18000621a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000621f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006226  test    rax, rax
0x180006229  jz      short loc_180006233
0x18000622b  mov     rcx, rbx
0x18000622e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006233  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000623a  test    rax, rax
0x18000623d  jz      short loc_18000624D
0x18000623f  test    byte ptr [rbx+4], 2
0x180006243  jnz     short loc_18000624D
0x180006245  mov     rcx, rbx
0x180006248  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000624d  cmp     [rbx+8], edi
0x180006250  jl      short loc_18000626C
0x180006252  cmp     r15d, 3
0x180006256  jnz     loc_18000633B
0x18000625c  mov     ecx, 8000FFFFh; this
0x180006261  mov     [rbx+8], ecx
0x180006264  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006269  mov     [rbx+0Ch], eax
0x18000626c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006273  jnz     short loc_180006294
0x180006275  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000627c  test    rax, rax
0x18000627f  jz      short loc_18000628A
0x180006281  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006286  test    al, al
0x180006288  jmp     short loc_180006292
0x18000628a  call    cs:__imp_IsDebuggerPresent
0x180006290  test    eax, eax
0x180006292  jz      short loc_18000629A
0x180006294  test    byte ptr [rbx+4], 2
0x180006298  jz      short loc_1800062BE
0x18000629a  mov     rax, cs:g_pfnResultLoggingCallback
0x1800062a1  test    rax, rax
0x1800062a4  jz      short loc_180006302
0x1800062a6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800062ad  jnz     short loc_180006302
0x1800062af  xor     r8d, r8d
0x1800062b2  xor     edx, edx
0x1800062b4  mov     rcx, rbx
0x1800062b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062bc  jmp     short loc_180006302
0x1800062be  mov     ebp, 800h
0x1800062c3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800062ca  test    rax, rax
0x1800062cd  jz      short loc_1800062E6
0x1800062cf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800062d6  jnz     short loc_1800062E6
0x1800062d8  mov     r8d, ebp
0x1800062db  mov     rdx, rsi
0x1800062de  mov     rcx, rbx
0x1800062e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e6  cmp     [rsi], di
0x1800062e9  jnz     short loc_1800062F9
0x1800062eb  mov     r8, rbx; unsigned __int64
0x1800062ee  mov     rdx, rbp; unsigned __int16 *
0x1800062f1  mov     rcx, rsi; this
0x1800062f4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800062f9  mov     rcx, rsi; lpOutputString
0x1800062fc  call    cs:__imp_OutputDebugStringW
0x180006302  test    byte ptr [rbx+4], 4
0x180006306  jnz     short loc_180006311
0x180006308  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000630f  jz      short loc_180006323
0x180006311  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006318  test    rax, rax
0x18000631b  jz      short loc_180006323
0x18000631d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006322  nop
0x180006323  mov     rbx, [rsp+78h+arg_10]
0x18000632b  add     rsp, 40h
0x18000632f  pop     r15
0x180006331  pop     r14
0x180006333  pop     r13
0x180006335  pop     r12
0x180006337  pop     rdi
0x180006338  pop     rsi
0x180006339  pop     rbp
0x18000633a  retn
0x18000633b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
