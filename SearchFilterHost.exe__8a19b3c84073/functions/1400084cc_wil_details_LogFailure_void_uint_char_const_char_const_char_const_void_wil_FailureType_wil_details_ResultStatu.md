# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400084cc`
- end: `0x1400087d1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `773`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140005780`
- `0x140005af4`
- `0x140018bfc`

## callees

- `0x1400056b8`
- `0x140007874`
- `0x1400080e8`
- `0x1400084cc`
- `0x140009428`
- `0x140009450`
- `0x1400095e0`
- `0x1400095fc`
- `0x14000b524`
- `0x14004f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400085fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400085fb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000878c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000878c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000871a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000871a`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1400084cc  mov     rax, rsp
0x1400084cf  mov     [rax+10h], edx
0x1400084d2  mov     [rax+8], rcx
0x1400084d6  push    rbp
0x1400084d7  push    rsi
0x1400084d8  push    rdi
0x1400084d9  push    r12
0x1400084db  push    r13
0x1400084dd  push    r14
0x1400084df  push    r15
0x1400084e1  sub     rsp, 50h
0x1400084e5  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x1400084ed  mov     [rax+18h], rbx
0x1400084f1  mov     r12, r9
0x1400084f4  mov     r13, r8
0x1400084f7  mov     r10, rcx
0x1400084fa  xor     eax, eax
0x1400084fc  mov     rsi, [rsp+88h+lpOutputString]
0x140008504  mov     [rsi], ax
0x140008507  mov     rax, [rsp+88h+arg_60]
0x14000850f  mov     byte ptr [rax], 0
0x140008512  mov     r14, [rsp+88h+arg_38]
0x14000851a  mov     edi, [r14]
0x14000851d  mov     rbx, [rsp+88h+arg_78]
0x140008525  mov     [rbx+8], edi
0x140008528  mov     eax, [r14+4]
0x14000852c  mov     [rbx+0Ch], eax
0x14000852f  xor     ebp, ebp
0x140008531  mov     r15d, [rsp+88h+arg_30]
0x140008539  mov     ecx, r15d
0x14000853c  test    r15d, r15d
0x14000853f  jz      short loc_1400085AB
0x140008541  sub     ecx, 1
0x140008544  jz      short loc_1400085A2
0x140008546  sub     ecx, 1
0x140008549  jz      short loc_140008559
0x14000854b  cmp     ecx, 1
0x14000854e  jnz     short loc_1400085B4
0x140008550  mov     ecx, edi; this
0x140008552  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140008557  jmp     short loc_1400085B2
0x140008559  test    edi, edi
0x14000855b  js      short loc_140008599
0x14000855d  mov     [rsp+88h+var_50], ebp
0x140008561  mov     edi, 8007029Ch
0x140008566  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x14000856a  mov     rax, [rsp+88h+arg_28]
0x140008572  mov     [rsp+88h+var_60], rax; __int64
0x140008577  mov     rax, [rsp+88h+arg_20]
0x14000857f  mov     [rsp+88h+var_68], rax; __int64
0x140008584  mov     rcx, r10; int
0x140008587  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000858c  mov     [rbx+8], edi
0x14000858f  mov     ecx, edi; this
0x140008591  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140008596  mov     [rbx+0Ch], eax
0x140008599  mov     ecx, edi; this
0x14000859b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400085a0  jmp     short loc_1400085B2
0x1400085a2  mov     ecx, edi; this
0x1400085a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400085a9  jmp     short loc_1400085B2
0x1400085ab  mov     ecx, edi; this
0x1400085ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400085b2  mov     ebp, eax
0x1400085b4  mov     [rbx], r15d
0x1400085b7  mov     eax, [rsp+88h+arg_70]
0x1400085be  mov     [rbx+4], eax
0x1400085c1  cmp     dword ptr [r14+8], 1
0x1400085c6  jnz     short loc_1400085CE
0x1400085c8  or      eax, 8
0x1400085cb  mov     [rbx+4], eax
0x1400085ce  mov     eax, 1
0x1400085d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400085db  inc     eax
0x1400085dd  mov     [rbx+10h], eax
0x1400085e0  mov     rax, [rsp+88h+arg_40]
0x1400085e8  xor     edi, edi
0x1400085ea  test    rax, rax
0x1400085ed  jz      short loc_1400085F4
0x1400085ef  cmp     [rax], di
0x1400085f2  jnz     short loc_1400085F7
0x1400085f4  mov     rax, rdi
0x1400085f7  mov     [rbx+18h], rax
0x1400085fb  call    cs:__imp_GetCurrentThreadId
0x140008601  mov     [rbx+20h], eax
0x140008604  mov     [rbx+38h], r13
0x140008608  mov     eax, [rsp+88h+arg_8]
0x14000860f  mov     [rbx+40h], eax
0x140008612  mov     [rbx+44h], ebp
0x140008615  mov     rax, [rsp+88h+arg_20]
0x14000861d  mov     [rbx+28h], rax
0x140008621  mov     [rbx+30h], r12
0x140008625  mov     rax, [rsp+88h+arg_28]
0x14000862d  mov     [rbx+88h], rax
0x140008634  mov     rax, [rsp+88h+arg_0]
0x14000863c  mov     [rbx+90h], rax
0x140008643  mov     [rbx+48h], rdi
0x140008647  xorps   xmm0, xmm0
0x14000864a  xor     eax, eax
0x14000864c  movups  xmmword ptr [rbx+68h], xmm0
0x140008650  mov     [rbx+78h], rax
0x140008654  movups  xmmword ptr [rbx+50h], xmm0
0x140008658  mov     [rbx+60h], rax
0x14000865c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140008663  test    rax, rax
0x140008666  jz      short loc_14000866F
0x140008668  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000866d  jmp     short loc_140008672
0x14000866f  mov     rax, rdi
0x140008672  mov     [rbx+80h], rax
0x140008679  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140008680  test    rax, rax
0x140008683  jz      short loc_14000868D
0x140008685  mov     rcx, rbx
0x140008688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000868d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140008694  test    rax, rax
0x140008697  jz      short loc_1400086AF
0x140008699  mov     r8d, 400h
0x14000869f  mov     rdx, [rsp+88h+arg_60]
0x1400086a7  mov     rcx, rbx
0x1400086aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086af  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400086b6  test    rax, rax
0x1400086b9  jz      short loc_1400086C3
0x1400086bb  mov     rcx, rbx
0x1400086be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400086ca  test    rax, rax
0x1400086cd  jz      short loc_1400086DD
0x1400086cf  test    byte ptr [rbx+4], 2
0x1400086d3  jnz     short loc_1400086DD
0x1400086d5  mov     rcx, rbx
0x1400086d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400086dd  cmp     [rbx+8], edi
0x1400086e0  jl      short loc_1400086FC
0x1400086e2  cmp     r15d, 3
0x1400086e6  jnz     loc_1400087CB
0x1400086ec  mov     ecx, 8000FFFFh; this
0x1400086f1  mov     [rbx+8], ecx
0x1400086f4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400086f9  mov     [rbx+0Ch], eax
0x1400086fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140008703  jnz     short loc_140008724
0x140008705  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000870c  test    rax, rax
0x14000870f  jz      short loc_14000871A
0x140008711  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008716  test    al, al
0x140008718  jmp     short loc_140008722
0x14000871a  call    cs:__imp_IsDebuggerPresent
0x140008720  test    eax, eax
0x140008722  jz      short loc_14000872A
0x140008724  test    byte ptr [rbx+4], 2
0x140008728  jz      short loc_14000874E
0x14000872a  mov     rax, cs:g_pfnResultLoggingCallback
0x140008731  test    rax, rax
0x140008734  jz      short loc_140008792
0x140008736  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000873d  jnz     short loc_140008792
0x14000873f  xor     r8d, r8d
0x140008742  xor     edx, edx
0x140008744  mov     rcx, rbx
0x140008747  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000874c  jmp     short loc_140008792
0x14000874e  mov     ebp, 800h
0x140008753  mov     rax, cs:g_pfnResultLoggingCallback
0x14000875a  test    rax, rax
0x14000875d  jz      short loc_140008776
0x14000875f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140008766  jnz     short loc_140008776
0x140008768  mov     r8d, ebp
0x14000876b  mov     rdx, rsi
0x14000876e  mov     rcx, rbx
0x140008771  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008776  cmp     [rsi], di
0x140008779  jnz     short loc_140008789
0x14000877b  mov     r8, rbx; unsigned __int64
0x14000877e  mov     rdx, rbp; wchar_t *
0x140008781  mov     rcx, rsi; this
0x140008784  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140008789  mov     rcx, rsi; lpOutputString
0x14000878c  call    cs:__imp_OutputDebugStringW
0x140008792  test    byte ptr [rbx+4], 4
0x140008796  jnz     short loc_1400087A1
0x140008798  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000879f  jz      short loc_1400087B3
0x1400087a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400087a8  test    rax, rax
0x1400087ab  jz      short loc_1400087B3
0x1400087ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400087b2  nop
0x1400087b3  mov     rbx, [rsp+88h+arg_10]
0x1400087bb  add     rsp, 50h
0x1400087bf  pop     r15
0x1400087c1  pop     r14
0x1400087c3  pop     r13
0x1400087c5  pop     r12
0x1400087c7  pop     rdi
0x1400087c8  pop     rsi
0x1400087c9  pop     rbp
0x1400087ca  retn
0x1400087cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
