# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005c3c`
- end: `0x180005f35`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800031f8`

## callees

- `0x180002c34`
- `0x1800051f4`
- `0x180005990`
- `0x180005c3c`
- `0x1800068a8`
- `0x1800068d0`
- `0x1800069fc`
- `0x180006a18`
- `0x180008fcc`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005d5f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ef0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005ef0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005e7e`

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
0x180005c3c  mov     [rsp+arg_10], rbx
0x180005c41  mov     [rsp+arg_8], edx
0x180005c45  mov     [rsp+arg_0], rcx
0x180005c4a  push    rbp
0x180005c4b  push    rsi
0x180005c4c  push    rdi
0x180005c4d  push    r12
0x180005c4f  push    r13
0x180005c51  push    r14
0x180005c53  push    r15
0x180005c55  sub     rsp, 40h
0x180005c59  mov     r12, r9
0x180005c5c  mov     r13, r8
0x180005c5f  mov     r10, rcx
0x180005c62  xor     eax, eax
0x180005c64  mov     rsi, [rsp+78h+lpOutputString]
0x180005c6c  mov     [rsi], ax
0x180005c6f  mov     rax, [rsp+78h+arg_60]
0x180005c77  mov     byte ptr [rax], 0
0x180005c7a  mov     r14, [rsp+78h+arg_38]
0x180005c82  mov     edi, [r14]
0x180005c85  mov     rbx, [rsp+78h+arg_78]
0x180005c8d  mov     [rbx+8], edi
0x180005c90  mov     eax, [r14+4]
0x180005c94  mov     [rbx+0Ch], eax
0x180005c97  xor     ebp, ebp
0x180005c99  mov     r15d, [rsp+78h+arg_30]
0x180005ca1  mov     ecx, r15d
0x180005ca4  test    r15d, r15d
0x180005ca7  jz      short loc_180005D0F
0x180005ca9  sub     ecx, 1
0x180005cac  jz      short loc_180005D06
0x180005cae  sub     ecx, 1
0x180005cb1  jz      short loc_180005CC1
0x180005cb3  cmp     ecx, 1
0x180005cb6  jnz     short loc_180005D18
0x180005cb8  mov     ecx, edi; this
0x180005cba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005cbf  jmp     short loc_180005D16
0x180005cc1  test    edi, edi
0x180005cc3  js      short loc_180005CFD
0x180005cc5  mov     edi, 8007029Ch
0x180005cca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005cce  mov     rax, [rsp+78h+arg_28]
0x180005cd6  mov     [rsp+78h+var_50], rax; __int64
0x180005cdb  mov     rax, [rsp+78h+arg_20]
0x180005ce3  mov     [rsp+78h+var_58], rax; __int64
0x180005ce8  mov     rcx, r10; int
0x180005ceb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005cf0  mov     [rbx+8], edi
0x180005cf3  mov     ecx, edi; this
0x180005cf5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005cfa  mov     [rbx+0Ch], eax
0x180005cfd  mov     ecx, edi; this
0x180005cff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005d04  jmp     short loc_180005D16
0x180005d06  mov     ecx, edi; this
0x180005d08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005d0d  jmp     short loc_180005D16
0x180005d0f  mov     ecx, edi; this
0x180005d11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005d16  mov     ebp, eax
0x180005d18  mov     [rbx], r15d
0x180005d1b  mov     eax, [rsp+78h+arg_70]
0x180005d22  mov     [rbx+4], eax
0x180005d25  cmp     dword ptr [r14+8], 1
0x180005d2a  jnz     short loc_180005D32
0x180005d2c  or      eax, 8
0x180005d2f  mov     [rbx+4], eax
0x180005d32  mov     eax, 1
0x180005d37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005d3f  inc     eax
0x180005d41  mov     [rbx+10h], eax
0x180005d44  mov     rax, [rsp+78h+arg_40]
0x180005d4c  xor     edi, edi
0x180005d4e  test    rax, rax
0x180005d51  jz      short loc_180005D58
0x180005d53  cmp     [rax], di
0x180005d56  jnz     short loc_180005D5B
0x180005d58  mov     rax, rdi
0x180005d5b  mov     [rbx+18h], rax
0x180005d5f  call    cs:__imp_GetCurrentThreadId
0x180005d65  mov     [rbx+20h], eax
0x180005d68  mov     [rbx+38h], r13
0x180005d6c  mov     eax, [rsp+78h+arg_8]
0x180005d73  mov     [rbx+40h], eax
0x180005d76  mov     [rbx+44h], ebp
0x180005d79  mov     rax, [rsp+78h+arg_20]
0x180005d81  mov     [rbx+28h], rax
0x180005d85  mov     [rbx+30h], r12
0x180005d89  mov     rax, [rsp+78h+arg_28]
0x180005d91  mov     [rbx+88h], rax
0x180005d98  mov     rax, [rsp+78h+arg_0]
0x180005da0  mov     [rbx+90h], rax
0x180005da7  mov     [rbx+48h], rdi
0x180005dab  xorps   xmm0, xmm0
0x180005dae  xor     eax, eax
0x180005db0  movups  xmmword ptr [rbx+68h], xmm0
0x180005db4  mov     [rbx+78h], rax
0x180005db8  movups  xmmword ptr [rbx+50h], xmm0
0x180005dbc  mov     [rbx+60h], rax
0x180005dc0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005dc7  test    rax, rax
0x180005dca  jz      short loc_180005DD3
0x180005dcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dd1  jmp     short loc_180005DD6
0x180005dd3  mov     rax, rdi
0x180005dd6  mov     [rbx+80h], rax
0x180005ddd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005de4  test    rax, rax
0x180005de7  jz      short loc_180005DF1
0x180005de9  mov     rcx, rbx
0x180005dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005df1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005df8  test    rax, rax
0x180005dfb  jz      short loc_180005E13
0x180005dfd  mov     r8d, 400h
0x180005e03  mov     rdx, [rsp+78h+arg_60]
0x180005e0b  mov     rcx, rbx
0x180005e0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e1a  test    rax, rax
0x180005e1d  jz      short loc_180005E27
0x180005e1f  mov     rcx, rbx
0x180005e22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e2e  test    rax, rax
0x180005e31  jz      short loc_180005E41
0x180005e33  test    byte ptr [rbx+4], 2
0x180005e37  jnz     short loc_180005E41
0x180005e39  mov     rcx, rbx
0x180005e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e41  cmp     [rbx+8], edi
0x180005e44  jl      short loc_180005E60
0x180005e46  cmp     r15d, 3
0x180005e4a  jnz     loc_180005F2F
0x180005e50  mov     ecx, 8000FFFFh; this
0x180005e55  mov     [rbx+8], ecx
0x180005e58  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e5d  mov     [rbx+0Ch], eax
0x180005e60  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005e67  jnz     short loc_180005E88
0x180005e69  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005e70  test    rax, rax
0x180005e73  jz      short loc_180005E7E
0x180005e75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e7a  test    al, al
0x180005e7c  jmp     short loc_180005E86
0x180005e7e  call    cs:__imp_IsDebuggerPresent
0x180005e84  test    eax, eax
0x180005e86  jz      short loc_180005E8E
0x180005e88  test    byte ptr [rbx+4], 2
0x180005e8c  jz      short loc_180005EB2
0x180005e8e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005e95  test    rax, rax
0x180005e98  jz      short loc_180005EF6
0x180005e9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ea1  jnz     short loc_180005EF6
0x180005ea3  xor     r8d, r8d
0x180005ea6  xor     edx, edx
0x180005ea8  mov     rcx, rbx
0x180005eab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eb0  jmp     short loc_180005EF6
0x180005eb2  mov     ebp, 800h
0x180005eb7  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ebe  test    rax, rax
0x180005ec1  jz      short loc_180005EDA
0x180005ec3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005eca  jnz     short loc_180005EDA
0x180005ecc  mov     r8d, ebp
0x180005ecf  mov     rdx, rsi
0x180005ed2  mov     rcx, rbx
0x180005ed5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005eda  cmp     [rsi], di
0x180005edd  jnz     short loc_180005EED
0x180005edf  mov     r8, rbx; unsigned __int64
0x180005ee2  mov     rdx, rbp; unsigned __int16 *
0x180005ee5  mov     rcx, rsi; this
0x180005ee8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005eed  mov     rcx, rsi; lpOutputString
0x180005ef0  call    cs:__imp_OutputDebugStringW
0x180005ef6  test    byte ptr [rbx+4], 4
0x180005efa  jnz     short loc_180005F05
0x180005efc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005f03  jz      short loc_180005F17
0x180005f05  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005f0c  test    rax, rax
0x180005f0f  jz      short loc_180005F17
0x180005f11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f16  nop
0x180005f17  mov     rbx, [rsp+78h+arg_10]
0x180005f1f  add     rsp, 40h
0x180005f23  pop     r15
0x180005f25  pop     r14
0x180005f27  pop     r13
0x180005f29  pop     r12
0x180005f2b  pop     rdi
0x180005f2c  pop     rsi
0x180005f2d  pop     rbp
0x180005f2e  retn
0x180005f2f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
