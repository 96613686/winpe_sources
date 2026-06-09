# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000df90`
- end: `0x18000e289`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000a4ec`

## callees

- `0x180009ef8`
- `0x18000d284`
- `0x18000db8c`
- `0x18000df90`
- `0x18000f06c`
- `0x18000f090`
- `0x18000f1bc`
- `0x18000f1d8`
- `0x180012104`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e0b3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e0b3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e1d2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e1d2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e244`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e244`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v27)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x18000df90  mov     [rsp+arg_10], rbx
0x18000df95  mov     [rsp+arg_8], edx
0x18000df99  mov     [rsp+arg_0], rcx
0x18000df9e  push    rbp
0x18000df9f  push    rsi
0x18000dfa0  push    rdi
0x18000dfa1  push    r12
0x18000dfa3  push    r13
0x18000dfa5  push    r14
0x18000dfa7  push    r15
0x18000dfa9  sub     rsp, 40h
0x18000dfad  mov     r12, r9
0x18000dfb0  mov     r13, r8
0x18000dfb3  mov     r10, rcx
0x18000dfb6  xor     eax, eax
0x18000dfb8  mov     rsi, [rsp+78h+lpOutputString]
0x18000dfc0  mov     [rsi], ax
0x18000dfc3  mov     rax, [rsp+78h+arg_60]
0x18000dfcb  mov     byte ptr [rax], 0
0x18000dfce  mov     r14, [rsp+78h+arg_38]
0x18000dfd6  mov     edi, [r14]
0x18000dfd9  mov     rbx, [rsp+78h+arg_78]
0x18000dfe1  mov     [rbx+8], edi
0x18000dfe4  mov     eax, [r14+4]
0x18000dfe8  mov     [rbx+0Ch], eax
0x18000dfeb  xor     ebp, ebp
0x18000dfed  mov     r15d, [rsp+78h+arg_30]
0x18000dff5  mov     ecx, r15d
0x18000dff8  test    r15d, r15d
0x18000dffb  jz      short loc_18000E063
0x18000dffd  sub     ecx, 1
0x18000e000  jz      short loc_18000E05A
0x18000e002  sub     ecx, 1
0x18000e005  jz      short loc_18000E015
0x18000e007  cmp     ecx, 1
0x18000e00a  jnz     short loc_18000E06C
0x18000e00c  mov     ecx, edi; this
0x18000e00e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e013  jmp     short loc_18000E06A
0x18000e015  test    edi, edi
0x18000e017  js      short loc_18000E051
0x18000e019  mov     edi, 8007029Ch
0x18000e01e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e022  mov     rax, [rsp+78h+arg_28]
0x18000e02a  mov     [rsp+78h+var_50], rax; __int64
0x18000e02f  mov     rax, [rsp+78h+arg_20]
0x18000e037  mov     [rsp+78h+var_58], rax; __int64
0x18000e03c  mov     rcx, r10; int
0x18000e03f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e044  mov     [rbx+8], edi
0x18000e047  mov     ecx, edi; this
0x18000e049  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e04e  mov     [rbx+0Ch], eax
0x18000e051  mov     ecx, edi; this
0x18000e053  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e058  jmp     short loc_18000E06A
0x18000e05a  mov     ecx, edi; this
0x18000e05c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e061  jmp     short loc_18000E06A
0x18000e063  mov     ecx, edi; this
0x18000e065  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e06a  mov     ebp, eax
0x18000e06c  mov     [rbx], r15d
0x18000e06f  mov     eax, [rsp+78h+arg_70]
0x18000e076  mov     [rbx+4], eax
0x18000e079  cmp     dword ptr [r14+8], 1
0x18000e07e  jnz     short loc_18000E086
0x18000e080  or      eax, 8
0x18000e083  mov     [rbx+4], eax
0x18000e086  mov     eax, 1
0x18000e08b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e093  inc     eax
0x18000e095  mov     [rbx+10h], eax
0x18000e098  mov     rax, [rsp+78h+arg_40]
0x18000e0a0  xor     edi, edi
0x18000e0a2  test    rax, rax
0x18000e0a5  jz      short loc_18000E0AC
0x18000e0a7  cmp     [rax], di
0x18000e0aa  jnz     short loc_18000E0AF
0x18000e0ac  mov     rax, rdi
0x18000e0af  mov     [rbx+18h], rax
0x18000e0b3  call    cs:__imp_GetCurrentThreadId
0x18000e0b9  mov     [rbx+20h], eax
0x18000e0bc  mov     [rbx+38h], r13
0x18000e0c0  mov     eax, [rsp+78h+arg_8]
0x18000e0c7  mov     [rbx+40h], eax
0x18000e0ca  mov     [rbx+44h], ebp
0x18000e0cd  mov     rax, [rsp+78h+arg_20]
0x18000e0d5  mov     [rbx+28h], rax
0x18000e0d9  mov     [rbx+30h], r12
0x18000e0dd  mov     rax, [rsp+78h+arg_28]
0x18000e0e5  mov     [rbx+88h], rax
0x18000e0ec  mov     rax, [rsp+78h+arg_0]
0x18000e0f4  mov     [rbx+90h], rax
0x18000e0fb  mov     [rbx+48h], rdi
0x18000e0ff  xorps   xmm0, xmm0
0x18000e102  xor     eax, eax
0x18000e104  movups  xmmword ptr [rbx+68h], xmm0
0x18000e108  mov     [rbx+78h], rax
0x18000e10c  movups  xmmword ptr [rbx+50h], xmm0
0x18000e110  mov     [rbx+60h], rax
0x18000e114  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e11b  test    rax, rax
0x18000e11e  jz      short loc_18000E127
0x18000e120  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e125  jmp     short loc_18000E12A
0x18000e127  mov     rax, rdi
0x18000e12a  mov     [rbx+80h], rax
0x18000e131  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e138  test    rax, rax
0x18000e13b  jz      short loc_18000E145
0x18000e13d  mov     rcx, rbx
0x18000e140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e145  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e14c  test    rax, rax
0x18000e14f  jz      short loc_18000E167
0x18000e151  mov     r8d, 400h
0x18000e157  mov     rdx, [rsp+78h+arg_60]
0x18000e15f  mov     rcx, rbx
0x18000e162  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e167  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e16e  test    rax, rax
0x18000e171  jz      short loc_18000E17B
0x18000e173  mov     rcx, rbx
0x18000e176  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e17b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e182  test    rax, rax
0x18000e185  jz      short loc_18000E195
0x18000e187  test    byte ptr [rbx+4], 2
0x18000e18b  jnz     short loc_18000E195
0x18000e18d  mov     rcx, rbx
0x18000e190  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e195  cmp     [rbx+8], edi
0x18000e198  jl      short loc_18000E1B4
0x18000e19a  cmp     r15d, 3
0x18000e19e  jnz     loc_18000E283
0x18000e1a4  mov     ecx, 8000FFFFh; this
0x18000e1a9  mov     [rbx+8], ecx
0x18000e1ac  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e1b1  mov     [rbx+0Ch], eax
0x18000e1b4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e1bb  jnz     short loc_18000E1DC
0x18000e1bd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e1c4  test    rax, rax
0x18000e1c7  jz      short loc_18000E1D2
0x18000e1c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e1ce  test    al, al
0x18000e1d0  jmp     short loc_18000E1DA
0x18000e1d2  call    cs:__imp_IsDebuggerPresent
0x18000e1d8  test    eax, eax
0x18000e1da  jz      short loc_18000E1E2
0x18000e1dc  test    byte ptr [rbx+4], 2
0x18000e1e0  jz      short loc_18000E206
0x18000e1e2  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e1e9  test    rax, rax
0x18000e1ec  jz      short loc_18000E24A
0x18000e1ee  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e1f5  jnz     short loc_18000E24A
0x18000e1f7  xor     r8d, r8d
0x18000e1fa  xor     edx, edx
0x18000e1fc  mov     rcx, rbx
0x18000e1ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e204  jmp     short loc_18000E24A
0x18000e206  mov     ebp, 800h
0x18000e20b  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e212  test    rax, rax
0x18000e215  jz      short loc_18000E22E
0x18000e217  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e21e  jnz     short loc_18000E22E
0x18000e220  mov     r8d, ebp
0x18000e223  mov     rdx, rsi
0x18000e226  mov     rcx, rbx
0x18000e229  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e22e  cmp     [rsi], di
0x18000e231  jnz     short loc_18000E241
0x18000e233  mov     r8, rbx; unsigned __int64
0x18000e236  mov     rdx, rbp; unsigned __int16 *
0x18000e239  mov     rcx, rsi; this
0x18000e23c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e241  mov     rcx, rsi; lpOutputString
0x18000e244  call    cs:__imp_OutputDebugStringW
0x18000e24a  test    byte ptr [rbx+4], 4
0x18000e24e  jnz     short loc_18000E259
0x18000e250  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e257  jz      short loc_18000E26B
0x18000e259  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e260  test    rax, rax
0x18000e263  jz      short loc_18000E26B
0x18000e265  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e26a  nop
0x18000e26b  mov     rbx, [rsp+78h+arg_10]
0x18000e273  add     rsp, 40h
0x18000e277  pop     r15
0x18000e279  pop     r14
0x18000e27b  pop     r13
0x18000e27d  pop     r12
0x18000e27f  pop     rdi
0x18000e280  pop     rsi
0x18000e281  pop     rbp
0x18000e282  retn
0x18000e283  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
