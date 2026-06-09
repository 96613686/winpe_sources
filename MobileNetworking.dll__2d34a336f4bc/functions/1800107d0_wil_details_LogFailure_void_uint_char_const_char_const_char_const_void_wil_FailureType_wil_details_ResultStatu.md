# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800107d0`
- end: `0x180010ac8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000f51c`
- `0x18000f86c`

## callees

- `0x180009234`
- `0x18000e4b0`
- `0x18000f464`
- `0x1800100fc`
- `0x1800107d0`
- `0x180010d2c`
- `0x180010d48`
- `0x180010d64`
- `0x1800115b4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108f3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108f3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010a12`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010a12`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010a84`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010a84`

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
0x1800107d0  mov     [rsp+arg_10], rbx
0x1800107d5  mov     [rsp+arg_8], edx
0x1800107d9  mov     [rsp+arg_0], rcx
0x1800107de  push    rbp
0x1800107df  push    rsi
0x1800107e0  push    rdi
0x1800107e1  push    r12
0x1800107e3  push    r13
0x1800107e5  push    r14
0x1800107e7  push    r15
0x1800107e9  sub     rsp, 40h
0x1800107ed  mov     r14, [rsp+78h+arg_38]
0x1800107f5  xor     eax, eax
0x1800107f7  mov     rbx, [rsp+78h+arg_78]
0x1800107ff  xor     ebp, ebp
0x180010801  mov     r15d, [rsp+78h+arg_30]
0x180010809  mov     r10, rcx
0x18001080c  mov     rsi, [rsp+78h+lpOutputString]
0x180010814  mov     r12, r9
0x180010817  mov     r13, r8
0x18001081a  mov     ecx, r15d
0x18001081d  mov     [rsi], ax
0x180010820  mov     rax, [rsp+78h+arg_60]
0x180010828  mov     byte ptr [rax], 0
0x18001082b  mov     edi, [r14]
0x18001082e  mov     [rbx+8], edi
0x180010831  mov     eax, [r14+4]
0x180010835  mov     [rbx+0Ch], eax
0x180010838  test    r15d, r15d
0x18001083b  jz      short loc_1800108A3
0x18001083d  sub     ecx, 1
0x180010840  jz      short loc_18001089A
0x180010842  sub     ecx, 1
0x180010845  jz      short loc_180010855
0x180010847  cmp     ecx, 1
0x18001084a  jnz     short loc_1800108AC
0x18001084c  mov     ecx, edi; this
0x18001084e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180010853  jmp     short loc_1800108AA
0x180010855  test    edi, edi
0x180010857  js      short loc_180010891
0x180010859  mov     rax, [rsp+78h+arg_28]
0x180010861  mov     edi, 8007029Ch
0x180010866  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001086a  mov     rcx, r10; int
0x18001086d  mov     [rsp+78h+var_50], rax; __int64
0x180010872  mov     rax, [rsp+78h+arg_20]
0x18001087a  mov     [rsp+78h+var_58], rax; __int64
0x18001087f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180010884  mov     ecx, edi; this
0x180010886  mov     [rbx+8], edi
0x180010889  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001088e  mov     [rbx+0Ch], eax
0x180010891  mov     ecx, edi; this
0x180010893  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180010898  jmp     short loc_1800108AA
0x18001089a  mov     ecx, edi; this
0x18001089c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800108a1  jmp     short loc_1800108AA
0x1800108a3  mov     ecx, edi; this
0x1800108a5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800108aa  mov     ebp, eax
0x1800108ac  mov     eax, [rsp+78h+arg_70]
0x1800108b3  mov     [rbx+4], eax
0x1800108b6  mov     [rbx], r15d
0x1800108b9  cmp     dword ptr [r14+8], 1
0x1800108be  jnz     short loc_1800108C6
0x1800108c0  or      eax, 8
0x1800108c3  mov     [rbx+4], eax
0x1800108c6  mov     eax, 1
0x1800108cb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800108d3  inc     eax
0x1800108d5  xor     edi, edi
0x1800108d7  mov     [rbx+10h], eax
0x1800108da  mov     rax, [rsp+78h+arg_40]
0x1800108e2  test    rax, rax
0x1800108e5  jz      short loc_1800108EC
0x1800108e7  cmp     [rax], di
0x1800108ea  jnz     short loc_1800108EF
0x1800108ec  mov     rax, rdi
0x1800108ef  mov     [rbx+18h], rax
0x1800108f3  call    cs:__imp_GetCurrentThreadId
0x1800108f9  mov     [rbx+38h], r13
0x1800108fd  xorps   xmm0, xmm0
0x180010900  mov     [rbx+20h], eax
0x180010903  mov     eax, [rsp+78h+arg_8]
0x18001090a  mov     [rbx+40h], eax
0x18001090d  mov     rax, [rsp+78h+arg_20]
0x180010915  mov     [rbx+28h], rax
0x180010919  mov     rax, [rsp+78h+arg_28]
0x180010921  mov     [rbx+88h], rax
0x180010928  mov     rax, [rsp+78h+arg_0]
0x180010930  mov     [rbx+90h], rax
0x180010937  xor     eax, eax
0x180010939  mov     [rbx+44h], ebp
0x18001093c  mov     [rbx+30h], r12
0x180010940  mov     [rbx+48h], rdi
0x180010944  movups  xmmword ptr [rbx+68h], xmm0
0x180010948  mov     [rbx+78h], rax
0x18001094c  movups  xmmword ptr [rbx+50h], xmm0
0x180010950  mov     [rbx+60h], rax
0x180010954  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001095b  test    rax, rax
0x18001095e  jz      short loc_180010967
0x180010960  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010965  jmp     short loc_18001096A
0x180010967  mov     rax, rdi
0x18001096a  mov     [rbx+80h], rax
0x180010971  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010978  test    rax, rax
0x18001097b  jz      short loc_180010985
0x18001097d  mov     rcx, rbx
0x180010980  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010985  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001098c  test    rax, rax
0x18001098f  jz      short loc_1800109A7
0x180010991  mov     rdx, [rsp+78h+arg_60]
0x180010999  mov     r8d, 400h
0x18001099f  mov     rcx, rbx
0x1800109a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109a7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800109ae  test    rax, rax
0x1800109b1  jz      short loc_1800109BB
0x1800109b3  mov     rcx, rbx
0x1800109b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109bb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800109c2  test    rax, rax
0x1800109c5  jz      short loc_1800109D5
0x1800109c7  test    byte ptr [rbx+4], 2
0x1800109cb  jnz     short loc_1800109D5
0x1800109cd  mov     rcx, rbx
0x1800109d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109d5  cmp     [rbx+8], edi
0x1800109d8  jl      short loc_1800109F4
0x1800109da  cmp     r15d, 3
0x1800109de  jnz     loc_180010AC2
0x1800109e4  mov     ecx, 8000FFFFh; this
0x1800109e9  mov     [rbx+8], ecx
0x1800109ec  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800109f1  mov     [rbx+0Ch], eax
0x1800109f4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800109fb  jnz     short loc_180010A1C
0x1800109fd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010a04  test    rax, rax
0x180010a07  jz      short loc_180010A12
0x180010a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a0e  test    al, al
0x180010a10  jmp     short loc_180010A1A
0x180010a12  call    cs:__imp_IsDebuggerPresent
0x180010a18  test    eax, eax
0x180010a1a  jz      short loc_180010A22
0x180010a1c  test    byte ptr [rbx+4], 2
0x180010a20  jz      short loc_180010A46
0x180010a22  mov     rax, cs:g_pfnResultLoggingCallback
0x180010a29  test    rax, rax
0x180010a2c  jz      short loc_180010A8A
0x180010a2e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010a35  jnz     short loc_180010A8A
0x180010a37  xor     r8d, r8d
0x180010a3a  xor     edx, edx
0x180010a3c  mov     rcx, rbx
0x180010a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a44  jmp     short loc_180010A8A
0x180010a46  mov     rax, cs:g_pfnResultLoggingCallback
0x180010a4d  mov     ebp, 800h
0x180010a52  test    rax, rax
0x180010a55  jz      short loc_180010A6E
0x180010a57  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010a5e  jnz     short loc_180010A6E
0x180010a60  mov     r8d, ebp
0x180010a63  mov     rdx, rsi
0x180010a66  mov     rcx, rbx
0x180010a69  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a6e  cmp     [rsi], di
0x180010a71  jnz     short loc_180010A81
0x180010a73  mov     r8, rbx; unsigned __int64
0x180010a76  mov     rdx, rbp; unsigned __int16 *
0x180010a79  mov     rcx, rsi; this
0x180010a7c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010a81  mov     rcx, rsi; lpOutputString
0x180010a84  call    cs:__imp_OutputDebugStringW
0x180010a8a  test    byte ptr [rbx+4], 4
0x180010a8e  jnz     short loc_180010A99
0x180010a90  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180010a97  jz      short loc_180010AAA
0x180010a99  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010aa0  test    rax, rax
0x180010aa3  jz      short loc_180010AAA
0x180010aa5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010aaa  mov     rbx, [rsp+78h+arg_10]
0x180010ab2  add     rsp, 40h
0x180010ab6  pop     r15
0x180010ab8  pop     r14
0x180010aba  pop     r13
0x180010abc  pop     r12
0x180010abe  pop     rdi
0x180010abf  pop     rsi
0x180010ac0  pop     rbp
0x180010ac1  retn
0x180010ac2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
