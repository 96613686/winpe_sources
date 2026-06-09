# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004ccc`
- end: `0x180004fd8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800031d0`
- `0x180003530`

## callees

- `0x180003110`
- `0x1800042c4`
- `0x180004b08`
- `0x180004ccc`
- `0x180008ec0`
- `0x180008ee0`
- `0x180008ef4`
- `0x180008f14`
- `0x180009df4`
- `0x18024f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004def`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004def`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f8c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004f8c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f14`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004f14`

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
0x180004ccc  mov     [rsp+arg_10], rbx
0x180004cd1  mov     [rsp+arg_8], edx
0x180004cd5  mov     [rsp+arg_0], rcx
0x180004cda  push    rbp
0x180004cdb  push    rsi
0x180004cdc  push    rdi
0x180004cdd  push    r12
0x180004cdf  push    r13
0x180004ce1  push    r14
0x180004ce3  push    r15
0x180004ce5  sub     rsp, 40h
0x180004ce9  mov     r12, r9
0x180004cec  mov     r13, r8
0x180004cef  mov     r10, rcx
0x180004cf2  xor     eax, eax
0x180004cf4  mov     rsi, [rsp+78h+lpOutputString]
0x180004cfc  mov     [rsi], ax
0x180004cff  mov     rax, [rsp+78h+arg_60]
0x180004d07  mov     byte ptr [rax], 0
0x180004d0a  mov     r14, [rsp+78h+arg_38]
0x180004d12  mov     edi, [r14]
0x180004d15  mov     rbx, [rsp+78h+arg_78]
0x180004d1d  mov     [rbx+8], edi
0x180004d20  mov     eax, [r14+4]
0x180004d24  mov     [rbx+0Ch], eax
0x180004d27  xor     ebp, ebp
0x180004d29  mov     r15d, [rsp+78h+arg_30]
0x180004d31  mov     ecx, r15d
0x180004d34  test    r15d, r15d
0x180004d37  jz      short loc_180004D9F
0x180004d39  sub     ecx, 1
0x180004d3c  jz      short loc_180004D96
0x180004d3e  sub     ecx, 1
0x180004d41  jz      short loc_180004D51
0x180004d43  cmp     ecx, 1
0x180004d46  jnz     short loc_180004DA8
0x180004d48  mov     ecx, edi; this
0x180004d4a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004d4f  jmp     short loc_180004DA6
0x180004d51  test    edi, edi
0x180004d53  js      short loc_180004D8D
0x180004d55  mov     edi, 8007029Ch
0x180004d5a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004d5e  mov     rax, [rsp+78h+arg_28]
0x180004d66  mov     [rsp+78h+var_50], rax; __int64
0x180004d6b  mov     rax, [rsp+78h+arg_20]
0x180004d73  mov     [rsp+78h+var_58], rax; __int64
0x180004d78  mov     rcx, r10; int
0x180004d7b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004d80  mov     [rbx+8], edi
0x180004d83  mov     ecx, edi; this
0x180004d85  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004d8a  mov     [rbx+0Ch], eax
0x180004d8d  mov     ecx, edi; this
0x180004d8f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004d94  jmp     short loc_180004DA6
0x180004d96  mov     ecx, edi; this
0x180004d98  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004d9d  jmp     short loc_180004DA6
0x180004d9f  mov     ecx, edi; this
0x180004da1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004da6  mov     ebp, eax
0x180004da8  mov     [rbx], r15d
0x180004dab  mov     eax, [rsp+78h+arg_70]
0x180004db2  mov     [rbx+4], eax
0x180004db5  cmp     dword ptr [r14+8], 1
0x180004dba  jnz     short loc_180004DC2
0x180004dbc  or      eax, 8
0x180004dbf  mov     [rbx+4], eax
0x180004dc2  mov     eax, 1
0x180004dc7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004dcf  inc     eax
0x180004dd1  mov     [rbx+10h], eax
0x180004dd4  mov     rax, [rsp+78h+arg_40]
0x180004ddc  xor     edi, edi
0x180004dde  test    rax, rax
0x180004de1  jz      short loc_180004DE8
0x180004de3  cmp     [rax], di
0x180004de6  jnz     short loc_180004DEB
0x180004de8  mov     rax, rdi
0x180004deb  mov     [rbx+18h], rax
0x180004def  call    cs:__imp_GetCurrentThreadId
0x180004df6  nop     dword ptr [rax+rax+00h]
0x180004dfb  mov     [rbx+20h], eax
0x180004dfe  mov     [rbx+38h], r13
0x180004e02  mov     eax, [rsp+78h+arg_8]
0x180004e09  mov     [rbx+40h], eax
0x180004e0c  mov     [rbx+44h], ebp
0x180004e0f  mov     rax, [rsp+78h+arg_20]
0x180004e17  mov     [rbx+28h], rax
0x180004e1b  mov     [rbx+30h], r12
0x180004e1f  mov     rax, [rsp+78h+arg_28]
0x180004e27  mov     [rbx+88h], rax
0x180004e2e  mov     rax, [rsp+78h+arg_0]
0x180004e36  mov     [rbx+90h], rax
0x180004e3d  mov     [rbx+48h], rdi
0x180004e41  xorps   xmm0, xmm0
0x180004e44  xor     eax, eax
0x180004e46  movups  xmmword ptr [rbx+68h], xmm0
0x180004e4a  mov     [rbx+78h], rax
0x180004e4e  movups  xmmword ptr [rbx+50h], xmm0
0x180004e52  mov     [rbx+60h], rax
0x180004e56  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004e5d  test    rax, rax
0x180004e60  jz      short loc_180004E69
0x180004e62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e67  jmp     short loc_180004E6C
0x180004e69  mov     rax, rdi
0x180004e6c  mov     [rbx+80h], rax
0x180004e73  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004e7a  test    rax, rax
0x180004e7d  jz      short loc_180004E87
0x180004e7f  mov     rcx, rbx
0x180004e82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004e87  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004e8e  test    rax, rax
0x180004e91  jz      short loc_180004EA9
0x180004e93  mov     r8d, 400h
0x180004e99  mov     rdx, [rsp+78h+arg_60]
0x180004ea1  mov     rcx, rbx
0x180004ea4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ea9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004eb0  test    rax, rax
0x180004eb3  jz      short loc_180004EBD
0x180004eb5  mov     rcx, rbx
0x180004eb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ebd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004ec4  test    rax, rax
0x180004ec7  jz      short loc_180004ED7
0x180004ec9  test    byte ptr [rbx+4], 2
0x180004ecd  jnz     short loc_180004ED7
0x180004ecf  mov     rcx, rbx
0x180004ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004ed7  cmp     [rbx+8], edi
0x180004eda  jl      short loc_180004EF6
0x180004edc  cmp     r15d, 3
0x180004ee0  jnz     loc_180004FD2
0x180004ee6  mov     ecx, 8000FFFFh; this
0x180004eeb  mov     [rbx+8], ecx
0x180004eee  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004ef3  mov     [rbx+0Ch], eax
0x180004ef6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004efd  jnz     short loc_180004F24
0x180004eff  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004f06  test    rax, rax
0x180004f09  jz      short loc_180004F14
0x180004f0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f10  test    al, al
0x180004f12  jmp     short loc_180004F22
0x180004f14  call    cs:__imp_IsDebuggerPresent
0x180004f1b  nop     dword ptr [rax+rax+00h]
0x180004f20  test    eax, eax
0x180004f22  jz      short loc_180004F2A
0x180004f24  test    byte ptr [rbx+4], 2
0x180004f28  jz      short loc_180004F4E
0x180004f2a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f31  test    rax, rax
0x180004f34  jz      short loc_180004F98
0x180004f36  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f3d  jnz     short loc_180004F98
0x180004f3f  xor     r8d, r8d
0x180004f42  xor     edx, edx
0x180004f44  mov     rcx, rbx
0x180004f47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f4c  jmp     short loc_180004F98
0x180004f4e  mov     ebp, 800h
0x180004f53  mov     rax, cs:g_pfnResultLoggingCallback
0x180004f5a  test    rax, rax
0x180004f5d  jz      short loc_180004F76
0x180004f5f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004f66  jnz     short loc_180004F76
0x180004f68  mov     r8d, ebp
0x180004f6b  mov     rdx, rsi
0x180004f6e  mov     rcx, rbx
0x180004f71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f76  cmp     [rsi], di
0x180004f79  jnz     short loc_180004F89
0x180004f7b  mov     r8, rbx; unsigned __int64
0x180004f7e  mov     rdx, rbp; unsigned __int16 *
0x180004f81  mov     rcx, rsi; this
0x180004f84  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004f89  mov     rcx, rsi; lpOutputString
0x180004f8c  call    cs:__imp_OutputDebugStringW
0x180004f93  nop     dword ptr [rax+rax+00h]
0x180004f98  test    byte ptr [rbx+4], 4
0x180004f9c  jnz     short loc_180004FA7
0x180004f9e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004fa5  jz      short loc_180004FB9
0x180004fa7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004fae  test    rax, rax
0x180004fb1  jz      short loc_180004FB9
0x180004fb3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fb8  nop
0x180004fb9  mov     rbx, [rsp+78h+arg_10]
0x180004fc1  add     rsp, 40h
0x180004fc5  pop     r15
0x180004fc7  pop     r14
0x180004fc9  pop     r13
0x180004fcb  pop     r12
0x180004fcd  pop     rdi
0x180004fce  pop     rsi
0x180004fcf  pop     rbp
0x180004fd0  retn
0x180004fd2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
