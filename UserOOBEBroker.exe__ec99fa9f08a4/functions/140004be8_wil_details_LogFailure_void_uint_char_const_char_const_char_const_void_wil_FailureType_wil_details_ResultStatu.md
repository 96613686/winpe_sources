# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004be8`
- end: `0x140004ee1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400033a0`

## callees

- `0x140002dac`
- `0x140004284`
- `0x140004a24`
- `0x140004be8`
- `0x140005174`
- `0x140005190`
- `0x1400051a4`
- `0x1400051c0`
- `0x140006234`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140004d0b`
- `KERNEL32!GetCurrentThreadId` at `0x140004d0b`
- `KERNEL32!OutputDebugStringW` at `0x140004e9c`
- `KERNEL32!OutputDebugStringW` at `0x140004e9c`
- `KERNEL32!IsDebuggerPresent` at `0x140004e2a`
- `KERNEL32!IsDebuggerPresent` at `0x140004e2a`

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
0x140004be8  mov     [rsp+arg_10], rbx
0x140004bed  mov     [rsp+arg_8], edx
0x140004bf1  mov     [rsp+arg_0], rcx
0x140004bf6  push    rbp
0x140004bf7  push    rsi
0x140004bf8  push    rdi
0x140004bf9  push    r12
0x140004bfb  push    r13
0x140004bfd  push    r14
0x140004bff  push    r15
0x140004c01  sub     rsp, 40h
0x140004c05  mov     r12, r9
0x140004c08  mov     r13, r8
0x140004c0b  mov     r10, rcx
0x140004c0e  xor     eax, eax
0x140004c10  mov     rsi, [rsp+78h+lpOutputString]
0x140004c18  mov     [rsi], ax
0x140004c1b  mov     rax, [rsp+78h+arg_60]
0x140004c23  mov     byte ptr [rax], 0
0x140004c26  mov     r14, [rsp+78h+arg_38]
0x140004c2e  mov     edi, [r14]
0x140004c31  mov     rbx, [rsp+78h+arg_78]
0x140004c39  mov     [rbx+8], edi
0x140004c3c  mov     eax, [r14+4]
0x140004c40  mov     [rbx+0Ch], eax
0x140004c43  xor     ebp, ebp
0x140004c45  mov     r15d, [rsp+78h+arg_30]
0x140004c4d  mov     ecx, r15d
0x140004c50  test    r15d, r15d
0x140004c53  jz      short loc_140004CBB
0x140004c55  sub     ecx, 1
0x140004c58  jz      short loc_140004CB2
0x140004c5a  sub     ecx, 1
0x140004c5d  jz      short loc_140004C6D
0x140004c5f  cmp     ecx, 1
0x140004c62  jnz     short loc_140004CC4
0x140004c64  mov     ecx, edi; this
0x140004c66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004c6b  jmp     short loc_140004CC2
0x140004c6d  test    edi, edi
0x140004c6f  js      short loc_140004CA9
0x140004c71  mov     edi, 8007029Ch
0x140004c76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004c7a  mov     rax, [rsp+78h+arg_28]
0x140004c82  mov     [rsp+78h+var_50], rax; __int64
0x140004c87  mov     rax, [rsp+78h+arg_20]
0x140004c8f  mov     [rsp+78h+var_58], rax; __int64
0x140004c94  mov     rcx, r10; int
0x140004c97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004c9c  mov     [rbx+8], edi
0x140004c9f  mov     ecx, edi; this
0x140004ca1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004ca6  mov     [rbx+0Ch], eax
0x140004ca9  mov     ecx, edi; this
0x140004cab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004cb0  jmp     short loc_140004CC2
0x140004cb2  mov     ecx, edi; this
0x140004cb4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004cb9  jmp     short loc_140004CC2
0x140004cbb  mov     ecx, edi; this
0x140004cbd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004cc2  mov     ebp, eax
0x140004cc4  mov     [rbx], r15d
0x140004cc7  mov     eax, [rsp+78h+arg_70]
0x140004cce  mov     [rbx+4], eax
0x140004cd1  cmp     dword ptr [r14+8], 1
0x140004cd6  jnz     short loc_140004CDE
0x140004cd8  or      eax, 8
0x140004cdb  mov     [rbx+4], eax
0x140004cde  mov     eax, 1
0x140004ce3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004ceb  inc     eax
0x140004ced  mov     [rbx+10h], eax
0x140004cf0  mov     rax, [rsp+78h+arg_40]
0x140004cf8  xor     edi, edi
0x140004cfa  test    rax, rax
0x140004cfd  jz      short loc_140004D04
0x140004cff  cmp     [rax], di
0x140004d02  jnz     short loc_140004D07
0x140004d04  mov     rax, rdi
0x140004d07  mov     [rbx+18h], rax
0x140004d0b  call    cs:__imp_GetCurrentThreadId
0x140004d11  mov     [rbx+20h], eax
0x140004d14  mov     [rbx+38h], r13
0x140004d18  mov     eax, [rsp+78h+arg_8]
0x140004d1f  mov     [rbx+40h], eax
0x140004d22  mov     [rbx+44h], ebp
0x140004d25  mov     rax, [rsp+78h+arg_20]
0x140004d2d  mov     [rbx+28h], rax
0x140004d31  mov     [rbx+30h], r12
0x140004d35  mov     rax, [rsp+78h+arg_28]
0x140004d3d  mov     [rbx+88h], rax
0x140004d44  mov     rax, [rsp+78h+arg_0]
0x140004d4c  mov     [rbx+90h], rax
0x140004d53  mov     [rbx+48h], rdi
0x140004d57  xorps   xmm0, xmm0
0x140004d5a  xor     eax, eax
0x140004d5c  movups  xmmword ptr [rbx+68h], xmm0
0x140004d60  mov     [rbx+78h], rax
0x140004d64  movups  xmmword ptr [rbx+50h], xmm0
0x140004d68  mov     [rbx+60h], rax
0x140004d6c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004d73  test    rax, rax
0x140004d76  jz      short loc_140004D7F
0x140004d78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d7d  jmp     short loc_140004D82
0x140004d7f  mov     rax, rdi
0x140004d82  mov     [rbx+80h], rax
0x140004d89  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004d90  test    rax, rax
0x140004d93  jz      short loc_140004D9D
0x140004d95  mov     rcx, rbx
0x140004d98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004d9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004da4  test    rax, rax
0x140004da7  jz      short loc_140004DBF
0x140004da9  mov     r8d, 400h
0x140004daf  mov     rdx, [rsp+78h+arg_60]
0x140004db7  mov     rcx, rbx
0x140004dba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dbf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004dc6  test    rax, rax
0x140004dc9  jz      short loc_140004DD3
0x140004dcb  mov     rcx, rbx
0x140004dce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004dd3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004dda  test    rax, rax
0x140004ddd  jz      short loc_140004DED
0x140004ddf  test    byte ptr [rbx+4], 2
0x140004de3  jnz     short loc_140004DED
0x140004de5  mov     rcx, rbx
0x140004de8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ded  cmp     [rbx+8], edi
0x140004df0  jl      short loc_140004E0C
0x140004df2  cmp     r15d, 3
0x140004df6  jnz     loc_140004EDB
0x140004dfc  mov     ecx, 8000FFFFh; this
0x140004e01  mov     [rbx+8], ecx
0x140004e04  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004e09  mov     [rbx+0Ch], eax
0x140004e0c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004e13  jnz     short loc_140004E34
0x140004e15  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004e1c  test    rax, rax
0x140004e1f  jz      short loc_140004E2A
0x140004e21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e26  test    al, al
0x140004e28  jmp     short loc_140004E32
0x140004e2a  call    cs:__imp_IsDebuggerPresent
0x140004e30  test    eax, eax
0x140004e32  jz      short loc_140004E3A
0x140004e34  test    byte ptr [rbx+4], 2
0x140004e38  jz      short loc_140004E5E
0x140004e3a  mov     rax, cs:g_pfnResultLoggingCallback
0x140004e41  test    rax, rax
0x140004e44  jz      short loc_140004EA2
0x140004e46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004e4d  jnz     short loc_140004EA2
0x140004e4f  xor     r8d, r8d
0x140004e52  xor     edx, edx
0x140004e54  mov     rcx, rbx
0x140004e57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e5c  jmp     short loc_140004EA2
0x140004e5e  mov     ebp, 800h
0x140004e63  mov     rax, cs:g_pfnResultLoggingCallback
0x140004e6a  test    rax, rax
0x140004e6d  jz      short loc_140004E86
0x140004e6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004e76  jnz     short loc_140004E86
0x140004e78  mov     r8d, ebp
0x140004e7b  mov     rdx, rsi
0x140004e7e  mov     rcx, rbx
0x140004e81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e86  cmp     [rsi], di
0x140004e89  jnz     short loc_140004E99
0x140004e8b  mov     r8, rbx; unsigned __int64
0x140004e8e  mov     rdx, rbp; unsigned __int16 *
0x140004e91  mov     rcx, rsi; this
0x140004e94  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004e99  mov     rcx, rsi; lpOutputString
0x140004e9c  call    cs:__imp_OutputDebugStringW
0x140004ea2  test    byte ptr [rbx+4], 4
0x140004ea6  jnz     short loc_140004EB1
0x140004ea8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004eaf  jz      short loc_140004EC3
0x140004eb1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004eb8  test    rax, rax
0x140004ebb  jz      short loc_140004EC3
0x140004ebd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec2  nop
0x140004ec3  mov     rbx, [rsp+78h+arg_10]
0x140004ecb  add     rsp, 40h
0x140004ecf  pop     r15
0x140004ed1  pop     r14
0x140004ed3  pop     r13
0x140004ed5  pop     r12
0x140004ed7  pop     rdi
0x140004ed8  pop     rsi
0x140004ed9  pop     rbp
0x140004eda  retn
0x140004edb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
