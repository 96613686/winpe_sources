# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016e74`
- end: `0x18001716d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180016d08`
- `0x180026550`
- `0x18002c40c`

## callees

- `0x180009be0`
- `0x180016e74`
- `0x1800261ec`
- `0x180026bfc`
- `0x180027040`
- `0x180027060`
- `0x180027074`
- `0x180027090`
- `0x180027408`
- `0x18006a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016f97`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016f97`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800170b6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800170b6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017128`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017128`

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
0x180016e74  mov     [rsp+arg_10], rbx
0x180016e79  mov     [rsp+arg_8], edx
0x180016e7d  mov     [rsp+arg_0], rcx
0x180016e82  push    rbp
0x180016e83  push    rsi
0x180016e84  push    rdi
0x180016e85  push    r12
0x180016e87  push    r13
0x180016e89  push    r14
0x180016e8b  push    r15
0x180016e8d  sub     rsp, 40h
0x180016e91  mov     r12, r9
0x180016e94  mov     r13, r8
0x180016e97  mov     r10, rcx
0x180016e9a  xor     eax, eax
0x180016e9c  mov     rsi, [rsp+78h+lpOutputString]
0x180016ea4  mov     [rsi], ax
0x180016ea7  mov     rax, [rsp+78h+arg_60]
0x180016eaf  mov     byte ptr [rax], 0
0x180016eb2  mov     r14, [rsp+78h+arg_38]
0x180016eba  mov     edi, [r14]
0x180016ebd  mov     rbx, [rsp+78h+arg_78]
0x180016ec5  mov     [rbx+8], edi
0x180016ec8  mov     eax, [r14+4]
0x180016ecc  mov     [rbx+0Ch], eax
0x180016ecf  xor     ebp, ebp
0x180016ed1  mov     r15d, [rsp+78h+arg_30]
0x180016ed9  mov     ecx, r15d
0x180016edc  test    r15d, r15d
0x180016edf  jz      short loc_180016F47
0x180016ee1  sub     ecx, 1
0x180016ee4  jz      short loc_180016F3E
0x180016ee6  sub     ecx, 1
0x180016ee9  jz      short loc_180016EF9
0x180016eeb  cmp     ecx, 1
0x180016eee  jnz     short loc_180016F50
0x180016ef0  mov     ecx, edi; this
0x180016ef2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016ef7  jmp     short loc_180016F4E
0x180016ef9  test    edi, edi
0x180016efb  js      short loc_180016F35
0x180016efd  mov     edi, 8007029Ch
0x180016f02  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180016f06  mov     rax, [rsp+78h+arg_28]
0x180016f0e  mov     [rsp+78h+var_50], rax; __int64
0x180016f13  mov     rax, [rsp+78h+arg_20]
0x180016f1b  mov     [rsp+78h+var_58], rax; __int64
0x180016f20  mov     rcx, r10; int
0x180016f23  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016f28  mov     [rbx+8], edi
0x180016f2b  mov     ecx, edi; this
0x180016f2d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016f32  mov     [rbx+0Ch], eax
0x180016f35  mov     ecx, edi; this
0x180016f37  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180016f3c  jmp     short loc_180016F4E
0x180016f3e  mov     ecx, edi; this
0x180016f40  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016f45  jmp     short loc_180016F4E
0x180016f47  mov     ecx, edi; this
0x180016f49  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180016f4e  mov     ebp, eax
0x180016f50  mov     [rbx], r15d
0x180016f53  mov     eax, [rsp+78h+arg_70]
0x180016f5a  mov     [rbx+4], eax
0x180016f5d  cmp     dword ptr [r14+8], 1
0x180016f62  jnz     short loc_180016F6A
0x180016f64  or      eax, 8
0x180016f67  mov     [rbx+4], eax
0x180016f6a  mov     eax, 1
0x180016f6f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016f77  inc     eax
0x180016f79  mov     [rbx+10h], eax
0x180016f7c  mov     rax, [rsp+78h+arg_40]
0x180016f84  xor     edi, edi
0x180016f86  test    rax, rax
0x180016f89  jz      short loc_180016F90
0x180016f8b  cmp     [rax], di
0x180016f8e  jnz     short loc_180016F93
0x180016f90  mov     rax, rdi
0x180016f93  mov     [rbx+18h], rax
0x180016f97  call    cs:__imp_GetCurrentThreadId
0x180016f9d  mov     [rbx+20h], eax
0x180016fa0  mov     [rbx+38h], r13
0x180016fa4  mov     eax, [rsp+78h+arg_8]
0x180016fab  mov     [rbx+40h], eax
0x180016fae  mov     [rbx+44h], ebp
0x180016fb1  mov     rax, [rsp+78h+arg_20]
0x180016fb9  mov     [rbx+28h], rax
0x180016fbd  mov     [rbx+30h], r12
0x180016fc1  mov     rax, [rsp+78h+arg_28]
0x180016fc9  mov     [rbx+88h], rax
0x180016fd0  mov     rax, [rsp+78h+arg_0]
0x180016fd8  mov     [rbx+90h], rax
0x180016fdf  mov     [rbx+48h], rdi
0x180016fe3  xorps   xmm0, xmm0
0x180016fe6  xor     eax, eax
0x180016fe8  movups  xmmword ptr [rbx+68h], xmm0
0x180016fec  mov     [rbx+78h], rax
0x180016ff0  movups  xmmword ptr [rbx+50h], xmm0
0x180016ff4  mov     [rbx+60h], rax
0x180016ff8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016fff  test    rax, rax
0x180017002  jz      short loc_18001700B
0x180017004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017009  jmp     short loc_18001700E
0x18001700b  mov     rax, rdi
0x18001700e  mov     [rbx+80h], rax
0x180017015  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001701c  test    rax, rax
0x18001701f  jz      short loc_180017029
0x180017021  mov     rcx, rbx
0x180017024  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017029  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180017030  test    rax, rax
0x180017033  jz      short loc_18001704B
0x180017035  mov     r8d, 400h
0x18001703b  mov     rdx, [rsp+78h+arg_60]
0x180017043  mov     rcx, rbx
0x180017046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001704b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017052  test    rax, rax
0x180017055  jz      short loc_18001705F
0x180017057  mov     rcx, rbx
0x18001705a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001705f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017066  test    rax, rax
0x180017069  jz      short loc_180017079
0x18001706b  test    byte ptr [rbx+4], 2
0x18001706f  jnz     short loc_180017079
0x180017071  mov     rcx, rbx
0x180017074  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017079  cmp     [rbx+8], edi
0x18001707c  jl      short loc_180017098
0x18001707e  cmp     r15d, 3
0x180017082  jnz     loc_180017167
0x180017088  mov     ecx, 8000FFFFh; this
0x18001708d  mov     [rbx+8], ecx
0x180017090  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180017095  mov     [rbx+0Ch], eax
0x180017098  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001709f  jnz     short loc_1800170C0
0x1800170a1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800170a8  test    rax, rax
0x1800170ab  jz      short loc_1800170B6
0x1800170ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170b2  test    al, al
0x1800170b4  jmp     short loc_1800170BE
0x1800170b6  call    cs:__imp_IsDebuggerPresent
0x1800170bc  test    eax, eax
0x1800170be  jz      short loc_1800170C6
0x1800170c0  test    byte ptr [rbx+4], 2
0x1800170c4  jz      short loc_1800170EA
0x1800170c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800170cd  test    rax, rax
0x1800170d0  jz      short loc_18001712E
0x1800170d2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800170d9  jnz     short loc_18001712E
0x1800170db  xor     r8d, r8d
0x1800170de  xor     edx, edx
0x1800170e0  mov     rcx, rbx
0x1800170e3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e8  jmp     short loc_18001712E
0x1800170ea  mov     ebp, 800h
0x1800170ef  mov     rax, cs:g_pfnResultLoggingCallback
0x1800170f6  test    rax, rax
0x1800170f9  jz      short loc_180017112
0x1800170fb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180017102  jnz     short loc_180017112
0x180017104  mov     r8d, ebp
0x180017107  mov     rdx, rsi
0x18001710a  mov     rcx, rbx
0x18001710d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017112  cmp     [rsi], di
0x180017115  jnz     short loc_180017125
0x180017117  mov     r8, rbx; unsigned __int64
0x18001711a  mov     rdx, rbp; unsigned __int16 *
0x18001711d  mov     rcx, rsi; this
0x180017120  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180017125  mov     rcx, rsi; lpOutputString
0x180017128  call    cs:__imp_OutputDebugStringW
0x18001712e  test    byte ptr [rbx+4], 4
0x180017132  jnz     short loc_18001713D
0x180017134  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001713b  jz      short loc_18001714F
0x18001713d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180017144  test    rax, rax
0x180017147  jz      short loc_18001714F
0x180017149  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001714e  nop
0x18001714f  mov     rbx, [rsp+78h+arg_10]
0x180017157  add     rsp, 40h
0x18001715b  pop     r15
0x18001715d  pop     r14
0x18001715f  pop     r13
0x180017161  pop     r12
0x180017163  pop     rdi
0x180017164  pop     rsi
0x180017165  pop     rbp
0x180017166  retn
0x180017167  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
