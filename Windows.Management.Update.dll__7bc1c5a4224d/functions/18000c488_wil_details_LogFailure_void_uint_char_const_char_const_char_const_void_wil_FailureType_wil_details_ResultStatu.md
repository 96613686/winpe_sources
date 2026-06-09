# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000c488`
- end: `0x18000c781`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800092d8`

## callees

- `0x180008d14`
- `0x18000b974`
- `0x18000c110`
- `0x18000c488`
- `0x18000d170`
- `0x18000d190`
- `0x18000d2bc`
- `0x18000d2d8`
- `0x18000fb7c`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000c5ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c73c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000c73c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c6ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000c6ca`

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
0x18000c488  mov     [rsp+arg_10], rbx
0x18000c48d  mov     [rsp+arg_8], edx
0x18000c491  mov     [rsp+arg_0], rcx
0x18000c496  push    rbp
0x18000c497  push    rsi
0x18000c498  push    rdi
0x18000c499  push    r12
0x18000c49b  push    r13
0x18000c49d  push    r14
0x18000c49f  push    r15
0x18000c4a1  sub     rsp, 40h
0x18000c4a5  mov     r12, r9
0x18000c4a8  mov     r13, r8
0x18000c4ab  mov     r10, rcx
0x18000c4ae  xor     eax, eax
0x18000c4b0  mov     rsi, [rsp+78h+lpOutputString]
0x18000c4b8  mov     [rsi], ax
0x18000c4bb  mov     rax, [rsp+78h+arg_60]
0x18000c4c3  mov     byte ptr [rax], 0
0x18000c4c6  mov     r14, [rsp+78h+arg_38]
0x18000c4ce  mov     edi, [r14]
0x18000c4d1  mov     rbx, [rsp+78h+arg_78]
0x18000c4d9  mov     [rbx+8], edi
0x18000c4dc  mov     eax, [r14+4]
0x18000c4e0  mov     [rbx+0Ch], eax
0x18000c4e3  xor     ebp, ebp
0x18000c4e5  mov     r15d, [rsp+78h+arg_30]
0x18000c4ed  mov     ecx, r15d
0x18000c4f0  test    r15d, r15d
0x18000c4f3  jz      short loc_18000C55B
0x18000c4f5  sub     ecx, 1
0x18000c4f8  jz      short loc_18000C552
0x18000c4fa  sub     ecx, 1
0x18000c4fd  jz      short loc_18000C50D
0x18000c4ff  cmp     ecx, 1
0x18000c502  jnz     short loc_18000C564
0x18000c504  mov     ecx, edi; this
0x18000c506  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000c50b  jmp     short loc_18000C562
0x18000c50d  test    edi, edi
0x18000c50f  js      short loc_18000C549
0x18000c511  mov     edi, 8007029Ch
0x18000c516  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000c51a  mov     rax, [rsp+78h+arg_28]
0x18000c522  mov     [rsp+78h+var_50], rax; __int64
0x18000c527  mov     rax, [rsp+78h+arg_20]
0x18000c52f  mov     [rsp+78h+var_58], rax; __int64
0x18000c534  mov     rcx, r10; int
0x18000c537  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000c53c  mov     [rbx+8], edi
0x18000c53f  mov     ecx, edi; this
0x18000c541  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c546  mov     [rbx+0Ch], eax
0x18000c549  mov     ecx, edi; this
0x18000c54b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000c550  jmp     short loc_18000C562
0x18000c552  mov     ecx, edi; this
0x18000c554  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000c559  jmp     short loc_18000C562
0x18000c55b  mov     ecx, edi; this
0x18000c55d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000c562  mov     ebp, eax
0x18000c564  mov     [rbx], r15d
0x18000c567  mov     eax, [rsp+78h+arg_70]
0x18000c56e  mov     [rbx+4], eax
0x18000c571  cmp     dword ptr [r14+8], 1
0x18000c576  jnz     short loc_18000C57E
0x18000c578  or      eax, 8
0x18000c57b  mov     [rbx+4], eax
0x18000c57e  mov     eax, 1
0x18000c583  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000c58b  inc     eax
0x18000c58d  mov     [rbx+10h], eax
0x18000c590  mov     rax, [rsp+78h+arg_40]
0x18000c598  xor     edi, edi
0x18000c59a  test    rax, rax
0x18000c59d  jz      short loc_18000C5A4
0x18000c59f  cmp     [rax], di
0x18000c5a2  jnz     short loc_18000C5A7
0x18000c5a4  mov     rax, rdi
0x18000c5a7  mov     [rbx+18h], rax
0x18000c5ab  call    cs:__imp_GetCurrentThreadId
0x18000c5b1  mov     [rbx+20h], eax
0x18000c5b4  mov     [rbx+38h], r13
0x18000c5b8  mov     eax, [rsp+78h+arg_8]
0x18000c5bf  mov     [rbx+40h], eax
0x18000c5c2  mov     [rbx+44h], ebp
0x18000c5c5  mov     rax, [rsp+78h+arg_20]
0x18000c5cd  mov     [rbx+28h], rax
0x18000c5d1  mov     [rbx+30h], r12
0x18000c5d5  mov     rax, [rsp+78h+arg_28]
0x18000c5dd  mov     [rbx+88h], rax
0x18000c5e4  mov     rax, [rsp+78h+arg_0]
0x18000c5ec  mov     [rbx+90h], rax
0x18000c5f3  mov     [rbx+48h], rdi
0x18000c5f7  xorps   xmm0, xmm0
0x18000c5fa  xor     eax, eax
0x18000c5fc  movups  xmmword ptr [rbx+68h], xmm0
0x18000c600  mov     [rbx+78h], rax
0x18000c604  movups  xmmword ptr [rbx+50h], xmm0
0x18000c608  mov     [rbx+60h], rax
0x18000c60c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000c613  test    rax, rax
0x18000c616  jz      short loc_18000C61F
0x18000c618  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c61d  jmp     short loc_18000C622
0x18000c61f  mov     rax, rdi
0x18000c622  mov     [rbx+80h], rax
0x18000c629  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000c630  test    rax, rax
0x18000c633  jz      short loc_18000C63D
0x18000c635  mov     rcx, rbx
0x18000c638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c63d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000c644  test    rax, rax
0x18000c647  jz      short loc_18000C65F
0x18000c649  mov     r8d, 400h
0x18000c64f  mov     rdx, [rsp+78h+arg_60]
0x18000c657  mov     rcx, rbx
0x18000c65a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c65f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c666  test    rax, rax
0x18000c669  jz      short loc_18000C673
0x18000c66b  mov     rcx, rbx
0x18000c66e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c673  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000c67a  test    rax, rax
0x18000c67d  jz      short loc_18000C68D
0x18000c67f  test    byte ptr [rbx+4], 2
0x18000c683  jnz     short loc_18000C68D
0x18000c685  mov     rcx, rbx
0x18000c688  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c68d  cmp     [rbx+8], edi
0x18000c690  jl      short loc_18000C6AC
0x18000c692  cmp     r15d, 3
0x18000c696  jnz     loc_18000C77B
0x18000c69c  mov     ecx, 8000FFFFh; this
0x18000c6a1  mov     [rbx+8], ecx
0x18000c6a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000c6a9  mov     [rbx+0Ch], eax
0x18000c6ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000c6b3  jnz     short loc_18000C6D4
0x18000c6b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000c6bc  test    rax, rax
0x18000c6bf  jz      short loc_18000C6CA
0x18000c6c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6c6  test    al, al
0x18000c6c8  jmp     short loc_18000C6D2
0x18000c6ca  call    cs:__imp_IsDebuggerPresent
0x18000c6d0  test    eax, eax
0x18000c6d2  jz      short loc_18000C6DA
0x18000c6d4  test    byte ptr [rbx+4], 2
0x18000c6d8  jz      short loc_18000C6FE
0x18000c6da  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c6e1  test    rax, rax
0x18000c6e4  jz      short loc_18000C742
0x18000c6e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c6ed  jnz     short loc_18000C742
0x18000c6ef  xor     r8d, r8d
0x18000c6f2  xor     edx, edx
0x18000c6f4  mov     rcx, rbx
0x18000c6f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c6fc  jmp     short loc_18000C742
0x18000c6fe  mov     ebp, 800h
0x18000c703  mov     rax, cs:g_pfnResultLoggingCallback
0x18000c70a  test    rax, rax
0x18000c70d  jz      short loc_18000C726
0x18000c70f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000c716  jnz     short loc_18000C726
0x18000c718  mov     r8d, ebp
0x18000c71b  mov     rdx, rsi
0x18000c71e  mov     rcx, rbx
0x18000c721  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c726  cmp     [rsi], di
0x18000c729  jnz     short loc_18000C739
0x18000c72b  mov     r8, rbx; unsigned __int64
0x18000c72e  mov     rdx, rbp; unsigned __int16 *
0x18000c731  mov     rcx, rsi; this
0x18000c734  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000c739  mov     rcx, rsi; lpOutputString
0x18000c73c  call    cs:__imp_OutputDebugStringW
0x18000c742  test    byte ptr [rbx+4], 4
0x18000c746  jnz     short loc_18000C751
0x18000c748  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000c74f  jz      short loc_18000C763
0x18000c751  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000c758  test    rax, rax
0x18000c75b  jz      short loc_18000C763
0x18000c75d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c762  nop
0x18000c763  mov     rbx, [rsp+78h+arg_10]
0x18000c76b  add     rsp, 40h
0x18000c76f  pop     r15
0x18000c771  pop     r14
0x18000c773  pop     r13
0x18000c775  pop     r12
0x18000c777  pop     rdi
0x18000c778  pop     rsi
0x18000c779  pop     rbp
0x18000c77a  retn
0x18000c77b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
