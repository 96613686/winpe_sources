# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180048c40`
- end: `0x180048f39`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800474a8`
- `0x180047814`
- `0x18004b338`

## callees

- `0x180037e98`
- `0x180038430`
- `0x180039630`
- `0x1800473e0`
- `0x18004871c`
- `0x180048c40`
- `0x1800491f4`
- `0x180049210`
- `0x18004a154`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048d63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180048d63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180048e82`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180048e82`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180048ef4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180048ef4`

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
0x180048c40  mov     [rsp+arg_10], rbx
0x180048c45  mov     [rsp+arg_8], edx
0x180048c49  mov     [rsp+arg_0], rcx
0x180048c4e  push    rbp
0x180048c4f  push    rsi
0x180048c50  push    rdi
0x180048c51  push    r12
0x180048c53  push    r13
0x180048c55  push    r14
0x180048c57  push    r15
0x180048c59  sub     rsp, 40h
0x180048c5d  mov     r12, r9
0x180048c60  mov     r13, r8
0x180048c63  mov     r10, rcx
0x180048c66  xor     eax, eax
0x180048c68  mov     rsi, [rsp+78h+lpOutputString]
0x180048c70  mov     [rsi], ax
0x180048c73  mov     rax, [rsp+78h+arg_60]
0x180048c7b  mov     byte ptr [rax], 0
0x180048c7e  mov     r14, [rsp+78h+arg_38]
0x180048c86  mov     edi, [r14]
0x180048c89  mov     rbx, [rsp+78h+arg_78]
0x180048c91  mov     [rbx+8], edi
0x180048c94  mov     eax, [r14+4]
0x180048c98  mov     [rbx+0Ch], eax
0x180048c9b  xor     ebp, ebp
0x180048c9d  mov     r15d, [rsp+78h+arg_30]
0x180048ca5  mov     ecx, r15d
0x180048ca8  test    r15d, r15d
0x180048cab  jz      short loc_180048D13
0x180048cad  sub     ecx, 1
0x180048cb0  jz      short loc_180048D0A
0x180048cb2  sub     ecx, 1
0x180048cb5  jz      short loc_180048CC5
0x180048cb7  cmp     ecx, 1
0x180048cba  jnz     short loc_180048D1C
0x180048cbc  mov     ecx, edi; this
0x180048cbe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180048cc3  jmp     short loc_180048D1A
0x180048cc5  test    edi, edi
0x180048cc7  js      short loc_180048D01
0x180048cc9  mov     edi, 8007029Ch
0x180048cce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180048cd2  mov     rax, [rsp+78h+arg_28]
0x180048cda  mov     [rsp+78h+var_50], rax; __int64
0x180048cdf  mov     rax, [rsp+78h+arg_20]
0x180048ce7  mov     [rsp+78h+var_58], rax; __int64
0x180048cec  mov     rcx, r10; int
0x180048cef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180048cf4  mov     [rbx+8], edi
0x180048cf7  mov     ecx, edi; this
0x180048cf9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180048cfe  mov     [rbx+0Ch], eax
0x180048d01  mov     ecx, edi; this
0x180048d03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180048d08  jmp     short loc_180048D1A
0x180048d0a  mov     ecx, edi; this
0x180048d0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180048d11  jmp     short loc_180048D1A
0x180048d13  mov     ecx, edi; this
0x180048d15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180048d1a  mov     ebp, eax
0x180048d1c  mov     [rbx], r15d
0x180048d1f  mov     eax, [rsp+78h+arg_70]
0x180048d26  mov     [rbx+4], eax
0x180048d29  cmp     dword ptr [r14+8], 1
0x180048d2e  jnz     short loc_180048D36
0x180048d30  or      eax, 8
0x180048d33  mov     [rbx+4], eax
0x180048d36  mov     eax, 1
0x180048d3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180048d43  inc     eax
0x180048d45  mov     [rbx+10h], eax
0x180048d48  mov     rax, [rsp+78h+arg_40]
0x180048d50  xor     edi, edi
0x180048d52  test    rax, rax
0x180048d55  jz      short loc_180048D5C
0x180048d57  cmp     [rax], di
0x180048d5a  jnz     short loc_180048D5F
0x180048d5c  mov     rax, rdi
0x180048d5f  mov     [rbx+18h], rax
0x180048d63  call    cs:__imp_GetCurrentThreadId
0x180048d69  mov     [rbx+20h], eax
0x180048d6c  mov     [rbx+38h], r13
0x180048d70  mov     eax, [rsp+78h+arg_8]
0x180048d77  mov     [rbx+40h], eax
0x180048d7a  mov     [rbx+44h], ebp
0x180048d7d  mov     rax, [rsp+78h+arg_20]
0x180048d85  mov     [rbx+28h], rax
0x180048d89  mov     [rbx+30h], r12
0x180048d8d  mov     rax, [rsp+78h+arg_28]
0x180048d95  mov     [rbx+88h], rax
0x180048d9c  mov     rax, [rsp+78h+arg_0]
0x180048da4  mov     [rbx+90h], rax
0x180048dab  mov     [rbx+48h], rdi
0x180048daf  xorps   xmm0, xmm0
0x180048db2  xor     eax, eax
0x180048db4  movups  xmmword ptr [rbx+68h], xmm0
0x180048db8  mov     [rbx+78h], rax
0x180048dbc  movups  xmmword ptr [rbx+50h], xmm0
0x180048dc0  mov     [rbx+60h], rax
0x180048dc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180048dcb  test    rax, rax
0x180048dce  jz      short loc_180048DD7
0x180048dd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048dd5  jmp     short loc_180048DDA
0x180048dd7  mov     rax, rdi
0x180048dda  mov     [rbx+80h], rax
0x180048de1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180048de8  test    rax, rax
0x180048deb  jz      short loc_180048DF5
0x180048ded  mov     rcx, rbx
0x180048df0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048df5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180048dfc  test    rax, rax
0x180048dff  jz      short loc_180048E17
0x180048e01  mov     r8d, 400h
0x180048e07  mov     rdx, [rsp+78h+arg_60]
0x180048e0f  mov     rcx, rbx
0x180048e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180048e1e  test    rax, rax
0x180048e21  jz      short loc_180048E2B
0x180048e23  mov     rcx, rbx
0x180048e26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e2b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180048e32  test    rax, rax
0x180048e35  jz      short loc_180048E45
0x180048e37  test    byte ptr [rbx+4], 2
0x180048e3b  jnz     short loc_180048E45
0x180048e3d  mov     rcx, rbx
0x180048e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e45  cmp     [rbx+8], edi
0x180048e48  jl      short loc_180048E64
0x180048e4a  cmp     r15d, 3
0x180048e4e  jnz     loc_180048F33
0x180048e54  mov     ecx, 8000FFFFh; this
0x180048e59  mov     [rbx+8], ecx
0x180048e5c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180048e61  mov     [rbx+0Ch], eax
0x180048e64  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180048e6b  jnz     short loc_180048E8C
0x180048e6d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180048e74  test    rax, rax
0x180048e77  jz      short loc_180048E82
0x180048e79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048e7e  test    al, al
0x180048e80  jmp     short loc_180048E8A
0x180048e82  call    cs:__imp_IsDebuggerPresent
0x180048e88  test    eax, eax
0x180048e8a  jz      short loc_180048E92
0x180048e8c  test    byte ptr [rbx+4], 2
0x180048e90  jz      short loc_180048EB6
0x180048e92  mov     rax, cs:g_pfnResultLoggingCallback
0x180048e99  test    rax, rax
0x180048e9c  jz      short loc_180048EFA
0x180048e9e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180048ea5  jnz     short loc_180048EFA
0x180048ea7  xor     r8d, r8d
0x180048eaa  xor     edx, edx
0x180048eac  mov     rcx, rbx
0x180048eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048eb4  jmp     short loc_180048EFA
0x180048eb6  mov     ebp, 800h
0x180048ebb  mov     rax, cs:g_pfnResultLoggingCallback
0x180048ec2  test    rax, rax
0x180048ec5  jz      short loc_180048EDE
0x180048ec7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180048ece  jnz     short loc_180048EDE
0x180048ed0  mov     r8d, ebp
0x180048ed3  mov     rdx, rsi
0x180048ed6  mov     rcx, rbx
0x180048ed9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048ede  cmp     [rsi], di
0x180048ee1  jnz     short loc_180048EF1
0x180048ee3  mov     r8, rbx; unsigned __int64
0x180048ee6  mov     rdx, rbp; unsigned __int16 *
0x180048ee9  mov     rcx, rsi; this
0x180048eec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180048ef1  mov     rcx, rsi; lpOutputString
0x180048ef4  call    cs:__imp_OutputDebugStringW
0x180048efa  test    byte ptr [rbx+4], 4
0x180048efe  jnz     short loc_180048F09
0x180048f00  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180048f07  jz      short loc_180048F1B
0x180048f09  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180048f10  test    rax, rax
0x180048f13  jz      short loc_180048F1B
0x180048f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048f1a  nop
0x180048f1b  mov     rbx, [rsp+78h+arg_10]
0x180048f23  add     rsp, 40h
0x180048f27  pop     r15
0x180048f29  pop     r14
0x180048f2b  pop     r13
0x180048f2d  pop     r12
0x180048f2f  pop     rdi
0x180048f30  pop     rsi
0x180048f31  pop     rbp
0x180048f32  retn
0x180048f33  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
