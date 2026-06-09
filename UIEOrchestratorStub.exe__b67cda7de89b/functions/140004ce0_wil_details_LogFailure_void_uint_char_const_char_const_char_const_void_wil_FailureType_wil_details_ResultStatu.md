# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004ce0`
- end: `0x140004fd9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000349c`

## callees

- `0x140002ee0`
- `0x140004374`
- `0x140004b1c`
- `0x140004ce0`
- `0x14000521c`
- `0x140005240`
- `0x140005254`
- `0x140005270`
- `0x14000629c`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e03`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004e03`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f22`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004f22`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f94`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f94`

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
0x140004ce0  mov     [rsp+arg_10], rbx
0x140004ce5  mov     [rsp+arg_8], edx
0x140004ce9  mov     [rsp+arg_0], rcx
0x140004cee  push    rbp
0x140004cef  push    rsi
0x140004cf0  push    rdi
0x140004cf1  push    r12
0x140004cf3  push    r13
0x140004cf5  push    r14
0x140004cf7  push    r15
0x140004cf9  sub     rsp, 40h
0x140004cfd  mov     r12, r9
0x140004d00  mov     r13, r8
0x140004d03  mov     r10, rcx
0x140004d06  xor     eax, eax
0x140004d08  mov     rsi, [rsp+78h+lpOutputString]
0x140004d10  mov     [rsi], ax
0x140004d13  mov     rax, [rsp+78h+arg_60]
0x140004d1b  mov     byte ptr [rax], 0
0x140004d1e  mov     r14, [rsp+78h+arg_38]
0x140004d26  mov     edi, [r14]
0x140004d29  mov     rbx, [rsp+78h+arg_78]
0x140004d31  mov     [rbx+8], edi
0x140004d34  mov     eax, [r14+4]
0x140004d38  mov     [rbx+0Ch], eax
0x140004d3b  xor     ebp, ebp
0x140004d3d  mov     r15d, [rsp+78h+arg_30]
0x140004d45  mov     ecx, r15d
0x140004d48  test    r15d, r15d
0x140004d4b  jz      short loc_140004DB3
0x140004d4d  sub     ecx, 1
0x140004d50  jz      short loc_140004DAA
0x140004d52  sub     ecx, 1
0x140004d55  jz      short loc_140004D65
0x140004d57  cmp     ecx, 1
0x140004d5a  jnz     short loc_140004DBC
0x140004d5c  mov     ecx, edi; this
0x140004d5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004d63  jmp     short loc_140004DBA
0x140004d65  test    edi, edi
0x140004d67  js      short loc_140004DA1
0x140004d69  mov     edi, 8007029Ch
0x140004d6e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004d72  mov     rax, [rsp+78h+arg_28]
0x140004d7a  mov     [rsp+78h+var_50], rax; __int64
0x140004d7f  mov     rax, [rsp+78h+arg_20]
0x140004d87  mov     [rsp+78h+var_58], rax; __int64
0x140004d8c  mov     rcx, r10; int
0x140004d8f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004d94  mov     [rbx+8], edi
0x140004d97  mov     ecx, edi; this
0x140004d99  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004d9e  mov     [rbx+0Ch], eax
0x140004da1  mov     ecx, edi; this
0x140004da3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004da8  jmp     short loc_140004DBA
0x140004daa  mov     ecx, edi; this
0x140004dac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004db1  jmp     short loc_140004DBA
0x140004db3  mov     ecx, edi; this
0x140004db5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004dba  mov     ebp, eax
0x140004dbc  mov     [rbx], r15d
0x140004dbf  mov     eax, [rsp+78h+arg_70]
0x140004dc6  mov     [rbx+4], eax
0x140004dc9  cmp     dword ptr [r14+8], 1
0x140004dce  jnz     short loc_140004DD6
0x140004dd0  or      eax, 8
0x140004dd3  mov     [rbx+4], eax
0x140004dd6  mov     eax, 1
0x140004ddb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004de3  inc     eax
0x140004de5  mov     [rbx+10h], eax
0x140004de8  mov     rax, [rsp+78h+arg_40]
0x140004df0  xor     edi, edi
0x140004df2  test    rax, rax
0x140004df5  jz      short loc_140004DFC
0x140004df7  cmp     [rax], di
0x140004dfa  jnz     short loc_140004DFF
0x140004dfc  mov     rax, rdi
0x140004dff  mov     [rbx+18h], rax
0x140004e03  call    cs:__imp_GetCurrentThreadId
0x140004e09  mov     [rbx+20h], eax
0x140004e0c  mov     [rbx+38h], r13
0x140004e10  mov     eax, [rsp+78h+arg_8]
0x140004e17  mov     [rbx+40h], eax
0x140004e1a  mov     [rbx+44h], ebp
0x140004e1d  mov     rax, [rsp+78h+arg_20]
0x140004e25  mov     [rbx+28h], rax
0x140004e29  mov     [rbx+30h], r12
0x140004e2d  mov     rax, [rsp+78h+arg_28]
0x140004e35  mov     [rbx+88h], rax
0x140004e3c  mov     rax, [rsp+78h+arg_0]
0x140004e44  mov     [rbx+90h], rax
0x140004e4b  mov     [rbx+48h], rdi
0x140004e4f  xorps   xmm0, xmm0
0x140004e52  xor     eax, eax
0x140004e54  movups  xmmword ptr [rbx+68h], xmm0
0x140004e58  mov     [rbx+78h], rax
0x140004e5c  movups  xmmword ptr [rbx+50h], xmm0
0x140004e60  mov     [rbx+60h], rax
0x140004e64  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004e6b  test    rax, rax
0x140004e6e  jz      short loc_140004E77
0x140004e70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e75  jmp     short loc_140004E7A
0x140004e77  mov     rax, rdi
0x140004e7a  mov     [rbx+80h], rax
0x140004e81  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004e88  test    rax, rax
0x140004e8b  jz      short loc_140004E95
0x140004e8d  mov     rcx, rbx
0x140004e90  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e95  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004e9c  test    rax, rax
0x140004e9f  jz      short loc_140004EB7
0x140004ea1  mov     r8d, 400h
0x140004ea7  mov     rdx, [rsp+78h+arg_60]
0x140004eaf  mov     rcx, rbx
0x140004eb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004eb7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004ebe  test    rax, rax
0x140004ec1  jz      short loc_140004ECB
0x140004ec3  mov     rcx, rbx
0x140004ec6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ecb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004ed2  test    rax, rax
0x140004ed5  jz      short loc_140004EE5
0x140004ed7  test    byte ptr [rbx+4], 2
0x140004edb  jnz     short loc_140004EE5
0x140004edd  mov     rcx, rbx
0x140004ee0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ee5  cmp     [rbx+8], edi
0x140004ee8  jl      short loc_140004F04
0x140004eea  cmp     r15d, 3
0x140004eee  jnz     loc_140004FD3
0x140004ef4  mov     ecx, 8000FFFFh; this
0x140004ef9  mov     [rbx+8], ecx
0x140004efc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004f01  mov     [rbx+0Ch], eax
0x140004f04  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004f0b  jnz     short loc_140004F2C
0x140004f0d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004f14  test    rax, rax
0x140004f17  jz      short loc_140004F22
0x140004f19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f1e  test    al, al
0x140004f20  jmp     short loc_140004F2A
0x140004f22  call    cs:__imp_IsDebuggerPresent
0x140004f28  test    eax, eax
0x140004f2a  jz      short loc_140004F32
0x140004f2c  test    byte ptr [rbx+4], 2
0x140004f30  jz      short loc_140004F56
0x140004f32  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f39  test    rax, rax
0x140004f3c  jz      short loc_140004F9A
0x140004f3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004f45  jnz     short loc_140004F9A
0x140004f47  xor     r8d, r8d
0x140004f4a  xor     edx, edx
0x140004f4c  mov     rcx, rbx
0x140004f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f54  jmp     short loc_140004F9A
0x140004f56  mov     ebp, 800h
0x140004f5b  mov     rax, cs:g_pfnResultLoggingCallback
0x140004f62  test    rax, rax
0x140004f65  jz      short loc_140004F7E
0x140004f67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004f6e  jnz     short loc_140004F7E
0x140004f70  mov     r8d, ebp
0x140004f73  mov     rdx, rsi
0x140004f76  mov     rcx, rbx
0x140004f79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f7e  cmp     [rsi], di
0x140004f81  jnz     short loc_140004F91
0x140004f83  mov     r8, rbx; unsigned __int64
0x140004f86  mov     rdx, rbp; unsigned __int16 *
0x140004f89  mov     rcx, rsi; this
0x140004f8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004f91  mov     rcx, rsi; lpOutputString
0x140004f94  call    cs:__imp_OutputDebugStringW
0x140004f9a  test    byte ptr [rbx+4], 4
0x140004f9e  jnz     short loc_140004FA9
0x140004fa0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004fa7  jz      short loc_140004FBB
0x140004fa9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004fb0  test    rax, rax
0x140004fb3  jz      short loc_140004FBB
0x140004fb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004fba  nop
0x140004fbb  mov     rbx, [rsp+78h+arg_10]
0x140004fc3  add     rsp, 40h
0x140004fc7  pop     r15
0x140004fc9  pop     r14
0x140004fcb  pop     r13
0x140004fcd  pop     r12
0x140004fcf  pop     rdi
0x140004fd0  pop     rsi
0x140004fd1  pop     rbp
0x140004fd2  retn
0x140004fd3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
