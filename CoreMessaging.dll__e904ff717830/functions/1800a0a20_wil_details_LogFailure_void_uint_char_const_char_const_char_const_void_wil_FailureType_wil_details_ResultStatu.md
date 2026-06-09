# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800a0a20`
- end: `0x1800a0d19`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18009f4b8`
- `0x18009f7fc`

## callees

- `0x180097c24`
- `0x18009f3f8`
- `0x1800a02e4`
- `0x1800a0a20`
- `0x1800a0ed4`
- `0x1800a0ef0`
- `0x1800a0f04`
- `0x1800a0f20`
- `0x1800a1ad8`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0b43`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a0b43`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a0cd4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a0cd4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a0c62`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a0c62`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x1800a0a20  mov     [rsp+arg_10], rbx
0x1800a0a25  mov     [rsp+arg_8], edx
0x1800a0a29  mov     [rsp+arg_0], rcx
0x1800a0a2e  push    rbp
0x1800a0a2f  push    rsi
0x1800a0a30  push    rdi
0x1800a0a31  push    r12
0x1800a0a33  push    r13
0x1800a0a35  push    r14
0x1800a0a37  push    r15
0x1800a0a39  sub     rsp, 40h
0x1800a0a3d  mov     r12, r9
0x1800a0a40  mov     r13, r8
0x1800a0a43  mov     r10, rcx
0x1800a0a46  xor     eax, eax
0x1800a0a48  mov     rsi, [rsp+78h+lpOutputString]
0x1800a0a50  mov     [rsi], ax
0x1800a0a53  mov     rax, [rsp+78h+arg_60]
0x1800a0a5b  mov     byte ptr [rax], 0
0x1800a0a5e  mov     r14, [rsp+78h+arg_38]
0x1800a0a66  mov     edi, [r14]
0x1800a0a69  mov     rbx, [rsp+78h+arg_78]
0x1800a0a71  mov     [rbx+8], edi
0x1800a0a74  mov     eax, [r14+4]
0x1800a0a78  mov     [rbx+0Ch], eax
0x1800a0a7b  xor     ebp, ebp
0x1800a0a7d  mov     r15d, [rsp+78h+arg_30]
0x1800a0a85  mov     ecx, r15d
0x1800a0a88  test    r15d, r15d
0x1800a0a8b  jz      short loc_1800A0AF3
0x1800a0a8d  sub     ecx, 1
0x1800a0a90  jz      short loc_1800A0AEA
0x1800a0a92  sub     ecx, 1
0x1800a0a95  jz      short loc_1800A0AA5
0x1800a0a97  cmp     ecx, 1
0x1800a0a9a  jnz     short loc_1800A0AFC
0x1800a0a9c  mov     ecx, edi; this
0x1800a0a9e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800a0aa3  jmp     short loc_1800A0AFA
0x1800a0aa5  test    edi, edi
0x1800a0aa7  js      short loc_1800A0AE1
0x1800a0aa9  mov     edi, 8007029Ch
0x1800a0aae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800a0ab2  mov     rax, [rsp+78h+arg_28]
0x1800a0aba  mov     [rsp+78h+var_50], rax; __int64
0x1800a0abf  mov     rax, [rsp+78h+arg_20]
0x1800a0ac7  mov     [rsp+78h+var_58], rax; __int64
0x1800a0acc  mov     rcx, r10; int
0x1800a0acf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800a0ad4  mov     [rbx+8], edi
0x1800a0ad7  mov     ecx, edi; this
0x1800a0ad9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a0ade  mov     [rbx+0Ch], eax
0x1800a0ae1  mov     ecx, edi; this
0x1800a0ae3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800a0ae8  jmp     short loc_1800A0AFA
0x1800a0aea  mov     ecx, edi; this
0x1800a0aec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800a0af1  jmp     short loc_1800A0AFA
0x1800a0af3  mov     ecx, edi; this
0x1800a0af5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800a0afa  mov     ebp, eax
0x1800a0afc  mov     [rbx], r15d
0x1800a0aff  mov     eax, [rsp+78h+arg_70]
0x1800a0b06  mov     [rbx+4], eax
0x1800a0b09  cmp     dword ptr [r14+8], 1
0x1800a0b0e  jnz     short loc_1800A0B16
0x1800a0b10  or      eax, 8
0x1800a0b13  mov     [rbx+4], eax
0x1800a0b16  mov     eax, 1
0x1800a0b1b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a0b23  inc     eax
0x1800a0b25  mov     [rbx+10h], eax
0x1800a0b28  mov     rax, [rsp+78h+arg_40]
0x1800a0b30  xor     edi, edi
0x1800a0b32  test    rax, rax
0x1800a0b35  jz      short loc_1800A0B3C
0x1800a0b37  cmp     [rax], di
0x1800a0b3a  jnz     short loc_1800A0B3F
0x1800a0b3c  mov     rax, rdi
0x1800a0b3f  mov     [rbx+18h], rax
0x1800a0b43  call    cs:__imp_GetCurrentThreadId
0x1800a0b49  mov     [rbx+20h], eax
0x1800a0b4c  mov     [rbx+38h], r13
0x1800a0b50  mov     eax, [rsp+78h+arg_8]
0x1800a0b57  mov     [rbx+40h], eax
0x1800a0b5a  mov     [rbx+44h], ebp
0x1800a0b5d  mov     rax, [rsp+78h+arg_20]
0x1800a0b65  mov     [rbx+28h], rax
0x1800a0b69  mov     [rbx+30h], r12
0x1800a0b6d  mov     rax, [rsp+78h+arg_28]
0x1800a0b75  mov     [rbx+88h], rax
0x1800a0b7c  mov     rax, [rsp+78h+arg_0]
0x1800a0b84  mov     [rbx+90h], rax
0x1800a0b8b  mov     [rbx+48h], rdi
0x1800a0b8f  xorps   xmm0, xmm0
0x1800a0b92  xor     eax, eax
0x1800a0b94  movups  xmmword ptr [rbx+68h], xmm0
0x1800a0b98  mov     [rbx+78h], rax
0x1800a0b9c  movups  xmmword ptr [rbx+50h], xmm0
0x1800a0ba0  mov     [rbx+60h], rax
0x1800a0ba4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a0bab  test    rax, rax
0x1800a0bae  jz      short loc_1800A0BB7
0x1800a0bb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0bb5  jmp     short loc_1800A0BBA
0x1800a0bb7  mov     rax, rdi
0x1800a0bba  mov     [rbx+80h], rax
0x1800a0bc1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a0bc8  test    rax, rax
0x1800a0bcb  jz      short loc_1800A0BD5
0x1800a0bcd  mov     rcx, rbx
0x1800a0bd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0bd5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a0bdc  test    rax, rax
0x1800a0bdf  jz      short loc_1800A0BF7
0x1800a0be1  mov     r8d, 400h
0x1800a0be7  mov     rdx, [rsp+78h+arg_60]
0x1800a0bef  mov     rcx, rbx
0x1800a0bf2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0bf7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a0bfe  test    rax, rax
0x1800a0c01  jz      short loc_1800A0C0B
0x1800a0c03  mov     rcx, rbx
0x1800a0c06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c0b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a0c12  test    rax, rax
0x1800a0c15  jz      short loc_1800A0C25
0x1800a0c17  test    byte ptr [rbx+4], 2
0x1800a0c1b  jnz     short loc_1800A0C25
0x1800a0c1d  mov     rcx, rbx
0x1800a0c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c25  cmp     [rbx+8], edi
0x1800a0c28  jl      short loc_1800A0C44
0x1800a0c2a  cmp     r15d, 3
0x1800a0c2e  jnz     loc_1800A0D13
0x1800a0c34  mov     ecx, 8000FFFFh; this
0x1800a0c39  mov     [rbx+8], ecx
0x1800a0c3c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a0c41  mov     [rbx+0Ch], eax
0x1800a0c44  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800a0c4b  jnz     short loc_1800A0C6C
0x1800a0c4d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a0c54  test    rax, rax
0x1800a0c57  jz      short loc_1800A0C62
0x1800a0c59  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c5e  test    al, al
0x1800a0c60  jmp     short loc_1800A0C6A
0x1800a0c62  call    cs:__imp_IsDebuggerPresent
0x1800a0c68  test    eax, eax
0x1800a0c6a  jz      short loc_1800A0C72
0x1800a0c6c  test    byte ptr [rbx+4], 2
0x1800a0c70  jz      short loc_1800A0C96
0x1800a0c72  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a0c79  test    rax, rax
0x1800a0c7c  jz      short loc_1800A0CDA
0x1800a0c7e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a0c85  jnz     short loc_1800A0CDA
0x1800a0c87  xor     r8d, r8d
0x1800a0c8a  xor     edx, edx
0x1800a0c8c  mov     rcx, rbx
0x1800a0c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0c94  jmp     short loc_1800A0CDA
0x1800a0c96  mov     ebp, 800h
0x1800a0c9b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a0ca2  test    rax, rax
0x1800a0ca5  jz      short loc_1800A0CBE
0x1800a0ca7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a0cae  jnz     short loc_1800A0CBE
0x1800a0cb0  mov     r8d, ebp
0x1800a0cb3  mov     rdx, rsi
0x1800a0cb6  mov     rcx, rbx
0x1800a0cb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0cbe  cmp     [rsi], di
0x1800a0cc1  jnz     short loc_1800A0CD1
0x1800a0cc3  mov     r8, rbx; unsigned __int64
0x1800a0cc6  mov     rdx, rbp; wchar_t *
0x1800a0cc9  mov     rcx, rsi; this
0x1800a0ccc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800a0cd1  mov     rcx, rsi; lpOutputString
0x1800a0cd4  call    cs:__imp_OutputDebugStringW
0x1800a0cda  test    byte ptr [rbx+4], 4
0x1800a0cde  jnz     short loc_1800A0CE9
0x1800a0ce0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800a0ce7  jz      short loc_1800A0CFB
0x1800a0ce9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a0cf0  test    rax, rax
0x1800a0cf3  jz      short loc_1800A0CFB
0x1800a0cf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a0cfa  nop
0x1800a0cfb  mov     rbx, [rsp+78h+arg_10]
0x1800a0d03  add     rsp, 40h
0x1800a0d07  pop     r15
0x1800a0d09  pop     r14
0x1800a0d0b  pop     r13
0x1800a0d0d  pop     r12
0x1800a0d0f  pop     rdi
0x1800a0d10  pop     rsi
0x1800a0d11  pop     rbp
0x1800a0d12  retn
0x1800a0d13  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
