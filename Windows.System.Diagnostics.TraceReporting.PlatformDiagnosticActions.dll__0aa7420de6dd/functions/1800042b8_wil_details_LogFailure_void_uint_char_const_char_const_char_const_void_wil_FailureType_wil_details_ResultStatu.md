# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800042b8`
- end: `0x1800045b1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002a80`

## callees

- `0x18000248c`
- `0x180003954`
- `0x1800040f4`
- `0x1800042b8`
- `0x180004844`
- `0x180004860`
- `0x180004874`
- `0x180004890`
- `0x1800059cc`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043db`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800043db`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800044fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800044fa`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000456c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000456c`

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
0x1800042b8  mov     [rsp+arg_10], rbx
0x1800042bd  mov     [rsp+arg_8], edx
0x1800042c1  mov     [rsp+arg_0], rcx
0x1800042c6  push    rbp
0x1800042c7  push    rsi
0x1800042c8  push    rdi
0x1800042c9  push    r12
0x1800042cb  push    r13
0x1800042cd  push    r14
0x1800042cf  push    r15
0x1800042d1  sub     rsp, 40h
0x1800042d5  mov     r12, r9
0x1800042d8  mov     r13, r8
0x1800042db  mov     r10, rcx
0x1800042de  xor     eax, eax
0x1800042e0  mov     rsi, [rsp+78h+lpOutputString]
0x1800042e8  mov     [rsi], ax
0x1800042eb  mov     rax, [rsp+78h+arg_60]
0x1800042f3  mov     byte ptr [rax], 0
0x1800042f6  mov     r14, [rsp+78h+arg_38]
0x1800042fe  mov     edi, [r14]
0x180004301  mov     rbx, [rsp+78h+arg_78]
0x180004309  mov     [rbx+8], edi
0x18000430c  mov     eax, [r14+4]
0x180004310  mov     [rbx+0Ch], eax
0x180004313  xor     ebp, ebp
0x180004315  mov     r15d, [rsp+78h+arg_30]
0x18000431d  mov     ecx, r15d
0x180004320  test    r15d, r15d
0x180004323  jz      short loc_18000438B
0x180004325  sub     ecx, 1
0x180004328  jz      short loc_180004382
0x18000432a  sub     ecx, 1
0x18000432d  jz      short loc_18000433D
0x18000432f  cmp     ecx, 1
0x180004332  jnz     short loc_180004394
0x180004334  mov     ecx, edi; this
0x180004336  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000433b  jmp     short loc_180004392
0x18000433d  test    edi, edi
0x18000433f  js      short loc_180004379
0x180004341  mov     edi, 8007029Ch
0x180004346  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000434a  mov     rax, [rsp+78h+arg_28]
0x180004352  mov     [rsp+78h+var_50], rax; __int64
0x180004357  mov     rax, [rsp+78h+arg_20]
0x18000435f  mov     [rsp+78h+var_58], rax; __int64
0x180004364  mov     rcx, r10; int
0x180004367  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000436c  mov     [rbx+8], edi
0x18000436f  mov     ecx, edi; this
0x180004371  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004376  mov     [rbx+0Ch], eax
0x180004379  mov     ecx, edi; this
0x18000437b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004380  jmp     short loc_180004392
0x180004382  mov     ecx, edi; this
0x180004384  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004389  jmp     short loc_180004392
0x18000438b  mov     ecx, edi; this
0x18000438d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004392  mov     ebp, eax
0x180004394  mov     [rbx], r15d
0x180004397  mov     eax, [rsp+78h+arg_70]
0x18000439e  mov     [rbx+4], eax
0x1800043a1  cmp     dword ptr [r14+8], 1
0x1800043a6  jnz     short loc_1800043AE
0x1800043a8  or      eax, 8
0x1800043ab  mov     [rbx+4], eax
0x1800043ae  mov     eax, 1
0x1800043b3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800043bb  inc     eax
0x1800043bd  mov     [rbx+10h], eax
0x1800043c0  mov     rax, [rsp+78h+arg_40]
0x1800043c8  xor     edi, edi
0x1800043ca  test    rax, rax
0x1800043cd  jz      short loc_1800043D4
0x1800043cf  cmp     [rax], di
0x1800043d2  jnz     short loc_1800043D7
0x1800043d4  mov     rax, rdi
0x1800043d7  mov     [rbx+18h], rax
0x1800043db  call    cs:__imp_GetCurrentThreadId
0x1800043e1  mov     [rbx+20h], eax
0x1800043e4  mov     [rbx+38h], r13
0x1800043e8  mov     eax, [rsp+78h+arg_8]
0x1800043ef  mov     [rbx+40h], eax
0x1800043f2  mov     [rbx+44h], ebp
0x1800043f5  mov     rax, [rsp+78h+arg_20]
0x1800043fd  mov     [rbx+28h], rax
0x180004401  mov     [rbx+30h], r12
0x180004405  mov     rax, [rsp+78h+arg_28]
0x18000440d  mov     [rbx+88h], rax
0x180004414  mov     rax, [rsp+78h+arg_0]
0x18000441c  mov     [rbx+90h], rax
0x180004423  mov     [rbx+48h], rdi
0x180004427  xorps   xmm0, xmm0
0x18000442a  xor     eax, eax
0x18000442c  movups  xmmword ptr [rbx+68h], xmm0
0x180004430  mov     [rbx+78h], rax
0x180004434  movups  xmmword ptr [rbx+50h], xmm0
0x180004438  mov     [rbx+60h], rax
0x18000443c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180004443  test    rax, rax
0x180004446  jz      short loc_18000444F
0x180004448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000444d  jmp     short loc_180004452
0x18000444f  mov     rax, rdi
0x180004452  mov     [rbx+80h], rax
0x180004459  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180004460  test    rax, rax
0x180004463  jz      short loc_18000446D
0x180004465  mov     rcx, rbx
0x180004468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000446d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004474  test    rax, rax
0x180004477  jz      short loc_18000448F
0x180004479  mov     r8d, 400h
0x18000447f  mov     rdx, [rsp+78h+arg_60]
0x180004487  mov     rcx, rbx
0x18000448a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000448f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004496  test    rax, rax
0x180004499  jz      short loc_1800044A3
0x18000449b  mov     rcx, rbx
0x18000449e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800044aa  test    rax, rax
0x1800044ad  jz      short loc_1800044BD
0x1800044af  test    byte ptr [rbx+4], 2
0x1800044b3  jnz     short loc_1800044BD
0x1800044b5  mov     rcx, rbx
0x1800044b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044bd  cmp     [rbx+8], edi
0x1800044c0  jl      short loc_1800044DC
0x1800044c2  cmp     r15d, 3
0x1800044c6  jnz     loc_1800045AB
0x1800044cc  mov     ecx, 8000FFFFh; this
0x1800044d1  mov     [rbx+8], ecx
0x1800044d4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800044d9  mov     [rbx+0Ch], eax
0x1800044dc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800044e3  jnz     short loc_180004504
0x1800044e5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800044ec  test    rax, rax
0x1800044ef  jz      short loc_1800044FA
0x1800044f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044f6  test    al, al
0x1800044f8  jmp     short loc_180004502
0x1800044fa  call    cs:__imp_IsDebuggerPresent
0x180004500  test    eax, eax
0x180004502  jz      short loc_18000450A
0x180004504  test    byte ptr [rbx+4], 2
0x180004508  jz      short loc_18000452E
0x18000450a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004511  test    rax, rax
0x180004514  jz      short loc_180004572
0x180004516  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000451d  jnz     short loc_180004572
0x18000451f  xor     r8d, r8d
0x180004522  xor     edx, edx
0x180004524  mov     rcx, rbx
0x180004527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000452c  jmp     short loc_180004572
0x18000452e  mov     ebp, 800h
0x180004533  mov     rax, cs:g_pfnResultLoggingCallback
0x18000453a  test    rax, rax
0x18000453d  jz      short loc_180004556
0x18000453f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004546  jnz     short loc_180004556
0x180004548  mov     r8d, ebp
0x18000454b  mov     rdx, rsi
0x18000454e  mov     rcx, rbx
0x180004551  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004556  cmp     [rsi], di
0x180004559  jnz     short loc_180004569
0x18000455b  mov     r8, rbx; unsigned __int64
0x18000455e  mov     rdx, rbp; unsigned __int16 *
0x180004561  mov     rcx, rsi; this
0x180004564  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004569  mov     rcx, rsi; lpOutputString
0x18000456c  call    cs:__imp_OutputDebugStringW
0x180004572  test    byte ptr [rbx+4], 4
0x180004576  jnz     short loc_180004581
0x180004578  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000457f  jz      short loc_180004593
0x180004581  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004588  test    rax, rax
0x18000458b  jz      short loc_180004593
0x18000458d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004592  nop
0x180004593  mov     rbx, [rsp+78h+arg_10]
0x18000459b  add     rsp, 40h
0x18000459f  pop     r15
0x1800045a1  pop     r14
0x1800045a3  pop     r13
0x1800045a5  pop     r12
0x1800045a7  pop     rdi
0x1800045a8  pop     rsi
0x1800045a9  pop     rbp
0x1800045aa  retn
0x1800045ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
