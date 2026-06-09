# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800067dc`
- end: `0x180006ad5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004dd4`
- `0x180005140`
- `0x180009cd4`

## callees

- `0x180004d08`
- `0x180005dc4`
- `0x1800065ec`
- `0x1800067dc`
- `0x180006ed0`
- `0x180006ef0`
- `0x180006f04`
- `0x180006f20`
- `0x180007d14`
- `0x18004e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800068ff`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006a90`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006a90`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006a1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006a1e`

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
0x1800067dc  mov     [rsp+arg_10], rbx
0x1800067e1  mov     [rsp+arg_8], edx
0x1800067e5  mov     [rsp+arg_0], rcx
0x1800067ea  push    rbp
0x1800067eb  push    rsi
0x1800067ec  push    rdi
0x1800067ed  push    r12
0x1800067ef  push    r13
0x1800067f1  push    r14
0x1800067f3  push    r15
0x1800067f5  sub     rsp, 40h
0x1800067f9  mov     r12, r9
0x1800067fc  mov     r13, r8
0x1800067ff  mov     r10, rcx
0x180006802  xor     eax, eax
0x180006804  mov     rsi, [rsp+78h+lpOutputString]
0x18000680c  mov     [rsi], ax
0x18000680f  mov     rax, [rsp+78h+arg_60]
0x180006817  mov     byte ptr [rax], 0
0x18000681a  mov     r14, [rsp+78h+arg_38]
0x180006822  mov     edi, [r14]
0x180006825  mov     rbx, [rsp+78h+arg_78]
0x18000682d  mov     [rbx+8], edi
0x180006830  mov     eax, [r14+4]
0x180006834  mov     [rbx+0Ch], eax
0x180006837  xor     ebp, ebp
0x180006839  mov     r15d, [rsp+78h+arg_30]
0x180006841  mov     ecx, r15d
0x180006844  test    r15d, r15d
0x180006847  jz      short loc_1800068AF
0x180006849  sub     ecx, 1
0x18000684c  jz      short loc_1800068A6
0x18000684e  sub     ecx, 1
0x180006851  jz      short loc_180006861
0x180006853  cmp     ecx, 1
0x180006856  jnz     short loc_1800068B8
0x180006858  mov     ecx, edi; this
0x18000685a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000685f  jmp     short loc_1800068B6
0x180006861  test    edi, edi
0x180006863  js      short loc_18000689D
0x180006865  mov     edi, 8007029Ch
0x18000686a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000686e  mov     rax, [rsp+78h+arg_28]
0x180006876  mov     [rsp+78h+var_50], rax; __int64
0x18000687b  mov     rax, [rsp+78h+arg_20]
0x180006883  mov     [rsp+78h+var_58], rax; __int64
0x180006888  mov     rcx, r10; int
0x18000688b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006890  mov     [rbx+8], edi
0x180006893  mov     ecx, edi; this
0x180006895  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000689a  mov     [rbx+0Ch], eax
0x18000689d  mov     ecx, edi; this
0x18000689f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800068a4  jmp     short loc_1800068B6
0x1800068a6  mov     ecx, edi; this
0x1800068a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800068ad  jmp     short loc_1800068B6
0x1800068af  mov     ecx, edi; this
0x1800068b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800068b6  mov     ebp, eax
0x1800068b8  mov     [rbx], r15d
0x1800068bb  mov     eax, [rsp+78h+arg_70]
0x1800068c2  mov     [rbx+4], eax
0x1800068c5  cmp     dword ptr [r14+8], 1
0x1800068ca  jnz     short loc_1800068D2
0x1800068cc  or      eax, 8
0x1800068cf  mov     [rbx+4], eax
0x1800068d2  mov     eax, 1
0x1800068d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800068df  inc     eax
0x1800068e1  mov     [rbx+10h], eax
0x1800068e4  mov     rax, [rsp+78h+arg_40]
0x1800068ec  xor     edi, edi
0x1800068ee  test    rax, rax
0x1800068f1  jz      short loc_1800068F8
0x1800068f3  cmp     [rax], di
0x1800068f6  jnz     short loc_1800068FB
0x1800068f8  mov     rax, rdi
0x1800068fb  mov     [rbx+18h], rax
0x1800068ff  call    cs:__imp_GetCurrentThreadId
0x180006905  mov     [rbx+20h], eax
0x180006908  mov     [rbx+38h], r13
0x18000690c  mov     eax, [rsp+78h+arg_8]
0x180006913  mov     [rbx+40h], eax
0x180006916  mov     [rbx+44h], ebp
0x180006919  mov     rax, [rsp+78h+arg_20]
0x180006921  mov     [rbx+28h], rax
0x180006925  mov     [rbx+30h], r12
0x180006929  mov     rax, [rsp+78h+arg_28]
0x180006931  mov     [rbx+88h], rax
0x180006938  mov     rax, [rsp+78h+arg_0]
0x180006940  mov     [rbx+90h], rax
0x180006947  mov     [rbx+48h], rdi
0x18000694b  xorps   xmm0, xmm0
0x18000694e  xor     eax, eax
0x180006950  movups  xmmword ptr [rbx+68h], xmm0
0x180006954  mov     [rbx+78h], rax
0x180006958  movups  xmmword ptr [rbx+50h], xmm0
0x18000695c  mov     [rbx+60h], rax
0x180006960  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006967  test    rax, rax
0x18000696a  jz      short loc_180006973
0x18000696c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006971  jmp     short loc_180006976
0x180006973  mov     rax, rdi
0x180006976  mov     [rbx+80h], rax
0x18000697d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006984  test    rax, rax
0x180006987  jz      short loc_180006991
0x180006989  mov     rcx, rbx
0x18000698c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006991  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006998  test    rax, rax
0x18000699b  jz      short loc_1800069B3
0x18000699d  mov     r8d, 400h
0x1800069a3  mov     rdx, [rsp+78h+arg_60]
0x1800069ab  mov     rcx, rbx
0x1800069ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069b3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800069ba  test    rax, rax
0x1800069bd  jz      short loc_1800069C7
0x1800069bf  mov     rcx, rbx
0x1800069c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069c7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800069ce  test    rax, rax
0x1800069d1  jz      short loc_1800069E1
0x1800069d3  test    byte ptr [rbx+4], 2
0x1800069d7  jnz     short loc_1800069E1
0x1800069d9  mov     rcx, rbx
0x1800069dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800069e1  cmp     [rbx+8], edi
0x1800069e4  jl      short loc_180006A00
0x1800069e6  cmp     r15d, 3
0x1800069ea  jnz     loc_180006ACF
0x1800069f0  mov     ecx, 8000FFFFh; this
0x1800069f5  mov     [rbx+8], ecx
0x1800069f8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800069fd  mov     [rbx+0Ch], eax
0x180006a00  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006a07  jnz     short loc_180006A28
0x180006a09  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006a10  test    rax, rax
0x180006a13  jz      short loc_180006A1E
0x180006a15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a1a  test    al, al
0x180006a1c  jmp     short loc_180006A26
0x180006a1e  call    cs:__imp_IsDebuggerPresent
0x180006a24  test    eax, eax
0x180006a26  jz      short loc_180006A2E
0x180006a28  test    byte ptr [rbx+4], 2
0x180006a2c  jz      short loc_180006A52
0x180006a2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a35  test    rax, rax
0x180006a38  jz      short loc_180006A96
0x180006a3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006a41  jnz     short loc_180006A96
0x180006a43  xor     r8d, r8d
0x180006a46  xor     edx, edx
0x180006a48  mov     rcx, rbx
0x180006a4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a50  jmp     short loc_180006A96
0x180006a52  mov     ebp, 800h
0x180006a57  mov     rax, cs:g_pfnResultLoggingCallback
0x180006a5e  test    rax, rax
0x180006a61  jz      short loc_180006A7A
0x180006a63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006a6a  jnz     short loc_180006A7A
0x180006a6c  mov     r8d, ebp
0x180006a6f  mov     rdx, rsi
0x180006a72  mov     rcx, rbx
0x180006a75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006a7a  cmp     [rsi], di
0x180006a7d  jnz     short loc_180006A8D
0x180006a7f  mov     r8, rbx; unsigned __int64
0x180006a82  mov     rdx, rbp; unsigned __int16 *
0x180006a85  mov     rcx, rsi; this
0x180006a88  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006a8d  mov     rcx, rsi; lpOutputString
0x180006a90  call    cs:__imp_OutputDebugStringW
0x180006a96  test    byte ptr [rbx+4], 4
0x180006a9a  jnz     short loc_180006AA5
0x180006a9c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006aa3  jz      short loc_180006AB7
0x180006aa5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006aac  test    rax, rax
0x180006aaf  jz      short loc_180006AB7
0x180006ab1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab6  nop
0x180006ab7  mov     rbx, [rsp+78h+arg_10]
0x180006abf  add     rsp, 40h
0x180006ac3  pop     r15
0x180006ac5  pop     r14
0x180006ac7  pop     r13
0x180006ac9  pop     r12
0x180006acb  pop     rdi
0x180006acc  pop     rsi
0x180006acd  pop     rbp
0x180006ace  retn
0x180006acf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
