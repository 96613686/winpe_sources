# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000a620`
- end: `0x18000a915`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a530`
- `0x18000f02c`
- `0x18000f0dc`

## callees

- `0x18000a36c`
- `0x18000a620`
- `0x18000a920`
- `0x18000ef80`
- `0x18000fdf4`
- `0x180010e40`
- `0x180010e5c`
- `0x180010e78`
- `0x18001226c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a743`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000a743`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a864`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000a864`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a8d6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000a8d6`

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
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
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
0x18000a620  mov     [rsp+arg_10], rbx
0x18000a625  mov     [rsp+arg_8], edx
0x18000a629  mov     [rsp+arg_0], rcx
0x18000a62e  push    rbp
0x18000a62f  push    rsi
0x18000a630  push    rdi
0x18000a631  push    r12
0x18000a633  push    r13
0x18000a635  push    r14
0x18000a637  push    r15
0x18000a639  sub     rsp, 40h
0x18000a63d  mov     r12, r9
0x18000a640  mov     r13, r8
0x18000a643  mov     r10, rcx
0x18000a646  xor     eax, eax
0x18000a648  mov     rsi, [rsp+78h+lpOutputString]
0x18000a650  mov     [rsi], ax
0x18000a653  mov     rax, [rsp+78h+arg_60]
0x18000a65b  mov     byte ptr [rax], 0
0x18000a65e  mov     r14, [rsp+78h+arg_38]
0x18000a666  mov     edi, [r14]
0x18000a669  mov     rbx, [rsp+78h+arg_78]
0x18000a671  mov     [rbx+8], edi
0x18000a674  mov     eax, [r14+4]
0x18000a678  mov     [rbx+0Ch], eax
0x18000a67b  xor     ebp, ebp
0x18000a67d  mov     r15d, [rsp+78h+arg_30]
0x18000a685  mov     ecx, r15d
0x18000a688  test    r15d, r15d
0x18000a68b  jz      short loc_18000A6F3
0x18000a68d  sub     ecx, 1
0x18000a690  jz      short loc_18000A6EA
0x18000a692  sub     ecx, 1
0x18000a695  jz      short loc_18000A6A5
0x18000a697  cmp     ecx, 1
0x18000a69a  jnz     short loc_18000A6FC
0x18000a69c  mov     ecx, edi; this
0x18000a69e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000a6a3  jmp     short loc_18000A6FA
0x18000a6a5  test    edi, edi
0x18000a6a7  js      short loc_18000A6E1
0x18000a6a9  mov     edi, 8007029Ch
0x18000a6ae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000a6b2  mov     rax, [rsp+78h+arg_28]
0x18000a6ba  mov     [rsp+78h+var_50], rax; __int64
0x18000a6bf  mov     rax, [rsp+78h+arg_20]
0x18000a6c7  mov     [rsp+78h+var_58], rax; __int64
0x18000a6cc  mov     rcx, r10; int
0x18000a6cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000a6d4  mov     [rbx+8], edi
0x18000a6d7  mov     ecx, edi; this
0x18000a6d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a6de  mov     [rbx+0Ch], eax
0x18000a6e1  mov     ecx, edi; this
0x18000a6e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000a6e8  jmp     short loc_18000A6FA
0x18000a6ea  mov     ecx, edi; this
0x18000a6ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000a6f1  jmp     short loc_18000A6FA
0x18000a6f3  mov     ecx, edi; this
0x18000a6f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000a6fa  mov     ebp, eax
0x18000a6fc  mov     [rbx], r15d
0x18000a6ff  mov     eax, [rsp+78h+arg_70]
0x18000a706  mov     [rbx+4], eax
0x18000a709  cmp     dword ptr [r14+8], 1
0x18000a70e  jnz     short loc_18000A716
0x18000a710  or      eax, 8
0x18000a713  mov     [rbx+4], eax
0x18000a716  mov     eax, 1
0x18000a71b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000a723  inc     eax
0x18000a725  mov     [rbx+10h], eax
0x18000a728  mov     rax, [rsp+78h+arg_40]
0x18000a730  xor     edi, edi
0x18000a732  test    rax, rax
0x18000a735  jz      short loc_18000A73C
0x18000a737  cmp     [rax], di
0x18000a73a  jnz     short loc_18000A73F
0x18000a73c  mov     rax, rdi
0x18000a73f  mov     [rbx+18h], rax
0x18000a743  call    cs:__imp_GetCurrentThreadId
0x18000a749  mov     [rbx+20h], eax
0x18000a74c  mov     [rbx+38h], r13
0x18000a750  mov     eax, [rsp+78h+arg_8]
0x18000a757  mov     [rbx+40h], eax
0x18000a75a  mov     [rbx+44h], ebp
0x18000a75d  mov     rax, [rsp+78h+arg_20]
0x18000a765  mov     [rbx+28h], rax
0x18000a769  mov     [rbx+30h], r12
0x18000a76d  mov     rax, [rsp+78h+arg_28]
0x18000a775  mov     [rbx+88h], rax
0x18000a77c  mov     rax, [rsp+78h+arg_0]
0x18000a784  mov     [rbx+90h], rax
0x18000a78b  mov     [rbx+48h], rdi
0x18000a78f  xorps   xmm0, xmm0
0x18000a792  xor     eax, eax
0x18000a794  movups  xmmword ptr [rbx+68h], xmm0
0x18000a798  mov     [rbx+78h], rax
0x18000a79c  movups  xmmword ptr [rbx+50h], xmm0
0x18000a7a0  mov     [rbx+60h], rax
0x18000a7a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000a7ab  test    rax, rax
0x18000a7ae  jz      short loc_18000A7B7
0x18000a7b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7b5  jmp     short loc_18000A7BA
0x18000a7b7  mov     rax, rdi
0x18000a7ba  mov     [rbx+80h], rax
0x18000a7c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000a7c8  test    rax, rax
0x18000a7cb  jz      short loc_18000A7D5
0x18000a7cd  mov     rcx, rbx
0x18000a7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000a7dc  test    rax, rax
0x18000a7df  jz      short loc_18000A7F7
0x18000a7e1  mov     r8d, 400h
0x18000a7e7  mov     rdx, [rsp+78h+arg_60]
0x18000a7ef  mov     rcx, rbx
0x18000a7f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a7fe  test    rax, rax
0x18000a801  jz      short loc_18000A80B
0x18000a803  mov     rcx, rbx
0x18000a806  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a80b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000a812  test    rax, rax
0x18000a815  jz      short loc_18000A825
0x18000a817  test    byte ptr [rbx+4], 2
0x18000a81b  jnz     short loc_18000A825
0x18000a81d  mov     rcx, rbx
0x18000a820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a825  cmp     [rbx+8], edi
0x18000a828  jl      short loc_18000A846
0x18000a82a  cmp     r15d, 3
0x18000a82e  jz      short loc_18000A836
0x18000a830  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18000a836  mov     ecx, 8000FFFFh; this
0x18000a83b  mov     [rbx+8], ecx
0x18000a83e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000a843  mov     [rbx+0Ch], eax
0x18000a846  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000a84d  jnz     short loc_18000A86E
0x18000a84f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000a856  test    rax, rax
0x18000a859  jz      short loc_18000A864
0x18000a85b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a860  test    al, al
0x18000a862  jmp     short loc_18000A86C
0x18000a864  call    cs:__imp_IsDebuggerPresent
0x18000a86a  test    eax, eax
0x18000a86c  jz      short loc_18000A874
0x18000a86e  test    byte ptr [rbx+4], 2
0x18000a872  jz      short loc_18000A898
0x18000a874  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a87b  test    rax, rax
0x18000a87e  jz      short loc_18000A8DC
0x18000a880  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a887  jnz     short loc_18000A8DC
0x18000a889  xor     r8d, r8d
0x18000a88c  xor     edx, edx
0x18000a88e  mov     rcx, rbx
0x18000a891  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a896  jmp     short loc_18000A8DC
0x18000a898  mov     ebp, 800h
0x18000a89d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000a8a4  test    rax, rax
0x18000a8a7  jz      short loc_18000A8C0
0x18000a8a9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000a8b0  jnz     short loc_18000A8C0
0x18000a8b2  mov     r8d, ebp
0x18000a8b5  mov     rdx, rsi
0x18000a8b8  mov     rcx, rbx
0x18000a8bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8c0  cmp     [rsi], di
0x18000a8c3  jnz     short loc_18000A8D3
0x18000a8c5  mov     r8, rbx; unsigned __int64
0x18000a8c8  mov     rdx, rbp; unsigned __int16 *
0x18000a8cb  mov     rcx, rsi; this
0x18000a8ce  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000a8d3  mov     rcx, rsi; lpOutputString
0x18000a8d6  call    cs:__imp_OutputDebugStringW
0x18000a8dc  test    byte ptr [rbx+4], 4
0x18000a8e0  jnz     short loc_18000A8EB
0x18000a8e2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000a8e9  jz      short loc_18000A8FD
0x18000a8eb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000a8f2  test    rax, rax
0x18000a8f5  jz      short loc_18000A8FD
0x18000a8f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8fc  nop
0x18000a8fd  mov     rbx, [rsp+78h+arg_10]
0x18000a905  add     rsp, 40h
0x18000a909  pop     r15
0x18000a90b  pop     r14
0x18000a90d  pop     r13
0x18000a90f  pop     r12
0x18000a911  pop     rdi
0x18000a912  pop     rsi
0x18000a913  pop     rbp
0x18000a914  retn
```
