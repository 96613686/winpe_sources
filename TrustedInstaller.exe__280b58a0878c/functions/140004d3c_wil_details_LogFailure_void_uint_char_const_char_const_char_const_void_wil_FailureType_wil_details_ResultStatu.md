# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004d3c`
- end: `0x140005034`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400036a0`
- `0x1400039f4`

## callees

- `0x1400035d8`
- `0x140004384`
- `0x140004b78`
- `0x140004d3c`
- `0x1400053b0`
- `0x1400053d0`
- `0x1400053e4`
- `0x140005400`
- `0x140005dc8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e5f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004ff0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004ff0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f7e`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x140004d3c  mov     [rsp+arg_10], rbx
0x140004d41  mov     [rsp+arg_8], edx
0x140004d45  mov     [rsp+arg_0], rcx
0x140004d4a  push    rbp
0x140004d4b  push    rsi
0x140004d4c  push    rdi
0x140004d4d  push    r12
0x140004d4f  push    r13
0x140004d51  push    r14
0x140004d53  push    r15
0x140004d55  sub     rsp, 40h
0x140004d59  mov     r14, [rsp+78h+arg_38]
0x140004d61  xor     eax, eax
0x140004d63  mov     rbx, [rsp+78h+arg_78]
0x140004d6b  xor     ebp, ebp
0x140004d6d  mov     r15d, [rsp+78h+arg_30]
0x140004d75  mov     r10, rcx
0x140004d78  mov     rsi, [rsp+78h+lpOutputString]
0x140004d80  mov     r12, r9
0x140004d83  mov     r13, r8
0x140004d86  mov     ecx, r15d
0x140004d89  mov     [rsi], ax
0x140004d8c  mov     rax, [rsp+78h+arg_60]
0x140004d94  mov     byte ptr [rax], 0
0x140004d97  mov     edi, [r14]
0x140004d9a  mov     [rbx+8], edi
0x140004d9d  mov     eax, [r14+4]
0x140004da1  mov     [rbx+0Ch], eax
0x140004da4  test    r15d, r15d
0x140004da7  jz      short loc_140004E0F
0x140004da9  sub     ecx, 1
0x140004dac  jz      short loc_140004E06
0x140004dae  sub     ecx, 1
0x140004db1  jz      short loc_140004DC1
0x140004db3  cmp     ecx, 1
0x140004db6  jnz     short loc_140004E18
0x140004db8  mov     ecx, edi; this
0x140004dba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004dbf  jmp     short loc_140004E16
0x140004dc1  test    edi, edi
0x140004dc3  js      short loc_140004DFD
0x140004dc5  mov     rax, [rsp+78h+arg_28]
0x140004dcd  mov     edi, 8007029Ch
0x140004dd2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004dd6  mov     rcx, r10; int
0x140004dd9  mov     [rsp+78h+var_50], rax; __int64
0x140004dde  mov     rax, [rsp+78h+arg_20]
0x140004de6  mov     [rsp+78h+var_58], rax; __int64
0x140004deb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004df0  mov     ecx, edi; this
0x140004df2  mov     [rbx+8], edi
0x140004df5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004dfa  mov     [rbx+0Ch], eax
0x140004dfd  mov     ecx, edi; this
0x140004dff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004e04  jmp     short loc_140004E16
0x140004e06  mov     ecx, edi; this
0x140004e08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004e0d  jmp     short loc_140004E16
0x140004e0f  mov     ecx, edi; this
0x140004e11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004e16  mov     ebp, eax
0x140004e18  mov     eax, [rsp+78h+arg_70]
0x140004e1f  mov     [rbx+4], eax
0x140004e22  mov     [rbx], r15d
0x140004e25  cmp     dword ptr [r14+8], 1
0x140004e2a  jnz     short loc_140004E32
0x140004e2c  or      eax, 8
0x140004e2f  mov     [rbx+4], eax
0x140004e32  mov     eax, 1
0x140004e37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004e3f  inc     eax
0x140004e41  xor     edi, edi
0x140004e43  mov     [rbx+10h], eax
0x140004e46  mov     rax, [rsp+78h+arg_40]
0x140004e4e  test    rax, rax
0x140004e51  jz      short loc_140004E58
0x140004e53  cmp     [rax], di
0x140004e56  jnz     short loc_140004E5B
0x140004e58  mov     rax, rdi
0x140004e5b  mov     [rbx+18h], rax
0x140004e5f  call    cs:__imp_GetCurrentThreadId
0x140004e65  mov     [rbx+38h], r13
0x140004e69  xorps   xmm0, xmm0
0x140004e6c  mov     [rbx+20h], eax
0x140004e6f  mov     eax, [rsp+78h+arg_8]
0x140004e76  mov     [rbx+40h], eax
0x140004e79  mov     rax, [rsp+78h+arg_20]
0x140004e81  mov     [rbx+28h], rax
0x140004e85  mov     rax, [rsp+78h+arg_28]
0x140004e8d  mov     [rbx+88h], rax
0x140004e94  mov     rax, [rsp+78h+arg_0]
0x140004e9c  mov     [rbx+90h], rax
0x140004ea3  xor     eax, eax
0x140004ea5  mov     [rbx+44h], ebp
0x140004ea8  mov     [rbx+30h], r12
0x140004eac  mov     [rbx+48h], rdi
0x140004eb0  movups  xmmword ptr [rbx+68h], xmm0
0x140004eb4  mov     [rbx+78h], rax
0x140004eb8  movups  xmmword ptr [rbx+50h], xmm0
0x140004ebc  mov     [rbx+60h], rax
0x140004ec0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004ec7  test    rax, rax
0x140004eca  jz      short loc_140004ED3
0x140004ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ed1  jmp     short loc_140004ED6
0x140004ed3  mov     rax, rdi
0x140004ed6  mov     [rbx+80h], rax
0x140004edd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004ee4  test    rax, rax
0x140004ee7  jz      short loc_140004EF1
0x140004ee9  mov     rcx, rbx
0x140004eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ef1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004ef8  test    rax, rax
0x140004efb  jz      short loc_140004F13
0x140004efd  mov     rdx, [rsp+78h+arg_60]
0x140004f05  mov     r8d, 400h
0x140004f0b  mov     rcx, rbx
0x140004f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004f1a  test    rax, rax
0x140004f1d  jz      short loc_140004F27
0x140004f1f  mov     rcx, rbx
0x140004f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004f2e  test    rax, rax
0x140004f31  jz      short loc_140004F41
0x140004f33  test    byte ptr [rbx+4], 2
0x140004f37  jnz     short loc_140004F41
0x140004f39  mov     rcx, rbx
0x140004f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f41  cmp     [rbx+8], edi
0x140004f44  jl      short loc_140004F60
0x140004f46  cmp     r15d, 3
0x140004f4a  jnz     loc_14000502E
0x140004f50  mov     ecx, 8000FFFFh; this
0x140004f55  mov     [rbx+8], ecx
0x140004f58  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004f5d  mov     [rbx+0Ch], eax
0x140004f60  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004f67  jnz     short loc_140004F88
0x140004f69  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004f70  test    rax, rax
0x140004f73  jz      short loc_140004F7E
0x140004f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f7a  test    al, al
0x140004f7c  jmp     short loc_140004F86
0x140004f7e  call    cs:__imp_IsDebuggerPresent
0x140004f84  test    eax, eax
0x140004f86  jz      short loc_140004F8E
0x140004f88  test    byte ptr [rbx+4], 2
0x140004f8c  jz      short loc_140004FB2
0x140004f8e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f95  test    rax, rax
0x140004f98  jz      short loc_140004FF6
0x140004f9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004fa1  jnz     short loc_140004FF6
0x140004fa3  xor     r8d, r8d
0x140004fa6  xor     edx, edx
0x140004fa8  mov     rcx, rbx
0x140004fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fb0  jmp     short loc_140004FF6
0x140004fb2  mov     rax, cs:g_pfnResultLoggingCallback
0x140004fb9  mov     ebp, 800h
0x140004fbe  test    rax, rax
0x140004fc1  jz      short loc_140004FDA
0x140004fc3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004fca  jnz     short loc_140004FDA
0x140004fcc  mov     r8d, ebp
0x140004fcf  mov     rdx, rsi
0x140004fd2  mov     rcx, rbx
0x140004fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fda  cmp     [rsi], di
0x140004fdd  jnz     short loc_140004FED
0x140004fdf  mov     r8, rbx; unsigned __int64
0x140004fe2  mov     rdx, rbp; wchar_t *
0x140004fe5  mov     rcx, rsi; this
0x140004fe8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140004fed  mov     rcx, rsi; lpOutputString
0x140004ff0  call    cs:__imp_OutputDebugStringW
0x140004ff6  test    byte ptr [rbx+4], 4
0x140004ffa  jnz     short loc_140005005
0x140004ffc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005003  jz      short loc_140005016
0x140005005  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000500c  test    rax, rax
0x14000500f  jz      short loc_140005016
0x140005011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005016  mov     rbx, [rsp+78h+arg_10]
0x14000501e  add     rsp, 40h
0x140005022  pop     r15
0x140005024  pop     r14
0x140005026  pop     r13
0x140005028  pop     r12
0x14000502a  pop     rdi
0x14000502b  pop     rsi
0x14000502c  pop     rbp
0x14000502d  retn
0x14000502e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
