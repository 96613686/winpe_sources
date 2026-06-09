# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180004450`
- end: `0x180004748`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ed4`

## callees

- `0x180002910`
- `0x180003af4`
- `0x18000428c`
- `0x180004450`
- `0x18000498c`
- `0x1800049b0`
- `0x1800049c4`
- `0x1800049e0`
- `0x18000533c`
- `0x180014010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180004573`
- `KERNEL32!GetCurrentThreadId` at `0x180004573`
- `KERNEL32!OutputDebugStringW` at `0x180004704`
- `KERNEL32!OutputDebugStringW` at `0x180004704`
- `KERNEL32!IsDebuggerPresent` at `0x180004692`
- `KERNEL32!IsDebuggerPresent` at `0x180004692`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180004450  mov     [rsp+arg_10], rbx
0x180004455  mov     [rsp+arg_8], edx
0x180004459  mov     [rsp+arg_0], rcx
0x18000445e  push    rbp
0x18000445f  push    rsi
0x180004460  push    rdi
0x180004461  push    r12
0x180004463  push    r13
0x180004465  push    r14
0x180004467  push    r15
0x180004469  sub     rsp, 40h
0x18000446d  mov     r14, [rsp+78h+arg_38]
0x180004475  xor     eax, eax
0x180004477  mov     rbx, [rsp+78h+arg_78]
0x18000447f  xor     ebp, ebp
0x180004481  mov     r15d, [rsp+78h+arg_30]
0x180004489  mov     r10, rcx
0x18000448c  mov     rsi, [rsp+78h+lpOutputString]
0x180004494  mov     r12, r9
0x180004497  mov     r13, r8
0x18000449a  mov     ecx, r15d
0x18000449d  mov     [rsi], ax
0x1800044a0  mov     rax, [rsp+78h+arg_60]
0x1800044a8  mov     byte ptr [rax], 0
0x1800044ab  mov     edi, [r14]
0x1800044ae  mov     [rbx+8], edi
0x1800044b1  mov     eax, [r14+4]
0x1800044b5  mov     [rbx+0Ch], eax
0x1800044b8  test    r15d, r15d
0x1800044bb  jz      short loc_180004523
0x1800044bd  sub     ecx, 1
0x1800044c0  jz      short loc_18000451A
0x1800044c2  sub     ecx, 1
0x1800044c5  jz      short loc_1800044D5
0x1800044c7  cmp     ecx, 1
0x1800044ca  jnz     short loc_18000452C
0x1800044cc  mov     ecx, edi; this
0x1800044ce  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800044d3  jmp     short loc_18000452A
0x1800044d5  test    edi, edi
0x1800044d7  js      short loc_180004511
0x1800044d9  mov     rax, [rsp+78h+arg_28]
0x1800044e1  mov     edi, 8007029Ch
0x1800044e6  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800044ea  mov     rcx, r10; int
0x1800044ed  mov     [rsp+78h+var_50], rax; __int64
0x1800044f2  mov     rax, [rsp+78h+arg_20]
0x1800044fa  mov     [rsp+78h+var_58], rax; __int64
0x1800044ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004504  mov     ecx, edi; this
0x180004506  mov     [rbx+8], edi
0x180004509  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000450e  mov     [rbx+0Ch], eax
0x180004511  mov     ecx, edi; this
0x180004513  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004518  jmp     short loc_18000452A
0x18000451a  mov     ecx, edi; this
0x18000451c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180004521  jmp     short loc_18000452A
0x180004523  mov     ecx, edi; this
0x180004525  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000452a  mov     ebp, eax
0x18000452c  mov     eax, [rsp+78h+arg_70]
0x180004533  mov     [rbx+4], eax
0x180004536  mov     [rbx], r15d
0x180004539  cmp     dword ptr [r14+8], 1
0x18000453e  jnz     short loc_180004546
0x180004540  or      eax, 8
0x180004543  mov     [rbx+4], eax
0x180004546  mov     eax, 1
0x18000454b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180004553  inc     eax
0x180004555  xor     edi, edi
0x180004557  mov     [rbx+10h], eax
0x18000455a  mov     rax, [rsp+78h+arg_40]
0x180004562  test    rax, rax
0x180004565  jz      short loc_18000456C
0x180004567  cmp     [rax], di
0x18000456a  jnz     short loc_18000456F
0x18000456c  mov     rax, rdi
0x18000456f  mov     [rbx+18h], rax
0x180004573  call    cs:__imp_GetCurrentThreadId
0x180004579  mov     [rbx+38h], r13
0x18000457d  xorps   xmm0, xmm0
0x180004580  mov     [rbx+20h], eax
0x180004583  mov     eax, [rsp+78h+arg_8]
0x18000458a  mov     [rbx+40h], eax
0x18000458d  mov     rax, [rsp+78h+arg_20]
0x180004595  mov     [rbx+28h], rax
0x180004599  mov     rax, [rsp+78h+arg_28]
0x1800045a1  mov     [rbx+88h], rax
0x1800045a8  mov     rax, [rsp+78h+arg_0]
0x1800045b0  mov     [rbx+90h], rax
0x1800045b7  xor     eax, eax
0x1800045b9  mov     [rbx+44h], ebp
0x1800045bc  mov     [rbx+30h], r12
0x1800045c0  mov     [rbx+48h], rdi
0x1800045c4  movups  xmmword ptr [rbx+68h], xmm0
0x1800045c8  mov     [rbx+78h], rax
0x1800045cc  movups  xmmword ptr [rbx+50h], xmm0
0x1800045d0  mov     [rbx+60h], rax
0x1800045d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800045db  test    rax, rax
0x1800045de  jz      short loc_1800045E7
0x1800045e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800045e5  jmp     short loc_1800045EA
0x1800045e7  mov     rax, rdi
0x1800045ea  mov     [rbx+80h], rax
0x1800045f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800045f8  test    rax, rax
0x1800045fb  jz      short loc_180004605
0x1800045fd  mov     rcx, rbx
0x180004600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004605  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000460c  test    rax, rax
0x18000460f  jz      short loc_180004627
0x180004611  mov     rdx, [rsp+78h+arg_60]
0x180004619  mov     r8d, 400h
0x18000461f  mov     rcx, rbx
0x180004622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004627  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000462e  test    rax, rax
0x180004631  jz      short loc_18000463B
0x180004633  mov     rcx, rbx
0x180004636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000463b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004642  test    rax, rax
0x180004645  jz      short loc_180004655
0x180004647  test    byte ptr [rbx+4], 2
0x18000464b  jnz     short loc_180004655
0x18000464d  mov     rcx, rbx
0x180004650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004655  cmp     [rbx+8], edi
0x180004658  jl      short loc_180004674
0x18000465a  cmp     r15d, 3
0x18000465e  jnz     loc_180004742
0x180004664  mov     ecx, 8000FFFFh; this
0x180004669  mov     [rbx+8], ecx
0x18000466c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180004671  mov     [rbx+0Ch], eax
0x180004674  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000467b  jnz     short loc_18000469C
0x18000467d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004684  test    rax, rax
0x180004687  jz      short loc_180004692
0x180004689  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000468e  test    al, al
0x180004690  jmp     short loc_18000469A
0x180004692  call    cs:__imp_IsDebuggerPresent
0x180004698  test    eax, eax
0x18000469a  jz      short loc_1800046A2
0x18000469c  test    byte ptr [rbx+4], 2
0x1800046a0  jz      short loc_1800046C6
0x1800046a2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046a9  test    rax, rax
0x1800046ac  jz      short loc_18000470A
0x1800046ae  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800046b5  jnz     short loc_18000470A
0x1800046b7  xor     r8d, r8d
0x1800046ba  xor     edx, edx
0x1800046bc  mov     rcx, rbx
0x1800046bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046c4  jmp     short loc_18000470A
0x1800046c6  mov     rax, cs:g_pfnResultLoggingCallback
0x1800046cd  mov     ebp, 800h
0x1800046d2  test    rax, rax
0x1800046d5  jz      short loc_1800046EE
0x1800046d7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800046de  jnz     short loc_1800046EE
0x1800046e0  mov     r8d, ebp
0x1800046e3  mov     rdx, rsi
0x1800046e6  mov     rcx, rbx
0x1800046e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800046ee  cmp     [rsi], di
0x1800046f1  jnz     short loc_180004701
0x1800046f3  mov     r8, rbx; unsigned __int64
0x1800046f6  mov     rdx, rbp; unsigned __int16 *
0x1800046f9  mov     rcx, rsi; this
0x1800046fc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004701  mov     rcx, rsi; lpOutputString
0x180004704  call    cs:__imp_OutputDebugStringW
0x18000470a  test    byte ptr [rbx+4], 4
0x18000470e  jnz     short loc_180004719
0x180004710  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004717  jz      short loc_18000472A
0x180004719  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180004720  test    rax, rax
0x180004723  jz      short loc_18000472A
0x180004725  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000472a  mov     rbx, [rsp+78h+arg_10]
0x180004732  add     rsp, 40h
0x180004736  pop     r15
0x180004738  pop     r14
0x18000473a  pop     r13
0x18000473c  pop     r12
0x18000473e  pop     rdi
0x18000473f  pop     rsi
0x180004740  pop     rbp
0x180004741  retn
0x180004742  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
