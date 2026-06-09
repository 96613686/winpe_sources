# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003740`
- end: `0x140003a38`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000227c`

## callees

- `0x140001cb8`
- `0x140002de4`
- `0x14000357c`
- `0x140003740`
- `0x140003c7c`
- `0x140003ca0`
- `0x140003cb4`
- `0x140003cd0`
- `0x14000492c`
- `0x140005010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140003863`
- `KERNEL32!GetCurrentThreadId` at `0x140003863`
- `KERNEL32!IsDebuggerPresent` at `0x140003982`
- `KERNEL32!IsDebuggerPresent` at `0x140003982`
- `KERNEL32!OutputDebugStringW` at `0x1400039f4`
- `KERNEL32!OutputDebugStringW` at `0x1400039f4`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x140003740  mov     [rsp+arg_10], rbx
0x140003745  mov     [rsp+arg_8], edx
0x140003749  mov     [rsp+arg_0], rcx
0x14000374e  push    rbp
0x14000374f  push    rsi
0x140003750  push    rdi
0x140003751  push    r12
0x140003753  push    r13
0x140003755  push    r14
0x140003757  push    r15
0x140003759  sub     rsp, 40h
0x14000375d  mov     r14, [rsp+78h+arg_38]
0x140003765  xor     eax, eax
0x140003767  mov     rbx, [rsp+78h+arg_78]
0x14000376f  xor     ebp, ebp
0x140003771  mov     r15d, [rsp+78h+arg_30]
0x140003779  mov     r10, rcx
0x14000377c  mov     rsi, [rsp+78h+lpOutputString]
0x140003784  mov     r12, r9
0x140003787  mov     r13, r8
0x14000378a  mov     ecx, r15d
0x14000378d  mov     [rsi], ax
0x140003790  mov     rax, [rsp+78h+arg_60]
0x140003798  mov     byte ptr [rax], 0
0x14000379b  mov     edi, [r14]
0x14000379e  mov     [rbx+8], edi
0x1400037a1  mov     eax, [r14+4]
0x1400037a5  mov     [rbx+0Ch], eax
0x1400037a8  test    r15d, r15d
0x1400037ab  jz      short loc_140003813
0x1400037ad  sub     ecx, 1
0x1400037b0  jz      short loc_14000380A
0x1400037b2  sub     ecx, 1
0x1400037b5  jz      short loc_1400037C5
0x1400037b7  cmp     ecx, 1
0x1400037ba  jnz     short loc_14000381C
0x1400037bc  mov     ecx, edi; this
0x1400037be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400037c3  jmp     short loc_14000381A
0x1400037c5  test    edi, edi
0x1400037c7  js      short loc_140003801
0x1400037c9  mov     rax, [rsp+78h+arg_28]
0x1400037d1  mov     edi, 8007029Ch
0x1400037d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400037da  mov     rcx, r10; int
0x1400037dd  mov     [rsp+78h+var_50], rax; __int64
0x1400037e2  mov     rax, [rsp+78h+arg_20]
0x1400037ea  mov     [rsp+78h+var_58], rax; __int64
0x1400037ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400037f4  mov     ecx, edi; this
0x1400037f6  mov     [rbx+8], edi
0x1400037f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400037fe  mov     [rbx+0Ch], eax
0x140003801  mov     ecx, edi; this
0x140003803  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140003808  jmp     short loc_14000381A
0x14000380a  mov     ecx, edi; this
0x14000380c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140003811  jmp     short loc_14000381A
0x140003813  mov     ecx, edi; this
0x140003815  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000381a  mov     ebp, eax
0x14000381c  mov     eax, [rsp+78h+arg_70]
0x140003823  mov     [rbx+4], eax
0x140003826  mov     [rbx], r15d
0x140003829  cmp     dword ptr [r14+8], 1
0x14000382e  jnz     short loc_140003836
0x140003830  or      eax, 8
0x140003833  mov     [rbx+4], eax
0x140003836  mov     eax, 1
0x14000383b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003843  inc     eax
0x140003845  xor     edi, edi
0x140003847  mov     [rbx+10h], eax
0x14000384a  mov     rax, [rsp+78h+arg_40]
0x140003852  test    rax, rax
0x140003855  jz      short loc_14000385C
0x140003857  cmp     [rax], di
0x14000385a  jnz     short loc_14000385F
0x14000385c  mov     rax, rdi
0x14000385f  mov     [rbx+18h], rax
0x140003863  call    cs:__imp_GetCurrentThreadId
0x140003869  mov     [rbx+38h], r13
0x14000386d  xorps   xmm0, xmm0
0x140003870  mov     [rbx+20h], eax
0x140003873  mov     eax, [rsp+78h+arg_8]
0x14000387a  mov     [rbx+40h], eax
0x14000387d  mov     rax, [rsp+78h+arg_20]
0x140003885  mov     [rbx+28h], rax
0x140003889  mov     rax, [rsp+78h+arg_28]
0x140003891  mov     [rbx+88h], rax
0x140003898  mov     rax, [rsp+78h+arg_0]
0x1400038a0  mov     [rbx+90h], rax
0x1400038a7  xor     eax, eax
0x1400038a9  mov     [rbx+44h], ebp
0x1400038ac  mov     [rbx+30h], r12
0x1400038b0  mov     [rbx+48h], rdi
0x1400038b4  movups  xmmword ptr [rbx+68h], xmm0
0x1400038b8  mov     [rbx+78h], rax
0x1400038bc  movups  xmmword ptr [rbx+50h], xmm0
0x1400038c0  mov     [rbx+60h], rax
0x1400038c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400038cb  test    rax, rax
0x1400038ce  jz      short loc_1400038D7
0x1400038d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038d5  jmp     short loc_1400038DA
0x1400038d7  mov     rax, rdi
0x1400038da  mov     [rbx+80h], rax
0x1400038e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1400038e8  test    rax, rax
0x1400038eb  jz      short loc_1400038F5
0x1400038ed  mov     rcx, rbx
0x1400038f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400038f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400038fc  test    rax, rax
0x1400038ff  jz      short loc_140003917
0x140003901  mov     rdx, [rsp+78h+arg_60]
0x140003909  mov     r8d, 400h
0x14000390f  mov     rcx, rbx
0x140003912  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003917  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000391e  test    rax, rax
0x140003921  jz      short loc_14000392B
0x140003923  mov     rcx, rbx
0x140003926  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000392b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003932  test    rax, rax
0x140003935  jz      short loc_140003945
0x140003937  test    byte ptr [rbx+4], 2
0x14000393b  jnz     short loc_140003945
0x14000393d  mov     rcx, rbx
0x140003940  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003945  cmp     [rbx+8], edi
0x140003948  jl      short loc_140003964
0x14000394a  cmp     r15d, 3
0x14000394e  jnz     loc_140003A32
0x140003954  mov     ecx, 8000FFFFh; this
0x140003959  mov     [rbx+8], ecx
0x14000395c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003961  mov     [rbx+0Ch], eax
0x140003964  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000396b  jnz     short loc_14000398C
0x14000396d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003974  test    rax, rax
0x140003977  jz      short loc_140003982
0x140003979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000397e  test    al, al
0x140003980  jmp     short loc_14000398A
0x140003982  call    cs:__imp_IsDebuggerPresent
0x140003988  test    eax, eax
0x14000398a  jz      short loc_140003992
0x14000398c  test    byte ptr [rbx+4], 2
0x140003990  jz      short loc_1400039B6
0x140003992  mov     rax, cs:g_pfnResultLoggingCallback
0x140003999  test    rax, rax
0x14000399c  jz      short loc_1400039FA
0x14000399e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400039a5  jnz     short loc_1400039FA
0x1400039a7  xor     r8d, r8d
0x1400039aa  xor     edx, edx
0x1400039ac  mov     rcx, rbx
0x1400039af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039b4  jmp     short loc_1400039FA
0x1400039b6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400039bd  mov     ebp, 800h
0x1400039c2  test    rax, rax
0x1400039c5  jz      short loc_1400039DE
0x1400039c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400039ce  jnz     short loc_1400039DE
0x1400039d0  mov     r8d, ebp
0x1400039d3  mov     rdx, rsi
0x1400039d6  mov     rcx, rbx
0x1400039d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400039de  cmp     [rsi], di
0x1400039e1  jnz     short loc_1400039F1
0x1400039e3  mov     r8, rbx; unsigned __int64
0x1400039e6  mov     rdx, rbp; unsigned __int16 *
0x1400039e9  mov     rcx, rsi; this
0x1400039ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1400039f1  mov     rcx, rsi; lpOutputString
0x1400039f4  call    cs:__imp_OutputDebugStringW
0x1400039fa  test    byte ptr [rbx+4], 4
0x1400039fe  jnz     short loc_140003A09
0x140003a00  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140003a07  jz      short loc_140003A1A
0x140003a09  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003a10  test    rax, rax
0x140003a13  jz      short loc_140003A1A
0x140003a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003a1a  mov     rbx, [rsp+78h+arg_10]
0x140003a22  add     rsp, 40h
0x140003a26  pop     r15
0x140003a28  pop     r14
0x140003a2a  pop     r13
0x140003a2c  pop     r12
0x140003a2e  pop     rdi
0x140003a2f  pop     rsi
0x140003a30  pop     rbp
0x140003a31  retn
0x140003a32  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
