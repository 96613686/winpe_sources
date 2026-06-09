# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005b3d0`
- end: `0x18005b762`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `914`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18005b2e0`
- `0x180088ff0`
- `0x1800890a0`

## callees

- `0x18005b3d0`
- `0x18005b7c4`
- `0x18007c85c`
- `0x18008469c`
- `0x180088f40`
- `0x18008983c`
- `0x180089e20`
- `0x180089e34`
- `0x18008a678`
- `0x1800c5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b4a0`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b4a0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005b599`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005b599`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005b661`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005b661`

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
  _WORD *v20; // rax
  int v21; // edx
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  int v26; // eax
  int v27; // edx
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
        v26 = wil::details::RecordReturn((wil::details *)v18, a2);
        break;
      case 2:
        if ( (v18 & 0x80000000) == 0 )
        {
          v18 = -2147024228;
          LODWORD(v28) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v27);
        }
        v26 = wil::details::RecordLog((wil::details *)v18, a2);
        break;
      case 3:
        v26 = wil::details::RecordFailFast((wil::details *)v18, a2);
        break;
      default:
        goto LABEL_5;
    }
  }
  else
  {
    v26 = wil::details::RecordException((wil::details *)v18, a2);
  }
  v19 = v26;
LABEL_5:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v21);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (wil::g_pfnIsDebuggerPresent
      ? (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0)
      : (v25 = !IsDebuggerPresent()),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x18005b3d0  mov     [rsp+arg_10], rbx
0x18005b3d5  mov     [rsp+arg_8], edx
0x18005b3d9  mov     [rsp+arg_0], rcx
0x18005b3de  push    rbp
0x18005b3df  push    rsi
0x18005b3e0  push    rdi
0x18005b3e1  push    r12
0x18005b3e3  push    r13
0x18005b3e5  push    r14
0x18005b3e7  push    r15
0x18005b3e9  sub     rsp, 40h
0x18005b3ed  mov     r12, r9
0x18005b3f0  mov     r13, r8
0x18005b3f3  mov     r10, rcx
0x18005b3f6  xor     eax, eax
0x18005b3f8  mov     rsi, [rsp+78h+lpOutputString]
0x18005b400  mov     [rsi], ax
0x18005b403  mov     rax, [rsp+78h+arg_60]
0x18005b40b  mov     byte ptr [rax], 0
0x18005b40e  mov     r14, [rsp+78h+arg_38]
0x18005b416  mov     edi, [r14]
0x18005b419  mov     rbx, [rsp+78h+arg_78]
0x18005b421  mov     [rbx+8], edi
0x18005b424  mov     eax, [r14+4]
0x18005b428  mov     [rbx+0Ch], eax
0x18005b42b  xor     ebp, ebp
0x18005b42d  mov     r15d, [rsp+78h+arg_30]
0x18005b435  mov     ecx, r15d
0x18005b438  test    r15d, r15d
0x18005b43b  jz      loc_18005B632
0x18005b441  sub     ecx, 1
0x18005b444  jz      loc_18005B6BE
0x18005b44a  sub     ecx, 1
0x18005b44d  jz      loc_18005B675
0x18005b453  cmp     ecx, 1
0x18005b456  jz      loc_18005B66C
0x18005b45c  mov     [rbx], r15d
0x18005b45f  mov     eax, [rsp+78h+arg_70]
0x18005b466  mov     [rbx+4], eax
0x18005b469  cmp     dword ptr [r14+8], 1
0x18005b46e  jz      loc_18005B6CA
0x18005b474  mov     eax, 1
0x18005b479  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005b481  inc     eax
0x18005b483  mov     [rbx+10h], eax
0x18005b486  mov     rax, [rsp+78h+arg_40]
0x18005b48e  xor     edi, edi
0x18005b490  test    rax, rax
0x18005b493  jnz     loc_18005B624
0x18005b499  mov     rax, rdi
0x18005b49c  mov     [rbx+18h], rax
0x18005b4a0  call    cs:__imp_GetCurrentThreadId
0x18005b4a6  mov     [rbx+20h], eax
0x18005b4a9  mov     [rbx+38h], r13
0x18005b4ad  mov     eax, [rsp+78h+arg_8]
0x18005b4b4  mov     [rbx+40h], eax
0x18005b4b7  mov     [rbx+44h], ebp
0x18005b4ba  mov     rax, [rsp+78h+arg_20]
0x18005b4c2  mov     [rbx+28h], rax
0x18005b4c6  mov     [rbx+30h], r12
0x18005b4ca  mov     rax, [rsp+78h+arg_28]
0x18005b4d2  mov     [rbx+88h], rax
0x18005b4d9  mov     rax, [rsp+78h+arg_0]
0x18005b4e1  mov     [rbx+90h], rax
0x18005b4e8  mov     [rbx+48h], rdi
0x18005b4ec  xorps   xmm0, xmm0
0x18005b4ef  xor     eax, eax
0x18005b4f1  movups  xmmword ptr [rbx+68h], xmm0
0x18005b4f5  mov     [rbx+78h], rax
0x18005b4f9  movups  xmmword ptr [rbx+50h], xmm0
0x18005b4fd  mov     [rbx+60h], rax
0x18005b501  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005b508  test    rax, rax
0x18005b50b  jz      loc_18005B5E6
0x18005b511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b516  mov     [rbx+80h], rax
0x18005b51d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005b524  test    rax, rax
0x18005b527  jz      short loc_18005B531
0x18005b529  mov     rcx, rbx
0x18005b52c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b531  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005b538  test    rax, rax
0x18005b53b  jz      short loc_18005B553
0x18005b53d  mov     r8d, 400h
0x18005b543  mov     rdx, [rsp+78h+arg_60]
0x18005b54b  mov     rcx, rbx
0x18005b54e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b553  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005b55a  test    rax, rax
0x18005b55d  jz      short loc_18005B567
0x18005b55f  mov     rcx, rbx
0x18005b562  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b567  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005b56e  test    rax, rax
0x18005b571  jnz     short loc_18005B5EE
0x18005b573  cmp     [rbx+8], edi
0x18005b576  jge     loc_18005B605
0x18005b57c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005b583  jnz     loc_18005B6E7
0x18005b589  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005b590  test    rax, rax
0x18005b593  jnz     loc_18005B6DB
0x18005b599  call    cs:__imp_IsDebuggerPresent
0x18005b59f  test    eax, eax
0x18005b5a1  jnz     loc_18005B6E7
0x18005b5a7  mov     rax, cs:g_pfnResultLoggingCallback
0x18005b5ae  test    rax, rax
0x18005b5b1  jnz     loc_18005B6F6
0x18005b5b7  test    byte ptr [rbx+4], 4
0x18005b5bb  jnz     loc_18005B748
0x18005b5c1  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005b5c8  jnz     loc_18005B748
0x18005b5ce  mov     rbx, [rsp+78h+arg_10]
0x18005b5d6  add     rsp, 40h
0x18005b5da  pop     r15
0x18005b5dc  pop     r14
0x18005b5de  pop     r13
0x18005b5e0  pop     r12
0x18005b5e2  pop     rdi
0x18005b5e3  pop     rsi
0x18005b5e4  pop     rbp
0x18005b5e5  retn
0x18005b5e6  mov     rax, rdi
0x18005b5e9  jmp     loc_18005B516
0x18005b5ee  test    byte ptr [rbx+4], 2
0x18005b5f2  jnz     loc_18005B573
0x18005b5f8  mov     rcx, rbx
0x18005b5fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b600  jmp     loc_18005B573
0x18005b605  cmp     r15d, 3
0x18005b609  jnz     loc_18005B6D5
0x18005b60f  mov     ecx, 8000FFFFh; this
0x18005b614  mov     [rbx+8], ecx
0x18005b617  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005b61c  mov     [rbx+0Ch], eax
0x18005b61f  jmp     loc_18005B57C
0x18005b624  cmp     [rax], di
0x18005b627  jnz     loc_18005B49C
0x18005b62d  jmp     loc_18005B499
0x18005b632  mov     ecx, edi; this
0x18005b634  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005b639  mov     ebp, eax
0x18005b63b  jmp     loc_18005B45C
0x18005b640  mov     ebp, 800h
0x18005b645  mov     rax, cs:g_pfnResultLoggingCallback
0x18005b64c  test    rax, rax
0x18005b64f  jnz     loc_18005B715
0x18005b655  cmp     [rsi], di
0x18005b658  jz      loc_18005B735
0x18005b65e  mov     rcx, rsi; lpOutputString
0x18005b661  call    cs:__imp_OutputDebugStringW
0x18005b667  jmp     loc_18005B5B7
0x18005b66c  mov     ecx, edi; this
0x18005b66e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005b673  jmp     short loc_18005B639
0x18005b675  test    edi, edi
0x18005b677  js      loc_1800C3C40
0x18005b67d  mov     [rsp+78h+var_40], ebp
0x18005b681  mov     edi, 8007029Ch
0x18005b686  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005b68a  mov     rax, [rsp+78h+arg_28]
0x18005b692  mov     [rsp+78h+var_50], rax; __int64
0x18005b697  mov     rax, [rsp+78h+arg_20]
0x18005b69f  mov     [rsp+78h+var_58], rax; __int64
0x18005b6a4  mov     rcx, r10; int
0x18005b6a7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18005b6ac  mov     [rbx+8], edi
0x18005b6af  mov     ecx, edi; this
0x18005b6b1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005b6b6  mov     [rbx+0Ch], eax
0x18005b6b9  jmp     loc_1800C3C40
0x18005b6be  mov     ecx, edi; this
0x18005b6c0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005b6c5  jmp     loc_18005B639
0x18005b6ca  or      eax, 8
0x18005b6cd  mov     [rbx+4], eax
0x18005b6d0  jmp     loc_18005B474
0x18005b6d5  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18005b6db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b6e0  test    al, al
0x18005b6e2  jmp     loc_18005B5A1
0x18005b6e7  test    byte ptr [rbx+4], 2
0x18005b6eb  jz      loc_18005B640
0x18005b6f1  jmp     loc_18005B5A7
0x18005b6f6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005b6fd  jnz     loc_18005B5B7
0x18005b703  xor     r8d, r8d
0x18005b706  xor     edx, edx
0x18005b708  mov     rcx, rbx
0x18005b70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b710  jmp     loc_18005B5B7
0x18005b715  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005b71c  jnz     loc_18005B655
0x18005b722  mov     r8, rbp
0x18005b725  mov     rdx, rsi
0x18005b728  mov     rcx, rbx
0x18005b72b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b730  jmp     loc_18005B655
0x18005b735  mov     r8, rbx; unsigned __int64
0x18005b738  mov     rdx, rbp; unsigned __int16 *
0x18005b73b  mov     rcx, rsi; this
0x18005b73e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005b743  jmp     loc_18005B65E
0x18005b748  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005b74f  test    rax, rax
0x18005b752  jz      loc_18005B5CE
0x18005b758  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005b75d  jmp     loc_18005B5CE
0x1800c3c40  mov     ecx, edi; this
0x1800c3c42  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800c3c47  nop
0x1800c3c48  jmp     loc_18005B639
```
