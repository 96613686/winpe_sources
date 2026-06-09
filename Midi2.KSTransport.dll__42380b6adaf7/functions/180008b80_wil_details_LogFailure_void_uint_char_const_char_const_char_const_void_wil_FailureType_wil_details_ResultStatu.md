# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008b80`
- end: `0x180008e79`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005d10`

## callees

- `0x180005754`
- `0x180008094`
- `0x180008850`
- `0x180008b80`
- `0x180009758`
- `0x180009780`
- `0x180009794`
- `0x1800097b0`
- `0x18000baf4`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ca3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008ca3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008e34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180008e34`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008dc2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180008dc2`

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
0x180008b80  mov     [rsp+arg_10], rbx
0x180008b85  mov     [rsp+arg_8], edx
0x180008b89  mov     [rsp+arg_0], rcx
0x180008b8e  push    rbp
0x180008b8f  push    rsi
0x180008b90  push    rdi
0x180008b91  push    r12
0x180008b93  push    r13
0x180008b95  push    r14
0x180008b97  push    r15
0x180008b99  sub     rsp, 40h
0x180008b9d  mov     r12, r9
0x180008ba0  mov     r13, r8
0x180008ba3  mov     r10, rcx
0x180008ba6  xor     eax, eax
0x180008ba8  mov     rsi, [rsp+78h+lpOutputString]
0x180008bb0  mov     [rsi], ax
0x180008bb3  mov     rax, [rsp+78h+arg_60]
0x180008bbb  mov     byte ptr [rax], 0
0x180008bbe  mov     r14, [rsp+78h+arg_38]
0x180008bc6  mov     edi, [r14]
0x180008bc9  mov     rbx, [rsp+78h+arg_78]
0x180008bd1  mov     [rbx+8], edi
0x180008bd4  mov     eax, [r14+4]
0x180008bd8  mov     [rbx+0Ch], eax
0x180008bdb  xor     ebp, ebp
0x180008bdd  mov     r15d, [rsp+78h+arg_30]
0x180008be5  mov     ecx, r15d
0x180008be8  test    r15d, r15d
0x180008beb  jz      short loc_180008C53
0x180008bed  sub     ecx, 1
0x180008bf0  jz      short loc_180008C4A
0x180008bf2  sub     ecx, 1
0x180008bf5  jz      short loc_180008C05
0x180008bf7  cmp     ecx, 1
0x180008bfa  jnz     short loc_180008C5C
0x180008bfc  mov     ecx, edi; this
0x180008bfe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008c03  jmp     short loc_180008C5A
0x180008c05  test    edi, edi
0x180008c07  js      short loc_180008C41
0x180008c09  mov     edi, 8007029Ch
0x180008c0e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008c12  mov     rax, [rsp+78h+arg_28]
0x180008c1a  mov     [rsp+78h+var_50], rax; __int64
0x180008c1f  mov     rax, [rsp+78h+arg_20]
0x180008c27  mov     [rsp+78h+var_58], rax; __int64
0x180008c2c  mov     rcx, r10; int
0x180008c2f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008c34  mov     [rbx+8], edi
0x180008c37  mov     ecx, edi; this
0x180008c39  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008c3e  mov     [rbx+0Ch], eax
0x180008c41  mov     ecx, edi; this
0x180008c43  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008c48  jmp     short loc_180008C5A
0x180008c4a  mov     ecx, edi; this
0x180008c4c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008c51  jmp     short loc_180008C5A
0x180008c53  mov     ecx, edi; this
0x180008c55  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008c5a  mov     ebp, eax
0x180008c5c  mov     [rbx], r15d
0x180008c5f  mov     eax, [rsp+78h+arg_70]
0x180008c66  mov     [rbx+4], eax
0x180008c69  cmp     dword ptr [r14+8], 1
0x180008c6e  jnz     short loc_180008C76
0x180008c70  or      eax, 8
0x180008c73  mov     [rbx+4], eax
0x180008c76  mov     eax, 1
0x180008c7b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008c83  inc     eax
0x180008c85  mov     [rbx+10h], eax
0x180008c88  mov     rax, [rsp+78h+arg_40]
0x180008c90  xor     edi, edi
0x180008c92  test    rax, rax
0x180008c95  jz      short loc_180008C9C
0x180008c97  cmp     [rax], di
0x180008c9a  jnz     short loc_180008C9F
0x180008c9c  mov     rax, rdi
0x180008c9f  mov     [rbx+18h], rax
0x180008ca3  call    cs:__imp_GetCurrentThreadId
0x180008ca9  mov     [rbx+20h], eax
0x180008cac  mov     [rbx+38h], r13
0x180008cb0  mov     eax, [rsp+78h+arg_8]
0x180008cb7  mov     [rbx+40h], eax
0x180008cba  mov     [rbx+44h], ebp
0x180008cbd  mov     rax, [rsp+78h+arg_20]
0x180008cc5  mov     [rbx+28h], rax
0x180008cc9  mov     [rbx+30h], r12
0x180008ccd  mov     rax, [rsp+78h+arg_28]
0x180008cd5  mov     [rbx+88h], rax
0x180008cdc  mov     rax, [rsp+78h+arg_0]
0x180008ce4  mov     [rbx+90h], rax
0x180008ceb  mov     [rbx+48h], rdi
0x180008cef  xorps   xmm0, xmm0
0x180008cf2  xor     eax, eax
0x180008cf4  movups  xmmword ptr [rbx+68h], xmm0
0x180008cf8  mov     [rbx+78h], rax
0x180008cfc  movups  xmmword ptr [rbx+50h], xmm0
0x180008d00  mov     [rbx+60h], rax
0x180008d04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008d0b  test    rax, rax
0x180008d0e  jz      short loc_180008D17
0x180008d10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d15  jmp     short loc_180008D1A
0x180008d17  mov     rax, rdi
0x180008d1a  mov     [rbx+80h], rax
0x180008d21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008d28  test    rax, rax
0x180008d2b  jz      short loc_180008D35
0x180008d2d  mov     rcx, rbx
0x180008d30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008d3c  test    rax, rax
0x180008d3f  jz      short loc_180008D57
0x180008d41  mov     r8d, 400h
0x180008d47  mov     rdx, [rsp+78h+arg_60]
0x180008d4f  mov     rcx, rbx
0x180008d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d5e  test    rax, rax
0x180008d61  jz      short loc_180008D6B
0x180008d63  mov     rcx, rbx
0x180008d66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008d72  test    rax, rax
0x180008d75  jz      short loc_180008D85
0x180008d77  test    byte ptr [rbx+4], 2
0x180008d7b  jnz     short loc_180008D85
0x180008d7d  mov     rcx, rbx
0x180008d80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d85  cmp     [rbx+8], edi
0x180008d88  jl      short loc_180008DA4
0x180008d8a  cmp     r15d, 3
0x180008d8e  jnz     loc_180008E73
0x180008d94  mov     ecx, 8000FFFFh; this
0x180008d99  mov     [rbx+8], ecx
0x180008d9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008da1  mov     [rbx+0Ch], eax
0x180008da4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180008dab  jnz     short loc_180008DCC
0x180008dad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180008db4  test    rax, rax
0x180008db7  jz      short loc_180008DC2
0x180008db9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008dbe  test    al, al
0x180008dc0  jmp     short loc_180008DCA
0x180008dc2  call    cs:__imp_IsDebuggerPresent
0x180008dc8  test    eax, eax
0x180008dca  jz      short loc_180008DD2
0x180008dcc  test    byte ptr [rbx+4], 2
0x180008dd0  jz      short loc_180008DF6
0x180008dd2  mov     rax, cs:g_pfnResultLoggingCallback
0x180008dd9  test    rax, rax
0x180008ddc  jz      short loc_180008E3A
0x180008dde  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008de5  jnz     short loc_180008E3A
0x180008de7  xor     r8d, r8d
0x180008dea  xor     edx, edx
0x180008dec  mov     rcx, rbx
0x180008def  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008df4  jmp     short loc_180008E3A
0x180008df6  mov     ebp, 800h
0x180008dfb  mov     rax, cs:g_pfnResultLoggingCallback
0x180008e02  test    rax, rax
0x180008e05  jz      short loc_180008E1E
0x180008e07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008e0e  jnz     short loc_180008E1E
0x180008e10  mov     r8d, ebp
0x180008e13  mov     rdx, rsi
0x180008e16  mov     rcx, rbx
0x180008e19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e1e  cmp     [rsi], di
0x180008e21  jnz     short loc_180008E31
0x180008e23  mov     r8, rbx; unsigned __int64
0x180008e26  mov     rdx, rbp; unsigned __int16 *
0x180008e29  mov     rcx, rsi; this
0x180008e2c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008e31  mov     rcx, rsi; lpOutputString
0x180008e34  call    cs:__imp_OutputDebugStringW
0x180008e3a  test    byte ptr [rbx+4], 4
0x180008e3e  jnz     short loc_180008E49
0x180008e40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180008e47  jz      short loc_180008E5B
0x180008e49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008e50  test    rax, rax
0x180008e53  jz      short loc_180008E5B
0x180008e55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e5a  nop
0x180008e5b  mov     rbx, [rsp+78h+arg_10]
0x180008e63  add     rsp, 40h
0x180008e67  pop     r15
0x180008e69  pop     r14
0x180008e6b  pop     r13
0x180008e6d  pop     r12
0x180008e6f  pop     rdi
0x180008e70  pop     rsi
0x180008e71  pop     rbp
0x180008e72  retn
0x180008e73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
