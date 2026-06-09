# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180012b9c`
- end: `0x180012e95`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180010168`

## callees

- `0x18000fba4`
- `0x180012174`
- `0x180012910`
- `0x180012b9c`
- `0x1800137c8`
- `0x1800137f0`
- `0x18001391c`
- `0x180013938`
- `0x180015b5c`
- `0x180019010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x180012dde`
- `KERNEL32!IsDebuggerPresent` at `0x180012dde`
- `KERNEL32!OutputDebugStringW` at `0x180012e50`
- `KERNEL32!OutputDebugStringW` at `0x180012e50`
- `KERNEL32!GetCurrentThreadId` at `0x180012cbf`
- `KERNEL32!GetCurrentThreadId` at `0x180012cbf`

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
0x180012b9c  mov     [rsp+arg_10], rbx
0x180012ba1  mov     [rsp+arg_8], edx
0x180012ba5  mov     [rsp+arg_0], rcx
0x180012baa  push    rbp
0x180012bab  push    rsi
0x180012bac  push    rdi
0x180012bad  push    r12
0x180012baf  push    r13
0x180012bb1  push    r14
0x180012bb3  push    r15
0x180012bb5  sub     rsp, 40h
0x180012bb9  mov     r12, r9
0x180012bbc  mov     r13, r8
0x180012bbf  mov     r10, rcx
0x180012bc2  xor     eax, eax
0x180012bc4  mov     rsi, [rsp+78h+lpOutputString]
0x180012bcc  mov     [rsi], ax
0x180012bcf  mov     rax, [rsp+78h+arg_60]
0x180012bd7  mov     byte ptr [rax], 0
0x180012bda  mov     r14, [rsp+78h+arg_38]
0x180012be2  mov     edi, [r14]
0x180012be5  mov     rbx, [rsp+78h+arg_78]
0x180012bed  mov     [rbx+8], edi
0x180012bf0  mov     eax, [r14+4]
0x180012bf4  mov     [rbx+0Ch], eax
0x180012bf7  xor     ebp, ebp
0x180012bf9  mov     r15d, [rsp+78h+arg_30]
0x180012c01  mov     ecx, r15d
0x180012c04  test    r15d, r15d
0x180012c07  jz      short loc_180012C6F
0x180012c09  sub     ecx, 1
0x180012c0c  jz      short loc_180012C66
0x180012c0e  sub     ecx, 1
0x180012c11  jz      short loc_180012C21
0x180012c13  cmp     ecx, 1
0x180012c16  jnz     short loc_180012C78
0x180012c18  mov     ecx, edi; this
0x180012c1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180012c1f  jmp     short loc_180012C76
0x180012c21  test    edi, edi
0x180012c23  js      short loc_180012C5D
0x180012c25  mov     edi, 8007029Ch
0x180012c2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180012c2e  mov     rax, [rsp+78h+arg_28]
0x180012c36  mov     [rsp+78h+var_50], rax; __int64
0x180012c3b  mov     rax, [rsp+78h+arg_20]
0x180012c43  mov     [rsp+78h+var_58], rax; __int64
0x180012c48  mov     rcx, r10; int
0x180012c4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180012c50  mov     [rbx+8], edi
0x180012c53  mov     ecx, edi; this
0x180012c55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012c5a  mov     [rbx+0Ch], eax
0x180012c5d  mov     ecx, edi; this
0x180012c5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180012c64  jmp     short loc_180012C76
0x180012c66  mov     ecx, edi; this
0x180012c68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180012c6d  jmp     short loc_180012C76
0x180012c6f  mov     ecx, edi; this
0x180012c71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180012c76  mov     ebp, eax
0x180012c78  mov     [rbx], r15d
0x180012c7b  mov     eax, [rsp+78h+arg_70]
0x180012c82  mov     [rbx+4], eax
0x180012c85  cmp     dword ptr [r14+8], 1
0x180012c8a  jnz     short loc_180012C92
0x180012c8c  or      eax, 8
0x180012c8f  mov     [rbx+4], eax
0x180012c92  mov     eax, 1
0x180012c97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180012c9f  inc     eax
0x180012ca1  mov     [rbx+10h], eax
0x180012ca4  mov     rax, [rsp+78h+arg_40]
0x180012cac  xor     edi, edi
0x180012cae  test    rax, rax
0x180012cb1  jz      short loc_180012CB8
0x180012cb3  cmp     [rax], di
0x180012cb6  jnz     short loc_180012CBB
0x180012cb8  mov     rax, rdi
0x180012cbb  mov     [rbx+18h], rax
0x180012cbf  call    cs:__imp_GetCurrentThreadId
0x180012cc5  mov     [rbx+20h], eax
0x180012cc8  mov     [rbx+38h], r13
0x180012ccc  mov     eax, [rsp+78h+arg_8]
0x180012cd3  mov     [rbx+40h], eax
0x180012cd6  mov     [rbx+44h], ebp
0x180012cd9  mov     rax, [rsp+78h+arg_20]
0x180012ce1  mov     [rbx+28h], rax
0x180012ce5  mov     [rbx+30h], r12
0x180012ce9  mov     rax, [rsp+78h+arg_28]
0x180012cf1  mov     [rbx+88h], rax
0x180012cf8  mov     rax, [rsp+78h+arg_0]
0x180012d00  mov     [rbx+90h], rax
0x180012d07  mov     [rbx+48h], rdi
0x180012d0b  xorps   xmm0, xmm0
0x180012d0e  xor     eax, eax
0x180012d10  movups  xmmword ptr [rbx+68h], xmm0
0x180012d14  mov     [rbx+78h], rax
0x180012d18  movups  xmmword ptr [rbx+50h], xmm0
0x180012d1c  mov     [rbx+60h], rax
0x180012d20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180012d27  test    rax, rax
0x180012d2a  jz      short loc_180012D33
0x180012d2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d31  jmp     short loc_180012D36
0x180012d33  mov     rax, rdi
0x180012d36  mov     [rbx+80h], rax
0x180012d3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012d44  test    rax, rax
0x180012d47  jz      short loc_180012D51
0x180012d49  mov     rcx, rbx
0x180012d4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012d58  test    rax, rax
0x180012d5b  jz      short loc_180012D73
0x180012d5d  mov     r8d, 400h
0x180012d63  mov     rdx, [rsp+78h+arg_60]
0x180012d6b  mov     rcx, rbx
0x180012d6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012d7a  test    rax, rax
0x180012d7d  jz      short loc_180012D87
0x180012d7f  mov     rcx, rbx
0x180012d82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012d87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012d8e  test    rax, rax
0x180012d91  jz      short loc_180012DA1
0x180012d93  test    byte ptr [rbx+4], 2
0x180012d97  jnz     short loc_180012DA1
0x180012d99  mov     rcx, rbx
0x180012d9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012da1  cmp     [rbx+8], edi
0x180012da4  jl      short loc_180012DC0
0x180012da6  cmp     r15d, 3
0x180012daa  jnz     loc_180012E8F
0x180012db0  mov     ecx, 8000FFFFh; this
0x180012db5  mov     [rbx+8], ecx
0x180012db8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012dbd  mov     [rbx+0Ch], eax
0x180012dc0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180012dc7  jnz     short loc_180012DE8
0x180012dc9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012dd0  test    rax, rax
0x180012dd3  jz      short loc_180012DDE
0x180012dd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012dda  test    al, al
0x180012ddc  jmp     short loc_180012DE6
0x180012dde  call    cs:__imp_IsDebuggerPresent
0x180012de4  test    eax, eax
0x180012de6  jz      short loc_180012DEE
0x180012de8  test    byte ptr [rbx+4], 2
0x180012dec  jz      short loc_180012E12
0x180012dee  mov     rax, cs:g_pfnResultLoggingCallback
0x180012df5  test    rax, rax
0x180012df8  jz      short loc_180012E56
0x180012dfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012e01  jnz     short loc_180012E56
0x180012e03  xor     r8d, r8d
0x180012e06  xor     edx, edx
0x180012e08  mov     rcx, rbx
0x180012e0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e10  jmp     short loc_180012E56
0x180012e12  mov     ebp, 800h
0x180012e17  mov     rax, cs:g_pfnResultLoggingCallback
0x180012e1e  test    rax, rax
0x180012e21  jz      short loc_180012E3A
0x180012e23  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012e2a  jnz     short loc_180012E3A
0x180012e2c  mov     r8d, ebp
0x180012e2f  mov     rdx, rsi
0x180012e32  mov     rcx, rbx
0x180012e35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e3a  cmp     [rsi], di
0x180012e3d  jnz     short loc_180012E4D
0x180012e3f  mov     r8, rbx; unsigned __int64
0x180012e42  mov     rdx, rbp; unsigned __int16 *
0x180012e45  mov     rcx, rsi; this
0x180012e48  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012e4d  mov     rcx, rsi; lpOutputString
0x180012e50  call    cs:__imp_OutputDebugStringW
0x180012e56  test    byte ptr [rbx+4], 4
0x180012e5a  jnz     short loc_180012E65
0x180012e5c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012e63  jz      short loc_180012E77
0x180012e65  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012e6c  test    rax, rax
0x180012e6f  jz      short loc_180012E77
0x180012e71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e76  nop
0x180012e77  mov     rbx, [rsp+78h+arg_10]
0x180012e7f  add     rsp, 40h
0x180012e83  pop     r15
0x180012e85  pop     r14
0x180012e87  pop     r13
0x180012e89  pop     r12
0x180012e8b  pop     rdi
0x180012e8c  pop     rsi
0x180012e8d  pop     rbp
0x180012e8e  retn
0x180012e8f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
