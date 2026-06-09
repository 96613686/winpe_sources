# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000a23c`
- end: `0x14000a535`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140005f68`

## callees

- `0x1400055c0`
- `0x1400097c4`
- `0x140009f4c`
- `0x14000a23c`
- `0x14000baf4`
- `0x14000bb10`
- `0x14000bb24`
- `0x14000bb40`
- `0x14000e394`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a35f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000a35f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a47e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000a47e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a4f0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000a4f0`

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
0x14000a23c  mov     [rsp+arg_10], rbx
0x14000a241  mov     [rsp+arg_8], edx
0x14000a245  mov     [rsp+arg_0], rcx
0x14000a24a  push    rbp
0x14000a24b  push    rsi
0x14000a24c  push    rdi
0x14000a24d  push    r12
0x14000a24f  push    r13
0x14000a251  push    r14
0x14000a253  push    r15
0x14000a255  sub     rsp, 40h
0x14000a259  mov     r12, r9
0x14000a25c  mov     r13, r8
0x14000a25f  mov     r10, rcx
0x14000a262  xor     eax, eax
0x14000a264  mov     rsi, [rsp+78h+lpOutputString]
0x14000a26c  mov     [rsi], ax
0x14000a26f  mov     rax, [rsp+78h+arg_60]
0x14000a277  mov     byte ptr [rax], 0
0x14000a27a  mov     r14, [rsp+78h+arg_38]
0x14000a282  mov     edi, [r14]
0x14000a285  mov     rbx, [rsp+78h+arg_78]
0x14000a28d  mov     [rbx+8], edi
0x14000a290  mov     eax, [r14+4]
0x14000a294  mov     [rbx+0Ch], eax
0x14000a297  xor     ebp, ebp
0x14000a299  mov     r15d, [rsp+78h+arg_30]
0x14000a2a1  mov     ecx, r15d
0x14000a2a4  test    r15d, r15d
0x14000a2a7  jz      short loc_14000A30F
0x14000a2a9  sub     ecx, 1
0x14000a2ac  jz      short loc_14000A306
0x14000a2ae  sub     ecx, 1
0x14000a2b1  jz      short loc_14000A2C1
0x14000a2b3  cmp     ecx, 1
0x14000a2b6  jnz     short loc_14000A318
0x14000a2b8  mov     ecx, edi; this
0x14000a2ba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000a2bf  jmp     short loc_14000A316
0x14000a2c1  test    edi, edi
0x14000a2c3  js      short loc_14000A2FD
0x14000a2c5  mov     edi, 8007029Ch
0x14000a2ca  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000a2ce  mov     rax, [rsp+78h+arg_28]
0x14000a2d6  mov     [rsp+78h+var_50], rax; __int64
0x14000a2db  mov     rax, [rsp+78h+arg_20]
0x14000a2e3  mov     [rsp+78h+var_58], rax; __int64
0x14000a2e8  mov     rcx, r10; int
0x14000a2eb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000a2f0  mov     [rbx+8], edi
0x14000a2f3  mov     ecx, edi; this
0x14000a2f5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a2fa  mov     [rbx+0Ch], eax
0x14000a2fd  mov     ecx, edi; this
0x14000a2ff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000a304  jmp     short loc_14000A316
0x14000a306  mov     ecx, edi; this
0x14000a308  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000a30d  jmp     short loc_14000A316
0x14000a30f  mov     ecx, edi; this
0x14000a311  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000a316  mov     ebp, eax
0x14000a318  mov     [rbx], r15d
0x14000a31b  mov     eax, [rsp+78h+arg_70]
0x14000a322  mov     [rbx+4], eax
0x14000a325  cmp     dword ptr [r14+8], 1
0x14000a32a  jnz     short loc_14000A332
0x14000a32c  or      eax, 8
0x14000a32f  mov     [rbx+4], eax
0x14000a332  mov     eax, 1
0x14000a337  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000a33f  inc     eax
0x14000a341  mov     [rbx+10h], eax
0x14000a344  mov     rax, [rsp+78h+arg_40]
0x14000a34c  xor     edi, edi
0x14000a34e  test    rax, rax
0x14000a351  jz      short loc_14000A358
0x14000a353  cmp     [rax], di
0x14000a356  jnz     short loc_14000A35B
0x14000a358  mov     rax, rdi
0x14000a35b  mov     [rbx+18h], rax
0x14000a35f  call    cs:__imp_GetCurrentThreadId
0x14000a365  mov     [rbx+20h], eax
0x14000a368  mov     [rbx+38h], r13
0x14000a36c  mov     eax, [rsp+78h+arg_8]
0x14000a373  mov     [rbx+40h], eax
0x14000a376  mov     [rbx+44h], ebp
0x14000a379  mov     rax, [rsp+78h+arg_20]
0x14000a381  mov     [rbx+28h], rax
0x14000a385  mov     [rbx+30h], r12
0x14000a389  mov     rax, [rsp+78h+arg_28]
0x14000a391  mov     [rbx+88h], rax
0x14000a398  mov     rax, [rsp+78h+arg_0]
0x14000a3a0  mov     [rbx+90h], rax
0x14000a3a7  mov     [rbx+48h], rdi
0x14000a3ab  xorps   xmm0, xmm0
0x14000a3ae  xor     eax, eax
0x14000a3b0  movups  xmmword ptr [rbx+68h], xmm0
0x14000a3b4  mov     [rbx+78h], rax
0x14000a3b8  movups  xmmword ptr [rbx+50h], xmm0
0x14000a3bc  mov     [rbx+60h], rax
0x14000a3c0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000a3c7  test    rax, rax
0x14000a3ca  jz      short loc_14000A3D3
0x14000a3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3d1  jmp     short loc_14000A3D6
0x14000a3d3  mov     rax, rdi
0x14000a3d6  mov     [rbx+80h], rax
0x14000a3dd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000a3e4  test    rax, rax
0x14000a3e7  jz      short loc_14000A3F1
0x14000a3e9  mov     rcx, rbx
0x14000a3ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a3f1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000a3f8  test    rax, rax
0x14000a3fb  jz      short loc_14000A413
0x14000a3fd  mov     r8d, 400h
0x14000a403  mov     rdx, [rsp+78h+arg_60]
0x14000a40b  mov     rcx, rbx
0x14000a40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a413  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a41a  test    rax, rax
0x14000a41d  jz      short loc_14000A427
0x14000a41f  mov     rcx, rbx
0x14000a422  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a427  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000a42e  test    rax, rax
0x14000a431  jz      short loc_14000A441
0x14000a433  test    byte ptr [rbx+4], 2
0x14000a437  jnz     short loc_14000A441
0x14000a439  mov     rcx, rbx
0x14000a43c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a441  cmp     [rbx+8], edi
0x14000a444  jl      short loc_14000A460
0x14000a446  cmp     r15d, 3
0x14000a44a  jnz     loc_14000A52F
0x14000a450  mov     ecx, 8000FFFFh; this
0x14000a455  mov     [rbx+8], ecx
0x14000a458  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000a45d  mov     [rbx+0Ch], eax
0x14000a460  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000a467  jnz     short loc_14000A488
0x14000a469  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000a470  test    rax, rax
0x14000a473  jz      short loc_14000A47E
0x14000a475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a47a  test    al, al
0x14000a47c  jmp     short loc_14000A486
0x14000a47e  call    cs:__imp_IsDebuggerPresent
0x14000a484  test    eax, eax
0x14000a486  jz      short loc_14000A48E
0x14000a488  test    byte ptr [rbx+4], 2
0x14000a48c  jz      short loc_14000A4B2
0x14000a48e  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a495  test    rax, rax
0x14000a498  jz      short loc_14000A4F6
0x14000a49a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a4a1  jnz     short loc_14000A4F6
0x14000a4a3  xor     r8d, r8d
0x14000a4a6  xor     edx, edx
0x14000a4a8  mov     rcx, rbx
0x14000a4ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4b0  jmp     short loc_14000A4F6
0x14000a4b2  mov     ebp, 800h
0x14000a4b7  mov     rax, cs:g_pfnResultLoggingCallback
0x14000a4be  test    rax, rax
0x14000a4c1  jz      short loc_14000A4DA
0x14000a4c3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000a4ca  jnz     short loc_14000A4DA
0x14000a4cc  mov     r8d, ebp
0x14000a4cf  mov     rdx, rsi
0x14000a4d2  mov     rcx, rbx
0x14000a4d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a4da  cmp     [rsi], di
0x14000a4dd  jnz     short loc_14000A4ED
0x14000a4df  mov     r8, rbx; unsigned __int64
0x14000a4e2  mov     rdx, rbp; unsigned __int16 *
0x14000a4e5  mov     rcx, rsi; this
0x14000a4e8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000a4ed  mov     rcx, rsi; lpOutputString
0x14000a4f0  call    cs:__imp_OutputDebugStringW
0x14000a4f6  test    byte ptr [rbx+4], 4
0x14000a4fa  jnz     short loc_14000A505
0x14000a4fc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000a503  jz      short loc_14000A517
0x14000a505  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000a50c  test    rax, rax
0x14000a50f  jz      short loc_14000A517
0x14000a511  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a516  nop
0x14000a517  mov     rbx, [rsp+78h+arg_10]
0x14000a51f  add     rsp, 40h
0x14000a523  pop     r15
0x14000a525  pop     r14
0x14000a527  pop     r13
0x14000a529  pop     r12
0x14000a52b  pop     rdi
0x14000a52c  pop     rsi
0x14000a52d  pop     rbp
0x14000a52e  retn
0x14000a52f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
