# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002b1b8`
- end: `0x18002b4ad`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800295dc`
- `0x18002968c`
- `0x180029780`

## callees

- `0x180023e20`
- `0x180029530`
- `0x18002a894`
- `0x18002b1b8`
- `0x18002bda4`
- `0x18002bdc0`
- `0x18002be7c`
- `0x18002be98`
- `0x18002d428`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b2db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18002b2db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b3fc`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18002b3fc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002b46e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002b46e`

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
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x18002b1b8  mov     [rsp+arg_10], rbx
0x18002b1bd  mov     [rsp+arg_8], edx
0x18002b1c1  mov     [rsp+arg_0], rcx
0x18002b1c6  push    rbp
0x18002b1c7  push    rsi
0x18002b1c8  push    rdi
0x18002b1c9  push    r12
0x18002b1cb  push    r13
0x18002b1cd  push    r14
0x18002b1cf  push    r15
0x18002b1d1  sub     rsp, 40h
0x18002b1d5  mov     r12, r9
0x18002b1d8  mov     r13, r8
0x18002b1db  mov     r10, rcx
0x18002b1de  xor     eax, eax
0x18002b1e0  mov     rsi, [rsp+78h+lpOutputString]
0x18002b1e8  mov     [rsi], ax
0x18002b1eb  mov     rax, [rsp+78h+arg_60]
0x18002b1f3  mov     byte ptr [rax], 0
0x18002b1f6  mov     r14, [rsp+78h+arg_38]
0x18002b1fe  mov     edi, [r14]
0x18002b201  mov     rbx, [rsp+78h+arg_78]
0x18002b209  mov     [rbx+8], edi
0x18002b20c  mov     eax, [r14+4]
0x18002b210  mov     [rbx+0Ch], eax
0x18002b213  xor     ebp, ebp
0x18002b215  mov     r15d, [rsp+78h+arg_30]
0x18002b21d  mov     ecx, r15d
0x18002b220  test    r15d, r15d
0x18002b223  jz      short loc_18002B28B
0x18002b225  sub     ecx, 1
0x18002b228  jz      short loc_18002B282
0x18002b22a  sub     ecx, 1
0x18002b22d  jz      short loc_18002B23D
0x18002b22f  cmp     ecx, 1
0x18002b232  jnz     short loc_18002B294
0x18002b234  mov     ecx, edi; this
0x18002b236  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002b23b  jmp     short loc_18002B292
0x18002b23d  test    edi, edi
0x18002b23f  js      short loc_18002B279
0x18002b241  mov     edi, 8007029Ch
0x18002b246  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18002b24a  mov     rax, [rsp+78h+arg_28]
0x18002b252  mov     [rsp+78h+var_50], rax; __int64
0x18002b257  mov     rax, [rsp+78h+arg_20]
0x18002b25f  mov     [rsp+78h+var_58], rax; __int64
0x18002b264  mov     rcx, r10; int
0x18002b267  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002b26c  mov     [rbx+8], edi
0x18002b26f  mov     ecx, edi; this
0x18002b271  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b276  mov     [rbx+0Ch], eax
0x18002b279  mov     ecx, edi; this
0x18002b27b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002b280  jmp     short loc_18002B292
0x18002b282  mov     ecx, edi; this
0x18002b284  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002b289  jmp     short loc_18002B292
0x18002b28b  mov     ecx, edi; this
0x18002b28d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002b292  mov     ebp, eax
0x18002b294  mov     [rbx], r15d
0x18002b297  mov     eax, [rsp+78h+arg_70]
0x18002b29e  mov     [rbx+4], eax
0x18002b2a1  cmp     dword ptr [r14+8], 1
0x18002b2a6  jnz     short loc_18002B2AE
0x18002b2a8  or      eax, 8
0x18002b2ab  mov     [rbx+4], eax
0x18002b2ae  mov     eax, 1
0x18002b2b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002b2bb  inc     eax
0x18002b2bd  mov     [rbx+10h], eax
0x18002b2c0  mov     rax, [rsp+78h+arg_40]
0x18002b2c8  xor     edi, edi
0x18002b2ca  test    rax, rax
0x18002b2cd  jz      short loc_18002B2D4
0x18002b2cf  cmp     [rax], di
0x18002b2d2  jnz     short loc_18002B2D7
0x18002b2d4  mov     rax, rdi
0x18002b2d7  mov     [rbx+18h], rax
0x18002b2db  call    cs:__imp_GetCurrentThreadId
0x18002b2e1  mov     [rbx+20h], eax
0x18002b2e4  mov     [rbx+38h], r13
0x18002b2e8  mov     eax, [rsp+78h+arg_8]
0x18002b2ef  mov     [rbx+40h], eax
0x18002b2f2  mov     [rbx+44h], ebp
0x18002b2f5  mov     rax, [rsp+78h+arg_20]
0x18002b2fd  mov     [rbx+28h], rax
0x18002b301  mov     [rbx+30h], r12
0x18002b305  mov     rax, [rsp+78h+arg_28]
0x18002b30d  mov     [rbx+88h], rax
0x18002b314  mov     rax, [rsp+78h+arg_0]
0x18002b31c  mov     [rbx+90h], rax
0x18002b323  mov     [rbx+48h], rdi
0x18002b327  xorps   xmm0, xmm0
0x18002b32a  xor     eax, eax
0x18002b32c  movups  xmmword ptr [rbx+68h], xmm0
0x18002b330  mov     [rbx+78h], rax
0x18002b334  movups  xmmword ptr [rbx+50h], xmm0
0x18002b338  mov     [rbx+60h], rax
0x18002b33c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002b343  test    rax, rax
0x18002b346  jz      short loc_18002B34F
0x18002b348  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b34d  jmp     short loc_18002B352
0x18002b34f  mov     rax, rdi
0x18002b352  mov     [rbx+80h], rax
0x18002b359  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002b360  test    rax, rax
0x18002b363  jz      short loc_18002B36D
0x18002b365  mov     rcx, rbx
0x18002b368  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b36d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002b374  test    rax, rax
0x18002b377  jz      short loc_18002B38F
0x18002b379  mov     r8d, 400h
0x18002b37f  mov     rdx, [rsp+78h+arg_60]
0x18002b387  mov     rcx, rbx
0x18002b38a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b38f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b396  test    rax, rax
0x18002b399  jz      short loc_18002B3A3
0x18002b39b  mov     rcx, rbx
0x18002b39e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002b3aa  test    rax, rax
0x18002b3ad  jz      short loc_18002B3BD
0x18002b3af  test    byte ptr [rbx+4], 2
0x18002b3b3  jnz     short loc_18002B3BD
0x18002b3b5  mov     rcx, rbx
0x18002b3b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3bd  cmp     [rbx+8], edi
0x18002b3c0  jl      short loc_18002B3DE
0x18002b3c2  cmp     r15d, 3
0x18002b3c6  jz      short loc_18002B3CE
0x18002b3c8  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002b3ce  mov     ecx, 8000FFFFh; this
0x18002b3d3  mov     [rbx+8], ecx
0x18002b3d6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002b3db  mov     [rbx+0Ch], eax
0x18002b3de  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002b3e5  jnz     short loc_18002B406
0x18002b3e7  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002b3ee  test    rax, rax
0x18002b3f1  jz      short loc_18002B3FC
0x18002b3f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b3f8  test    al, al
0x18002b3fa  jmp     short loc_18002B404
0x18002b3fc  call    cs:__imp_IsDebuggerPresent
0x18002b402  test    eax, eax
0x18002b404  jz      short loc_18002B40C
0x18002b406  test    byte ptr [rbx+4], 2
0x18002b40a  jz      short loc_18002B430
0x18002b40c  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b413  test    rax, rax
0x18002b416  jz      short loc_18002B474
0x18002b418  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b41f  jnz     short loc_18002B474
0x18002b421  xor     r8d, r8d
0x18002b424  xor     edx, edx
0x18002b426  mov     rcx, rbx
0x18002b429  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b42e  jmp     short loc_18002B474
0x18002b430  mov     ebp, 800h
0x18002b435  mov     rax, cs:g_pfnResultLoggingCallback
0x18002b43c  test    rax, rax
0x18002b43f  jz      short loc_18002B458
0x18002b441  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002b448  jnz     short loc_18002B458
0x18002b44a  mov     r8d, ebp
0x18002b44d  mov     rdx, rsi
0x18002b450  mov     rcx, rbx
0x18002b453  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b458  cmp     [rsi], di
0x18002b45b  jnz     short loc_18002B46B
0x18002b45d  mov     r8, rbx; unsigned __int64
0x18002b460  mov     rdx, rbp; wchar_t *
0x18002b463  mov     rcx, rsi; this
0x18002b466  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18002b46b  mov     rcx, rsi; lpOutputString
0x18002b46e  call    cs:__imp_OutputDebugStringW
0x18002b474  test    byte ptr [rbx+4], 4
0x18002b478  jnz     short loc_18002B483
0x18002b47a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002b481  jz      short loc_18002B495
0x18002b483  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002b48a  test    rax, rax
0x18002b48d  jz      short loc_18002B495
0x18002b48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002b494  nop
0x18002b495  mov     rbx, [rsp+78h+arg_10]
0x18002b49d  add     rsp, 40h
0x18002b4a1  pop     r15
0x18002b4a3  pop     r14
0x18002b4a5  pop     r13
0x18002b4a7  pop     r12
0x18002b4a9  pop     rdi
0x18002b4aa  pop     rsi
0x18002b4ab  pop     rbp
0x18002b4ac  retn
```
