# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005472c`
- end: `0x180054a21`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18005463c`
- `0x18005a3c0`
- `0x18005a470`

## callees

- `0x18004a2b8`
- `0x18005472c`
- `0x180054a30`
- `0x18005a310`
- `0x18005bbb4`
- `0x18005cc98`
- `0x18005cd64`
- `0x18005cd80`
- `0x18005e7cc`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005484f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005484f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180054970`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180054970`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800549e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800549e2`

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
0x18005472c  mov     [rsp+arg_10], rbx
0x180054731  mov     [rsp+arg_8], edx
0x180054735  mov     [rsp+arg_0], rcx
0x18005473a  push    rbp
0x18005473b  push    rsi
0x18005473c  push    rdi
0x18005473d  push    r12
0x18005473f  push    r13
0x180054741  push    r14
0x180054743  push    r15
0x180054745  sub     rsp, 40h
0x180054749  mov     r12, r9
0x18005474c  mov     r13, r8
0x18005474f  mov     r10, rcx
0x180054752  xor     eax, eax
0x180054754  mov     rsi, [rsp+78h+lpOutputString]
0x18005475c  mov     [rsi], ax
0x18005475f  mov     rax, [rsp+78h+arg_60]
0x180054767  mov     byte ptr [rax], 0
0x18005476a  mov     r14, [rsp+78h+arg_38]
0x180054772  mov     edi, [r14]
0x180054775  mov     rbx, [rsp+78h+arg_78]
0x18005477d  mov     [rbx+8], edi
0x180054780  mov     eax, [r14+4]
0x180054784  mov     [rbx+0Ch], eax
0x180054787  xor     ebp, ebp
0x180054789  mov     r15d, [rsp+78h+arg_30]
0x180054791  mov     ecx, r15d
0x180054794  test    r15d, r15d
0x180054797  jz      short loc_1800547FF
0x180054799  sub     ecx, 1
0x18005479c  jz      short loc_1800547F6
0x18005479e  sub     ecx, 1
0x1800547a1  jz      short loc_1800547B1
0x1800547a3  cmp     ecx, 1
0x1800547a6  jnz     short loc_180054808
0x1800547a8  mov     ecx, edi; this
0x1800547aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800547af  jmp     short loc_180054806
0x1800547b1  test    edi, edi
0x1800547b3  js      short loc_1800547ED
0x1800547b5  mov     edi, 8007029Ch
0x1800547ba  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800547be  mov     rax, [rsp+78h+arg_28]
0x1800547c6  mov     [rsp+78h+var_50], rax; __int64
0x1800547cb  mov     rax, [rsp+78h+arg_20]
0x1800547d3  mov     [rsp+78h+var_58], rax; __int64
0x1800547d8  mov     rcx, r10; int
0x1800547db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800547e0  mov     [rbx+8], edi
0x1800547e3  mov     ecx, edi; this
0x1800547e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800547ea  mov     [rbx+0Ch], eax
0x1800547ed  mov     ecx, edi; this
0x1800547ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800547f4  jmp     short loc_180054806
0x1800547f6  mov     ecx, edi; this
0x1800547f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800547fd  jmp     short loc_180054806
0x1800547ff  mov     ecx, edi; this
0x180054801  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180054806  mov     ebp, eax
0x180054808  mov     [rbx], r15d
0x18005480b  mov     eax, [rsp+78h+arg_70]
0x180054812  mov     [rbx+4], eax
0x180054815  cmp     dword ptr [r14+8], 1
0x18005481a  jnz     short loc_180054822
0x18005481c  or      eax, 8
0x18005481f  mov     [rbx+4], eax
0x180054822  mov     eax, 1
0x180054827  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005482f  inc     eax
0x180054831  mov     [rbx+10h], eax
0x180054834  mov     rax, [rsp+78h+arg_40]
0x18005483c  xor     edi, edi
0x18005483e  test    rax, rax
0x180054841  jz      short loc_180054848
0x180054843  cmp     [rax], di
0x180054846  jnz     short loc_18005484B
0x180054848  mov     rax, rdi
0x18005484b  mov     [rbx+18h], rax
0x18005484f  call    cs:__imp_GetCurrentThreadId
0x180054855  mov     [rbx+20h], eax
0x180054858  mov     [rbx+38h], r13
0x18005485c  mov     eax, [rsp+78h+arg_8]
0x180054863  mov     [rbx+40h], eax
0x180054866  mov     [rbx+44h], ebp
0x180054869  mov     rax, [rsp+78h+arg_20]
0x180054871  mov     [rbx+28h], rax
0x180054875  mov     [rbx+30h], r12
0x180054879  mov     rax, [rsp+78h+arg_28]
0x180054881  mov     [rbx+88h], rax
0x180054888  mov     rax, [rsp+78h+arg_0]
0x180054890  mov     [rbx+90h], rax
0x180054897  mov     [rbx+48h], rdi
0x18005489b  xorps   xmm0, xmm0
0x18005489e  xor     eax, eax
0x1800548a0  movups  xmmword ptr [rbx+68h], xmm0
0x1800548a4  mov     [rbx+78h], rax
0x1800548a8  movups  xmmword ptr [rbx+50h], xmm0
0x1800548ac  mov     [rbx+60h], rax
0x1800548b0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800548b7  test    rax, rax
0x1800548ba  jz      short loc_1800548C3
0x1800548bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548c1  jmp     short loc_1800548C6
0x1800548c3  mov     rax, rdi
0x1800548c6  mov     [rbx+80h], rax
0x1800548cd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800548d4  test    rax, rax
0x1800548d7  jz      short loc_1800548E1
0x1800548d9  mov     rcx, rbx
0x1800548dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800548e1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800548e8  test    rax, rax
0x1800548eb  jz      short loc_180054903
0x1800548ed  mov     r8d, 400h
0x1800548f3  mov     rdx, [rsp+78h+arg_60]
0x1800548fb  mov     rcx, rbx
0x1800548fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054903  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005490a  test    rax, rax
0x18005490d  jz      short loc_180054917
0x18005490f  mov     rcx, rbx
0x180054912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054917  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005491e  test    rax, rax
0x180054921  jz      short loc_180054931
0x180054923  test    byte ptr [rbx+4], 2
0x180054927  jnz     short loc_180054931
0x180054929  mov     rcx, rbx
0x18005492c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054931  cmp     [rbx+8], edi
0x180054934  jl      short loc_180054952
0x180054936  cmp     r15d, 3
0x18005493a  jz      short loc_180054942
0x18005493c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180054942  mov     ecx, 8000FFFFh; this
0x180054947  mov     [rbx+8], ecx
0x18005494a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005494f  mov     [rbx+0Ch], eax
0x180054952  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180054959  jnz     short loc_18005497A
0x18005495b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180054962  test    rax, rax
0x180054965  jz      short loc_180054970
0x180054967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005496c  test    al, al
0x18005496e  jmp     short loc_180054978
0x180054970  call    cs:__imp_IsDebuggerPresent
0x180054976  test    eax, eax
0x180054978  jz      short loc_180054980
0x18005497a  test    byte ptr [rbx+4], 2
0x18005497e  jz      short loc_1800549A4
0x180054980  mov     rax, cs:g_pfnResultLoggingCallback
0x180054987  test    rax, rax
0x18005498a  jz      short loc_1800549E8
0x18005498c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180054993  jnz     short loc_1800549E8
0x180054995  xor     r8d, r8d
0x180054998  xor     edx, edx
0x18005499a  mov     rcx, rbx
0x18005499d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549a2  jmp     short loc_1800549E8
0x1800549a4  mov     ebp, 800h
0x1800549a9  mov     rax, cs:g_pfnResultLoggingCallback
0x1800549b0  test    rax, rax
0x1800549b3  jz      short loc_1800549CC
0x1800549b5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800549bc  jnz     short loc_1800549CC
0x1800549be  mov     r8d, ebp
0x1800549c1  mov     rdx, rsi
0x1800549c4  mov     rcx, rbx
0x1800549c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800549cc  cmp     [rsi], di
0x1800549cf  jnz     short loc_1800549DF
0x1800549d1  mov     r8, rbx; unsigned __int64
0x1800549d4  mov     rdx, rbp; unsigned __int16 *
0x1800549d7  mov     rcx, rsi; this
0x1800549da  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800549df  mov     rcx, rsi; lpOutputString
0x1800549e2  call    cs:__imp_OutputDebugStringW
0x1800549e8  test    byte ptr [rbx+4], 4
0x1800549ec  jnz     short loc_1800549F7
0x1800549ee  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800549f5  jz      short loc_180054A09
0x1800549f7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800549fe  test    rax, rax
0x180054a01  jz      short loc_180054A09
0x180054a03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180054a08  nop
0x180054a09  mov     rbx, [rsp+78h+arg_10]
0x180054a11  add     rsp, 40h
0x180054a15  pop     r15
0x180054a17  pop     r14
0x180054a19  pop     r13
0x180054a1b  pop     r12
0x180054a1d  pop     rdi
0x180054a1e  pop     rsi
0x180054a1f  pop     rbp
0x180054a20  retn
```
