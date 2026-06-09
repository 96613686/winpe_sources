# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800055e4`
- end: `0x1800058dd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002cac`

## callees

- `0x1800026b8`
- `0x180004c84`
- `0x180005420`
- `0x1800055e4`
- `0x180006034`
- `0x180006050`
- `0x18000617c`
- `0x180006198`
- `0x18000870c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005707`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005707`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005898`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005898`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005826`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005826`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x1800055e4  mov     [rsp+arg_10], rbx
0x1800055e9  mov     [rsp+arg_8], edx
0x1800055ed  mov     [rsp+arg_0], rcx
0x1800055f2  push    rbp
0x1800055f3  push    rsi
0x1800055f4  push    rdi
0x1800055f5  push    r12
0x1800055f7  push    r13
0x1800055f9  push    r14
0x1800055fb  push    r15
0x1800055fd  sub     rsp, 40h
0x180005601  mov     r12, r9
0x180005604  mov     r13, r8
0x180005607  mov     r10, rcx
0x18000560a  xor     eax, eax
0x18000560c  mov     rsi, [rsp+78h+lpOutputString]
0x180005614  mov     [rsi], ax
0x180005617  mov     rax, [rsp+78h+arg_60]
0x18000561f  mov     byte ptr [rax], 0
0x180005622  mov     r14, [rsp+78h+arg_38]
0x18000562a  mov     edi, [r14]
0x18000562d  mov     rbx, [rsp+78h+arg_78]
0x180005635  mov     [rbx+8], edi
0x180005638  mov     eax, [r14+4]
0x18000563c  mov     [rbx+0Ch], eax
0x18000563f  xor     ebp, ebp
0x180005641  mov     r15d, [rsp+78h+arg_30]
0x180005649  mov     ecx, r15d
0x18000564c  test    r15d, r15d
0x18000564f  jz      short loc_1800056B7
0x180005651  sub     ecx, 1
0x180005654  jz      short loc_1800056AE
0x180005656  sub     ecx, 1
0x180005659  jz      short loc_180005669
0x18000565b  cmp     ecx, 1
0x18000565e  jnz     short loc_1800056C0
0x180005660  mov     ecx, edi; this
0x180005662  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005667  jmp     short loc_1800056BE
0x180005669  test    edi, edi
0x18000566b  js      short loc_1800056A5
0x18000566d  mov     edi, 8007029Ch
0x180005672  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005676  mov     rax, [rsp+78h+arg_28]
0x18000567e  mov     [rsp+78h+var_50], rax; __int64
0x180005683  mov     rax, [rsp+78h+arg_20]
0x18000568b  mov     [rsp+78h+var_58], rax; __int64
0x180005690  mov     rcx, r10; int
0x180005693  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005698  mov     [rbx+8], edi
0x18000569b  mov     ecx, edi; this
0x18000569d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800056a2  mov     [rbx+0Ch], eax
0x1800056a5  mov     ecx, edi; this
0x1800056a7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800056ac  jmp     short loc_1800056BE
0x1800056ae  mov     ecx, edi; this
0x1800056b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800056b5  jmp     short loc_1800056BE
0x1800056b7  mov     ecx, edi; this
0x1800056b9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800056be  mov     ebp, eax
0x1800056c0  mov     [rbx], r15d
0x1800056c3  mov     eax, [rsp+78h+arg_70]
0x1800056ca  mov     [rbx+4], eax
0x1800056cd  cmp     dword ptr [r14+8], 1
0x1800056d2  jnz     short loc_1800056DA
0x1800056d4  or      eax, 8
0x1800056d7  mov     [rbx+4], eax
0x1800056da  mov     eax, 1
0x1800056df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800056e7  inc     eax
0x1800056e9  mov     [rbx+10h], eax
0x1800056ec  mov     rax, [rsp+78h+arg_40]
0x1800056f4  xor     edi, edi
0x1800056f6  test    rax, rax
0x1800056f9  jz      short loc_180005700
0x1800056fb  cmp     [rax], di
0x1800056fe  jnz     short loc_180005703
0x180005700  mov     rax, rdi
0x180005703  mov     [rbx+18h], rax
0x180005707  call    cs:__imp_GetCurrentThreadId
0x18000570d  mov     [rbx+20h], eax
0x180005710  mov     [rbx+38h], r13
0x180005714  mov     eax, [rsp+78h+arg_8]
0x18000571b  mov     [rbx+40h], eax
0x18000571e  mov     [rbx+44h], ebp
0x180005721  mov     rax, [rsp+78h+arg_20]
0x180005729  mov     [rbx+28h], rax
0x18000572d  mov     [rbx+30h], r12
0x180005731  mov     rax, [rsp+78h+arg_28]
0x180005739  mov     [rbx+88h], rax
0x180005740  mov     rax, [rsp+78h+arg_0]
0x180005748  mov     [rbx+90h], rax
0x18000574f  mov     [rbx+48h], rdi
0x180005753  xorps   xmm0, xmm0
0x180005756  xor     eax, eax
0x180005758  movups  xmmword ptr [rbx+68h], xmm0
0x18000575c  mov     [rbx+78h], rax
0x180005760  movups  xmmword ptr [rbx+50h], xmm0
0x180005764  mov     [rbx+60h], rax
0x180005768  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000576f  test    rax, rax
0x180005772  jz      short loc_18000577B
0x180005774  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005779  jmp     short loc_18000577E
0x18000577b  mov     rax, rdi
0x18000577e  mov     [rbx+80h], rax
0x180005785  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000578c  test    rax, rax
0x18000578f  jz      short loc_180005799
0x180005791  mov     rcx, rbx
0x180005794  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005799  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800057a0  test    rax, rax
0x1800057a3  jz      short loc_1800057BB
0x1800057a5  mov     r8d, 400h
0x1800057ab  mov     rdx, [rsp+78h+arg_60]
0x1800057b3  mov     rcx, rbx
0x1800057b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057bb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800057c2  test    rax, rax
0x1800057c5  jz      short loc_1800057CF
0x1800057c7  mov     rcx, rbx
0x1800057ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057cf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800057d6  test    rax, rax
0x1800057d9  jz      short loc_1800057E9
0x1800057db  test    byte ptr [rbx+4], 2
0x1800057df  jnz     short loc_1800057E9
0x1800057e1  mov     rcx, rbx
0x1800057e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800057e9  cmp     [rbx+8], edi
0x1800057ec  jl      short loc_180005808
0x1800057ee  cmp     r15d, 3
0x1800057f2  jnz     loc_1800058D7
0x1800057f8  mov     ecx, 8000FFFFh; this
0x1800057fd  mov     [rbx+8], ecx
0x180005800  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005805  mov     [rbx+0Ch], eax
0x180005808  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000580f  jnz     short loc_180005830
0x180005811  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005818  test    rax, rax
0x18000581b  jz      short loc_180005826
0x18000581d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005822  test    al, al
0x180005824  jmp     short loc_18000582E
0x180005826  call    cs:__imp_IsDebuggerPresent
0x18000582c  test    eax, eax
0x18000582e  jz      short loc_180005836
0x180005830  test    byte ptr [rbx+4], 2
0x180005834  jz      short loc_18000585A
0x180005836  mov     rax, cs:g_pfnResultLoggingCallback
0x18000583d  test    rax, rax
0x180005840  jz      short loc_18000589E
0x180005842  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005849  jnz     short loc_18000589E
0x18000584b  xor     r8d, r8d
0x18000584e  xor     edx, edx
0x180005850  mov     rcx, rbx
0x180005853  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005858  jmp     short loc_18000589E
0x18000585a  mov     ebp, 800h
0x18000585f  mov     rax, cs:g_pfnResultLoggingCallback
0x180005866  test    rax, rax
0x180005869  jz      short loc_180005882
0x18000586b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005872  jnz     short loc_180005882
0x180005874  mov     r8d, ebp
0x180005877  mov     rdx, rsi
0x18000587a  mov     rcx, rbx
0x18000587d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005882  cmp     [rsi], di
0x180005885  jnz     short loc_180005895
0x180005887  mov     r8, rbx; unsigned __int64
0x18000588a  mov     rdx, rbp; unsigned __int16 *
0x18000588d  mov     rcx, rsi; this
0x180005890  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005895  mov     rcx, rsi; lpOutputString
0x180005898  call    cs:__imp_OutputDebugStringW
0x18000589e  test    byte ptr [rbx+4], 4
0x1800058a2  jnz     short loc_1800058AD
0x1800058a4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800058ab  jz      short loc_1800058BF
0x1800058ad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800058b4  test    rax, rax
0x1800058b7  jz      short loc_1800058BF
0x1800058b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800058be  nop
0x1800058bf  mov     rbx, [rsp+78h+arg_10]
0x1800058c7  add     rsp, 40h
0x1800058cb  pop     r15
0x1800058cd  pop     r14
0x1800058cf  pop     r13
0x1800058d1  pop     r12
0x1800058d3  pop     rdi
0x1800058d4  pop     rsi
0x1800058d5  pop     rbp
0x1800058d6  retn
0x1800058d7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
