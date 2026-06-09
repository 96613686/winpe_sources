# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008a9c`
- end: `0x180008d95`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005d54`

## callees

- `0x180005760`
- `0x180007fa4`
- `0x1800087f0`
- `0x180008a9c`
- `0x180009750`
- `0x180009770`
- `0x18000989c`
- `0x1800098b8`
- `0x18000c258`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008bbf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008cde`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008cde`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008d50`

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
0x180008a9c  mov     [rsp+arg_10], rbx
0x180008aa1  mov     [rsp+arg_8], edx
0x180008aa5  mov     [rsp+arg_0], rcx
0x180008aaa  push    rbp
0x180008aab  push    rsi
0x180008aac  push    rdi
0x180008aad  push    r12
0x180008aaf  push    r13
0x180008ab1  push    r14
0x180008ab3  push    r15
0x180008ab5  sub     rsp, 40h
0x180008ab9  mov     r12, r9
0x180008abc  mov     r13, r8
0x180008abf  mov     r10, rcx
0x180008ac2  xor     eax, eax
0x180008ac4  mov     rsi, [rsp+78h+lpOutputString]
0x180008acc  mov     [rsi], ax
0x180008acf  mov     rax, [rsp+78h+arg_60]
0x180008ad7  mov     byte ptr [rax], 0
0x180008ada  mov     r14, [rsp+78h+arg_38]
0x180008ae2  mov     edi, [r14]
0x180008ae5  mov     rbx, [rsp+78h+arg_78]
0x180008aed  mov     [rbx+8], edi
0x180008af0  mov     eax, [r14+4]
0x180008af4  mov     [rbx+0Ch], eax
0x180008af7  xor     ebp, ebp
0x180008af9  mov     r15d, [rsp+78h+arg_30]
0x180008b01  mov     ecx, r15d
0x180008b04  test    r15d, r15d
0x180008b07  jz      short loc_180008B6F
0x180008b09  sub     ecx, 1
0x180008b0c  jz      short loc_180008B66
0x180008b0e  sub     ecx, 1
0x180008b11  jz      short loc_180008B21
0x180008b13  cmp     ecx, 1
0x180008b16  jnz     short loc_180008B78
0x180008b18  mov     ecx, edi; this
0x180008b1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008b1f  jmp     short loc_180008B76
0x180008b21  test    edi, edi
0x180008b23  js      short loc_180008B5D
0x180008b25  mov     edi, 8007029Ch
0x180008b2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008b2e  mov     rax, [rsp+78h+arg_28]
0x180008b36  mov     [rsp+78h+var_50], rax; __int64
0x180008b3b  mov     rax, [rsp+78h+arg_20]
0x180008b43  mov     [rsp+78h+var_58], rax; __int64
0x180008b48  mov     rcx, r10; int
0x180008b4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008b50  mov     [rbx+8], edi
0x180008b53  mov     ecx, edi; this
0x180008b55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008b5a  mov     [rbx+0Ch], eax
0x180008b5d  mov     ecx, edi; this
0x180008b5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008b64  jmp     short loc_180008B76
0x180008b66  mov     ecx, edi; this
0x180008b68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008b6d  jmp     short loc_180008B76
0x180008b6f  mov     ecx, edi; this
0x180008b71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008b76  mov     ebp, eax
0x180008b78  mov     [rbx], r15d
0x180008b7b  mov     eax, [rsp+78h+arg_70]
0x180008b82  mov     [rbx+4], eax
0x180008b85  cmp     dword ptr [r14+8], 1
0x180008b8a  jnz     short loc_180008B92
0x180008b8c  or      eax, 8
0x180008b8f  mov     [rbx+4], eax
0x180008b92  mov     eax, 1
0x180008b97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008b9f  inc     eax
0x180008ba1  mov     [rbx+10h], eax
0x180008ba4  mov     rax, [rsp+78h+arg_40]
0x180008bac  xor     edi, edi
0x180008bae  test    rax, rax
0x180008bb1  jz      short loc_180008BB8
0x180008bb3  cmp     [rax], di
0x180008bb6  jnz     short loc_180008BBB
0x180008bb8  mov     rax, rdi
0x180008bbb  mov     [rbx+18h], rax
0x180008bbf  call    cs:__imp_GetCurrentThreadId
0x180008bc5  mov     [rbx+20h], eax
0x180008bc8  mov     [rbx+38h], r13
0x180008bcc  mov     eax, [rsp+78h+arg_8]
0x180008bd3  mov     [rbx+40h], eax
0x180008bd6  mov     [rbx+44h], ebp
0x180008bd9  mov     rax, [rsp+78h+arg_20]
0x180008be1  mov     [rbx+28h], rax
0x180008be5  mov     [rbx+30h], r12
0x180008be9  mov     rax, [rsp+78h+arg_28]
0x180008bf1  mov     [rbx+88h], rax
0x180008bf8  mov     rax, [rsp+78h+arg_0]
0x180008c00  mov     [rbx+90h], rax
0x180008c07  mov     [rbx+48h], rdi
0x180008c0b  xorps   xmm0, xmm0
0x180008c0e  xor     eax, eax
0x180008c10  movups  xmmword ptr [rbx+68h], xmm0
0x180008c14  mov     [rbx+78h], rax
0x180008c18  movups  xmmword ptr [rbx+50h], xmm0
0x180008c1c  mov     [rbx+60h], rax
0x180008c20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008c27  test    rax, rax
0x180008c2a  jz      short loc_180008C33
0x180008c2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c31  jmp     short loc_180008C36
0x180008c33  mov     rax, rdi
0x180008c36  mov     [rbx+80h], rax
0x180008c3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008c44  test    rax, rax
0x180008c47  jz      short loc_180008C51
0x180008c49  mov     rcx, rbx
0x180008c4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008c58  test    rax, rax
0x180008c5b  jz      short loc_180008C73
0x180008c5d  mov     r8d, 400h
0x180008c63  mov     rdx, [rsp+78h+arg_60]
0x180008c6b  mov     rcx, rbx
0x180008c6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008c7a  test    rax, rax
0x180008c7d  jz      short loc_180008C87
0x180008c7f  mov     rcx, rbx
0x180008c82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008c8e  test    rax, rax
0x180008c91  jz      short loc_180008CA1
0x180008c93  test    byte ptr [rbx+4], 2
0x180008c97  jnz     short loc_180008CA1
0x180008c99  mov     rcx, rbx
0x180008c9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ca1  cmp     [rbx+8], edi
0x180008ca4  jl      short loc_180008CC0
0x180008ca6  cmp     r15d, 3
0x180008caa  jnz     loc_180008D8F
0x180008cb0  mov     ecx, 8000FFFFh; this
0x180008cb5  mov     [rbx+8], ecx
0x180008cb8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008cbd  mov     [rbx+0Ch], eax
0x180008cc0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008cc7  jnz     short loc_180008CE8
0x180008cc9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008cd0  test    rax, rax
0x180008cd3  jz      short loc_180008CDE
0x180008cd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008cda  test    al, al
0x180008cdc  jmp     short loc_180008CE6
0x180008cde  call    cs:__imp_IsDebuggerPresent
0x180008ce4  test    eax, eax
0x180008ce6  jz      short loc_180008CEE
0x180008ce8  test    byte ptr [rbx+4], 2
0x180008cec  jz      short loc_180008D12
0x180008cee  mov     rax, cs:g_pfnResultLoggingCallback
0x180008cf5  test    rax, rax
0x180008cf8  jz      short loc_180008D56
0x180008cfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008d01  jnz     short loc_180008D56
0x180008d03  xor     r8d, r8d
0x180008d06  xor     edx, edx
0x180008d08  mov     rcx, rbx
0x180008d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d10  jmp     short loc_180008D56
0x180008d12  mov     ebp, 800h
0x180008d17  mov     rax, cs:g_pfnResultLoggingCallback
0x180008d1e  test    rax, rax
0x180008d21  jz      short loc_180008D3A
0x180008d23  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008d2a  jnz     short loc_180008D3A
0x180008d2c  mov     r8d, ebp
0x180008d2f  mov     rdx, rsi
0x180008d32  mov     rcx, rbx
0x180008d35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d3a  cmp     [rsi], di
0x180008d3d  jnz     short loc_180008D4D
0x180008d3f  mov     r8, rbx; unsigned __int64
0x180008d42  mov     rdx, rbp; wchar_t *
0x180008d45  mov     rcx, rsi; this
0x180008d48  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180008d4d  mov     rcx, rsi; lpOutputString
0x180008d50  call    cs:__imp_OutputDebugStringW
0x180008d56  test    byte ptr [rbx+4], 4
0x180008d5a  jnz     short loc_180008D65
0x180008d5c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008d63  jz      short loc_180008D77
0x180008d65  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008d6c  test    rax, rax
0x180008d6f  jz      short loc_180008D77
0x180008d71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d76  nop
0x180008d77  mov     rbx, [rsp+78h+arg_10]
0x180008d7f  add     rsp, 40h
0x180008d83  pop     r15
0x180008d85  pop     r14
0x180008d87  pop     r13
0x180008d89  pop     r12
0x180008d8b  pop     rdi
0x180008d8c  pop     rsi
0x180008d8d  pop     rbp
0x180008d8e  retn
0x180008d8f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
