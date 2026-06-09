# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005480`
- end: `0x180005779`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003910`

## callees

- `0x18000331c`
- `0x1800049a4`
- `0x1800051f0`
- `0x180005480`
- `0x180005a88`
- `0x180005ab0`
- `0x180005ac4`
- `0x180005ae0`
- `0x180006f00`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800055a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800056c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005734`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005734`

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
0x180005480  mov     [rsp+arg_10], rbx
0x180005485  mov     [rsp+arg_8], edx
0x180005489  mov     [rsp+arg_0], rcx
0x18000548e  push    rbp
0x18000548f  push    rsi
0x180005490  push    rdi
0x180005491  push    r12
0x180005493  push    r13
0x180005495  push    r14
0x180005497  push    r15
0x180005499  sub     rsp, 40h
0x18000549d  mov     r12, r9
0x1800054a0  mov     r13, r8
0x1800054a3  mov     r10, rcx
0x1800054a6  xor     eax, eax
0x1800054a8  mov     rsi, [rsp+78h+lpOutputString]
0x1800054b0  mov     [rsi], ax
0x1800054b3  mov     rax, [rsp+78h+arg_60]
0x1800054bb  mov     byte ptr [rax], 0
0x1800054be  mov     r14, [rsp+78h+arg_38]
0x1800054c6  mov     edi, [r14]
0x1800054c9  mov     rbx, [rsp+78h+arg_78]
0x1800054d1  mov     [rbx+8], edi
0x1800054d4  mov     eax, [r14+4]
0x1800054d8  mov     [rbx+0Ch], eax
0x1800054db  xor     ebp, ebp
0x1800054dd  mov     r15d, [rsp+78h+arg_30]
0x1800054e5  mov     ecx, r15d
0x1800054e8  test    r15d, r15d
0x1800054eb  jz      short loc_180005553
0x1800054ed  sub     ecx, 1
0x1800054f0  jz      short loc_18000554A
0x1800054f2  sub     ecx, 1
0x1800054f5  jz      short loc_180005505
0x1800054f7  cmp     ecx, 1
0x1800054fa  jnz     short loc_18000555C
0x1800054fc  mov     ecx, edi; this
0x1800054fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005503  jmp     short loc_18000555A
0x180005505  test    edi, edi
0x180005507  js      short loc_180005541
0x180005509  mov     edi, 8007029Ch
0x18000550e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005512  mov     rax, [rsp+78h+arg_28]
0x18000551a  mov     [rsp+78h+var_50], rax; __int64
0x18000551f  mov     rax, [rsp+78h+arg_20]
0x180005527  mov     [rsp+78h+var_58], rax; __int64
0x18000552c  mov     rcx, r10; int
0x18000552f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005534  mov     [rbx+8], edi
0x180005537  mov     ecx, edi; this
0x180005539  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000553e  mov     [rbx+0Ch], eax
0x180005541  mov     ecx, edi; this
0x180005543  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005548  jmp     short loc_18000555A
0x18000554a  mov     ecx, edi; this
0x18000554c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005551  jmp     short loc_18000555A
0x180005553  mov     ecx, edi; this
0x180005555  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000555a  mov     ebp, eax
0x18000555c  mov     [rbx], r15d
0x18000555f  mov     eax, [rsp+78h+arg_70]
0x180005566  mov     [rbx+4], eax
0x180005569  cmp     dword ptr [r14+8], 1
0x18000556e  jnz     short loc_180005576
0x180005570  or      eax, 8
0x180005573  mov     [rbx+4], eax
0x180005576  mov     eax, 1
0x18000557b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005583  inc     eax
0x180005585  mov     [rbx+10h], eax
0x180005588  mov     rax, [rsp+78h+arg_40]
0x180005590  xor     edi, edi
0x180005592  test    rax, rax
0x180005595  jz      short loc_18000559C
0x180005597  cmp     [rax], di
0x18000559a  jnz     short loc_18000559F
0x18000559c  mov     rax, rdi
0x18000559f  mov     [rbx+18h], rax
0x1800055a3  call    cs:__imp_GetCurrentThreadId
0x1800055a9  mov     [rbx+20h], eax
0x1800055ac  mov     [rbx+38h], r13
0x1800055b0  mov     eax, [rsp+78h+arg_8]
0x1800055b7  mov     [rbx+40h], eax
0x1800055ba  mov     [rbx+44h], ebp
0x1800055bd  mov     rax, [rsp+78h+arg_20]
0x1800055c5  mov     [rbx+28h], rax
0x1800055c9  mov     [rbx+30h], r12
0x1800055cd  mov     rax, [rsp+78h+arg_28]
0x1800055d5  mov     [rbx+88h], rax
0x1800055dc  mov     rax, [rsp+78h+arg_0]
0x1800055e4  mov     [rbx+90h], rax
0x1800055eb  mov     [rbx+48h], rdi
0x1800055ef  xorps   xmm0, xmm0
0x1800055f2  xor     eax, eax
0x1800055f4  movups  xmmword ptr [rbx+68h], xmm0
0x1800055f8  mov     [rbx+78h], rax
0x1800055fc  movups  xmmword ptr [rbx+50h], xmm0
0x180005600  mov     [rbx+60h], rax
0x180005604  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000560b  test    rax, rax
0x18000560e  jz      short loc_180005617
0x180005610  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005615  jmp     short loc_18000561A
0x180005617  mov     rax, rdi
0x18000561a  mov     [rbx+80h], rax
0x180005621  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005628  test    rax, rax
0x18000562b  jz      short loc_180005635
0x18000562d  mov     rcx, rbx
0x180005630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005635  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000563c  test    rax, rax
0x18000563f  jz      short loc_180005657
0x180005641  mov     r8d, 400h
0x180005647  mov     rdx, [rsp+78h+arg_60]
0x18000564f  mov     rcx, rbx
0x180005652  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005657  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000565e  test    rax, rax
0x180005661  jz      short loc_18000566B
0x180005663  mov     rcx, rbx
0x180005666  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000566b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005672  test    rax, rax
0x180005675  jz      short loc_180005685
0x180005677  test    byte ptr [rbx+4], 2
0x18000567b  jnz     short loc_180005685
0x18000567d  mov     rcx, rbx
0x180005680  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005685  cmp     [rbx+8], edi
0x180005688  jl      short loc_1800056A4
0x18000568a  cmp     r15d, 3
0x18000568e  jnz     loc_180005773
0x180005694  mov     ecx, 8000FFFFh; this
0x180005699  mov     [rbx+8], ecx
0x18000569c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800056a1  mov     [rbx+0Ch], eax
0x1800056a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800056ab  jnz     short loc_1800056CC
0x1800056ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800056b4  test    rax, rax
0x1800056b7  jz      short loc_1800056C2
0x1800056b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056be  test    al, al
0x1800056c0  jmp     short loc_1800056CA
0x1800056c2  call    cs:__imp_IsDebuggerPresent
0x1800056c8  test    eax, eax
0x1800056ca  jz      short loc_1800056D2
0x1800056cc  test    byte ptr [rbx+4], 2
0x1800056d0  jz      short loc_1800056F6
0x1800056d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800056d9  test    rax, rax
0x1800056dc  jz      short loc_18000573A
0x1800056de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800056e5  jnz     short loc_18000573A
0x1800056e7  xor     r8d, r8d
0x1800056ea  xor     edx, edx
0x1800056ec  mov     rcx, rbx
0x1800056ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800056f4  jmp     short loc_18000573A
0x1800056f6  mov     ebp, 800h
0x1800056fb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005702  test    rax, rax
0x180005705  jz      short loc_18000571E
0x180005707  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000570e  jnz     short loc_18000571E
0x180005710  mov     r8d, ebp
0x180005713  mov     rdx, rsi
0x180005716  mov     rcx, rbx
0x180005719  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000571e  cmp     [rsi], di
0x180005721  jnz     short loc_180005731
0x180005723  mov     r8, rbx; unsigned __int64
0x180005726  mov     rdx, rbp; unsigned __int16 *
0x180005729  mov     rcx, rsi; this
0x18000572c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005731  mov     rcx, rsi; lpOutputString
0x180005734  call    cs:__imp_OutputDebugStringW
0x18000573a  test    byte ptr [rbx+4], 4
0x18000573e  jnz     short loc_180005749
0x180005740  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005747  jz      short loc_18000575B
0x180005749  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005750  test    rax, rax
0x180005753  jz      short loc_18000575B
0x180005755  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000575a  nop
0x18000575b  mov     rbx, [rsp+78h+arg_10]
0x180005763  add     rsp, 40h
0x180005767  pop     r15
0x180005769  pop     r14
0x18000576b  pop     r13
0x18000576d  pop     r12
0x18000576f  pop     rdi
0x180005770  pop     rsi
0x180005771  pop     rbp
0x180005772  retn
0x180005773  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
