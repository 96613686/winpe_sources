# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180099dd0`
- end: `0x18009a079`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `681`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `11`
- tags: ``

## callers

- `0x180097adc`
- `0x180097b88`
- `0x180097c84`

## callees

- `0x18003efd4`
- `0x180054f9c`
- `0x180065470`
- `0x180068514`
- `0x180068530`
- `0x1800685ec`
- `0x180068608`
- `0x18006a0b0`
- `0x180099228`
- `0x180099dd0`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099ee0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180099ee0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009a01d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18009a01d`

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
        __int64 a15,
        unsigned __int64 a16)
{
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  __int64 ModuleName; // rax
  wchar_t *v26; // rdx
  const struct wil::FailureInfo *v27; // r9
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, 0, 0, a6, v28);
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
  *(_DWORD *)(a16 + 4) = 0;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v19;
  *(_QWORD *)(a16 + 40) = 0;
  *(_QWORD *)(a16 + 48) = 0;
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
      wil::details::in1diag3::FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, v26, a16, v27);
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
0x180099dd0  mov     [rsp+arg_0], rcx
0x180099dd5  push    rbx
0x180099dd6  push    rbp
0x180099dd7  push    rsi
0x180099dd8  push    rdi
0x180099dd9  push    r12
0x180099ddb  push    r13
0x180099ddd  push    r14
0x180099ddf  push    r15
0x180099de1  sub     rsp, 48h
0x180099de5  mov     r12, r8
0x180099de8  mov     r13d, edx
0x180099deb  mov     r10, rcx
0x180099dee  xor     eax, eax
0x180099df0  mov     rsi, [rsp+88h+lpOutputString]
0x180099df8  mov     [rsi], ax
0x180099dfb  mov     rax, [rsp+88h+arg_60]
0x180099e03  mov     byte ptr [rax], 0
0x180099e06  mov     r14, [rsp+88h+arg_38]
0x180099e0e  mov     edi, [r14]
0x180099e11  mov     rbx, [rsp+88h+arg_78]
0x180099e19  mov     [rbx+8], edi
0x180099e1c  mov     eax, [r14+4]
0x180099e20  mov     [rbx+0Ch], eax
0x180099e23  xor     ebp, ebp
0x180099e25  mov     r15d, [rsp+88h+arg_30]
0x180099e2d  mov     ecx, r15d
0x180099e30  test    r15d, r15d
0x180099e33  jz      short loc_180099E96
0x180099e35  sub     ecx, 1
0x180099e38  jz      short loc_180099E8D
0x180099e3a  sub     ecx, 1
0x180099e3d  jz      short loc_180099E4D
0x180099e3f  cmp     ecx, 1
0x180099e42  jnz     short loc_180099E9F
0x180099e44  mov     ecx, edi; this
0x180099e46  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180099e4b  jmp     short loc_180099E9D
0x180099e4d  test    edi, edi
0x180099e4f  js      short loc_180099E84
0x180099e51  mov     edi, 8007029Ch
0x180099e56  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x180099e5a  mov     rax, [rsp+88h+arg_28]
0x180099e62  mov     [rsp+88h+var_60], rax; __int64
0x180099e67  mov     [rsp+88h+var_68], rbp; __int64
0x180099e6c  xor     r9d, r9d; int
0x180099e6f  mov     rcx, r10; int
0x180099e72  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180099e77  mov     [rbx+8], edi
0x180099e7a  mov     ecx, edi; this
0x180099e7c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180099e81  mov     [rbx+0Ch], eax
0x180099e84  mov     ecx, edi; this
0x180099e86  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180099e8b  jmp     short loc_180099E9D
0x180099e8d  mov     ecx, edi; this
0x180099e8f  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180099e94  jmp     short loc_180099E9D
0x180099e96  mov     ecx, edi; this
0x180099e98  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180099e9d  mov     ebp, eax
0x180099e9f  mov     [rbx], r15d
0x180099ea2  xor     edi, edi
0x180099ea4  mov     [rbx+4], edi
0x180099ea7  cmp     dword ptr [r14+8], 1
0x180099eac  jnz     short loc_180099EB5
0x180099eae  mov     dword ptr [rbx+4], 8
0x180099eb5  mov     eax, 1
0x180099eba  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180099ec2  inc     eax
0x180099ec4  mov     [rbx+10h], eax
0x180099ec7  mov     rax, [rsp+88h+arg_40]
0x180099ecf  test    rax, rax
0x180099ed2  jz      short loc_180099ED9
0x180099ed4  cmp     [rax], di
0x180099ed7  jnz     short loc_180099EDC
0x180099ed9  mov     rax, rdi
0x180099edc  mov     [rbx+18h], rax
0x180099ee0  call    cs:__imp_GetCurrentThreadId
0x180099ee6  mov     [rbx+20h], eax
0x180099ee9  mov     [rbx+38h], r12
0x180099eed  mov     [rbx+40h], r13d
0x180099ef1  mov     [rbx+44h], ebp
0x180099ef4  mov     [rbx+28h], rdi
0x180099ef8  mov     [rbx+30h], rdi
0x180099efc  mov     rax, [rsp+88h+arg_28]
0x180099f04  mov     [rbx+88h], rax
0x180099f0b  mov     rax, [rsp+88h+arg_0]
0x180099f13  mov     [rbx+90h], rax
0x180099f1a  mov     [rbx+48h], rdi
0x180099f1e  xorps   xmm0, xmm0
0x180099f21  xor     eax, eax
0x180099f23  movups  xmmword ptr [rbx+68h], xmm0
0x180099f27  mov     [rbx+78h], rax
0x180099f2b  movups  xmmword ptr [rbx+50h], xmm0
0x180099f2f  mov     [rbx+60h], rax
0x180099f33  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180099f3a  test    rax, rax
0x180099f3d  jz      short loc_180099F46
0x180099f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f44  jmp     short loc_180099F49
0x180099f46  mov     rax, rdi
0x180099f49  mov     [rbx+80h], rax
0x180099f50  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180099f57  test    rax, rax
0x180099f5a  jz      short loc_180099F64
0x180099f5c  mov     rcx, rbx
0x180099f5f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f64  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180099f6b  test    rax, rax
0x180099f6e  jz      short loc_180099F86
0x180099f70  mov     r8d, 400h
0x180099f76  mov     rdx, [rsp+88h+arg_60]
0x180099f7e  mov     rcx, rbx
0x180099f81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f86  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180099f8d  test    rax, rax
0x180099f90  jz      short loc_180099F9A
0x180099f92  mov     rcx, rbx
0x180099f95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099f9a  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180099fa1  test    rax, rax
0x180099fa4  jz      short loc_180099FB4
0x180099fa6  test    byte ptr [rbx+4], 2
0x180099faa  jnz     short loc_180099FB4
0x180099fac  mov     rcx, rbx
0x180099faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180099fb4  cmp     [rbx+8], edi
0x180099fb7  jl      short loc_180099FD5
0x180099fb9  cmp     r15d, 3
0x180099fbd  jz      short loc_180099FC5
0x180099fbf  call    ?FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::FailFastImmediate_Unexpected(void)
0x180099fc5  mov     ecx, 8000FFFFh; this
0x180099fca  mov     [rbx+8], ecx
0x180099fcd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180099fd2  mov     [rbx+0Ch], eax
0x180099fd5  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180099fda  test    al, al
0x180099fdc  jz      short loc_18009A025
0x180099fde  test    byte ptr [rbx+4], 2
0x180099fe2  jnz     short loc_18009A025
0x180099fe4  mov     rax, cs:g_pfnResultLoggingCallback
0x180099feb  test    rax, rax
0x180099fee  jz      short loc_18009A00A
0x180099ff0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180099ff7  jnz     short loc_18009A00A
0x180099ff9  mov     r8d, 800h
0x180099fff  mov     rdx, rsi
0x18009a002  mov     rcx, rbx
0x18009a005  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a00a  cmp     [rsi], di
0x18009a00d  jnz     short loc_18009A01A
0x18009a00f  mov     r8, rbx; unsigned __int64
0x18009a012  mov     rcx, rsi; this
0x18009a015  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18009a01a  mov     rcx, rsi; lpOutputString
0x18009a01d  call    cs:__imp_OutputDebugStringW
0x18009a023  jmp     short loc_18009A047
0x18009a025  mov     rax, cs:g_pfnResultLoggingCallback
0x18009a02c  test    rax, rax
0x18009a02f  jz      short loc_18009A047
0x18009a031  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18009a038  jnz     short loc_18009A047
0x18009a03a  xor     r8d, r8d
0x18009a03d  xor     edx, edx
0x18009a03f  mov     rcx, rbx
0x18009a042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a047  test    byte ptr [rbx+4], 4
0x18009a04b  jnz     short loc_18009A056
0x18009a04d  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18009a054  jz      short loc_18009A068
0x18009a056  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18009a05d  test    rax, rax
0x18009a060  jz      short loc_18009A068
0x18009a062  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18009a067  nop
0x18009a068  add     rsp, 48h
0x18009a06c  pop     r15
0x18009a06e  pop     r14
0x18009a070  pop     r13
0x18009a072  pop     r12
0x18009a074  pop     rdi
0x18009a075  pop     rsi
0x18009a076  pop     rbp
0x18009a077  pop     rbx
0x18009a078  retn
```
