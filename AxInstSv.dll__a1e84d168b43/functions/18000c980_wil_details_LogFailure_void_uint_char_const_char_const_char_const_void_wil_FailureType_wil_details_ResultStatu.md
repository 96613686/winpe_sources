# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c980`
- end: `0x18000cc79`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180007984`
- `0x180007cd0`

## callees

- `0x1800078c4`
- `0x18000b174`
- `0x18000bd84`
- `0x18000c980`
- `0x18000db78`
- `0x18000dba0`
- `0x18000dd24`
- `0x18000dd40`
- `0x180010e28`
- `0x180015010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caa3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000caa3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cbc2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000cbc2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cc34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000cc34`

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
0x18000c980  mov     [rsp+arg_10], rbx
0x18000c985  mov     [rsp+arg_8], edx
0x18000c989  mov     [rsp+arg_0], rcx
0x18000c98e  push    rbp
0x18000c98f  push    rsi
0x18000c990  push    rdi
0x18000c991  push    r12
0x18000c993  push    r13
0x18000c995  push    r14
0x18000c997  push    r15
0x18000c999  sub     rsp, 40h
0x18000c99d  mov     r12, r9
0x18000c9a0  mov     r13, r8
0x18000c9a3  mov     r10, rcx
0x18000c9a6  xor     eax, eax
0x18000c9a8  mov     rsi, [rsp+78h+lpOutputString]
0x18000c9b0  mov     [rsi], ax
0x18000c9b3  mov     rax, [rsp+78h+arg_60]
0x18000c9bb  mov     byte ptr [rax], 0
0x18000c9be  mov     r14, [rsp+78h+arg_38]
0x18000c9c6  mov     edi, [r14]
0x18000c9c9  mov     rbx, [rsp+78h+arg_78]
0x18000c9d1  mov     [rbx+8], edi
0x18000c9d4  mov     eax, [r14+4]
0x18000c9d8  mov     [rbx+0Ch], eax
0x18000c9db  xor     ebp, ebp
0x18000c9dd  mov     r15d, [rsp+78h+arg_30]
0x18000c9e5  mov     ecx, r15d
0x18000c9e8  test    r15d, r15d
0x18000c9eb  jz      short loc_18000CA53
0x18000c9ed  sub     ecx, 1
0x18000c9f0  jz      short loc_18000CA4A
0x18000c9f2  sub     ecx, 1
0x18000c9f5  jz      short loc_18000CA05
0x18000c9f7  cmp     ecx, 1
0x18000c9fa  jnz     short loc_18000CA5C
0x18000c9fc  mov     ecx, edi; this
0x18000c9fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ca03  jmp     short loc_18000CA5A
0x18000ca05  test    edi, edi
0x18000ca07  js      short loc_18000CA41
0x18000ca09  mov     edi, 8007029Ch
0x18000ca0e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ca12  mov     rax, [rsp+78h+arg_28]
0x18000ca1a  mov     [rsp+78h+var_50], rax; __int64
0x18000ca1f  mov     rax, [rsp+78h+arg_20]
0x18000ca27  mov     [rsp+78h+var_58], rax; __int64
0x18000ca2c  mov     rcx, r10; int
0x18000ca2f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000ca34  mov     [rbx+8], edi
0x18000ca37  mov     ecx, edi; this
0x18000ca39  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000ca3e  mov     [rbx+0Ch], eax
0x18000ca41  mov     ecx, edi; this
0x18000ca43  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ca48  jmp     short loc_18000CA5A
0x18000ca4a  mov     ecx, edi; this
0x18000ca4c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ca51  jmp     short loc_18000CA5A
0x18000ca53  mov     ecx, edi; this
0x18000ca55  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ca5a  mov     ebp, eax
0x18000ca5c  mov     [rbx], r15d
0x18000ca5f  mov     eax, [rsp+78h+arg_70]
0x18000ca66  mov     [rbx+4], eax
0x18000ca69  cmp     dword ptr [r14+8], 1
0x18000ca6e  jnz     short loc_18000CA76
0x18000ca70  or      eax, 8
0x18000ca73  mov     [rbx+4], eax
0x18000ca76  mov     eax, 1
0x18000ca7b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ca83  inc     eax
0x18000ca85  mov     [rbx+10h], eax
0x18000ca88  mov     rax, [rsp+78h+arg_40]
0x18000ca90  xor     edi, edi
0x18000ca92  test    rax, rax
0x18000ca95  jz      short loc_18000CA9C
0x18000ca97  cmp     [rax], di
0x18000ca9a  jnz     short loc_18000CA9F
0x18000ca9c  mov     rax, rdi
0x18000ca9f  mov     [rbx+18h], rax
0x18000caa3  call    cs:__imp_GetCurrentThreadId
0x18000caa9  mov     [rbx+20h], eax
0x18000caac  mov     [rbx+38h], r13
0x18000cab0  mov     eax, [rsp+78h+arg_8]
0x18000cab7  mov     [rbx+40h], eax
0x18000caba  mov     [rbx+44h], ebp
0x18000cabd  mov     rax, [rsp+78h+arg_20]
0x18000cac5  mov     [rbx+28h], rax
0x18000cac9  mov     [rbx+30h], r12
0x18000cacd  mov     rax, [rsp+78h+arg_28]
0x18000cad5  mov     [rbx+88h], rax
0x18000cadc  mov     rax, [rsp+78h+arg_0]
0x18000cae4  mov     [rbx+90h], rax
0x18000caeb  mov     [rbx+48h], rdi
0x18000caef  xorps   xmm0, xmm0
0x18000caf2  xor     eax, eax
0x18000caf4  movups  xmmword ptr [rbx+68h], xmm0
0x18000caf8  mov     [rbx+78h], rax
0x18000cafc  movups  xmmword ptr [rbx+50h], xmm0
0x18000cb00  mov     [rbx+60h], rax
0x18000cb04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000cb0b  test    rax, rax
0x18000cb0e  jz      short loc_18000CB17
0x18000cb10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb15  jmp     short loc_18000CB1A
0x18000cb17  mov     rax, rdi
0x18000cb1a  mov     [rbx+80h], rax
0x18000cb21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000cb28  test    rax, rax
0x18000cb2b  jz      short loc_18000CB35
0x18000cb2d  mov     rcx, rbx
0x18000cb30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000cb3c  test    rax, rax
0x18000cb3f  jz      short loc_18000CB57
0x18000cb41  mov     r8d, 400h
0x18000cb47  mov     rdx, [rsp+78h+arg_60]
0x18000cb4f  mov     rcx, rbx
0x18000cb52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cb5e  test    rax, rax
0x18000cb61  jz      short loc_18000CB6B
0x18000cb63  mov     rcx, rbx
0x18000cb66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000cb72  test    rax, rax
0x18000cb75  jz      short loc_18000CB85
0x18000cb77  test    byte ptr [rbx+4], 2
0x18000cb7b  jnz     short loc_18000CB85
0x18000cb7d  mov     rcx, rbx
0x18000cb80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cb85  cmp     [rbx+8], edi
0x18000cb88  jl      short loc_18000CBA4
0x18000cb8a  cmp     r15d, 3
0x18000cb8e  jnz     loc_18000CC73
0x18000cb94  mov     ecx, 8000FFFFh; this
0x18000cb99  mov     [rbx+8], ecx
0x18000cb9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000cba1  mov     [rbx+0Ch], eax
0x18000cba4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000cbab  jnz     short loc_18000CBCC
0x18000cbad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000cbb4  test    rax, rax
0x18000cbb7  jz      short loc_18000CBC2
0x18000cbb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbbe  test    al, al
0x18000cbc0  jmp     short loc_18000CBCA
0x18000cbc2  call    cs:__imp_IsDebuggerPresent
0x18000cbc8  test    eax, eax
0x18000cbca  jz      short loc_18000CBD2
0x18000cbcc  test    byte ptr [rbx+4], 2
0x18000cbd0  jz      short loc_18000CBF6
0x18000cbd2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cbd9  test    rax, rax
0x18000cbdc  jz      short loc_18000CC3A
0x18000cbde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cbe5  jnz     short loc_18000CC3A
0x18000cbe7  xor     r8d, r8d
0x18000cbea  xor     edx, edx
0x18000cbec  mov     rcx, rbx
0x18000cbef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cbf4  jmp     short loc_18000CC3A
0x18000cbf6  mov     ebp, 800h
0x18000cbfb  mov     rax, cs:g_pfnResultLoggingCallback
0x18000cc02  test    rax, rax
0x18000cc05  jz      short loc_18000CC1E
0x18000cc07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000cc0e  jnz     short loc_18000CC1E
0x18000cc10  mov     r8d, ebp
0x18000cc13  mov     rdx, rsi
0x18000cc16  mov     rcx, rbx
0x18000cc19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc1e  cmp     [rsi], di
0x18000cc21  jnz     short loc_18000CC31
0x18000cc23  mov     r8, rbx; unsigned __int64
0x18000cc26  mov     rdx, rbp; unsigned __int16 *
0x18000cc29  mov     rcx, rsi; this
0x18000cc2c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000cc31  mov     rcx, rsi; lpOutputString
0x18000cc34  call    cs:__imp_OutputDebugStringW
0x18000cc3a  test    byte ptr [rbx+4], 4
0x18000cc3e  jnz     short loc_18000CC49
0x18000cc40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000cc47  jz      short loc_18000CC5B
0x18000cc49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000cc50  test    rax, rax
0x18000cc53  jz      short loc_18000CC5B
0x18000cc55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cc5a  nop
0x18000cc5b  mov     rbx, [rsp+78h+arg_10]
0x18000cc63  add     rsp, 40h
0x18000cc67  pop     r15
0x18000cc69  pop     r14
0x18000cc6b  pop     r13
0x18000cc6d  pop     r12
0x18000cc6f  pop     rdi
0x18000cc70  pop     rsi
0x18000cc71  pop     rbp
0x18000cc72  retn
0x18000cc73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
