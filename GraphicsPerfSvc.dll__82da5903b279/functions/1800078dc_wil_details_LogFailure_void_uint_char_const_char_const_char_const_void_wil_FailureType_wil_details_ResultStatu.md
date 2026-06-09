# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800078dc`
- end: `0x180007bd5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800050ac`
- `0x180005418`
- `0x180015de4`

## callees

- `0x180004fe0`
- `0x180006c14`
- `0x1800074c8`
- `0x1800078dc`
- `0x1800087b0`
- `0x1800087d0`
- `0x180008920`
- `0x18000893c`
- `0x18000a720`
- `0x180031010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079ff`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800079ff`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b1e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b1e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b90`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b90`

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
0x1800078dc  mov     [rsp+arg_10], rbx
0x1800078e1  mov     [rsp+arg_8], edx
0x1800078e5  mov     [rsp+arg_0], rcx
0x1800078ea  push    rbp
0x1800078eb  push    rsi
0x1800078ec  push    rdi
0x1800078ed  push    r12
0x1800078ef  push    r13
0x1800078f1  push    r14
0x1800078f3  push    r15
0x1800078f5  sub     rsp, 40h
0x1800078f9  mov     r12, r9
0x1800078fc  mov     r13, r8
0x1800078ff  mov     r10, rcx
0x180007902  xor     eax, eax
0x180007904  mov     rsi, [rsp+78h+lpOutputString]
0x18000790c  mov     [rsi], ax
0x18000790f  mov     rax, [rsp+78h+arg_60]
0x180007917  mov     byte ptr [rax], 0
0x18000791a  mov     r14, [rsp+78h+arg_38]
0x180007922  mov     edi, [r14]
0x180007925  mov     rbx, [rsp+78h+arg_78]
0x18000792d  mov     [rbx+8], edi
0x180007930  mov     eax, [r14+4]
0x180007934  mov     [rbx+0Ch], eax
0x180007937  xor     ebp, ebp
0x180007939  mov     r15d, [rsp+78h+arg_30]
0x180007941  mov     ecx, r15d
0x180007944  test    r15d, r15d
0x180007947  jz      short loc_1800079AF
0x180007949  sub     ecx, 1
0x18000794c  jz      short loc_1800079A6
0x18000794e  sub     ecx, 1
0x180007951  jz      short loc_180007961
0x180007953  cmp     ecx, 1
0x180007956  jnz     short loc_1800079B8
0x180007958  mov     ecx, edi; this
0x18000795a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000795f  jmp     short loc_1800079B6
0x180007961  test    edi, edi
0x180007963  js      short loc_18000799D
0x180007965  mov     edi, 8007029Ch
0x18000796a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000796e  mov     rax, [rsp+78h+arg_28]
0x180007976  mov     [rsp+78h+var_50], rax; __int64
0x18000797b  mov     rax, [rsp+78h+arg_20]
0x180007983  mov     [rsp+78h+var_58], rax; __int64
0x180007988  mov     rcx, r10; int
0x18000798b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007990  mov     [rbx+8], edi
0x180007993  mov     ecx, edi; this
0x180007995  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000799a  mov     [rbx+0Ch], eax
0x18000799d  mov     ecx, edi; this
0x18000799f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800079a4  jmp     short loc_1800079B6
0x1800079a6  mov     ecx, edi; this
0x1800079a8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800079ad  jmp     short loc_1800079B6
0x1800079af  mov     ecx, edi; this
0x1800079b1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800079b6  mov     ebp, eax
0x1800079b8  mov     [rbx], r15d
0x1800079bb  mov     eax, [rsp+78h+arg_70]
0x1800079c2  mov     [rbx+4], eax
0x1800079c5  cmp     dword ptr [r14+8], 1
0x1800079ca  jnz     short loc_1800079D2
0x1800079cc  or      eax, 8
0x1800079cf  mov     [rbx+4], eax
0x1800079d2  mov     eax, 1
0x1800079d7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800079df  inc     eax
0x1800079e1  mov     [rbx+10h], eax
0x1800079e4  mov     rax, [rsp+78h+arg_40]
0x1800079ec  xor     edi, edi
0x1800079ee  test    rax, rax
0x1800079f1  jz      short loc_1800079F8
0x1800079f3  cmp     [rax], di
0x1800079f6  jnz     short loc_1800079FB
0x1800079f8  mov     rax, rdi
0x1800079fb  mov     [rbx+18h], rax
0x1800079ff  call    cs:__imp_GetCurrentThreadId
0x180007a05  mov     [rbx+20h], eax
0x180007a08  mov     [rbx+38h], r13
0x180007a0c  mov     eax, [rsp+78h+arg_8]
0x180007a13  mov     [rbx+40h], eax
0x180007a16  mov     [rbx+44h], ebp
0x180007a19  mov     rax, [rsp+78h+arg_20]
0x180007a21  mov     [rbx+28h], rax
0x180007a25  mov     [rbx+30h], r12
0x180007a29  mov     rax, [rsp+78h+arg_28]
0x180007a31  mov     [rbx+88h], rax
0x180007a38  mov     rax, [rsp+78h+arg_0]
0x180007a40  mov     [rbx+90h], rax
0x180007a47  mov     [rbx+48h], rdi
0x180007a4b  xorps   xmm0, xmm0
0x180007a4e  xor     eax, eax
0x180007a50  movups  xmmword ptr [rbx+68h], xmm0
0x180007a54  mov     [rbx+78h], rax
0x180007a58  movups  xmmword ptr [rbx+50h], xmm0
0x180007a5c  mov     [rbx+60h], rax
0x180007a60  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a67  test    rax, rax
0x180007a6a  jz      short loc_180007A73
0x180007a6c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a71  jmp     short loc_180007A76
0x180007a73  mov     rax, rdi
0x180007a76  mov     [rbx+80h], rax
0x180007a7d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007a84  test    rax, rax
0x180007a87  jz      short loc_180007A91
0x180007a89  mov     rcx, rbx
0x180007a8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a91  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007a98  test    rax, rax
0x180007a9b  jz      short loc_180007AB3
0x180007a9d  mov     r8d, 400h
0x180007aa3  mov     rdx, [rsp+78h+arg_60]
0x180007aab  mov     rcx, rbx
0x180007aae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ab3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007aba  test    rax, rax
0x180007abd  jz      short loc_180007AC7
0x180007abf  mov     rcx, rbx
0x180007ac2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ac7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ace  test    rax, rax
0x180007ad1  jz      short loc_180007AE1
0x180007ad3  test    byte ptr [rbx+4], 2
0x180007ad7  jnz     short loc_180007AE1
0x180007ad9  mov     rcx, rbx
0x180007adc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae1  cmp     [rbx+8], edi
0x180007ae4  jl      short loc_180007B00
0x180007ae6  cmp     r15d, 3
0x180007aea  jnz     loc_180007BCF
0x180007af0  mov     ecx, 8000FFFFh; this
0x180007af5  mov     [rbx+8], ecx
0x180007af8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007afd  mov     [rbx+0Ch], eax
0x180007b00  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007b07  jnz     short loc_180007B28
0x180007b09  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b10  test    rax, rax
0x180007b13  jz      short loc_180007B1E
0x180007b15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1a  test    al, al
0x180007b1c  jmp     short loc_180007B26
0x180007b1e  call    cs:__imp_IsDebuggerPresent
0x180007b24  test    eax, eax
0x180007b26  jz      short loc_180007B2E
0x180007b28  test    byte ptr [rbx+4], 2
0x180007b2c  jz      short loc_180007B52
0x180007b2e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b35  test    rax, rax
0x180007b38  jz      short loc_180007B96
0x180007b3a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b41  jnz     short loc_180007B96
0x180007b43  xor     r8d, r8d
0x180007b46  xor     edx, edx
0x180007b48  mov     rcx, rbx
0x180007b4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b50  jmp     short loc_180007B96
0x180007b52  mov     ebp, 800h
0x180007b57  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b5e  test    rax, rax
0x180007b61  jz      short loc_180007B7A
0x180007b63  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b6a  jnz     short loc_180007B7A
0x180007b6c  mov     r8d, ebp
0x180007b6f  mov     rdx, rsi
0x180007b72  mov     rcx, rbx
0x180007b75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b7a  cmp     [rsi], di
0x180007b7d  jnz     short loc_180007B8D
0x180007b7f  mov     r8, rbx; unsigned __int64
0x180007b82  mov     rdx, rbp; unsigned __int16 *
0x180007b85  mov     rcx, rsi; this
0x180007b88  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007b8d  mov     rcx, rsi; lpOutputString
0x180007b90  call    cs:__imp_OutputDebugStringW
0x180007b96  test    byte ptr [rbx+4], 4
0x180007b9a  jnz     short loc_180007BA5
0x180007b9c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007ba3  jz      short loc_180007BB7
0x180007ba5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007bac  test    rax, rax
0x180007baf  jz      short loc_180007BB7
0x180007bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb6  nop
0x180007bb7  mov     rbx, [rsp+78h+arg_10]
0x180007bbf  add     rsp, 40h
0x180007bc3  pop     r15
0x180007bc5  pop     r14
0x180007bc7  pop     r13
0x180007bc9  pop     r12
0x180007bcb  pop     rdi
0x180007bcc  pop     rsi
0x180007bcd  pop     rbp
0x180007bce  retn
0x180007bcf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
