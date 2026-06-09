# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180015c90`
- end: `0x180015f89`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180015ad4`
- `0x18001d3d0`
- `0x18001d73c`

## callees

- `0x180015c90`
- `0x180016230`
- `0x18001d304`
- `0x18001e3d4`
- `0x18001ee40`
- `0x18001ee60`
- `0x18001ee74`
- `0x18001ee90`
- `0x18001fe48`
- `0x1800dc010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015db3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015db3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015ed2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015ed2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015f44`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015f44`

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
0x180015c90  mov     [rsp+arg_10], rbx
0x180015c95  mov     [rsp+arg_8], edx
0x180015c99  mov     [rsp+arg_0], rcx
0x180015c9e  push    rbp
0x180015c9f  push    rsi
0x180015ca0  push    rdi
0x180015ca1  push    r12
0x180015ca3  push    r13
0x180015ca5  push    r14
0x180015ca7  push    r15
0x180015ca9  sub     rsp, 40h
0x180015cad  mov     r12, r9
0x180015cb0  mov     r13, r8
0x180015cb3  mov     r10, rcx
0x180015cb6  xor     eax, eax
0x180015cb8  mov     rsi, [rsp+78h+lpOutputString]
0x180015cc0  mov     [rsi], ax
0x180015cc3  mov     rax, [rsp+78h+arg_60]
0x180015ccb  mov     byte ptr [rax], 0
0x180015cce  mov     r14, [rsp+78h+arg_38]
0x180015cd6  mov     edi, [r14]
0x180015cd9  mov     rbx, [rsp+78h+arg_78]
0x180015ce1  mov     [rbx+8], edi
0x180015ce4  mov     eax, [r14+4]
0x180015ce8  mov     [rbx+0Ch], eax
0x180015ceb  xor     ebp, ebp
0x180015ced  mov     r15d, [rsp+78h+arg_30]
0x180015cf5  mov     ecx, r15d
0x180015cf8  test    r15d, r15d
0x180015cfb  jz      short loc_180015D63
0x180015cfd  sub     ecx, 1
0x180015d00  jz      short loc_180015D5A
0x180015d02  sub     ecx, 1
0x180015d05  jz      short loc_180015D15
0x180015d07  cmp     ecx, 1
0x180015d0a  jnz     short loc_180015D6C
0x180015d0c  mov     ecx, edi; this
0x180015d0e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180015d13  jmp     short loc_180015D6A
0x180015d15  test    edi, edi
0x180015d17  js      short loc_180015D51
0x180015d19  mov     edi, 8007029Ch
0x180015d1e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180015d22  mov     rax, [rsp+78h+arg_28]
0x180015d2a  mov     [rsp+78h+var_50], rax; __int64
0x180015d2f  mov     rax, [rsp+78h+arg_20]
0x180015d37  mov     [rsp+78h+var_58], rax; __int64
0x180015d3c  mov     rcx, r10; int
0x180015d3f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015d44  mov     [rbx+8], edi
0x180015d47  mov     ecx, edi; this
0x180015d49  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015d4e  mov     [rbx+0Ch], eax
0x180015d51  mov     ecx, edi; this
0x180015d53  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180015d58  jmp     short loc_180015D6A
0x180015d5a  mov     ecx, edi; this
0x180015d5c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015d61  jmp     short loc_180015D6A
0x180015d63  mov     ecx, edi; this
0x180015d65  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180015d6a  mov     ebp, eax
0x180015d6c  mov     [rbx], r15d
0x180015d6f  mov     eax, [rsp+78h+arg_70]
0x180015d76  mov     [rbx+4], eax
0x180015d79  cmp     dword ptr [r14+8], 1
0x180015d7e  jnz     short loc_180015D86
0x180015d80  or      eax, 8
0x180015d83  mov     [rbx+4], eax
0x180015d86  mov     eax, 1
0x180015d8b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015d93  inc     eax
0x180015d95  mov     [rbx+10h], eax
0x180015d98  mov     rax, [rsp+78h+arg_40]
0x180015da0  xor     edi, edi
0x180015da2  test    rax, rax
0x180015da5  jz      short loc_180015DAC
0x180015da7  cmp     [rax], di
0x180015daa  jnz     short loc_180015DAF
0x180015dac  mov     rax, rdi
0x180015daf  mov     [rbx+18h], rax
0x180015db3  call    cs:__imp_GetCurrentThreadId
0x180015db9  mov     [rbx+20h], eax
0x180015dbc  mov     [rbx+38h], r13
0x180015dc0  mov     eax, [rsp+78h+arg_8]
0x180015dc7  mov     [rbx+40h], eax
0x180015dca  mov     [rbx+44h], ebp
0x180015dcd  mov     rax, [rsp+78h+arg_20]
0x180015dd5  mov     [rbx+28h], rax
0x180015dd9  mov     [rbx+30h], r12
0x180015ddd  mov     rax, [rsp+78h+arg_28]
0x180015de5  mov     [rbx+88h], rax
0x180015dec  mov     rax, [rsp+78h+arg_0]
0x180015df4  mov     [rbx+90h], rax
0x180015dfb  mov     [rbx+48h], rdi
0x180015dff  xorps   xmm0, xmm0
0x180015e02  xor     eax, eax
0x180015e04  movups  xmmword ptr [rbx+68h], xmm0
0x180015e08  mov     [rbx+78h], rax
0x180015e0c  movups  xmmword ptr [rbx+50h], xmm0
0x180015e10  mov     [rbx+60h], rax
0x180015e14  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015e1b  test    rax, rax
0x180015e1e  jz      short loc_180015E27
0x180015e20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e25  jmp     short loc_180015E2A
0x180015e27  mov     rax, rdi
0x180015e2a  mov     [rbx+80h], rax
0x180015e31  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015e38  test    rax, rax
0x180015e3b  jz      short loc_180015E45
0x180015e3d  mov     rcx, rbx
0x180015e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e45  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015e4c  test    rax, rax
0x180015e4f  jz      short loc_180015E67
0x180015e51  mov     r8d, 400h
0x180015e57  mov     rdx, [rsp+78h+arg_60]
0x180015e5f  mov     rcx, rbx
0x180015e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e67  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015e6e  test    rax, rax
0x180015e71  jz      short loc_180015E7B
0x180015e73  mov     rcx, rbx
0x180015e76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e7b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015e82  test    rax, rax
0x180015e85  jz      short loc_180015E95
0x180015e87  test    byte ptr [rbx+4], 2
0x180015e8b  jnz     short loc_180015E95
0x180015e8d  mov     rcx, rbx
0x180015e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015e95  cmp     [rbx+8], edi
0x180015e98  jl      short loc_180015EB4
0x180015e9a  cmp     r15d, 3
0x180015e9e  jnz     loc_180015F83
0x180015ea4  mov     ecx, 8000FFFFh; this
0x180015ea9  mov     [rbx+8], ecx
0x180015eac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015eb1  mov     [rbx+0Ch], eax
0x180015eb4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180015ebb  jnz     short loc_180015EDC
0x180015ebd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015ec4  test    rax, rax
0x180015ec7  jz      short loc_180015ED2
0x180015ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ece  test    al, al
0x180015ed0  jmp     short loc_180015EDA
0x180015ed2  call    cs:__imp_IsDebuggerPresent
0x180015ed8  test    eax, eax
0x180015eda  jz      short loc_180015EE2
0x180015edc  test    byte ptr [rbx+4], 2
0x180015ee0  jz      short loc_180015F06
0x180015ee2  mov     rax, cs:g_pfnResultLoggingCallback
0x180015ee9  test    rax, rax
0x180015eec  jz      short loc_180015F4A
0x180015eee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015ef5  jnz     short loc_180015F4A
0x180015ef7  xor     r8d, r8d
0x180015efa  xor     edx, edx
0x180015efc  mov     rcx, rbx
0x180015eff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f04  jmp     short loc_180015F4A
0x180015f06  mov     ebp, 800h
0x180015f0b  mov     rax, cs:g_pfnResultLoggingCallback
0x180015f12  test    rax, rax
0x180015f15  jz      short loc_180015F2E
0x180015f17  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015f1e  jnz     short loc_180015F2E
0x180015f20  mov     r8d, ebp
0x180015f23  mov     rdx, rsi
0x180015f26  mov     rcx, rbx
0x180015f29  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f2e  cmp     [rsi], di
0x180015f31  jnz     short loc_180015F41
0x180015f33  mov     r8, rbx; unsigned __int64
0x180015f36  mov     rdx, rbp; unsigned __int16 *
0x180015f39  mov     rcx, rsi; this
0x180015f3c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015f41  mov     rcx, rsi; lpOutputString
0x180015f44  call    cs:__imp_OutputDebugStringW
0x180015f4a  test    byte ptr [rbx+4], 4
0x180015f4e  jnz     short loc_180015F59
0x180015f50  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180015f57  jz      short loc_180015F6B
0x180015f59  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015f60  test    rax, rax
0x180015f63  jz      short loc_180015F6B
0x180015f65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f6a  nop
0x180015f6b  mov     rbx, [rsp+78h+arg_10]
0x180015f73  add     rsp, 40h
0x180015f77  pop     r15
0x180015f79  pop     r14
0x180015f7b  pop     r13
0x180015f7d  pop     r12
0x180015f7f  pop     rdi
0x180015f80  pop     rsi
0x180015f81  pop     rbp
0x180015f82  retn
0x180015f83  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
