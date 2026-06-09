# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008324`
- end: `0x18000861d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006998`
- `0x180006d04`
- `0x180009e8c`

## callees

- `0x180004b74`
- `0x180004f5c`
- `0x180005300`
- `0x1800068d0`
- `0x180008324`
- `0x18000886c`
- `0x180008888`
- `0x1800088a4`
- `0x180009508`
- `0x180026010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008447`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008447`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008566`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008566`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800085d8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800085d8`

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
0x180008324  mov     [rsp+arg_10], rbx
0x180008329  mov     [rsp+arg_8], edx
0x18000832d  mov     [rsp+arg_0], rcx
0x180008332  push    rbp
0x180008333  push    rsi
0x180008334  push    rdi
0x180008335  push    r12
0x180008337  push    r13
0x180008339  push    r14
0x18000833b  push    r15
0x18000833d  sub     rsp, 40h
0x180008341  mov     r12, r9
0x180008344  mov     r13, r8
0x180008347  mov     r10, rcx
0x18000834a  xor     eax, eax
0x18000834c  mov     rsi, [rsp+78h+lpOutputString]
0x180008354  mov     [rsi], ax
0x180008357  mov     rax, [rsp+78h+arg_60]
0x18000835f  mov     byte ptr [rax], 0
0x180008362  mov     r14, [rsp+78h+arg_38]
0x18000836a  mov     edi, [r14]
0x18000836d  mov     rbx, [rsp+78h+arg_78]
0x180008375  mov     [rbx+8], edi
0x180008378  mov     eax, [r14+4]
0x18000837c  mov     [rbx+0Ch], eax
0x18000837f  xor     ebp, ebp
0x180008381  mov     r15d, [rsp+78h+arg_30]
0x180008389  mov     ecx, r15d
0x18000838c  test    r15d, r15d
0x18000838f  jz      short loc_1800083F7
0x180008391  sub     ecx, 1
0x180008394  jz      short loc_1800083EE
0x180008396  sub     ecx, 1
0x180008399  jz      short loc_1800083A9
0x18000839b  cmp     ecx, 1
0x18000839e  jnz     short loc_180008400
0x1800083a0  mov     ecx, edi; this
0x1800083a2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800083a7  jmp     short loc_1800083FE
0x1800083a9  test    edi, edi
0x1800083ab  js      short loc_1800083E5
0x1800083ad  mov     edi, 8007029Ch
0x1800083b2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800083b6  mov     rax, [rsp+78h+arg_28]
0x1800083be  mov     [rsp+78h+var_50], rax; __int64
0x1800083c3  mov     rax, [rsp+78h+arg_20]
0x1800083cb  mov     [rsp+78h+var_58], rax; __int64
0x1800083d0  mov     rcx, r10; int
0x1800083d3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800083d8  mov     [rbx+8], edi
0x1800083db  mov     ecx, edi; this
0x1800083dd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800083e2  mov     [rbx+0Ch], eax
0x1800083e5  mov     ecx, edi; this
0x1800083e7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800083ec  jmp     short loc_1800083FE
0x1800083ee  mov     ecx, edi; this
0x1800083f0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800083f5  jmp     short loc_1800083FE
0x1800083f7  mov     ecx, edi; this
0x1800083f9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800083fe  mov     ebp, eax
0x180008400  mov     [rbx], r15d
0x180008403  mov     eax, [rsp+78h+arg_70]
0x18000840a  mov     [rbx+4], eax
0x18000840d  cmp     dword ptr [r14+8], 1
0x180008412  jnz     short loc_18000841A
0x180008414  or      eax, 8
0x180008417  mov     [rbx+4], eax
0x18000841a  mov     eax, 1
0x18000841f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008427  inc     eax
0x180008429  mov     [rbx+10h], eax
0x18000842c  mov     rax, [rsp+78h+arg_40]
0x180008434  xor     edi, edi
0x180008436  test    rax, rax
0x180008439  jz      short loc_180008440
0x18000843b  cmp     [rax], di
0x18000843e  jnz     short loc_180008443
0x180008440  mov     rax, rdi
0x180008443  mov     [rbx+18h], rax
0x180008447  call    cs:__imp_GetCurrentThreadId
0x18000844d  mov     [rbx+20h], eax
0x180008450  mov     [rbx+38h], r13
0x180008454  mov     eax, [rsp+78h+arg_8]
0x18000845b  mov     [rbx+40h], eax
0x18000845e  mov     [rbx+44h], ebp
0x180008461  mov     rax, [rsp+78h+arg_20]
0x180008469  mov     [rbx+28h], rax
0x18000846d  mov     [rbx+30h], r12
0x180008471  mov     rax, [rsp+78h+arg_28]
0x180008479  mov     [rbx+88h], rax
0x180008480  mov     rax, [rsp+78h+arg_0]
0x180008488  mov     [rbx+90h], rax
0x18000848f  mov     [rbx+48h], rdi
0x180008493  xorps   xmm0, xmm0
0x180008496  xor     eax, eax
0x180008498  movups  xmmword ptr [rbx+68h], xmm0
0x18000849c  mov     [rbx+78h], rax
0x1800084a0  movups  xmmword ptr [rbx+50h], xmm0
0x1800084a4  mov     [rbx+60h], rax
0x1800084a8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800084af  test    rax, rax
0x1800084b2  jz      short loc_1800084BB
0x1800084b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084b9  jmp     short loc_1800084BE
0x1800084bb  mov     rax, rdi
0x1800084be  mov     [rbx+80h], rax
0x1800084c5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800084cc  test    rax, rax
0x1800084cf  jz      short loc_1800084D9
0x1800084d1  mov     rcx, rbx
0x1800084d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084d9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800084e0  test    rax, rax
0x1800084e3  jz      short loc_1800084FB
0x1800084e5  mov     r8d, 400h
0x1800084eb  mov     rdx, [rsp+78h+arg_60]
0x1800084f3  mov     rcx, rbx
0x1800084f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800084fb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008502  test    rax, rax
0x180008505  jz      short loc_18000850F
0x180008507  mov     rcx, rbx
0x18000850a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000850f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008516  test    rax, rax
0x180008519  jz      short loc_180008529
0x18000851b  test    byte ptr [rbx+4], 2
0x18000851f  jnz     short loc_180008529
0x180008521  mov     rcx, rbx
0x180008524  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008529  cmp     [rbx+8], edi
0x18000852c  jl      short loc_180008548
0x18000852e  cmp     r15d, 3
0x180008532  jnz     loc_180008617
0x180008538  mov     ecx, 8000FFFFh; this
0x18000853d  mov     [rbx+8], ecx
0x180008540  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008545  mov     [rbx+0Ch], eax
0x180008548  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000854f  jnz     short loc_180008570
0x180008551  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008558  test    rax, rax
0x18000855b  jz      short loc_180008566
0x18000855d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008562  test    al, al
0x180008564  jmp     short loc_18000856E
0x180008566  call    cs:__imp_IsDebuggerPresent
0x18000856c  test    eax, eax
0x18000856e  jz      short loc_180008576
0x180008570  test    byte ptr [rbx+4], 2
0x180008574  jz      short loc_18000859A
0x180008576  mov     rax, cs:g_pfnResultLoggingCallback
0x18000857d  test    rax, rax
0x180008580  jz      short loc_1800085DE
0x180008582  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008589  jnz     short loc_1800085DE
0x18000858b  xor     r8d, r8d
0x18000858e  xor     edx, edx
0x180008590  mov     rcx, rbx
0x180008593  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008598  jmp     short loc_1800085DE
0x18000859a  mov     ebp, 800h
0x18000859f  mov     rax, cs:g_pfnResultLoggingCallback
0x1800085a6  test    rax, rax
0x1800085a9  jz      short loc_1800085C2
0x1800085ab  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800085b2  jnz     short loc_1800085C2
0x1800085b4  mov     r8d, ebp
0x1800085b7  mov     rdx, rsi
0x1800085ba  mov     rcx, rbx
0x1800085bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085c2  cmp     [rsi], di
0x1800085c5  jnz     short loc_1800085D5
0x1800085c7  mov     r8, rbx; unsigned __int64
0x1800085ca  mov     rdx, rbp; unsigned __int16 *
0x1800085cd  mov     rcx, rsi; this
0x1800085d0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800085d5  mov     rcx, rsi; lpOutputString
0x1800085d8  call    cs:__imp_OutputDebugStringW
0x1800085de  test    byte ptr [rbx+4], 4
0x1800085e2  jnz     short loc_1800085ED
0x1800085e4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800085eb  jz      short loc_1800085FF
0x1800085ed  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800085f4  test    rax, rax
0x1800085f7  jz      short loc_1800085FF
0x1800085f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085fe  nop
0x1800085ff  mov     rbx, [rsp+78h+arg_10]
0x180008607  add     rsp, 40h
0x18000860b  pop     r15
0x18000860d  pop     r14
0x18000860f  pop     r13
0x180008611  pop     r12
0x180008613  pop     rdi
0x180008614  pop     rsi
0x180008615  pop     rbp
0x180008616  retn
0x180008617  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
