# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400055b8`
- end: `0x1400058c4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1400026e0`
- `0x140002790`
- `0x140002b44`

## callees

- `0x1400025c8`
- `0x1400044e4`
- `0x1400053c4`
- `0x1400055b8`
- `0x140005cc0`
- `0x140005ce0`
- `0x140005cf4`
- `0x140005d14`
- `0x14000738c`
- `0x14000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400056db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400056db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005800`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005800`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005878`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005878`

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
0x1400055b8  mov     [rsp+arg_10], rbx
0x1400055bd  mov     [rsp+arg_8], edx
0x1400055c1  mov     [rsp+arg_0], rcx
0x1400055c6  push    rbp
0x1400055c7  push    rsi
0x1400055c8  push    rdi
0x1400055c9  push    r12
0x1400055cb  push    r13
0x1400055cd  push    r14
0x1400055cf  push    r15
0x1400055d1  sub     rsp, 40h
0x1400055d5  mov     r12, r9
0x1400055d8  mov     r13, r8
0x1400055db  mov     r10, rcx
0x1400055de  xor     eax, eax
0x1400055e0  mov     rsi, [rsp+78h+lpOutputString]
0x1400055e8  mov     [rsi], ax
0x1400055eb  mov     rax, [rsp+78h+arg_60]
0x1400055f3  mov     byte ptr [rax], 0
0x1400055f6  mov     r14, [rsp+78h+arg_38]
0x1400055fe  mov     edi, [r14]
0x140005601  mov     rbx, [rsp+78h+arg_78]
0x140005609  mov     [rbx+8], edi
0x14000560c  mov     eax, [r14+4]
0x140005610  mov     [rbx+0Ch], eax
0x140005613  xor     ebp, ebp
0x140005615  mov     r15d, [rsp+78h+arg_30]
0x14000561d  mov     ecx, r15d
0x140005620  test    r15d, r15d
0x140005623  jz      short loc_14000568B
0x140005625  sub     ecx, 1
0x140005628  jz      short loc_140005682
0x14000562a  sub     ecx, 1
0x14000562d  jz      short loc_14000563D
0x14000562f  cmp     ecx, 1
0x140005632  jnz     short loc_140005694
0x140005634  mov     ecx, edi; this
0x140005636  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000563b  jmp     short loc_140005692
0x14000563d  test    edi, edi
0x14000563f  js      short loc_140005679
0x140005641  mov     edi, 8007029Ch
0x140005646  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000564a  mov     rax, [rsp+78h+arg_28]
0x140005652  mov     [rsp+78h+var_50], rax; __int64
0x140005657  mov     rax, [rsp+78h+arg_20]
0x14000565f  mov     [rsp+78h+var_58], rax; __int64
0x140005664  mov     rcx, r10; int
0x140005667  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000566c  mov     [rbx+8], edi
0x14000566f  mov     ecx, edi; this
0x140005671  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005676  mov     [rbx+0Ch], eax
0x140005679  mov     ecx, edi; this
0x14000567b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005680  jmp     short loc_140005692
0x140005682  mov     ecx, edi; this
0x140005684  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005689  jmp     short loc_140005692
0x14000568b  mov     ecx, edi; this
0x14000568d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005692  mov     ebp, eax
0x140005694  mov     [rbx], r15d
0x140005697  mov     eax, [rsp+78h+arg_70]
0x14000569e  mov     [rbx+4], eax
0x1400056a1  cmp     dword ptr [r14+8], 1
0x1400056a6  jnz     short loc_1400056AE
0x1400056a8  or      eax, 8
0x1400056ab  mov     [rbx+4], eax
0x1400056ae  mov     eax, 1
0x1400056b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400056bb  inc     eax
0x1400056bd  mov     [rbx+10h], eax
0x1400056c0  mov     rax, [rsp+78h+arg_40]
0x1400056c8  xor     edi, edi
0x1400056ca  test    rax, rax
0x1400056cd  jz      short loc_1400056D4
0x1400056cf  cmp     [rax], di
0x1400056d2  jnz     short loc_1400056D7
0x1400056d4  mov     rax, rdi
0x1400056d7  mov     [rbx+18h], rax
0x1400056db  call    cs:__imp_GetCurrentThreadId
0x1400056e2  nop     dword ptr [rax+rax+00h]
0x1400056e7  mov     [rbx+20h], eax
0x1400056ea  mov     [rbx+38h], r13
0x1400056ee  mov     eax, [rsp+78h+arg_8]
0x1400056f5  mov     [rbx+40h], eax
0x1400056f8  mov     [rbx+44h], ebp
0x1400056fb  mov     rax, [rsp+78h+arg_20]
0x140005703  mov     [rbx+28h], rax
0x140005707  mov     [rbx+30h], r12
0x14000570b  mov     rax, [rsp+78h+arg_28]
0x140005713  mov     [rbx+88h], rax
0x14000571a  mov     rax, [rsp+78h+arg_0]
0x140005722  mov     [rbx+90h], rax
0x140005729  mov     [rbx+48h], rdi
0x14000572d  xorps   xmm0, xmm0
0x140005730  xor     eax, eax
0x140005732  movups  xmmword ptr [rbx+68h], xmm0
0x140005736  mov     [rbx+78h], rax
0x14000573a  movups  xmmword ptr [rbx+50h], xmm0
0x14000573e  mov     [rbx+60h], rax
0x140005742  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005749  test    rax, rax
0x14000574c  jz      short loc_140005755
0x14000574e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005753  jmp     short loc_140005758
0x140005755  mov     rax, rdi
0x140005758  mov     [rbx+80h], rax
0x14000575f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005766  test    rax, rax
0x140005769  jz      short loc_140005773
0x14000576b  mov     rcx, rbx
0x14000576e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005773  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000577a  test    rax, rax
0x14000577d  jz      short loc_140005795
0x14000577f  mov     r8d, 400h
0x140005785  mov     rdx, [rsp+78h+arg_60]
0x14000578d  mov     rcx, rbx
0x140005790  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005795  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000579c  test    rax, rax
0x14000579f  jz      short loc_1400057A9
0x1400057a1  mov     rcx, rbx
0x1400057a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057a9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400057b0  test    rax, rax
0x1400057b3  jz      short loc_1400057C3
0x1400057b5  test    byte ptr [rbx+4], 2
0x1400057b9  jnz     short loc_1400057C3
0x1400057bb  mov     rcx, rbx
0x1400057be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057c3  cmp     [rbx+8], edi
0x1400057c6  jl      short loc_1400057E2
0x1400057c8  cmp     r15d, 3
0x1400057cc  jnz     loc_1400058BE
0x1400057d2  mov     ecx, 8000FFFFh; this
0x1400057d7  mov     [rbx+8], ecx
0x1400057da  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400057df  mov     [rbx+0Ch], eax
0x1400057e2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400057e9  jnz     short loc_140005810
0x1400057eb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400057f2  test    rax, rax
0x1400057f5  jz      short loc_140005800
0x1400057f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400057fc  test    al, al
0x1400057fe  jmp     short loc_14000580E
0x140005800  call    cs:__imp_IsDebuggerPresent
0x140005807  nop     dword ptr [rax+rax+00h]
0x14000580c  test    eax, eax
0x14000580e  jz      short loc_140005816
0x140005810  test    byte ptr [rbx+4], 2
0x140005814  jz      short loc_14000583A
0x140005816  mov     rax, cs:g_pfnResultLoggingCallback
0x14000581d  test    rax, rax
0x140005820  jz      short loc_140005884
0x140005822  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005829  jnz     short loc_140005884
0x14000582b  xor     r8d, r8d
0x14000582e  xor     edx, edx
0x140005830  mov     rcx, rbx
0x140005833  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005838  jmp     short loc_140005884
0x14000583a  mov     ebp, 800h
0x14000583f  mov     rax, cs:g_pfnResultLoggingCallback
0x140005846  test    rax, rax
0x140005849  jz      short loc_140005862
0x14000584b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005852  jnz     short loc_140005862
0x140005854  mov     r8d, ebp
0x140005857  mov     rdx, rsi
0x14000585a  mov     rcx, rbx
0x14000585d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005862  cmp     [rsi], di
0x140005865  jnz     short loc_140005875
0x140005867  mov     r8, rbx; unsigned __int64
0x14000586a  mov     rdx, rbp; unsigned __int16 *
0x14000586d  mov     rcx, rsi; this
0x140005870  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005875  mov     rcx, rsi; lpOutputString
0x140005878  call    cs:__imp_OutputDebugStringW
0x14000587f  nop     dword ptr [rax+rax+00h]
0x140005884  test    byte ptr [rbx+4], 4
0x140005888  jnz     short loc_140005893
0x14000588a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005891  jz      short loc_1400058A5
0x140005893  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000589a  test    rax, rax
0x14000589d  jz      short loc_1400058A5
0x14000589f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400058a4  nop
0x1400058a5  mov     rbx, [rsp+78h+arg_10]
0x1400058ad  add     rsp, 40h
0x1400058b1  pop     r15
0x1400058b3  pop     r14
0x1400058b5  pop     r13
0x1400058b7  pop     r12
0x1400058b9  pop     rdi
0x1400058ba  pop     rsi
0x1400058bb  pop     rbp
0x1400058bc  retn
0x1400058be  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
