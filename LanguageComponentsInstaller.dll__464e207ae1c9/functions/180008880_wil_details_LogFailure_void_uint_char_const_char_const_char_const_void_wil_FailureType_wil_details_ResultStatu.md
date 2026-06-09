# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008880`
- end: `0x180008b79`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800057b4`

## callees

- `0x180004eb0`
- `0x180007d64`
- `0x1800085cc`
- `0x180008880`
- `0x180008efc`
- `0x180008f20`
- `0x180008f34`
- `0x180008f50`
- `0x18000a364`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800089a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008ac2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008ac2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008b34`

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
0x180008880  mov     [rsp+arg_10], rbx
0x180008885  mov     [rsp+arg_8], edx
0x180008889  mov     [rsp+arg_0], rcx
0x18000888e  push    rbp
0x18000888f  push    rsi
0x180008890  push    rdi
0x180008891  push    r12
0x180008893  push    r13
0x180008895  push    r14
0x180008897  push    r15
0x180008899  sub     rsp, 40h
0x18000889d  mov     r12, r9
0x1800088a0  mov     r13, r8
0x1800088a3  mov     r10, rcx
0x1800088a6  xor     eax, eax
0x1800088a8  mov     rsi, [rsp+78h+lpOutputString]
0x1800088b0  mov     [rsi], ax
0x1800088b3  mov     rax, [rsp+78h+arg_60]
0x1800088bb  mov     byte ptr [rax], 0
0x1800088be  mov     r14, [rsp+78h+arg_38]
0x1800088c6  mov     edi, [r14]
0x1800088c9  mov     rbx, [rsp+78h+arg_78]
0x1800088d1  mov     [rbx+8], edi
0x1800088d4  mov     eax, [r14+4]
0x1800088d8  mov     [rbx+0Ch], eax
0x1800088db  xor     ebp, ebp
0x1800088dd  mov     r15d, [rsp+78h+arg_30]
0x1800088e5  mov     ecx, r15d
0x1800088e8  test    r15d, r15d
0x1800088eb  jz      short loc_180008953
0x1800088ed  sub     ecx, 1
0x1800088f0  jz      short loc_18000894A
0x1800088f2  sub     ecx, 1
0x1800088f5  jz      short loc_180008905
0x1800088f7  cmp     ecx, 1
0x1800088fa  jnz     short loc_18000895C
0x1800088fc  mov     ecx, edi; this
0x1800088fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008903  jmp     short loc_18000895A
0x180008905  test    edi, edi
0x180008907  js      short loc_180008941
0x180008909  mov     edi, 8007029Ch
0x18000890e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008912  mov     rax, [rsp+78h+arg_28]
0x18000891a  mov     [rsp+78h+var_50], rax; __int64
0x18000891f  mov     rax, [rsp+78h+arg_20]
0x180008927  mov     [rsp+78h+var_58], rax; __int64
0x18000892c  mov     rcx, r10; int
0x18000892f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008934  mov     [rbx+8], edi
0x180008937  mov     ecx, edi; this
0x180008939  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000893e  mov     [rbx+0Ch], eax
0x180008941  mov     ecx, edi; this
0x180008943  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008948  jmp     short loc_18000895A
0x18000894a  mov     ecx, edi; this
0x18000894c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008951  jmp     short loc_18000895A
0x180008953  mov     ecx, edi; this
0x180008955  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000895a  mov     ebp, eax
0x18000895c  mov     [rbx], r15d
0x18000895f  mov     eax, [rsp+78h+arg_70]
0x180008966  mov     [rbx+4], eax
0x180008969  cmp     dword ptr [r14+8], 1
0x18000896e  jnz     short loc_180008976
0x180008970  or      eax, 8
0x180008973  mov     [rbx+4], eax
0x180008976  mov     eax, 1
0x18000897b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008983  inc     eax
0x180008985  mov     [rbx+10h], eax
0x180008988  mov     rax, [rsp+78h+arg_40]
0x180008990  xor     edi, edi
0x180008992  test    rax, rax
0x180008995  jz      short loc_18000899C
0x180008997  cmp     [rax], di
0x18000899a  jnz     short loc_18000899F
0x18000899c  mov     rax, rdi
0x18000899f  mov     [rbx+18h], rax
0x1800089a3  call    cs:__imp_GetCurrentThreadId
0x1800089a9  mov     [rbx+20h], eax
0x1800089ac  mov     [rbx+38h], r13
0x1800089b0  mov     eax, [rsp+78h+arg_8]
0x1800089b7  mov     [rbx+40h], eax
0x1800089ba  mov     [rbx+44h], ebp
0x1800089bd  mov     rax, [rsp+78h+arg_20]
0x1800089c5  mov     [rbx+28h], rax
0x1800089c9  mov     [rbx+30h], r12
0x1800089cd  mov     rax, [rsp+78h+arg_28]
0x1800089d5  mov     [rbx+88h], rax
0x1800089dc  mov     rax, [rsp+78h+arg_0]
0x1800089e4  mov     [rbx+90h], rax
0x1800089eb  mov     [rbx+48h], rdi
0x1800089ef  xorps   xmm0, xmm0
0x1800089f2  xor     eax, eax
0x1800089f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800089f8  mov     [rbx+78h], rax
0x1800089fc  movups  xmmword ptr [rbx+50h], xmm0
0x180008a00  mov     [rbx+60h], rax
0x180008a04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008a0b  test    rax, rax
0x180008a0e  jz      short loc_180008A17
0x180008a10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a15  jmp     short loc_180008A1A
0x180008a17  mov     rax, rdi
0x180008a1a  mov     [rbx+80h], rax
0x180008a21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008a28  test    rax, rax
0x180008a2b  jz      short loc_180008A35
0x180008a2d  mov     rcx, rbx
0x180008a30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008a3c  test    rax, rax
0x180008a3f  jz      short loc_180008A57
0x180008a41  mov     r8d, 400h
0x180008a47  mov     rdx, [rsp+78h+arg_60]
0x180008a4f  mov     rcx, rbx
0x180008a52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a5e  test    rax, rax
0x180008a61  jz      short loc_180008A6B
0x180008a63  mov     rcx, rbx
0x180008a66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008a72  test    rax, rax
0x180008a75  jz      short loc_180008A85
0x180008a77  test    byte ptr [rbx+4], 2
0x180008a7b  jnz     short loc_180008A85
0x180008a7d  mov     rcx, rbx
0x180008a80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a85  cmp     [rbx+8], edi
0x180008a88  jl      short loc_180008AA4
0x180008a8a  cmp     r15d, 3
0x180008a8e  jnz     loc_180008B73
0x180008a94  mov     ecx, 8000FFFFh; this
0x180008a99  mov     [rbx+8], ecx
0x180008a9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008aa1  mov     [rbx+0Ch], eax
0x180008aa4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008aab  jnz     short loc_180008ACC
0x180008aad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008ab4  test    rax, rax
0x180008ab7  jz      short loc_180008AC2
0x180008ab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008abe  test    al, al
0x180008ac0  jmp     short loc_180008ACA
0x180008ac2  call    cs:__imp_IsDebuggerPresent
0x180008ac8  test    eax, eax
0x180008aca  jz      short loc_180008AD2
0x180008acc  test    byte ptr [rbx+4], 2
0x180008ad0  jz      short loc_180008AF6
0x180008ad2  mov     rax, cs:g_pfnResultLoggingCallback
0x180008ad9  test    rax, rax
0x180008adc  jz      short loc_180008B3A
0x180008ade  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008ae5  jnz     short loc_180008B3A
0x180008ae7  xor     r8d, r8d
0x180008aea  xor     edx, edx
0x180008aec  mov     rcx, rbx
0x180008aef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008af4  jmp     short loc_180008B3A
0x180008af6  mov     ebp, 800h
0x180008afb  mov     rax, cs:g_pfnResultLoggingCallback
0x180008b02  test    rax, rax
0x180008b05  jz      short loc_180008B1E
0x180008b07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008b0e  jnz     short loc_180008B1E
0x180008b10  mov     r8d, ebp
0x180008b13  mov     rdx, rsi
0x180008b16  mov     rcx, rbx
0x180008b19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b1e  cmp     [rsi], di
0x180008b21  jnz     short loc_180008B31
0x180008b23  mov     r8, rbx; unsigned __int64
0x180008b26  mov     rdx, rbp; unsigned __int16 *
0x180008b29  mov     rcx, rsi; this
0x180008b2c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008b31  mov     rcx, rsi; lpOutputString
0x180008b34  call    cs:__imp_OutputDebugStringW
0x180008b3a  test    byte ptr [rbx+4], 4
0x180008b3e  jnz     short loc_180008B49
0x180008b40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008b47  jz      short loc_180008B5B
0x180008b49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008b50  test    rax, rax
0x180008b53  jz      short loc_180008B5B
0x180008b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b5a  nop
0x180008b5b  mov     rbx, [rsp+78h+arg_10]
0x180008b63  add     rsp, 40h
0x180008b67  pop     r15
0x180008b69  pop     r14
0x180008b6b  pop     r13
0x180008b6d  pop     r12
0x180008b6f  pop     rdi
0x180008b70  pop     rsi
0x180008b71  pop     rbp
0x180008b72  retn
0x180008b73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
