# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007918`
- end: `0x180007c11`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180005ef0`
- `0x18000625c`
- `0x18000b31c`

## callees

- `0x180005e24`
- `0x180006e94`
- `0x180007754`
- `0x180007918`
- `0x180008008`
- `0x180008030`
- `0x180008044`
- `0x180008060`
- `0x180008ec4`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a3b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007a3b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007bcc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007bcc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b5a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007b5a`

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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
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
0x180007918  mov     [rsp+arg_10], rbx
0x18000791d  mov     [rsp+arg_8], edx
0x180007921  mov     [rsp+arg_0], rcx
0x180007926  push    rbp
0x180007927  push    rsi
0x180007928  push    rdi
0x180007929  push    r12
0x18000792b  push    r13
0x18000792d  push    r14
0x18000792f  push    r15
0x180007931  sub     rsp, 40h
0x180007935  mov     r12, r9
0x180007938  mov     r13, r8
0x18000793b  mov     r10, rcx
0x18000793e  xor     eax, eax
0x180007940  mov     rsi, [rsp+78h+lpOutputString]
0x180007948  mov     [rsi], ax
0x18000794b  mov     rax, [rsp+78h+arg_60]
0x180007953  mov     byte ptr [rax], 0
0x180007956  mov     r14, [rsp+78h+arg_38]
0x18000795e  mov     edi, [r14]
0x180007961  mov     rbx, [rsp+78h+arg_78]
0x180007969  mov     [rbx+8], edi
0x18000796c  mov     eax, [r14+4]
0x180007970  mov     [rbx+0Ch], eax
0x180007973  xor     ebp, ebp
0x180007975  mov     r15d, [rsp+78h+arg_30]
0x18000797d  mov     ecx, r15d
0x180007980  test    r15d, r15d
0x180007983  jz      short loc_1800079EB
0x180007985  sub     ecx, 1
0x180007988  jz      short loc_1800079E2
0x18000798a  sub     ecx, 1
0x18000798d  jz      short loc_18000799D
0x18000798f  cmp     ecx, 1
0x180007992  jnz     short loc_1800079F4
0x180007994  mov     ecx, edi; this
0x180007996  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000799b  jmp     short loc_1800079F2
0x18000799d  test    edi, edi
0x18000799f  js      short loc_1800079D9
0x1800079a1  mov     edi, 8007029Ch
0x1800079a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800079aa  mov     rax, [rsp+78h+arg_28]
0x1800079b2  mov     [rsp+78h+var_50], rax; __int64
0x1800079b7  mov     rax, [rsp+78h+arg_20]
0x1800079bf  mov     [rsp+78h+var_58], rax; __int64
0x1800079c4  mov     rcx, r10; int
0x1800079c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800079cc  mov     [rbx+8], edi
0x1800079cf  mov     ecx, edi; this
0x1800079d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800079d6  mov     [rbx+0Ch], eax
0x1800079d9  mov     ecx, edi; this
0x1800079db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800079e0  jmp     short loc_1800079F2
0x1800079e2  mov     ecx, edi; this
0x1800079e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800079e9  jmp     short loc_1800079F2
0x1800079eb  mov     ecx, edi; this
0x1800079ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800079f2  mov     ebp, eax
0x1800079f4  mov     [rbx], r15d
0x1800079f7  mov     eax, [rsp+78h+arg_70]
0x1800079fe  mov     [rbx+4], eax
0x180007a01  cmp     dword ptr [r14+8], 1
0x180007a06  jnz     short loc_180007A0E
0x180007a08  or      eax, 8
0x180007a0b  mov     [rbx+4], eax
0x180007a0e  mov     eax, 1
0x180007a13  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007a1b  inc     eax
0x180007a1d  mov     [rbx+10h], eax
0x180007a20  mov     rax, [rsp+78h+arg_40]
0x180007a28  xor     edi, edi
0x180007a2a  test    rax, rax
0x180007a2d  jz      short loc_180007A34
0x180007a2f  cmp     [rax], di
0x180007a32  jnz     short loc_180007A37
0x180007a34  mov     rax, rdi
0x180007a37  mov     [rbx+18h], rax
0x180007a3b  call    cs:__imp_GetCurrentThreadId
0x180007a41  mov     [rbx+20h], eax
0x180007a44  mov     [rbx+38h], r13
0x180007a48  mov     eax, [rsp+78h+arg_8]
0x180007a4f  mov     [rbx+40h], eax
0x180007a52  mov     [rbx+44h], ebp
0x180007a55  mov     rax, [rsp+78h+arg_20]
0x180007a5d  mov     [rbx+28h], rax
0x180007a61  mov     [rbx+30h], r12
0x180007a65  mov     rax, [rsp+78h+arg_28]
0x180007a6d  mov     [rbx+88h], rax
0x180007a74  mov     rax, [rsp+78h+arg_0]
0x180007a7c  mov     [rbx+90h], rax
0x180007a83  mov     [rbx+48h], rdi
0x180007a87  xorps   xmm0, xmm0
0x180007a8a  xor     eax, eax
0x180007a8c  movups  xmmword ptr [rbx+68h], xmm0
0x180007a90  mov     [rbx+78h], rax
0x180007a94  movups  xmmword ptr [rbx+50h], xmm0
0x180007a98  mov     [rbx+60h], rax
0x180007a9c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007aa3  test    rax, rax
0x180007aa6  jz      short loc_180007AAF
0x180007aa8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aad  jmp     short loc_180007AB2
0x180007aaf  mov     rax, rdi
0x180007ab2  mov     [rbx+80h], rax
0x180007ab9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007ac0  test    rax, rax
0x180007ac3  jz      short loc_180007ACD
0x180007ac5  mov     rcx, rbx
0x180007ac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007acd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007ad4  test    rax, rax
0x180007ad7  jz      short loc_180007AEF
0x180007ad9  mov     r8d, 400h
0x180007adf  mov     rdx, [rsp+78h+arg_60]
0x180007ae7  mov     rcx, rbx
0x180007aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007aef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007af6  test    rax, rax
0x180007af9  jz      short loc_180007B03
0x180007afb  mov     rcx, rbx
0x180007afe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b03  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007b0a  test    rax, rax
0x180007b0d  jz      short loc_180007B1D
0x180007b0f  test    byte ptr [rbx+4], 2
0x180007b13  jnz     short loc_180007B1D
0x180007b15  mov     rcx, rbx
0x180007b18  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b1d  cmp     [rbx+8], edi
0x180007b20  jl      short loc_180007B3C
0x180007b22  cmp     r15d, 3
0x180007b26  jnz     loc_180007C0B
0x180007b2c  mov     ecx, 8000FFFFh; this
0x180007b31  mov     [rbx+8], ecx
0x180007b34  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007b39  mov     [rbx+0Ch], eax
0x180007b3c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007b43  jnz     short loc_180007B64
0x180007b45  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007b4c  test    rax, rax
0x180007b4f  jz      short loc_180007B5A
0x180007b51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b56  test    al, al
0x180007b58  jmp     short loc_180007B62
0x180007b5a  call    cs:__imp_IsDebuggerPresent
0x180007b60  test    eax, eax
0x180007b62  jz      short loc_180007B6A
0x180007b64  test    byte ptr [rbx+4], 2
0x180007b68  jz      short loc_180007B8E
0x180007b6a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b71  test    rax, rax
0x180007b74  jz      short loc_180007BD2
0x180007b76  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007b7d  jnz     short loc_180007BD2
0x180007b7f  xor     r8d, r8d
0x180007b82  xor     edx, edx
0x180007b84  mov     rcx, rbx
0x180007b87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b8c  jmp     short loc_180007BD2
0x180007b8e  mov     ebp, 800h
0x180007b93  mov     rax, cs:g_pfnResultLoggingCallback
0x180007b9a  test    rax, rax
0x180007b9d  jz      short loc_180007BB6
0x180007b9f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007ba6  jnz     short loc_180007BB6
0x180007ba8  mov     r8d, ebp
0x180007bab  mov     rdx, rsi
0x180007bae  mov     rcx, rbx
0x180007bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bb6  cmp     [rsi], di
0x180007bb9  jnz     short loc_180007BC9
0x180007bbb  mov     r8, rbx; unsigned __int64
0x180007bbe  mov     rdx, rbp; unsigned __int16 *
0x180007bc1  mov     rcx, rsi; this
0x180007bc4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007bc9  mov     rcx, rsi; lpOutputString
0x180007bcc  call    cs:__imp_OutputDebugStringW
0x180007bd2  test    byte ptr [rbx+4], 4
0x180007bd6  jnz     short loc_180007BE1
0x180007bd8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007bdf  jz      short loc_180007BF3
0x180007be1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007be8  test    rax, rax
0x180007beb  jz      short loc_180007BF3
0x180007bed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007bf2  nop
0x180007bf3  mov     rbx, [rsp+78h+arg_10]
0x180007bfb  add     rsp, 40h
0x180007bff  pop     r15
0x180007c01  pop     r14
0x180007c03  pop     r13
0x180007c05  pop     r12
0x180007c07  pop     rdi
0x180007c08  pop     rsi
0x180007c09  pop     rbp
0x180007c0a  retn
0x180007c0b  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
```
