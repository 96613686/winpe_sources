# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005cd0`
- end: `0x180005fc9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800030f4`

## callees

- `0x180002b38`
- `0x180005204`
- `0x1800059a4`
- `0x180005cd0`
- `0x180006648`
- `0x180006670`
- `0x180006684`
- `0x1800066a0`
- `0x180008854`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005df3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005df3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005f84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005f84`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005f12`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005f12`

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
0x180005cd0  mov     [rsp+arg_10], rbx
0x180005cd5  mov     [rsp+arg_8], edx
0x180005cd9  mov     [rsp+arg_0], rcx
0x180005cde  push    rbp
0x180005cdf  push    rsi
0x180005ce0  push    rdi
0x180005ce1  push    r12
0x180005ce3  push    r13
0x180005ce5  push    r14
0x180005ce7  push    r15
0x180005ce9  sub     rsp, 40h
0x180005ced  mov     r12, r9
0x180005cf0  mov     r13, r8
0x180005cf3  mov     r10, rcx
0x180005cf6  xor     eax, eax
0x180005cf8  mov     rsi, [rsp+78h+lpOutputString]
0x180005d00  mov     [rsi], ax
0x180005d03  mov     rax, [rsp+78h+arg_60]
0x180005d0b  mov     byte ptr [rax], 0
0x180005d0e  mov     r14, [rsp+78h+arg_38]
0x180005d16  mov     edi, [r14]
0x180005d19  mov     rbx, [rsp+78h+arg_78]
0x180005d21  mov     [rbx+8], edi
0x180005d24  mov     eax, [r14+4]
0x180005d28  mov     [rbx+0Ch], eax
0x180005d2b  xor     ebp, ebp
0x180005d2d  mov     r15d, [rsp+78h+arg_30]
0x180005d35  mov     ecx, r15d
0x180005d38  test    r15d, r15d
0x180005d3b  jz      short loc_180005DA3
0x180005d3d  sub     ecx, 1
0x180005d40  jz      short loc_180005D9A
0x180005d42  sub     ecx, 1
0x180005d45  jz      short loc_180005D55
0x180005d47  cmp     ecx, 1
0x180005d4a  jnz     short loc_180005DAC
0x180005d4c  mov     ecx, edi; this
0x180005d4e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005d53  jmp     short loc_180005DAA
0x180005d55  test    edi, edi
0x180005d57  js      short loc_180005D91
0x180005d59  mov     edi, 8007029Ch
0x180005d5e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005d62  mov     rax, [rsp+78h+arg_28]
0x180005d6a  mov     [rsp+78h+var_50], rax; __int64
0x180005d6f  mov     rax, [rsp+78h+arg_20]
0x180005d77  mov     [rsp+78h+var_58], rax; __int64
0x180005d7c  mov     rcx, r10; int
0x180005d7f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005d84  mov     [rbx+8], edi
0x180005d87  mov     ecx, edi; this
0x180005d89  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005d8e  mov     [rbx+0Ch], eax
0x180005d91  mov     ecx, edi; this
0x180005d93  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005d98  jmp     short loc_180005DAA
0x180005d9a  mov     ecx, edi; this
0x180005d9c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005da1  jmp     short loc_180005DAA
0x180005da3  mov     ecx, edi; this
0x180005da5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005daa  mov     ebp, eax
0x180005dac  mov     [rbx], r15d
0x180005daf  mov     eax, [rsp+78h+arg_70]
0x180005db6  mov     [rbx+4], eax
0x180005db9  cmp     dword ptr [r14+8], 1
0x180005dbe  jnz     short loc_180005DC6
0x180005dc0  or      eax, 8
0x180005dc3  mov     [rbx+4], eax
0x180005dc6  mov     eax, 1
0x180005dcb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005dd3  inc     eax
0x180005dd5  mov     [rbx+10h], eax
0x180005dd8  mov     rax, [rsp+78h+arg_40]
0x180005de0  xor     edi, edi
0x180005de2  test    rax, rax
0x180005de5  jz      short loc_180005DEC
0x180005de7  cmp     [rax], di
0x180005dea  jnz     short loc_180005DEF
0x180005dec  mov     rax, rdi
0x180005def  mov     [rbx+18h], rax
0x180005df3  call    cs:__imp_GetCurrentThreadId
0x180005df9  mov     [rbx+20h], eax
0x180005dfc  mov     [rbx+38h], r13
0x180005e00  mov     eax, [rsp+78h+arg_8]
0x180005e07  mov     [rbx+40h], eax
0x180005e0a  mov     [rbx+44h], ebp
0x180005e0d  mov     rax, [rsp+78h+arg_20]
0x180005e15  mov     [rbx+28h], rax
0x180005e19  mov     [rbx+30h], r12
0x180005e1d  mov     rax, [rsp+78h+arg_28]
0x180005e25  mov     [rbx+88h], rax
0x180005e2c  mov     rax, [rsp+78h+arg_0]
0x180005e34  mov     [rbx+90h], rax
0x180005e3b  mov     [rbx+48h], rdi
0x180005e3f  xorps   xmm0, xmm0
0x180005e42  xor     eax, eax
0x180005e44  movups  xmmword ptr [rbx+68h], xmm0
0x180005e48  mov     [rbx+78h], rax
0x180005e4c  movups  xmmword ptr [rbx+50h], xmm0
0x180005e50  mov     [rbx+60h], rax
0x180005e54  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005e5b  test    rax, rax
0x180005e5e  jz      short loc_180005E67
0x180005e60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e65  jmp     short loc_180005E6A
0x180005e67  mov     rax, rdi
0x180005e6a  mov     [rbx+80h], rax
0x180005e71  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005e78  test    rax, rax
0x180005e7b  jz      short loc_180005E85
0x180005e7d  mov     rcx, rbx
0x180005e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e85  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005e8c  test    rax, rax
0x180005e8f  jz      short loc_180005EA7
0x180005e91  mov     r8d, 400h
0x180005e97  mov     rdx, [rsp+78h+arg_60]
0x180005e9f  mov     rcx, rbx
0x180005ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005eae  test    rax, rax
0x180005eb1  jz      short loc_180005EBB
0x180005eb3  mov     rcx, rbx
0x180005eb6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ebb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005ec2  test    rax, rax
0x180005ec5  jz      short loc_180005ED5
0x180005ec7  test    byte ptr [rbx+4], 2
0x180005ecb  jnz     short loc_180005ED5
0x180005ecd  mov     rcx, rbx
0x180005ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ed5  cmp     [rbx+8], edi
0x180005ed8  jl      short loc_180005EF4
0x180005eda  cmp     r15d, 3
0x180005ede  jnz     loc_180005FC3
0x180005ee4  mov     ecx, 8000FFFFh; this
0x180005ee9  mov     [rbx+8], ecx
0x180005eec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005ef1  mov     [rbx+0Ch], eax
0x180005ef4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005efb  jnz     short loc_180005F1C
0x180005efd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005f04  test    rax, rax
0x180005f07  jz      short loc_180005F12
0x180005f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0e  test    al, al
0x180005f10  jmp     short loc_180005F1A
0x180005f12  call    cs:__imp_IsDebuggerPresent
0x180005f18  test    eax, eax
0x180005f1a  jz      short loc_180005F22
0x180005f1c  test    byte ptr [rbx+4], 2
0x180005f20  jz      short loc_180005F46
0x180005f22  mov     rax, cs:g_pfnResultLoggingCallback
0x180005f29  test    rax, rax
0x180005f2c  jz      short loc_180005F8A
0x180005f2e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005f35  jnz     short loc_180005F8A
0x180005f37  xor     r8d, r8d
0x180005f3a  xor     edx, edx
0x180005f3c  mov     rcx, rbx
0x180005f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f44  jmp     short loc_180005F8A
0x180005f46  mov     ebp, 800h
0x180005f4b  mov     rax, cs:g_pfnResultLoggingCallback
0x180005f52  test    rax, rax
0x180005f55  jz      short loc_180005F6E
0x180005f57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005f5e  jnz     short loc_180005F6E
0x180005f60  mov     r8d, ebp
0x180005f63  mov     rdx, rsi
0x180005f66  mov     rcx, rbx
0x180005f69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f6e  cmp     [rsi], di
0x180005f71  jnz     short loc_180005F81
0x180005f73  mov     r8, rbx; unsigned __int64
0x180005f76  mov     rdx, rbp; unsigned __int16 *
0x180005f79  mov     rcx, rsi; this
0x180005f7c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005f81  mov     rcx, rsi; lpOutputString
0x180005f84  call    cs:__imp_OutputDebugStringW
0x180005f8a  test    byte ptr [rbx+4], 4
0x180005f8e  jnz     short loc_180005F99
0x180005f90  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005f97  jz      short loc_180005FAB
0x180005f99  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005fa0  test    rax, rax
0x180005fa3  jz      short loc_180005FAB
0x180005fa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005faa  nop
0x180005fab  mov     rbx, [rsp+78h+arg_10]
0x180005fb3  add     rsp, 40h
0x180005fb7  pop     r15
0x180005fb9  pop     r14
0x180005fbb  pop     r13
0x180005fbd  pop     r12
0x180005fbf  pop     rdi
0x180005fc0  pop     rsi
0x180005fc1  pop     rbp
0x180005fc2  retn
0x180005fc3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
