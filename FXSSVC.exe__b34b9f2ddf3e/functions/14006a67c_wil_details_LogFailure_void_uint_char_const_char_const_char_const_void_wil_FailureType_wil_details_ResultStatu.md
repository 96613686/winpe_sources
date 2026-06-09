# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14006a67c`
- end: `0x14006a975`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140067c14`

## callees

- `0x140067650`
- `0x140069a44`
- `0x14006a1e0`
- `0x14006a67c`
- `0x14006b068`
- `0x14006b090`
- `0x14006b1bc`
- `0x14006b1d8`
- `0x14006d33c`
- `0x140085010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x14006a8be`
- `KERNEL32!IsDebuggerPresent` at `0x14006a8be`
- `KERNEL32!OutputDebugStringW` at `0x14006a930`
- `KERNEL32!OutputDebugStringW` at `0x14006a930`
- `KERNEL32!GetCurrentThreadId` at `0x14006a79f`
- `KERNEL32!GetCurrentThreadId` at `0x14006a79f`

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
0x14006a67c  mov     [rsp+arg_10], rbx
0x14006a681  mov     [rsp+arg_8], edx
0x14006a685  mov     [rsp+arg_0], rcx
0x14006a68a  push    rbp
0x14006a68b  push    rsi
0x14006a68c  push    rdi
0x14006a68d  push    r12
0x14006a68f  push    r13
0x14006a691  push    r14
0x14006a693  push    r15
0x14006a695  sub     rsp, 40h
0x14006a699  mov     r12, r9
0x14006a69c  mov     r13, r8
0x14006a69f  mov     r10, rcx
0x14006a6a2  xor     eax, eax
0x14006a6a4  mov     rsi, [rsp+78h+lpOutputString]
0x14006a6ac  mov     [rsi], ax
0x14006a6af  mov     rax, [rsp+78h+arg_60]
0x14006a6b7  mov     byte ptr [rax], 0
0x14006a6ba  mov     r14, [rsp+78h+arg_38]
0x14006a6c2  mov     edi, [r14]
0x14006a6c5  mov     rbx, [rsp+78h+arg_78]
0x14006a6cd  mov     [rbx+8], edi
0x14006a6d0  mov     eax, [r14+4]
0x14006a6d4  mov     [rbx+0Ch], eax
0x14006a6d7  xor     ebp, ebp
0x14006a6d9  mov     r15d, [rsp+78h+arg_30]
0x14006a6e1  mov     ecx, r15d
0x14006a6e4  test    r15d, r15d
0x14006a6e7  jz      short loc_14006A74F
0x14006a6e9  sub     ecx, 1
0x14006a6ec  jz      short loc_14006A746
0x14006a6ee  sub     ecx, 1
0x14006a6f1  jz      short loc_14006A701
0x14006a6f3  cmp     ecx, 1
0x14006a6f6  jnz     short loc_14006A758
0x14006a6f8  mov     ecx, edi; this
0x14006a6fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14006a6ff  jmp     short loc_14006A756
0x14006a701  test    edi, edi
0x14006a703  js      short loc_14006A73D
0x14006a705  mov     edi, 8007029Ch
0x14006a70a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14006a70e  mov     rax, [rsp+78h+arg_28]
0x14006a716  mov     [rsp+78h+var_50], rax; __int64
0x14006a71b  mov     rax, [rsp+78h+arg_20]
0x14006a723  mov     [rsp+78h+var_58], rax; __int64
0x14006a728  mov     rcx, r10; int
0x14006a72b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14006a730  mov     [rbx+8], edi
0x14006a733  mov     ecx, edi; this
0x14006a735  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14006a73a  mov     [rbx+0Ch], eax
0x14006a73d  mov     ecx, edi; this
0x14006a73f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14006a744  jmp     short loc_14006A756
0x14006a746  mov     ecx, edi; this
0x14006a748  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14006a74d  jmp     short loc_14006A756
0x14006a74f  mov     ecx, edi; this
0x14006a751  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14006a756  mov     ebp, eax
0x14006a758  mov     [rbx], r15d
0x14006a75b  mov     eax, [rsp+78h+arg_70]
0x14006a762  mov     [rbx+4], eax
0x14006a765  cmp     dword ptr [r14+8], 1
0x14006a76a  jnz     short loc_14006A772
0x14006a76c  or      eax, 8
0x14006a76f  mov     [rbx+4], eax
0x14006a772  mov     eax, 1
0x14006a777  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14006a77f  inc     eax
0x14006a781  mov     [rbx+10h], eax
0x14006a784  mov     rax, [rsp+78h+arg_40]
0x14006a78c  xor     edi, edi
0x14006a78e  test    rax, rax
0x14006a791  jz      short loc_14006A798
0x14006a793  cmp     [rax], di
0x14006a796  jnz     short loc_14006A79B
0x14006a798  mov     rax, rdi
0x14006a79b  mov     [rbx+18h], rax
0x14006a79f  call    cs:__imp_GetCurrentThreadId
0x14006a7a5  mov     [rbx+20h], eax
0x14006a7a8  mov     [rbx+38h], r13
0x14006a7ac  mov     eax, [rsp+78h+arg_8]
0x14006a7b3  mov     [rbx+40h], eax
0x14006a7b6  mov     [rbx+44h], ebp
0x14006a7b9  mov     rax, [rsp+78h+arg_20]
0x14006a7c1  mov     [rbx+28h], rax
0x14006a7c5  mov     [rbx+30h], r12
0x14006a7c9  mov     rax, [rsp+78h+arg_28]
0x14006a7d1  mov     [rbx+88h], rax
0x14006a7d8  mov     rax, [rsp+78h+arg_0]
0x14006a7e0  mov     [rbx+90h], rax
0x14006a7e7  mov     [rbx+48h], rdi
0x14006a7eb  xorps   xmm0, xmm0
0x14006a7ee  xor     eax, eax
0x14006a7f0  movups  xmmword ptr [rbx+68h], xmm0
0x14006a7f4  mov     [rbx+78h], rax
0x14006a7f8  movups  xmmword ptr [rbx+50h], xmm0
0x14006a7fc  mov     [rbx+60h], rax
0x14006a800  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14006a807  test    rax, rax
0x14006a80a  jz      short loc_14006A813
0x14006a80c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a811  jmp     short loc_14006A816
0x14006a813  mov     rax, rdi
0x14006a816  mov     [rbx+80h], rax
0x14006a81d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14006a824  test    rax, rax
0x14006a827  jz      short loc_14006A831
0x14006a829  mov     rcx, rbx
0x14006a82c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a831  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14006a838  test    rax, rax
0x14006a83b  jz      short loc_14006A853
0x14006a83d  mov     r8d, 400h
0x14006a843  mov     rdx, [rsp+78h+arg_60]
0x14006a84b  mov     rcx, rbx
0x14006a84e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a853  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006a85a  test    rax, rax
0x14006a85d  jz      short loc_14006A867
0x14006a85f  mov     rcx, rbx
0x14006a862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a867  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14006a86e  test    rax, rax
0x14006a871  jz      short loc_14006A881
0x14006a873  test    byte ptr [rbx+4], 2
0x14006a877  jnz     short loc_14006A881
0x14006a879  mov     rcx, rbx
0x14006a87c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a881  cmp     [rbx+8], edi
0x14006a884  jl      short loc_14006A8A0
0x14006a886  cmp     r15d, 3
0x14006a88a  jnz     loc_14006A96F
0x14006a890  mov     ecx, 8000FFFFh; this
0x14006a895  mov     [rbx+8], ecx
0x14006a898  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14006a89d  mov     [rbx+0Ch], eax
0x14006a8a0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14006a8a7  jnz     short loc_14006A8C8
0x14006a8a9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14006a8b0  test    rax, rax
0x14006a8b3  jz      short loc_14006A8BE
0x14006a8b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a8ba  test    al, al
0x14006a8bc  jmp     short loc_14006A8C6
0x14006a8be  call    cs:__imp_IsDebuggerPresent
0x14006a8c4  test    eax, eax
0x14006a8c6  jz      short loc_14006A8CE
0x14006a8c8  test    byte ptr [rbx+4], 2
0x14006a8cc  jz      short loc_14006A8F2
0x14006a8ce  mov     rax, cs:g_pfnResultLoggingCallback
0x14006a8d5  test    rax, rax
0x14006a8d8  jz      short loc_14006A936
0x14006a8da  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14006a8e1  jnz     short loc_14006A936
0x14006a8e3  xor     r8d, r8d
0x14006a8e6  xor     edx, edx
0x14006a8e8  mov     rcx, rbx
0x14006a8eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a8f0  jmp     short loc_14006A936
0x14006a8f2  mov     ebp, 800h
0x14006a8f7  mov     rax, cs:g_pfnResultLoggingCallback
0x14006a8fe  test    rax, rax
0x14006a901  jz      short loc_14006A91A
0x14006a903  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14006a90a  jnz     short loc_14006A91A
0x14006a90c  mov     r8d, ebp
0x14006a90f  mov     rdx, rsi
0x14006a912  mov     rcx, rbx
0x14006a915  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a91a  cmp     [rsi], di
0x14006a91d  jnz     short loc_14006A92D
0x14006a91f  mov     r8, rbx; unsigned __int64
0x14006a922  mov     rdx, rbp; unsigned __int16 *
0x14006a925  mov     rcx, rsi; this
0x14006a928  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14006a92d  mov     rcx, rsi; lpOutputString
0x14006a930  call    cs:__imp_OutputDebugStringW
0x14006a936  test    byte ptr [rbx+4], 4
0x14006a93a  jnz     short loc_14006A945
0x14006a93c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14006a943  jz      short loc_14006A957
0x14006a945  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14006a94c  test    rax, rax
0x14006a94f  jz      short loc_14006A957
0x14006a951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006a956  nop
0x14006a957  mov     rbx, [rsp+78h+arg_10]
0x14006a95f  add     rsp, 40h
0x14006a963  pop     r15
0x14006a965  pop     r14
0x14006a967  pop     r13
0x14006a969  pop     r12
0x14006a96b  pop     rdi
0x14006a96c  pop     rsi
0x14006a96d  pop     rbp
0x14006a96e  retn
0x14006a96f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
