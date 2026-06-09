# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800141e0`
- end: `0x1800144d5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000ad90`
- `0x18000ae50`
- `0x18000af40`

## callees

- `0x18000acd8`
- `0x18000f774`
- `0x18000fffc`
- `0x1800141e0`
- `0x1800151e8`
- `0x180015210`
- `0x180015488`
- `0x1800154a4`
- `0x180018020`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014303`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180014303`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180014424`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180014424`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014496`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180014496`

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
0x1800141e0  mov     [rsp+arg_10], rbx
0x1800141e5  mov     [rsp+arg_8], edx
0x1800141e9  mov     [rsp+arg_0], rcx
0x1800141ee  push    rbp
0x1800141ef  push    rsi
0x1800141f0  push    rdi
0x1800141f1  push    r12
0x1800141f3  push    r13
0x1800141f5  push    r14
0x1800141f7  push    r15
0x1800141f9  sub     rsp, 40h
0x1800141fd  mov     r12, r9
0x180014200  mov     r13, r8
0x180014203  mov     r10, rcx
0x180014206  xor     eax, eax
0x180014208  mov     rsi, [rsp+78h+lpOutputString]
0x180014210  mov     [rsi], ax
0x180014213  mov     rax, [rsp+78h+arg_60]
0x18001421b  mov     byte ptr [rax], 0
0x18001421e  mov     r14, [rsp+78h+arg_38]
0x180014226  mov     edi, [r14]
0x180014229  mov     rbx, [rsp+78h+arg_78]
0x180014231  mov     [rbx+8], edi
0x180014234  mov     eax, [r14+4]
0x180014238  mov     [rbx+0Ch], eax
0x18001423b  xor     ebp, ebp
0x18001423d  mov     r15d, [rsp+78h+arg_30]
0x180014245  mov     ecx, r15d
0x180014248  test    r15d, r15d
0x18001424b  jz      short loc_1800142B3
0x18001424d  sub     ecx, 1
0x180014250  jz      short loc_1800142AA
0x180014252  sub     ecx, 1
0x180014255  jz      short loc_180014265
0x180014257  cmp     ecx, 1
0x18001425a  jnz     short loc_1800142BC
0x18001425c  mov     ecx, edi; this
0x18001425e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180014263  jmp     short loc_1800142BA
0x180014265  test    edi, edi
0x180014267  js      short loc_1800142A1
0x180014269  mov     edi, 8007029Ch
0x18001426e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180014272  mov     rax, [rsp+78h+arg_28]
0x18001427a  mov     [rsp+78h+var_50], rax; __int64
0x18001427f  mov     rax, [rsp+78h+arg_20]
0x180014287  mov     [rsp+78h+var_58], rax; __int64
0x18001428c  mov     rcx, r10; int
0x18001428f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180014294  mov     [rbx+8], edi
0x180014297  mov     ecx, edi; this
0x180014299  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001429e  mov     [rbx+0Ch], eax
0x1800142a1  mov     ecx, edi; this
0x1800142a3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800142a8  jmp     short loc_1800142BA
0x1800142aa  mov     ecx, edi; this
0x1800142ac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800142b1  jmp     short loc_1800142BA
0x1800142b3  mov     ecx, edi; this
0x1800142b5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800142ba  mov     ebp, eax
0x1800142bc  mov     [rbx], r15d
0x1800142bf  mov     eax, [rsp+78h+arg_70]
0x1800142c6  mov     [rbx+4], eax
0x1800142c9  cmp     dword ptr [r14+8], 1
0x1800142ce  jnz     short loc_1800142D6
0x1800142d0  or      eax, 8
0x1800142d3  mov     [rbx+4], eax
0x1800142d6  mov     eax, 1
0x1800142db  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800142e3  inc     eax
0x1800142e5  mov     [rbx+10h], eax
0x1800142e8  mov     rax, [rsp+78h+arg_40]
0x1800142f0  xor     edi, edi
0x1800142f2  test    rax, rax
0x1800142f5  jz      short loc_1800142FC
0x1800142f7  cmp     [rax], di
0x1800142fa  jnz     short loc_1800142FF
0x1800142fc  mov     rax, rdi
0x1800142ff  mov     [rbx+18h], rax
0x180014303  call    cs:__imp_GetCurrentThreadId
0x180014309  mov     [rbx+20h], eax
0x18001430c  mov     [rbx+38h], r13
0x180014310  mov     eax, [rsp+78h+arg_8]
0x180014317  mov     [rbx+40h], eax
0x18001431a  mov     [rbx+44h], ebp
0x18001431d  mov     rax, [rsp+78h+arg_20]
0x180014325  mov     [rbx+28h], rax
0x180014329  mov     [rbx+30h], r12
0x18001432d  mov     rax, [rsp+78h+arg_28]
0x180014335  mov     [rbx+88h], rax
0x18001433c  mov     rax, [rsp+78h+arg_0]
0x180014344  mov     [rbx+90h], rax
0x18001434b  mov     [rbx+48h], rdi
0x18001434f  xorps   xmm0, xmm0
0x180014352  xor     eax, eax
0x180014354  movups  xmmword ptr [rbx+68h], xmm0
0x180014358  mov     [rbx+78h], rax
0x18001435c  movups  xmmword ptr [rbx+50h], xmm0
0x180014360  mov     [rbx+60h], rax
0x180014364  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001436b  test    rax, rax
0x18001436e  jz      short loc_180014377
0x180014370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014375  jmp     short loc_18001437A
0x180014377  mov     rax, rdi
0x18001437a  mov     [rbx+80h], rax
0x180014381  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180014388  test    rax, rax
0x18001438b  jz      short loc_180014395
0x18001438d  mov     rcx, rbx
0x180014390  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014395  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001439c  test    rax, rax
0x18001439f  jz      short loc_1800143B7
0x1800143a1  mov     r8d, 400h
0x1800143a7  mov     rdx, [rsp+78h+arg_60]
0x1800143af  mov     rcx, rbx
0x1800143b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143b7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800143be  test    rax, rax
0x1800143c1  jz      short loc_1800143CB
0x1800143c3  mov     rcx, rbx
0x1800143c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143cb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800143d2  test    rax, rax
0x1800143d5  jz      short loc_1800143E5
0x1800143d7  test    byte ptr [rbx+4], 2
0x1800143db  jnz     short loc_1800143E5
0x1800143dd  mov     rcx, rbx
0x1800143e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143e5  cmp     [rbx+8], edi
0x1800143e8  jl      short loc_180014406
0x1800143ea  cmp     r15d, 3
0x1800143ee  jz      short loc_1800143F6
0x1800143f0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800143f6  mov     ecx, 8000FFFFh; this
0x1800143fb  mov     [rbx+8], ecx
0x1800143fe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180014403  mov     [rbx+0Ch], eax
0x180014406  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001440d  jnz     short loc_18001442E
0x18001440f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180014416  test    rax, rax
0x180014419  jz      short loc_180014424
0x18001441b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014420  test    al, al
0x180014422  jmp     short loc_18001442C
0x180014424  call    cs:__imp_IsDebuggerPresent
0x18001442a  test    eax, eax
0x18001442c  jz      short loc_180014434
0x18001442e  test    byte ptr [rbx+4], 2
0x180014432  jz      short loc_180014458
0x180014434  mov     rax, cs:g_pfnResultLoggingCallback
0x18001443b  test    rax, rax
0x18001443e  jz      short loc_18001449C
0x180014440  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180014447  jnz     short loc_18001449C
0x180014449  xor     r8d, r8d
0x18001444c  xor     edx, edx
0x18001444e  mov     rcx, rbx
0x180014451  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014456  jmp     short loc_18001449C
0x180014458  mov     ebp, 800h
0x18001445d  mov     rax, cs:g_pfnResultLoggingCallback
0x180014464  test    rax, rax
0x180014467  jz      short loc_180014480
0x180014469  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180014470  jnz     short loc_180014480
0x180014472  mov     r8d, ebp
0x180014475  mov     rdx, rsi
0x180014478  mov     rcx, rbx
0x18001447b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014480  cmp     [rsi], di
0x180014483  jnz     short loc_180014493
0x180014485  mov     r8, rbx; unsigned __int64
0x180014488  mov     rdx, rbp; unsigned __int16 *
0x18001448b  mov     rcx, rsi; this
0x18001448e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180014493  mov     rcx, rsi; lpOutputString
0x180014496  call    cs:__imp_OutputDebugStringW
0x18001449c  test    byte ptr [rbx+4], 4
0x1800144a0  jnz     short loc_1800144AB
0x1800144a2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800144a9  jz      short loc_1800144BD
0x1800144ab  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800144b2  test    rax, rax
0x1800144b5  jz      short loc_1800144BD
0x1800144b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800144bc  nop
0x1800144bd  mov     rbx, [rsp+78h+arg_10]
0x1800144c5  add     rsp, 40h
0x1800144c9  pop     r15
0x1800144cb  pop     r14
0x1800144cd  pop     r13
0x1800144cf  pop     r12
0x1800144d1  pop     rdi
0x1800144d2  pop     rsi
0x1800144d3  pop     rbp
0x1800144d4  retn
```
