# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)

- ea: `0x18000ca04`
- end: `0x18000cd14`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7PEAUFailureInfo@2@@Z`
- size: `784`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000984c`

## callees

- `0x180009264`
- `0x18000be84`
- `0x18000c694`
- `0x18000ca04`
- `0x18000d820`
- `0x18000d840`
- `0x18000d9a0`
- `0x18000d9c0`
- `0x180010464`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb23`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000cb23`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cc48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cc48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ccc8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000ccc8`

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
        unsigned __int64 a15)
{
  unsigned int v17; // edi
  int v18; // esi
  int v19; // eax
  int v20; // edx
  _WORD *v21; // rax
  int v22; // edx
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  int IsDebuggerPresent; // ecx
  wil::details *v27; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a15 + 8) = *a8;
  *(_DWORD *)(a15 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a15 + 8) = -2147024228;
          *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v20);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a15 = a7;
  *(_DWORD *)(a15 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a15 + 4) = 8;
  *(_DWORD *)(a15 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a15 + 24) = v21;
  *(_DWORD *)(a15 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a15 + 56) = a3;
  *(_DWORD *)(a15 + 64) = a2;
  *(_DWORD *)(a15 + 68) = v18;
  *(_QWORD *)(a15 + 40) = a5;
  *(_QWORD *)(a15 + 48) = a4;
  *(_QWORD *)(a15 + 136) = a6;
  *(_QWORD *)(a15 + 144) = a1;
  *(_QWORD *)(a15 + 72) = 0;
  *(_OWORD *)(a15 + 104) = 0;
  *(_QWORD *)(a15 + 120) = 0;
  *(_OWORD *)(a15 + 80) = 0;
  *(_QWORD *)(a15 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName();
  else
    ModuleName = 0;
  *(_QWORD *)(a15 + 128) = ModuleName;
  if ( wil::details::g_pfnNotifyFailure )
    wil::details::g_pfnNotifyFailure(a15);
  if ( wil::details::g_pfnGetContextAndNotifyFailure )
    wil::details::g_pfnGetContextAndNotifyFailure(a15, a13, 1024);
  if ( wil::details::g_pfnLoggingCallback )
    wil::details::g_pfnLoggingCallback(a15);
  if ( wil::details::g_pfnOriginateCallback && (*(_BYTE *)(a15 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a15);
  if ( *(int *)(a15 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a15 + 8) = -2147418113;
    *(_DWORD *)(a15 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v22);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
         IsDebuggerPresent))
    && (*(_BYTE *)(a15 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a15, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a15, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a15, 0, 0);
  }
  if ( (*(_BYTE *)(a15 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x18000ca04  mov     [rsp+arg_10], rbx
0x18000ca09  mov     [rsp+arg_8], edx
0x18000ca0d  mov     [rsp+arg_0], rcx
0x18000ca12  push    rbp
0x18000ca13  push    rsi
0x18000ca14  push    rdi
0x18000ca15  push    r12
0x18000ca17  push    r13
0x18000ca19  push    r14
0x18000ca1b  push    r15
0x18000ca1d  sub     rsp, 40h
0x18000ca21  mov     r12, r9
0x18000ca24  mov     r13, r8
0x18000ca27  mov     r10, rcx
0x18000ca2a  xor     r8d, r8d
0x18000ca2d  mov     r14, [rsp+78h+lpOutputString]
0x18000ca35  mov     [r14], r8w
0x18000ca39  mov     rax, [rsp+78h+arg_60]
0x18000ca41  mov     [rax], r8b
0x18000ca44  mov     rbx, [rsp+78h+arg_70]
0x18000ca4c  mov     r15, [rsp+78h+arg_38]
0x18000ca54  mov     edi, [r15]
0x18000ca57  mov     [rbx+8], edi
0x18000ca5a  mov     eax, [r15+4]
0x18000ca5e  mov     [rbx+0Ch], eax
0x18000ca61  mov     esi, r8d
0x18000ca64  mov     ebp, [rsp+78h+arg_30]
0x18000ca6b  mov     ecx, ebp
0x18000ca6d  test    ebp, ebp
0x18000ca6f  jz      short loc_18000CADA
0x18000ca71  sub     ecx, 1
0x18000ca74  jz      short loc_18000CAD1
0x18000ca76  sub     ecx, 1
0x18000ca79  jz      short loc_18000CA89
0x18000ca7b  cmp     ecx, 1
0x18000ca7e  jnz     short loc_18000CAE3
0x18000ca80  mov     ecx, edi; this
0x18000ca82  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ca87  jmp     short loc_18000CAE1
0x18000ca89  test    edi, edi
0x18000ca8b  js      short loc_18000CAC8
0x18000ca8d  mov     edi, 8007029Ch
0x18000ca92  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ca96  mov     rax, [rsp+78h+arg_28]
0x18000ca9e  mov     [rsp+78h+var_50], rax; __int64
0x18000caa3  mov     rax, [rsp+78h+arg_20]
0x18000caab  mov     [rsp+78h+var_58], rax; __int64
0x18000cab0  mov     r8, r13; int
0x18000cab3  mov     rcx, r10; int
0x18000cab6  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110J@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long)
0x18000cabb  mov     [rbx+8], edi
0x18000cabe  mov     ecx, edi; this
0x18000cac0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cac5  mov     [rbx+0Ch], eax
0x18000cac8  mov     ecx, edi; this
0x18000caca  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000cacf  jmp     short loc_18000CAE1
0x18000cad1  mov     ecx, edi; this
0x18000cad3  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000cad8  jmp     short loc_18000CAE1
0x18000cada  mov     ecx, edi; this
0x18000cadc  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000cae1  mov     esi, eax
0x18000cae3  mov     [rbx], ebp
0x18000cae5  xor     edi, edi
0x18000cae7  mov     [rbx+4], edi
0x18000caea  cmp     dword ptr [r15+8], 1
0x18000caef  jnz     short loc_18000CAF8
0x18000caf1  mov     dword ptr [rbx+4], 8
0x18000caf8  mov     eax, 1
0x18000cafd  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureInfo *)'::`2'::s_failureId
0x18000cb05  inc     eax
0x18000cb07  mov     [rbx+10h], eax
0x18000cb0a  mov     rax, [rsp+78h+arg_40]
0x18000cb12  test    rax, rax
0x18000cb15  jz      short loc_18000CB1C
0x18000cb17  cmp     [rax], di
0x18000cb1a  jnz     short loc_18000CB1F
0x18000cb1c  mov     rax, rdi
0x18000cb1f  mov     [rbx+18h], rax
0x18000cb23  call    cs:__imp_GetCurrentThreadId
0x18000cb2a  nop     dword ptr [rax+rax+00h]
0x18000cb2f  mov     [rbx+20h], eax
0x18000cb32  mov     [rbx+38h], r13
0x18000cb36  mov     eax, [rsp+78h+arg_8]
0x18000cb3d  mov     [rbx+40h], eax
0x18000cb40  mov     [rbx+44h], esi
0x18000cb43  mov     rax, [rsp+78h+arg_20]
0x18000cb4b  mov     [rbx+28h], rax
0x18000cb4f  mov     [rbx+30h], r12
0x18000cb53  mov     rax, [rsp+78h+arg_28]
0x18000cb5b  mov     [rbx+88h], rax
0x18000cb62  mov     rax, [rsp+78h+arg_0]
0x18000cb6a  mov     [rbx+90h], rax
0x18000cb71  mov     [rbx+48h], rdi
0x18000cb75  xorps   xmm0, xmm0
0x18000cb78  xor     eax, eax
0x18000cb7a  movups  xmmword ptr [rbx+68h], xmm0
0x18000cb7e  mov     [rbx+78h], rax
0x18000cb82  movups  xmmword ptr [rbx+50h], xmm0
0x18000cb86  mov     [rbx+60h], rax
0x18000cb8a  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cb91  test    rax, rax
0x18000cb94  jz      short loc_18000CB9D
0x18000cb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb9b  jmp     short loc_18000CBA0
0x18000cb9d  mov     rax, rdi
0x18000cba0  mov     [rbx+80h], rax
0x18000cba7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cbae  test    rax, rax
0x18000cbb1  jz      short loc_18000CBBB
0x18000cbb3  mov     rcx, rbx
0x18000cbb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbbb  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cbc2  test    rax, rax
0x18000cbc5  jz      short loc_18000CBDD
0x18000cbc7  mov     r8d, 400h
0x18000cbcd  mov     rdx, [rsp+78h+arg_60]
0x18000cbd5  mov     rcx, rbx
0x18000cbd8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbdd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cbe4  test    rax, rax
0x18000cbe7  jz      short loc_18000CBF1
0x18000cbe9  mov     rcx, rbx
0x18000cbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbf1  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cbf8  test    rax, rax
0x18000cbfb  jz      short loc_18000CC0B
0x18000cbfd  test    byte ptr [rbx+4], 2
0x18000cc01  jnz     short loc_18000CC0B
0x18000cc03  mov     rcx, rbx
0x18000cc06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc0b  cmp     [rbx+8], edi
0x18000cc0e  jl      short loc_18000CC29
0x18000cc10  cmp     ebp, 3
0x18000cc13  jnz     loc_18000CD0E
0x18000cc19  mov     ecx, 8000FFFFh; this
0x18000cc1e  mov     [rbx+8], ecx
0x18000cc21  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cc26  mov     [rbx+0Ch], eax
0x18000cc29  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cc30  jnz     short loc_18000CC5F
0x18000cc32  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cc39  test    rax, rax
0x18000cc3c  jz      short loc_18000CC48
0x18000cc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc43  movzx   ecx, al
0x18000cc46  jmp     short loc_18000CC5B
0x18000cc48  call    cs:__imp_IsDebuggerPresent
0x18000cc4f  nop     dword ptr [rax+rax+00h]
0x18000cc54  mov     ecx, edi
0x18000cc56  test    eax, eax
0x18000cc58  setnz   cl
0x18000cc5b  test    ecx, ecx
0x18000cc5d  jz      short loc_18000CC65
0x18000cc5f  test    byte ptr [rbx+4], 2
0x18000cc63  jz      short loc_18000CC89
0x18000cc65  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cc6c  test    rax, rax
0x18000cc6f  jz      short loc_18000CCD4
0x18000cc71  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cc78  jnz     short loc_18000CCD4
0x18000cc7a  xor     r8d, r8d
0x18000cc7d  xor     edx, edx
0x18000cc7f  mov     rcx, rbx
0x18000cc82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc87  jmp     short loc_18000CCD4
0x18000cc89  mov     esi, 800h
0x18000cc8e  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cc95  test    rax, rax
0x18000cc98  jz      short loc_18000CCB1
0x18000cc9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cca1  jnz     short loc_18000CCB1
0x18000cca3  mov     r8d, esi
0x18000cca6  mov     rdx, r14
0x18000cca9  mov     rcx, rbx
0x18000ccac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccb1  cmp     [r14], di
0x18000ccb5  jnz     short loc_18000CCC5
0x18000ccb7  mov     r8, rbx; unsigned __int64
0x18000ccba  mov     rdx, rsi; unsigned __int16 *
0x18000ccbd  mov     rcx, r14; this
0x18000ccc0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000ccc5  mov     rcx, r14; lpOutputString
0x18000ccc8  call    cs:__imp_OutputDebugStringW
0x18000cccf  nop     dword ptr [rax+rax+00h]
0x18000ccd4  test    byte ptr [rbx+4], 4
0x18000ccd8  jnz     short loc_18000CCE3
0x18000ccda  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000cce1  jz      short loc_18000CCF5
0x18000cce3  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000ccea  test    rax, rax
0x18000cced  jz      short loc_18000CCF5
0x18000ccef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ccf4  nop
0x18000ccf5  mov     rbx, [rsp+78h+arg_10]
0x18000ccfd  add     rsp, 40h
0x18000cd01  pop     r15
0x18000cd03  pop     r14
0x18000cd05  pop     r13
0x18000cd07  pop     r12
0x18000cd09  pop     rdi
0x18000cd0a  pop     rsi
0x18000cd0b  pop     rbp
0x18000cd0c  retn
0x18000cd0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
