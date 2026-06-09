# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006430`
- end: `0x180006729`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003848`

## callees

- `0x18000328c`
- `0x180005954`
- `0x1800060fc`
- `0x180006430`
- `0x180006da8`
- `0x180006dd0`
- `0x180006de4`
- `0x180006e00`
- `0x180009004`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006553`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006553`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800066e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800066e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006672`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006672`

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
0x180006430  mov     [rsp+arg_10], rbx
0x180006435  mov     [rsp+arg_8], edx
0x180006439  mov     [rsp+arg_0], rcx
0x18000643e  push    rbp
0x18000643f  push    rsi
0x180006440  push    rdi
0x180006441  push    r12
0x180006443  push    r13
0x180006445  push    r14
0x180006447  push    r15
0x180006449  sub     rsp, 40h
0x18000644d  mov     r12, r9
0x180006450  mov     r13, r8
0x180006453  mov     r10, rcx
0x180006456  xor     eax, eax
0x180006458  mov     rsi, [rsp+78h+lpOutputString]
0x180006460  mov     [rsi], ax
0x180006463  mov     rax, [rsp+78h+arg_60]
0x18000646b  mov     byte ptr [rax], 0
0x18000646e  mov     r14, [rsp+78h+arg_38]
0x180006476  mov     edi, [r14]
0x180006479  mov     rbx, [rsp+78h+arg_78]
0x180006481  mov     [rbx+8], edi
0x180006484  mov     eax, [r14+4]
0x180006488  mov     [rbx+0Ch], eax
0x18000648b  xor     ebp, ebp
0x18000648d  mov     r15d, [rsp+78h+arg_30]
0x180006495  mov     ecx, r15d
0x180006498  test    r15d, r15d
0x18000649b  jz      short loc_180006503
0x18000649d  sub     ecx, 1
0x1800064a0  jz      short loc_1800064FA
0x1800064a2  sub     ecx, 1
0x1800064a5  jz      short loc_1800064B5
0x1800064a7  cmp     ecx, 1
0x1800064aa  jnz     short loc_18000650C
0x1800064ac  mov     ecx, edi; this
0x1800064ae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800064b3  jmp     short loc_18000650A
0x1800064b5  test    edi, edi
0x1800064b7  js      short loc_1800064F1
0x1800064b9  mov     edi, 8007029Ch
0x1800064be  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800064c2  mov     rax, [rsp+78h+arg_28]
0x1800064ca  mov     [rsp+78h+var_50], rax; __int64
0x1800064cf  mov     rax, [rsp+78h+arg_20]
0x1800064d7  mov     [rsp+78h+var_58], rax; __int64
0x1800064dc  mov     rcx, r10; int
0x1800064df  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800064e4  mov     [rbx+8], edi
0x1800064e7  mov     ecx, edi; this
0x1800064e9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800064ee  mov     [rbx+0Ch], eax
0x1800064f1  mov     ecx, edi; this
0x1800064f3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800064f8  jmp     short loc_18000650A
0x1800064fa  mov     ecx, edi; this
0x1800064fc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006501  jmp     short loc_18000650A
0x180006503  mov     ecx, edi; this
0x180006505  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000650a  mov     ebp, eax
0x18000650c  mov     [rbx], r15d
0x18000650f  mov     eax, [rsp+78h+arg_70]
0x180006516  mov     [rbx+4], eax
0x180006519  cmp     dword ptr [r14+8], 1
0x18000651e  jnz     short loc_180006526
0x180006520  or      eax, 8
0x180006523  mov     [rbx+4], eax
0x180006526  mov     eax, 1
0x18000652b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006533  inc     eax
0x180006535  mov     [rbx+10h], eax
0x180006538  mov     rax, [rsp+78h+arg_40]
0x180006540  xor     edi, edi
0x180006542  test    rax, rax
0x180006545  jz      short loc_18000654C
0x180006547  cmp     [rax], di
0x18000654a  jnz     short loc_18000654F
0x18000654c  mov     rax, rdi
0x18000654f  mov     [rbx+18h], rax
0x180006553  call    cs:__imp_GetCurrentThreadId
0x180006559  mov     [rbx+20h], eax
0x18000655c  mov     [rbx+38h], r13
0x180006560  mov     eax, [rsp+78h+arg_8]
0x180006567  mov     [rbx+40h], eax
0x18000656a  mov     [rbx+44h], ebp
0x18000656d  mov     rax, [rsp+78h+arg_20]
0x180006575  mov     [rbx+28h], rax
0x180006579  mov     [rbx+30h], r12
0x18000657d  mov     rax, [rsp+78h+arg_28]
0x180006585  mov     [rbx+88h], rax
0x18000658c  mov     rax, [rsp+78h+arg_0]
0x180006594  mov     [rbx+90h], rax
0x18000659b  mov     [rbx+48h], rdi
0x18000659f  xorps   xmm0, xmm0
0x1800065a2  xor     eax, eax
0x1800065a4  movups  xmmword ptr [rbx+68h], xmm0
0x1800065a8  mov     [rbx+78h], rax
0x1800065ac  movups  xmmword ptr [rbx+50h], xmm0
0x1800065b0  mov     [rbx+60h], rax
0x1800065b4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800065bb  test    rax, rax
0x1800065be  jz      short loc_1800065C7
0x1800065c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065c5  jmp     short loc_1800065CA
0x1800065c7  mov     rax, rdi
0x1800065ca  mov     [rbx+80h], rax
0x1800065d1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800065d8  test    rax, rax
0x1800065db  jz      short loc_1800065E5
0x1800065dd  mov     rcx, rbx
0x1800065e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800065ec  test    rax, rax
0x1800065ef  jz      short loc_180006607
0x1800065f1  mov     r8d, 400h
0x1800065f7  mov     rdx, [rsp+78h+arg_60]
0x1800065ff  mov     rcx, rbx
0x180006602  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006607  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000660e  test    rax, rax
0x180006611  jz      short loc_18000661B
0x180006613  mov     rcx, rbx
0x180006616  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006622  test    rax, rax
0x180006625  jz      short loc_180006635
0x180006627  test    byte ptr [rbx+4], 2
0x18000662b  jnz     short loc_180006635
0x18000662d  mov     rcx, rbx
0x180006630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006635  cmp     [rbx+8], edi
0x180006638  jl      short loc_180006654
0x18000663a  cmp     r15d, 3
0x18000663e  jnz     loc_180006723
0x180006644  mov     ecx, 8000FFFFh; this
0x180006649  mov     [rbx+8], ecx
0x18000664c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006651  mov     [rbx+0Ch], eax
0x180006654  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000665b  jnz     short loc_18000667C
0x18000665d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006664  test    rax, rax
0x180006667  jz      short loc_180006672
0x180006669  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000666e  test    al, al
0x180006670  jmp     short loc_18000667A
0x180006672  call    cs:__imp_IsDebuggerPresent
0x180006678  test    eax, eax
0x18000667a  jz      short loc_180006682
0x18000667c  test    byte ptr [rbx+4], 2
0x180006680  jz      short loc_1800066A6
0x180006682  mov     rax, cs:g_pfnResultLoggingCallback
0x180006689  test    rax, rax
0x18000668c  jz      short loc_1800066EA
0x18000668e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006695  jnz     short loc_1800066EA
0x180006697  xor     r8d, r8d
0x18000669a  xor     edx, edx
0x18000669c  mov     rcx, rbx
0x18000669f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a4  jmp     short loc_1800066EA
0x1800066a6  mov     ebp, 800h
0x1800066ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066b2  test    rax, rax
0x1800066b5  jz      short loc_1800066CE
0x1800066b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800066be  jnz     short loc_1800066CE
0x1800066c0  mov     r8d, ebp
0x1800066c3  mov     rdx, rsi
0x1800066c6  mov     rcx, rbx
0x1800066c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066ce  cmp     [rsi], di
0x1800066d1  jnz     short loc_1800066E1
0x1800066d3  mov     r8, rbx; unsigned __int64
0x1800066d6  mov     rdx, rbp; unsigned __int16 *
0x1800066d9  mov     rcx, rsi; this
0x1800066dc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800066e1  mov     rcx, rsi; lpOutputString
0x1800066e4  call    cs:__imp_OutputDebugStringW
0x1800066ea  test    byte ptr [rbx+4], 4
0x1800066ee  jnz     short loc_1800066F9
0x1800066f0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800066f7  jz      short loc_18000670B
0x1800066f9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006700  test    rax, rax
0x180006703  jz      short loc_18000670B
0x180006705  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000670a  nop
0x18000670b  mov     rbx, [rsp+78h+arg_10]
0x180006713  add     rsp, 40h
0x180006717  pop     r15
0x180006719  pop     r14
0x18000671b  pop     r13
0x18000671d  pop     r12
0x18000671f  pop     rdi
0x180006720  pop     rsi
0x180006721  pop     rbp
0x180006722  retn
0x180006723  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
