# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004680`
- end: `0x140004979`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140002d50`
- `0x1400030bc`
- `0x1400078fc`

## callees

- `0x140002c88`
- `0x140003c94`
- `0x1400044bc`
- `0x140004680`
- `0x140004d4c`
- `0x140004d70`
- `0x140004d84`
- `0x140004da0`
- `0x140005b64`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400047a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400048c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400048c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004934`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004934`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x140004680  mov     [rsp+arg_10], rbx
0x140004685  mov     [rsp+arg_8], edx
0x140004689  mov     [rsp+arg_0], rcx
0x14000468e  push    rbp
0x14000468f  push    rsi
0x140004690  push    rdi
0x140004691  push    r12
0x140004693  push    r13
0x140004695  push    r14
0x140004697  push    r15
0x140004699  sub     rsp, 40h
0x14000469d  mov     r12, r9
0x1400046a0  mov     r13, r8
0x1400046a3  mov     r10, rcx
0x1400046a6  xor     eax, eax
0x1400046a8  mov     rsi, [rsp+78h+lpOutputString]
0x1400046b0  mov     [rsi], ax
0x1400046b3  mov     rax, [rsp+78h+arg_60]
0x1400046bb  mov     byte ptr [rax], 0
0x1400046be  mov     r14, [rsp+78h+arg_38]
0x1400046c6  mov     edi, [r14]
0x1400046c9  mov     rbx, [rsp+78h+arg_78]
0x1400046d1  mov     [rbx+8], edi
0x1400046d4  mov     eax, [r14+4]
0x1400046d8  mov     [rbx+0Ch], eax
0x1400046db  xor     ebp, ebp
0x1400046dd  mov     r15d, [rsp+78h+arg_30]
0x1400046e5  mov     ecx, r15d
0x1400046e8  test    r15d, r15d
0x1400046eb  jz      short loc_140004753
0x1400046ed  sub     ecx, 1
0x1400046f0  jz      short loc_14000474A
0x1400046f2  sub     ecx, 1
0x1400046f5  jz      short loc_140004705
0x1400046f7  cmp     ecx, 1
0x1400046fa  jnz     short loc_14000475C
0x1400046fc  mov     ecx, edi; this
0x1400046fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004703  jmp     short loc_14000475A
0x140004705  test    edi, edi
0x140004707  js      short loc_140004741
0x140004709  mov     edi, 8007029Ch
0x14000470e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004712  mov     rax, [rsp+78h+arg_28]
0x14000471a  mov     [rsp+78h+var_50], rax; __int64
0x14000471f  mov     rax, [rsp+78h+arg_20]
0x140004727  mov     [rsp+78h+var_58], rax; __int64
0x14000472c  mov     rcx, r10; int
0x14000472f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004734  mov     [rbx+8], edi
0x140004737  mov     ecx, edi; this
0x140004739  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000473e  mov     [rbx+0Ch], eax
0x140004741  mov     ecx, edi; this
0x140004743  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004748  jmp     short loc_14000475A
0x14000474a  mov     ecx, edi; this
0x14000474c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004751  jmp     short loc_14000475A
0x140004753  mov     ecx, edi; this
0x140004755  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000475a  mov     ebp, eax
0x14000475c  mov     [rbx], r15d
0x14000475f  mov     eax, [rsp+78h+arg_70]
0x140004766  mov     [rbx+4], eax
0x140004769  cmp     dword ptr [r14+8], 1
0x14000476e  jnz     short loc_140004776
0x140004770  or      eax, 8
0x140004773  mov     [rbx+4], eax
0x140004776  mov     eax, 1
0x14000477b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004783  inc     eax
0x140004785  mov     [rbx+10h], eax
0x140004788  mov     rax, [rsp+78h+arg_40]
0x140004790  xor     edi, edi
0x140004792  test    rax, rax
0x140004795  jz      short loc_14000479C
0x140004797  cmp     [rax], di
0x14000479a  jnz     short loc_14000479F
0x14000479c  mov     rax, rdi
0x14000479f  mov     [rbx+18h], rax
0x1400047a3  call    cs:__imp_GetCurrentThreadId
0x1400047a9  mov     [rbx+20h], eax
0x1400047ac  mov     [rbx+38h], r13
0x1400047b0  mov     eax, [rsp+78h+arg_8]
0x1400047b7  mov     [rbx+40h], eax
0x1400047ba  mov     [rbx+44h], ebp
0x1400047bd  mov     rax, [rsp+78h+arg_20]
0x1400047c5  mov     [rbx+28h], rax
0x1400047c9  mov     [rbx+30h], r12
0x1400047cd  mov     rax, [rsp+78h+arg_28]
0x1400047d5  mov     [rbx+88h], rax
0x1400047dc  mov     rax, [rsp+78h+arg_0]
0x1400047e4  mov     [rbx+90h], rax
0x1400047eb  mov     [rbx+48h], rdi
0x1400047ef  xorps   xmm0, xmm0
0x1400047f2  xor     eax, eax
0x1400047f4  movups  xmmword ptr [rbx+68h], xmm0
0x1400047f8  mov     [rbx+78h], rax
0x1400047fc  movups  xmmword ptr [rbx+50h], xmm0
0x140004800  mov     [rbx+60h], rax
0x140004804  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000480b  test    rax, rax
0x14000480e  jz      short loc_140004817
0x140004810  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004815  jmp     short loc_14000481A
0x140004817  mov     rax, rdi
0x14000481a  mov     [rbx+80h], rax
0x140004821  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004828  test    rax, rax
0x14000482b  jz      short loc_140004835
0x14000482d  mov     rcx, rbx
0x140004830  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004835  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000483c  test    rax, rax
0x14000483f  jz      short loc_140004857
0x140004841  mov     r8d, 400h
0x140004847  mov     rdx, [rsp+78h+arg_60]
0x14000484f  mov     rcx, rbx
0x140004852  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004857  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000485e  test    rax, rax
0x140004861  jz      short loc_14000486B
0x140004863  mov     rcx, rbx
0x140004866  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000486b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004872  test    rax, rax
0x140004875  jz      short loc_140004885
0x140004877  test    byte ptr [rbx+4], 2
0x14000487b  jnz     short loc_140004885
0x14000487d  mov     rcx, rbx
0x140004880  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004885  cmp     [rbx+8], edi
0x140004888  jl      short loc_1400048A4
0x14000488a  cmp     r15d, 3
0x14000488e  jnz     loc_140004973
0x140004894  mov     ecx, 8000FFFFh; this
0x140004899  mov     [rbx+8], ecx
0x14000489c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400048a1  mov     [rbx+0Ch], eax
0x1400048a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400048ab  jnz     short loc_1400048CC
0x1400048ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400048b4  test    rax, rax
0x1400048b7  jz      short loc_1400048C2
0x1400048b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048be  test    al, al
0x1400048c0  jmp     short loc_1400048CA
0x1400048c2  call    cs:__imp_IsDebuggerPresent
0x1400048c8  test    eax, eax
0x1400048ca  jz      short loc_1400048D2
0x1400048cc  test    byte ptr [rbx+4], 2
0x1400048d0  jz      short loc_1400048F6
0x1400048d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400048d9  test    rax, rax
0x1400048dc  jz      short loc_14000493A
0x1400048de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400048e5  jnz     short loc_14000493A
0x1400048e7  xor     r8d, r8d
0x1400048ea  xor     edx, edx
0x1400048ec  mov     rcx, rbx
0x1400048ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400048f4  jmp     short loc_14000493A
0x1400048f6  mov     ebp, 800h
0x1400048fb  mov     rax, cs:g_pfnResultLoggingCallback
0x140004902  test    rax, rax
0x140004905  jz      short loc_14000491E
0x140004907  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000490e  jnz     short loc_14000491E
0x140004910  mov     r8d, ebp
0x140004913  mov     rdx, rsi
0x140004916  mov     rcx, rbx
0x140004919  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000491e  cmp     [rsi], di
0x140004921  jnz     short loc_140004931
0x140004923  mov     r8, rbx; unsigned __int64
0x140004926  mov     rdx, rbp; unsigned __int16 *
0x140004929  mov     rcx, rsi; this
0x14000492c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004931  mov     rcx, rsi; lpOutputString
0x140004934  call    cs:__imp_OutputDebugStringW
0x14000493a  test    byte ptr [rbx+4], 4
0x14000493e  jnz     short loc_140004949
0x140004940  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004947  jz      short loc_14000495B
0x140004949  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004950  test    rax, rax
0x140004953  jz      short loc_14000495B
0x140004955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000495a  nop
0x14000495b  mov     rbx, [rsp+78h+arg_10]
0x140004963  add     rsp, 40h
0x140004967  pop     r15
0x140004969  pop     r14
0x14000496b  pop     r13
0x14000496d  pop     r12
0x14000496f  pop     rdi
0x140004970  pop     rsi
0x140004971  pop     rbp
0x140004972  retn
0x140004973  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
