# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800063a8`
- end: `0x1800066a0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004754`
- `0x180004aa8`
- `0x180064fa8`

## callees

- `0x18000468c`
- `0x1800058d4`
- `0x180006150`
- `0x1800063a8`
- `0x180006a5c`
- `0x180006a80`
- `0x180006a94`
- `0x180006ab0`
- `0x180007914`
- `0x18006c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800064cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000665c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000665c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800065ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800065ea`

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
0x1800063a8  mov     [rsp+arg_10], rbx
0x1800063ad  mov     [rsp+arg_8], edx
0x1800063b1  mov     [rsp+arg_0], rcx
0x1800063b6  push    rbp
0x1800063b7  push    rsi
0x1800063b8  push    rdi
0x1800063b9  push    r12
0x1800063bb  push    r13
0x1800063bd  push    r14
0x1800063bf  push    r15
0x1800063c1  sub     rsp, 40h
0x1800063c5  mov     r14, [rsp+78h+arg_38]
0x1800063cd  xor     eax, eax
0x1800063cf  mov     rbx, [rsp+78h+arg_78]
0x1800063d7  xor     ebp, ebp
0x1800063d9  mov     r15d, [rsp+78h+arg_30]
0x1800063e1  mov     r10, rcx
0x1800063e4  mov     rsi, [rsp+78h+lpOutputString]
0x1800063ec  mov     r12, r9
0x1800063ef  mov     r13, r8
0x1800063f2  mov     ecx, r15d
0x1800063f5  mov     [rsi], ax
0x1800063f8  mov     rax, [rsp+78h+arg_60]
0x180006400  mov     byte ptr [rax], 0
0x180006403  mov     edi, [r14]
0x180006406  mov     [rbx+8], edi
0x180006409  mov     eax, [r14+4]
0x18000640d  mov     [rbx+0Ch], eax
0x180006410  test    r15d, r15d
0x180006413  jz      short loc_18000647B
0x180006415  sub     ecx, 1
0x180006418  jz      short loc_180006472
0x18000641a  sub     ecx, 1
0x18000641d  jz      short loc_18000642D
0x18000641f  cmp     ecx, 1
0x180006422  jnz     short loc_180006484
0x180006424  mov     ecx, edi; this
0x180006426  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000642b  jmp     short loc_180006482
0x18000642d  test    edi, edi
0x18000642f  js      short loc_180006469
0x180006431  mov     rax, [rsp+78h+arg_28]
0x180006439  mov     edi, 8007029Ch
0x18000643e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006442  mov     rcx, r10; int
0x180006445  mov     [rsp+78h+var_50], rax; __int64
0x18000644a  mov     rax, [rsp+78h+arg_20]
0x180006452  mov     [rsp+78h+var_58], rax; __int64
0x180006457  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000645c  mov     ecx, edi; this
0x18000645e  mov     [rbx+8], edi
0x180006461  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006466  mov     [rbx+0Ch], eax
0x180006469  mov     ecx, edi; this
0x18000646b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006470  jmp     short loc_180006482
0x180006472  mov     ecx, edi; this
0x180006474  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006479  jmp     short loc_180006482
0x18000647b  mov     ecx, edi; this
0x18000647d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006482  mov     ebp, eax
0x180006484  mov     eax, [rsp+78h+arg_70]
0x18000648b  mov     [rbx+4], eax
0x18000648e  mov     [rbx], r15d
0x180006491  cmp     dword ptr [r14+8], 1
0x180006496  jnz     short loc_18000649E
0x180006498  or      eax, 8
0x18000649b  mov     [rbx+4], eax
0x18000649e  mov     eax, 1
0x1800064a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800064ab  inc     eax
0x1800064ad  xor     edi, edi
0x1800064af  mov     [rbx+10h], eax
0x1800064b2  mov     rax, [rsp+78h+arg_40]
0x1800064ba  test    rax, rax
0x1800064bd  jz      short loc_1800064C4
0x1800064bf  cmp     [rax], di
0x1800064c2  jnz     short loc_1800064C7
0x1800064c4  mov     rax, rdi
0x1800064c7  mov     [rbx+18h], rax
0x1800064cb  call    cs:__imp_GetCurrentThreadId
0x1800064d1  mov     [rbx+38h], r13
0x1800064d5  xorps   xmm0, xmm0
0x1800064d8  mov     [rbx+20h], eax
0x1800064db  mov     eax, [rsp+78h+arg_8]
0x1800064e2  mov     [rbx+40h], eax
0x1800064e5  mov     rax, [rsp+78h+arg_20]
0x1800064ed  mov     [rbx+28h], rax
0x1800064f1  mov     rax, [rsp+78h+arg_28]
0x1800064f9  mov     [rbx+88h], rax
0x180006500  mov     rax, [rsp+78h+arg_0]
0x180006508  mov     [rbx+90h], rax
0x18000650f  xor     eax, eax
0x180006511  mov     [rbx+44h], ebp
0x180006514  mov     [rbx+30h], r12
0x180006518  mov     [rbx+48h], rdi
0x18000651c  movups  xmmword ptr [rbx+68h], xmm0
0x180006520  mov     [rbx+78h], rax
0x180006524  movups  xmmword ptr [rbx+50h], xmm0
0x180006528  mov     [rbx+60h], rax
0x18000652c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006533  test    rax, rax
0x180006536  jz      short loc_18000653F
0x180006538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000653d  jmp     short loc_180006542
0x18000653f  mov     rax, rdi
0x180006542  mov     [rbx+80h], rax
0x180006549  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006550  test    rax, rax
0x180006553  jz      short loc_18000655D
0x180006555  mov     rcx, rbx
0x180006558  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000655d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006564  test    rax, rax
0x180006567  jz      short loc_18000657F
0x180006569  mov     rdx, [rsp+78h+arg_60]
0x180006571  mov     r8d, 400h
0x180006577  mov     rcx, rbx
0x18000657a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000657f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006586  test    rax, rax
0x180006589  jz      short loc_180006593
0x18000658b  mov     rcx, rbx
0x18000658e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006593  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000659a  test    rax, rax
0x18000659d  jz      short loc_1800065AD
0x18000659f  test    byte ptr [rbx+4], 2
0x1800065a3  jnz     short loc_1800065AD
0x1800065a5  mov     rcx, rbx
0x1800065a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ad  cmp     [rbx+8], edi
0x1800065b0  jl      short loc_1800065CC
0x1800065b2  cmp     r15d, 3
0x1800065b6  jnz     loc_18000669A
0x1800065bc  mov     ecx, 8000FFFFh; this
0x1800065c1  mov     [rbx+8], ecx
0x1800065c4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800065c9  mov     [rbx+0Ch], eax
0x1800065cc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800065d3  jnz     short loc_1800065F4
0x1800065d5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800065dc  test    rax, rax
0x1800065df  jz      short loc_1800065EA
0x1800065e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e6  test    al, al
0x1800065e8  jmp     short loc_1800065F2
0x1800065ea  call    cs:__imp_IsDebuggerPresent
0x1800065f0  test    eax, eax
0x1800065f2  jz      short loc_1800065FA
0x1800065f4  test    byte ptr [rbx+4], 2
0x1800065f8  jz      short loc_18000661E
0x1800065fa  mov     rax, cs:g_pfnResultLoggingCallback
0x180006601  test    rax, rax
0x180006604  jz      short loc_180006662
0x180006606  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000660d  jnz     short loc_180006662
0x18000660f  xor     r8d, r8d
0x180006612  xor     edx, edx
0x180006614  mov     rcx, rbx
0x180006617  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661c  jmp     short loc_180006662
0x18000661e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006625  mov     ebp, 800h
0x18000662a  test    rax, rax
0x18000662d  jz      short loc_180006646
0x18000662f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006636  jnz     short loc_180006646
0x180006638  mov     r8d, ebp
0x18000663b  mov     rdx, rsi
0x18000663e  mov     rcx, rbx
0x180006641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006646  cmp     [rsi], di
0x180006649  jnz     short loc_180006659
0x18000664b  mov     r8, rbx; unsigned __int64
0x18000664e  mov     rdx, rbp; unsigned __int16 *
0x180006651  mov     rcx, rsi; this
0x180006654  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006659  mov     rcx, rsi; lpOutputString
0x18000665c  call    cs:__imp_OutputDebugStringW
0x180006662  test    byte ptr [rbx+4], 4
0x180006666  jnz     short loc_180006671
0x180006668  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000666f  jz      short loc_180006682
0x180006671  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006678  test    rax, rax
0x18000667b  jz      short loc_180006682
0x18000667d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006682  mov     rbx, [rsp+78h+arg_10]
0x18000668a  add     rsp, 40h
0x18000668e  pop     r15
0x180006690  pop     r14
0x180006692  pop     r13
0x180006694  pop     r12
0x180006696  pop     rdi
0x180006697  pop     rsi
0x180006698  pop     rbp
0x180006699  retn
0x18000669a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
