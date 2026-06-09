# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000771c`
- end: `0x140007a15`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002c48`

## callees

- `0x140002684`
- `0x14000623c`
- `0x140006cec`
- `0x14000771c`
- `0x140008600`
- `0x140008620`
- `0x14000874c`
- `0x140008768`
- `0x14000b51c`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000783f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000783f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400079d0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1400079d0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000795e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000795e`

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
0x14000771c  mov     [rsp+arg_10], rbx
0x140007721  mov     [rsp+arg_8], edx
0x140007725  mov     [rsp+arg_0], rcx
0x14000772a  push    rbp
0x14000772b  push    rsi
0x14000772c  push    rdi
0x14000772d  push    r12
0x14000772f  push    r13
0x140007731  push    r14
0x140007733  push    r15
0x140007735  sub     rsp, 40h
0x140007739  mov     r12, r9
0x14000773c  mov     r13, r8
0x14000773f  mov     r10, rcx
0x140007742  xor     eax, eax
0x140007744  mov     rsi, [rsp+78h+lpOutputString]
0x14000774c  mov     [rsi], ax
0x14000774f  mov     rax, [rsp+78h+arg_60]
0x140007757  mov     byte ptr [rax], 0
0x14000775a  mov     r14, [rsp+78h+arg_38]
0x140007762  mov     edi, [r14]
0x140007765  mov     rbx, [rsp+78h+arg_78]
0x14000776d  mov     [rbx+8], edi
0x140007770  mov     eax, [r14+4]
0x140007774  mov     [rbx+0Ch], eax
0x140007777  xor     ebp, ebp
0x140007779  mov     r15d, [rsp+78h+arg_30]
0x140007781  mov     ecx, r15d
0x140007784  test    r15d, r15d
0x140007787  jz      short loc_1400077EF
0x140007789  sub     ecx, 1
0x14000778c  jz      short loc_1400077E6
0x14000778e  sub     ecx, 1
0x140007791  jz      short loc_1400077A1
0x140007793  cmp     ecx, 1
0x140007796  jnz     short loc_1400077F8
0x140007798  mov     ecx, edi; this
0x14000779a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000779f  jmp     short loc_1400077F6
0x1400077a1  test    edi, edi
0x1400077a3  js      short loc_1400077DD
0x1400077a5  mov     edi, 8007029Ch
0x1400077aa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400077ae  mov     rax, [rsp+78h+arg_28]
0x1400077b6  mov     [rsp+78h+var_50], rax; __int64
0x1400077bb  mov     rax, [rsp+78h+arg_20]
0x1400077c3  mov     [rsp+78h+var_58], rax; __int64
0x1400077c8  mov     rcx, r10; int
0x1400077cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400077d0  mov     [rbx+8], edi
0x1400077d3  mov     ecx, edi; this
0x1400077d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400077da  mov     [rbx+0Ch], eax
0x1400077dd  mov     ecx, edi; this
0x1400077df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400077e4  jmp     short loc_1400077F6
0x1400077e6  mov     ecx, edi; this
0x1400077e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400077ed  jmp     short loc_1400077F6
0x1400077ef  mov     ecx, edi; this
0x1400077f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400077f6  mov     ebp, eax
0x1400077f8  mov     [rbx], r15d
0x1400077fb  mov     eax, [rsp+78h+arg_70]
0x140007802  mov     [rbx+4], eax
0x140007805  cmp     dword ptr [r14+8], 1
0x14000780a  jnz     short loc_140007812
0x14000780c  or      eax, 8
0x14000780f  mov     [rbx+4], eax
0x140007812  mov     eax, 1
0x140007817  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000781f  inc     eax
0x140007821  mov     [rbx+10h], eax
0x140007824  mov     rax, [rsp+78h+arg_40]
0x14000782c  xor     edi, edi
0x14000782e  test    rax, rax
0x140007831  jz      short loc_140007838
0x140007833  cmp     [rax], di
0x140007836  jnz     short loc_14000783B
0x140007838  mov     rax, rdi
0x14000783b  mov     [rbx+18h], rax
0x14000783f  call    cs:__imp_GetCurrentThreadId
0x140007845  mov     [rbx+20h], eax
0x140007848  mov     [rbx+38h], r13
0x14000784c  mov     eax, [rsp+78h+arg_8]
0x140007853  mov     [rbx+40h], eax
0x140007856  mov     [rbx+44h], ebp
0x140007859  mov     rax, [rsp+78h+arg_20]
0x140007861  mov     [rbx+28h], rax
0x140007865  mov     [rbx+30h], r12
0x140007869  mov     rax, [rsp+78h+arg_28]
0x140007871  mov     [rbx+88h], rax
0x140007878  mov     rax, [rsp+78h+arg_0]
0x140007880  mov     [rbx+90h], rax
0x140007887  mov     [rbx+48h], rdi
0x14000788b  xorps   xmm0, xmm0
0x14000788e  xor     eax, eax
0x140007890  movups  xmmword ptr [rbx+68h], xmm0
0x140007894  mov     [rbx+78h], rax
0x140007898  movups  xmmword ptr [rbx+50h], xmm0
0x14000789c  mov     [rbx+60h], rax
0x1400078a0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400078a7  test    rax, rax
0x1400078aa  jz      short loc_1400078B3
0x1400078ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078b1  jmp     short loc_1400078B6
0x1400078b3  mov     rax, rdi
0x1400078b6  mov     [rbx+80h], rax
0x1400078bd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400078c4  test    rax, rax
0x1400078c7  jz      short loc_1400078D1
0x1400078c9  mov     rcx, rbx
0x1400078cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078d1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400078d8  test    rax, rax
0x1400078db  jz      short loc_1400078F3
0x1400078dd  mov     r8d, 400h
0x1400078e3  mov     rdx, [rsp+78h+arg_60]
0x1400078eb  mov     rcx, rbx
0x1400078ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400078f3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400078fa  test    rax, rax
0x1400078fd  jz      short loc_140007907
0x1400078ff  mov     rcx, rbx
0x140007902  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007907  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000790e  test    rax, rax
0x140007911  jz      short loc_140007921
0x140007913  test    byte ptr [rbx+4], 2
0x140007917  jnz     short loc_140007921
0x140007919  mov     rcx, rbx
0x14000791c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007921  cmp     [rbx+8], edi
0x140007924  jl      short loc_140007940
0x140007926  cmp     r15d, 3
0x14000792a  jnz     loc_140007A0F
0x140007930  mov     ecx, 8000FFFFh; this
0x140007935  mov     [rbx+8], ecx
0x140007938  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000793d  mov     [rbx+0Ch], eax
0x140007940  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007947  jnz     short loc_140007968
0x140007949  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007950  test    rax, rax
0x140007953  jz      short loc_14000795E
0x140007955  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000795a  test    al, al
0x14000795c  jmp     short loc_140007966
0x14000795e  call    cs:__imp_IsDebuggerPresent
0x140007964  test    eax, eax
0x140007966  jz      short loc_14000796E
0x140007968  test    byte ptr [rbx+4], 2
0x14000796c  jz      short loc_140007992
0x14000796e  mov     rax, cs:g_pfnResultLoggingCallback
0x140007975  test    rax, rax
0x140007978  jz      short loc_1400079D6
0x14000797a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007981  jnz     short loc_1400079D6
0x140007983  xor     r8d, r8d
0x140007986  xor     edx, edx
0x140007988  mov     rcx, rbx
0x14000798b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007990  jmp     short loc_1400079D6
0x140007992  mov     ebp, 800h
0x140007997  mov     rax, cs:g_pfnResultLoggingCallback
0x14000799e  test    rax, rax
0x1400079a1  jz      short loc_1400079BA
0x1400079a3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400079aa  jnz     short loc_1400079BA
0x1400079ac  mov     r8d, ebp
0x1400079af  mov     rdx, rsi
0x1400079b2  mov     rcx, rbx
0x1400079b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079ba  cmp     [rsi], di
0x1400079bd  jnz     short loc_1400079CD
0x1400079bf  mov     r8, rbx; unsigned __int64
0x1400079c2  mov     rdx, rbp; unsigned __int16 *
0x1400079c5  mov     rcx, rsi; this
0x1400079c8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400079cd  mov     rcx, rsi; lpOutputString
0x1400079d0  call    cs:__imp_OutputDebugStringW
0x1400079d6  test    byte ptr [rbx+4], 4
0x1400079da  jnz     short loc_1400079E5
0x1400079dc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400079e3  jz      short loc_1400079F7
0x1400079e5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400079ec  test    rax, rax
0x1400079ef  jz      short loc_1400079F7
0x1400079f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400079f6  nop
0x1400079f7  mov     rbx, [rsp+78h+arg_10]
0x1400079ff  add     rsp, 40h
0x140007a03  pop     r15
0x140007a05  pop     r14
0x140007a07  pop     r13
0x140007a09  pop     r12
0x140007a0b  pop     rdi
0x140007a0c  pop     rsi
0x140007a0d  pop     rbp
0x140007a0e  retn
0x140007a0f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
