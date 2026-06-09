# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004c50`
- end: `0x180004f5b`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002bdc`

## callees

- `0x180001fd0`
- `0x1800025f4`
- `0x1800043bc`
- `0x180004a8c`
- `0x180004c50`
- `0x18000593c`
- `0x180005a90`
- `0x180005ab0`
- `0x18000786c`
- `0x18000a010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180004f10`
- `KERNEL32!OutputDebugStringW` at `0x180004f10`
- `KERNEL32!GetCurrentThreadId` at `0x180004d73`
- `KERNEL32!GetCurrentThreadId` at `0x180004d73`
- `KERNEL32!IsDebuggerPresent` at `0x180004e98`
- `KERNEL32!IsDebuggerPresent` at `0x180004e98`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180004c50  mov     [rsp+arg_10], rbx
0x180004c55  mov     [rsp+arg_8], edx
0x180004c59  mov     [rsp+arg_0], rcx
0x180004c5e  push    rbp
0x180004c5f  push    rsi
0x180004c60  push    rdi
0x180004c61  push    r12
0x180004c63  push    r13
0x180004c65  push    r14
0x180004c67  push    r15
0x180004c69  sub     rsp, 40h
0x180004c6d  mov     r14, [rsp+78h+arg_38]
0x180004c75  xor     eax, eax
0x180004c77  mov     rbx, [rsp+78h+arg_78]
0x180004c7f  xor     ebp, ebp
0x180004c81  mov     r15d, [rsp+78h+arg_30]
0x180004c89  mov     r10, rcx
0x180004c8c  mov     rsi, [rsp+78h+lpOutputString]
0x180004c94  mov     r12, r9
0x180004c97  mov     r13, r8
0x180004c9a  mov     ecx, r15d
0x180004c9d  mov     [rsi], ax
0x180004ca0  mov     rax, [rsp+78h+arg_60]
0x180004ca8  mov     byte ptr [rax], 0
0x180004cab  mov     edi, [r14]
0x180004cae  mov     [rbx+8], edi
0x180004cb1  mov     eax, [r14+4]
0x180004cb5  mov     [rbx+0Ch], eax
0x180004cb8  test    r15d, r15d
0x180004cbb  jz      short loc_180004D23
0x180004cbd  sub     ecx, 1
0x180004cc0  jz      short loc_180004D1A
0x180004cc2  sub     ecx, 1
0x180004cc5  jz      short loc_180004CD5
0x180004cc7  cmp     ecx, 1
0x180004cca  jnz     short loc_180004D2C
0x180004ccc  mov     ecx, edi; this
0x180004cce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004cd3  jmp     short loc_180004D2A
0x180004cd5  test    edi, edi
0x180004cd7  js      short loc_180004D11
0x180004cd9  mov     rax, [rsp+78h+arg_28]
0x180004ce1  mov     edi, 8007029Ch
0x180004ce6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004cea  mov     rcx, r10; int
0x180004ced  mov     [rsp+78h+var_50], rax; __int64
0x180004cf2  mov     rax, [rsp+78h+arg_20]
0x180004cfa  mov     [rsp+78h+var_58], rax; __int64
0x180004cff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004d04  mov     ecx, edi; this
0x180004d06  mov     [rbx+8], edi
0x180004d09  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004d0e  mov     [rbx+0Ch], eax
0x180004d11  mov     ecx, edi; this
0x180004d13  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004d18  jmp     short loc_180004D2A
0x180004d1a  mov     ecx, edi; this
0x180004d1c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004d21  jmp     short loc_180004D2A
0x180004d23  mov     ecx, edi; this
0x180004d25  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004d2a  mov     ebp, eax
0x180004d2c  mov     eax, [rsp+78h+arg_70]
0x180004d33  mov     [rbx+4], eax
0x180004d36  mov     [rbx], r15d
0x180004d39  cmp     dword ptr [r14+8], 1
0x180004d3e  jnz     short loc_180004D46
0x180004d40  or      eax, 8
0x180004d43  mov     [rbx+4], eax
0x180004d46  mov     eax, 1
0x180004d4b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004d53  inc     eax
0x180004d55  xor     edi, edi
0x180004d57  mov     [rbx+10h], eax
0x180004d5a  mov     rax, [rsp+78h+arg_40]
0x180004d62  test    rax, rax
0x180004d65  jz      short loc_180004D6C
0x180004d67  cmp     [rax], di
0x180004d6a  jnz     short loc_180004D6F
0x180004d6c  mov     rax, rdi
0x180004d6f  mov     [rbx+18h], rax
0x180004d73  call    cs:__imp_GetCurrentThreadId
0x180004d7a  nop     dword ptr [rax+rax+00h]
0x180004d7f  mov     [rbx+38h], r13
0x180004d83  xorps   xmm0, xmm0
0x180004d86  mov     [rbx+20h], eax
0x180004d89  mov     eax, [rsp+78h+arg_8]
0x180004d90  mov     [rbx+40h], eax
0x180004d93  mov     rax, [rsp+78h+arg_20]
0x180004d9b  mov     [rbx+28h], rax
0x180004d9f  mov     rax, [rsp+78h+arg_28]
0x180004da7  mov     [rbx+88h], rax
0x180004dae  mov     rax, [rsp+78h+arg_0]
0x180004db6  mov     [rbx+90h], rax
0x180004dbd  xor     eax, eax
0x180004dbf  mov     [rbx+44h], ebp
0x180004dc2  mov     [rbx+30h], r12
0x180004dc6  mov     [rbx+48h], rdi
0x180004dca  movups  xmmword ptr [rbx+68h], xmm0
0x180004dce  mov     [rbx+78h], rax
0x180004dd2  movups  xmmword ptr [rbx+50h], xmm0
0x180004dd6  mov     [rbx+60h], rax
0x180004dda  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004de1  test    rax, rax
0x180004de4  jz      short loc_180004DED
0x180004de6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004deb  jmp     short loc_180004DF0
0x180004ded  mov     rax, rdi
0x180004df0  mov     [rbx+80h], rax
0x180004df7  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004dfe  test    rax, rax
0x180004e01  jz      short loc_180004E0B
0x180004e03  mov     rcx, rbx
0x180004e06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e0b  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004e12  test    rax, rax
0x180004e15  jz      short loc_180004E2D
0x180004e17  mov     rdx, [rsp+78h+arg_60]
0x180004e1f  mov     r8d, 400h
0x180004e25  mov     rcx, rbx
0x180004e28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e2d  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e34  test    rax, rax
0x180004e37  jz      short loc_180004E41
0x180004e39  mov     rcx, rbx
0x180004e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e41  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004e48  test    rax, rax
0x180004e4b  jz      short loc_180004E5B
0x180004e4d  test    byte ptr [rbx+4], 2
0x180004e51  jnz     short loc_180004E5B
0x180004e53  mov     rcx, rbx
0x180004e56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e5b  cmp     [rbx+8], edi
0x180004e5e  jl      short loc_180004E7A
0x180004e60  cmp     r15d, 3
0x180004e64  jnz     loc_180004F55
0x180004e6a  mov     ecx, 8000FFFFh; this
0x180004e6f  mov     [rbx+8], ecx
0x180004e72  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004e77  mov     [rbx+0Ch], eax
0x180004e7a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004e81  jnz     short loc_180004EA8
0x180004e83  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004e8a  test    rax, rax
0x180004e8d  jz      short loc_180004E98
0x180004e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e94  test    al, al
0x180004e96  jmp     short loc_180004EA6
0x180004e98  call    cs:__imp_IsDebuggerPresent
0x180004e9f  nop     dword ptr [rax+rax+00h]
0x180004ea4  test    eax, eax
0x180004ea6  jz      short loc_180004EAE
0x180004ea8  test    byte ptr [rbx+4], 2
0x180004eac  jz      short loc_180004ED2
0x180004eae  mov     rax, cs:g_pfnResultLoggingCallback
0x180004eb5  test    rax, rax
0x180004eb8  jz      short loc_180004F1C
0x180004eba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004ec1  jnz     short loc_180004F1C
0x180004ec3  xor     r8d, r8d
0x180004ec6  xor     edx, edx
0x180004ec8  mov     rcx, rbx
0x180004ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed0  jmp     short loc_180004F1C
0x180004ed2  mov     rax, cs:g_pfnResultLoggingCallback
0x180004ed9  mov     ebp, 800h
0x180004ede  test    rax, rax
0x180004ee1  jz      short loc_180004EFA
0x180004ee3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004eea  jnz     short loc_180004EFA
0x180004eec  mov     r8d, ebp
0x180004eef  mov     rdx, rsi
0x180004ef2  mov     rcx, rbx
0x180004ef5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004efa  cmp     [rsi], di
0x180004efd  jnz     short loc_180004F0D
0x180004eff  mov     r8, rbx; unsigned __int64
0x180004f02  mov     rdx, rbp; unsigned __int16 *
0x180004f05  mov     rcx, rsi; this
0x180004f08  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004f0d  mov     rcx, rsi; lpOutputString
0x180004f10  call    cs:__imp_OutputDebugStringW
0x180004f17  nop     dword ptr [rax+rax+00h]
0x180004f1c  test    byte ptr [rbx+4], 4
0x180004f20  jnz     short loc_180004F2B
0x180004f22  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004f29  jz      short loc_180004F3C
0x180004f2b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004f32  test    rax, rax
0x180004f35  jz      short loc_180004F3C
0x180004f37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3c  mov     rbx, [rsp+78h+arg_10]
0x180004f44  add     rsp, 40h
0x180004f48  pop     r15
0x180004f4a  pop     r14
0x180004f4c  pop     r13
0x180004f4e  pop     r12
0x180004f50  pop     rdi
0x180004f51  pop     rsi
0x180004f52  pop     rbp
0x180004f53  retn
0x180004f55  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
