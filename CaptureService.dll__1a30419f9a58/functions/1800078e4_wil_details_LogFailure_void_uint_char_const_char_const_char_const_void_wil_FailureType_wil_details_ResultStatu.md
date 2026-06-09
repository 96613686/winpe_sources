# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800078e4`
- end: `0x180007bdd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000486c`
- `0x180004bc0`
- `0x18000cb28`

## callees

- `0x1800047a4`
- `0x180006af4`
- `0x18000740c`
- `0x1800078e4`
- `0x180008674`
- `0x180008690`
- `0x180008814`
- `0x180008830`
- `0x18000a900`
- `0x180022010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a07`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a07`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b26`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b98`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b98`

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
0x1800078e4  mov     [rsp+arg_10], rbx
0x1800078e9  mov     [rsp+arg_8], edx
0x1800078ed  mov     [rsp+arg_0], rcx
0x1800078f2  push    rbp
0x1800078f3  push    rsi
0x1800078f4  push    rdi
0x1800078f5  push    r12
0x1800078f7  push    r13
0x1800078f9  push    r14
0x1800078fb  push    r15
0x1800078fd  sub     rsp, 40h
0x180007901  mov     r12, r9
0x180007904  mov     r13, r8
0x180007907  mov     r10, rcx
0x18000790a  xor     eax, eax
0x18000790c  mov     rsi, [rsp+78h+lpOutputString]
0x180007914  mov     [rsi], ax
0x180007917  mov     rax, [rsp+78h+arg_60]
0x18000791f  mov     byte ptr [rax], 0
0x180007922  mov     r14, [rsp+78h+arg_38]
0x18000792a  mov     edi, [r14]
0x18000792d  mov     rbx, [rsp+78h+arg_78]
0x180007935  mov     [rbx+8], edi
0x180007938  mov     eax, [r14+4]
0x18000793c  mov     [rbx+0Ch], eax
0x18000793f  xor     ebp, ebp
0x180007941  mov     r15d, [rsp+78h+arg_30]
0x180007949  mov     ecx, r15d
0x18000794c  test    r15d, r15d
0x18000794f  jz      short loc_1800079B7
0x180007951  sub     ecx, 1
0x180007954  jz      short loc_1800079AE
0x180007956  sub     ecx, 1
0x180007959  jz      short loc_180007969
0x18000795b  cmp     ecx, 1
0x18000795e  jnz     short loc_1800079C0
0x180007960  mov     ecx, edi; this
0x180007962  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007967  jmp     short loc_1800079BE
0x180007969  test    edi, edi
0x18000796b  js      short loc_1800079A5
0x18000796d  mov     edi, 8007029Ch
0x180007972  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007976  mov     rax, [rsp+78h+arg_28]
0x18000797e  mov     [rsp+78h+var_50], rax; __int64
0x180007983  mov     rax, [rsp+78h+arg_20]
0x18000798b  mov     [rsp+78h+var_58], rax; __int64
0x180007990  mov     rcx, r10; int
0x180007993  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007998  mov     [rbx+8], edi
0x18000799b  mov     ecx, edi; this
0x18000799d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800079a2  mov     [rbx+0Ch], eax
0x1800079a5  mov     ecx, edi; this
0x1800079a7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800079ac  jmp     short loc_1800079BE
0x1800079ae  mov     ecx, edi; this
0x1800079b0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800079b5  jmp     short loc_1800079BE
0x1800079b7  mov     ecx, edi; this
0x1800079b9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800079be  mov     ebp, eax
0x1800079c0  mov     [rbx], r15d
0x1800079c3  mov     eax, [rsp+78h+arg_70]
0x1800079ca  mov     [rbx+4], eax
0x1800079cd  cmp     dword ptr [r14+8], 1
0x1800079d2  jnz     short loc_1800079DA
0x1800079d4  or      eax, 8
0x1800079d7  mov     [rbx+4], eax
0x1800079da  mov     eax, 1
0x1800079df  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800079e7  inc     eax
0x1800079e9  mov     [rbx+10h], eax
0x1800079ec  mov     rax, [rsp+78h+arg_40]
0x1800079f4  xor     edi, edi
0x1800079f6  test    rax, rax
0x1800079f9  jz      short loc_180007A00
0x1800079fb  cmp     [rax], di
0x1800079fe  jnz     short loc_180007A03
0x180007a00  mov     rax, rdi
0x180007a03  mov     [rbx+18h], rax
0x180007a07  call    cs:__imp_GetCurrentThreadId
0x180007a0d  mov     [rbx+20h], eax
0x180007a10  mov     [rbx+38h], r13
0x180007a14  mov     eax, [rsp+78h+arg_8]
0x180007a1b  mov     [rbx+40h], eax
0x180007a1e  mov     [rbx+44h], ebp
0x180007a21  mov     rax, [rsp+78h+arg_20]
0x180007a29  mov     [rbx+28h], rax
0x180007a2d  mov     [rbx+30h], r12
0x180007a31  mov     rax, [rsp+78h+arg_28]
0x180007a39  mov     [rbx+88h], rax
0x180007a40  mov     rax, [rsp+78h+arg_0]
0x180007a48  mov     [rbx+90h], rax
0x180007a4f  mov     [rbx+48h], rdi
0x180007a53  xorps   xmm0, xmm0
0x180007a56  xor     eax, eax
0x180007a58  movups  xmmword ptr [rbx+68h], xmm0
0x180007a5c  mov     [rbx+78h], rax
0x180007a60  movups  xmmword ptr [rbx+50h], xmm0
0x180007a64  mov     [rbx+60h], rax
0x180007a68  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007a6f  test    rax, rax
0x180007a72  jz      short loc_180007A7B
0x180007a74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a79  jmp     short loc_180007A7E
0x180007a7b  mov     rax, rdi
0x180007a7e  mov     [rbx+80h], rax
0x180007a85  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007a8c  test    rax, rax
0x180007a8f  jz      short loc_180007A99
0x180007a91  mov     rcx, rbx
0x180007a94  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a99  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007aa0  test    rax, rax
0x180007aa3  jz      short loc_180007ABB
0x180007aa5  mov     r8d, 400h
0x180007aab  mov     rdx, [rsp+78h+arg_60]
0x180007ab3  mov     rcx, rbx
0x180007ab6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007abb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ac2  test    rax, rax
0x180007ac5  jz      short loc_180007ACF
0x180007ac7  mov     rcx, rbx
0x180007aca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007acf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007ad6  test    rax, rax
0x180007ad9  jz      short loc_180007AE9
0x180007adb  test    byte ptr [rbx+4], 2
0x180007adf  jnz     short loc_180007AE9
0x180007ae1  mov     rcx, rbx
0x180007ae4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ae9  cmp     [rbx+8], edi
0x180007aec  jl      short loc_180007B08
0x180007aee  cmp     r15d, 3
0x180007af2  jnz     loc_180007BD7
0x180007af8  mov     ecx, 8000FFFFh; this
0x180007afd  mov     [rbx+8], ecx
0x180007b00  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b05  mov     [rbx+0Ch], eax
0x180007b08  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007b0f  jnz     short loc_180007B30
0x180007b11  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b18  test    rax, rax
0x180007b1b  jz      short loc_180007B26
0x180007b1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b22  test    al, al
0x180007b24  jmp     short loc_180007B2E
0x180007b26  call    cs:__imp_IsDebuggerPresent
0x180007b2c  test    eax, eax
0x180007b2e  jz      short loc_180007B36
0x180007b30  test    byte ptr [rbx+4], 2
0x180007b34  jz      short loc_180007B5A
0x180007b36  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b3d  test    rax, rax
0x180007b40  jz      short loc_180007B9E
0x180007b42  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b49  jnz     short loc_180007B9E
0x180007b4b  xor     r8d, r8d
0x180007b4e  xor     edx, edx
0x180007b50  mov     rcx, rbx
0x180007b53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b58  jmp     short loc_180007B9E
0x180007b5a  mov     ebp, 800h
0x180007b5f  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b66  test    rax, rax
0x180007b69  jz      short loc_180007B82
0x180007b6b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b72  jnz     short loc_180007B82
0x180007b74  mov     r8d, ebp
0x180007b77  mov     rdx, rsi
0x180007b7a  mov     rcx, rbx
0x180007b7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b82  cmp     [rsi], di
0x180007b85  jnz     short loc_180007B95
0x180007b87  mov     r8, rbx; unsigned __int64
0x180007b8a  mov     rdx, rbp; unsigned __int16 *
0x180007b8d  mov     rcx, rsi; this
0x180007b90  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007b95  mov     rcx, rsi; lpOutputString
0x180007b98  call    cs:__imp_OutputDebugStringW
0x180007b9e  test    byte ptr [rbx+4], 4
0x180007ba2  jnz     short loc_180007BAD
0x180007ba4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007bab  jz      short loc_180007BBF
0x180007bad  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007bb4  test    rax, rax
0x180007bb7  jz      short loc_180007BBF
0x180007bb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bbe  nop
0x180007bbf  mov     rbx, [rsp+78h+arg_10]
0x180007bc7  add     rsp, 40h
0x180007bcb  pop     r15
0x180007bcd  pop     r14
0x180007bcf  pop     r13
0x180007bd1  pop     r12
0x180007bd3  pop     rdi
0x180007bd4  pop     rsi
0x180007bd5  pop     rbp
0x180007bd6  retn
0x180007bd7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
