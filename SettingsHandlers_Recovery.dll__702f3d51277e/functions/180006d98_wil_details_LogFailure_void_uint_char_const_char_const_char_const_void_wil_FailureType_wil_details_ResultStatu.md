# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006d98`
- end: `0x180007091`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004068`

## callees

- `0x180003a74`
- `0x180006304`
- `0x180006aa4`
- `0x180006d98`
- `0x180007ad0`
- `0x180007af0`
- `0x180007c1c`
- `0x180007c38`
- `0x18000a48c`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ebb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006ebb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006fda`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006fda`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000704c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000704c`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x180006d98  mov     [rsp+arg_10], rbx
0x180006d9d  mov     [rsp+arg_8], edx
0x180006da1  mov     [rsp+arg_0], rcx
0x180006da6  push    rbp
0x180006da7  push    rsi
0x180006da8  push    rdi
0x180006da9  push    r12
0x180006dab  push    r13
0x180006dad  push    r14
0x180006daf  push    r15
0x180006db1  sub     rsp, 40h
0x180006db5  mov     r12, r9
0x180006db8  mov     r13, r8
0x180006dbb  mov     r10, rcx
0x180006dbe  xor     eax, eax
0x180006dc0  mov     rsi, [rsp+78h+lpOutputString]
0x180006dc8  mov     [rsi], ax
0x180006dcb  mov     rax, [rsp+78h+arg_60]
0x180006dd3  mov     byte ptr [rax], 0
0x180006dd6  mov     r14, [rsp+78h+arg_38]
0x180006dde  mov     edi, [r14]
0x180006de1  mov     rbx, [rsp+78h+arg_78]
0x180006de9  mov     [rbx+8], edi
0x180006dec  mov     eax, [r14+4]
0x180006df0  mov     [rbx+0Ch], eax
0x180006df3  xor     ebp, ebp
0x180006df5  mov     r15d, [rsp+78h+arg_30]
0x180006dfd  mov     ecx, r15d
0x180006e00  test    r15d, r15d
0x180006e03  jz      short loc_180006E6B
0x180006e05  sub     ecx, 1
0x180006e08  jz      short loc_180006E62
0x180006e0a  sub     ecx, 1
0x180006e0d  jz      short loc_180006E1D
0x180006e0f  cmp     ecx, 1
0x180006e12  jnz     short loc_180006E74
0x180006e14  mov     ecx, edi; this
0x180006e16  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006e1b  jmp     short loc_180006E72
0x180006e1d  test    edi, edi
0x180006e1f  js      short loc_180006E59
0x180006e21  mov     edi, 8007029Ch
0x180006e26  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006e2a  mov     rax, [rsp+78h+arg_28]
0x180006e32  mov     [rsp+78h+var_50], rax; __int64
0x180006e37  mov     rax, [rsp+78h+arg_20]
0x180006e3f  mov     [rsp+78h+var_58], rax; __int64
0x180006e44  mov     rcx, r10; int
0x180006e47  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006e4c  mov     [rbx+8], edi
0x180006e4f  mov     ecx, edi; this
0x180006e51  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006e56  mov     [rbx+0Ch], eax
0x180006e59  mov     ecx, edi; this
0x180006e5b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006e60  jmp     short loc_180006E72
0x180006e62  mov     ecx, edi; this
0x180006e64  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006e69  jmp     short loc_180006E72
0x180006e6b  mov     ecx, edi; this
0x180006e6d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006e72  mov     ebp, eax
0x180006e74  mov     [rbx], r15d
0x180006e77  mov     eax, [rsp+78h+arg_70]
0x180006e7e  mov     [rbx+4], eax
0x180006e81  cmp     dword ptr [r14+8], 1
0x180006e86  jnz     short loc_180006E8E
0x180006e88  or      eax, 8
0x180006e8b  mov     [rbx+4], eax
0x180006e8e  mov     eax, 1
0x180006e93  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006e9b  inc     eax
0x180006e9d  mov     [rbx+10h], eax
0x180006ea0  mov     rax, [rsp+78h+arg_40]
0x180006ea8  xor     edi, edi
0x180006eaa  test    rax, rax
0x180006ead  jz      short loc_180006EB4
0x180006eaf  cmp     [rax], di
0x180006eb2  jnz     short loc_180006EB7
0x180006eb4  mov     rax, rdi
0x180006eb7  mov     [rbx+18h], rax
0x180006ebb  call    cs:__imp_GetCurrentThreadId
0x180006ec1  mov     [rbx+20h], eax
0x180006ec4  mov     [rbx+38h], r13
0x180006ec8  mov     eax, [rsp+78h+arg_8]
0x180006ecf  mov     [rbx+40h], eax
0x180006ed2  mov     [rbx+44h], ebp
0x180006ed5  mov     rax, [rsp+78h+arg_20]
0x180006edd  mov     [rbx+28h], rax
0x180006ee1  mov     [rbx+30h], r12
0x180006ee5  mov     rax, [rsp+78h+arg_28]
0x180006eed  mov     [rbx+88h], rax
0x180006ef4  mov     rax, [rsp+78h+arg_0]
0x180006efc  mov     [rbx+90h], rax
0x180006f03  mov     [rbx+48h], rdi
0x180006f07  xorps   xmm0, xmm0
0x180006f0a  xor     eax, eax
0x180006f0c  movups  xmmword ptr [rbx+68h], xmm0
0x180006f10  mov     [rbx+78h], rax
0x180006f14  movups  xmmword ptr [rbx+50h], xmm0
0x180006f18  mov     [rbx+60h], rax
0x180006f1c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006f23  test    rax, rax
0x180006f26  jz      short loc_180006F2F
0x180006f28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2d  jmp     short loc_180006F32
0x180006f2f  mov     rax, rdi
0x180006f32  mov     [rbx+80h], rax
0x180006f39  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006f40  test    rax, rax
0x180006f43  jz      short loc_180006F4D
0x180006f45  mov     rcx, rbx
0x180006f48  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f4d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006f54  test    rax, rax
0x180006f57  jz      short loc_180006F6F
0x180006f59  mov     r8d, 400h
0x180006f5f  mov     rdx, [rsp+78h+arg_60]
0x180006f67  mov     rcx, rbx
0x180006f6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f6f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006f76  test    rax, rax
0x180006f79  jz      short loc_180006F83
0x180006f7b  mov     rcx, rbx
0x180006f7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f83  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006f8a  test    rax, rax
0x180006f8d  jz      short loc_180006F9D
0x180006f8f  test    byte ptr [rbx+4], 2
0x180006f93  jnz     short loc_180006F9D
0x180006f95  mov     rcx, rbx
0x180006f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9d  cmp     [rbx+8], edi
0x180006fa0  jl      short loc_180006FBC
0x180006fa2  cmp     r15d, 3
0x180006fa6  jnz     loc_18000708B
0x180006fac  mov     ecx, 8000FFFFh; this
0x180006fb1  mov     [rbx+8], ecx
0x180006fb4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006fb9  mov     [rbx+0Ch], eax
0x180006fbc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006fc3  jnz     short loc_180006FE4
0x180006fc5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006fcc  test    rax, rax
0x180006fcf  jz      short loc_180006FDA
0x180006fd1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fd6  test    al, al
0x180006fd8  jmp     short loc_180006FE2
0x180006fda  call    cs:__imp_IsDebuggerPresent
0x180006fe0  test    eax, eax
0x180006fe2  jz      short loc_180006FEA
0x180006fe4  test    byte ptr [rbx+4], 2
0x180006fe8  jz      short loc_18000700E
0x180006fea  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ff1  test    rax, rax
0x180006ff4  jz      short loc_180007052
0x180006ff6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006ffd  jnz     short loc_180007052
0x180006fff  xor     r8d, r8d
0x180007002  xor     edx, edx
0x180007004  mov     rcx, rbx
0x180007007  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000700c  jmp     short loc_180007052
0x18000700e  mov     ebp, 800h
0x180007013  mov     rax, cs:g_pfnResultLoggingCallback
0x18000701a  test    rax, rax
0x18000701d  jz      short loc_180007036
0x18000701f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007026  jnz     short loc_180007036
0x180007028  mov     r8d, ebp
0x18000702b  mov     rdx, rsi
0x18000702e  mov     rcx, rbx
0x180007031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007036  cmp     [rsi], di
0x180007039  jnz     short loc_180007049
0x18000703b  mov     r8, rbx; unsigned __int64
0x18000703e  mov     rdx, rbp; unsigned __int16 *
0x180007041  mov     rcx, rsi; this
0x180007044  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007049  mov     rcx, rsi; lpOutputString
0x18000704c  call    cs:__imp_OutputDebugStringW
0x180007052  test    byte ptr [rbx+4], 4
0x180007056  jnz     short loc_180007061
0x180007058  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000705f  jz      short loc_180007073
0x180007061  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007068  test    rax, rax
0x18000706b  jz      short loc_180007073
0x18000706d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007072  nop
0x180007073  mov     rbx, [rsp+78h+arg_10]
0x18000707b  add     rsp, 40h
0x18000707f  pop     r15
0x180007081  pop     r14
0x180007083  pop     r13
0x180007085  pop     r12
0x180007087  pop     rdi
0x180007088  pop     rsi
0x180007089  pop     rbp
0x18000708a  retn
0x18000708b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
