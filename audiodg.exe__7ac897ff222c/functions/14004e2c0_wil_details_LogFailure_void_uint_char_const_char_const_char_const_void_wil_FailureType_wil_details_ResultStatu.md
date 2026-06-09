# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14004e2c0`
- end: `0x14004e5b5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x14004e038`
- `0x14004e1c4`
- `0x14005f87c`
- `0x14005f93c`

## callees

- `0x140017688`
- `0x14003b4d8`
- `0x14003d0b4`
- `0x14004df80`
- `0x14004e2c0`
- `0x14004e5c0`
- `0x140060ad0`
- `0x140061468`
- `0x14006208c`
- `0x1400b5010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004e3e3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14004e3e3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14004e576`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14004e576`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14004e504`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14004e504`

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
0x14004e2c0  mov     [rsp+arg_10], rbx
0x14004e2c5  mov     [rsp+arg_8], edx
0x14004e2c9  mov     [rsp+arg_0], rcx
0x14004e2ce  push    rbp
0x14004e2cf  push    rsi
0x14004e2d0  push    rdi
0x14004e2d1  push    r12
0x14004e2d3  push    r13
0x14004e2d5  push    r14
0x14004e2d7  push    r15
0x14004e2d9  sub     rsp, 40h
0x14004e2dd  mov     r12, r9
0x14004e2e0  mov     r13, r8
0x14004e2e3  mov     r10, rcx
0x14004e2e6  xor     eax, eax
0x14004e2e8  mov     rsi, [rsp+78h+lpOutputString]
0x14004e2f0  mov     [rsi], ax
0x14004e2f3  mov     rax, [rsp+78h+arg_60]
0x14004e2fb  mov     byte ptr [rax], 0
0x14004e2fe  mov     r14, [rsp+78h+arg_38]
0x14004e306  mov     edi, [r14]
0x14004e309  mov     rbx, [rsp+78h+arg_78]
0x14004e311  mov     [rbx+8], edi
0x14004e314  mov     eax, [r14+4]
0x14004e318  mov     [rbx+0Ch], eax
0x14004e31b  xor     ebp, ebp
0x14004e31d  mov     r15d, [rsp+78h+arg_30]
0x14004e325  mov     ecx, r15d
0x14004e328  test    r15d, r15d
0x14004e32b  jz      short loc_14004E393
0x14004e32d  sub     ecx, 1
0x14004e330  jz      short loc_14004E38A
0x14004e332  sub     ecx, 1
0x14004e335  jz      short loc_14004E345
0x14004e337  cmp     ecx, 1
0x14004e33a  jnz     short loc_14004E39C
0x14004e33c  mov     ecx, edi; this
0x14004e33e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14004e343  jmp     short loc_14004E39A
0x14004e345  test    edi, edi
0x14004e347  js      short loc_14004E381
0x14004e349  mov     edi, 8007029Ch
0x14004e34e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14004e352  mov     rax, [rsp+78h+arg_28]
0x14004e35a  mov     [rsp+78h+var_50], rax; __int64
0x14004e35f  mov     rax, [rsp+78h+arg_20]
0x14004e367  mov     [rsp+78h+var_58], rax; __int64
0x14004e36c  mov     rcx, r10; int
0x14004e36f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14004e374  mov     [rbx+8], edi
0x14004e377  mov     ecx, edi; this
0x14004e379  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14004e37e  mov     [rbx+0Ch], eax
0x14004e381  mov     ecx, edi; this
0x14004e383  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14004e388  jmp     short loc_14004E39A
0x14004e38a  mov     ecx, edi; this
0x14004e38c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14004e391  jmp     short loc_14004E39A
0x14004e393  mov     ecx, edi; this
0x14004e395  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14004e39a  mov     ebp, eax
0x14004e39c  mov     [rbx], r15d
0x14004e39f  mov     eax, [rsp+78h+arg_70]
0x14004e3a6  mov     [rbx+4], eax
0x14004e3a9  cmp     dword ptr [r14+8], 1
0x14004e3ae  jnz     short loc_14004E3B6
0x14004e3b0  or      eax, 8
0x14004e3b3  mov     [rbx+4], eax
0x14004e3b6  mov     eax, 1
0x14004e3bb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14004e3c3  inc     eax
0x14004e3c5  mov     [rbx+10h], eax
0x14004e3c8  mov     rax, [rsp+78h+arg_40]
0x14004e3d0  xor     edi, edi
0x14004e3d2  test    rax, rax
0x14004e3d5  jz      short loc_14004E3DC
0x14004e3d7  cmp     [rax], di
0x14004e3da  jnz     short loc_14004E3DF
0x14004e3dc  mov     rax, rdi
0x14004e3df  mov     [rbx+18h], rax
0x14004e3e3  call    cs:__imp_GetCurrentThreadId
0x14004e3e9  mov     [rbx+20h], eax
0x14004e3ec  mov     [rbx+38h], r13
0x14004e3f0  mov     eax, [rsp+78h+arg_8]
0x14004e3f7  mov     [rbx+40h], eax
0x14004e3fa  mov     [rbx+44h], ebp
0x14004e3fd  mov     rax, [rsp+78h+arg_20]
0x14004e405  mov     [rbx+28h], rax
0x14004e409  mov     [rbx+30h], r12
0x14004e40d  mov     rax, [rsp+78h+arg_28]
0x14004e415  mov     [rbx+88h], rax
0x14004e41c  mov     rax, [rsp+78h+arg_0]
0x14004e424  mov     [rbx+90h], rax
0x14004e42b  mov     [rbx+48h], rdi
0x14004e42f  xorps   xmm0, xmm0
0x14004e432  xor     eax, eax
0x14004e434  movups  xmmword ptr [rbx+68h], xmm0
0x14004e438  mov     [rbx+78h], rax
0x14004e43c  movups  xmmword ptr [rbx+50h], xmm0
0x14004e440  mov     [rbx+60h], rax
0x14004e444  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14004e44b  test    rax, rax
0x14004e44e  jz      short loc_14004E457
0x14004e450  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e455  jmp     short loc_14004E45A
0x14004e457  mov     rax, rdi
0x14004e45a  mov     [rbx+80h], rax
0x14004e461  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14004e468  test    rax, rax
0x14004e46b  jz      short loc_14004E475
0x14004e46d  mov     rcx, rbx
0x14004e470  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e475  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14004e47c  test    rax, rax
0x14004e47f  jz      short loc_14004E497
0x14004e481  mov     r8d, 400h
0x14004e487  mov     rdx, [rsp+78h+arg_60]
0x14004e48f  mov     rcx, rbx
0x14004e492  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e497  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14004e49e  test    rax, rax
0x14004e4a1  jz      short loc_14004E4AB
0x14004e4a3  mov     rcx, rbx
0x14004e4a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e4ab  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14004e4b2  test    rax, rax
0x14004e4b5  jz      short loc_14004E4C5
0x14004e4b7  test    byte ptr [rbx+4], 2
0x14004e4bb  jnz     short loc_14004E4C5
0x14004e4bd  mov     rcx, rbx
0x14004e4c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e4c5  cmp     [rbx+8], edi
0x14004e4c8  jl      short loc_14004E4E6
0x14004e4ca  cmp     r15d, 3
0x14004e4ce  jz      short loc_14004E4D6
0x14004e4d0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x14004e4d6  mov     ecx, 8000FFFFh; this
0x14004e4db  mov     [rbx+8], ecx
0x14004e4de  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14004e4e3  mov     [rbx+0Ch], eax
0x14004e4e6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14004e4ed  jnz     short loc_14004E50E
0x14004e4ef  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14004e4f6  test    rax, rax
0x14004e4f9  jz      short loc_14004E504
0x14004e4fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e500  test    al, al
0x14004e502  jmp     short loc_14004E50C
0x14004e504  call    cs:__imp_IsDebuggerPresent
0x14004e50a  test    eax, eax
0x14004e50c  jz      short loc_14004E514
0x14004e50e  test    byte ptr [rbx+4], 2
0x14004e512  jz      short loc_14004E538
0x14004e514  mov     rax, cs:g_pfnResultLoggingCallback
0x14004e51b  test    rax, rax
0x14004e51e  jz      short loc_14004E57C
0x14004e520  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14004e527  jnz     short loc_14004E57C
0x14004e529  xor     r8d, r8d
0x14004e52c  xor     edx, edx
0x14004e52e  mov     rcx, rbx
0x14004e531  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e536  jmp     short loc_14004E57C
0x14004e538  mov     ebp, 800h
0x14004e53d  mov     rax, cs:g_pfnResultLoggingCallback
0x14004e544  test    rax, rax
0x14004e547  jz      short loc_14004E560
0x14004e549  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14004e550  jnz     short loc_14004E560
0x14004e552  mov     r8d, ebp
0x14004e555  mov     rdx, rsi
0x14004e558  mov     rcx, rbx
0x14004e55b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e560  cmp     [rsi], di
0x14004e563  jnz     short loc_14004E573
0x14004e565  mov     r8, rbx; unsigned __int64
0x14004e568  mov     rdx, rbp; unsigned __int16 *
0x14004e56b  mov     rcx, rsi; this
0x14004e56e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14004e573  mov     rcx, rsi; lpOutputString
0x14004e576  call    cs:__imp_OutputDebugStringW
0x14004e57c  test    byte ptr [rbx+4], 4
0x14004e580  jnz     short loc_14004E58B
0x14004e582  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14004e589  jz      short loc_14004E59D
0x14004e58b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14004e592  test    rax, rax
0x14004e595  jz      short loc_14004E59D
0x14004e597  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14004e59c  nop
0x14004e59d  mov     rbx, [rsp+78h+arg_10]
0x14004e5a5  add     rsp, 40h
0x14004e5a9  pop     r15
0x14004e5ab  pop     r14
0x14004e5ad  pop     r13
0x14004e5af  pop     r12
0x14004e5b1  pop     rdi
0x14004e5b2  pop     rsi
0x14004e5b3  pop     rbp
0x14004e5b4  retn
```
