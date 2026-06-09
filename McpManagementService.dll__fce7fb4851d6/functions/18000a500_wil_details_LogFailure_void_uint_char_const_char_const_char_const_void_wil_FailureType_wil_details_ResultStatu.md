# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a500`
- end: `0x18000a7f9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180005fe4`
- `0x1800060a4`
- `0x18000645c`

## callees

- `0x180005f1c`
- `0x1800092ec`
- `0x180009d64`
- `0x18000a500`
- `0x18000b63c`
- `0x18000b660`
- `0x18000b798`
- `0x18000b7b4`
- `0x18000e0c8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a623`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a623`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a742`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a742`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a7b4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a7b4`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
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
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x18000a500  mov     [rsp+arg_10], rbx
0x18000a505  mov     [rsp+arg_8], edx
0x18000a509  mov     [rsp+arg_0], rcx
0x18000a50e  push    rbp
0x18000a50f  push    rsi
0x18000a510  push    rdi
0x18000a511  push    r12
0x18000a513  push    r13
0x18000a515  push    r14
0x18000a517  push    r15
0x18000a519  sub     rsp, 40h
0x18000a51d  mov     r12, r9
0x18000a520  mov     r13, r8
0x18000a523  mov     r10, rcx
0x18000a526  xor     eax, eax
0x18000a528  mov     rsi, [rsp+78h+lpOutputString]
0x18000a530  mov     [rsi], ax
0x18000a533  mov     rax, [rsp+78h+arg_60]
0x18000a53b  mov     byte ptr [rax], 0
0x18000a53e  mov     r14, [rsp+78h+arg_38]
0x18000a546  mov     edi, [r14]
0x18000a549  mov     rbx, [rsp+78h+arg_78]
0x18000a551  mov     [rbx+8], edi
0x18000a554  mov     eax, [r14+4]
0x18000a558  mov     [rbx+0Ch], eax
0x18000a55b  xor     ebp, ebp
0x18000a55d  mov     r15d, [rsp+78h+arg_30]
0x18000a565  mov     ecx, r15d
0x18000a568  test    r15d, r15d
0x18000a56b  jz      short loc_18000A5D3
0x18000a56d  sub     ecx, 1
0x18000a570  jz      short loc_18000A5CA
0x18000a572  sub     ecx, 1
0x18000a575  jz      short loc_18000A585
0x18000a577  cmp     ecx, 1
0x18000a57a  jnz     short loc_18000A5DC
0x18000a57c  mov     ecx, edi; this
0x18000a57e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a583  jmp     short loc_18000A5DA
0x18000a585  test    edi, edi
0x18000a587  js      short loc_18000A5C1
0x18000a589  mov     edi, 8007029Ch
0x18000a58e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a592  mov     rax, [rsp+78h+arg_28]
0x18000a59a  mov     [rsp+78h+var_50], rax; __int64
0x18000a59f  mov     rax, [rsp+78h+arg_20]
0x18000a5a7  mov     [rsp+78h+var_58], rax; __int64
0x18000a5ac  mov     rcx, r10; int
0x18000a5af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a5b4  mov     [rbx+8], edi
0x18000a5b7  mov     ecx, edi; this
0x18000a5b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a5be  mov     [rbx+0Ch], eax
0x18000a5c1  mov     ecx, edi; this
0x18000a5c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a5c8  jmp     short loc_18000A5DA
0x18000a5ca  mov     ecx, edi; this
0x18000a5cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a5d1  jmp     short loc_18000A5DA
0x18000a5d3  mov     ecx, edi; this
0x18000a5d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a5da  mov     ebp, eax
0x18000a5dc  mov     [rbx], r15d
0x18000a5df  mov     eax, [rsp+78h+arg_70]
0x18000a5e6  mov     [rbx+4], eax
0x18000a5e9  cmp     dword ptr [r14+8], 1
0x18000a5ee  jnz     short loc_18000A5F6
0x18000a5f0  or      eax, 8
0x18000a5f3  mov     [rbx+4], eax
0x18000a5f6  mov     eax, 1
0x18000a5fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a603  inc     eax
0x18000a605  mov     [rbx+10h], eax
0x18000a608  mov     rax, [rsp+78h+arg_40]
0x18000a610  xor     edi, edi
0x18000a612  test    rax, rax
0x18000a615  jz      short loc_18000A61C
0x18000a617  cmp     [rax], di
0x18000a61a  jnz     short loc_18000A61F
0x18000a61c  mov     rax, rdi
0x18000a61f  mov     [rbx+18h], rax
0x18000a623  call    cs:__imp_GetCurrentThreadId
0x18000a629  mov     [rbx+20h], eax
0x18000a62c  mov     [rbx+38h], r13
0x18000a630  mov     eax, [rsp+78h+arg_8]
0x18000a637  mov     [rbx+40h], eax
0x18000a63a  mov     [rbx+44h], ebp
0x18000a63d  mov     rax, [rsp+78h+arg_20]
0x18000a645  mov     [rbx+28h], rax
0x18000a649  mov     [rbx+30h], r12
0x18000a64d  mov     rax, [rsp+78h+arg_28]
0x18000a655  mov     [rbx+88h], rax
0x18000a65c  mov     rax, [rsp+78h+arg_0]
0x18000a664  mov     [rbx+90h], rax
0x18000a66b  mov     [rbx+48h], rdi
0x18000a66f  xorps   xmm0, xmm0
0x18000a672  xor     eax, eax
0x18000a674  movups  xmmword ptr [rbx+68h], xmm0
0x18000a678  mov     [rbx+78h], rax
0x18000a67c  movups  xmmword ptr [rbx+50h], xmm0
0x18000a680  mov     [rbx+60h], rax
0x18000a684  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a68b  test    rax, rax
0x18000a68e  jz      short loc_18000A697
0x18000a690  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a695  jmp     short loc_18000A69A
0x18000a697  mov     rax, rdi
0x18000a69a  mov     [rbx+80h], rax
0x18000a6a1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a6a8  test    rax, rax
0x18000a6ab  jz      short loc_18000A6B5
0x18000a6ad  mov     rcx, rbx
0x18000a6b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6b5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a6bc  test    rax, rax
0x18000a6bf  jz      short loc_18000A6D7
0x18000a6c1  mov     r8d, 400h
0x18000a6c7  mov     rdx, [rsp+78h+arg_60]
0x18000a6cf  mov     rcx, rbx
0x18000a6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6d7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a6de  test    rax, rax
0x18000a6e1  jz      short loc_18000A6EB
0x18000a6e3  mov     rcx, rbx
0x18000a6e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a6eb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a6f2  test    rax, rax
0x18000a6f5  jz      short loc_18000A705
0x18000a6f7  test    byte ptr [rbx+4], 2
0x18000a6fb  jnz     short loc_18000A705
0x18000a6fd  mov     rcx, rbx
0x18000a700  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a705  cmp     [rbx+8], edi
0x18000a708  jl      short loc_18000A724
0x18000a70a  cmp     r15d, 3
0x18000a70e  jnz     loc_18000A7F3
0x18000a714  mov     ecx, 8000FFFFh; this
0x18000a719  mov     [rbx+8], ecx
0x18000a71c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a721  mov     [rbx+0Ch], eax
0x18000a724  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a72b  jnz     short loc_18000A74C
0x18000a72d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a734  test    rax, rax
0x18000a737  jz      short loc_18000A742
0x18000a739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a73e  test    al, al
0x18000a740  jmp     short loc_18000A74A
0x18000a742  call    cs:__imp_IsDebuggerPresent
0x18000a748  test    eax, eax
0x18000a74a  jz      short loc_18000A752
0x18000a74c  test    byte ptr [rbx+4], 2
0x18000a750  jz      short loc_18000A776
0x18000a752  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a759  test    rax, rax
0x18000a75c  jz      short loc_18000A7BA
0x18000a75e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a765  jnz     short loc_18000A7BA
0x18000a767  xor     r8d, r8d
0x18000a76a  xor     edx, edx
0x18000a76c  mov     rcx, rbx
0x18000a76f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a774  jmp     short loc_18000A7BA
0x18000a776  mov     ebp, 800h
0x18000a77b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a782  test    rax, rax
0x18000a785  jz      short loc_18000A79E
0x18000a787  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a78e  jnz     short loc_18000A79E
0x18000a790  mov     r8d, ebp
0x18000a793  mov     rdx, rsi
0x18000a796  mov     rcx, rbx
0x18000a799  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a79e  cmp     [rsi], di
0x18000a7a1  jnz     short loc_18000A7B1
0x18000a7a3  mov     r8, rbx; unsigned __int64
0x18000a7a6  mov     rdx, rbp; unsigned __int16 *
0x18000a7a9  mov     rcx, rsi; this
0x18000a7ac  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a7b1  mov     rcx, rsi; lpOutputString
0x18000a7b4  call    cs:__imp_OutputDebugStringW
0x18000a7ba  test    byte ptr [rbx+4], 4
0x18000a7be  jnz     short loc_18000A7C9
0x18000a7c0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a7c7  jz      short loc_18000A7DB
0x18000a7c9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a7d0  test    rax, rax
0x18000a7d3  jz      short loc_18000A7DB
0x18000a7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7da  nop
0x18000a7db  mov     rbx, [rsp+78h+arg_10]
0x18000a7e3  add     rsp, 40h
0x18000a7e7  pop     r15
0x18000a7e9  pop     r14
0x18000a7eb  pop     r13
0x18000a7ed  pop     r12
0x18000a7ef  pop     rdi
0x18000a7f0  pop     rsi
0x18000a7f1  pop     rbp
0x18000a7f2  retn
0x18000a7f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
