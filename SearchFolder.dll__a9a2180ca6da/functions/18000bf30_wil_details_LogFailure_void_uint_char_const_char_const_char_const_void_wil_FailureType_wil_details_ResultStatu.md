# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000bf30`
- end: `0x18000c229`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180008a8c`
- `0x180008df8`
- `0x180011d30`

## callees

- `0x180003da0`
- `0x1800089b4`
- `0x18000b394`
- `0x18000bf30`
- `0x18000cfbc`
- `0x18000cfe0`
- `0x18000d09c`
- `0x18000d0b8`
- `0x18000fe60`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c053`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c1e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c172`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c172`

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
0x18000bf30  mov     [rsp+arg_10], rbx
0x18000bf35  mov     [rsp+arg_8], edx
0x18000bf39  mov     [rsp+arg_0], rcx
0x18000bf3e  push    rbp
0x18000bf3f  push    rsi
0x18000bf40  push    rdi
0x18000bf41  push    r12
0x18000bf43  push    r13
0x18000bf45  push    r14
0x18000bf47  push    r15
0x18000bf49  sub     rsp, 40h
0x18000bf4d  mov     r12, r9
0x18000bf50  mov     r13, r8
0x18000bf53  mov     r10, rcx
0x18000bf56  xor     eax, eax
0x18000bf58  mov     rsi, [rsp+78h+lpOutputString]
0x18000bf60  mov     [rsi], ax
0x18000bf63  mov     rax, [rsp+78h+arg_60]
0x18000bf6b  mov     byte ptr [rax], 0
0x18000bf6e  mov     r14, [rsp+78h+arg_38]
0x18000bf76  mov     edi, [r14]
0x18000bf79  mov     rbx, [rsp+78h+arg_78]
0x18000bf81  mov     [rbx+8], edi
0x18000bf84  mov     eax, [r14+4]
0x18000bf88  mov     [rbx+0Ch], eax
0x18000bf8b  xor     ebp, ebp
0x18000bf8d  mov     r15d, [rsp+78h+arg_30]
0x18000bf95  mov     ecx, r15d
0x18000bf98  test    r15d, r15d
0x18000bf9b  jz      short loc_18000C003
0x18000bf9d  sub     ecx, 1
0x18000bfa0  jz      short loc_18000BFFA
0x18000bfa2  sub     ecx, 1
0x18000bfa5  jz      short loc_18000BFB5
0x18000bfa7  cmp     ecx, 1
0x18000bfaa  jnz     short loc_18000C00C
0x18000bfac  mov     ecx, edi; this
0x18000bfae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000bfb3  jmp     short loc_18000C00A
0x18000bfb5  test    edi, edi
0x18000bfb7  js      short loc_18000BFF1
0x18000bfb9  mov     edi, 8007029Ch
0x18000bfbe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000bfc2  mov     rax, [rsp+78h+arg_28]
0x18000bfca  mov     [rsp+78h+var_50], rax; __int64
0x18000bfcf  mov     rax, [rsp+78h+arg_20]
0x18000bfd7  mov     [rsp+78h+var_58], rax; __int64
0x18000bfdc  mov     rcx, r10; int
0x18000bfdf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000bfe4  mov     [rbx+8], edi
0x18000bfe7  mov     ecx, edi; this
0x18000bfe9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000bfee  mov     [rbx+0Ch], eax
0x18000bff1  mov     ecx, edi; this
0x18000bff3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000bff8  jmp     short loc_18000C00A
0x18000bffa  mov     ecx, edi; this
0x18000bffc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c001  jmp     short loc_18000C00A
0x18000c003  mov     ecx, edi; this
0x18000c005  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c00a  mov     ebp, eax
0x18000c00c  mov     [rbx], r15d
0x18000c00f  mov     eax, [rsp+78h+arg_70]
0x18000c016  mov     [rbx+4], eax
0x18000c019  cmp     dword ptr [r14+8], 1
0x18000c01e  jnz     short loc_18000C026
0x18000c020  or      eax, 8
0x18000c023  mov     [rbx+4], eax
0x18000c026  mov     eax, 1
0x18000c02b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c033  inc     eax
0x18000c035  mov     [rbx+10h], eax
0x18000c038  mov     rax, [rsp+78h+arg_40]
0x18000c040  xor     edi, edi
0x18000c042  test    rax, rax
0x18000c045  jz      short loc_18000C04C
0x18000c047  cmp     [rax], di
0x18000c04a  jnz     short loc_18000C04F
0x18000c04c  mov     rax, rdi
0x18000c04f  mov     [rbx+18h], rax
0x18000c053  call    cs:__imp_GetCurrentThreadId
0x18000c059  mov     [rbx+20h], eax
0x18000c05c  mov     [rbx+38h], r13
0x18000c060  mov     eax, [rsp+78h+arg_8]
0x18000c067  mov     [rbx+40h], eax
0x18000c06a  mov     [rbx+44h], ebp
0x18000c06d  mov     rax, [rsp+78h+arg_20]
0x18000c075  mov     [rbx+28h], rax
0x18000c079  mov     [rbx+30h], r12
0x18000c07d  mov     rax, [rsp+78h+arg_28]
0x18000c085  mov     [rbx+88h], rax
0x18000c08c  mov     rax, [rsp+78h+arg_0]
0x18000c094  mov     [rbx+90h], rax
0x18000c09b  mov     [rbx+48h], rdi
0x18000c09f  xorps   xmm0, xmm0
0x18000c0a2  xor     eax, eax
0x18000c0a4  movups  xmmword ptr [rbx+68h], xmm0
0x18000c0a8  mov     [rbx+78h], rax
0x18000c0ac  movups  xmmword ptr [rbx+50h], xmm0
0x18000c0b0  mov     [rbx+60h], rax
0x18000c0b4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c0bb  test    rax, rax
0x18000c0be  jz      short loc_18000C0C7
0x18000c0c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0c5  jmp     short loc_18000C0CA
0x18000c0c7  mov     rax, rdi
0x18000c0ca  mov     [rbx+80h], rax
0x18000c0d1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c0d8  test    rax, rax
0x18000c0db  jz      short loc_18000C0E5
0x18000c0dd  mov     rcx, rbx
0x18000c0e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c0e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c0ec  test    rax, rax
0x18000c0ef  jz      short loc_18000C107
0x18000c0f1  mov     r8d, 400h
0x18000c0f7  mov     rdx, [rsp+78h+arg_60]
0x18000c0ff  mov     rcx, rbx
0x18000c102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c107  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c10e  test    rax, rax
0x18000c111  jz      short loc_18000C11B
0x18000c113  mov     rcx, rbx
0x18000c116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c11b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c122  test    rax, rax
0x18000c125  jz      short loc_18000C135
0x18000c127  test    byte ptr [rbx+4], 2
0x18000c12b  jnz     short loc_18000C135
0x18000c12d  mov     rcx, rbx
0x18000c130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c135  cmp     [rbx+8], edi
0x18000c138  jl      short loc_18000C154
0x18000c13a  cmp     r15d, 3
0x18000c13e  jnz     loc_18000C223
0x18000c144  mov     ecx, 8000FFFFh; this
0x18000c149  mov     [rbx+8], ecx
0x18000c14c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c151  mov     [rbx+0Ch], eax
0x18000c154  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c15b  jnz     short loc_18000C17C
0x18000c15d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c164  test    rax, rax
0x18000c167  jz      short loc_18000C172
0x18000c169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c16e  test    al, al
0x18000c170  jmp     short loc_18000C17A
0x18000c172  call    cs:__imp_IsDebuggerPresent
0x18000c178  test    eax, eax
0x18000c17a  jz      short loc_18000C182
0x18000c17c  test    byte ptr [rbx+4], 2
0x18000c180  jz      short loc_18000C1A6
0x18000c182  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c189  test    rax, rax
0x18000c18c  jz      short loc_18000C1EA
0x18000c18e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c195  jnz     short loc_18000C1EA
0x18000c197  xor     r8d, r8d
0x18000c19a  xor     edx, edx
0x18000c19c  mov     rcx, rbx
0x18000c19f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1a4  jmp     short loc_18000C1EA
0x18000c1a6  mov     ebp, 800h
0x18000c1ab  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c1b2  test    rax, rax
0x18000c1b5  jz      short loc_18000C1CE
0x18000c1b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c1be  jnz     short loc_18000C1CE
0x18000c1c0  mov     r8d, ebp
0x18000c1c3  mov     rdx, rsi
0x18000c1c6  mov     rcx, rbx
0x18000c1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c1ce  cmp     [rsi], di
0x18000c1d1  jnz     short loc_18000C1E1
0x18000c1d3  mov     r8, rbx; unsigned __int64
0x18000c1d6  mov     rdx, rbp; unsigned __int16 *
0x18000c1d9  mov     rcx, rsi; this
0x18000c1dc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c1e1  mov     rcx, rsi; lpOutputString
0x18000c1e4  call    cs:__imp_OutputDebugStringW
0x18000c1ea  test    byte ptr [rbx+4], 4
0x18000c1ee  jnz     short loc_18000C1F9
0x18000c1f0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c1f7  jz      short loc_18000C20B
0x18000c1f9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c200  test    rax, rax
0x18000c203  jz      short loc_18000C20B
0x18000c205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c20a  nop
0x18000c20b  mov     rbx, [rsp+78h+arg_10]
0x18000c213  add     rsp, 40h
0x18000c217  pop     r15
0x18000c219  pop     r14
0x18000c21b  pop     r13
0x18000c21d  pop     r12
0x18000c21f  pop     rdi
0x18000c220  pop     rsi
0x18000c221  pop     rbp
0x18000c222  retn
0x18000c223  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
