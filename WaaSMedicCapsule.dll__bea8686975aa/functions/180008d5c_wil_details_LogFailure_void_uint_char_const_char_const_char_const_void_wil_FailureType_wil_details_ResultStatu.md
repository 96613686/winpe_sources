# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008d5c`
- end: `0x180009055`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180006e3c`

## callees

- `0x180006848`
- `0x180008254`
- `0x180008b98`
- `0x180008d5c`
- `0x180009750`
- `0x180009770`
- `0x180009784`
- `0x1800097a0`
- `0x18000ab38`
- `0x180064010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008e7f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009010`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009010`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008f9e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008f9e`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x180008d5c  mov     [rsp+arg_10], rbx
0x180008d61  mov     [rsp+arg_8], edx
0x180008d65  mov     [rsp+arg_0], rcx
0x180008d6a  push    rbp
0x180008d6b  push    rsi
0x180008d6c  push    rdi
0x180008d6d  push    r12
0x180008d6f  push    r13
0x180008d71  push    r14
0x180008d73  push    r15
0x180008d75  sub     rsp, 40h
0x180008d79  mov     r12, r9
0x180008d7c  mov     r13, r8
0x180008d7f  mov     r10, rcx
0x180008d82  xor     eax, eax
0x180008d84  mov     rsi, [rsp+78h+lpOutputString]
0x180008d8c  mov     [rsi], ax
0x180008d8f  mov     rax, [rsp+78h+arg_60]
0x180008d97  mov     byte ptr [rax], 0
0x180008d9a  mov     r14, [rsp+78h+arg_38]
0x180008da2  mov     edi, [r14]
0x180008da5  mov     rbx, [rsp+78h+arg_78]
0x180008dad  mov     [rbx+8], edi
0x180008db0  mov     eax, [r14+4]
0x180008db4  mov     [rbx+0Ch], eax
0x180008db7  xor     ebp, ebp
0x180008db9  mov     r15d, [rsp+78h+arg_30]
0x180008dc1  mov     ecx, r15d
0x180008dc4  test    r15d, r15d
0x180008dc7  jz      short loc_180008E2F
0x180008dc9  sub     ecx, 1
0x180008dcc  jz      short loc_180008E26
0x180008dce  sub     ecx, 1
0x180008dd1  jz      short loc_180008DE1
0x180008dd3  cmp     ecx, 1
0x180008dd6  jnz     short loc_180008E38
0x180008dd8  mov     ecx, edi; this
0x180008dda  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008ddf  jmp     short loc_180008E36
0x180008de1  test    edi, edi
0x180008de3  js      short loc_180008E1D
0x180008de5  mov     edi, 8007029Ch
0x180008dea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008dee  mov     rax, [rsp+78h+arg_28]
0x180008df6  mov     [rsp+78h+var_50], rax; __int64
0x180008dfb  mov     rax, [rsp+78h+arg_20]
0x180008e03  mov     [rsp+78h+var_58], rax; __int64
0x180008e08  mov     rcx, r10; int
0x180008e0b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008e10  mov     [rbx+8], edi
0x180008e13  mov     ecx, edi; this
0x180008e15  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008e1a  mov     [rbx+0Ch], eax
0x180008e1d  mov     ecx, edi; this
0x180008e1f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008e24  jmp     short loc_180008E36
0x180008e26  mov     ecx, edi; this
0x180008e28  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008e2d  jmp     short loc_180008E36
0x180008e2f  mov     ecx, edi; this
0x180008e31  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008e36  mov     ebp, eax
0x180008e38  mov     [rbx], r15d
0x180008e3b  mov     eax, [rsp+78h+arg_70]
0x180008e42  mov     [rbx+4], eax
0x180008e45  cmp     dword ptr [r14+8], 1
0x180008e4a  jnz     short loc_180008E52
0x180008e4c  or      eax, 8
0x180008e4f  mov     [rbx+4], eax
0x180008e52  mov     eax, 1
0x180008e57  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008e5f  inc     eax
0x180008e61  mov     [rbx+10h], eax
0x180008e64  mov     rax, [rsp+78h+arg_40]
0x180008e6c  xor     edi, edi
0x180008e6e  test    rax, rax
0x180008e71  jz      short loc_180008E78
0x180008e73  cmp     [rax], di
0x180008e76  jnz     short loc_180008E7B
0x180008e78  mov     rax, rdi
0x180008e7b  mov     [rbx+18h], rax
0x180008e7f  call    cs:__imp_GetCurrentThreadId
0x180008e85  mov     [rbx+20h], eax
0x180008e88  mov     [rbx+38h], r13
0x180008e8c  mov     eax, [rsp+78h+arg_8]
0x180008e93  mov     [rbx+40h], eax
0x180008e96  mov     [rbx+44h], ebp
0x180008e99  mov     rax, [rsp+78h+arg_20]
0x180008ea1  mov     [rbx+28h], rax
0x180008ea5  mov     [rbx+30h], r12
0x180008ea9  mov     rax, [rsp+78h+arg_28]
0x180008eb1  mov     [rbx+88h], rax
0x180008eb8  mov     rax, [rsp+78h+arg_0]
0x180008ec0  mov     [rbx+90h], rax
0x180008ec7  mov     [rbx+48h], rdi
0x180008ecb  xorps   xmm0, xmm0
0x180008ece  xor     eax, eax
0x180008ed0  movups  xmmword ptr [rbx+68h], xmm0
0x180008ed4  mov     [rbx+78h], rax
0x180008ed8  movups  xmmword ptr [rbx+50h], xmm0
0x180008edc  mov     [rbx+60h], rax
0x180008ee0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008ee7  test    rax, rax
0x180008eea  jz      short loc_180008EF3
0x180008eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ef1  jmp     short loc_180008EF6
0x180008ef3  mov     rax, rdi
0x180008ef6  mov     [rbx+80h], rax
0x180008efd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008f04  test    rax, rax
0x180008f07  jz      short loc_180008F11
0x180008f09  mov     rcx, rbx
0x180008f0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f11  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008f18  test    rax, rax
0x180008f1b  jz      short loc_180008F33
0x180008f1d  mov     r8d, 400h
0x180008f23  mov     rdx, [rsp+78h+arg_60]
0x180008f2b  mov     rcx, rbx
0x180008f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f33  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008f3a  test    rax, rax
0x180008f3d  jz      short loc_180008F47
0x180008f3f  mov     rcx, rbx
0x180008f42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f47  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008f4e  test    rax, rax
0x180008f51  jz      short loc_180008F61
0x180008f53  test    byte ptr [rbx+4], 2
0x180008f57  jnz     short loc_180008F61
0x180008f59  mov     rcx, rbx
0x180008f5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f61  cmp     [rbx+8], edi
0x180008f64  jl      short loc_180008F80
0x180008f66  cmp     r15d, 3
0x180008f6a  jnz     loc_18000904F
0x180008f70  mov     ecx, 8000FFFFh; this
0x180008f75  mov     [rbx+8], ecx
0x180008f78  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008f7d  mov     [rbx+0Ch], eax
0x180008f80  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008f87  jnz     short loc_180008FA8
0x180008f89  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008f90  test    rax, rax
0x180008f93  jz      short loc_180008F9E
0x180008f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f9a  test    al, al
0x180008f9c  jmp     short loc_180008FA6
0x180008f9e  call    cs:__imp_IsDebuggerPresent
0x180008fa4  test    eax, eax
0x180008fa6  jz      short loc_180008FAE
0x180008fa8  test    byte ptr [rbx+4], 2
0x180008fac  jz      short loc_180008FD2
0x180008fae  mov     rax, cs:g_pfnResultLoggingCallback
0x180008fb5  test    rax, rax
0x180008fb8  jz      short loc_180009016
0x180008fba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008fc1  jnz     short loc_180009016
0x180008fc3  xor     r8d, r8d
0x180008fc6  xor     edx, edx
0x180008fc8  mov     rcx, rbx
0x180008fcb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fd0  jmp     short loc_180009016
0x180008fd2  mov     ebp, 800h
0x180008fd7  mov     rax, cs:g_pfnResultLoggingCallback
0x180008fde  test    rax, rax
0x180008fe1  jz      short loc_180008FFA
0x180008fe3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008fea  jnz     short loc_180008FFA
0x180008fec  mov     r8d, ebp
0x180008fef  mov     rdx, rsi
0x180008ff2  mov     rcx, rbx
0x180008ff5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ffa  cmp     [rsi], di
0x180008ffd  jnz     short loc_18000900D
0x180008fff  mov     r8, rbx; unsigned __int64
0x180009002  mov     rdx, rbp; unsigned __int16 *
0x180009005  mov     rcx, rsi; this
0x180009008  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000900d  mov     rcx, rsi; lpOutputString
0x180009010  call    cs:__imp_OutputDebugStringW
0x180009016  test    byte ptr [rbx+4], 4
0x18000901a  jnz     short loc_180009025
0x18000901c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009023  jz      short loc_180009037
0x180009025  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000902c  test    rax, rax
0x18000902f  jz      short loc_180009037
0x180009031  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009036  nop
0x180009037  mov     rbx, [rsp+78h+arg_10]
0x18000903f  add     rsp, 40h
0x180009043  pop     r15
0x180009045  pop     r14
0x180009047  pop     r13
0x180009049  pop     r12
0x18000904b  pop     rdi
0x18000904c  pop     rsi
0x18000904d  pop     rbp
0x18000904e  retn
0x18000904f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
