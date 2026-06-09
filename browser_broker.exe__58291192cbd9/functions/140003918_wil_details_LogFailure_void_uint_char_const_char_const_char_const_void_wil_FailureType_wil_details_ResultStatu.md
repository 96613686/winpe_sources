# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003918`
- end: `0x140003c10`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400022b4`
- `0x140002600`

## callees

- `0x1400021f4`
- `0x140002f54`
- `0x140003728`
- `0x140003918`
- `0x140003f1c`
- `0x140003f40`
- `0x140003f54`
- `0x140003f70`
- `0x140004a00`
- `0x140006010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140003a3b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003b5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140003b5a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003bcc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140003bcc`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
  *(_QWORD *)(a16 + 72) = 0;
  *(_OWORD *)(a16 + 104) = 0;
  *(_QWORD *)(a16 + 120) = 0;
  *(_OWORD *)(a16 + 80) = 0;
  *(_QWORD *)(a16 + 96) = 0;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x140003918  mov     [rsp+arg_10], rbx
0x14000391d  mov     [rsp+arg_8], edx
0x140003921  mov     [rsp+arg_0], rcx
0x140003926  push    rbp
0x140003927  push    rsi
0x140003928  push    rdi
0x140003929  push    r12
0x14000392b  push    r13
0x14000392d  push    r14
0x14000392f  push    r15
0x140003931  sub     rsp, 40h
0x140003935  mov     r14, [rsp+78h+arg_38]
0x14000393d  xor     eax, eax
0x14000393f  mov     rbx, [rsp+78h+arg_78]
0x140003947  xor     ebp, ebp
0x140003949  mov     r15d, [rsp+78h+arg_30]
0x140003951  mov     r10, rcx
0x140003954  mov     rsi, [rsp+78h+lpOutputString]
0x14000395c  mov     r12, r9
0x14000395f  mov     r13, r8
0x140003962  mov     ecx, r15d
0x140003965  mov     [rsi], ax
0x140003968  mov     rax, [rsp+78h+arg_60]
0x140003970  mov     byte ptr [rax], 0
0x140003973  mov     edi, [r14]
0x140003976  mov     [rbx+8], edi
0x140003979  mov     eax, [r14+4]
0x14000397d  mov     [rbx+0Ch], eax
0x140003980  test    r15d, r15d
0x140003983  jz      short loc_1400039EB
0x140003985  sub     ecx, 1
0x140003988  jz      short loc_1400039E2
0x14000398a  sub     ecx, 1
0x14000398d  jz      short loc_14000399D
0x14000398f  cmp     ecx, 1
0x140003992  jnz     short loc_1400039F4
0x140003994  mov     ecx, edi; this
0x140003996  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000399b  jmp     short loc_1400039F2
0x14000399d  test    edi, edi
0x14000399f  js      short loc_1400039D9
0x1400039a1  mov     rax, [rsp+78h+arg_28]
0x1400039a9  mov     edi, 8007029Ch
0x1400039ae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400039b2  mov     rcx, r10; int
0x1400039b5  mov     [rsp+78h+var_50], rax; __int64
0x1400039ba  mov     rax, [rsp+78h+arg_20]
0x1400039c2  mov     [rsp+78h+var_58], rax; __int64
0x1400039c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400039cc  mov     ecx, edi; this
0x1400039ce  mov     [rbx+8], edi
0x1400039d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400039d6  mov     [rbx+0Ch], eax
0x1400039d9  mov     ecx, edi; this
0x1400039db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400039e0  jmp     short loc_1400039F2
0x1400039e2  mov     ecx, edi; this
0x1400039e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400039e9  jmp     short loc_1400039F2
0x1400039eb  mov     ecx, edi; this
0x1400039ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400039f2  mov     ebp, eax
0x1400039f4  mov     eax, [rsp+78h+arg_70]
0x1400039fb  mov     [rbx+4], eax
0x1400039fe  mov     [rbx], r15d
0x140003a01  cmp     dword ptr [r14+8], 1
0x140003a06  jnz     short loc_140003A0E
0x140003a08  or      eax, 8
0x140003a0b  mov     [rbx+4], eax
0x140003a0e  mov     eax, 1
0x140003a13  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140003a1b  inc     eax
0x140003a1d  xor     edi, edi
0x140003a1f  mov     [rbx+10h], eax
0x140003a22  mov     rax, [rsp+78h+arg_40]
0x140003a2a  test    rax, rax
0x140003a2d  jz      short loc_140003A34
0x140003a2f  cmp     [rax], di
0x140003a32  jnz     short loc_140003A37
0x140003a34  mov     rax, rdi
0x140003a37  mov     [rbx+18h], rax
0x140003a3b  call    cs:__imp_GetCurrentThreadId
0x140003a41  mov     [rbx+38h], r13
0x140003a45  xorps   xmm0, xmm0
0x140003a48  mov     [rbx+20h], eax
0x140003a4b  mov     eax, [rsp+78h+arg_8]
0x140003a52  mov     [rbx+40h], eax
0x140003a55  mov     rax, [rsp+78h+arg_20]
0x140003a5d  mov     [rbx+28h], rax
0x140003a61  mov     rax, [rsp+78h+arg_28]
0x140003a69  mov     [rbx+88h], rax
0x140003a70  mov     rax, [rsp+78h+arg_0]
0x140003a78  mov     [rbx+90h], rax
0x140003a7f  xor     eax, eax
0x140003a81  mov     [rbx+44h], ebp
0x140003a84  mov     [rbx+30h], r12
0x140003a88  mov     [rbx+48h], rdi
0x140003a8c  movups  xmmword ptr [rbx+68h], xmm0
0x140003a90  mov     [rbx+78h], rax
0x140003a94  movups  xmmword ptr [rbx+50h], xmm0
0x140003a98  mov     [rbx+60h], rax
0x140003a9c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140003aa3  test    rax, rax
0x140003aa6  jz      short loc_140003AAF
0x140003aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003aad  jmp     short loc_140003AB2
0x140003aaf  mov     rax, rdi
0x140003ab2  mov     [rbx+80h], rax
0x140003ab9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140003ac0  test    rax, rax
0x140003ac3  jz      short loc_140003ACD
0x140003ac5  mov     rcx, rbx
0x140003ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003acd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140003ad4  test    rax, rax
0x140003ad7  jz      short loc_140003AEF
0x140003ad9  mov     rdx, [rsp+78h+arg_60]
0x140003ae1  mov     r8d, 400h
0x140003ae7  mov     rcx, rbx
0x140003aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003aef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003af6  test    rax, rax
0x140003af9  jz      short loc_140003B03
0x140003afb  mov     rcx, rbx
0x140003afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b03  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140003b0a  test    rax, rax
0x140003b0d  jz      short loc_140003B1D
0x140003b0f  test    byte ptr [rbx+4], 2
0x140003b13  jnz     short loc_140003B1D
0x140003b15  mov     rcx, rbx
0x140003b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b1d  cmp     [rbx+8], edi
0x140003b20  jl      short loc_140003B3C
0x140003b22  cmp     r15d, 3
0x140003b26  jnz     loc_140003C0A
0x140003b2c  mov     ecx, 8000FFFFh; this
0x140003b31  mov     [rbx+8], ecx
0x140003b34  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140003b39  mov     [rbx+0Ch], eax
0x140003b3c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140003b43  jnz     short loc_140003B64
0x140003b45  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140003b4c  test    rax, rax
0x140003b4f  jz      short loc_140003B5A
0x140003b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b56  test    al, al
0x140003b58  jmp     short loc_140003B62
0x140003b5a  call    cs:__imp_IsDebuggerPresent
0x140003b60  test    eax, eax
0x140003b62  jz      short loc_140003B6A
0x140003b64  test    byte ptr [rbx+4], 2
0x140003b68  jz      short loc_140003B8E
0x140003b6a  mov     rax, cs:g_pfnResultLoggingCallback
0x140003b71  test    rax, rax
0x140003b74  jz      short loc_140003BD2
0x140003b76  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140003b7d  jnz     short loc_140003BD2
0x140003b7f  xor     r8d, r8d
0x140003b82  xor     edx, edx
0x140003b84  mov     rcx, rbx
0x140003b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003b8c  jmp     short loc_140003BD2
0x140003b8e  mov     rax, cs:g_pfnResultLoggingCallback
0x140003b95  mov     ebp, 800h
0x140003b9a  test    rax, rax
0x140003b9d  jz      short loc_140003BB6
0x140003b9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140003ba6  jnz     short loc_140003BB6
0x140003ba8  mov     r8d, ebp
0x140003bab  mov     rdx, rsi
0x140003bae  mov     rcx, rbx
0x140003bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bb6  cmp     [rsi], di
0x140003bb9  jnz     short loc_140003BC9
0x140003bbb  mov     r8, rbx; unsigned __int64
0x140003bbe  mov     rdx, rbp; unsigned __int16 *
0x140003bc1  mov     rcx, rsi; this
0x140003bc4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140003bc9  mov     rcx, rsi; lpOutputString
0x140003bcc  call    cs:__imp_OutputDebugStringW
0x140003bd2  test    byte ptr [rbx+4], 4
0x140003bd6  jnz     short loc_140003BE1
0x140003bd8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140003bdf  jz      short loc_140003BF2
0x140003be1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140003be8  test    rax, rax
0x140003beb  jz      short loc_140003BF2
0x140003bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140003bf2  mov     rbx, [rsp+78h+arg_10]
0x140003bfa  add     rsp, 40h
0x140003bfe  pop     r15
0x140003c00  pop     r14
0x140003c02  pop     r13
0x140003c04  pop     r12
0x140003c06  pop     rdi
0x140003c07  pop     rsi
0x140003c08  pop     rbp
0x140003c09  retn
0x140003c0a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
