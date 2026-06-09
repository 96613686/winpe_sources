# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005d34`
- end: `0x140006035`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400040f0`

## callees

- `0x140003b08`
- `0x140005304`
- `0x140005b70`
- `0x140005d34`
- `0x140006294`
- `0x1400062b0`
- `0x1400062c4`
- `0x1400062e0`
- `0x1400073b0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005e5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140005e5f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005ff0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140005ff0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005f7e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140005f7e`

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
  wil::details *v26; // [rsp+30h] [rbp-58h]

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
0x140005d34  mov     rax, rsp
0x140005d37  mov     [rax+10h], edx
0x140005d3a  mov     [rax+8], rcx
0x140005d3e  push    rbp
0x140005d3f  push    rsi
0x140005d40  push    rdi
0x140005d41  push    r12
0x140005d43  push    r13
0x140005d45  push    r14
0x140005d47  push    r15
0x140005d49  sub     rsp, 50h
0x140005d4d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x140005d55  mov     [rax+18h], rbx
0x140005d59  mov     r12, r9
0x140005d5c  mov     r13, r8
0x140005d5f  mov     r10, rcx
0x140005d62  xor     eax, eax
0x140005d64  mov     rsi, [rsp+88h+lpOutputString]
0x140005d6c  mov     [rsi], ax
0x140005d6f  mov     rax, [rsp+88h+arg_60]
0x140005d77  mov     byte ptr [rax], 0
0x140005d7a  mov     r14, [rsp+88h+arg_38]
0x140005d82  mov     edi, [r14]
0x140005d85  mov     rbx, [rsp+88h+arg_78]
0x140005d8d  mov     [rbx+8], edi
0x140005d90  mov     eax, [r14+4]
0x140005d94  mov     [rbx+0Ch], eax
0x140005d97  xor     ebp, ebp
0x140005d99  mov     r15d, [rsp+88h+arg_30]
0x140005da1  mov     ecx, r15d
0x140005da4  test    r15d, r15d
0x140005da7  jz      short loc_140005E0F
0x140005da9  sub     ecx, 1
0x140005dac  jz      short loc_140005E06
0x140005dae  sub     ecx, 1
0x140005db1  jz      short loc_140005DC1
0x140005db3  cmp     ecx, 1
0x140005db6  jnz     short loc_140005E18
0x140005db8  mov     ecx, edi; this
0x140005dba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005dbf  jmp     short loc_140005E16
0x140005dc1  test    edi, edi
0x140005dc3  js      short loc_140005DFD
0x140005dc5  mov     edi, 8007029Ch
0x140005dca  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x140005dce  mov     rax, [rsp+88h+arg_28]
0x140005dd6  mov     [rsp+88h+var_60], rax; __int64
0x140005ddb  mov     rax, [rsp+88h+arg_20]
0x140005de3  mov     [rsp+88h+var_68], rax; __int64
0x140005de8  mov     rcx, r10; int
0x140005deb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005df0  mov     [rbx+8], edi
0x140005df3  mov     ecx, edi; this
0x140005df5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005dfa  mov     [rbx+0Ch], eax
0x140005dfd  mov     ecx, edi; this
0x140005dff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005e04  jmp     short loc_140005E16
0x140005e06  mov     ecx, edi; this
0x140005e08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005e0d  jmp     short loc_140005E16
0x140005e0f  mov     ecx, edi; this
0x140005e11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005e16  mov     ebp, eax
0x140005e18  mov     [rbx], r15d
0x140005e1b  mov     eax, [rsp+88h+arg_70]
0x140005e22  mov     [rbx+4], eax
0x140005e25  cmp     dword ptr [r14+8], 1
0x140005e2a  jnz     short loc_140005E32
0x140005e2c  or      eax, 8
0x140005e2f  mov     [rbx+4], eax
0x140005e32  mov     eax, 1
0x140005e37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005e3f  inc     eax
0x140005e41  mov     [rbx+10h], eax
0x140005e44  mov     rax, [rsp+88h+arg_40]
0x140005e4c  xor     edi, edi
0x140005e4e  test    rax, rax
0x140005e51  jz      short loc_140005E58
0x140005e53  cmp     [rax], di
0x140005e56  jnz     short loc_140005E5B
0x140005e58  mov     rax, rdi
0x140005e5b  mov     [rbx+18h], rax
0x140005e5f  call    cs:__imp_GetCurrentThreadId
0x140005e65  mov     [rbx+20h], eax
0x140005e68  mov     [rbx+38h], r13
0x140005e6c  mov     eax, [rsp+88h+arg_8]
0x140005e73  mov     [rbx+40h], eax
0x140005e76  mov     [rbx+44h], ebp
0x140005e79  mov     rax, [rsp+88h+arg_20]
0x140005e81  mov     [rbx+28h], rax
0x140005e85  mov     [rbx+30h], r12
0x140005e89  mov     rax, [rsp+88h+arg_28]
0x140005e91  mov     [rbx+88h], rax
0x140005e98  mov     rax, [rsp+88h+arg_0]
0x140005ea0  mov     [rbx+90h], rax
0x140005ea7  mov     [rbx+48h], rdi
0x140005eab  xorps   xmm0, xmm0
0x140005eae  xor     eax, eax
0x140005eb0  movups  xmmword ptr [rbx+68h], xmm0
0x140005eb4  mov     [rbx+78h], rax
0x140005eb8  movups  xmmword ptr [rbx+50h], xmm0
0x140005ebc  mov     [rbx+60h], rax
0x140005ec0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005ec7  test    rax, rax
0x140005eca  jz      short loc_140005ED3
0x140005ecc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ed1  jmp     short loc_140005ED6
0x140005ed3  mov     rax, rdi
0x140005ed6  mov     [rbx+80h], rax
0x140005edd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005ee4  test    rax, rax
0x140005ee7  jz      short loc_140005EF1
0x140005ee9  mov     rcx, rbx
0x140005eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005ef1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005ef8  test    rax, rax
0x140005efb  jz      short loc_140005F13
0x140005efd  mov     r8d, 400h
0x140005f03  mov     rdx, [rsp+88h+arg_60]
0x140005f0b  mov     rcx, rbx
0x140005f0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005f1a  test    rax, rax
0x140005f1d  jz      short loc_140005F27
0x140005f1f  mov     rcx, rbx
0x140005f22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005f2e  test    rax, rax
0x140005f31  jz      short loc_140005F41
0x140005f33  test    byte ptr [rbx+4], 2
0x140005f37  jnz     short loc_140005F41
0x140005f39  mov     rcx, rbx
0x140005f3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f41  cmp     [rbx+8], edi
0x140005f44  jl      short loc_140005F60
0x140005f46  cmp     r15d, 3
0x140005f4a  jnz     loc_14000602F
0x140005f50  mov     ecx, 8000FFFFh; this
0x140005f55  mov     [rbx+8], ecx
0x140005f58  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005f5d  mov     [rbx+0Ch], eax
0x140005f60  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005f67  jnz     short loc_140005F88
0x140005f69  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005f70  test    rax, rax
0x140005f73  jz      short loc_140005F7E
0x140005f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005f7a  test    al, al
0x140005f7c  jmp     short loc_140005F86
0x140005f7e  call    cs:__imp_IsDebuggerPresent
0x140005f84  test    eax, eax
0x140005f86  jz      short loc_140005F8E
0x140005f88  test    byte ptr [rbx+4], 2
0x140005f8c  jz      short loc_140005FB2
0x140005f8e  mov     rax, cs:g_pfnResultLoggingCallback
0x140005f95  test    rax, rax
0x140005f98  jz      short loc_140005FF6
0x140005f9a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005fa1  jnz     short loc_140005FF6
0x140005fa3  xor     r8d, r8d
0x140005fa6  xor     edx, edx
0x140005fa8  mov     rcx, rbx
0x140005fab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fb0  jmp     short loc_140005FF6
0x140005fb2  mov     ebp, 800h
0x140005fb7  mov     rax, cs:g_pfnResultLoggingCallback
0x140005fbe  test    rax, rax
0x140005fc1  jz      short loc_140005FDA
0x140005fc3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005fca  jnz     short loc_140005FDA
0x140005fcc  mov     r8d, ebp
0x140005fcf  mov     rdx, rsi
0x140005fd2  mov     rcx, rbx
0x140005fd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005fda  cmp     [rsi], di
0x140005fdd  jnz     short loc_140005FED
0x140005fdf  mov     r8, rbx; unsigned __int64
0x140005fe2  mov     rdx, rbp; unsigned __int16 *
0x140005fe5  mov     rcx, rsi; this
0x140005fe8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005fed  mov     rcx, rsi; lpOutputString
0x140005ff0  call    cs:__imp_OutputDebugStringW
0x140005ff6  test    byte ptr [rbx+4], 4
0x140005ffa  jnz     short loc_140006005
0x140005ffc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006003  jz      short loc_140006017
0x140006005  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000600c  test    rax, rax
0x14000600f  jz      short loc_140006017
0x140006011  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006016  nop
0x140006017  mov     rbx, [rsp+88h+arg_10]
0x14000601f  add     rsp, 50h
0x140006023  pop     r15
0x140006025  pop     r14
0x140006027  pop     r13
0x140006029  pop     r12
0x14000602b  pop     rdi
0x14000602c  pop     rsi
0x14000602d  pop     rbp
0x14000602e  retn
0x14000602f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
