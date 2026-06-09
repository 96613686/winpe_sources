# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005502c`
- end: `0x180055337`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: `void __fastcall(__int64, __int64, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180052038`
- `0x180052398`

## callees

- `0x180049648`
- `0x180051f78`
- `0x180054054`
- `0x18005502c`
- `0x180056270`
- `0x180056290`
- `0x18005642c`
- `0x18005644c`
- `0x180057e74`
- `0x180077010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180055274`
- `KERNEL32!IsDebuggerPresent` at `0x180055274`
- `KERNEL32!OutputDebugStringW` at `0x1800552ec`
- `KERNEL32!OutputDebugStringW` at `0x1800552ec`
- `KERNEL32!GetCurrentThreadId` at `0x18005514f`
- `KERNEL32!GetCurrentThreadId` at `0x18005514f`

## pseudocode

```c
void __fastcall wil::details::LogFailure(
        __int64 a1,
        __int64 a2,
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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]
  int v29; // [rsp+88h] [rbp+10h]

  v29 = a2;
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
        v20 = wil::details::RecordReturn((wil::details *)v19);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v19);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = v29;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x18005502c  mov     [rsp+arg_10], rbx
0x180055031  mov     [rsp+arg_8], edx
0x180055035  mov     [rsp+arg_0], rcx
0x18005503a  push    rbp
0x18005503b  push    rsi
0x18005503c  push    rdi
0x18005503d  push    r12
0x18005503f  push    r13
0x180055041  push    r14
0x180055043  push    r15
0x180055045  sub     rsp, 40h
0x180055049  mov     r14, [rsp+78h+arg_38]
0x180055051  xor     eax, eax
0x180055053  mov     rbx, [rsp+78h+arg_78]
0x18005505b  xor     ebp, ebp
0x18005505d  mov     r15d, [rsp+78h+arg_30]
0x180055065  mov     r10, rcx
0x180055068  mov     rsi, [rsp+78h+lpOutputString]
0x180055070  mov     r12, r9
0x180055073  mov     r13, r8
0x180055076  mov     ecx, r15d
0x180055079  mov     [rsi], ax
0x18005507c  mov     rax, [rsp+78h+arg_60]
0x180055084  mov     byte ptr [rax], 0
0x180055087  mov     edi, [r14]
0x18005508a  mov     [rbx+8], edi
0x18005508d  mov     eax, [r14+4]
0x180055091  mov     [rbx+0Ch], eax
0x180055094  test    r15d, r15d
0x180055097  jz      short loc_1800550FF
0x180055099  sub     ecx, 1
0x18005509c  jz      short loc_1800550F6
0x18005509e  sub     ecx, 1
0x1800550a1  jz      short loc_1800550B1
0x1800550a3  cmp     ecx, 1
0x1800550a6  jnz     short loc_180055108
0x1800550a8  mov     ecx, edi; this
0x1800550aa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800550af  jmp     short loc_180055106
0x1800550b1  test    edi, edi
0x1800550b3  js      short loc_1800550ED
0x1800550b5  mov     rax, [rsp+78h+arg_28]
0x1800550bd  mov     edi, 8007029Ch
0x1800550c2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800550c6  mov     rcx, r10; int
0x1800550c9  mov     [rsp+78h+var_50], rax; __int64
0x1800550ce  mov     rax, [rsp+78h+arg_20]
0x1800550d6  mov     [rsp+78h+var_58], rax; __int64
0x1800550db  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800550e0  mov     ecx, edi; this
0x1800550e2  mov     [rbx+8], edi
0x1800550e5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800550ea  mov     [rbx+0Ch], eax
0x1800550ed  mov     ecx, edi; this
0x1800550ef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800550f4  jmp     short loc_180055106
0x1800550f6  mov     ecx, edi; this
0x1800550f8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800550fd  jmp     short loc_180055106
0x1800550ff  mov     ecx, edi; this
0x180055101  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180055106  mov     ebp, eax
0x180055108  mov     eax, [rsp+78h+arg_70]
0x18005510f  mov     [rbx+4], eax
0x180055112  mov     [rbx], r15d
0x180055115  cmp     dword ptr [r14+8], 1
0x18005511a  jnz     short loc_180055122
0x18005511c  or      eax, 8
0x18005511f  mov     [rbx+4], eax
0x180055122  mov     eax, 1
0x180055127  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005512f  inc     eax
0x180055131  xor     edi, edi
0x180055133  mov     [rbx+10h], eax
0x180055136  mov     rax, [rsp+78h+arg_40]
0x18005513e  test    rax, rax
0x180055141  jz      short loc_180055148
0x180055143  cmp     [rax], di
0x180055146  jnz     short loc_18005514B
0x180055148  mov     rax, rdi
0x18005514b  mov     [rbx+18h], rax
0x18005514f  call    cs:__imp_GetCurrentThreadId
0x180055156  nop     dword ptr [rax+rax+00h]
0x18005515b  mov     [rbx+38h], r13
0x18005515f  xorps   xmm0, xmm0
0x180055162  mov     [rbx+20h], eax
0x180055165  mov     eax, [rsp+78h+arg_8]
0x18005516c  mov     [rbx+40h], eax
0x18005516f  mov     rax, [rsp+78h+arg_20]
0x180055177  mov     [rbx+28h], rax
0x18005517b  mov     rax, [rsp+78h+arg_28]
0x180055183  mov     [rbx+88h], rax
0x18005518a  mov     rax, [rsp+78h+arg_0]
0x180055192  mov     [rbx+90h], rax
0x180055199  xor     eax, eax
0x18005519b  mov     [rbx+44h], ebp
0x18005519e  mov     [rbx+30h], r12
0x1800551a2  mov     [rbx+48h], rdi
0x1800551a6  movups  xmmword ptr [rbx+68h], xmm0
0x1800551aa  mov     [rbx+78h], rax
0x1800551ae  movups  xmmword ptr [rbx+50h], xmm0
0x1800551b2  mov     [rbx+60h], rax
0x1800551b6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800551bd  test    rax, rax
0x1800551c0  jz      short loc_1800551C9
0x1800551c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551c7  jmp     short loc_1800551CC
0x1800551c9  mov     rax, rdi
0x1800551cc  mov     [rbx+80h], rax
0x1800551d3  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800551da  test    rax, rax
0x1800551dd  jz      short loc_1800551E7
0x1800551df  mov     rcx, rbx
0x1800551e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800551e7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800551ee  test    rax, rax
0x1800551f1  jz      short loc_180055209
0x1800551f3  mov     rdx, [rsp+78h+arg_60]
0x1800551fb  mov     r8d, 400h
0x180055201  mov     rcx, rbx
0x180055204  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055209  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180055210  test    rax, rax
0x180055213  jz      short loc_18005521D
0x180055215  mov     rcx, rbx
0x180055218  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005521d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180055224  test    rax, rax
0x180055227  jz      short loc_180055237
0x180055229  test    byte ptr [rbx+4], 2
0x18005522d  jnz     short loc_180055237
0x18005522f  mov     rcx, rbx
0x180055232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055237  cmp     [rbx+8], edi
0x18005523a  jl      short loc_180055256
0x18005523c  cmp     r15d, 3
0x180055240  jnz     loc_180055331
0x180055246  mov     ecx, 8000FFFFh; this
0x18005524b  mov     [rbx+8], ecx
0x18005524e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180055253  mov     [rbx+0Ch], eax
0x180055256  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005525d  jnz     short loc_180055284
0x18005525f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180055266  test    rax, rax
0x180055269  jz      short loc_180055274
0x18005526b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055270  test    al, al
0x180055272  jmp     short loc_180055282
0x180055274  call    cs:__imp_IsDebuggerPresent
0x18005527b  nop     dword ptr [rax+rax+00h]
0x180055280  test    eax, eax
0x180055282  jz      short loc_18005528A
0x180055284  test    byte ptr [rbx+4], 2
0x180055288  jz      short loc_1800552AE
0x18005528a  mov     rax, cs:g_pfnResultLoggingCallback
0x180055291  test    rax, rax
0x180055294  jz      short loc_1800552F8
0x180055296  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005529d  jnz     short loc_1800552F8
0x18005529f  xor     r8d, r8d
0x1800552a2  xor     edx, edx
0x1800552a4  mov     rcx, rbx
0x1800552a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552ac  jmp     short loc_1800552F8
0x1800552ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800552b5  mov     ebp, 800h
0x1800552ba  test    rax, rax
0x1800552bd  jz      short loc_1800552D6
0x1800552bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800552c6  jnz     short loc_1800552D6
0x1800552c8  mov     r8d, ebp
0x1800552cb  mov     rdx, rsi
0x1800552ce  mov     rcx, rbx
0x1800552d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800552d6  cmp     [rsi], di
0x1800552d9  jnz     short loc_1800552E9
0x1800552db  mov     r8, rbx; unsigned __int64
0x1800552de  mov     rdx, rbp; unsigned __int16 *
0x1800552e1  mov     rcx, rsi; this
0x1800552e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800552e9  mov     rcx, rsi; lpOutputString
0x1800552ec  call    cs:__imp_OutputDebugStringW
0x1800552f3  nop     dword ptr [rax+rax+00h]
0x1800552f8  test    byte ptr [rbx+4], 4
0x1800552fc  jnz     short loc_180055307
0x1800552fe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180055305  jz      short loc_180055318
0x180055307  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005530e  test    rax, rax
0x180055311  jz      short loc_180055318
0x180055313  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180055318  mov     rbx, [rsp+78h+arg_10]
0x180055320  add     rsp, 40h
0x180055324  pop     r15
0x180055326  pop     r14
0x180055328  pop     r13
0x18005532a  pop     r12
0x18005532c  pop     rdi
0x18005532d  pop     rsi
0x18005532e  pop     rbp
0x18005532f  retn
0x180055331  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
