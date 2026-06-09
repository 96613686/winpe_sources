# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000e318`
- end: `0x18000e611`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180006d3c`
- `0x180006dfc`
- `0x1800071b4`

## callees

- `0x180006c10`
- `0x18000cc28`
- `0x18000dd60`
- `0x18000e318`
- `0x18000f8b0`
- `0x18000f8d0`
- `0x18000fa1c`
- `0x18000fa38`
- `0x1800126ec`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e43b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000e43b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e55a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000e55a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e5cc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000e5cc`

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
0x18000e318  mov     [rsp+arg_10], rbx
0x18000e31d  mov     [rsp+arg_8], edx
0x18000e321  mov     [rsp+arg_0], rcx
0x18000e326  push    rbp
0x18000e327  push    rsi
0x18000e328  push    rdi
0x18000e329  push    r12
0x18000e32b  push    r13
0x18000e32d  push    r14
0x18000e32f  push    r15
0x18000e331  sub     rsp, 40h
0x18000e335  mov     r12, r9
0x18000e338  mov     r13, r8
0x18000e33b  mov     r10, rcx
0x18000e33e  xor     eax, eax
0x18000e340  mov     rsi, [rsp+78h+lpOutputString]
0x18000e348  mov     [rsi], ax
0x18000e34b  mov     rax, [rsp+78h+arg_60]
0x18000e353  mov     byte ptr [rax], 0
0x18000e356  mov     r14, [rsp+78h+arg_38]
0x18000e35e  mov     edi, [r14]
0x18000e361  mov     rbx, [rsp+78h+arg_78]
0x18000e369  mov     [rbx+8], edi
0x18000e36c  mov     eax, [r14+4]
0x18000e370  mov     [rbx+0Ch], eax
0x18000e373  xor     ebp, ebp
0x18000e375  mov     r15d, [rsp+78h+arg_30]
0x18000e37d  mov     ecx, r15d
0x18000e380  test    r15d, r15d
0x18000e383  jz      short loc_18000E3EB
0x18000e385  sub     ecx, 1
0x18000e388  jz      short loc_18000E3E2
0x18000e38a  sub     ecx, 1
0x18000e38d  jz      short loc_18000E39D
0x18000e38f  cmp     ecx, 1
0x18000e392  jnz     short loc_18000E3F4
0x18000e394  mov     ecx, edi; this
0x18000e396  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000e39b  jmp     short loc_18000E3F2
0x18000e39d  test    edi, edi
0x18000e39f  js      short loc_18000E3D9
0x18000e3a1  mov     edi, 8007029Ch
0x18000e3a6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000e3aa  mov     rax, [rsp+78h+arg_28]
0x18000e3b2  mov     [rsp+78h+var_50], rax; __int64
0x18000e3b7  mov     rax, [rsp+78h+arg_20]
0x18000e3bf  mov     [rsp+78h+var_58], rax; __int64
0x18000e3c4  mov     rcx, r10; int
0x18000e3c7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000e3cc  mov     [rbx+8], edi
0x18000e3cf  mov     ecx, edi; this
0x18000e3d1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e3d6  mov     [rbx+0Ch], eax
0x18000e3d9  mov     ecx, edi; this
0x18000e3db  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000e3e0  jmp     short loc_18000E3F2
0x18000e3e2  mov     ecx, edi; this
0x18000e3e4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000e3e9  jmp     short loc_18000E3F2
0x18000e3eb  mov     ecx, edi; this
0x18000e3ed  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000e3f2  mov     ebp, eax
0x18000e3f4  mov     [rbx], r15d
0x18000e3f7  mov     eax, [rsp+78h+arg_70]
0x18000e3fe  mov     [rbx+4], eax
0x18000e401  cmp     dword ptr [r14+8], 1
0x18000e406  jnz     short loc_18000E40E
0x18000e408  or      eax, 8
0x18000e40b  mov     [rbx+4], eax
0x18000e40e  mov     eax, 1
0x18000e413  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000e41b  inc     eax
0x18000e41d  mov     [rbx+10h], eax
0x18000e420  mov     rax, [rsp+78h+arg_40]
0x18000e428  xor     edi, edi
0x18000e42a  test    rax, rax
0x18000e42d  jz      short loc_18000E434
0x18000e42f  cmp     [rax], di
0x18000e432  jnz     short loc_18000E437
0x18000e434  mov     rax, rdi
0x18000e437  mov     [rbx+18h], rax
0x18000e43b  call    cs:__imp_GetCurrentThreadId
0x18000e441  mov     [rbx+20h], eax
0x18000e444  mov     [rbx+38h], r13
0x18000e448  mov     eax, [rsp+78h+arg_8]
0x18000e44f  mov     [rbx+40h], eax
0x18000e452  mov     [rbx+44h], ebp
0x18000e455  mov     rax, [rsp+78h+arg_20]
0x18000e45d  mov     [rbx+28h], rax
0x18000e461  mov     [rbx+30h], r12
0x18000e465  mov     rax, [rsp+78h+arg_28]
0x18000e46d  mov     [rbx+88h], rax
0x18000e474  mov     rax, [rsp+78h+arg_0]
0x18000e47c  mov     [rbx+90h], rax
0x18000e483  mov     [rbx+48h], rdi
0x18000e487  xorps   xmm0, xmm0
0x18000e48a  xor     eax, eax
0x18000e48c  movups  xmmword ptr [rbx+68h], xmm0
0x18000e490  mov     [rbx+78h], rax
0x18000e494  movups  xmmword ptr [rbx+50h], xmm0
0x18000e498  mov     [rbx+60h], rax
0x18000e49c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000e4a3  test    rax, rax
0x18000e4a6  jz      short loc_18000E4AF
0x18000e4a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ad  jmp     short loc_18000E4B2
0x18000e4af  mov     rax, rdi
0x18000e4b2  mov     [rbx+80h], rax
0x18000e4b9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000e4c0  test    rax, rax
0x18000e4c3  jz      short loc_18000E4CD
0x18000e4c5  mov     rcx, rbx
0x18000e4c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4cd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000e4d4  test    rax, rax
0x18000e4d7  jz      short loc_18000E4EF
0x18000e4d9  mov     r8d, 400h
0x18000e4df  mov     rdx, [rsp+78h+arg_60]
0x18000e4e7  mov     rcx, rbx
0x18000e4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e4ef  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e4f6  test    rax, rax
0x18000e4f9  jz      short loc_18000E503
0x18000e4fb  mov     rcx, rbx
0x18000e4fe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e503  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000e50a  test    rax, rax
0x18000e50d  jz      short loc_18000E51D
0x18000e50f  test    byte ptr [rbx+4], 2
0x18000e513  jnz     short loc_18000E51D
0x18000e515  mov     rcx, rbx
0x18000e518  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e51d  cmp     [rbx+8], edi
0x18000e520  jl      short loc_18000E53C
0x18000e522  cmp     r15d, 3
0x18000e526  jnz     loc_18000E60B
0x18000e52c  mov     ecx, 8000FFFFh; this
0x18000e531  mov     [rbx+8], ecx
0x18000e534  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000e539  mov     [rbx+0Ch], eax
0x18000e53c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000e543  jnz     short loc_18000E564
0x18000e545  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000e54c  test    rax, rax
0x18000e54f  jz      short loc_18000E55A
0x18000e551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e556  test    al, al
0x18000e558  jmp     short loc_18000E562
0x18000e55a  call    cs:__imp_IsDebuggerPresent
0x18000e560  test    eax, eax
0x18000e562  jz      short loc_18000E56A
0x18000e564  test    byte ptr [rbx+4], 2
0x18000e568  jz      short loc_18000E58E
0x18000e56a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e571  test    rax, rax
0x18000e574  jz      short loc_18000E5D2
0x18000e576  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e57d  jnz     short loc_18000E5D2
0x18000e57f  xor     r8d, r8d
0x18000e582  xor     edx, edx
0x18000e584  mov     rcx, rbx
0x18000e587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e58c  jmp     short loc_18000E5D2
0x18000e58e  mov     ebp, 800h
0x18000e593  mov     rax, cs:g_pfnResultLoggingCallback
0x18000e59a  test    rax, rax
0x18000e59d  jz      short loc_18000E5B6
0x18000e59f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000e5a6  jnz     short loc_18000E5B6
0x18000e5a8  mov     r8d, ebp
0x18000e5ab  mov     rdx, rsi
0x18000e5ae  mov     rcx, rbx
0x18000e5b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5b6  cmp     [rsi], di
0x18000e5b9  jnz     short loc_18000E5C9
0x18000e5bb  mov     r8, rbx; unsigned __int64
0x18000e5be  mov     rdx, rbp; unsigned __int16 *
0x18000e5c1  mov     rcx, rsi; this
0x18000e5c4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000e5c9  mov     rcx, rsi; lpOutputString
0x18000e5cc  call    cs:__imp_OutputDebugStringW
0x18000e5d2  test    byte ptr [rbx+4], 4
0x18000e5d6  jnz     short loc_18000E5E1
0x18000e5d8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000e5df  jz      short loc_18000E5F3
0x18000e5e1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000e5e8  test    rax, rax
0x18000e5eb  jz      short loc_18000E5F3
0x18000e5ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e5f2  nop
0x18000e5f3  mov     rbx, [rsp+78h+arg_10]
0x18000e5fb  add     rsp, 40h
0x18000e5ff  pop     r15
0x18000e601  pop     r14
0x18000e603  pop     r13
0x18000e605  pop     r12
0x18000e607  pop     rdi
0x18000e608  pop     rsi
0x18000e609  pop     rbp
0x18000e60a  retn
0x18000e60b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
