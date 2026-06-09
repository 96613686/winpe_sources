# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006468`
- end: `0x180006761`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003ddc`

## callees

- `0x1800034d8`
- `0x180005778`
- `0x1800060f0`
- `0x180006468`
- `0x180006b20`
- `0x180006b40`
- `0x180006b54`
- `0x180006b70`
- `0x1800071d4`
- `0x180010010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000658b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000658b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800066aa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800066aa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000671c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000671c`

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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x180006468  mov     [rsp+arg_10], rbx
0x18000646d  mov     [rsp+arg_8], edx
0x180006471  mov     [rsp+arg_0], rcx
0x180006476  push    rbp
0x180006477  push    rsi
0x180006478  push    rdi
0x180006479  push    r12
0x18000647b  push    r13
0x18000647d  push    r14
0x18000647f  push    r15
0x180006481  sub     rsp, 40h
0x180006485  mov     r12, r9
0x180006488  mov     r13, r8
0x18000648b  mov     r10, rcx
0x18000648e  xor     eax, eax
0x180006490  mov     rsi, [rsp+78h+lpOutputString]
0x180006498  mov     [rsi], ax
0x18000649b  mov     rax, [rsp+78h+arg_60]
0x1800064a3  mov     byte ptr [rax], 0
0x1800064a6  mov     r14, [rsp+78h+arg_38]
0x1800064ae  mov     edi, [r14]
0x1800064b1  mov     rbx, [rsp+78h+arg_78]
0x1800064b9  mov     [rbx+8], edi
0x1800064bc  mov     eax, [r14+4]
0x1800064c0  mov     [rbx+0Ch], eax
0x1800064c3  xor     ebp, ebp
0x1800064c5  mov     r15d, [rsp+78h+arg_30]
0x1800064cd  mov     ecx, r15d
0x1800064d0  test    r15d, r15d
0x1800064d3  jz      short loc_18000653B
0x1800064d5  sub     ecx, 1
0x1800064d8  jz      short loc_180006532
0x1800064da  sub     ecx, 1
0x1800064dd  jz      short loc_1800064ED
0x1800064df  cmp     ecx, 1
0x1800064e2  jnz     short loc_180006544
0x1800064e4  mov     ecx, edi; this
0x1800064e6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800064eb  jmp     short loc_180006542
0x1800064ed  test    edi, edi
0x1800064ef  js      short loc_180006529
0x1800064f1  mov     edi, 8007029Ch
0x1800064f6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800064fa  mov     rax, [rsp+78h+arg_28]
0x180006502  mov     [rsp+78h+var_50], rax; __int64
0x180006507  mov     rax, [rsp+78h+arg_20]
0x18000650f  mov     [rsp+78h+var_58], rax; __int64
0x180006514  mov     rcx, r10; int
0x180006517  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000651c  mov     [rbx+8], edi
0x18000651f  mov     ecx, edi; this
0x180006521  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006526  mov     [rbx+0Ch], eax
0x180006529  mov     ecx, edi; this
0x18000652b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006530  jmp     short loc_180006542
0x180006532  mov     ecx, edi; this
0x180006534  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006539  jmp     short loc_180006542
0x18000653b  mov     ecx, edi; this
0x18000653d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006542  mov     ebp, eax
0x180006544  mov     [rbx], r15d
0x180006547  mov     eax, [rsp+78h+arg_70]
0x18000654e  mov     [rbx+4], eax
0x180006551  cmp     dword ptr [r14+8], 1
0x180006556  jnz     short loc_18000655E
0x180006558  or      eax, 8
0x18000655b  mov     [rbx+4], eax
0x18000655e  mov     eax, 1
0x180006563  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000656b  inc     eax
0x18000656d  mov     [rbx+10h], eax
0x180006570  mov     rax, [rsp+78h+arg_40]
0x180006578  xor     edi, edi
0x18000657a  test    rax, rax
0x18000657d  jz      short loc_180006584
0x18000657f  cmp     [rax], di
0x180006582  jnz     short loc_180006587
0x180006584  mov     rax, rdi
0x180006587  mov     [rbx+18h], rax
0x18000658b  call    cs:__imp_GetCurrentThreadId
0x180006591  mov     [rbx+20h], eax
0x180006594  mov     [rbx+38h], r13
0x180006598  mov     eax, [rsp+78h+arg_8]
0x18000659f  mov     [rbx+40h], eax
0x1800065a2  mov     [rbx+44h], ebp
0x1800065a5  mov     rax, [rsp+78h+arg_20]
0x1800065ad  mov     [rbx+28h], rax
0x1800065b1  mov     [rbx+30h], r12
0x1800065b5  mov     rax, [rsp+78h+arg_28]
0x1800065bd  mov     [rbx+88h], rax
0x1800065c4  mov     rax, [rsp+78h+arg_0]
0x1800065cc  mov     [rbx+90h], rax
0x1800065d3  mov     [rbx+48h], rdi
0x1800065d7  xorps   xmm0, xmm0
0x1800065da  xor     eax, eax
0x1800065dc  movups  xmmword ptr [rbx+68h], xmm0
0x1800065e0  mov     [rbx+78h], rax
0x1800065e4  movups  xmmword ptr [rbx+50h], xmm0
0x1800065e8  mov     [rbx+60h], rax
0x1800065ec  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800065f3  test    rax, rax
0x1800065f6  jz      short loc_1800065FF
0x1800065f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065fd  jmp     short loc_180006602
0x1800065ff  mov     rax, rdi
0x180006602  mov     [rbx+80h], rax
0x180006609  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006610  test    rax, rax
0x180006613  jz      short loc_18000661D
0x180006615  mov     rcx, rbx
0x180006618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000661d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006624  test    rax, rax
0x180006627  jz      short loc_18000663F
0x180006629  mov     r8d, 400h
0x18000662f  mov     rdx, [rsp+78h+arg_60]
0x180006637  mov     rcx, rbx
0x18000663a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000663f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006646  test    rax, rax
0x180006649  jz      short loc_180006653
0x18000664b  mov     rcx, rbx
0x18000664e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006653  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000665a  test    rax, rax
0x18000665d  jz      short loc_18000666D
0x18000665f  test    byte ptr [rbx+4], 2
0x180006663  jnz     short loc_18000666D
0x180006665  mov     rcx, rbx
0x180006668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000666d  cmp     [rbx+8], edi
0x180006670  jl      short loc_18000668C
0x180006672  cmp     r15d, 3
0x180006676  jnz     loc_18000675B
0x18000667c  mov     ecx, 8000FFFFh; this
0x180006681  mov     [rbx+8], ecx
0x180006684  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006689  mov     [rbx+0Ch], eax
0x18000668c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006693  jnz     short loc_1800066B4
0x180006695  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000669c  test    rax, rax
0x18000669f  jz      short loc_1800066AA
0x1800066a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066a6  test    al, al
0x1800066a8  jmp     short loc_1800066B2
0x1800066aa  call    cs:__imp_IsDebuggerPresent
0x1800066b0  test    eax, eax
0x1800066b2  jz      short loc_1800066BA
0x1800066b4  test    byte ptr [rbx+4], 2
0x1800066b8  jz      short loc_1800066DE
0x1800066ba  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066c1  test    rax, rax
0x1800066c4  jz      short loc_180006722
0x1800066c6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800066cd  jnz     short loc_180006722
0x1800066cf  xor     r8d, r8d
0x1800066d2  xor     edx, edx
0x1800066d4  mov     rcx, rbx
0x1800066d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066dc  jmp     short loc_180006722
0x1800066de  mov     ebp, 800h
0x1800066e3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800066ea  test    rax, rax
0x1800066ed  jz      short loc_180006706
0x1800066ef  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800066f6  jnz     short loc_180006706
0x1800066f8  mov     r8d, ebp
0x1800066fb  mov     rdx, rsi
0x1800066fe  mov     rcx, rbx
0x180006701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006706  cmp     [rsi], di
0x180006709  jnz     short loc_180006719
0x18000670b  mov     r8, rbx; unsigned __int64
0x18000670e  mov     rdx, rbp; wchar_t *
0x180006711  mov     rcx, rsi; this
0x180006714  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180006719  mov     rcx, rsi; lpOutputString
0x18000671c  call    cs:__imp_OutputDebugStringW
0x180006722  test    byte ptr [rbx+4], 4
0x180006726  jnz     short loc_180006731
0x180006728  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000672f  jz      short loc_180006743
0x180006731  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006738  test    rax, rax
0x18000673b  jz      short loc_180006743
0x18000673d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006742  nop
0x180006743  mov     rbx, [rsp+78h+arg_10]
0x18000674b  add     rsp, 40h
0x18000674f  pop     r15
0x180006751  pop     r14
0x180006753  pop     r13
0x180006755  pop     r12
0x180006757  pop     rdi
0x180006758  pop     rsi
0x180006759  pop     rbp
0x18000675a  retn
0x18000675b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
