# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004480`
- end: `0x140004778`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002e38`

## callees

- `0x140002874`
- `0x140003b24`
- `0x1400042bc`
- `0x140004480`
- `0x140004b38`
- `0x140004b60`
- `0x140004b74`
- `0x140004b90`
- `0x1400054ec`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400045a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400045a3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004734`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004734`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400046c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400046c2`

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
0x140004480  mov     [rsp+arg_10], rbx
0x140004485  mov     [rsp+arg_8], edx
0x140004489  mov     [rsp+arg_0], rcx
0x14000448e  push    rbp
0x14000448f  push    rsi
0x140004490  push    rdi
0x140004491  push    r12
0x140004493  push    r13
0x140004495  push    r14
0x140004497  push    r15
0x140004499  sub     rsp, 40h
0x14000449d  mov     r14, [rsp+78h+arg_38]
0x1400044a5  xor     eax, eax
0x1400044a7  mov     rbx, [rsp+78h+arg_78]
0x1400044af  xor     ebp, ebp
0x1400044b1  mov     r15d, [rsp+78h+arg_30]
0x1400044b9  mov     r10, rcx
0x1400044bc  mov     rsi, [rsp+78h+lpOutputString]
0x1400044c4  mov     r12, r9
0x1400044c7  mov     r13, r8
0x1400044ca  mov     ecx, r15d
0x1400044cd  mov     [rsi], ax
0x1400044d0  mov     rax, [rsp+78h+arg_60]
0x1400044d8  mov     byte ptr [rax], 0
0x1400044db  mov     edi, [r14]
0x1400044de  mov     [rbx+8], edi
0x1400044e1  mov     eax, [r14+4]
0x1400044e5  mov     [rbx+0Ch], eax
0x1400044e8  test    r15d, r15d
0x1400044eb  jz      short loc_140004553
0x1400044ed  sub     ecx, 1
0x1400044f0  jz      short loc_14000454A
0x1400044f2  sub     ecx, 1
0x1400044f5  jz      short loc_140004505
0x1400044f7  cmp     ecx, 1
0x1400044fa  jnz     short loc_14000455C
0x1400044fc  mov     ecx, edi; this
0x1400044fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004503  jmp     short loc_14000455A
0x140004505  test    edi, edi
0x140004507  js      short loc_140004541
0x140004509  mov     rax, [rsp+78h+arg_28]
0x140004511  mov     edi, 8007029Ch
0x140004516  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000451a  mov     rcx, r10; int
0x14000451d  mov     [rsp+78h+var_50], rax; __int64
0x140004522  mov     rax, [rsp+78h+arg_20]
0x14000452a  mov     [rsp+78h+var_58], rax; __int64
0x14000452f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004534  mov     ecx, edi; this
0x140004536  mov     [rbx+8], edi
0x140004539  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000453e  mov     [rbx+0Ch], eax
0x140004541  mov     ecx, edi; this
0x140004543  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004548  jmp     short loc_14000455A
0x14000454a  mov     ecx, edi; this
0x14000454c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004551  jmp     short loc_14000455A
0x140004553  mov     ecx, edi; this
0x140004555  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000455a  mov     ebp, eax
0x14000455c  mov     eax, [rsp+78h+arg_70]
0x140004563  mov     [rbx+4], eax
0x140004566  mov     [rbx], r15d
0x140004569  cmp     dword ptr [r14+8], 1
0x14000456e  jnz     short loc_140004576
0x140004570  or      eax, 8
0x140004573  mov     [rbx+4], eax
0x140004576  mov     eax, 1
0x14000457b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004583  inc     eax
0x140004585  xor     edi, edi
0x140004587  mov     [rbx+10h], eax
0x14000458a  mov     rax, [rsp+78h+arg_40]
0x140004592  test    rax, rax
0x140004595  jz      short loc_14000459C
0x140004597  cmp     [rax], di
0x14000459a  jnz     short loc_14000459F
0x14000459c  mov     rax, rdi
0x14000459f  mov     [rbx+18h], rax
0x1400045a3  call    cs:__imp_GetCurrentThreadId
0x1400045a9  mov     [rbx+38h], r13
0x1400045ad  xorps   xmm0, xmm0
0x1400045b0  mov     [rbx+20h], eax
0x1400045b3  mov     eax, [rsp+78h+arg_8]
0x1400045ba  mov     [rbx+40h], eax
0x1400045bd  mov     rax, [rsp+78h+arg_20]
0x1400045c5  mov     [rbx+28h], rax
0x1400045c9  mov     rax, [rsp+78h+arg_28]
0x1400045d1  mov     [rbx+88h], rax
0x1400045d8  mov     rax, [rsp+78h+arg_0]
0x1400045e0  mov     [rbx+90h], rax
0x1400045e7  xor     eax, eax
0x1400045e9  mov     [rbx+44h], ebp
0x1400045ec  mov     [rbx+30h], r12
0x1400045f0  mov     [rbx+48h], rdi
0x1400045f4  movups  xmmword ptr [rbx+68h], xmm0
0x1400045f8  mov     [rbx+78h], rax
0x1400045fc  movups  xmmword ptr [rbx+50h], xmm0
0x140004600  mov     [rbx+60h], rax
0x140004604  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000460b  test    rax, rax
0x14000460e  jz      short loc_140004617
0x140004610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004615  jmp     short loc_14000461A
0x140004617  mov     rax, rdi
0x14000461a  mov     [rbx+80h], rax
0x140004621  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004628  test    rax, rax
0x14000462b  jz      short loc_140004635
0x14000462d  mov     rcx, rbx
0x140004630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004635  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000463c  test    rax, rax
0x14000463f  jz      short loc_140004657
0x140004641  mov     rdx, [rsp+78h+arg_60]
0x140004649  mov     r8d, 400h
0x14000464f  mov     rcx, rbx
0x140004652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004657  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000465e  test    rax, rax
0x140004661  jz      short loc_14000466B
0x140004663  mov     rcx, rbx
0x140004666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000466b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004672  test    rax, rax
0x140004675  jz      short loc_140004685
0x140004677  test    byte ptr [rbx+4], 2
0x14000467b  jnz     short loc_140004685
0x14000467d  mov     rcx, rbx
0x140004680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004685  cmp     [rbx+8], edi
0x140004688  jl      short loc_1400046A4
0x14000468a  cmp     r15d, 3
0x14000468e  jnz     loc_140004772
0x140004694  mov     ecx, 8000FFFFh; this
0x140004699  mov     [rbx+8], ecx
0x14000469c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400046a1  mov     [rbx+0Ch], eax
0x1400046a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400046ab  jnz     short loc_1400046CC
0x1400046ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400046b4  test    rax, rax
0x1400046b7  jz      short loc_1400046C2
0x1400046b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046be  test    al, al
0x1400046c0  jmp     short loc_1400046CA
0x1400046c2  call    cs:__imp_IsDebuggerPresent
0x1400046c8  test    eax, eax
0x1400046ca  jz      short loc_1400046D2
0x1400046cc  test    byte ptr [rbx+4], 2
0x1400046d0  jz      short loc_1400046F6
0x1400046d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400046d9  test    rax, rax
0x1400046dc  jz      short loc_14000473A
0x1400046de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400046e5  jnz     short loc_14000473A
0x1400046e7  xor     r8d, r8d
0x1400046ea  xor     edx, edx
0x1400046ec  mov     rcx, rbx
0x1400046ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400046f4  jmp     short loc_14000473A
0x1400046f6  mov     rax, cs:g_pfnResultLoggingCallback
0x1400046fd  mov     ebp, 800h
0x140004702  test    rax, rax
0x140004705  jz      short loc_14000471E
0x140004707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000470e  jnz     short loc_14000471E
0x140004710  mov     r8d, ebp
0x140004713  mov     rdx, rsi
0x140004716  mov     rcx, rbx
0x140004719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000471e  cmp     [rsi], di
0x140004721  jnz     short loc_140004731
0x140004723  mov     r8, rbx; unsigned __int64
0x140004726  mov     rdx, rbp; unsigned __int16 *
0x140004729  mov     rcx, rsi; this
0x14000472c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004731  mov     rcx, rsi; lpOutputString
0x140004734  call    cs:__imp_OutputDebugStringW
0x14000473a  test    byte ptr [rbx+4], 4
0x14000473e  jnz     short loc_140004749
0x140004740  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004747  jz      short loc_14000475A
0x140004749  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004750  test    rax, rax
0x140004753  jz      short loc_14000475A
0x140004755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000475a  mov     rbx, [rsp+78h+arg_10]
0x140004762  add     rsp, 40h
0x140004766  pop     r15
0x140004768  pop     r14
0x14000476a  pop     r13
0x14000476c  pop     r12
0x14000476e  pop     rdi
0x14000476f  pop     rsi
0x140004770  pop     rbp
0x140004771  retn
0x140004772  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
