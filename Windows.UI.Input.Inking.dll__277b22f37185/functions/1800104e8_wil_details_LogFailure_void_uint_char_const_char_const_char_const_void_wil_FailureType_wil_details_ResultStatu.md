# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800104e8`
- end: `0x1800107e1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a7d8`
- `0x18000ab44`
- `0x18005fdc8`

## callees

- `0x18000a710`
- `0x18000e9b4`
- `0x18000fe50`
- `0x1800104e8`
- `0x180012108`
- `0x180012130`
- `0x180012280`
- `0x18001229c`
- `0x180014a30`
- `0x1800fb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001060b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001060b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001072a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001072a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001079c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001079c`

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
0x1800104e8  mov     [rsp+arg_10], rbx
0x1800104ed  mov     [rsp+arg_8], edx
0x1800104f1  mov     [rsp+arg_0], rcx
0x1800104f6  push    rbp
0x1800104f7  push    rsi
0x1800104f8  push    rdi
0x1800104f9  push    r12
0x1800104fb  push    r13
0x1800104fd  push    r14
0x1800104ff  push    r15
0x180010501  sub     rsp, 40h
0x180010505  mov     r12, r9
0x180010508  mov     r13, r8
0x18001050b  mov     r10, rcx
0x18001050e  xor     eax, eax
0x180010510  mov     rsi, [rsp+78h+lpOutputString]
0x180010518  mov     [rsi], ax
0x18001051b  mov     rax, [rsp+78h+arg_60]
0x180010523  mov     byte ptr [rax], 0
0x180010526  mov     r14, [rsp+78h+arg_38]
0x18001052e  mov     edi, [r14]
0x180010531  mov     rbx, [rsp+78h+arg_78]
0x180010539  mov     [rbx+8], edi
0x18001053c  mov     eax, [r14+4]
0x180010540  mov     [rbx+0Ch], eax
0x180010543  xor     ebp, ebp
0x180010545  mov     r15d, [rsp+78h+arg_30]
0x18001054d  mov     ecx, r15d
0x180010550  test    r15d, r15d
0x180010553  jz      short loc_1800105BB
0x180010555  sub     ecx, 1
0x180010558  jz      short loc_1800105B2
0x18001055a  sub     ecx, 1
0x18001055d  jz      short loc_18001056D
0x18001055f  cmp     ecx, 1
0x180010562  jnz     short loc_1800105C4
0x180010564  mov     ecx, edi; this
0x180010566  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001056b  jmp     short loc_1800105C2
0x18001056d  test    edi, edi
0x18001056f  js      short loc_1800105A9
0x180010571  mov     edi, 8007029Ch
0x180010576  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001057a  mov     rax, [rsp+78h+arg_28]
0x180010582  mov     [rsp+78h+var_50], rax; __int64
0x180010587  mov     rax, [rsp+78h+arg_20]
0x18001058f  mov     [rsp+78h+var_58], rax; __int64
0x180010594  mov     rcx, r10; int
0x180010597  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001059c  mov     [rbx+8], edi
0x18001059f  mov     ecx, edi; this
0x1800105a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800105a6  mov     [rbx+0Ch], eax
0x1800105a9  mov     ecx, edi; this
0x1800105ab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800105b0  jmp     short loc_1800105C2
0x1800105b2  mov     ecx, edi; this
0x1800105b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800105b9  jmp     short loc_1800105C2
0x1800105bb  mov     ecx, edi; this
0x1800105bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800105c2  mov     ebp, eax
0x1800105c4  mov     [rbx], r15d
0x1800105c7  mov     eax, [rsp+78h+arg_70]
0x1800105ce  mov     [rbx+4], eax
0x1800105d1  cmp     dword ptr [r14+8], 1
0x1800105d6  jnz     short loc_1800105DE
0x1800105d8  or      eax, 8
0x1800105db  mov     [rbx+4], eax
0x1800105de  mov     eax, 1
0x1800105e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800105eb  inc     eax
0x1800105ed  mov     [rbx+10h], eax
0x1800105f0  mov     rax, [rsp+78h+arg_40]
0x1800105f8  xor     edi, edi
0x1800105fa  test    rax, rax
0x1800105fd  jz      short loc_180010604
0x1800105ff  cmp     [rax], di
0x180010602  jnz     short loc_180010607
0x180010604  mov     rax, rdi
0x180010607  mov     [rbx+18h], rax
0x18001060b  call    cs:__imp_GetCurrentThreadId
0x180010611  mov     [rbx+20h], eax
0x180010614  mov     [rbx+38h], r13
0x180010618  mov     eax, [rsp+78h+arg_8]
0x18001061f  mov     [rbx+40h], eax
0x180010622  mov     [rbx+44h], ebp
0x180010625  mov     rax, [rsp+78h+arg_20]
0x18001062d  mov     [rbx+28h], rax
0x180010631  mov     [rbx+30h], r12
0x180010635  mov     rax, [rsp+78h+arg_28]
0x18001063d  mov     [rbx+88h], rax
0x180010644  mov     rax, [rsp+78h+arg_0]
0x18001064c  mov     [rbx+90h], rax
0x180010653  mov     [rbx+48h], rdi
0x180010657  xorps   xmm0, xmm0
0x18001065a  xor     eax, eax
0x18001065c  movups  xmmword ptr [rbx+68h], xmm0
0x180010660  mov     [rbx+78h], rax
0x180010664  movups  xmmword ptr [rbx+50h], xmm0
0x180010668  mov     [rbx+60h], rax
0x18001066c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010673  test    rax, rax
0x180010676  jz      short loc_18001067F
0x180010678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001067d  jmp     short loc_180010682
0x18001067f  mov     rax, rdi
0x180010682  mov     [rbx+80h], rax
0x180010689  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010690  test    rax, rax
0x180010693  jz      short loc_18001069D
0x180010695  mov     rcx, rbx
0x180010698  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001069d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800106a4  test    rax, rax
0x1800106a7  jz      short loc_1800106BF
0x1800106a9  mov     r8d, 400h
0x1800106af  mov     rdx, [rsp+78h+arg_60]
0x1800106b7  mov     rcx, rbx
0x1800106ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800106c6  test    rax, rax
0x1800106c9  jz      short loc_1800106D3
0x1800106cb  mov     rcx, rbx
0x1800106ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800106da  test    rax, rax
0x1800106dd  jz      short loc_1800106ED
0x1800106df  test    byte ptr [rbx+4], 2
0x1800106e3  jnz     short loc_1800106ED
0x1800106e5  mov     rcx, rbx
0x1800106e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800106ed  cmp     [rbx+8], edi
0x1800106f0  jl      short loc_18001070C
0x1800106f2  cmp     r15d, 3
0x1800106f6  jnz     loc_1800107DB
0x1800106fc  mov     ecx, 8000FFFFh; this
0x180010701  mov     [rbx+8], ecx
0x180010704  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010709  mov     [rbx+0Ch], eax
0x18001070c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180010713  jnz     short loc_180010734
0x180010715  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001071c  test    rax, rax
0x18001071f  jz      short loc_18001072A
0x180010721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010726  test    al, al
0x180010728  jmp     short loc_180010732
0x18001072a  call    cs:__imp_IsDebuggerPresent
0x180010730  test    eax, eax
0x180010732  jz      short loc_18001073A
0x180010734  test    byte ptr [rbx+4], 2
0x180010738  jz      short loc_18001075E
0x18001073a  mov     rax, cs:g_pfnResultLoggingCallback
0x180010741  test    rax, rax
0x180010744  jz      short loc_1800107A2
0x180010746  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001074d  jnz     short loc_1800107A2
0x18001074f  xor     r8d, r8d
0x180010752  xor     edx, edx
0x180010754  mov     rcx, rbx
0x180010757  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001075c  jmp     short loc_1800107A2
0x18001075e  mov     ebp, 800h
0x180010763  mov     rax, cs:g_pfnResultLoggingCallback
0x18001076a  test    rax, rax
0x18001076d  jz      short loc_180010786
0x18001076f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010776  jnz     short loc_180010786
0x180010778  mov     r8d, ebp
0x18001077b  mov     rdx, rsi
0x18001077e  mov     rcx, rbx
0x180010781  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010786  cmp     [rsi], di
0x180010789  jnz     short loc_180010799
0x18001078b  mov     r8, rbx; unsigned __int64
0x18001078e  mov     rdx, rbp; unsigned __int16 *
0x180010791  mov     rcx, rsi; this
0x180010794  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010799  mov     rcx, rsi; lpOutputString
0x18001079c  call    cs:__imp_OutputDebugStringW
0x1800107a2  test    byte ptr [rbx+4], 4
0x1800107a6  jnz     short loc_1800107B1
0x1800107a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800107af  jz      short loc_1800107C3
0x1800107b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800107b8  test    rax, rax
0x1800107bb  jz      short loc_1800107C3
0x1800107bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800107c2  nop
0x1800107c3  mov     rbx, [rsp+78h+arg_10]
0x1800107cb  add     rsp, 40h
0x1800107cf  pop     r15
0x1800107d1  pop     r14
0x1800107d3  pop     r13
0x1800107d5  pop     r12
0x1800107d7  pop     rdi
0x1800107d8  pop     rsi
0x1800107d9  pop     rbp
0x1800107da  retn
0x1800107db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
