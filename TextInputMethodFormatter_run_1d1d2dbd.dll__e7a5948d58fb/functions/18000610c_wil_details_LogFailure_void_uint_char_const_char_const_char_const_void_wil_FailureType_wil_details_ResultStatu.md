# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000610c`
- end: `0x180006405`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003d00`

## callees

- `0x18000370c`
- `0x1800054d4`
- `0x180005f24`
- `0x18000610c`
- `0x180006750`
- `0x180006770`
- `0x180006784`
- `0x1800067a0`
- `0x180007a48`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000622f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000622f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800063c0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800063c0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000634e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000634e`

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
0x18000610c  mov     [rsp+arg_10], rbx
0x180006111  mov     [rsp+arg_8], edx
0x180006115  mov     [rsp+arg_0], rcx
0x18000611a  push    rbp
0x18000611b  push    rsi
0x18000611c  push    rdi
0x18000611d  push    r12
0x18000611f  push    r13
0x180006121  push    r14
0x180006123  push    r15
0x180006125  sub     rsp, 40h
0x180006129  mov     r12, r9
0x18000612c  mov     r13, r8
0x18000612f  mov     r10, rcx
0x180006132  xor     eax, eax
0x180006134  mov     rsi, [rsp+78h+lpOutputString]
0x18000613c  mov     [rsi], ax
0x18000613f  mov     rax, [rsp+78h+arg_60]
0x180006147  mov     byte ptr [rax], 0
0x18000614a  mov     r14, [rsp+78h+arg_38]
0x180006152  mov     edi, [r14]
0x180006155  mov     rbx, [rsp+78h+arg_78]
0x18000615d  mov     [rbx+8], edi
0x180006160  mov     eax, [r14+4]
0x180006164  mov     [rbx+0Ch], eax
0x180006167  xor     ebp, ebp
0x180006169  mov     r15d, [rsp+78h+arg_30]
0x180006171  mov     ecx, r15d
0x180006174  test    r15d, r15d
0x180006177  jz      short loc_1800061DF
0x180006179  sub     ecx, 1
0x18000617c  jz      short loc_1800061D6
0x18000617e  sub     ecx, 1
0x180006181  jz      short loc_180006191
0x180006183  cmp     ecx, 1
0x180006186  jnz     short loc_1800061E8
0x180006188  mov     ecx, edi; this
0x18000618a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000618f  jmp     short loc_1800061E6
0x180006191  test    edi, edi
0x180006193  js      short loc_1800061CD
0x180006195  mov     edi, 8007029Ch
0x18000619a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000619e  mov     rax, [rsp+78h+arg_28]
0x1800061a6  mov     [rsp+78h+var_50], rax; __int64
0x1800061ab  mov     rax, [rsp+78h+arg_20]
0x1800061b3  mov     [rsp+78h+var_58], rax; __int64
0x1800061b8  mov     rcx, r10; int
0x1800061bb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800061c0  mov     [rbx+8], edi
0x1800061c3  mov     ecx, edi; this
0x1800061c5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800061ca  mov     [rbx+0Ch], eax
0x1800061cd  mov     ecx, edi; this
0x1800061cf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800061d4  jmp     short loc_1800061E6
0x1800061d6  mov     ecx, edi; this
0x1800061d8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800061dd  jmp     short loc_1800061E6
0x1800061df  mov     ecx, edi; this
0x1800061e1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800061e6  mov     ebp, eax
0x1800061e8  mov     [rbx], r15d
0x1800061eb  mov     eax, [rsp+78h+arg_70]
0x1800061f2  mov     [rbx+4], eax
0x1800061f5  cmp     dword ptr [r14+8], 1
0x1800061fa  jnz     short loc_180006202
0x1800061fc  or      eax, 8
0x1800061ff  mov     [rbx+4], eax
0x180006202  mov     eax, 1
0x180006207  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000620f  inc     eax
0x180006211  mov     [rbx+10h], eax
0x180006214  mov     rax, [rsp+78h+arg_40]
0x18000621c  xor     edi, edi
0x18000621e  test    rax, rax
0x180006221  jz      short loc_180006228
0x180006223  cmp     [rax], di
0x180006226  jnz     short loc_18000622B
0x180006228  mov     rax, rdi
0x18000622b  mov     [rbx+18h], rax
0x18000622f  call    cs:__imp_GetCurrentThreadId
0x180006235  mov     [rbx+20h], eax
0x180006238  mov     [rbx+38h], r13
0x18000623c  mov     eax, [rsp+78h+arg_8]
0x180006243  mov     [rbx+40h], eax
0x180006246  mov     [rbx+44h], ebp
0x180006249  mov     rax, [rsp+78h+arg_20]
0x180006251  mov     [rbx+28h], rax
0x180006255  mov     [rbx+30h], r12
0x180006259  mov     rax, [rsp+78h+arg_28]
0x180006261  mov     [rbx+88h], rax
0x180006268  mov     rax, [rsp+78h+arg_0]
0x180006270  mov     [rbx+90h], rax
0x180006277  mov     [rbx+48h], rdi
0x18000627b  xorps   xmm0, xmm0
0x18000627e  xor     eax, eax
0x180006280  movups  xmmword ptr [rbx+68h], xmm0
0x180006284  mov     [rbx+78h], rax
0x180006288  movups  xmmword ptr [rbx+50h], xmm0
0x18000628c  mov     [rbx+60h], rax
0x180006290  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006297  test    rax, rax
0x18000629a  jz      short loc_1800062A3
0x18000629c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062a1  jmp     short loc_1800062A6
0x1800062a3  mov     rax, rdi
0x1800062a6  mov     [rbx+80h], rax
0x1800062ad  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800062b4  test    rax, rax
0x1800062b7  jz      short loc_1800062C1
0x1800062b9  mov     rcx, rbx
0x1800062bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062c1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800062c8  test    rax, rax
0x1800062cb  jz      short loc_1800062E3
0x1800062cd  mov     r8d, 400h
0x1800062d3  mov     rdx, [rsp+78h+arg_60]
0x1800062db  mov     rcx, rbx
0x1800062de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062e3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800062ea  test    rax, rax
0x1800062ed  jz      short loc_1800062F7
0x1800062ef  mov     rcx, rbx
0x1800062f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800062f7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800062fe  test    rax, rax
0x180006301  jz      short loc_180006311
0x180006303  test    byte ptr [rbx+4], 2
0x180006307  jnz     short loc_180006311
0x180006309  mov     rcx, rbx
0x18000630c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006311  cmp     [rbx+8], edi
0x180006314  jl      short loc_180006330
0x180006316  cmp     r15d, 3
0x18000631a  jnz     loc_1800063FF
0x180006320  mov     ecx, 8000FFFFh; this
0x180006325  mov     [rbx+8], ecx
0x180006328  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000632d  mov     [rbx+0Ch], eax
0x180006330  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006337  jnz     short loc_180006358
0x180006339  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006340  test    rax, rax
0x180006343  jz      short loc_18000634E
0x180006345  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000634a  test    al, al
0x18000634c  jmp     short loc_180006356
0x18000634e  call    cs:__imp_IsDebuggerPresent
0x180006354  test    eax, eax
0x180006356  jz      short loc_18000635E
0x180006358  test    byte ptr [rbx+4], 2
0x18000635c  jz      short loc_180006382
0x18000635e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006365  test    rax, rax
0x180006368  jz      short loc_1800063C6
0x18000636a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006371  jnz     short loc_1800063C6
0x180006373  xor     r8d, r8d
0x180006376  xor     edx, edx
0x180006378  mov     rcx, rbx
0x18000637b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006380  jmp     short loc_1800063C6
0x180006382  mov     ebp, 800h
0x180006387  mov     rax, cs:g_pfnResultLoggingCallback
0x18000638e  test    rax, rax
0x180006391  jz      short loc_1800063AA
0x180006393  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000639a  jnz     short loc_1800063AA
0x18000639c  mov     r8d, ebp
0x18000639f  mov     rdx, rsi
0x1800063a2  mov     rcx, rbx
0x1800063a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063aa  cmp     [rsi], di
0x1800063ad  jnz     short loc_1800063BD
0x1800063af  mov     r8, rbx; unsigned __int64
0x1800063b2  mov     rdx, rbp; unsigned __int16 *
0x1800063b5  mov     rcx, rsi; this
0x1800063b8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800063bd  mov     rcx, rsi; lpOutputString
0x1800063c0  call    cs:__imp_OutputDebugStringW
0x1800063c6  test    byte ptr [rbx+4], 4
0x1800063ca  jnz     short loc_1800063D5
0x1800063cc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800063d3  jz      short loc_1800063E7
0x1800063d5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800063dc  test    rax, rax
0x1800063df  jz      short loc_1800063E7
0x1800063e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800063e6  nop
0x1800063e7  mov     rbx, [rsp+78h+arg_10]
0x1800063ef  add     rsp, 40h
0x1800063f3  pop     r15
0x1800063f5  pop     r14
0x1800063f7  pop     r13
0x1800063f9  pop     r12
0x1800063fb  pop     rdi
0x1800063fc  pop     rsi
0x1800063fd  pop     rbp
0x1800063fe  retn
0x1800063ff  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
