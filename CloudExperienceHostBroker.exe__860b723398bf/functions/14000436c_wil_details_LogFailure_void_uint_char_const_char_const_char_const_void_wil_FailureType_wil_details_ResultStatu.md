# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000436c`
- end: `0x140004665`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x140002a5c`
- `0x140002dc8`
- `0x140007050`

## callees

- `0x140002994`
- `0x1400039a4`
- `0x14000417c`
- `0x14000436c`
- `0x140004a3c`
- `0x140004a60`
- `0x140004a74`
- `0x140004a90`
- `0x140005890`
- `0x14000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000448f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000448f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400045ae`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400045ae`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004620`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004620`

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
0x14000436c  mov     [rsp+arg_10], rbx
0x140004371  mov     [rsp+arg_8], edx
0x140004375  mov     [rsp+arg_0], rcx
0x14000437a  push    rbp
0x14000437b  push    rsi
0x14000437c  push    rdi
0x14000437d  push    r12
0x14000437f  push    r13
0x140004381  push    r14
0x140004383  push    r15
0x140004385  sub     rsp, 40h
0x140004389  mov     r12, r9
0x14000438c  mov     r13, r8
0x14000438f  mov     r10, rcx
0x140004392  xor     eax, eax
0x140004394  mov     rsi, [rsp+78h+lpOutputString]
0x14000439c  mov     [rsi], ax
0x14000439f  mov     rax, [rsp+78h+arg_60]
0x1400043a7  mov     byte ptr [rax], 0
0x1400043aa  mov     r14, [rsp+78h+arg_38]
0x1400043b2  mov     edi, [r14]
0x1400043b5  mov     rbx, [rsp+78h+arg_78]
0x1400043bd  mov     [rbx+8], edi
0x1400043c0  mov     eax, [r14+4]
0x1400043c4  mov     [rbx+0Ch], eax
0x1400043c7  xor     ebp, ebp
0x1400043c9  mov     r15d, [rsp+78h+arg_30]
0x1400043d1  mov     ecx, r15d
0x1400043d4  test    r15d, r15d
0x1400043d7  jz      short loc_14000443F
0x1400043d9  sub     ecx, 1
0x1400043dc  jz      short loc_140004436
0x1400043de  sub     ecx, 1
0x1400043e1  jz      short loc_1400043F1
0x1400043e3  cmp     ecx, 1
0x1400043e6  jnz     short loc_140004448
0x1400043e8  mov     ecx, edi; this
0x1400043ea  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400043ef  jmp     short loc_140004446
0x1400043f1  test    edi, edi
0x1400043f3  js      short loc_14000442D
0x1400043f5  mov     edi, 8007029Ch
0x1400043fa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400043fe  mov     rax, [rsp+78h+arg_28]
0x140004406  mov     [rsp+78h+var_50], rax; __int64
0x14000440b  mov     rax, [rsp+78h+arg_20]
0x140004413  mov     [rsp+78h+var_58], rax; __int64
0x140004418  mov     rcx, r10; int
0x14000441b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004420  mov     [rbx+8], edi
0x140004423  mov     ecx, edi; this
0x140004425  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000442a  mov     [rbx+0Ch], eax
0x14000442d  mov     ecx, edi; this
0x14000442f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004434  jmp     short loc_140004446
0x140004436  mov     ecx, edi; this
0x140004438  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000443d  jmp     short loc_140004446
0x14000443f  mov     ecx, edi; this
0x140004441  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004446  mov     ebp, eax
0x140004448  mov     [rbx], r15d
0x14000444b  mov     eax, [rsp+78h+arg_70]
0x140004452  mov     [rbx+4], eax
0x140004455  cmp     dword ptr [r14+8], 1
0x14000445a  jnz     short loc_140004462
0x14000445c  or      eax, 8
0x14000445f  mov     [rbx+4], eax
0x140004462  mov     eax, 1
0x140004467  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000446f  inc     eax
0x140004471  mov     [rbx+10h], eax
0x140004474  mov     rax, [rsp+78h+arg_40]
0x14000447c  xor     edi, edi
0x14000447e  test    rax, rax
0x140004481  jz      short loc_140004488
0x140004483  cmp     [rax], di
0x140004486  jnz     short loc_14000448B
0x140004488  mov     rax, rdi
0x14000448b  mov     [rbx+18h], rax
0x14000448f  call    cs:__imp_GetCurrentThreadId
0x140004495  mov     [rbx+20h], eax
0x140004498  mov     [rbx+38h], r13
0x14000449c  mov     eax, [rsp+78h+arg_8]
0x1400044a3  mov     [rbx+40h], eax
0x1400044a6  mov     [rbx+44h], ebp
0x1400044a9  mov     rax, [rsp+78h+arg_20]
0x1400044b1  mov     [rbx+28h], rax
0x1400044b5  mov     [rbx+30h], r12
0x1400044b9  mov     rax, [rsp+78h+arg_28]
0x1400044c1  mov     [rbx+88h], rax
0x1400044c8  mov     rax, [rsp+78h+arg_0]
0x1400044d0  mov     [rbx+90h], rax
0x1400044d7  mov     [rbx+48h], rdi
0x1400044db  xorps   xmm0, xmm0
0x1400044de  xor     eax, eax
0x1400044e0  movups  xmmword ptr [rbx+68h], xmm0
0x1400044e4  mov     [rbx+78h], rax
0x1400044e8  movups  xmmword ptr [rbx+50h], xmm0
0x1400044ec  mov     [rbx+60h], rax
0x1400044f0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1400044f7  test    rax, rax
0x1400044fa  jz      short loc_140004503
0x1400044fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004501  jmp     short loc_140004506
0x140004503  mov     rax, rdi
0x140004506  mov     [rbx+80h], rax
0x14000450d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004514  test    rax, rax
0x140004517  jz      short loc_140004521
0x140004519  mov     rcx, rbx
0x14000451c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004521  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004528  test    rax, rax
0x14000452b  jz      short loc_140004543
0x14000452d  mov     r8d, 400h
0x140004533  mov     rdx, [rsp+78h+arg_60]
0x14000453b  mov     rcx, rbx
0x14000453e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004543  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000454a  test    rax, rax
0x14000454d  jz      short loc_140004557
0x14000454f  mov     rcx, rbx
0x140004552  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004557  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000455e  test    rax, rax
0x140004561  jz      short loc_140004571
0x140004563  test    byte ptr [rbx+4], 2
0x140004567  jnz     short loc_140004571
0x140004569  mov     rcx, rbx
0x14000456c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004571  cmp     [rbx+8], edi
0x140004574  jl      short loc_140004590
0x140004576  cmp     r15d, 3
0x14000457a  jnz     loc_14000465F
0x140004580  mov     ecx, 8000FFFFh; this
0x140004585  mov     [rbx+8], ecx
0x140004588  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000458d  mov     [rbx+0Ch], eax
0x140004590  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004597  jnz     short loc_1400045B8
0x140004599  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400045a0  test    rax, rax
0x1400045a3  jz      short loc_1400045AE
0x1400045a5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045aa  test    al, al
0x1400045ac  jmp     short loc_1400045B6
0x1400045ae  call    cs:__imp_IsDebuggerPresent
0x1400045b4  test    eax, eax
0x1400045b6  jz      short loc_1400045BE
0x1400045b8  test    byte ptr [rbx+4], 2
0x1400045bc  jz      short loc_1400045E2
0x1400045be  mov     rax, cs:g_pfnResultLoggingCallback
0x1400045c5  test    rax, rax
0x1400045c8  jz      short loc_140004626
0x1400045ca  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400045d1  jnz     short loc_140004626
0x1400045d3  xor     r8d, r8d
0x1400045d6  xor     edx, edx
0x1400045d8  mov     rcx, rbx
0x1400045db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400045e0  jmp     short loc_140004626
0x1400045e2  mov     ebp, 800h
0x1400045e7  mov     rax, cs:g_pfnResultLoggingCallback
0x1400045ee  test    rax, rax
0x1400045f1  jz      short loc_14000460A
0x1400045f3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400045fa  jnz     short loc_14000460A
0x1400045fc  mov     r8d, ebp
0x1400045ff  mov     rdx, rsi
0x140004602  mov     rcx, rbx
0x140004605  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000460a  cmp     [rsi], di
0x14000460d  jnz     short loc_14000461D
0x14000460f  mov     r8, rbx; unsigned __int64
0x140004612  mov     rdx, rbp; unsigned __int16 *
0x140004615  mov     rcx, rsi; this
0x140004618  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000461d  mov     rcx, rsi; lpOutputString
0x140004620  call    cs:__imp_OutputDebugStringW
0x140004626  test    byte ptr [rbx+4], 4
0x14000462a  jnz     short loc_140004635
0x14000462c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004633  jz      short loc_140004647
0x140004635  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000463c  test    rax, rax
0x14000463f  jz      short loc_140004647
0x140004641  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004646  nop
0x140004647  mov     rbx, [rsp+78h+arg_10]
0x14000464f  add     rsp, 40h
0x140004653  pop     r15
0x140004655  pop     r14
0x140004657  pop     r13
0x140004659  pop     r12
0x14000465b  pop     rdi
0x14000465c  pop     rsi
0x14000465d  pop     rbp
0x14000465e  retn
0x14000465f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
