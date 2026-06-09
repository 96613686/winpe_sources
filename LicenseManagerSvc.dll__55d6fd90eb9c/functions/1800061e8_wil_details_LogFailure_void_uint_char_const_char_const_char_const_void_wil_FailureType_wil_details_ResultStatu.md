# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800061e8`
- end: `0x1800064e1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800047c0`
- `0x180004880`
- `0x180004c38`

## callees

- `0x180001c34`
- `0x1800046a0`
- `0x180005794`
- `0x1800061e8`
- `0x180006950`
- `0x180006970`
- `0x180006984`
- `0x1800069a0`
- `0x180007558`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000630b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000630b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000649c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000649c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000642a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000642a`

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
0x1800061e8  mov     [rsp+arg_10], rbx
0x1800061ed  mov     [rsp+arg_8], edx
0x1800061f1  mov     [rsp+arg_0], rcx
0x1800061f6  push    rbp
0x1800061f7  push    rsi
0x1800061f8  push    rdi
0x1800061f9  push    r12
0x1800061fb  push    r13
0x1800061fd  push    r14
0x1800061ff  push    r15
0x180006201  sub     rsp, 40h
0x180006205  mov     r12, r9
0x180006208  mov     r13, r8
0x18000620b  mov     r10, rcx
0x18000620e  xor     eax, eax
0x180006210  mov     rsi, [rsp+78h+lpOutputString]
0x180006218  mov     [rsi], ax
0x18000621b  mov     rax, [rsp+78h+arg_60]
0x180006223  mov     byte ptr [rax], 0
0x180006226  mov     r14, [rsp+78h+arg_38]
0x18000622e  mov     edi, [r14]
0x180006231  mov     rbx, [rsp+78h+arg_78]
0x180006239  mov     [rbx+8], edi
0x18000623c  mov     eax, [r14+4]
0x180006240  mov     [rbx+0Ch], eax
0x180006243  xor     ebp, ebp
0x180006245  mov     r15d, [rsp+78h+arg_30]
0x18000624d  mov     ecx, r15d
0x180006250  test    r15d, r15d
0x180006253  jz      short loc_1800062BB
0x180006255  sub     ecx, 1
0x180006258  jz      short loc_1800062B2
0x18000625a  sub     ecx, 1
0x18000625d  jz      short loc_18000626D
0x18000625f  cmp     ecx, 1
0x180006262  jnz     short loc_1800062C4
0x180006264  mov     ecx, edi; this
0x180006266  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000626b  jmp     short loc_1800062C2
0x18000626d  test    edi, edi
0x18000626f  js      short loc_1800062A9
0x180006271  mov     edi, 8007029Ch
0x180006276  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000627a  mov     rax, [rsp+78h+arg_28]
0x180006282  mov     [rsp+78h+var_50], rax; __int64
0x180006287  mov     rax, [rsp+78h+arg_20]
0x18000628f  mov     [rsp+78h+var_58], rax; __int64
0x180006294  mov     rcx, r10; int
0x180006297  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000629c  mov     [rbx+8], edi
0x18000629f  mov     ecx, edi; this
0x1800062a1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800062a6  mov     [rbx+0Ch], eax
0x1800062a9  mov     ecx, edi; this
0x1800062ab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800062b0  jmp     short loc_1800062C2
0x1800062b2  mov     ecx, edi; this
0x1800062b4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800062b9  jmp     short loc_1800062C2
0x1800062bb  mov     ecx, edi; this
0x1800062bd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800062c2  mov     ebp, eax
0x1800062c4  mov     [rbx], r15d
0x1800062c7  mov     eax, [rsp+78h+arg_70]
0x1800062ce  mov     [rbx+4], eax
0x1800062d1  cmp     dword ptr [r14+8], 1
0x1800062d6  jnz     short loc_1800062DE
0x1800062d8  or      eax, 8
0x1800062db  mov     [rbx+4], eax
0x1800062de  mov     eax, 1
0x1800062e3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800062eb  inc     eax
0x1800062ed  mov     [rbx+10h], eax
0x1800062f0  mov     rax, [rsp+78h+arg_40]
0x1800062f8  xor     edi, edi
0x1800062fa  test    rax, rax
0x1800062fd  jz      short loc_180006304
0x1800062ff  cmp     [rax], di
0x180006302  jnz     short loc_180006307
0x180006304  mov     rax, rdi
0x180006307  mov     [rbx+18h], rax
0x18000630b  call    cs:__imp_GetCurrentThreadId
0x180006311  mov     [rbx+20h], eax
0x180006314  mov     [rbx+38h], r13
0x180006318  mov     eax, [rsp+78h+arg_8]
0x18000631f  mov     [rbx+40h], eax
0x180006322  mov     [rbx+44h], ebp
0x180006325  mov     rax, [rsp+78h+arg_20]
0x18000632d  mov     [rbx+28h], rax
0x180006331  mov     [rbx+30h], r12
0x180006335  mov     rax, [rsp+78h+arg_28]
0x18000633d  mov     [rbx+88h], rax
0x180006344  mov     rax, [rsp+78h+arg_0]
0x18000634c  mov     [rbx+90h], rax
0x180006353  mov     [rbx+48h], rdi
0x180006357  xorps   xmm0, xmm0
0x18000635a  xor     eax, eax
0x18000635c  movups  xmmword ptr [rbx+68h], xmm0
0x180006360  mov     [rbx+78h], rax
0x180006364  movups  xmmword ptr [rbx+50h], xmm0
0x180006368  mov     [rbx+60h], rax
0x18000636c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006373  test    rax, rax
0x180006376  jz      short loc_18000637F
0x180006378  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000637d  jmp     short loc_180006382
0x18000637f  mov     rax, rdi
0x180006382  mov     [rbx+80h], rax
0x180006389  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006390  test    rax, rax
0x180006393  jz      short loc_18000639D
0x180006395  mov     rcx, rbx
0x180006398  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000639d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800063a4  test    rax, rax
0x1800063a7  jz      short loc_1800063BF
0x1800063a9  mov     r8d, 400h
0x1800063af  mov     rdx, [rsp+78h+arg_60]
0x1800063b7  mov     rcx, rbx
0x1800063ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063bf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063c6  test    rax, rax
0x1800063c9  jz      short loc_1800063D3
0x1800063cb  mov     rcx, rbx
0x1800063ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063d3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800063da  test    rax, rax
0x1800063dd  jz      short loc_1800063ED
0x1800063df  test    byte ptr [rbx+4], 2
0x1800063e3  jnz     short loc_1800063ED
0x1800063e5  mov     rcx, rbx
0x1800063e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063ed  cmp     [rbx+8], edi
0x1800063f0  jl      short loc_18000640C
0x1800063f2  cmp     r15d, 3
0x1800063f6  jnz     loc_1800064DB
0x1800063fc  mov     ecx, 8000FFFFh; this
0x180006401  mov     [rbx+8], ecx
0x180006404  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006409  mov     [rbx+0Ch], eax
0x18000640c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006413  jnz     short loc_180006434
0x180006415  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000641c  test    rax, rax
0x18000641f  jz      short loc_18000642A
0x180006421  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006426  test    al, al
0x180006428  jmp     short loc_180006432
0x18000642a  call    cs:__imp_IsDebuggerPresent
0x180006430  test    eax, eax
0x180006432  jz      short loc_18000643A
0x180006434  test    byte ptr [rbx+4], 2
0x180006438  jz      short loc_18000645E
0x18000643a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006441  test    rax, rax
0x180006444  jz      short loc_1800064A2
0x180006446  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000644d  jnz     short loc_1800064A2
0x18000644f  xor     r8d, r8d
0x180006452  xor     edx, edx
0x180006454  mov     rcx, rbx
0x180006457  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000645c  jmp     short loc_1800064A2
0x18000645e  mov     ebp, 800h
0x180006463  mov     rax, cs:g_pfnResultLoggingCallback
0x18000646a  test    rax, rax
0x18000646d  jz      short loc_180006486
0x18000646f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006476  jnz     short loc_180006486
0x180006478  mov     r8d, ebp
0x18000647b  mov     rdx, rsi
0x18000647e  mov     rcx, rbx
0x180006481  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006486  cmp     [rsi], di
0x180006489  jnz     short loc_180006499
0x18000648b  mov     r8, rbx; unsigned __int64
0x18000648e  mov     rdx, rbp; unsigned __int16 *
0x180006491  mov     rcx, rsi; this
0x180006494  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006499  mov     rcx, rsi; lpOutputString
0x18000649c  call    cs:__imp_OutputDebugStringW
0x1800064a2  test    byte ptr [rbx+4], 4
0x1800064a6  jnz     short loc_1800064B1
0x1800064a8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800064af  jz      short loc_1800064C3
0x1800064b1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800064b8  test    rax, rax
0x1800064bb  jz      short loc_1800064C3
0x1800064bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800064c2  nop
0x1800064c3  mov     rbx, [rsp+78h+arg_10]
0x1800064cb  add     rsp, 40h
0x1800064cf  pop     r15
0x1800064d1  pop     r14
0x1800064d3  pop     r13
0x1800064d5  pop     r12
0x1800064d7  pop     rdi
0x1800064d8  pop     rsi
0x1800064d9  pop     rbp
0x1800064da  retn
0x1800064db  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
