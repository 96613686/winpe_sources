# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007bf4`
- end: `0x180007eed`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005534`

## callees

- `0x180004f70`
- `0x180007294`
- `0x180007a30`
- `0x180007bf4`
- `0x1800085fc`
- `0x180008620`
- `0x18000874c`
- `0x180008768`
- `0x18000aafc`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d17`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d17`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007e36`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007e36`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ea8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ea8`

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
0x180007bf4  mov     [rsp+arg_10], rbx
0x180007bf9  mov     [rsp+arg_8], edx
0x180007bfd  mov     [rsp+arg_0], rcx
0x180007c02  push    rbp
0x180007c03  push    rsi
0x180007c04  push    rdi
0x180007c05  push    r12
0x180007c07  push    r13
0x180007c09  push    r14
0x180007c0b  push    r15
0x180007c0d  sub     rsp, 40h
0x180007c11  mov     r12, r9
0x180007c14  mov     r13, r8
0x180007c17  mov     r10, rcx
0x180007c1a  xor     eax, eax
0x180007c1c  mov     rsi, [rsp+78h+lpOutputString]
0x180007c24  mov     [rsi], ax
0x180007c27  mov     rax, [rsp+78h+arg_60]
0x180007c2f  mov     byte ptr [rax], 0
0x180007c32  mov     r14, [rsp+78h+arg_38]
0x180007c3a  mov     edi, [r14]
0x180007c3d  mov     rbx, [rsp+78h+arg_78]
0x180007c45  mov     [rbx+8], edi
0x180007c48  mov     eax, [r14+4]
0x180007c4c  mov     [rbx+0Ch], eax
0x180007c4f  xor     ebp, ebp
0x180007c51  mov     r15d, [rsp+78h+arg_30]
0x180007c59  mov     ecx, r15d
0x180007c5c  test    r15d, r15d
0x180007c5f  jz      short loc_180007CC7
0x180007c61  sub     ecx, 1
0x180007c64  jz      short loc_180007CBE
0x180007c66  sub     ecx, 1
0x180007c69  jz      short loc_180007C79
0x180007c6b  cmp     ecx, 1
0x180007c6e  jnz     short loc_180007CD0
0x180007c70  mov     ecx, edi; this
0x180007c72  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007c77  jmp     short loc_180007CCE
0x180007c79  test    edi, edi
0x180007c7b  js      short loc_180007CB5
0x180007c7d  mov     edi, 8007029Ch
0x180007c82  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007c86  mov     rax, [rsp+78h+arg_28]
0x180007c8e  mov     [rsp+78h+var_50], rax; __int64
0x180007c93  mov     rax, [rsp+78h+arg_20]
0x180007c9b  mov     [rsp+78h+var_58], rax; __int64
0x180007ca0  mov     rcx, r10; int
0x180007ca3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007ca8  mov     [rbx+8], edi
0x180007cab  mov     ecx, edi; this
0x180007cad  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007cb2  mov     [rbx+0Ch], eax
0x180007cb5  mov     ecx, edi; this
0x180007cb7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007cbc  jmp     short loc_180007CCE
0x180007cbe  mov     ecx, edi; this
0x180007cc0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007cc5  jmp     short loc_180007CCE
0x180007cc7  mov     ecx, edi; this
0x180007cc9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007cce  mov     ebp, eax
0x180007cd0  mov     [rbx], r15d
0x180007cd3  mov     eax, [rsp+78h+arg_70]
0x180007cda  mov     [rbx+4], eax
0x180007cdd  cmp     dword ptr [r14+8], 1
0x180007ce2  jnz     short loc_180007CEA
0x180007ce4  or      eax, 8
0x180007ce7  mov     [rbx+4], eax
0x180007cea  mov     eax, 1
0x180007cef  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007cf7  inc     eax
0x180007cf9  mov     [rbx+10h], eax
0x180007cfc  mov     rax, [rsp+78h+arg_40]
0x180007d04  xor     edi, edi
0x180007d06  test    rax, rax
0x180007d09  jz      short loc_180007D10
0x180007d0b  cmp     [rax], di
0x180007d0e  jnz     short loc_180007D13
0x180007d10  mov     rax, rdi
0x180007d13  mov     [rbx+18h], rax
0x180007d17  call    cs:__imp_GetCurrentThreadId
0x180007d1d  mov     [rbx+20h], eax
0x180007d20  mov     [rbx+38h], r13
0x180007d24  mov     eax, [rsp+78h+arg_8]
0x180007d2b  mov     [rbx+40h], eax
0x180007d2e  mov     [rbx+44h], ebp
0x180007d31  mov     rax, [rsp+78h+arg_20]
0x180007d39  mov     [rbx+28h], rax
0x180007d3d  mov     [rbx+30h], r12
0x180007d41  mov     rax, [rsp+78h+arg_28]
0x180007d49  mov     [rbx+88h], rax
0x180007d50  mov     rax, [rsp+78h+arg_0]
0x180007d58  mov     [rbx+90h], rax
0x180007d5f  mov     [rbx+48h], rdi
0x180007d63  xorps   xmm0, xmm0
0x180007d66  xor     eax, eax
0x180007d68  movups  xmmword ptr [rbx+68h], xmm0
0x180007d6c  mov     [rbx+78h], rax
0x180007d70  movups  xmmword ptr [rbx+50h], xmm0
0x180007d74  mov     [rbx+60h], rax
0x180007d78  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007d7f  test    rax, rax
0x180007d82  jz      short loc_180007D8B
0x180007d84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d89  jmp     short loc_180007D8E
0x180007d8b  mov     rax, rdi
0x180007d8e  mov     [rbx+80h], rax
0x180007d95  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007d9c  test    rax, rax
0x180007d9f  jz      short loc_180007DA9
0x180007da1  mov     rcx, rbx
0x180007da4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007db0  test    rax, rax
0x180007db3  jz      short loc_180007DCB
0x180007db5  mov     r8d, 400h
0x180007dbb  mov     rdx, [rsp+78h+arg_60]
0x180007dc3  mov     rcx, rbx
0x180007dc6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dcb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007dd2  test    rax, rax
0x180007dd5  jz      short loc_180007DDF
0x180007dd7  mov     rcx, rbx
0x180007dda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ddf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007de6  test    rax, rax
0x180007de9  jz      short loc_180007DF9
0x180007deb  test    byte ptr [rbx+4], 2
0x180007def  jnz     short loc_180007DF9
0x180007df1  mov     rcx, rbx
0x180007df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007df9  cmp     [rbx+8], edi
0x180007dfc  jl      short loc_180007E18
0x180007dfe  cmp     r15d, 3
0x180007e02  jnz     loc_180007EE7
0x180007e08  mov     ecx, 8000FFFFh; this
0x180007e0d  mov     [rbx+8], ecx
0x180007e10  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007e15  mov     [rbx+0Ch], eax
0x180007e18  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007e1f  jnz     short loc_180007E40
0x180007e21  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007e28  test    rax, rax
0x180007e2b  jz      short loc_180007E36
0x180007e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e32  test    al, al
0x180007e34  jmp     short loc_180007E3E
0x180007e36  call    cs:__imp_IsDebuggerPresent
0x180007e3c  test    eax, eax
0x180007e3e  jz      short loc_180007E46
0x180007e40  test    byte ptr [rbx+4], 2
0x180007e44  jz      short loc_180007E6A
0x180007e46  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e4d  test    rax, rax
0x180007e50  jz      short loc_180007EAE
0x180007e52  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007e59  jnz     short loc_180007EAE
0x180007e5b  xor     r8d, r8d
0x180007e5e  xor     edx, edx
0x180007e60  mov     rcx, rbx
0x180007e63  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e68  jmp     short loc_180007EAE
0x180007e6a  mov     ebp, 800h
0x180007e6f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e76  test    rax, rax
0x180007e79  jz      short loc_180007E92
0x180007e7b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007e82  jnz     short loc_180007E92
0x180007e84  mov     r8d, ebp
0x180007e87  mov     rdx, rsi
0x180007e8a  mov     rcx, rbx
0x180007e8d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e92  cmp     [rsi], di
0x180007e95  jnz     short loc_180007EA5
0x180007e97  mov     r8, rbx; unsigned __int64
0x180007e9a  mov     rdx, rbp; unsigned __int16 *
0x180007e9d  mov     rcx, rsi; this
0x180007ea0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007ea5  mov     rcx, rsi; lpOutputString
0x180007ea8  call    cs:__imp_OutputDebugStringW
0x180007eae  test    byte ptr [rbx+4], 4
0x180007eb2  jnz     short loc_180007EBD
0x180007eb4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007ebb  jz      short loc_180007ECF
0x180007ebd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007ec4  test    rax, rax
0x180007ec7  jz      short loc_180007ECF
0x180007ec9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ece  nop
0x180007ecf  mov     rbx, [rsp+78h+arg_10]
0x180007ed7  add     rsp, 40h
0x180007edb  pop     r15
0x180007edd  pop     r14
0x180007edf  pop     r13
0x180007ee1  pop     r12
0x180007ee3  pop     rdi
0x180007ee4  pop     rsi
0x180007ee5  pop     rbp
0x180007ee6  retn
0x180007ee7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
