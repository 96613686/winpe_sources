# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008378`
- end: `0x180008671`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800054c0`
- `0x18000582c`
- `0x180013ad8`

## callees

- `0x1800052ec`
- `0x180007684`
- `0x180007f38`
- `0x180008378`
- `0x180009410`
- `0x180009430`
- `0x180009580`
- `0x18000959c`
- `0x18000b690`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000849b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000849b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000862c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000862c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800085ba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800085ba`

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
0x180008378  mov     [rsp+arg_10], rbx
0x18000837d  mov     [rsp+arg_8], edx
0x180008381  mov     [rsp+arg_0], rcx
0x180008386  push    rbp
0x180008387  push    rsi
0x180008388  push    rdi
0x180008389  push    r12
0x18000838b  push    r13
0x18000838d  push    r14
0x18000838f  push    r15
0x180008391  sub     rsp, 40h
0x180008395  mov     r12, r9
0x180008398  mov     r13, r8
0x18000839b  mov     r10, rcx
0x18000839e  xor     eax, eax
0x1800083a0  mov     rsi, [rsp+78h+lpOutputString]
0x1800083a8  mov     [rsi], ax
0x1800083ab  mov     rax, [rsp+78h+arg_60]
0x1800083b3  mov     byte ptr [rax], 0
0x1800083b6  mov     r14, [rsp+78h+arg_38]
0x1800083be  mov     edi, [r14]
0x1800083c1  mov     rbx, [rsp+78h+arg_78]
0x1800083c9  mov     [rbx+8], edi
0x1800083cc  mov     eax, [r14+4]
0x1800083d0  mov     [rbx+0Ch], eax
0x1800083d3  xor     ebp, ebp
0x1800083d5  mov     r15d, [rsp+78h+arg_30]
0x1800083dd  mov     ecx, r15d
0x1800083e0  test    r15d, r15d
0x1800083e3  jz      short loc_18000844B
0x1800083e5  sub     ecx, 1
0x1800083e8  jz      short loc_180008442
0x1800083ea  sub     ecx, 1
0x1800083ed  jz      short loc_1800083FD
0x1800083ef  cmp     ecx, 1
0x1800083f2  jnz     short loc_180008454
0x1800083f4  mov     ecx, edi; this
0x1800083f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800083fb  jmp     short loc_180008452
0x1800083fd  test    edi, edi
0x1800083ff  js      short loc_180008439
0x180008401  mov     edi, 8007029Ch
0x180008406  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000840a  mov     rax, [rsp+78h+arg_28]
0x180008412  mov     [rsp+78h+var_50], rax; __int64
0x180008417  mov     rax, [rsp+78h+arg_20]
0x18000841f  mov     [rsp+78h+var_58], rax; __int64
0x180008424  mov     rcx, r10; int
0x180008427  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000842c  mov     [rbx+8], edi
0x18000842f  mov     ecx, edi; this
0x180008431  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008436  mov     [rbx+0Ch], eax
0x180008439  mov     ecx, edi; this
0x18000843b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008440  jmp     short loc_180008452
0x180008442  mov     ecx, edi; this
0x180008444  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008449  jmp     short loc_180008452
0x18000844b  mov     ecx, edi; this
0x18000844d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008452  mov     ebp, eax
0x180008454  mov     [rbx], r15d
0x180008457  mov     eax, [rsp+78h+arg_70]
0x18000845e  mov     [rbx+4], eax
0x180008461  cmp     dword ptr [r14+8], 1
0x180008466  jnz     short loc_18000846E
0x180008468  or      eax, 8
0x18000846b  mov     [rbx+4], eax
0x18000846e  mov     eax, 1
0x180008473  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000847b  inc     eax
0x18000847d  mov     [rbx+10h], eax
0x180008480  mov     rax, [rsp+78h+arg_40]
0x180008488  xor     edi, edi
0x18000848a  test    rax, rax
0x18000848d  jz      short loc_180008494
0x18000848f  cmp     [rax], di
0x180008492  jnz     short loc_180008497
0x180008494  mov     rax, rdi
0x180008497  mov     [rbx+18h], rax
0x18000849b  call    cs:__imp_GetCurrentThreadId
0x1800084a1  mov     [rbx+20h], eax
0x1800084a4  mov     [rbx+38h], r13
0x1800084a8  mov     eax, [rsp+78h+arg_8]
0x1800084af  mov     [rbx+40h], eax
0x1800084b2  mov     [rbx+44h], ebp
0x1800084b5  mov     rax, [rsp+78h+arg_20]
0x1800084bd  mov     [rbx+28h], rax
0x1800084c1  mov     [rbx+30h], r12
0x1800084c5  mov     rax, [rsp+78h+arg_28]
0x1800084cd  mov     [rbx+88h], rax
0x1800084d4  mov     rax, [rsp+78h+arg_0]
0x1800084dc  mov     [rbx+90h], rax
0x1800084e3  mov     [rbx+48h], rdi
0x1800084e7  xorps   xmm0, xmm0
0x1800084ea  xor     eax, eax
0x1800084ec  movups  xmmword ptr [rbx+68h], xmm0
0x1800084f0  mov     [rbx+78h], rax
0x1800084f4  movups  xmmword ptr [rbx+50h], xmm0
0x1800084f8  mov     [rbx+60h], rax
0x1800084fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008503  test    rax, rax
0x180008506  jz      short loc_18000850F
0x180008508  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000850d  jmp     short loc_180008512
0x18000850f  mov     rax, rdi
0x180008512  mov     [rbx+80h], rax
0x180008519  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180008520  test    rax, rax
0x180008523  jz      short loc_18000852D
0x180008525  mov     rcx, rbx
0x180008528  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000852d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180008534  test    rax, rax
0x180008537  jz      short loc_18000854F
0x180008539  mov     r8d, 400h
0x18000853f  mov     rdx, [rsp+78h+arg_60]
0x180008547  mov     rcx, rbx
0x18000854a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000854f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180008556  test    rax, rax
0x180008559  jz      short loc_180008563
0x18000855b  mov     rcx, rbx
0x18000855e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008563  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000856a  test    rax, rax
0x18000856d  jz      short loc_18000857D
0x18000856f  test    byte ptr [rbx+4], 2
0x180008573  jnz     short loc_18000857D
0x180008575  mov     rcx, rbx
0x180008578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000857d  cmp     [rbx+8], edi
0x180008580  jl      short loc_18000859C
0x180008582  cmp     r15d, 3
0x180008586  jnz     loc_18000866B
0x18000858c  mov     ecx, 8000FFFFh; this
0x180008591  mov     [rbx+8], ecx
0x180008594  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008599  mov     [rbx+0Ch], eax
0x18000859c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800085a3  jnz     short loc_1800085C4
0x1800085a5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800085ac  test    rax, rax
0x1800085af  jz      short loc_1800085BA
0x1800085b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085b6  test    al, al
0x1800085b8  jmp     short loc_1800085C2
0x1800085ba  call    cs:__imp_IsDebuggerPresent
0x1800085c0  test    eax, eax
0x1800085c2  jz      short loc_1800085CA
0x1800085c4  test    byte ptr [rbx+4], 2
0x1800085c8  jz      short loc_1800085EE
0x1800085ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1800085d1  test    rax, rax
0x1800085d4  jz      short loc_180008632
0x1800085d6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800085dd  jnz     short loc_180008632
0x1800085df  xor     r8d, r8d
0x1800085e2  xor     edx, edx
0x1800085e4  mov     rcx, rbx
0x1800085e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085ec  jmp     short loc_180008632
0x1800085ee  mov     ebp, 800h
0x1800085f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800085fa  test    rax, rax
0x1800085fd  jz      short loc_180008616
0x1800085ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008606  jnz     short loc_180008616
0x180008608  mov     r8d, ebp
0x18000860b  mov     rdx, rsi
0x18000860e  mov     rcx, rbx
0x180008611  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008616  cmp     [rsi], di
0x180008619  jnz     short loc_180008629
0x18000861b  mov     r8, rbx; unsigned __int64
0x18000861e  mov     rdx, rbp; unsigned __int16 *
0x180008621  mov     rcx, rsi; this
0x180008624  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180008629  mov     rcx, rsi; lpOutputString
0x18000862c  call    cs:__imp_OutputDebugStringW
0x180008632  test    byte ptr [rbx+4], 4
0x180008636  jnz     short loc_180008641
0x180008638  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000863f  jz      short loc_180008653
0x180008641  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180008648  test    rax, rax
0x18000864b  jz      short loc_180008653
0x18000864d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008652  nop
0x180008653  mov     rbx, [rsp+78h+arg_10]
0x18000865b  add     rsp, 40h
0x18000865f  pop     r15
0x180008661  pop     r14
0x180008663  pop     r13
0x180008665  pop     r12
0x180008667  pop     rdi
0x180008668  pop     rsi
0x180008669  pop     rbp
0x18000866a  retn
0x18000866b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
