# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006b94`
- end: `0x180006e8d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004254`
- `0x1800045c0`
- `0x18000b614`

## callees

- `0x18000418c`
- `0x180005f94`
- `0x1800067a0`
- `0x180006b94`
- `0x180007ab0`
- `0x180007ad0`
- `0x180007c54`
- `0x180007c70`
- `0x180009c20`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cb7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006cb7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e48`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006e48`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006dd6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006dd6`

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
0x180006b94  mov     [rsp+arg_10], rbx
0x180006b99  mov     [rsp+arg_8], edx
0x180006b9d  mov     [rsp+arg_0], rcx
0x180006ba2  push    rbp
0x180006ba3  push    rsi
0x180006ba4  push    rdi
0x180006ba5  push    r12
0x180006ba7  push    r13
0x180006ba9  push    r14
0x180006bab  push    r15
0x180006bad  sub     rsp, 40h
0x180006bb1  mov     r12, r9
0x180006bb4  mov     r13, r8
0x180006bb7  mov     r10, rcx
0x180006bba  xor     eax, eax
0x180006bbc  mov     rsi, [rsp+78h+lpOutputString]
0x180006bc4  mov     [rsi], ax
0x180006bc7  mov     rax, [rsp+78h+arg_60]
0x180006bcf  mov     byte ptr [rax], 0
0x180006bd2  mov     r14, [rsp+78h+arg_38]
0x180006bda  mov     edi, [r14]
0x180006bdd  mov     rbx, [rsp+78h+arg_78]
0x180006be5  mov     [rbx+8], edi
0x180006be8  mov     eax, [r14+4]
0x180006bec  mov     [rbx+0Ch], eax
0x180006bef  xor     ebp, ebp
0x180006bf1  mov     r15d, [rsp+78h+arg_30]
0x180006bf9  mov     ecx, r15d
0x180006bfc  test    r15d, r15d
0x180006bff  jz      short loc_180006C67
0x180006c01  sub     ecx, 1
0x180006c04  jz      short loc_180006C5E
0x180006c06  sub     ecx, 1
0x180006c09  jz      short loc_180006C19
0x180006c0b  cmp     ecx, 1
0x180006c0e  jnz     short loc_180006C70
0x180006c10  mov     ecx, edi; this
0x180006c12  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006c17  jmp     short loc_180006C6E
0x180006c19  test    edi, edi
0x180006c1b  js      short loc_180006C55
0x180006c1d  mov     edi, 8007029Ch
0x180006c22  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006c26  mov     rax, [rsp+78h+arg_28]
0x180006c2e  mov     [rsp+78h+var_50], rax; __int64
0x180006c33  mov     rax, [rsp+78h+arg_20]
0x180006c3b  mov     [rsp+78h+var_58], rax; __int64
0x180006c40  mov     rcx, r10; int
0x180006c43  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006c48  mov     [rbx+8], edi
0x180006c4b  mov     ecx, edi; this
0x180006c4d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006c52  mov     [rbx+0Ch], eax
0x180006c55  mov     ecx, edi; this
0x180006c57  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006c5c  jmp     short loc_180006C6E
0x180006c5e  mov     ecx, edi; this
0x180006c60  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006c65  jmp     short loc_180006C6E
0x180006c67  mov     ecx, edi; this
0x180006c69  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006c6e  mov     ebp, eax
0x180006c70  mov     [rbx], r15d
0x180006c73  mov     eax, [rsp+78h+arg_70]
0x180006c7a  mov     [rbx+4], eax
0x180006c7d  cmp     dword ptr [r14+8], 1
0x180006c82  jnz     short loc_180006C8A
0x180006c84  or      eax, 8
0x180006c87  mov     [rbx+4], eax
0x180006c8a  mov     eax, 1
0x180006c8f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006c97  inc     eax
0x180006c99  mov     [rbx+10h], eax
0x180006c9c  mov     rax, [rsp+78h+arg_40]
0x180006ca4  xor     edi, edi
0x180006ca6  test    rax, rax
0x180006ca9  jz      short loc_180006CB0
0x180006cab  cmp     [rax], di
0x180006cae  jnz     short loc_180006CB3
0x180006cb0  mov     rax, rdi
0x180006cb3  mov     [rbx+18h], rax
0x180006cb7  call    cs:__imp_GetCurrentThreadId
0x180006cbd  mov     [rbx+20h], eax
0x180006cc0  mov     [rbx+38h], r13
0x180006cc4  mov     eax, [rsp+78h+arg_8]
0x180006ccb  mov     [rbx+40h], eax
0x180006cce  mov     [rbx+44h], ebp
0x180006cd1  mov     rax, [rsp+78h+arg_20]
0x180006cd9  mov     [rbx+28h], rax
0x180006cdd  mov     [rbx+30h], r12
0x180006ce1  mov     rax, [rsp+78h+arg_28]
0x180006ce9  mov     [rbx+88h], rax
0x180006cf0  mov     rax, [rsp+78h+arg_0]
0x180006cf8  mov     [rbx+90h], rax
0x180006cff  mov     [rbx+48h], rdi
0x180006d03  xorps   xmm0, xmm0
0x180006d06  xor     eax, eax
0x180006d08  movups  xmmword ptr [rbx+68h], xmm0
0x180006d0c  mov     [rbx+78h], rax
0x180006d10  movups  xmmword ptr [rbx+50h], xmm0
0x180006d14  mov     [rbx+60h], rax
0x180006d18  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006d1f  test    rax, rax
0x180006d22  jz      short loc_180006D2B
0x180006d24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d29  jmp     short loc_180006D2E
0x180006d2b  mov     rax, rdi
0x180006d2e  mov     [rbx+80h], rax
0x180006d35  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006d3c  test    rax, rax
0x180006d3f  jz      short loc_180006D49
0x180006d41  mov     rcx, rbx
0x180006d44  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d49  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006d50  test    rax, rax
0x180006d53  jz      short loc_180006D6B
0x180006d55  mov     r8d, 400h
0x180006d5b  mov     rdx, [rsp+78h+arg_60]
0x180006d63  mov     rcx, rbx
0x180006d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d6b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d72  test    rax, rax
0x180006d75  jz      short loc_180006D7F
0x180006d77  mov     rcx, rbx
0x180006d7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d7f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006d86  test    rax, rax
0x180006d89  jz      short loc_180006D99
0x180006d8b  test    byte ptr [rbx+4], 2
0x180006d8f  jnz     short loc_180006D99
0x180006d91  mov     rcx, rbx
0x180006d94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d99  cmp     [rbx+8], edi
0x180006d9c  jl      short loc_180006DB8
0x180006d9e  cmp     r15d, 3
0x180006da2  jnz     loc_180006E87
0x180006da8  mov     ecx, 8000FFFFh; this
0x180006dad  mov     [rbx+8], ecx
0x180006db0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006db5  mov     [rbx+0Ch], eax
0x180006db8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006dbf  jnz     short loc_180006DE0
0x180006dc1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006dc8  test    rax, rax
0x180006dcb  jz      short loc_180006DD6
0x180006dcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006dd2  test    al, al
0x180006dd4  jmp     short loc_180006DDE
0x180006dd6  call    cs:__imp_IsDebuggerPresent
0x180006ddc  test    eax, eax
0x180006dde  jz      short loc_180006DE6
0x180006de0  test    byte ptr [rbx+4], 2
0x180006de4  jz      short loc_180006E0A
0x180006de6  mov     rax, cs:g_pfnResultLoggingCallback
0x180006ded  test    rax, rax
0x180006df0  jz      short loc_180006E4E
0x180006df2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006df9  jnz     short loc_180006E4E
0x180006dfb  xor     r8d, r8d
0x180006dfe  xor     edx, edx
0x180006e00  mov     rcx, rbx
0x180006e03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e08  jmp     short loc_180006E4E
0x180006e0a  mov     ebp, 800h
0x180006e0f  mov     rax, cs:g_pfnResultLoggingCallback
0x180006e16  test    rax, rax
0x180006e19  jz      short loc_180006E32
0x180006e1b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006e22  jnz     short loc_180006E32
0x180006e24  mov     r8d, ebp
0x180006e27  mov     rdx, rsi
0x180006e2a  mov     rcx, rbx
0x180006e2d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e32  cmp     [rsi], di
0x180006e35  jnz     short loc_180006E45
0x180006e37  mov     r8, rbx; unsigned __int64
0x180006e3a  mov     rdx, rbp; unsigned __int16 *
0x180006e3d  mov     rcx, rsi; this
0x180006e40  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006e45  mov     rcx, rsi; lpOutputString
0x180006e48  call    cs:__imp_OutputDebugStringW
0x180006e4e  test    byte ptr [rbx+4], 4
0x180006e52  jnz     short loc_180006E5D
0x180006e54  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006e5b  jz      short loc_180006E6F
0x180006e5d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006e64  test    rax, rax
0x180006e67  jz      short loc_180006E6F
0x180006e69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e6e  nop
0x180006e6f  mov     rbx, [rsp+78h+arg_10]
0x180006e77  add     rsp, 40h
0x180006e7b  pop     r15
0x180006e7d  pop     r14
0x180006e7f  pop     r13
0x180006e81  pop     r12
0x180006e83  pop     rdi
0x180006e84  pop     rsi
0x180006e85  pop     rbp
0x180006e86  retn
0x180006e87  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
