# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004338`
- end: `0x180004631`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ae8`

## callees

- `0x18000252c`
- `0x1800039d4`
- `0x180004174`
- `0x180004338`
- `0x18000487c`
- `0x1800048a0`
- `0x1800048b4`
- `0x1800048d0`
- `0x1800057d4`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000445b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000445b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045ec`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800045ec`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000457a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000457a`

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
0x180004338  mov     [rsp+arg_10], rbx
0x18000433d  mov     [rsp+arg_8], edx
0x180004341  mov     [rsp+arg_0], rcx
0x180004346  push    rbp
0x180004347  push    rsi
0x180004348  push    rdi
0x180004349  push    r12
0x18000434b  push    r13
0x18000434d  push    r14
0x18000434f  push    r15
0x180004351  sub     rsp, 40h
0x180004355  mov     r12, r9
0x180004358  mov     r13, r8
0x18000435b  mov     r10, rcx
0x18000435e  xor     eax, eax
0x180004360  mov     rsi, [rsp+78h+lpOutputString]
0x180004368  mov     [rsi], ax
0x18000436b  mov     rax, [rsp+78h+arg_60]
0x180004373  mov     byte ptr [rax], 0
0x180004376  mov     r14, [rsp+78h+arg_38]
0x18000437e  mov     edi, [r14]
0x180004381  mov     rbx, [rsp+78h+arg_78]
0x180004389  mov     [rbx+8], edi
0x18000438c  mov     eax, [r14+4]
0x180004390  mov     [rbx+0Ch], eax
0x180004393  xor     ebp, ebp
0x180004395  mov     r15d, [rsp+78h+arg_30]
0x18000439d  mov     ecx, r15d
0x1800043a0  test    r15d, r15d
0x1800043a3  jz      short loc_18000440B
0x1800043a5  sub     ecx, 1
0x1800043a8  jz      short loc_180004402
0x1800043aa  sub     ecx, 1
0x1800043ad  jz      short loc_1800043BD
0x1800043af  cmp     ecx, 1
0x1800043b2  jnz     short loc_180004414
0x1800043b4  mov     ecx, edi; this
0x1800043b6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800043bb  jmp     short loc_180004412
0x1800043bd  test    edi, edi
0x1800043bf  js      short loc_1800043F9
0x1800043c1  mov     edi, 8007029Ch
0x1800043c6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800043ca  mov     rax, [rsp+78h+arg_28]
0x1800043d2  mov     [rsp+78h+var_50], rax; __int64
0x1800043d7  mov     rax, [rsp+78h+arg_20]
0x1800043df  mov     [rsp+78h+var_58], rax; __int64
0x1800043e4  mov     rcx, r10; int
0x1800043e7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800043ec  mov     [rbx+8], edi
0x1800043ef  mov     ecx, edi; this
0x1800043f1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800043f6  mov     [rbx+0Ch], eax
0x1800043f9  mov     ecx, edi; this
0x1800043fb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004400  jmp     short loc_180004412
0x180004402  mov     ecx, edi; this
0x180004404  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004409  jmp     short loc_180004412
0x18000440b  mov     ecx, edi; this
0x18000440d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004412  mov     ebp, eax
0x180004414  mov     [rbx], r15d
0x180004417  mov     eax, [rsp+78h+arg_70]
0x18000441e  mov     [rbx+4], eax
0x180004421  cmp     dword ptr [r14+8], 1
0x180004426  jnz     short loc_18000442E
0x180004428  or      eax, 8
0x18000442b  mov     [rbx+4], eax
0x18000442e  mov     eax, 1
0x180004433  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000443b  inc     eax
0x18000443d  mov     [rbx+10h], eax
0x180004440  mov     rax, [rsp+78h+arg_40]
0x180004448  xor     edi, edi
0x18000444a  test    rax, rax
0x18000444d  jz      short loc_180004454
0x18000444f  cmp     [rax], di
0x180004452  jnz     short loc_180004457
0x180004454  mov     rax, rdi
0x180004457  mov     [rbx+18h], rax
0x18000445b  call    cs:__imp_GetCurrentThreadId
0x180004461  mov     [rbx+20h], eax
0x180004464  mov     [rbx+38h], r13
0x180004468  mov     eax, [rsp+78h+arg_8]
0x18000446f  mov     [rbx+40h], eax
0x180004472  mov     [rbx+44h], ebp
0x180004475  mov     rax, [rsp+78h+arg_20]
0x18000447d  mov     [rbx+28h], rax
0x180004481  mov     [rbx+30h], r12
0x180004485  mov     rax, [rsp+78h+arg_28]
0x18000448d  mov     [rbx+88h], rax
0x180004494  mov     rax, [rsp+78h+arg_0]
0x18000449c  mov     [rbx+90h], rax
0x1800044a3  mov     [rbx+48h], rdi
0x1800044a7  xorps   xmm0, xmm0
0x1800044aa  xor     eax, eax
0x1800044ac  movups  xmmword ptr [rbx+68h], xmm0
0x1800044b0  mov     [rbx+78h], rax
0x1800044b4  movups  xmmword ptr [rbx+50h], xmm0
0x1800044b8  mov     [rbx+60h], rax
0x1800044bc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800044c3  test    rax, rax
0x1800044c6  jz      short loc_1800044CF
0x1800044c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044cd  jmp     short loc_1800044D2
0x1800044cf  mov     rax, rdi
0x1800044d2  mov     [rbx+80h], rax
0x1800044d9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800044e0  test    rax, rax
0x1800044e3  jz      short loc_1800044ED
0x1800044e5  mov     rcx, rbx
0x1800044e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044ed  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800044f4  test    rax, rax
0x1800044f7  jz      short loc_18000450F
0x1800044f9  mov     r8d, 400h
0x1800044ff  mov     rdx, [rsp+78h+arg_60]
0x180004507  mov     rcx, rbx
0x18000450a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000450f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004516  test    rax, rax
0x180004519  jz      short loc_180004523
0x18000451b  mov     rcx, rbx
0x18000451e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004523  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000452a  test    rax, rax
0x18000452d  jz      short loc_18000453D
0x18000452f  test    byte ptr [rbx+4], 2
0x180004533  jnz     short loc_18000453D
0x180004535  mov     rcx, rbx
0x180004538  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000453d  cmp     [rbx+8], edi
0x180004540  jl      short loc_18000455C
0x180004542  cmp     r15d, 3
0x180004546  jnz     loc_18000462B
0x18000454c  mov     ecx, 8000FFFFh; this
0x180004551  mov     [rbx+8], ecx
0x180004554  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004559  mov     [rbx+0Ch], eax
0x18000455c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004563  jnz     short loc_180004584
0x180004565  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000456c  test    rax, rax
0x18000456f  jz      short loc_18000457A
0x180004571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004576  test    al, al
0x180004578  jmp     short loc_180004582
0x18000457a  call    cs:__imp_IsDebuggerPresent
0x180004580  test    eax, eax
0x180004582  jz      short loc_18000458A
0x180004584  test    byte ptr [rbx+4], 2
0x180004588  jz      short loc_1800045AE
0x18000458a  mov     rax, cs:g_pfnResultLoggingCallback
0x180004591  test    rax, rax
0x180004594  jz      short loc_1800045F2
0x180004596  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000459d  jnz     short loc_1800045F2
0x18000459f  xor     r8d, r8d
0x1800045a2  xor     edx, edx
0x1800045a4  mov     rcx, rbx
0x1800045a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045ac  jmp     short loc_1800045F2
0x1800045ae  mov     ebp, 800h
0x1800045b3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800045ba  test    rax, rax
0x1800045bd  jz      short loc_1800045D6
0x1800045bf  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800045c6  jnz     short loc_1800045D6
0x1800045c8  mov     r8d, ebp
0x1800045cb  mov     rdx, rsi
0x1800045ce  mov     rcx, rbx
0x1800045d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045d6  cmp     [rsi], di
0x1800045d9  jnz     short loc_1800045E9
0x1800045db  mov     r8, rbx; unsigned __int64
0x1800045de  mov     rdx, rbp; unsigned __int16 *
0x1800045e1  mov     rcx, rsi; this
0x1800045e4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800045e9  mov     rcx, rsi; lpOutputString
0x1800045ec  call    cs:__imp_OutputDebugStringW
0x1800045f2  test    byte ptr [rbx+4], 4
0x1800045f6  jnz     short loc_180004601
0x1800045f8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800045ff  jz      short loc_180004613
0x180004601  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004608  test    rax, rax
0x18000460b  jz      short loc_180004613
0x18000460d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004612  nop
0x180004613  mov     rbx, [rsp+78h+arg_10]
0x18000461b  add     rsp, 40h
0x18000461f  pop     r15
0x180004621  pop     r14
0x180004623  pop     r13
0x180004625  pop     r12
0x180004627  pop     rdi
0x180004628  pop     rsi
0x180004629  pop     rbp
0x18000462a  retn
0x18000462b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
