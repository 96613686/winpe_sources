# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001199c`
- end: `0x180011c91`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x180011518`
- `0x180011640`
- `0x18001173c`
- `0x1800210f4`

## callees

- `0x18001199c`
- `0x180012edc`
- `0x1800178e8`
- `0x180022448`
- `0x1800229e8`
- `0x180027800`
- `0x180027814`
- `0x180027830`
- `0x180027d88`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011abf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011be0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011be0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c52`

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
0x18001199c  mov     [rsp+arg_10], rbx
0x1800119a1  mov     [rsp+arg_8], edx
0x1800119a5  mov     [rsp+arg_0], rcx
0x1800119aa  push    rbp
0x1800119ab  push    rsi
0x1800119ac  push    rdi
0x1800119ad  push    r12
0x1800119af  push    r13
0x1800119b1  push    r14
0x1800119b3  push    r15
0x1800119b5  sub     rsp, 40h
0x1800119b9  mov     r12, r9
0x1800119bc  mov     r13, r8
0x1800119bf  mov     r10, rcx
0x1800119c2  xor     eax, eax
0x1800119c4  mov     rsi, [rsp+78h+lpOutputString]
0x1800119cc  mov     [rsi], ax
0x1800119cf  mov     rax, [rsp+78h+arg_60]
0x1800119d7  mov     byte ptr [rax], 0
0x1800119da  mov     r14, [rsp+78h+arg_38]
0x1800119e2  mov     edi, [r14]
0x1800119e5  mov     rbx, [rsp+78h+arg_78]
0x1800119ed  mov     [rbx+8], edi
0x1800119f0  mov     eax, [r14+4]
0x1800119f4  mov     [rbx+0Ch], eax
0x1800119f7  xor     ebp, ebp
0x1800119f9  mov     r15d, [rsp+78h+arg_30]
0x180011a01  mov     ecx, r15d
0x180011a04  test    r15d, r15d
0x180011a07  jz      short loc_180011A6F
0x180011a09  sub     ecx, 1
0x180011a0c  jz      short loc_180011A66
0x180011a0e  sub     ecx, 1
0x180011a11  jz      short loc_180011A21
0x180011a13  cmp     ecx, 1
0x180011a16  jnz     short loc_180011A78
0x180011a18  mov     ecx, edi; this
0x180011a1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011a1f  jmp     short loc_180011A76
0x180011a21  test    edi, edi
0x180011a23  js      short loc_180011A5D
0x180011a25  mov     edi, 8007029Ch
0x180011a2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011a2e  mov     rax, [rsp+78h+arg_28]
0x180011a36  mov     [rsp+78h+var_50], rax; __int64
0x180011a3b  mov     rax, [rsp+78h+arg_20]
0x180011a43  mov     [rsp+78h+var_58], rax; __int64
0x180011a48  mov     rcx, r10; int
0x180011a4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011a50  mov     [rbx+8], edi
0x180011a53  mov     ecx, edi; this
0x180011a55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011a5a  mov     [rbx+0Ch], eax
0x180011a5d  mov     ecx, edi; this
0x180011a5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011a64  jmp     short loc_180011A76
0x180011a66  mov     ecx, edi; this
0x180011a68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011a6d  jmp     short loc_180011A76
0x180011a6f  mov     ecx, edi; this
0x180011a71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011a76  mov     ebp, eax
0x180011a78  mov     [rbx], r15d
0x180011a7b  mov     eax, [rsp+78h+arg_70]
0x180011a82  mov     [rbx+4], eax
0x180011a85  cmp     dword ptr [r14+8], 1
0x180011a8a  jnz     short loc_180011A92
0x180011a8c  or      eax, 8
0x180011a8f  mov     [rbx+4], eax
0x180011a92  mov     eax, 1
0x180011a97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011a9f  inc     eax
0x180011aa1  mov     [rbx+10h], eax
0x180011aa4  mov     rax, [rsp+78h+arg_40]
0x180011aac  xor     edi, edi
0x180011aae  test    rax, rax
0x180011ab1  jz      short loc_180011AB8
0x180011ab3  cmp     [rax], di
0x180011ab6  jnz     short loc_180011ABB
0x180011ab8  mov     rax, rdi
0x180011abb  mov     [rbx+18h], rax
0x180011abf  call    cs:__imp_GetCurrentThreadId
0x180011ac5  mov     [rbx+20h], eax
0x180011ac8  mov     [rbx+38h], r13
0x180011acc  mov     eax, [rsp+78h+arg_8]
0x180011ad3  mov     [rbx+40h], eax
0x180011ad6  mov     [rbx+44h], ebp
0x180011ad9  mov     rax, [rsp+78h+arg_20]
0x180011ae1  mov     [rbx+28h], rax
0x180011ae5  mov     [rbx+30h], r12
0x180011ae9  mov     rax, [rsp+78h+arg_28]
0x180011af1  mov     [rbx+88h], rax
0x180011af8  mov     rax, [rsp+78h+arg_0]
0x180011b00  mov     [rbx+90h], rax
0x180011b07  mov     [rbx+48h], rdi
0x180011b0b  xorps   xmm0, xmm0
0x180011b0e  xor     eax, eax
0x180011b10  movups  xmmword ptr [rbx+68h], xmm0
0x180011b14  mov     [rbx+78h], rax
0x180011b18  movups  xmmword ptr [rbx+50h], xmm0
0x180011b1c  mov     [rbx+60h], rax
0x180011b20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011b27  test    rax, rax
0x180011b2a  jz      short loc_180011B33
0x180011b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b31  jmp     short loc_180011B36
0x180011b33  mov     rax, rdi
0x180011b36  mov     [rbx+80h], rax
0x180011b3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011b44  test    rax, rax
0x180011b47  jz      short loc_180011B51
0x180011b49  mov     rcx, rbx
0x180011b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011b58  test    rax, rax
0x180011b5b  jz      short loc_180011B73
0x180011b5d  mov     r8d, 400h
0x180011b63  mov     rdx, [rsp+78h+arg_60]
0x180011b6b  mov     rcx, rbx
0x180011b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011b7a  test    rax, rax
0x180011b7d  jz      short loc_180011B87
0x180011b7f  mov     rcx, rbx
0x180011b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011b8e  test    rax, rax
0x180011b91  jz      short loc_180011BA1
0x180011b93  test    byte ptr [rbx+4], 2
0x180011b97  jnz     short loc_180011BA1
0x180011b99  mov     rcx, rbx
0x180011b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011ba1  cmp     [rbx+8], edi
0x180011ba4  jl      short loc_180011BC2
0x180011ba6  cmp     r15d, 3
0x180011baa  jz      short loc_180011BB2
0x180011bac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180011bb2  mov     ecx, 8000FFFFh; this
0x180011bb7  mov     [rbx+8], ecx
0x180011bba  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011bbf  mov     [rbx+0Ch], eax
0x180011bc2  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011bc9  jnz     short loc_180011BEA
0x180011bcb  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011bd2  test    rax, rax
0x180011bd5  jz      short loc_180011BE0
0x180011bd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bdc  test    al, al
0x180011bde  jmp     short loc_180011BE8
0x180011be0  call    cs:__imp_IsDebuggerPresent
0x180011be6  test    eax, eax
0x180011be8  jz      short loc_180011BF0
0x180011bea  test    byte ptr [rbx+4], 2
0x180011bee  jz      short loc_180011C14
0x180011bf0  mov     rax, cs:g_pfnResultLoggingCallback
0x180011bf7  test    rax, rax
0x180011bfa  jz      short loc_180011C58
0x180011bfc  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011c03  jnz     short loc_180011C58
0x180011c05  xor     r8d, r8d
0x180011c08  xor     edx, edx
0x180011c0a  mov     rcx, rbx
0x180011c0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c12  jmp     short loc_180011C58
0x180011c14  mov     ebp, 800h
0x180011c19  mov     rax, cs:g_pfnResultLoggingCallback
0x180011c20  test    rax, rax
0x180011c23  jz      short loc_180011C3C
0x180011c25  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011c2c  jnz     short loc_180011C3C
0x180011c2e  mov     r8d, ebp
0x180011c31  mov     rdx, rsi
0x180011c34  mov     rcx, rbx
0x180011c37  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c3c  cmp     [rsi], di
0x180011c3f  jnz     short loc_180011C4F
0x180011c41  mov     r8, rbx; unsigned __int64
0x180011c44  mov     rdx, rbp; unsigned __int16 *
0x180011c47  mov     rcx, rsi; this
0x180011c4a  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011c4f  mov     rcx, rsi; lpOutputString
0x180011c52  call    cs:__imp_OutputDebugStringW
0x180011c58  test    byte ptr [rbx+4], 4
0x180011c5c  jnz     short loc_180011C67
0x180011c5e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011c65  jz      short loc_180011C79
0x180011c67  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011c6e  test    rax, rax
0x180011c71  jz      short loc_180011C79
0x180011c73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c78  nop
0x180011c79  mov     rbx, [rsp+78h+arg_10]
0x180011c81  add     rsp, 40h
0x180011c85  pop     r15
0x180011c87  pop     r14
0x180011c89  pop     r13
0x180011c8b  pop     r12
0x180011c8d  pop     rdi
0x180011c8e  pop     rsi
0x180011c8f  pop     rbp
0x180011c90  retn
```
