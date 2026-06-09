# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003ca30`
- end: `0x18003cd29`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18003aaf0`
- `0x18003ae1c`
- `0x18003ef8c`

## callees

- `0x1800196f8`
- `0x18003aa28`
- `0x18003c51c`
- `0x18003ca30`
- `0x18003d0c8`
- `0x18003d0f0`
- `0x18003d104`
- `0x18003d120`
- `0x18003e05c`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb53`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003cb53`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003cc72`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003cc72`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003cce4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003cce4`

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
0x18003ca30  mov     [rsp+arg_10], rbx
0x18003ca35  mov     [rsp+arg_8], edx
0x18003ca39  mov     [rsp+arg_0], rcx
0x18003ca3e  push    rbp
0x18003ca3f  push    rsi
0x18003ca40  push    rdi
0x18003ca41  push    r12
0x18003ca43  push    r13
0x18003ca45  push    r14
0x18003ca47  push    r15
0x18003ca49  sub     rsp, 40h
0x18003ca4d  mov     r12, r9
0x18003ca50  mov     r13, r8
0x18003ca53  mov     r10, rcx
0x18003ca56  xor     eax, eax
0x18003ca58  mov     rsi, [rsp+78h+lpOutputString]
0x18003ca60  mov     [rsi], ax
0x18003ca63  mov     rax, [rsp+78h+arg_60]
0x18003ca6b  mov     byte ptr [rax], 0
0x18003ca6e  mov     r14, [rsp+78h+arg_38]
0x18003ca76  mov     edi, [r14]
0x18003ca79  mov     rbx, [rsp+78h+arg_78]
0x18003ca81  mov     [rbx+8], edi
0x18003ca84  mov     eax, [r14+4]
0x18003ca88  mov     [rbx+0Ch], eax
0x18003ca8b  xor     ebp, ebp
0x18003ca8d  mov     r15d, [rsp+78h+arg_30]
0x18003ca95  mov     ecx, r15d
0x18003ca98  test    r15d, r15d
0x18003ca9b  jz      short loc_18003CB03
0x18003ca9d  sub     ecx, 1
0x18003caa0  jz      short loc_18003CAFA
0x18003caa2  sub     ecx, 1
0x18003caa5  jz      short loc_18003CAB5
0x18003caa7  cmp     ecx, 1
0x18003caaa  jnz     short loc_18003CB0C
0x18003caac  mov     ecx, edi; this
0x18003caae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003cab3  jmp     short loc_18003CB0A
0x18003cab5  test    edi, edi
0x18003cab7  js      short loc_18003CAF1
0x18003cab9  mov     edi, 8007029Ch
0x18003cabe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003cac2  mov     rax, [rsp+78h+arg_28]
0x18003caca  mov     [rsp+78h+var_50], rax; __int64
0x18003cacf  mov     rax, [rsp+78h+arg_20]
0x18003cad7  mov     [rsp+78h+var_58], rax; __int64
0x18003cadc  mov     rcx, r10; int
0x18003cadf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003cae4  mov     [rbx+8], edi
0x18003cae7  mov     ecx, edi; this
0x18003cae9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003caee  mov     [rbx+0Ch], eax
0x18003caf1  mov     ecx, edi; this
0x18003caf3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003caf8  jmp     short loc_18003CB0A
0x18003cafa  mov     ecx, edi; this
0x18003cafc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003cb01  jmp     short loc_18003CB0A
0x18003cb03  mov     ecx, edi; this
0x18003cb05  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003cb0a  mov     ebp, eax
0x18003cb0c  mov     [rbx], r15d
0x18003cb0f  mov     eax, [rsp+78h+arg_70]
0x18003cb16  mov     [rbx+4], eax
0x18003cb19  cmp     dword ptr [r14+8], 1
0x18003cb1e  jnz     short loc_18003CB26
0x18003cb20  or      eax, 8
0x18003cb23  mov     [rbx+4], eax
0x18003cb26  mov     eax, 1
0x18003cb2b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003cb33  inc     eax
0x18003cb35  mov     [rbx+10h], eax
0x18003cb38  mov     rax, [rsp+78h+arg_40]
0x18003cb40  xor     edi, edi
0x18003cb42  test    rax, rax
0x18003cb45  jz      short loc_18003CB4C
0x18003cb47  cmp     [rax], di
0x18003cb4a  jnz     short loc_18003CB4F
0x18003cb4c  mov     rax, rdi
0x18003cb4f  mov     [rbx+18h], rax
0x18003cb53  call    cs:__imp_GetCurrentThreadId
0x18003cb59  mov     [rbx+20h], eax
0x18003cb5c  mov     [rbx+38h], r13
0x18003cb60  mov     eax, [rsp+78h+arg_8]
0x18003cb67  mov     [rbx+40h], eax
0x18003cb6a  mov     [rbx+44h], ebp
0x18003cb6d  mov     rax, [rsp+78h+arg_20]
0x18003cb75  mov     [rbx+28h], rax
0x18003cb79  mov     [rbx+30h], r12
0x18003cb7d  mov     rax, [rsp+78h+arg_28]
0x18003cb85  mov     [rbx+88h], rax
0x18003cb8c  mov     rax, [rsp+78h+arg_0]
0x18003cb94  mov     [rbx+90h], rax
0x18003cb9b  mov     [rbx+48h], rdi
0x18003cb9f  xorps   xmm0, xmm0
0x18003cba2  xor     eax, eax
0x18003cba4  movups  xmmword ptr [rbx+68h], xmm0
0x18003cba8  mov     [rbx+78h], rax
0x18003cbac  movups  xmmword ptr [rbx+50h], xmm0
0x18003cbb0  mov     [rbx+60h], rax
0x18003cbb4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003cbbb  test    rax, rax
0x18003cbbe  jz      short loc_18003CBC7
0x18003cbc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbc5  jmp     short loc_18003CBCA
0x18003cbc7  mov     rax, rdi
0x18003cbca  mov     [rbx+80h], rax
0x18003cbd1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003cbd8  test    rax, rax
0x18003cbdb  jz      short loc_18003CBE5
0x18003cbdd  mov     rcx, rbx
0x18003cbe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cbe5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003cbec  test    rax, rax
0x18003cbef  jz      short loc_18003CC07
0x18003cbf1  mov     r8d, 400h
0x18003cbf7  mov     rdx, [rsp+78h+arg_60]
0x18003cbff  mov     rcx, rbx
0x18003cc02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc07  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003cc0e  test    rax, rax
0x18003cc11  jz      short loc_18003CC1B
0x18003cc13  mov     rcx, rbx
0x18003cc16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc1b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003cc22  test    rax, rax
0x18003cc25  jz      short loc_18003CC35
0x18003cc27  test    byte ptr [rbx+4], 2
0x18003cc2b  jnz     short loc_18003CC35
0x18003cc2d  mov     rcx, rbx
0x18003cc30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc35  cmp     [rbx+8], edi
0x18003cc38  jl      short loc_18003CC54
0x18003cc3a  cmp     r15d, 3
0x18003cc3e  jnz     loc_18003CD23
0x18003cc44  mov     ecx, 8000FFFFh; this
0x18003cc49  mov     [rbx+8], ecx
0x18003cc4c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003cc51  mov     [rbx+0Ch], eax
0x18003cc54  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003cc5b  jnz     short loc_18003CC7C
0x18003cc5d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003cc64  test    rax, rax
0x18003cc67  jz      short loc_18003CC72
0x18003cc69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cc6e  test    al, al
0x18003cc70  jmp     short loc_18003CC7A
0x18003cc72  call    cs:__imp_IsDebuggerPresent
0x18003cc78  test    eax, eax
0x18003cc7a  jz      short loc_18003CC82
0x18003cc7c  test    byte ptr [rbx+4], 2
0x18003cc80  jz      short loc_18003CCA6
0x18003cc82  mov     rax, cs:g_pfnResultLoggingCallback
0x18003cc89  test    rax, rax
0x18003cc8c  jz      short loc_18003CCEA
0x18003cc8e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003cc95  jnz     short loc_18003CCEA
0x18003cc97  xor     r8d, r8d
0x18003cc9a  xor     edx, edx
0x18003cc9c  mov     rcx, rbx
0x18003cc9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cca4  jmp     short loc_18003CCEA
0x18003cca6  mov     ebp, 800h
0x18003ccab  mov     rax, cs:g_pfnResultLoggingCallback
0x18003ccb2  test    rax, rax
0x18003ccb5  jz      short loc_18003CCCE
0x18003ccb7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003ccbe  jnz     short loc_18003CCCE
0x18003ccc0  mov     r8d, ebp
0x18003ccc3  mov     rdx, rsi
0x18003ccc6  mov     rcx, rbx
0x18003ccc9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccce  cmp     [rsi], di
0x18003ccd1  jnz     short loc_18003CCE1
0x18003ccd3  mov     r8, rbx; unsigned __int64
0x18003ccd6  mov     rdx, rbp; unsigned __int16 *
0x18003ccd9  mov     rcx, rsi; this
0x18003ccdc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003cce1  mov     rcx, rsi; lpOutputString
0x18003cce4  call    cs:__imp_OutputDebugStringW
0x18003ccea  test    byte ptr [rbx+4], 4
0x18003ccee  jnz     short loc_18003CCF9
0x18003ccf0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003ccf7  jz      short loc_18003CD0B
0x18003ccf9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003cd00  test    rax, rax
0x18003cd03  jz      short loc_18003CD0B
0x18003cd05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003cd0a  nop
0x18003cd0b  mov     rbx, [rsp+78h+arg_10]
0x18003cd13  add     rsp, 40h
0x18003cd17  pop     r15
0x18003cd19  pop     r14
0x18003cd1b  pop     r13
0x18003cd1d  pop     r12
0x18003cd1f  pop     rdi
0x18003cd20  pop     rsi
0x18003cd21  pop     rbp
0x18003cd22  retn
0x18003cd23  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
