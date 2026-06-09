# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006460`
- end: `0x140006759`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140004b34`
- `0x140004e90`
- `0x140007c6c`

## callees

- `0x140004a74`
- `0x140005a74`
- `0x140006170`
- `0x140006460`
- `0x140006a5c`
- `0x140006a80`
- `0x140006a94`
- `0x140006ab0`
- `0x140007754`
- `0x14000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006583`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140006583`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006714`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006714`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400066a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400066a2`

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
0x140006460  mov     [rsp+arg_10], rbx
0x140006465  mov     [rsp+arg_8], edx
0x140006469  mov     [rsp+arg_0], rcx
0x14000646e  push    rbp
0x14000646f  push    rsi
0x140006470  push    rdi
0x140006471  push    r12
0x140006473  push    r13
0x140006475  push    r14
0x140006477  push    r15
0x140006479  sub     rsp, 40h
0x14000647d  mov     r12, r9
0x140006480  mov     r13, r8
0x140006483  mov     r10, rcx
0x140006486  xor     eax, eax
0x140006488  mov     rsi, [rsp+78h+lpOutputString]
0x140006490  mov     [rsi], ax
0x140006493  mov     rax, [rsp+78h+arg_60]
0x14000649b  mov     byte ptr [rax], 0
0x14000649e  mov     r14, [rsp+78h+arg_38]
0x1400064a6  mov     edi, [r14]
0x1400064a9  mov     rbx, [rsp+78h+arg_78]
0x1400064b1  mov     [rbx+8], edi
0x1400064b4  mov     eax, [r14+4]
0x1400064b8  mov     [rbx+0Ch], eax
0x1400064bb  xor     ebp, ebp
0x1400064bd  mov     r15d, [rsp+78h+arg_30]
0x1400064c5  mov     ecx, r15d
0x1400064c8  test    r15d, r15d
0x1400064cb  jz      short loc_140006533
0x1400064cd  sub     ecx, 1
0x1400064d0  jz      short loc_14000652A
0x1400064d2  sub     ecx, 1
0x1400064d5  jz      short loc_1400064E5
0x1400064d7  cmp     ecx, 1
0x1400064da  jnz     short loc_14000653C
0x1400064dc  mov     ecx, edi; this
0x1400064de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400064e3  jmp     short loc_14000653A
0x1400064e5  test    edi, edi
0x1400064e7  js      short loc_140006521
0x1400064e9  mov     edi, 8007029Ch
0x1400064ee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400064f2  mov     rax, [rsp+78h+arg_28]
0x1400064fa  mov     [rsp+78h+var_50], rax; __int64
0x1400064ff  mov     rax, [rsp+78h+arg_20]
0x140006507  mov     [rsp+78h+var_58], rax; __int64
0x14000650c  mov     rcx, r10; int
0x14000650f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006514  mov     [rbx+8], edi
0x140006517  mov     ecx, edi; this
0x140006519  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000651e  mov     [rbx+0Ch], eax
0x140006521  mov     ecx, edi; this
0x140006523  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006528  jmp     short loc_14000653A
0x14000652a  mov     ecx, edi; this
0x14000652c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006531  jmp     short loc_14000653A
0x140006533  mov     ecx, edi; this
0x140006535  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000653a  mov     ebp, eax
0x14000653c  mov     [rbx], r15d
0x14000653f  mov     eax, [rsp+78h+arg_70]
0x140006546  mov     [rbx+4], eax
0x140006549  cmp     dword ptr [r14+8], 1
0x14000654e  jnz     short loc_140006556
0x140006550  or      eax, 8
0x140006553  mov     [rbx+4], eax
0x140006556  mov     eax, 1
0x14000655b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006563  inc     eax
0x140006565  mov     [rbx+10h], eax
0x140006568  mov     rax, [rsp+78h+arg_40]
0x140006570  xor     edi, edi
0x140006572  test    rax, rax
0x140006575  jz      short loc_14000657C
0x140006577  cmp     [rax], di
0x14000657a  jnz     short loc_14000657F
0x14000657c  mov     rax, rdi
0x14000657f  mov     [rbx+18h], rax
0x140006583  call    cs:__imp_GetCurrentThreadId
0x140006589  mov     [rbx+20h], eax
0x14000658c  mov     [rbx+38h], r13
0x140006590  mov     eax, [rsp+78h+arg_8]
0x140006597  mov     [rbx+40h], eax
0x14000659a  mov     [rbx+44h], ebp
0x14000659d  mov     rax, [rsp+78h+arg_20]
0x1400065a5  mov     [rbx+28h], rax
0x1400065a9  mov     [rbx+30h], r12
0x1400065ad  mov     rax, [rsp+78h+arg_28]
0x1400065b5  mov     [rbx+88h], rax
0x1400065bc  mov     rax, [rsp+78h+arg_0]
0x1400065c4  mov     [rbx+90h], rax
0x1400065cb  mov     [rbx+48h], rdi
0x1400065cf  xorps   xmm0, xmm0
0x1400065d2  xor     eax, eax
0x1400065d4  movups  xmmword ptr [rbx+68h], xmm0
0x1400065d8  mov     [rbx+78h], rax
0x1400065dc  movups  xmmword ptr [rbx+50h], xmm0
0x1400065e0  mov     [rbx+60h], rax
0x1400065e4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400065eb  test    rax, rax
0x1400065ee  jz      short loc_1400065F7
0x1400065f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400065f5  jmp     short loc_1400065FA
0x1400065f7  mov     rax, rdi
0x1400065fa  mov     [rbx+80h], rax
0x140006601  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006608  test    rax, rax
0x14000660b  jz      short loc_140006615
0x14000660d  mov     rcx, rbx
0x140006610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006615  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000661c  test    rax, rax
0x14000661f  jz      short loc_140006637
0x140006621  mov     r8d, 400h
0x140006627  mov     rdx, [rsp+78h+arg_60]
0x14000662f  mov     rcx, rbx
0x140006632  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006637  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000663e  test    rax, rax
0x140006641  jz      short loc_14000664B
0x140006643  mov     rcx, rbx
0x140006646  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000664b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006652  test    rax, rax
0x140006655  jz      short loc_140006665
0x140006657  test    byte ptr [rbx+4], 2
0x14000665b  jnz     short loc_140006665
0x14000665d  mov     rcx, rbx
0x140006660  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006665  cmp     [rbx+8], edi
0x140006668  jl      short loc_140006684
0x14000666a  cmp     r15d, 3
0x14000666e  jnz     loc_140006753
0x140006674  mov     ecx, 8000FFFFh; this
0x140006679  mov     [rbx+8], ecx
0x14000667c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006681  mov     [rbx+0Ch], eax
0x140006684  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000668b  jnz     short loc_1400066AC
0x14000668d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006694  test    rax, rax
0x140006697  jz      short loc_1400066A2
0x140006699  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000669e  test    al, al
0x1400066a0  jmp     short loc_1400066AA
0x1400066a2  call    cs:__imp_IsDebuggerPresent
0x1400066a8  test    eax, eax
0x1400066aa  jz      short loc_1400066B2
0x1400066ac  test    byte ptr [rbx+4], 2
0x1400066b0  jz      short loc_1400066D6
0x1400066b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400066b9  test    rax, rax
0x1400066bc  jz      short loc_14000671A
0x1400066be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400066c5  jnz     short loc_14000671A
0x1400066c7  xor     r8d, r8d
0x1400066ca  xor     edx, edx
0x1400066cc  mov     rcx, rbx
0x1400066cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066d4  jmp     short loc_14000671A
0x1400066d6  mov     ebp, 800h
0x1400066db  mov     rax, cs:g_pfnResultLoggingCallback
0x1400066e2  test    rax, rax
0x1400066e5  jz      short loc_1400066FE
0x1400066e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400066ee  jnz     short loc_1400066FE
0x1400066f0  mov     r8d, ebp
0x1400066f3  mov     rdx, rsi
0x1400066f6  mov     rcx, rbx
0x1400066f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400066fe  cmp     [rsi], di
0x140006701  jnz     short loc_140006711
0x140006703  mov     r8, rbx; unsigned __int64
0x140006706  mov     rdx, rbp; unsigned __int16 *
0x140006709  mov     rcx, rsi; this
0x14000670c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006711  mov     rcx, rsi; lpOutputString
0x140006714  call    cs:__imp_OutputDebugStringW
0x14000671a  test    byte ptr [rbx+4], 4
0x14000671e  jnz     short loc_140006729
0x140006720  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006727  jz      short loc_14000673B
0x140006729  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006730  test    rax, rax
0x140006733  jz      short loc_14000673B
0x140006735  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000673a  nop
0x14000673b  mov     rbx, [rsp+78h+arg_10]
0x140006743  add     rsp, 40h
0x140006747  pop     r15
0x140006749  pop     r14
0x14000674b  pop     r13
0x14000674d  pop     r12
0x14000674f  pop     rdi
0x140006750  pop     rsi
0x140006751  pop     rbp
0x140006752  retn
0x140006753  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
