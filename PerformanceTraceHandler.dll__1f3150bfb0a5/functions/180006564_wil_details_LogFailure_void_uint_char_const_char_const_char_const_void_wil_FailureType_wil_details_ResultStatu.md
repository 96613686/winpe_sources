# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006564`
- end: `0x180006859`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180003e70`
- `0x180003f30`
- `0x18000402c`
- `0x18000f1c4`

## callees

- `0x180003dbc`
- `0x180005904`
- `0x180006160`
- `0x180006564`
- `0x180007484`
- `0x1800074a0`
- `0x180007624`
- `0x180007640`
- `0x180009390`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006687`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006687`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000681a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000681a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800067a8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800067a8`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180006564  mov     [rsp+arg_10], rbx
0x180006569  mov     [rsp+arg_8], edx
0x18000656d  mov     [rsp+arg_0], rcx
0x180006572  push    rbp
0x180006573  push    rsi
0x180006574  push    rdi
0x180006575  push    r12
0x180006577  push    r13
0x180006579  push    r14
0x18000657b  push    r15
0x18000657d  sub     rsp, 40h
0x180006581  mov     r12, r9
0x180006584  mov     r13, r8
0x180006587  mov     r10, rcx
0x18000658a  xor     eax, eax
0x18000658c  mov     rsi, [rsp+78h+lpOutputString]
0x180006594  mov     [rsi], ax
0x180006597  mov     rax, [rsp+78h+arg_60]
0x18000659f  mov     byte ptr [rax], 0
0x1800065a2  mov     r14, [rsp+78h+arg_38]
0x1800065aa  mov     edi, [r14]
0x1800065ad  mov     rbx, [rsp+78h+arg_78]
0x1800065b5  mov     [rbx+8], edi
0x1800065b8  mov     eax, [r14+4]
0x1800065bc  mov     [rbx+0Ch], eax
0x1800065bf  xor     ebp, ebp
0x1800065c1  mov     r15d, [rsp+78h+arg_30]
0x1800065c9  mov     ecx, r15d
0x1800065cc  test    r15d, r15d
0x1800065cf  jz      short loc_180006637
0x1800065d1  sub     ecx, 1
0x1800065d4  jz      short loc_18000662E
0x1800065d6  sub     ecx, 1
0x1800065d9  jz      short loc_1800065E9
0x1800065db  cmp     ecx, 1
0x1800065de  jnz     short loc_180006640
0x1800065e0  mov     ecx, edi; this
0x1800065e2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800065e7  jmp     short loc_18000663E
0x1800065e9  test    edi, edi
0x1800065eb  js      short loc_180006625
0x1800065ed  mov     edi, 8007029Ch
0x1800065f2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800065f6  mov     rax, [rsp+78h+arg_28]
0x1800065fe  mov     [rsp+78h+var_50], rax; __int64
0x180006603  mov     rax, [rsp+78h+arg_20]
0x18000660b  mov     [rsp+78h+var_58], rax; __int64
0x180006610  mov     rcx, r10; int
0x180006613  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006618  mov     [rbx+8], edi
0x18000661b  mov     ecx, edi; this
0x18000661d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006622  mov     [rbx+0Ch], eax
0x180006625  mov     ecx, edi; this
0x180006627  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000662c  jmp     short loc_18000663E
0x18000662e  mov     ecx, edi; this
0x180006630  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006635  jmp     short loc_18000663E
0x180006637  mov     ecx, edi; this
0x180006639  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000663e  mov     ebp, eax
0x180006640  mov     [rbx], r15d
0x180006643  mov     eax, [rsp+78h+arg_70]
0x18000664a  mov     [rbx+4], eax
0x18000664d  cmp     dword ptr [r14+8], 1
0x180006652  jnz     short loc_18000665A
0x180006654  or      eax, 8
0x180006657  mov     [rbx+4], eax
0x18000665a  mov     eax, 1
0x18000665f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006667  inc     eax
0x180006669  mov     [rbx+10h], eax
0x18000666c  mov     rax, [rsp+78h+arg_40]
0x180006674  xor     edi, edi
0x180006676  test    rax, rax
0x180006679  jz      short loc_180006680
0x18000667b  cmp     [rax], di
0x18000667e  jnz     short loc_180006683
0x180006680  mov     rax, rdi
0x180006683  mov     [rbx+18h], rax
0x180006687  call    cs:__imp_GetCurrentThreadId
0x18000668d  mov     [rbx+20h], eax
0x180006690  mov     [rbx+38h], r13
0x180006694  mov     eax, [rsp+78h+arg_8]
0x18000669b  mov     [rbx+40h], eax
0x18000669e  mov     [rbx+44h], ebp
0x1800066a1  mov     rax, [rsp+78h+arg_20]
0x1800066a9  mov     [rbx+28h], rax
0x1800066ad  mov     [rbx+30h], r12
0x1800066b1  mov     rax, [rsp+78h+arg_28]
0x1800066b9  mov     [rbx+88h], rax
0x1800066c0  mov     rax, [rsp+78h+arg_0]
0x1800066c8  mov     [rbx+90h], rax
0x1800066cf  mov     [rbx+48h], rdi
0x1800066d3  xorps   xmm0, xmm0
0x1800066d6  xor     eax, eax
0x1800066d8  movups  xmmword ptr [rbx+68h], xmm0
0x1800066dc  mov     [rbx+78h], rax
0x1800066e0  movups  xmmword ptr [rbx+50h], xmm0
0x1800066e4  mov     [rbx+60h], rax
0x1800066e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800066ef  test    rax, rax
0x1800066f2  jz      short loc_1800066FB
0x1800066f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f9  jmp     short loc_1800066FE
0x1800066fb  mov     rax, rdi
0x1800066fe  mov     [rbx+80h], rax
0x180006705  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000670c  test    rax, rax
0x18000670f  jz      short loc_180006719
0x180006711  mov     rcx, rbx
0x180006714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006719  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006720  test    rax, rax
0x180006723  jz      short loc_18000673B
0x180006725  mov     r8d, 400h
0x18000672b  mov     rdx, [rsp+78h+arg_60]
0x180006733  mov     rcx, rbx
0x180006736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000673b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006742  test    rax, rax
0x180006745  jz      short loc_18000674F
0x180006747  mov     rcx, rbx
0x18000674a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000674f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006756  test    rax, rax
0x180006759  jz      short loc_180006769
0x18000675b  test    byte ptr [rbx+4], 2
0x18000675f  jnz     short loc_180006769
0x180006761  mov     rcx, rbx
0x180006764  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006769  cmp     [rbx+8], edi
0x18000676c  jl      short loc_18000678A
0x18000676e  cmp     r15d, 3
0x180006772  jz      short loc_18000677A
0x180006774  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000677a  mov     ecx, 8000FFFFh; this
0x18000677f  mov     [rbx+8], ecx
0x180006782  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006787  mov     [rbx+0Ch], eax
0x18000678a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006791  jnz     short loc_1800067B2
0x180006793  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000679a  test    rax, rax
0x18000679d  jz      short loc_1800067A8
0x18000679f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067a4  test    al, al
0x1800067a6  jmp     short loc_1800067B0
0x1800067a8  call    cs:__imp_IsDebuggerPresent
0x1800067ae  test    eax, eax
0x1800067b0  jz      short loc_1800067B8
0x1800067b2  test    byte ptr [rbx+4], 2
0x1800067b6  jz      short loc_1800067DC
0x1800067b8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800067bf  test    rax, rax
0x1800067c2  jz      short loc_180006820
0x1800067c4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800067cb  jnz     short loc_180006820
0x1800067cd  xor     r8d, r8d
0x1800067d0  xor     edx, edx
0x1800067d2  mov     rcx, rbx
0x1800067d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800067da  jmp     short loc_180006820
0x1800067dc  mov     ebp, 800h
0x1800067e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800067e8  test    rax, rax
0x1800067eb  jz      short loc_180006804
0x1800067ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800067f4  jnz     short loc_180006804
0x1800067f6  mov     r8d, ebp
0x1800067f9  mov     rdx, rsi
0x1800067fc  mov     rcx, rbx
0x1800067ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006804  cmp     [rsi], di
0x180006807  jnz     short loc_180006817
0x180006809  mov     r8, rbx; unsigned __int64
0x18000680c  mov     rdx, rbp; unsigned __int16 *
0x18000680f  mov     rcx, rsi; this
0x180006812  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006817  mov     rcx, rsi; lpOutputString
0x18000681a  call    cs:__imp_OutputDebugStringW
0x180006820  test    byte ptr [rbx+4], 4
0x180006824  jnz     short loc_18000682F
0x180006826  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000682d  jz      short loc_180006841
0x18000682f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006836  test    rax, rax
0x180006839  jz      short loc_180006841
0x18000683b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006840  nop
0x180006841  mov     rbx, [rsp+78h+arg_10]
0x180006849  add     rsp, 40h
0x18000684d  pop     r15
0x18000684f  pop     r14
0x180006851  pop     r13
0x180006853  pop     r12
0x180006855  pop     rdi
0x180006856  pop     rsi
0x180006857  pop     rbp
0x180006858  retn
```
