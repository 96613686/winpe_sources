# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800114cc`
- end: `0x1800117c1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x1800113d0`
- `0x18001d180`
- `0x18001d240`
- `0x18002555c`

## callees

- `0x18000efa0`
- `0x1800114cc`
- `0x1800117d0`
- `0x18001781c`
- `0x18001d0c8`
- `0x18001e0ac`
- `0x18001f344`
- `0x18001f408`
- `0x180020a78`
- `0x180045010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800115ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800115ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011710`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011710`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011782`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011782`

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
0x1800114cc  mov     [rsp+arg_10], rbx
0x1800114d1  mov     [rsp+arg_8], edx
0x1800114d5  mov     [rsp+arg_0], rcx
0x1800114da  push    rbp
0x1800114db  push    rsi
0x1800114dc  push    rdi
0x1800114dd  push    r12
0x1800114df  push    r13
0x1800114e1  push    r14
0x1800114e3  push    r15
0x1800114e5  sub     rsp, 40h
0x1800114e9  mov     r12, r9
0x1800114ec  mov     r13, r8
0x1800114ef  mov     r10, rcx
0x1800114f2  xor     eax, eax
0x1800114f4  mov     rsi, [rsp+78h+lpOutputString]
0x1800114fc  mov     [rsi], ax
0x1800114ff  mov     rax, [rsp+78h+arg_60]
0x180011507  mov     byte ptr [rax], 0
0x18001150a  mov     r14, [rsp+78h+arg_38]
0x180011512  mov     edi, [r14]
0x180011515  mov     rbx, [rsp+78h+arg_78]
0x18001151d  mov     [rbx+8], edi
0x180011520  mov     eax, [r14+4]
0x180011524  mov     [rbx+0Ch], eax
0x180011527  xor     ebp, ebp
0x180011529  mov     r15d, [rsp+78h+arg_30]
0x180011531  mov     ecx, r15d
0x180011534  test    r15d, r15d
0x180011537  jz      short loc_18001159F
0x180011539  sub     ecx, 1
0x18001153c  jz      short loc_180011596
0x18001153e  sub     ecx, 1
0x180011541  jz      short loc_180011551
0x180011543  cmp     ecx, 1
0x180011546  jnz     short loc_1800115A8
0x180011548  mov     ecx, edi; this
0x18001154a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001154f  jmp     short loc_1800115A6
0x180011551  test    edi, edi
0x180011553  js      short loc_18001158D
0x180011555  mov     edi, 8007029Ch
0x18001155a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001155e  mov     rax, [rsp+78h+arg_28]
0x180011566  mov     [rsp+78h+var_50], rax; __int64
0x18001156b  mov     rax, [rsp+78h+arg_20]
0x180011573  mov     [rsp+78h+var_58], rax; __int64
0x180011578  mov     rcx, r10; int
0x18001157b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011580  mov     [rbx+8], edi
0x180011583  mov     ecx, edi; this
0x180011585  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001158a  mov     [rbx+0Ch], eax
0x18001158d  mov     ecx, edi; this
0x18001158f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011594  jmp     short loc_1800115A6
0x180011596  mov     ecx, edi; this
0x180011598  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001159d  jmp     short loc_1800115A6
0x18001159f  mov     ecx, edi; this
0x1800115a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800115a6  mov     ebp, eax
0x1800115a8  mov     [rbx], r15d
0x1800115ab  mov     eax, [rsp+78h+arg_70]
0x1800115b2  mov     [rbx+4], eax
0x1800115b5  cmp     dword ptr [r14+8], 1
0x1800115ba  jnz     short loc_1800115C2
0x1800115bc  or      eax, 8
0x1800115bf  mov     [rbx+4], eax
0x1800115c2  mov     eax, 1
0x1800115c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800115cf  inc     eax
0x1800115d1  mov     [rbx+10h], eax
0x1800115d4  mov     rax, [rsp+78h+arg_40]
0x1800115dc  xor     edi, edi
0x1800115de  test    rax, rax
0x1800115e1  jz      short loc_1800115E8
0x1800115e3  cmp     [rax], di
0x1800115e6  jnz     short loc_1800115EB
0x1800115e8  mov     rax, rdi
0x1800115eb  mov     [rbx+18h], rax
0x1800115ef  call    cs:__imp_GetCurrentThreadId
0x1800115f5  mov     [rbx+20h], eax
0x1800115f8  mov     [rbx+38h], r13
0x1800115fc  mov     eax, [rsp+78h+arg_8]
0x180011603  mov     [rbx+40h], eax
0x180011606  mov     [rbx+44h], ebp
0x180011609  mov     rax, [rsp+78h+arg_20]
0x180011611  mov     [rbx+28h], rax
0x180011615  mov     [rbx+30h], r12
0x180011619  mov     rax, [rsp+78h+arg_28]
0x180011621  mov     [rbx+88h], rax
0x180011628  mov     rax, [rsp+78h+arg_0]
0x180011630  mov     [rbx+90h], rax
0x180011637  mov     [rbx+48h], rdi
0x18001163b  xorps   xmm0, xmm0
0x18001163e  xor     eax, eax
0x180011640  movups  xmmword ptr [rbx+68h], xmm0
0x180011644  mov     [rbx+78h], rax
0x180011648  movups  xmmword ptr [rbx+50h], xmm0
0x18001164c  mov     [rbx+60h], rax
0x180011650  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011657  test    rax, rax
0x18001165a  jz      short loc_180011663
0x18001165c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011661  jmp     short loc_180011666
0x180011663  mov     rax, rdi
0x180011666  mov     [rbx+80h], rax
0x18001166d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011674  test    rax, rax
0x180011677  jz      short loc_180011681
0x180011679  mov     rcx, rbx
0x18001167c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011681  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011688  test    rax, rax
0x18001168b  jz      short loc_1800116A3
0x18001168d  mov     r8d, 400h
0x180011693  mov     rdx, [rsp+78h+arg_60]
0x18001169b  mov     rcx, rbx
0x18001169e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116a3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800116aa  test    rax, rax
0x1800116ad  jz      short loc_1800116B7
0x1800116af  mov     rcx, rbx
0x1800116b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116b7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800116be  test    rax, rax
0x1800116c1  jz      short loc_1800116D1
0x1800116c3  test    byte ptr [rbx+4], 2
0x1800116c7  jnz     short loc_1800116D1
0x1800116c9  mov     rcx, rbx
0x1800116cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800116d1  cmp     [rbx+8], edi
0x1800116d4  jl      short loc_1800116F2
0x1800116d6  cmp     r15d, 3
0x1800116da  jz      short loc_1800116E2
0x1800116dc  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800116e2  mov     ecx, 8000FFFFh; this
0x1800116e7  mov     [rbx+8], ecx
0x1800116ea  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800116ef  mov     [rbx+0Ch], eax
0x1800116f2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800116f9  jnz     short loc_18001171A
0x1800116fb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011702  test    rax, rax
0x180011705  jz      short loc_180011710
0x180011707  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001170c  test    al, al
0x18001170e  jmp     short loc_180011718
0x180011710  call    cs:__imp_IsDebuggerPresent
0x180011716  test    eax, eax
0x180011718  jz      short loc_180011720
0x18001171a  test    byte ptr [rbx+4], 2
0x18001171e  jz      short loc_180011744
0x180011720  mov     rax, cs:g_pfnResultLoggingCallback
0x180011727  test    rax, rax
0x18001172a  jz      short loc_180011788
0x18001172c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011733  jnz     short loc_180011788
0x180011735  xor     r8d, r8d
0x180011738  xor     edx, edx
0x18001173a  mov     rcx, rbx
0x18001173d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011742  jmp     short loc_180011788
0x180011744  mov     ebp, 800h
0x180011749  mov     rax, cs:g_pfnResultLoggingCallback
0x180011750  test    rax, rax
0x180011753  jz      short loc_18001176C
0x180011755  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001175c  jnz     short loc_18001176C
0x18001175e  mov     r8d, ebp
0x180011761  mov     rdx, rsi
0x180011764  mov     rcx, rbx
0x180011767  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001176c  cmp     [rsi], di
0x18001176f  jnz     short loc_18001177F
0x180011771  mov     r8, rbx; unsigned __int64
0x180011774  mov     rdx, rbp; unsigned __int16 *
0x180011777  mov     rcx, rsi; this
0x18001177a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001177f  mov     rcx, rsi; lpOutputString
0x180011782  call    cs:__imp_OutputDebugStringW
0x180011788  test    byte ptr [rbx+4], 4
0x18001178c  jnz     short loc_180011797
0x18001178e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011795  jz      short loc_1800117A9
0x180011797  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001179e  test    rax, rax
0x1800117a1  jz      short loc_1800117A9
0x1800117a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800117a8  nop
0x1800117a9  mov     rbx, [rsp+78h+arg_10]
0x1800117b1  add     rsp, 40h
0x1800117b5  pop     r15
0x1800117b7  pop     r14
0x1800117b9  pop     r13
0x1800117bb  pop     r12
0x1800117bd  pop     rdi
0x1800117be  pop     rsi
0x1800117bf  pop     rbp
0x1800117c0  retn
```
