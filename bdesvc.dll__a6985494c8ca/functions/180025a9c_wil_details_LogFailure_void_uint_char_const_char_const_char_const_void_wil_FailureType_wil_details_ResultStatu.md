# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180025a9c`
- end: `0x180025da4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180025884`
- `0x1800259ac`
- `0x1800359c8`
- `0x180050c4c`

## callees

- `0x180025a9c`
- `0x18002b7d0`
- `0x180035914`
- `0x1800363d4`
- `0x180037168`
- `0x180037190`
- `0x1800371a4`
- `0x1800371c4`
- `0x180038338`
- `0x18007e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025bbf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180025bbf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025ce6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180025ce6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025d5e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180025d5e`

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
0x180025a9c  mov     [rsp+arg_10], rbx
0x180025aa1  mov     [rsp+arg_8], edx
0x180025aa5  mov     [rsp+arg_0], rcx
0x180025aaa  push    rbp
0x180025aab  push    rsi
0x180025aac  push    rdi
0x180025aad  push    r12
0x180025aaf  push    r13
0x180025ab1  push    r14
0x180025ab3  push    r15
0x180025ab5  sub     rsp, 40h
0x180025ab9  mov     r12, r9
0x180025abc  mov     r13, r8
0x180025abf  mov     r10, rcx
0x180025ac2  xor     eax, eax
0x180025ac4  mov     rsi, [rsp+78h+lpOutputString]
0x180025acc  mov     [rsi], ax
0x180025acf  mov     rax, [rsp+78h+arg_60]
0x180025ad7  mov     byte ptr [rax], 0
0x180025ada  mov     r14, [rsp+78h+arg_38]
0x180025ae2  mov     edi, [r14]
0x180025ae5  mov     rbx, [rsp+78h+arg_78]
0x180025aed  mov     [rbx+8], edi
0x180025af0  mov     eax, [r14+4]
0x180025af4  mov     [rbx+0Ch], eax
0x180025af7  xor     ebp, ebp
0x180025af9  mov     r15d, [rsp+78h+arg_30]
0x180025b01  mov     ecx, r15d
0x180025b04  test    r15d, r15d
0x180025b07  jz      short loc_180025B6F
0x180025b09  sub     ecx, 1
0x180025b0c  jz      short loc_180025B66
0x180025b0e  sub     ecx, 1
0x180025b11  jz      short loc_180025B21
0x180025b13  cmp     ecx, 1
0x180025b16  jnz     short loc_180025B78
0x180025b18  mov     ecx, edi; this
0x180025b1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180025b1f  jmp     short loc_180025B76
0x180025b21  test    edi, edi
0x180025b23  js      short loc_180025B5D
0x180025b25  mov     edi, 8007029Ch
0x180025b2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180025b2e  mov     rax, [rsp+78h+arg_28]
0x180025b36  mov     [rsp+78h+var_50], rax; __int64
0x180025b3b  mov     rax, [rsp+78h+arg_20]
0x180025b43  mov     [rsp+78h+var_58], rax; __int64
0x180025b48  mov     rcx, r10; int
0x180025b4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180025b50  mov     [rbx+8], edi
0x180025b53  mov     ecx, edi; this
0x180025b55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025b5a  mov     [rbx+0Ch], eax
0x180025b5d  mov     ecx, edi; this
0x180025b5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180025b64  jmp     short loc_180025B76
0x180025b66  mov     ecx, edi; this
0x180025b68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180025b6d  jmp     short loc_180025B76
0x180025b6f  mov     ecx, edi; this
0x180025b71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180025b76  mov     ebp, eax
0x180025b78  mov     [rbx], r15d
0x180025b7b  mov     eax, [rsp+78h+arg_70]
0x180025b82  mov     [rbx+4], eax
0x180025b85  cmp     dword ptr [r14+8], 1
0x180025b8a  jnz     short loc_180025B92
0x180025b8c  or      eax, 8
0x180025b8f  mov     [rbx+4], eax
0x180025b92  mov     eax, 1
0x180025b97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180025b9f  inc     eax
0x180025ba1  mov     [rbx+10h], eax
0x180025ba4  mov     rax, [rsp+78h+arg_40]
0x180025bac  xor     edi, edi
0x180025bae  test    rax, rax
0x180025bb1  jz      short loc_180025BB8
0x180025bb3  cmp     [rax], di
0x180025bb6  jnz     short loc_180025BBB
0x180025bb8  mov     rax, rdi
0x180025bbb  mov     [rbx+18h], rax
0x180025bbf  call    cs:__imp_GetCurrentThreadId
0x180025bc6  nop     dword ptr [rax+rax+00h]
0x180025bcb  mov     [rbx+20h], eax
0x180025bce  mov     [rbx+38h], r13
0x180025bd2  mov     eax, [rsp+78h+arg_8]
0x180025bd9  mov     [rbx+40h], eax
0x180025bdc  mov     [rbx+44h], ebp
0x180025bdf  mov     rax, [rsp+78h+arg_20]
0x180025be7  mov     [rbx+28h], rax
0x180025beb  mov     [rbx+30h], r12
0x180025bef  mov     rax, [rsp+78h+arg_28]
0x180025bf7  mov     [rbx+88h], rax
0x180025bfe  mov     rax, [rsp+78h+arg_0]
0x180025c06  mov     [rbx+90h], rax
0x180025c0d  mov     [rbx+48h], rdi
0x180025c11  xorps   xmm0, xmm0
0x180025c14  xor     eax, eax
0x180025c16  movups  xmmword ptr [rbx+68h], xmm0
0x180025c1a  mov     [rbx+78h], rax
0x180025c1e  movups  xmmword ptr [rbx+50h], xmm0
0x180025c22  mov     [rbx+60h], rax
0x180025c26  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180025c2d  test    rax, rax
0x180025c30  jz      short loc_180025C39
0x180025c32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c37  jmp     short loc_180025C3C
0x180025c39  mov     rax, rdi
0x180025c3c  mov     [rbx+80h], rax
0x180025c43  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180025c4a  test    rax, rax
0x180025c4d  jz      short loc_180025C57
0x180025c4f  mov     rcx, rbx
0x180025c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c57  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180025c5e  test    rax, rax
0x180025c61  jz      short loc_180025C79
0x180025c63  mov     r8d, 400h
0x180025c69  mov     rdx, [rsp+78h+arg_60]
0x180025c71  mov     rcx, rbx
0x180025c74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c79  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025c80  test    rax, rax
0x180025c83  jz      short loc_180025C8D
0x180025c85  mov     rcx, rbx
0x180025c88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025c8d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180025c94  test    rax, rax
0x180025c97  jz      short loc_180025CA7
0x180025c99  test    byte ptr [rbx+4], 2
0x180025c9d  jnz     short loc_180025CA7
0x180025c9f  mov     rcx, rbx
0x180025ca2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ca7  cmp     [rbx+8], edi
0x180025caa  jl      short loc_180025CC8
0x180025cac  cmp     r15d, 3
0x180025cb0  jz      short loc_180025CB8
0x180025cb2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180025cb8  mov     ecx, 8000FFFFh; this
0x180025cbd  mov     [rbx+8], ecx
0x180025cc0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180025cc5  mov     [rbx+0Ch], eax
0x180025cc8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180025ccf  jnz     short loc_180025CF6
0x180025cd1  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180025cd8  test    rax, rax
0x180025cdb  jz      short loc_180025CE6
0x180025cdd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025ce2  test    al, al
0x180025ce4  jmp     short loc_180025CF4
0x180025ce6  call    cs:__imp_IsDebuggerPresent
0x180025ced  nop     dword ptr [rax+rax+00h]
0x180025cf2  test    eax, eax
0x180025cf4  jz      short loc_180025CFC
0x180025cf6  test    byte ptr [rbx+4], 2
0x180025cfa  jz      short loc_180025D20
0x180025cfc  mov     rax, cs:g_pfnResultLoggingCallback
0x180025d03  test    rax, rax
0x180025d06  jz      short loc_180025D6A
0x180025d08  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025d0f  jnz     short loc_180025D6A
0x180025d11  xor     r8d, r8d
0x180025d14  xor     edx, edx
0x180025d16  mov     rcx, rbx
0x180025d19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d1e  jmp     short loc_180025D6A
0x180025d20  mov     ebp, 800h
0x180025d25  mov     rax, cs:g_pfnResultLoggingCallback
0x180025d2c  test    rax, rax
0x180025d2f  jz      short loc_180025D48
0x180025d31  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180025d38  jnz     short loc_180025D48
0x180025d3a  mov     r8d, ebp
0x180025d3d  mov     rdx, rsi
0x180025d40  mov     rcx, rbx
0x180025d43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d48  cmp     [rsi], di
0x180025d4b  jnz     short loc_180025D5B
0x180025d4d  mov     r8, rbx; unsigned __int64
0x180025d50  mov     rdx, rbp; unsigned __int16 *
0x180025d53  mov     rcx, rsi; this
0x180025d56  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180025d5b  mov     rcx, rsi; lpOutputString
0x180025d5e  call    cs:__imp_OutputDebugStringW
0x180025d65  nop     dword ptr [rax+rax+00h]
0x180025d6a  test    byte ptr [rbx+4], 4
0x180025d6e  jnz     short loc_180025D79
0x180025d70  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180025d77  jz      short loc_180025D8B
0x180025d79  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180025d80  test    rax, rax
0x180025d83  jz      short loc_180025D8B
0x180025d85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025d8a  nop
0x180025d8b  mov     rbx, [rsp+78h+arg_10]
0x180025d93  add     rsp, 40h
0x180025d97  pop     r15
0x180025d99  pop     r14
0x180025d9b  pop     r13
0x180025d9d  pop     r12
0x180025d9f  pop     rdi
0x180025da0  pop     rsi
0x180025da1  pop     rbp
0x180025da2  retn
```
