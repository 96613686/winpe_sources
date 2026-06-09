# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013298`
- end: `0x1800135a4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180010938`

## callees

- `0x18001034c`
- `0x1800127e4`
- `0x180012ff0`
- `0x180013298`
- `0x180013fec`
- `0x180014010`
- `0x180014158`
- `0x180014178`
- `0x180016634`
- `0x180019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1800134e0`
- `KERNEL32!IsDebuggerPresent` at `0x1800134e0`
- `KERNEL32!OutputDebugStringW` at `0x180013558`
- `KERNEL32!OutputDebugStringW` at `0x180013558`
- `KERNEL32!GetCurrentThreadId` at `0x1800133bb`
- `KERNEL32!GetCurrentThreadId` at `0x1800133bb`

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
0x180013298  mov     [rsp+arg_10], rbx
0x18001329d  mov     [rsp+arg_8], edx
0x1800132a1  mov     [rsp+arg_0], rcx
0x1800132a6  push    rbp
0x1800132a7  push    rsi
0x1800132a8  push    rdi
0x1800132a9  push    r12
0x1800132ab  push    r13
0x1800132ad  push    r14
0x1800132af  push    r15
0x1800132b1  sub     rsp, 40h
0x1800132b5  mov     r12, r9
0x1800132b8  mov     r13, r8
0x1800132bb  mov     r10, rcx
0x1800132be  xor     eax, eax
0x1800132c0  mov     rsi, [rsp+78h+lpOutputString]
0x1800132c8  mov     [rsi], ax
0x1800132cb  mov     rax, [rsp+78h+arg_60]
0x1800132d3  mov     byte ptr [rax], 0
0x1800132d6  mov     r14, [rsp+78h+arg_38]
0x1800132de  mov     edi, [r14]
0x1800132e1  mov     rbx, [rsp+78h+arg_78]
0x1800132e9  mov     [rbx+8], edi
0x1800132ec  mov     eax, [r14+4]
0x1800132f0  mov     [rbx+0Ch], eax
0x1800132f3  xor     ebp, ebp
0x1800132f5  mov     r15d, [rsp+78h+arg_30]
0x1800132fd  mov     ecx, r15d
0x180013300  test    r15d, r15d
0x180013303  jz      short loc_18001336B
0x180013305  sub     ecx, 1
0x180013308  jz      short loc_180013362
0x18001330a  sub     ecx, 1
0x18001330d  jz      short loc_18001331D
0x18001330f  cmp     ecx, 1
0x180013312  jnz     short loc_180013374
0x180013314  mov     ecx, edi; this
0x180013316  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001331b  jmp     short loc_180013372
0x18001331d  test    edi, edi
0x18001331f  js      short loc_180013359
0x180013321  mov     edi, 8007029Ch
0x180013326  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001332a  mov     rax, [rsp+78h+arg_28]
0x180013332  mov     [rsp+78h+var_50], rax; __int64
0x180013337  mov     rax, [rsp+78h+arg_20]
0x18001333f  mov     [rsp+78h+var_58], rax; __int64
0x180013344  mov     rcx, r10; int
0x180013347  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001334c  mov     [rbx+8], edi
0x18001334f  mov     ecx, edi; this
0x180013351  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013356  mov     [rbx+0Ch], eax
0x180013359  mov     ecx, edi; this
0x18001335b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013360  jmp     short loc_180013372
0x180013362  mov     ecx, edi; this
0x180013364  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013369  jmp     short loc_180013372
0x18001336b  mov     ecx, edi; this
0x18001336d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013372  mov     ebp, eax
0x180013374  mov     [rbx], r15d
0x180013377  mov     eax, [rsp+78h+arg_70]
0x18001337e  mov     [rbx+4], eax
0x180013381  cmp     dword ptr [r14+8], 1
0x180013386  jnz     short loc_18001338E
0x180013388  or      eax, 8
0x18001338b  mov     [rbx+4], eax
0x18001338e  mov     eax, 1
0x180013393  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001339b  inc     eax
0x18001339d  mov     [rbx+10h], eax
0x1800133a0  mov     rax, [rsp+78h+arg_40]
0x1800133a8  xor     edi, edi
0x1800133aa  test    rax, rax
0x1800133ad  jz      short loc_1800133B4
0x1800133af  cmp     [rax], di
0x1800133b2  jnz     short loc_1800133B7
0x1800133b4  mov     rax, rdi
0x1800133b7  mov     [rbx+18h], rax
0x1800133bb  call    cs:__imp_GetCurrentThreadId
0x1800133c2  nop     dword ptr [rax+rax+00h]
0x1800133c7  mov     [rbx+20h], eax
0x1800133ca  mov     [rbx+38h], r13
0x1800133ce  mov     eax, [rsp+78h+arg_8]
0x1800133d5  mov     [rbx+40h], eax
0x1800133d8  mov     [rbx+44h], ebp
0x1800133db  mov     rax, [rsp+78h+arg_20]
0x1800133e3  mov     [rbx+28h], rax
0x1800133e7  mov     [rbx+30h], r12
0x1800133eb  mov     rax, [rsp+78h+arg_28]
0x1800133f3  mov     [rbx+88h], rax
0x1800133fa  mov     rax, [rsp+78h+arg_0]
0x180013402  mov     [rbx+90h], rax
0x180013409  mov     [rbx+48h], rdi
0x18001340d  xorps   xmm0, xmm0
0x180013410  xor     eax, eax
0x180013412  movups  xmmword ptr [rbx+68h], xmm0
0x180013416  mov     [rbx+78h], rax
0x18001341a  movups  xmmword ptr [rbx+50h], xmm0
0x18001341e  mov     [rbx+60h], rax
0x180013422  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013429  test    rax, rax
0x18001342c  jz      short loc_180013435
0x18001342e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013433  jmp     short loc_180013438
0x180013435  mov     rax, rdi
0x180013438  mov     [rbx+80h], rax
0x18001343f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013446  test    rax, rax
0x180013449  jz      short loc_180013453
0x18001344b  mov     rcx, rbx
0x18001344e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013453  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001345a  test    rax, rax
0x18001345d  jz      short loc_180013475
0x18001345f  mov     r8d, 400h
0x180013465  mov     rdx, [rsp+78h+arg_60]
0x18001346d  mov     rcx, rbx
0x180013470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013475  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001347c  test    rax, rax
0x18001347f  jz      short loc_180013489
0x180013481  mov     rcx, rbx
0x180013484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013489  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013490  test    rax, rax
0x180013493  jz      short loc_1800134A3
0x180013495  test    byte ptr [rbx+4], 2
0x180013499  jnz     short loc_1800134A3
0x18001349b  mov     rcx, rbx
0x18001349e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134a3  cmp     [rbx+8], edi
0x1800134a6  jl      short loc_1800134C2
0x1800134a8  cmp     r15d, 3
0x1800134ac  jnz     loc_18001359E
0x1800134b2  mov     ecx, 8000FFFFh; this
0x1800134b7  mov     [rbx+8], ecx
0x1800134ba  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800134bf  mov     [rbx+0Ch], eax
0x1800134c2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800134c9  jnz     short loc_1800134F0
0x1800134cb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800134d2  test    rax, rax
0x1800134d5  jz      short loc_1800134E0
0x1800134d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800134dc  test    al, al
0x1800134de  jmp     short loc_1800134EE
0x1800134e0  call    cs:__imp_IsDebuggerPresent
0x1800134e7  nop     dword ptr [rax+rax+00h]
0x1800134ec  test    eax, eax
0x1800134ee  jz      short loc_1800134F6
0x1800134f0  test    byte ptr [rbx+4], 2
0x1800134f4  jz      short loc_18001351A
0x1800134f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800134fd  test    rax, rax
0x180013500  jz      short loc_180013564
0x180013502  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013509  jnz     short loc_180013564
0x18001350b  xor     r8d, r8d
0x18001350e  xor     edx, edx
0x180013510  mov     rcx, rbx
0x180013513  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013518  jmp     short loc_180013564
0x18001351a  mov     ebp, 800h
0x18001351f  mov     rax, cs:g_pfnResultLoggingCallback
0x180013526  test    rax, rax
0x180013529  jz      short loc_180013542
0x18001352b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013532  jnz     short loc_180013542
0x180013534  mov     r8d, ebp
0x180013537  mov     rdx, rsi
0x18001353a  mov     rcx, rbx
0x18001353d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013542  cmp     [rsi], di
0x180013545  jnz     short loc_180013555
0x180013547  mov     r8, rbx; unsigned __int64
0x18001354a  mov     rdx, rbp; unsigned __int16 *
0x18001354d  mov     rcx, rsi; this
0x180013550  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180013555  mov     rcx, rsi; lpOutputString
0x180013558  call    cs:__imp_OutputDebugStringW
0x18001355f  nop     dword ptr [rax+rax+00h]
0x180013564  test    byte ptr [rbx+4], 4
0x180013568  jnz     short loc_180013573
0x18001356a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180013571  jz      short loc_180013585
0x180013573  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001357a  test    rax, rax
0x18001357d  jz      short loc_180013585
0x18001357f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013584  nop
0x180013585  mov     rbx, [rsp+78h+arg_10]
0x18001358d  add     rsp, 40h
0x180013591  pop     r15
0x180013593  pop     r14
0x180013595  pop     r13
0x180013597  pop     r12
0x180013599  pop     rdi
0x18001359a  pop     rsi
0x18001359b  pop     rbp
0x18001359c  retn
0x18001359e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
