# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004da8`
- end: `0x1800050a1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003564`

## callees

- `0x180002fa8`
- `0x180004444`
- `0x180004be4`
- `0x180004da8`
- `0x1800052ec`
- `0x180005310`
- `0x180005324`
- `0x180005340`
- `0x18000638c`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ecb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004ecb`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004fea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180004fea`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000505c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000505c`

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
0x180004da8  mov     [rsp+arg_10], rbx
0x180004dad  mov     [rsp+arg_8], edx
0x180004db1  mov     [rsp+arg_0], rcx
0x180004db6  push    rbp
0x180004db7  push    rsi
0x180004db8  push    rdi
0x180004db9  push    r12
0x180004dbb  push    r13
0x180004dbd  push    r14
0x180004dbf  push    r15
0x180004dc1  sub     rsp, 40h
0x180004dc5  mov     r12, r9
0x180004dc8  mov     r13, r8
0x180004dcb  mov     r10, rcx
0x180004dce  xor     eax, eax
0x180004dd0  mov     rsi, [rsp+78h+lpOutputString]
0x180004dd8  mov     [rsi], ax
0x180004ddb  mov     rax, [rsp+78h+arg_60]
0x180004de3  mov     byte ptr [rax], 0
0x180004de6  mov     r14, [rsp+78h+arg_38]
0x180004dee  mov     edi, [r14]
0x180004df1  mov     rbx, [rsp+78h+arg_78]
0x180004df9  mov     [rbx+8], edi
0x180004dfc  mov     eax, [r14+4]
0x180004e00  mov     [rbx+0Ch], eax
0x180004e03  xor     ebp, ebp
0x180004e05  mov     r15d, [rsp+78h+arg_30]
0x180004e0d  mov     ecx, r15d
0x180004e10  test    r15d, r15d
0x180004e13  jz      short loc_180004E7B
0x180004e15  sub     ecx, 1
0x180004e18  jz      short loc_180004E72
0x180004e1a  sub     ecx, 1
0x180004e1d  jz      short loc_180004E2D
0x180004e1f  cmp     ecx, 1
0x180004e22  jnz     short loc_180004E84
0x180004e24  mov     ecx, edi; this
0x180004e26  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180004e2b  jmp     short loc_180004E82
0x180004e2d  test    edi, edi
0x180004e2f  js      short loc_180004E69
0x180004e31  mov     edi, 8007029Ch
0x180004e36  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180004e3a  mov     rax, [rsp+78h+arg_28]
0x180004e42  mov     [rsp+78h+var_50], rax; __int64
0x180004e47  mov     rax, [rsp+78h+arg_20]
0x180004e4f  mov     [rsp+78h+var_58], rax; __int64
0x180004e54  mov     rcx, r10; int
0x180004e57  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004e5c  mov     [rbx+8], edi
0x180004e5f  mov     ecx, edi; this
0x180004e61  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004e66  mov     [rbx+0Ch], eax
0x180004e69  mov     ecx, edi; this
0x180004e6b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004e70  jmp     short loc_180004E82
0x180004e72  mov     ecx, edi; this
0x180004e74  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004e79  jmp     short loc_180004E82
0x180004e7b  mov     ecx, edi; this
0x180004e7d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004e82  mov     ebp, eax
0x180004e84  mov     [rbx], r15d
0x180004e87  mov     eax, [rsp+78h+arg_70]
0x180004e8e  mov     [rbx+4], eax
0x180004e91  cmp     dword ptr [r14+8], 1
0x180004e96  jnz     short loc_180004E9E
0x180004e98  or      eax, 8
0x180004e9b  mov     [rbx+4], eax
0x180004e9e  mov     eax, 1
0x180004ea3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004eab  inc     eax
0x180004ead  mov     [rbx+10h], eax
0x180004eb0  mov     rax, [rsp+78h+arg_40]
0x180004eb8  xor     edi, edi
0x180004eba  test    rax, rax
0x180004ebd  jz      short loc_180004EC4
0x180004ebf  cmp     [rax], di
0x180004ec2  jnz     short loc_180004EC7
0x180004ec4  mov     rax, rdi
0x180004ec7  mov     [rbx+18h], rax
0x180004ecb  call    cs:__imp_GetCurrentThreadId
0x180004ed1  mov     [rbx+20h], eax
0x180004ed4  mov     [rbx+38h], r13
0x180004ed8  mov     eax, [rsp+78h+arg_8]
0x180004edf  mov     [rbx+40h], eax
0x180004ee2  mov     [rbx+44h], ebp
0x180004ee5  mov     rax, [rsp+78h+arg_20]
0x180004eed  mov     [rbx+28h], rax
0x180004ef1  mov     [rbx+30h], r12
0x180004ef5  mov     rax, [rsp+78h+arg_28]
0x180004efd  mov     [rbx+88h], rax
0x180004f04  mov     rax, [rsp+78h+arg_0]
0x180004f0c  mov     [rbx+90h], rax
0x180004f13  mov     [rbx+48h], rdi
0x180004f17  xorps   xmm0, xmm0
0x180004f1a  xor     eax, eax
0x180004f1c  movups  xmmword ptr [rbx+68h], xmm0
0x180004f20  mov     [rbx+78h], rax
0x180004f24  movups  xmmword ptr [rbx+50h], xmm0
0x180004f28  mov     [rbx+60h], rax
0x180004f2c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004f33  test    rax, rax
0x180004f36  jz      short loc_180004F3F
0x180004f38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f3d  jmp     short loc_180004F42
0x180004f3f  mov     rax, rdi
0x180004f42  mov     [rbx+80h], rax
0x180004f49  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004f50  test    rax, rax
0x180004f53  jz      short loc_180004F5D
0x180004f55  mov     rcx, rbx
0x180004f58  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f5d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004f64  test    rax, rax
0x180004f67  jz      short loc_180004F7F
0x180004f69  mov     r8d, 400h
0x180004f6f  mov     rdx, [rsp+78h+arg_60]
0x180004f77  mov     rcx, rbx
0x180004f7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f7f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f86  test    rax, rax
0x180004f89  jz      short loc_180004F93
0x180004f8b  mov     rcx, rbx
0x180004f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004f93  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004f9a  test    rax, rax
0x180004f9d  jz      short loc_180004FAD
0x180004f9f  test    byte ptr [rbx+4], 2
0x180004fa3  jnz     short loc_180004FAD
0x180004fa5  mov     rcx, rbx
0x180004fa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fad  cmp     [rbx+8], edi
0x180004fb0  jl      short loc_180004FCC
0x180004fb2  cmp     r15d, 3
0x180004fb6  jnz     loc_18000509B
0x180004fbc  mov     ecx, 8000FFFFh; this
0x180004fc1  mov     [rbx+8], ecx
0x180004fc4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004fc9  mov     [rbx+0Ch], eax
0x180004fcc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004fd3  jnz     short loc_180004FF4
0x180004fd5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004fdc  test    rax, rax
0x180004fdf  jz      short loc_180004FEA
0x180004fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004fe6  test    al, al
0x180004fe8  jmp     short loc_180004FF2
0x180004fea  call    cs:__imp_IsDebuggerPresent
0x180004ff0  test    eax, eax
0x180004ff2  jz      short loc_180004FFA
0x180004ff4  test    byte ptr [rbx+4], 2
0x180004ff8  jz      short loc_18000501E
0x180004ffa  mov     rax, cs:g_pfnResultLoggingCallback
0x180005001  test    rax, rax
0x180005004  jz      short loc_180005062
0x180005006  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000500d  jnz     short loc_180005062
0x18000500f  xor     r8d, r8d
0x180005012  xor     edx, edx
0x180005014  mov     rcx, rbx
0x180005017  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000501c  jmp     short loc_180005062
0x18000501e  mov     ebp, 800h
0x180005023  mov     rax, cs:g_pfnResultLoggingCallback
0x18000502a  test    rax, rax
0x18000502d  jz      short loc_180005046
0x18000502f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005036  jnz     short loc_180005046
0x180005038  mov     r8d, ebp
0x18000503b  mov     rdx, rsi
0x18000503e  mov     rcx, rbx
0x180005041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005046  cmp     [rsi], di
0x180005049  jnz     short loc_180005059
0x18000504b  mov     r8, rbx; unsigned __int64
0x18000504e  mov     rdx, rbp; unsigned __int16 *
0x180005051  mov     rcx, rsi; this
0x180005054  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005059  mov     rcx, rsi; lpOutputString
0x18000505c  call    cs:__imp_OutputDebugStringW
0x180005062  test    byte ptr [rbx+4], 4
0x180005066  jnz     short loc_180005071
0x180005068  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000506f  jz      short loc_180005083
0x180005071  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005078  test    rax, rax
0x18000507b  jz      short loc_180005083
0x18000507d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005082  nop
0x180005083  mov     rbx, [rsp+78h+arg_10]
0x18000508b  add     rsp, 40h
0x18000508f  pop     r15
0x180005091  pop     r14
0x180005093  pop     r13
0x180005095  pop     r12
0x180005097  pop     rdi
0x180005098  pop     rsi
0x180005099  pop     rbp
0x18000509a  retn
0x18000509b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
