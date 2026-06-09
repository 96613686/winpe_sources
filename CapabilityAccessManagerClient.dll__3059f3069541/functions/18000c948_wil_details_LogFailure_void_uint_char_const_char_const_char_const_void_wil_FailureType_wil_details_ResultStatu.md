# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c948`
- end: `0x18000cc41`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180009b8c`
- `0x180009ef8`
- `0x180012f44`

## callees

- `0x180009ac0`
- `0x18000bc24`
- `0x18000c4ec`
- `0x18000c948`
- `0x18000d814`
- `0x18000d830`
- `0x18000d980`
- `0x18000d99c`
- `0x18000f96c`
- `0x180039010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca6b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ca6b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cbfc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cbfc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cb8a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cb8a`

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
0x18000c948  mov     [rsp+arg_10], rbx
0x18000c94d  mov     [rsp+arg_8], edx
0x18000c951  mov     [rsp+arg_0], rcx
0x18000c956  push    rbp
0x18000c957  push    rsi
0x18000c958  push    rdi
0x18000c959  push    r12
0x18000c95b  push    r13
0x18000c95d  push    r14
0x18000c95f  push    r15
0x18000c961  sub     rsp, 40h
0x18000c965  mov     r12, r9
0x18000c968  mov     r13, r8
0x18000c96b  mov     r10, rcx
0x18000c96e  xor     eax, eax
0x18000c970  mov     rsi, [rsp+78h+lpOutputString]
0x18000c978  mov     [rsi], ax
0x18000c97b  mov     rax, [rsp+78h+arg_60]
0x18000c983  mov     byte ptr [rax], 0
0x18000c986  mov     r14, [rsp+78h+arg_38]
0x18000c98e  mov     edi, [r14]
0x18000c991  mov     rbx, [rsp+78h+arg_78]
0x18000c999  mov     [rbx+8], edi
0x18000c99c  mov     eax, [r14+4]
0x18000c9a0  mov     [rbx+0Ch], eax
0x18000c9a3  xor     ebp, ebp
0x18000c9a5  mov     r15d, [rsp+78h+arg_30]
0x18000c9ad  mov     ecx, r15d
0x18000c9b0  test    r15d, r15d
0x18000c9b3  jz      short loc_18000CA1B
0x18000c9b5  sub     ecx, 1
0x18000c9b8  jz      short loc_18000CA12
0x18000c9ba  sub     ecx, 1
0x18000c9bd  jz      short loc_18000C9CD
0x18000c9bf  cmp     ecx, 1
0x18000c9c2  jnz     short loc_18000CA24
0x18000c9c4  mov     ecx, edi; this
0x18000c9c6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c9cb  jmp     short loc_18000CA22
0x18000c9cd  test    edi, edi
0x18000c9cf  js      short loc_18000CA09
0x18000c9d1  mov     edi, 8007029Ch
0x18000c9d6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c9da  mov     rax, [rsp+78h+arg_28]
0x18000c9e2  mov     [rsp+78h+var_50], rax; __int64
0x18000c9e7  mov     rax, [rsp+78h+arg_20]
0x18000c9ef  mov     [rsp+78h+var_58], rax; __int64
0x18000c9f4  mov     rcx, r10; int
0x18000c9f7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c9fc  mov     [rbx+8], edi
0x18000c9ff  mov     ecx, edi; this
0x18000ca01  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ca06  mov     [rbx+0Ch], eax
0x18000ca09  mov     ecx, edi; this
0x18000ca0b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ca10  jmp     short loc_18000CA22
0x18000ca12  mov     ecx, edi; this
0x18000ca14  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ca19  jmp     short loc_18000CA22
0x18000ca1b  mov     ecx, edi; this
0x18000ca1d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ca22  mov     ebp, eax
0x18000ca24  mov     [rbx], r15d
0x18000ca27  mov     eax, [rsp+78h+arg_70]
0x18000ca2e  mov     [rbx+4], eax
0x18000ca31  cmp     dword ptr [r14+8], 1
0x18000ca36  jnz     short loc_18000CA3E
0x18000ca38  or      eax, 8
0x18000ca3b  mov     [rbx+4], eax
0x18000ca3e  mov     eax, 1
0x18000ca43  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ca4b  inc     eax
0x18000ca4d  mov     [rbx+10h], eax
0x18000ca50  mov     rax, [rsp+78h+arg_40]
0x18000ca58  xor     edi, edi
0x18000ca5a  test    rax, rax
0x18000ca5d  jz      short loc_18000CA64
0x18000ca5f  cmp     [rax], di
0x18000ca62  jnz     short loc_18000CA67
0x18000ca64  mov     rax, rdi
0x18000ca67  mov     [rbx+18h], rax
0x18000ca6b  call    cs:__imp_GetCurrentThreadId
0x18000ca71  mov     [rbx+20h], eax
0x18000ca74  mov     [rbx+38h], r13
0x18000ca78  mov     eax, [rsp+78h+arg_8]
0x18000ca7f  mov     [rbx+40h], eax
0x18000ca82  mov     [rbx+44h], ebp
0x18000ca85  mov     rax, [rsp+78h+arg_20]
0x18000ca8d  mov     [rbx+28h], rax
0x18000ca91  mov     [rbx+30h], r12
0x18000ca95  mov     rax, [rsp+78h+arg_28]
0x18000ca9d  mov     [rbx+88h], rax
0x18000caa4  mov     rax, [rsp+78h+arg_0]
0x18000caac  mov     [rbx+90h], rax
0x18000cab3  mov     [rbx+48h], rdi
0x18000cab7  xorps   xmm0, xmm0
0x18000caba  xor     eax, eax
0x18000cabc  movups  xmmword ptr [rbx+68h], xmm0
0x18000cac0  mov     [rbx+78h], rax
0x18000cac4  movups  xmmword ptr [rbx+50h], xmm0
0x18000cac8  mov     [rbx+60h], rax
0x18000cacc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cad3  test    rax, rax
0x18000cad6  jz      short loc_18000CADF
0x18000cad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cadd  jmp     short loc_18000CAE2
0x18000cadf  mov     rax, rdi
0x18000cae2  mov     [rbx+80h], rax
0x18000cae9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000caf0  test    rax, rax
0x18000caf3  jz      short loc_18000CAFD
0x18000caf5  mov     rcx, rbx
0x18000caf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cafd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cb04  test    rax, rax
0x18000cb07  jz      short loc_18000CB1F
0x18000cb09  mov     r8d, 400h
0x18000cb0f  mov     rdx, [rsp+78h+arg_60]
0x18000cb17  mov     rcx, rbx
0x18000cb1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb1f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cb26  test    rax, rax
0x18000cb29  jz      short loc_18000CB33
0x18000cb2b  mov     rcx, rbx
0x18000cb2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb33  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cb3a  test    rax, rax
0x18000cb3d  jz      short loc_18000CB4D
0x18000cb3f  test    byte ptr [rbx+4], 2
0x18000cb43  jnz     short loc_18000CB4D
0x18000cb45  mov     rcx, rbx
0x18000cb48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb4d  cmp     [rbx+8], edi
0x18000cb50  jl      short loc_18000CB6C
0x18000cb52  cmp     r15d, 3
0x18000cb56  jnz     loc_18000CC3B
0x18000cb5c  mov     ecx, 8000FFFFh; this
0x18000cb61  mov     [rbx+8], ecx
0x18000cb64  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cb69  mov     [rbx+0Ch], eax
0x18000cb6c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cb73  jnz     short loc_18000CB94
0x18000cb75  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cb7c  test    rax, rax
0x18000cb7f  jz      short loc_18000CB8A
0x18000cb81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb86  test    al, al
0x18000cb88  jmp     short loc_18000CB92
0x18000cb8a  call    cs:__imp_IsDebuggerPresent
0x18000cb90  test    eax, eax
0x18000cb92  jz      short loc_18000CB9A
0x18000cb94  test    byte ptr [rbx+4], 2
0x18000cb98  jz      short loc_18000CBBE
0x18000cb9a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cba1  test    rax, rax
0x18000cba4  jz      short loc_18000CC02
0x18000cba6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cbad  jnz     short loc_18000CC02
0x18000cbaf  xor     r8d, r8d
0x18000cbb2  xor     edx, edx
0x18000cbb4  mov     rcx, rbx
0x18000cbb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbbc  jmp     short loc_18000CC02
0x18000cbbe  mov     ebp, 800h
0x18000cbc3  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cbca  test    rax, rax
0x18000cbcd  jz      short loc_18000CBE6
0x18000cbcf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cbd6  jnz     short loc_18000CBE6
0x18000cbd8  mov     r8d, ebp
0x18000cbdb  mov     rdx, rsi
0x18000cbde  mov     rcx, rbx
0x18000cbe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbe6  cmp     [rsi], di
0x18000cbe9  jnz     short loc_18000CBF9
0x18000cbeb  mov     r8, rbx; unsigned __int64
0x18000cbee  mov     rdx, rbp; unsigned __int16 *
0x18000cbf1  mov     rcx, rsi; this
0x18000cbf4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cbf9  mov     rcx, rsi; lpOutputString
0x18000cbfc  call    cs:__imp_OutputDebugStringW
0x18000cc02  test    byte ptr [rbx+4], 4
0x18000cc06  jnz     short loc_18000CC11
0x18000cc08  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000cc0f  jz      short loc_18000CC23
0x18000cc11  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cc18  test    rax, rax
0x18000cc1b  jz      short loc_18000CC23
0x18000cc1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc22  nop
0x18000cc23  mov     rbx, [rsp+78h+arg_10]
0x18000cc2b  add     rsp, 40h
0x18000cc2f  pop     r15
0x18000cc31  pop     r14
0x18000cc33  pop     r13
0x18000cc35  pop     r12
0x18000cc37  pop     rdi
0x18000cc38  pop     rsi
0x18000cc39  pop     rbp
0x18000cc3a  retn
0x18000cc3b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
