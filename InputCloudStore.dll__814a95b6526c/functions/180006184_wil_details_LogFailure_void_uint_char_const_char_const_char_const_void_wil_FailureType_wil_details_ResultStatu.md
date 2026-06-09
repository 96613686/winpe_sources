# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006184`
- end: `0x18000647d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800046cc`
- `0x180004a38`
- `0x18000fed8`

## callees

- `0x180004604`
- `0x1800056d4`
- `0x180005f94`
- `0x180006184`
- `0x180006890`
- `0x1800068b0`
- `0x1800068c4`
- `0x1800068e0`
- `0x180007694`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062a7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800062a7`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800063c6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800063c6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006438`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006438`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180006184  mov     [rsp+arg_10], rbx
0x180006189  mov     [rsp+arg_8], edx
0x18000618d  mov     [rsp+arg_0], rcx
0x180006192  push    rbp
0x180006193  push    rsi
0x180006194  push    rdi
0x180006195  push    r12
0x180006197  push    r13
0x180006199  push    r14
0x18000619b  push    r15
0x18000619d  sub     rsp, 40h
0x1800061a1  mov     r12, r9
0x1800061a4  mov     r13, r8
0x1800061a7  mov     r10, rcx
0x1800061aa  xor     eax, eax
0x1800061ac  mov     rsi, [rsp+78h+lpOutputString]
0x1800061b4  mov     [rsi], ax
0x1800061b7  mov     rax, [rsp+78h+arg_60]
0x1800061bf  mov     byte ptr [rax], 0
0x1800061c2  mov     r14, [rsp+78h+arg_38]
0x1800061ca  mov     edi, [r14]
0x1800061cd  mov     rbx, [rsp+78h+arg_78]
0x1800061d5  mov     [rbx+8], edi
0x1800061d8  mov     eax, [r14+4]
0x1800061dc  mov     [rbx+0Ch], eax
0x1800061df  xor     ebp, ebp
0x1800061e1  mov     r15d, [rsp+78h+arg_30]
0x1800061e9  mov     ecx, r15d
0x1800061ec  test    r15d, r15d
0x1800061ef  jz      short loc_180006257
0x1800061f1  sub     ecx, 1
0x1800061f4  jz      short loc_18000624E
0x1800061f6  sub     ecx, 1
0x1800061f9  jz      short loc_180006209
0x1800061fb  cmp     ecx, 1
0x1800061fe  jnz     short loc_180006260
0x180006200  mov     ecx, edi; this
0x180006202  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006207  jmp     short loc_18000625E
0x180006209  test    edi, edi
0x18000620b  js      short loc_180006245
0x18000620d  mov     edi, 8007029Ch
0x180006212  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006216  mov     rax, [rsp+78h+arg_28]
0x18000621e  mov     [rsp+78h+var_50], rax; __int64
0x180006223  mov     rax, [rsp+78h+arg_20]
0x18000622b  mov     [rsp+78h+var_58], rax; __int64
0x180006230  mov     rcx, r10; int
0x180006233  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006238  mov     [rbx+8], edi
0x18000623b  mov     ecx, edi; this
0x18000623d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006242  mov     [rbx+0Ch], eax
0x180006245  mov     ecx, edi; this
0x180006247  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000624c  jmp     short loc_18000625E
0x18000624e  mov     ecx, edi; this
0x180006250  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006255  jmp     short loc_18000625E
0x180006257  mov     ecx, edi; this
0x180006259  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000625e  mov     ebp, eax
0x180006260  mov     [rbx], r15d
0x180006263  mov     eax, [rsp+78h+arg_70]
0x18000626a  mov     [rbx+4], eax
0x18000626d  cmp     dword ptr [r14+8], 1
0x180006272  jnz     short loc_18000627A
0x180006274  or      eax, 8
0x180006277  mov     [rbx+4], eax
0x18000627a  mov     eax, 1
0x18000627f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006287  inc     eax
0x180006289  mov     [rbx+10h], eax
0x18000628c  mov     rax, [rsp+78h+arg_40]
0x180006294  xor     edi, edi
0x180006296  test    rax, rax
0x180006299  jz      short loc_1800062A0
0x18000629b  cmp     [rax], di
0x18000629e  jnz     short loc_1800062A3
0x1800062a0  mov     rax, rdi
0x1800062a3  mov     [rbx+18h], rax
0x1800062a7  call    cs:__imp_GetCurrentThreadId
0x1800062ad  mov     [rbx+20h], eax
0x1800062b0  mov     [rbx+38h], r13
0x1800062b4  mov     eax, [rsp+78h+arg_8]
0x1800062bb  mov     [rbx+40h], eax
0x1800062be  mov     [rbx+44h], ebp
0x1800062c1  mov     rax, [rsp+78h+arg_20]
0x1800062c9  mov     [rbx+28h], rax
0x1800062cd  mov     [rbx+30h], r12
0x1800062d1  mov     rax, [rsp+78h+arg_28]
0x1800062d9  mov     [rbx+88h], rax
0x1800062e0  mov     rax, [rsp+78h+arg_0]
0x1800062e8  mov     [rbx+90h], rax
0x1800062ef  mov     [rbx+48h], rdi
0x1800062f3  xorps   xmm0, xmm0
0x1800062f6  xor     eax, eax
0x1800062f8  movups  xmmword ptr [rbx+68h], xmm0
0x1800062fc  mov     [rbx+78h], rax
0x180006300  movups  xmmword ptr [rbx+50h], xmm0
0x180006304  mov     [rbx+60h], rax
0x180006308  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000630f  test    rax, rax
0x180006312  jz      short loc_18000631B
0x180006314  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006319  jmp     short loc_18000631E
0x18000631b  mov     rax, rdi
0x18000631e  mov     [rbx+80h], rax
0x180006325  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000632c  test    rax, rax
0x18000632f  jz      short loc_180006339
0x180006331  mov     rcx, rbx
0x180006334  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006339  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006340  test    rax, rax
0x180006343  jz      short loc_18000635B
0x180006345  mov     r8d, 400h
0x18000634b  mov     rdx, [rsp+78h+arg_60]
0x180006353  mov     rcx, rbx
0x180006356  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000635b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006362  test    rax, rax
0x180006365  jz      short loc_18000636F
0x180006367  mov     rcx, rbx
0x18000636a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000636f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006376  test    rax, rax
0x180006379  jz      short loc_180006389
0x18000637b  test    byte ptr [rbx+4], 2
0x18000637f  jnz     short loc_180006389
0x180006381  mov     rcx, rbx
0x180006384  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006389  cmp     [rbx+8], edi
0x18000638c  jl      short loc_1800063A8
0x18000638e  cmp     r15d, 3
0x180006392  jnz     loc_180006477
0x180006398  mov     ecx, 8000FFFFh; this
0x18000639d  mov     [rbx+8], ecx
0x1800063a0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800063a5  mov     [rbx+0Ch], eax
0x1800063a8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800063af  jnz     short loc_1800063D0
0x1800063b1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800063b8  test    rax, rax
0x1800063bb  jz      short loc_1800063C6
0x1800063bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063c2  test    al, al
0x1800063c4  jmp     short loc_1800063CE
0x1800063c6  call    cs:__imp_IsDebuggerPresent
0x1800063cc  test    eax, eax
0x1800063ce  jz      short loc_1800063D6
0x1800063d0  test    byte ptr [rbx+4], 2
0x1800063d4  jz      short loc_1800063FA
0x1800063d6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800063dd  test    rax, rax
0x1800063e0  jz      short loc_18000643E
0x1800063e2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800063e9  jnz     short loc_18000643E
0x1800063eb  xor     r8d, r8d
0x1800063ee  xor     edx, edx
0x1800063f0  mov     rcx, rbx
0x1800063f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063f8  jmp     short loc_18000643E
0x1800063fa  mov     ebp, 800h
0x1800063ff  mov     rax, cs:g_pfnResultLoggingCallback
0x180006406  test    rax, rax
0x180006409  jz      short loc_180006422
0x18000640b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006412  jnz     short loc_180006422
0x180006414  mov     r8d, ebp
0x180006417  mov     rdx, rsi
0x18000641a  mov     rcx, rbx
0x18000641d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006422  cmp     [rsi], di
0x180006425  jnz     short loc_180006435
0x180006427  mov     r8, rbx; unsigned __int64
0x18000642a  mov     rdx, rbp; wchar_t *
0x18000642d  mov     rcx, rsi; this
0x180006430  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180006435  mov     rcx, rsi; lpOutputString
0x180006438  call    cs:__imp_OutputDebugStringW
0x18000643e  test    byte ptr [rbx+4], 4
0x180006442  jnz     short loc_18000644D
0x180006444  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000644b  jz      short loc_18000645F
0x18000644d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006454  test    rax, rax
0x180006457  jz      short loc_18000645F
0x180006459  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645e  nop
0x18000645f  mov     rbx, [rsp+78h+arg_10]
0x180006467  add     rsp, 40h
0x18000646b  pop     r15
0x18000646d  pop     r14
0x18000646f  pop     r13
0x180006471  pop     r12
0x180006473  pop     rdi
0x180006474  pop     rsi
0x180006475  pop     rbp
0x180006476  retn
0x180006477  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
