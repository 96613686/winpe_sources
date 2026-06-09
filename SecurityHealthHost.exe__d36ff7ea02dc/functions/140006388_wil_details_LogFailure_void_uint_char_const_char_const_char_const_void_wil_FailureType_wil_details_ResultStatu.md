# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006388`
- end: `0x140006681`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140005ab0`

## callees

- `0x1400057b8`
- `0x140005d20`
- `0x1400061c4`
- `0x140006388`
- `0x1400066d8`
- `0x140006700`
- `0x140006714`
- `0x140006730`
- `0x1400068ec`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400064ab`
- `KERNEL32!GetCurrentThreadId` at `0x1400064ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000663c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000663c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400065ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400065ca`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x140006388  mov     [rsp+arg_10], rbx
0x14000638d  mov     [rsp+arg_8], edx
0x140006391  mov     [rsp+arg_0], rcx
0x140006396  push    rbp
0x140006397  push    rsi
0x140006398  push    rdi
0x140006399  push    r12
0x14000639b  push    r13
0x14000639d  push    r14
0x14000639f  push    r15
0x1400063a1  sub     rsp, 40h
0x1400063a5  mov     r12, r9
0x1400063a8  mov     r13, r8
0x1400063ab  mov     r10, rcx
0x1400063ae  xor     eax, eax
0x1400063b0  mov     rsi, [rsp+78h+lpOutputString]
0x1400063b8  mov     [rsi], ax
0x1400063bb  mov     rax, [rsp+78h+arg_60]
0x1400063c3  mov     byte ptr [rax], 0
0x1400063c6  mov     r14, [rsp+78h+arg_38]
0x1400063ce  mov     edi, [r14]
0x1400063d1  mov     rbx, [rsp+78h+arg_78]
0x1400063d9  mov     [rbx+8], edi
0x1400063dc  mov     eax, [r14+4]
0x1400063e0  mov     [rbx+0Ch], eax
0x1400063e3  xor     ebp, ebp
0x1400063e5  mov     r15d, [rsp+78h+arg_30]
0x1400063ed  mov     ecx, r15d
0x1400063f0  test    r15d, r15d
0x1400063f3  jz      short loc_14000645B
0x1400063f5  sub     ecx, 1
0x1400063f8  jz      short loc_140006452
0x1400063fa  sub     ecx, 1
0x1400063fd  jz      short loc_14000640D
0x1400063ff  cmp     ecx, 1
0x140006402  jnz     short loc_140006464
0x140006404  mov     ecx, edi; this
0x140006406  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000640b  jmp     short loc_140006462
0x14000640d  test    edi, edi
0x14000640f  js      short loc_140006449
0x140006411  mov     edi, 8007029Ch
0x140006416  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000641a  mov     rax, [rsp+78h+arg_28]
0x140006422  mov     [rsp+78h+var_50], rax; __int64
0x140006427  mov     rax, [rsp+78h+arg_20]
0x14000642f  mov     [rsp+78h+var_58], rax; __int64
0x140006434  mov     rcx, r10; int
0x140006437  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000643c  mov     [rbx+8], edi
0x14000643f  mov     ecx, edi; this
0x140006441  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006446  mov     [rbx+0Ch], eax
0x140006449  mov     ecx, edi; this
0x14000644b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006450  jmp     short loc_140006462
0x140006452  mov     ecx, edi; this
0x140006454  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006459  jmp     short loc_140006462
0x14000645b  mov     ecx, edi; this
0x14000645d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006462  mov     ebp, eax
0x140006464  mov     [rbx], r15d
0x140006467  mov     eax, [rsp+78h+arg_70]
0x14000646e  mov     [rbx+4], eax
0x140006471  cmp     dword ptr [r14+8], 1
0x140006476  jnz     short loc_14000647E
0x140006478  or      eax, 8
0x14000647b  mov     [rbx+4], eax
0x14000647e  mov     eax, 1
0x140006483  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000648b  inc     eax
0x14000648d  mov     [rbx+10h], eax
0x140006490  mov     rax, [rsp+78h+arg_40]
0x140006498  xor     edi, edi
0x14000649a  test    rax, rax
0x14000649d  jz      short loc_1400064A4
0x14000649f  cmp     [rax], di
0x1400064a2  jnz     short loc_1400064A7
0x1400064a4  mov     rax, rdi
0x1400064a7  mov     [rbx+18h], rax
0x1400064ab  call    cs:__imp_GetCurrentThreadId
0x1400064b1  mov     [rbx+20h], eax
0x1400064b4  mov     [rbx+38h], r13
0x1400064b8  mov     eax, [rsp+78h+arg_8]
0x1400064bf  mov     [rbx+40h], eax
0x1400064c2  mov     [rbx+44h], ebp
0x1400064c5  mov     rax, [rsp+78h+arg_20]
0x1400064cd  mov     [rbx+28h], rax
0x1400064d1  mov     [rbx+30h], r12
0x1400064d5  mov     rax, [rsp+78h+arg_28]
0x1400064dd  mov     [rbx+88h], rax
0x1400064e4  mov     rax, [rsp+78h+arg_0]
0x1400064ec  mov     [rbx+90h], rax
0x1400064f3  mov     [rbx+48h], rdi
0x1400064f7  xorps   xmm0, xmm0
0x1400064fa  xor     eax, eax
0x1400064fc  movups  xmmword ptr [rbx+68h], xmm0
0x140006500  mov     [rbx+78h], rax
0x140006504  movups  xmmword ptr [rbx+50h], xmm0
0x140006508  mov     [rbx+60h], rax
0x14000650c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006513  test    rax, rax
0x140006516  jz      short loc_14000651F
0x140006518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000651d  jmp     short loc_140006522
0x14000651f  mov     rax, rdi
0x140006522  mov     [rbx+80h], rax
0x140006529  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006530  test    rax, rax
0x140006533  jz      short loc_14000653D
0x140006535  mov     rcx, rbx
0x140006538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000653d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006544  test    rax, rax
0x140006547  jz      short loc_14000655F
0x140006549  mov     r8d, 400h
0x14000654f  mov     rdx, [rsp+78h+arg_60]
0x140006557  mov     rcx, rbx
0x14000655a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000655f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006566  test    rax, rax
0x140006569  jz      short loc_140006573
0x14000656b  mov     rcx, rbx
0x14000656e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006573  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000657a  test    rax, rax
0x14000657d  jz      short loc_14000658D
0x14000657f  test    byte ptr [rbx+4], 2
0x140006583  jnz     short loc_14000658D
0x140006585  mov     rcx, rbx
0x140006588  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000658d  cmp     [rbx+8], edi
0x140006590  jl      short loc_1400065AC
0x140006592  cmp     r15d, 3
0x140006596  jnz     loc_14000667B
0x14000659c  mov     ecx, 8000FFFFh; this
0x1400065a1  mov     [rbx+8], ecx
0x1400065a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400065a9  mov     [rbx+0Ch], eax
0x1400065ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400065b3  jnz     short loc_1400065D4
0x1400065b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400065bc  test    rax, rax
0x1400065bf  jz      short loc_1400065CA
0x1400065c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065c6  test    al, al
0x1400065c8  jmp     short loc_1400065D2
0x1400065ca  call    cs:__imp_IsDebuggerPresent
0x1400065d0  test    eax, eax
0x1400065d2  jz      short loc_1400065DA
0x1400065d4  test    byte ptr [rbx+4], 2
0x1400065d8  jz      short loc_1400065FE
0x1400065da  mov     rax, cs:g_pfnResultLoggingCallback
0x1400065e1  test    rax, rax
0x1400065e4  jz      short loc_140006642
0x1400065e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400065ed  jnz     short loc_140006642
0x1400065ef  xor     r8d, r8d
0x1400065f2  xor     edx, edx
0x1400065f4  mov     rcx, rbx
0x1400065f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065fc  jmp     short loc_140006642
0x1400065fe  mov     ebp, 800h
0x140006603  mov     rax, cs:g_pfnResultLoggingCallback
0x14000660a  test    rax, rax
0x14000660d  jz      short loc_140006626
0x14000660f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006616  jnz     short loc_140006626
0x140006618  mov     r8d, ebp
0x14000661b  mov     rdx, rsi
0x14000661e  mov     rcx, rbx
0x140006621  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006626  cmp     [rsi], di
0x140006629  jnz     short loc_140006639
0x14000662b  mov     r8, rbx; unsigned __int64
0x14000662e  mov     rdx, rbp; unsigned __int16 *
0x140006631  mov     rcx, rsi; this
0x140006634  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006639  mov     rcx, rsi; lpOutputString
0x14000663c  call    cs:__imp_OutputDebugStringW
0x140006642  test    byte ptr [rbx+4], 4
0x140006646  jnz     short loc_140006651
0x140006648  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000664f  jz      short loc_140006663
0x140006651  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006658  test    rax, rax
0x14000665b  jz      short loc_140006663
0x14000665d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006662  nop
0x140006663  mov     rbx, [rsp+78h+arg_10]
0x14000666b  add     rsp, 40h
0x14000666f  pop     r15
0x140006671  pop     r14
0x140006673  pop     r13
0x140006675  pop     r12
0x140006677  pop     rdi
0x140006678  pop     rsi
0x140006679  pop     rbp
0x14000667a  retn
0x14000667b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
