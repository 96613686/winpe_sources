# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004334`
- end: `0x180004640`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180002698`
- `0x180002a18`

## callees

- `0x1800025d0`
- `0x1800038f4`
- `0x180004140`
- `0x180004334`
- `0x180004a80`
- `0x180004aa0`
- `0x180004ab4`
- `0x180004ad4`
- `0x180005abc`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004457`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180004457`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045f4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000457c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000457c`

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
0x180004334  mov     [rsp+arg_10], rbx
0x180004339  mov     [rsp+arg_8], edx
0x18000433d  mov     [rsp+arg_0], rcx
0x180004342  push    rbp
0x180004343  push    rsi
0x180004344  push    rdi
0x180004345  push    r12
0x180004347  push    r13
0x180004349  push    r14
0x18000434b  push    r15
0x18000434d  sub     rsp, 40h
0x180004351  mov     r12, r9
0x180004354  mov     r13, r8
0x180004357  mov     r10, rcx
0x18000435a  xor     eax, eax
0x18000435c  mov     rsi, [rsp+78h+lpOutputString]
0x180004364  mov     [rsi], ax
0x180004367  mov     rax, [rsp+78h+arg_60]
0x18000436f  mov     byte ptr [rax], 0
0x180004372  mov     r14, [rsp+78h+arg_38]
0x18000437a  mov     edi, [r14]
0x18000437d  mov     rbx, [rsp+78h+arg_78]
0x180004385  mov     [rbx+8], edi
0x180004388  mov     eax, [r14+4]
0x18000438c  mov     [rbx+0Ch], eax
0x18000438f  xor     ebp, ebp
0x180004391  mov     r15d, [rsp+78h+arg_30]
0x180004399  mov     ecx, r15d
0x18000439c  test    r15d, r15d
0x18000439f  jz      short loc_180004407
0x1800043a1  sub     ecx, 1
0x1800043a4  jz      short loc_1800043FE
0x1800043a6  sub     ecx, 1
0x1800043a9  jz      short loc_1800043B9
0x1800043ab  cmp     ecx, 1
0x1800043ae  jnz     short loc_180004410
0x1800043b0  mov     ecx, edi; this
0x1800043b2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800043b7  jmp     short loc_18000440E
0x1800043b9  test    edi, edi
0x1800043bb  js      short loc_1800043F5
0x1800043bd  mov     edi, 8007029Ch
0x1800043c2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800043c6  mov     rax, [rsp+78h+arg_28]
0x1800043ce  mov     [rsp+78h+var_50], rax; __int64
0x1800043d3  mov     rax, [rsp+78h+arg_20]
0x1800043db  mov     [rsp+78h+var_58], rax; __int64
0x1800043e0  mov     rcx, r10; int
0x1800043e3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800043e8  mov     [rbx+8], edi
0x1800043eb  mov     ecx, edi; this
0x1800043ed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800043f2  mov     [rbx+0Ch], eax
0x1800043f5  mov     ecx, edi; this
0x1800043f7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800043fc  jmp     short loc_18000440E
0x1800043fe  mov     ecx, edi; this
0x180004400  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004405  jmp     short loc_18000440E
0x180004407  mov     ecx, edi; this
0x180004409  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000440e  mov     ebp, eax
0x180004410  mov     [rbx], r15d
0x180004413  mov     eax, [rsp+78h+arg_70]
0x18000441a  mov     [rbx+4], eax
0x18000441d  cmp     dword ptr [r14+8], 1
0x180004422  jnz     short loc_18000442A
0x180004424  or      eax, 8
0x180004427  mov     [rbx+4], eax
0x18000442a  mov     eax, 1
0x18000442f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004437  inc     eax
0x180004439  mov     [rbx+10h], eax
0x18000443c  mov     rax, [rsp+78h+arg_40]
0x180004444  xor     edi, edi
0x180004446  test    rax, rax
0x180004449  jz      short loc_180004450
0x18000444b  cmp     [rax], di
0x18000444e  jnz     short loc_180004453
0x180004450  mov     rax, rdi
0x180004453  mov     [rbx+18h], rax
0x180004457  call    cs:__imp_GetCurrentThreadId
0x18000445e  nop     dword ptr [rax+rax+00h]
0x180004463  mov     [rbx+20h], eax
0x180004466  mov     [rbx+38h], r13
0x18000446a  mov     eax, [rsp+78h+arg_8]
0x180004471  mov     [rbx+40h], eax
0x180004474  mov     [rbx+44h], ebp
0x180004477  mov     rax, [rsp+78h+arg_20]
0x18000447f  mov     [rbx+28h], rax
0x180004483  mov     [rbx+30h], r12
0x180004487  mov     rax, [rsp+78h+arg_28]
0x18000448f  mov     [rbx+88h], rax
0x180004496  mov     rax, [rsp+78h+arg_0]
0x18000449e  mov     [rbx+90h], rax
0x1800044a5  mov     [rbx+48h], rdi
0x1800044a9  xorps   xmm0, xmm0
0x1800044ac  xor     eax, eax
0x1800044ae  movups  xmmword ptr [rbx+68h], xmm0
0x1800044b2  mov     [rbx+78h], rax
0x1800044b6  movups  xmmword ptr [rbx+50h], xmm0
0x1800044ba  mov     [rbx+60h], rax
0x1800044be  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800044c5  test    rax, rax
0x1800044c8  jz      short loc_1800044D1
0x1800044ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cf  jmp     short loc_1800044D4
0x1800044d1  mov     rax, rdi
0x1800044d4  mov     [rbx+80h], rax
0x1800044db  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800044e2  test    rax, rax
0x1800044e5  jz      short loc_1800044EF
0x1800044e7  mov     rcx, rbx
0x1800044ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ef  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800044f6  test    rax, rax
0x1800044f9  jz      short loc_180004511
0x1800044fb  mov     r8d, 400h
0x180004501  mov     rdx, [rsp+78h+arg_60]
0x180004509  mov     rcx, rbx
0x18000450c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004511  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004518  test    rax, rax
0x18000451b  jz      short loc_180004525
0x18000451d  mov     rcx, rbx
0x180004520  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004525  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000452c  test    rax, rax
0x18000452f  jz      short loc_18000453F
0x180004531  test    byte ptr [rbx+4], 2
0x180004535  jnz     short loc_18000453F
0x180004537  mov     rcx, rbx
0x18000453a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453f  cmp     [rbx+8], edi
0x180004542  jl      short loc_18000455E
0x180004544  cmp     r15d, 3
0x180004548  jnz     loc_18000463A
0x18000454e  mov     ecx, 8000FFFFh; this
0x180004553  mov     [rbx+8], ecx
0x180004556  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000455b  mov     [rbx+0Ch], eax
0x18000455e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004565  jnz     short loc_18000458C
0x180004567  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000456e  test    rax, rax
0x180004571  jz      short loc_18000457C
0x180004573  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004578  test    al, al
0x18000457a  jmp     short loc_18000458A
0x18000457c  call    cs:__imp_IsDebuggerPresent
0x180004583  nop     dword ptr [rax+rax+00h]
0x180004588  test    eax, eax
0x18000458a  jz      short loc_180004592
0x18000458c  test    byte ptr [rbx+4], 2
0x180004590  jz      short loc_1800045B6
0x180004592  mov     rax, cs:g_pfnResultLoggingCallback
0x180004599  test    rax, rax
0x18000459c  jz      short loc_180004600
0x18000459e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800045a5  jnz     short loc_180004600
0x1800045a7  xor     r8d, r8d
0x1800045aa  xor     edx, edx
0x1800045ac  mov     rcx, rbx
0x1800045af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045b4  jmp     short loc_180004600
0x1800045b6  mov     ebp, 800h
0x1800045bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800045c2  test    rax, rax
0x1800045c5  jz      short loc_1800045DE
0x1800045c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800045ce  jnz     short loc_1800045DE
0x1800045d0  mov     r8d, ebp
0x1800045d3  mov     rdx, rsi
0x1800045d6  mov     rcx, rbx
0x1800045d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045de  cmp     [rsi], di
0x1800045e1  jnz     short loc_1800045F1
0x1800045e3  mov     r8, rbx; unsigned __int64
0x1800045e6  mov     rdx, rbp; unsigned __int16 *
0x1800045e9  mov     rcx, rsi; this
0x1800045ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800045f1  mov     rcx, rsi; lpOutputString
0x1800045f4  call    cs:__imp_OutputDebugStringW
0x1800045fb  nop     dword ptr [rax+rax+00h]
0x180004600  test    byte ptr [rbx+4], 4
0x180004604  jnz     short loc_18000460F
0x180004606  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000460d  jz      short loc_180004621
0x18000460f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004616  test    rax, rax
0x180004619  jz      short loc_180004621
0x18000461b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004620  nop
0x180004621  mov     rbx, [rsp+78h+arg_10]
0x180004629  add     rsp, 40h
0x18000462d  pop     r15
0x18000462f  pop     r14
0x180004631  pop     r13
0x180004633  pop     r12
0x180004635  pop     rdi
0x180004636  pop     rsi
0x180004637  pop     rbp
0x180004638  retn
0x18000463a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
