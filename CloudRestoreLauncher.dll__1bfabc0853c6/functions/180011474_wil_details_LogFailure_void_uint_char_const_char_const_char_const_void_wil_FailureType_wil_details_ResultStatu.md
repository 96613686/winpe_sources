# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011474`
- end: `0x180011752`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `734`
- prototype: ``
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x18000f864`
- `0x18000fbb4`
- `0x180013eec`

## callees

- `0x18000f79c`
- `0x180010984`
- `0x180011244`
- `0x180011434`
- `0x180011474`
- `0x180011ba0`
- `0x180011bc0`
- `0x180011bd4`
- `0x180011bf0`
- `0x180012ab4`
- `0x18012d010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x1800116e9`
- `KERNEL32!OutputDebugStringW` at `0x1800116e9`
- `KERNEL32!GetCurrentThreadId` at `0x18001159b`
- `KERNEL32!GetCurrentThreadId` at `0x18001159b`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v26; // r9
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180011474  mov     [rsp+arg_10], rbx
0x180011479  mov     [rsp+arg_8], edx
0x18001147d  mov     [rsp+arg_0], rcx
0x180011482  push    rbp
0x180011483  push    rsi
0x180011484  push    rdi
0x180011485  push    r12
0x180011487  push    r13
0x180011489  push    r14
0x18001148b  push    r15
0x18001148d  sub     rsp, 40h
0x180011491  mov     r12, r9
0x180011494  mov     r13, r8
0x180011497  mov     r10, rcx
0x18001149a  xor     eax, eax
0x18001149c  mov     rsi, [rsp+78h+lpOutputString]
0x1800114a4  mov     [rsi], ax
0x1800114a7  mov     rax, [rsp+78h+arg_60]
0x1800114af  mov     byte ptr [rax], 0
0x1800114b2  mov     r14, [rsp+78h+arg_38]
0x1800114ba  mov     edi, [r14]
0x1800114bd  mov     rbx, [rsp+78h+arg_78]
0x1800114c5  mov     [rbx+8], edi
0x1800114c8  mov     eax, [r14+4]
0x1800114cc  mov     [rbx+0Ch], eax
0x1800114cf  xor     ebp, ebp
0x1800114d1  mov     r15d, [rsp+78h+arg_30]
0x1800114d9  mov     ecx, r15d
0x1800114dc  test    r15d, r15d
0x1800114df  jz      short loc_18001154B
0x1800114e1  sub     ecx, 1
0x1800114e4  jz      short loc_180011542
0x1800114e6  sub     ecx, 1
0x1800114e9  jz      short loc_1800114F9
0x1800114eb  cmp     ecx, 1
0x1800114ee  jnz     short loc_180011554
0x1800114f0  mov     ecx, edi; this
0x1800114f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800114f7  jmp     short loc_180011552
0x1800114f9  test    edi, edi
0x1800114fb  js      short loc_180011539
0x1800114fd  mov     [rsp+78h+var_40], ebp
0x180011501  mov     edi, 8007029Ch
0x180011506  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001150a  mov     rax, [rsp+78h+arg_28]
0x180011512  mov     [rsp+78h+var_50], rax; __int64
0x180011517  mov     rax, [rsp+78h+arg_20]
0x18001151f  mov     [rsp+78h+var_58], rax; __int64
0x180011524  mov     rcx, r10; int
0x180011527  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001152c  mov     [rbx+8], edi
0x18001152f  mov     ecx, edi; this
0x180011531  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011536  mov     [rbx+0Ch], eax
0x180011539  mov     ecx, edi; this
0x18001153b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011540  jmp     short loc_180011552
0x180011542  mov     ecx, edi; this
0x180011544  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011549  jmp     short loc_180011552
0x18001154b  mov     ecx, edi; this
0x18001154d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011552  mov     ebp, eax
0x180011554  mov     [rbx], r15d
0x180011557  mov     eax, [rsp+78h+arg_70]
0x18001155e  mov     [rbx+4], eax
0x180011561  cmp     dword ptr [r14+8], 1
0x180011566  jnz     short loc_18001156E
0x180011568  or      eax, 8
0x18001156b  mov     [rbx+4], eax
0x18001156e  mov     eax, 1
0x180011573  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001157b  inc     eax
0x18001157d  mov     [rbx+10h], eax
0x180011580  mov     rax, [rsp+78h+arg_40]
0x180011588  xor     edi, edi
0x18001158a  test    rax, rax
0x18001158d  jz      short loc_180011594
0x18001158f  cmp     [rax], di
0x180011592  jnz     short loc_180011597
0x180011594  mov     rax, rdi
0x180011597  mov     [rbx+18h], rax
0x18001159b  call    cs:__imp_GetCurrentThreadId
0x1800115a1  mov     [rbx+20h], eax
0x1800115a4  mov     [rbx+38h], r13
0x1800115a8  mov     eax, [rsp+78h+arg_8]
0x1800115af  mov     [rbx+40h], eax
0x1800115b2  mov     [rbx+44h], ebp
0x1800115b5  mov     rax, [rsp+78h+arg_20]
0x1800115bd  mov     [rbx+28h], rax
0x1800115c1  mov     [rbx+30h], r12
0x1800115c5  mov     rax, [rsp+78h+arg_28]
0x1800115cd  mov     [rbx+88h], rax
0x1800115d4  mov     rax, [rsp+78h+arg_0]
0x1800115dc  mov     [rbx+90h], rax
0x1800115e3  mov     [rbx+48h], rdi
0x1800115e7  xorps   xmm0, xmm0
0x1800115ea  xor     eax, eax
0x1800115ec  movups  xmmword ptr [rbx+68h], xmm0
0x1800115f0  mov     [rbx+78h], rax
0x1800115f4  movups  xmmword ptr [rbx+50h], xmm0
0x1800115f8  mov     [rbx+60h], rax
0x1800115fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011603  test    rax, rax
0x180011606  jz      short loc_18001160F
0x180011608  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001160d  jmp     short loc_180011612
0x18001160f  mov     rax, rdi
0x180011612  mov     [rbx+80h], rax
0x180011619  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011620  test    rax, rax
0x180011623  jz      short loc_18001162D
0x180011625  mov     rcx, rbx
0x180011628  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001162d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011634  test    rax, rax
0x180011637  jz      short loc_18001164F
0x180011639  mov     r8d, 400h
0x18001163f  mov     rdx, [rsp+78h+arg_60]
0x180011647  mov     rcx, rbx
0x18001164a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001164f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011656  test    rax, rax
0x180011659  jz      short loc_180011663
0x18001165b  mov     rcx, rbx
0x18001165e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011663  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001166a  test    rax, rax
0x18001166d  jz      short loc_18001167D
0x18001166f  test    byte ptr [rbx+4], 2
0x180011673  jnz     short loc_18001167D
0x180011675  mov     rcx, rbx
0x180011678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001167d  cmp     [rbx+8], edi
0x180011680  jl      short loc_18001169C
0x180011682  cmp     r15d, 3
0x180011686  jnz     loc_18001174C
0x18001168c  mov     ecx, 8000FFFFh; this
0x180011691  mov     [rbx+8], ecx
0x180011694  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011699  mov     [rbx+0Ch], eax
0x18001169c  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x1800116a1  test    al, al
0x1800116a3  jz      short loc_1800116F1
0x1800116a5  test    byte ptr [rbx+4], 2
0x1800116a9  jnz     short loc_1800116F1
0x1800116ab  mov     ebp, 800h
0x1800116b0  mov     rax, cs:g_pfnResultLoggingCallback
0x1800116b7  test    rax, rax
0x1800116ba  jz      short loc_1800116D3
0x1800116bc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800116c3  jnz     short loc_1800116D3
0x1800116c5  mov     r8d, ebp
0x1800116c8  mov     rdx, rsi
0x1800116cb  mov     rcx, rbx
0x1800116ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d3  cmp     [rsi], di
0x1800116d6  jnz     short loc_1800116E6
0x1800116d8  mov     r8, rbx; unsigned __int64
0x1800116db  mov     rdx, rbp; unsigned __int16 *
0x1800116de  mov     rcx, rsi; this
0x1800116e1  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800116e6  mov     rcx, rsi; lpOutputString
0x1800116e9  call    cs:__imp_OutputDebugStringW
0x1800116ef  jmp     short loc_180011713
0x1800116f1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800116f8  test    rax, rax
0x1800116fb  jz      short loc_180011713
0x1800116fd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011704  jnz     short loc_180011713
0x180011706  xor     r8d, r8d
0x180011709  xor     edx, edx
0x18001170b  mov     rcx, rbx
0x18001170e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011713  test    byte ptr [rbx+4], 4
0x180011717  jnz     short loc_180011722
0x180011719  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011720  jz      short loc_180011734
0x180011722  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011729  test    rax, rax
0x18001172c  jz      short loc_180011734
0x18001172e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011733  nop
0x180011734  mov     rbx, [rsp+78h+arg_10]
0x18001173c  add     rsp, 40h
0x180011740  pop     r15
0x180011742  pop     r14
0x180011744  pop     r13
0x180011746  pop     r12
0x180011748  pop     rdi
0x180011749  pop     rsi
0x18001174a  pop     rbp
0x18001174b  retn
0x18001174c  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
