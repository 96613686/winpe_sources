# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18004a534`
- end: `0x18004a835`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `769`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180040bd0`
- `0x180040f1c`

## callees

- `0x1800383a8`
- `0x18003f554`
- `0x18003fa70`
- `0x180040b10`
- `0x18004a534`
- `0x18004ba00`
- `0x18004ba1c`
- `0x18004ba38`
- `0x18004c6e8`
- `0x1800b0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a65f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18004a65f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004a77e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18004a77e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004a7f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18004a7f0`

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
0x18004a534  mov     rax, rsp
0x18004a537  mov     [rax+10h], edx
0x18004a53a  mov     [rax+8], rcx
0x18004a53e  push    rbp
0x18004a53f  push    rsi
0x18004a540  push    rdi
0x18004a541  push    r12
0x18004a543  push    r13
0x18004a545  push    r14
0x18004a547  push    r15
0x18004a549  sub     rsp, 50h
0x18004a54d  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18004a555  mov     [rax+18h], rbx
0x18004a559  mov     r12, r9
0x18004a55c  mov     r13, r8
0x18004a55f  mov     r10, rcx
0x18004a562  xor     eax, eax
0x18004a564  mov     rsi, [rsp+88h+lpOutputString]
0x18004a56c  mov     [rsi], ax
0x18004a56f  mov     rax, [rsp+88h+arg_60]
0x18004a577  mov     byte ptr [rax], 0
0x18004a57a  mov     r14, [rsp+88h+arg_38]
0x18004a582  mov     edi, [r14]
0x18004a585  mov     rbx, [rsp+88h+arg_78]
0x18004a58d  mov     [rbx+8], edi
0x18004a590  mov     eax, [r14+4]
0x18004a594  mov     [rbx+0Ch], eax
0x18004a597  xor     ebp, ebp
0x18004a599  mov     r15d, [rsp+88h+arg_30]
0x18004a5a1  mov     ecx, r15d
0x18004a5a4  test    r15d, r15d
0x18004a5a7  jz      short loc_18004A60F
0x18004a5a9  sub     ecx, 1
0x18004a5ac  jz      short loc_18004A606
0x18004a5ae  sub     ecx, 1
0x18004a5b1  jz      short loc_18004A5C1
0x18004a5b3  cmp     ecx, 1
0x18004a5b6  jnz     short loc_18004A618
0x18004a5b8  mov     ecx, edi; this
0x18004a5ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18004a5bf  jmp     short loc_18004A616
0x18004a5c1  test    edi, edi
0x18004a5c3  js      short loc_18004A5FD
0x18004a5c5  mov     edi, 8007029Ch
0x18004a5ca  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18004a5ce  mov     rax, [rsp+88h+arg_28]
0x18004a5d6  mov     [rsp+88h+var_60], rax; __int64
0x18004a5db  mov     rax, [rsp+88h+arg_20]
0x18004a5e3  mov     [rsp+88h+var_68], rax; __int64
0x18004a5e8  mov     rcx, r10; int
0x18004a5eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18004a5f0  mov     [rbx+8], edi
0x18004a5f3  mov     ecx, edi; this
0x18004a5f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004a5fa  mov     [rbx+0Ch], eax
0x18004a5fd  mov     ecx, edi; this
0x18004a5ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18004a604  jmp     short loc_18004A616
0x18004a606  mov     ecx, edi; this
0x18004a608  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18004a60d  jmp     short loc_18004A616
0x18004a60f  mov     ecx, edi; this
0x18004a611  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18004a616  mov     ebp, eax
0x18004a618  mov     [rbx], r15d
0x18004a61b  mov     eax, [rsp+88h+arg_70]
0x18004a622  mov     [rbx+4], eax
0x18004a625  cmp     dword ptr [r14+8], 1
0x18004a62a  jnz     short loc_18004A632
0x18004a62c  or      eax, 8
0x18004a62f  mov     [rbx+4], eax
0x18004a632  mov     eax, 1
0x18004a637  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18004a63f  inc     eax
0x18004a641  mov     [rbx+10h], eax
0x18004a644  mov     rax, [rsp+88h+arg_40]
0x18004a64c  xor     edi, edi
0x18004a64e  test    rax, rax
0x18004a651  jz      short loc_18004A658
0x18004a653  cmp     [rax], di
0x18004a656  jnz     short loc_18004A65B
0x18004a658  mov     rax, rdi
0x18004a65b  mov     [rbx+18h], rax
0x18004a65f  call    cs:__imp_GetCurrentThreadId
0x18004a665  mov     [rbx+20h], eax
0x18004a668  mov     [rbx+38h], r13
0x18004a66c  mov     eax, [rsp+88h+arg_8]
0x18004a673  mov     [rbx+40h], eax
0x18004a676  mov     [rbx+44h], ebp
0x18004a679  mov     rax, [rsp+88h+arg_20]
0x18004a681  mov     [rbx+28h], rax
0x18004a685  mov     [rbx+30h], r12
0x18004a689  mov     rax, [rsp+88h+arg_28]
0x18004a691  mov     [rbx+88h], rax
0x18004a698  mov     rax, [rsp+88h+arg_0]
0x18004a6a0  mov     [rbx+90h], rax
0x18004a6a7  mov     [rbx+48h], rdi
0x18004a6ab  xorps   xmm0, xmm0
0x18004a6ae  xor     eax, eax
0x18004a6b0  movups  xmmword ptr [rbx+68h], xmm0
0x18004a6b4  mov     [rbx+78h], rax
0x18004a6b8  movups  xmmword ptr [rbx+50h], xmm0
0x18004a6bc  mov     [rbx+60h], rax
0x18004a6c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18004a6c7  test    rax, rax
0x18004a6ca  jz      short loc_18004A6D3
0x18004a6cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6d1  jmp     short loc_18004A6D6
0x18004a6d3  mov     rax, rdi
0x18004a6d6  mov     [rbx+80h], rax
0x18004a6dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18004a6e4  test    rax, rax
0x18004a6e7  jz      short loc_18004A6F1
0x18004a6e9  mov     rcx, rbx
0x18004a6ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a6f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18004a6f8  test    rax, rax
0x18004a6fb  jz      short loc_18004A713
0x18004a6fd  mov     r8d, 400h
0x18004a703  mov     rdx, [rsp+88h+arg_60]
0x18004a70b  mov     rcx, rbx
0x18004a70e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a713  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004a71a  test    rax, rax
0x18004a71d  jz      short loc_18004A727
0x18004a71f  mov     rcx, rbx
0x18004a722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a727  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18004a72e  test    rax, rax
0x18004a731  jz      short loc_18004A741
0x18004a733  test    byte ptr [rbx+4], 2
0x18004a737  jnz     short loc_18004A741
0x18004a739  mov     rcx, rbx
0x18004a73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a741  cmp     [rbx+8], edi
0x18004a744  jl      short loc_18004A760
0x18004a746  cmp     r15d, 3
0x18004a74a  jnz     loc_18004A82F
0x18004a750  mov     ecx, 8000FFFFh; this
0x18004a755  mov     [rbx+8], ecx
0x18004a758  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18004a75d  mov     [rbx+0Ch], eax
0x18004a760  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18004a767  jnz     short loc_18004A788
0x18004a769  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18004a770  test    rax, rax
0x18004a773  jz      short loc_18004A77E
0x18004a775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a77a  test    al, al
0x18004a77c  jmp     short loc_18004A786
0x18004a77e  call    cs:__imp_IsDebuggerPresent
0x18004a784  test    eax, eax
0x18004a786  jz      short loc_18004A78E
0x18004a788  test    byte ptr [rbx+4], 2
0x18004a78c  jz      short loc_18004A7B2
0x18004a78e  mov     rax, cs:g_pfnResultLoggingCallback
0x18004a795  test    rax, rax
0x18004a798  jz      short loc_18004A7F6
0x18004a79a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004a7a1  jnz     short loc_18004A7F6
0x18004a7a3  xor     r8d, r8d
0x18004a7a6  xor     edx, edx
0x18004a7a8  mov     rcx, rbx
0x18004a7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7b0  jmp     short loc_18004A7F6
0x18004a7b2  mov     ebp, 800h
0x18004a7b7  mov     rax, cs:g_pfnResultLoggingCallback
0x18004a7be  test    rax, rax
0x18004a7c1  jz      short loc_18004A7DA
0x18004a7c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18004a7ca  jnz     short loc_18004A7DA
0x18004a7cc  mov     r8d, ebp
0x18004a7cf  mov     rdx, rsi
0x18004a7d2  mov     rcx, rbx
0x18004a7d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a7da  cmp     [rsi], di
0x18004a7dd  jnz     short loc_18004A7ED
0x18004a7df  mov     r8, rbx; unsigned __int64
0x18004a7e2  mov     rdx, rbp; unsigned __int16 *
0x18004a7e5  mov     rcx, rsi; this
0x18004a7e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18004a7ed  mov     rcx, rsi; lpOutputString
0x18004a7f0  call    cs:__imp_OutputDebugStringW
0x18004a7f6  test    byte ptr [rbx+4], 4
0x18004a7fa  jnz     short loc_18004A805
0x18004a7fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18004a803  jz      short loc_18004A817
0x18004a805  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18004a80c  test    rax, rax
0x18004a80f  jz      short loc_18004A817
0x18004a811  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004a816  nop
0x18004a817  mov     rbx, [rsp+88h+arg_10]
0x18004a81f  add     rsp, 50h
0x18004a823  pop     r15
0x18004a825  pop     r14
0x18004a827  pop     r13
0x18004a829  pop     r12
0x18004a82b  pop     rdi
0x18004a82c  pop     rsi
0x18004a82d  pop     rbp
0x18004a82e  retn
0x18004a82f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
