# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000846c`
- end: `0x180008765`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000667c`
- `0x1800069c0`
- `0x18003dbc0`

## callees

- `0x1800065bc`
- `0x1800079f4`
- `0x180008238`
- `0x18000846c`
- `0x180008db8`
- `0x180008de0`
- `0x180008df4`
- `0x180008e10`
- `0x18000a378`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000858f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000858f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800086ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800086ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008720`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008720`

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
0x18000846c  mov     [rsp+arg_10], rbx
0x180008471  mov     [rsp+arg_8], edx
0x180008475  mov     [rsp+arg_0], rcx
0x18000847a  push    rbp
0x18000847b  push    rsi
0x18000847c  push    rdi
0x18000847d  push    r12
0x18000847f  push    r13
0x180008481  push    r14
0x180008483  push    r15
0x180008485  sub     rsp, 40h
0x180008489  mov     r12, r9
0x18000848c  mov     r13, r8
0x18000848f  mov     r10, rcx
0x180008492  xor     eax, eax
0x180008494  mov     rsi, [rsp+78h+lpOutputString]
0x18000849c  mov     [rsi], ax
0x18000849f  mov     rax, [rsp+78h+arg_60]
0x1800084a7  mov     byte ptr [rax], 0
0x1800084aa  mov     r14, [rsp+78h+arg_38]
0x1800084b2  mov     edi, [r14]
0x1800084b5  mov     rbx, [rsp+78h+arg_78]
0x1800084bd  mov     [rbx+8], edi
0x1800084c0  mov     eax, [r14+4]
0x1800084c4  mov     [rbx+0Ch], eax
0x1800084c7  xor     ebp, ebp
0x1800084c9  mov     r15d, [rsp+78h+arg_30]
0x1800084d1  mov     ecx, r15d
0x1800084d4  test    r15d, r15d
0x1800084d7  jz      short loc_18000853F
0x1800084d9  sub     ecx, 1
0x1800084dc  jz      short loc_180008536
0x1800084de  sub     ecx, 1
0x1800084e1  jz      short loc_1800084F1
0x1800084e3  cmp     ecx, 1
0x1800084e6  jnz     short loc_180008548
0x1800084e8  mov     ecx, edi; this
0x1800084ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800084ef  jmp     short loc_180008546
0x1800084f1  test    edi, edi
0x1800084f3  js      short loc_18000852D
0x1800084f5  mov     edi, 8007029Ch
0x1800084fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800084fe  mov     rax, [rsp+78h+arg_28]
0x180008506  mov     [rsp+78h+var_50], rax; __int64
0x18000850b  mov     rax, [rsp+78h+arg_20]
0x180008513  mov     [rsp+78h+var_58], rax; __int64
0x180008518  mov     rcx, r10; int
0x18000851b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008520  mov     [rbx+8], edi
0x180008523  mov     ecx, edi; this
0x180008525  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000852a  mov     [rbx+0Ch], eax
0x18000852d  mov     ecx, edi; this
0x18000852f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008534  jmp     short loc_180008546
0x180008536  mov     ecx, edi; this
0x180008538  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000853d  jmp     short loc_180008546
0x18000853f  mov     ecx, edi; this
0x180008541  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008546  mov     ebp, eax
0x180008548  mov     [rbx], r15d
0x18000854b  mov     eax, [rsp+78h+arg_70]
0x180008552  mov     [rbx+4], eax
0x180008555  cmp     dword ptr [r14+8], 1
0x18000855a  jnz     short loc_180008562
0x18000855c  or      eax, 8
0x18000855f  mov     [rbx+4], eax
0x180008562  mov     eax, 1
0x180008567  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000856f  inc     eax
0x180008571  mov     [rbx+10h], eax
0x180008574  mov     rax, [rsp+78h+arg_40]
0x18000857c  xor     edi, edi
0x18000857e  test    rax, rax
0x180008581  jz      short loc_180008588
0x180008583  cmp     [rax], di
0x180008586  jnz     short loc_18000858B
0x180008588  mov     rax, rdi
0x18000858b  mov     [rbx+18h], rax
0x18000858f  call    cs:__imp_GetCurrentThreadId
0x180008595  mov     [rbx+20h], eax
0x180008598  mov     [rbx+38h], r13
0x18000859c  mov     eax, [rsp+78h+arg_8]
0x1800085a3  mov     [rbx+40h], eax
0x1800085a6  mov     [rbx+44h], ebp
0x1800085a9  mov     rax, [rsp+78h+arg_20]
0x1800085b1  mov     [rbx+28h], rax
0x1800085b5  mov     [rbx+30h], r12
0x1800085b9  mov     rax, [rsp+78h+arg_28]
0x1800085c1  mov     [rbx+88h], rax
0x1800085c8  mov     rax, [rsp+78h+arg_0]
0x1800085d0  mov     [rbx+90h], rax
0x1800085d7  mov     [rbx+48h], rdi
0x1800085db  xorps   xmm0, xmm0
0x1800085de  xor     eax, eax
0x1800085e0  movups  xmmword ptr [rbx+68h], xmm0
0x1800085e4  mov     [rbx+78h], rax
0x1800085e8  movups  xmmword ptr [rbx+50h], xmm0
0x1800085ec  mov     [rbx+60h], rax
0x1800085f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800085f7  test    rax, rax
0x1800085fa  jz      short loc_180008603
0x1800085fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008601  jmp     short loc_180008606
0x180008603  mov     rax, rdi
0x180008606  mov     [rbx+80h], rax
0x18000860d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008614  test    rax, rax
0x180008617  jz      short loc_180008621
0x180008619  mov     rcx, rbx
0x18000861c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008621  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008628  test    rax, rax
0x18000862b  jz      short loc_180008643
0x18000862d  mov     r8d, 400h
0x180008633  mov     rdx, [rsp+78h+arg_60]
0x18000863b  mov     rcx, rbx
0x18000863e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008643  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000864a  test    rax, rax
0x18000864d  jz      short loc_180008657
0x18000864f  mov     rcx, rbx
0x180008652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008657  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000865e  test    rax, rax
0x180008661  jz      short loc_180008671
0x180008663  test    byte ptr [rbx+4], 2
0x180008667  jnz     short loc_180008671
0x180008669  mov     rcx, rbx
0x18000866c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008671  cmp     [rbx+8], edi
0x180008674  jl      short loc_180008690
0x180008676  cmp     r15d, 3
0x18000867a  jnz     loc_18000875F
0x180008680  mov     ecx, 8000FFFFh; this
0x180008685  mov     [rbx+8], ecx
0x180008688  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000868d  mov     [rbx+0Ch], eax
0x180008690  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008697  jnz     short loc_1800086B8
0x180008699  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800086a0  test    rax, rax
0x1800086a3  jz      short loc_1800086AE
0x1800086a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086aa  test    al, al
0x1800086ac  jmp     short loc_1800086B6
0x1800086ae  call    cs:__imp_IsDebuggerPresent
0x1800086b4  test    eax, eax
0x1800086b6  jz      short loc_1800086BE
0x1800086b8  test    byte ptr [rbx+4], 2
0x1800086bc  jz      short loc_1800086E2
0x1800086be  mov     rax, cs:g_pfnResultLoggingCallback
0x1800086c5  test    rax, rax
0x1800086c8  jz      short loc_180008726
0x1800086ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800086d1  jnz     short loc_180008726
0x1800086d3  xor     r8d, r8d
0x1800086d6  xor     edx, edx
0x1800086d8  mov     rcx, rbx
0x1800086db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800086e0  jmp     short loc_180008726
0x1800086e2  mov     ebp, 800h
0x1800086e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800086ee  test    rax, rax
0x1800086f1  jz      short loc_18000870A
0x1800086f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800086fa  jnz     short loc_18000870A
0x1800086fc  mov     r8d, ebp
0x1800086ff  mov     rdx, rsi
0x180008702  mov     rcx, rbx
0x180008705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000870a  cmp     [rsi], di
0x18000870d  jnz     short loc_18000871D
0x18000870f  mov     r8, rbx; unsigned __int64
0x180008712  mov     rdx, rbp; unsigned __int16 *
0x180008715  mov     rcx, rsi; this
0x180008718  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000871d  mov     rcx, rsi; lpOutputString
0x180008720  call    cs:__imp_OutputDebugStringW
0x180008726  test    byte ptr [rbx+4], 4
0x18000872a  jnz     short loc_180008735
0x18000872c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008733  jz      short loc_180008747
0x180008735  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000873c  test    rax, rax
0x18000873f  jz      short loc_180008747
0x180008741  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008746  nop
0x180008747  mov     rbx, [rsp+78h+arg_10]
0x18000874f  add     rsp, 40h
0x180008753  pop     r15
0x180008755  pop     r14
0x180008757  pop     r13
0x180008759  pop     r12
0x18000875b  pop     rdi
0x18000875c  pop     rsi
0x18000875d  pop     rbp
0x18000875e  retn
0x18000875f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
