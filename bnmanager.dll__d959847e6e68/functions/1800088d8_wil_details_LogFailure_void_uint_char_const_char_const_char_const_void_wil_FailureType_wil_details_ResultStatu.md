# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800088d8`
- end: `0x180008bd1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002f78`

## callees

- `0x1800029b4`
- `0x180007e54`
- `0x1800086c0`
- `0x1800088d8`
- `0x1800093ec`
- `0x180009410`
- `0x18000953c`
- `0x180009558`
- `0x18000bb7c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089fb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089fb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008b1a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008b1a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b8c`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x1800088d8  mov     [rsp+arg_10], rbx
0x1800088dd  mov     [rsp+arg_8], edx
0x1800088e1  mov     [rsp+arg_0], rcx
0x1800088e6  push    rbp
0x1800088e7  push    rsi
0x1800088e8  push    rdi
0x1800088e9  push    r12
0x1800088eb  push    r13
0x1800088ed  push    r14
0x1800088ef  push    r15
0x1800088f1  sub     rsp, 40h
0x1800088f5  mov     r12, r9
0x1800088f8  mov     r13, r8
0x1800088fb  mov     r10, rcx
0x1800088fe  xor     eax, eax
0x180008900  mov     rsi, [rsp+78h+lpOutputString]
0x180008908  mov     [rsi], ax
0x18000890b  mov     rax, [rsp+78h+arg_60]
0x180008913  mov     byte ptr [rax], 0
0x180008916  mov     r14, [rsp+78h+arg_38]
0x18000891e  mov     edi, [r14]
0x180008921  mov     rbx, [rsp+78h+arg_78]
0x180008929  mov     [rbx+8], edi
0x18000892c  mov     eax, [r14+4]
0x180008930  mov     [rbx+0Ch], eax
0x180008933  xor     ebp, ebp
0x180008935  mov     r15d, [rsp+78h+arg_30]
0x18000893d  mov     ecx, r15d
0x180008940  test    r15d, r15d
0x180008943  jz      short loc_1800089AB
0x180008945  sub     ecx, 1
0x180008948  jz      short loc_1800089A2
0x18000894a  sub     ecx, 1
0x18000894d  jz      short loc_18000895D
0x18000894f  cmp     ecx, 1
0x180008952  jnz     short loc_1800089B4
0x180008954  mov     ecx, edi; this
0x180008956  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000895b  jmp     short loc_1800089B2
0x18000895d  test    edi, edi
0x18000895f  js      short loc_180008999
0x180008961  mov     edi, 8007029Ch
0x180008966  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000896a  mov     rax, [rsp+78h+arg_28]
0x180008972  mov     [rsp+78h+var_50], rax; __int64
0x180008977  mov     rax, [rsp+78h+arg_20]
0x18000897f  mov     [rsp+78h+var_58], rax; __int64
0x180008984  mov     rcx, r10; int
0x180008987  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000898c  mov     [rbx+8], edi
0x18000898f  mov     ecx, edi; this
0x180008991  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008996  mov     [rbx+0Ch], eax
0x180008999  mov     ecx, edi; this
0x18000899b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800089a0  jmp     short loc_1800089B2
0x1800089a2  mov     ecx, edi; this
0x1800089a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800089a9  jmp     short loc_1800089B2
0x1800089ab  mov     ecx, edi; this
0x1800089ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800089b2  mov     ebp, eax
0x1800089b4  mov     [rbx], r15d
0x1800089b7  mov     eax, [rsp+78h+arg_70]
0x1800089be  mov     [rbx+4], eax
0x1800089c1  cmp     dword ptr [r14+8], 1
0x1800089c6  jnz     short loc_1800089CE
0x1800089c8  or      eax, 8
0x1800089cb  mov     [rbx+4], eax
0x1800089ce  mov     eax, 1
0x1800089d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800089db  inc     eax
0x1800089dd  mov     [rbx+10h], eax
0x1800089e0  mov     rax, [rsp+78h+arg_40]
0x1800089e8  xor     edi, edi
0x1800089ea  test    rax, rax
0x1800089ed  jz      short loc_1800089F4
0x1800089ef  cmp     [rax], di
0x1800089f2  jnz     short loc_1800089F7
0x1800089f4  mov     rax, rdi
0x1800089f7  mov     [rbx+18h], rax
0x1800089fb  call    cs:__imp_GetCurrentThreadId
0x180008a01  mov     [rbx+20h], eax
0x180008a04  mov     [rbx+38h], r13
0x180008a08  mov     eax, [rsp+78h+arg_8]
0x180008a0f  mov     [rbx+40h], eax
0x180008a12  mov     [rbx+44h], ebp
0x180008a15  mov     rax, [rsp+78h+arg_20]
0x180008a1d  mov     [rbx+28h], rax
0x180008a21  mov     [rbx+30h], r12
0x180008a25  mov     rax, [rsp+78h+arg_28]
0x180008a2d  mov     [rbx+88h], rax
0x180008a34  mov     rax, [rsp+78h+arg_0]
0x180008a3c  mov     [rbx+90h], rax
0x180008a43  mov     [rbx+48h], rdi
0x180008a47  xorps   xmm0, xmm0
0x180008a4a  xor     eax, eax
0x180008a4c  movups  xmmword ptr [rbx+68h], xmm0
0x180008a50  mov     [rbx+78h], rax
0x180008a54  movups  xmmword ptr [rbx+50h], xmm0
0x180008a58  mov     [rbx+60h], rax
0x180008a5c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008a63  test    rax, rax
0x180008a66  jz      short loc_180008A6F
0x180008a68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a6d  jmp     short loc_180008A72
0x180008a6f  mov     rax, rdi
0x180008a72  mov     [rbx+80h], rax
0x180008a79  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008a80  test    rax, rax
0x180008a83  jz      short loc_180008A8D
0x180008a85  mov     rcx, rbx
0x180008a88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a8d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008a94  test    rax, rax
0x180008a97  jz      short loc_180008AAF
0x180008a99  mov     r8d, 400h
0x180008a9f  mov     rdx, [rsp+78h+arg_60]
0x180008aa7  mov     rcx, rbx
0x180008aaa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008aaf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008ab6  test    rax, rax
0x180008ab9  jz      short loc_180008AC3
0x180008abb  mov     rcx, rbx
0x180008abe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008aca  test    rax, rax
0x180008acd  jz      short loc_180008ADD
0x180008acf  test    byte ptr [rbx+4], 2
0x180008ad3  jnz     short loc_180008ADD
0x180008ad5  mov     rcx, rbx
0x180008ad8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008add  cmp     [rbx+8], edi
0x180008ae0  jl      short loc_180008AFC
0x180008ae2  cmp     r15d, 3
0x180008ae6  jnz     loc_180008BCB
0x180008aec  mov     ecx, 8000FFFFh; this
0x180008af1  mov     [rbx+8], ecx
0x180008af4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008af9  mov     [rbx+0Ch], eax
0x180008afc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008b03  jnz     short loc_180008B24
0x180008b05  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008b0c  test    rax, rax
0x180008b0f  jz      short loc_180008B1A
0x180008b11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b16  test    al, al
0x180008b18  jmp     short loc_180008B22
0x180008b1a  call    cs:__imp_IsDebuggerPresent
0x180008b20  test    eax, eax
0x180008b22  jz      short loc_180008B2A
0x180008b24  test    byte ptr [rbx+4], 2
0x180008b28  jz      short loc_180008B4E
0x180008b2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b31  test    rax, rax
0x180008b34  jz      short loc_180008B92
0x180008b36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008b3d  jnz     short loc_180008B92
0x180008b3f  xor     r8d, r8d
0x180008b42  xor     edx, edx
0x180008b44  mov     rcx, rbx
0x180008b47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b4c  jmp     short loc_180008B92
0x180008b4e  mov     ebp, 800h
0x180008b53  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b5a  test    rax, rax
0x180008b5d  jz      short loc_180008B76
0x180008b5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008b66  jnz     short loc_180008B76
0x180008b68  mov     r8d, ebp
0x180008b6b  mov     rdx, rsi
0x180008b6e  mov     rcx, rbx
0x180008b71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b76  cmp     [rsi], di
0x180008b79  jnz     short loc_180008B89
0x180008b7b  mov     r8, rbx; unsigned __int64
0x180008b7e  mov     rdx, rbp; unsigned __int16 *
0x180008b81  mov     rcx, rsi; this
0x180008b84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008b89  mov     rcx, rsi; lpOutputString
0x180008b8c  call    cs:__imp_OutputDebugStringW
0x180008b92  test    byte ptr [rbx+4], 4
0x180008b96  jnz     short loc_180008BA1
0x180008b98  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008b9f  jz      short loc_180008BB3
0x180008ba1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008ba8  test    rax, rax
0x180008bab  jz      short loc_180008BB3
0x180008bad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008bb2  nop
0x180008bb3  mov     rbx, [rsp+78h+arg_10]
0x180008bbb  add     rsp, 40h
0x180008bbf  pop     r15
0x180008bc1  pop     r14
0x180008bc3  pop     r13
0x180008bc5  pop     r12
0x180008bc7  pop     rdi
0x180008bc8  pop     rsi
0x180008bc9  pop     rbp
0x180008bca  retn
0x180008bcb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
