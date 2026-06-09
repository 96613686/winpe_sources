# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000427c`
- end: `0x180004588`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000248c`
- `0x1800027ec`

## callees

- `0x1800023cc`
- `0x180003874`
- `0x1800040b8`
- `0x18000427c`
- `0x180005088`
- `0x1800050b0`
- `0x1800050c4`
- `0x1800050e4`
- `0x1800060cc`
- `0x180021010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000453c`
- `KERNEL32!OutputDebugStringW` at `0x18000453c`
- `KERNEL32!IsDebuggerPresent` at `0x1800044c4`
- `KERNEL32!IsDebuggerPresent` at `0x1800044c4`
- `KERNEL32!GetCurrentThreadId` at `0x18000439f`
- `KERNEL32!GetCurrentThreadId` at `0x18000439f`

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
0x18000427c  mov     [rsp+arg_10], rbx
0x180004281  mov     [rsp+arg_8], edx
0x180004285  mov     [rsp+arg_0], rcx
0x18000428a  push    rbp
0x18000428b  push    rsi
0x18000428c  push    rdi
0x18000428d  push    r12
0x18000428f  push    r13
0x180004291  push    r14
0x180004293  push    r15
0x180004295  sub     rsp, 40h
0x180004299  mov     r12, r9
0x18000429c  mov     r13, r8
0x18000429f  mov     r10, rcx
0x1800042a2  xor     eax, eax
0x1800042a4  mov     rsi, [rsp+78h+lpOutputString]
0x1800042ac  mov     [rsi], ax
0x1800042af  mov     rax, [rsp+78h+arg_60]
0x1800042b7  mov     byte ptr [rax], 0
0x1800042ba  mov     r14, [rsp+78h+arg_38]
0x1800042c2  mov     edi, [r14]
0x1800042c5  mov     rbx, [rsp+78h+arg_78]
0x1800042cd  mov     [rbx+8], edi
0x1800042d0  mov     eax, [r14+4]
0x1800042d4  mov     [rbx+0Ch], eax
0x1800042d7  xor     ebp, ebp
0x1800042d9  mov     r15d, [rsp+78h+arg_30]
0x1800042e1  mov     ecx, r15d
0x1800042e4  test    r15d, r15d
0x1800042e7  jz      short loc_18000434F
0x1800042e9  sub     ecx, 1
0x1800042ec  jz      short loc_180004346
0x1800042ee  sub     ecx, 1
0x1800042f1  jz      short loc_180004301
0x1800042f3  cmp     ecx, 1
0x1800042f6  jnz     short loc_180004358
0x1800042f8  mov     ecx, edi; this
0x1800042fa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800042ff  jmp     short loc_180004356
0x180004301  test    edi, edi
0x180004303  js      short loc_18000433D
0x180004305  mov     edi, 8007029Ch
0x18000430a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000430e  mov     rax, [rsp+78h+arg_28]
0x180004316  mov     [rsp+78h+var_50], rax; __int64
0x18000431b  mov     rax, [rsp+78h+arg_20]
0x180004323  mov     [rsp+78h+var_58], rax; __int64
0x180004328  mov     rcx, r10; int
0x18000432b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004330  mov     [rbx+8], edi
0x180004333  mov     ecx, edi; this
0x180004335  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000433a  mov     [rbx+0Ch], eax
0x18000433d  mov     ecx, edi; this
0x18000433f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004344  jmp     short loc_180004356
0x180004346  mov     ecx, edi; this
0x180004348  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000434d  jmp     short loc_180004356
0x18000434f  mov     ecx, edi; this
0x180004351  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004356  mov     ebp, eax
0x180004358  mov     [rbx], r15d
0x18000435b  mov     eax, [rsp+78h+arg_70]
0x180004362  mov     [rbx+4], eax
0x180004365  cmp     dword ptr [r14+8], 1
0x18000436a  jnz     short loc_180004372
0x18000436c  or      eax, 8
0x18000436f  mov     [rbx+4], eax
0x180004372  mov     eax, 1
0x180004377  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000437f  inc     eax
0x180004381  mov     [rbx+10h], eax
0x180004384  mov     rax, [rsp+78h+arg_40]
0x18000438c  xor     edi, edi
0x18000438e  test    rax, rax
0x180004391  jz      short loc_180004398
0x180004393  cmp     [rax], di
0x180004396  jnz     short loc_18000439B
0x180004398  mov     rax, rdi
0x18000439b  mov     [rbx+18h], rax
0x18000439f  call    cs:__imp_GetCurrentThreadId
0x1800043a6  nop     dword ptr [rax+rax+00h]
0x1800043ab  mov     [rbx+20h], eax
0x1800043ae  mov     [rbx+38h], r13
0x1800043b2  mov     eax, [rsp+78h+arg_8]
0x1800043b9  mov     [rbx+40h], eax
0x1800043bc  mov     [rbx+44h], ebp
0x1800043bf  mov     rax, [rsp+78h+arg_20]
0x1800043c7  mov     [rbx+28h], rax
0x1800043cb  mov     [rbx+30h], r12
0x1800043cf  mov     rax, [rsp+78h+arg_28]
0x1800043d7  mov     [rbx+88h], rax
0x1800043de  mov     rax, [rsp+78h+arg_0]
0x1800043e6  mov     [rbx+90h], rax
0x1800043ed  mov     [rbx+48h], rdi
0x1800043f1  xorps   xmm0, xmm0
0x1800043f4  xor     eax, eax
0x1800043f6  movups  xmmword ptr [rbx+68h], xmm0
0x1800043fa  mov     [rbx+78h], rax
0x1800043fe  movups  xmmword ptr [rbx+50h], xmm0
0x180004402  mov     [rbx+60h], rax
0x180004406  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000440d  test    rax, rax
0x180004410  jz      short loc_180004419
0x180004412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004417  jmp     short loc_18000441C
0x180004419  mov     rax, rdi
0x18000441c  mov     [rbx+80h], rax
0x180004423  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000442a  test    rax, rax
0x18000442d  jz      short loc_180004437
0x18000442f  mov     rcx, rbx
0x180004432  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004437  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000443e  test    rax, rax
0x180004441  jz      short loc_180004459
0x180004443  mov     r8d, 400h
0x180004449  mov     rdx, [rsp+78h+arg_60]
0x180004451  mov     rcx, rbx
0x180004454  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004459  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004460  test    rax, rax
0x180004463  jz      short loc_18000446D
0x180004465  mov     rcx, rbx
0x180004468  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000446d  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180004474  test    rax, rax
0x180004477  jz      short loc_180004487
0x180004479  test    byte ptr [rbx+4], 2
0x18000447d  jnz     short loc_180004487
0x18000447f  mov     rcx, rbx
0x180004482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004487  cmp     [rbx+8], edi
0x18000448a  jl      short loc_1800044A6
0x18000448c  cmp     r15d, 3
0x180004490  jnz     loc_180004582
0x180004496  mov     ecx, 8000FFFFh; this
0x18000449b  mov     [rbx+8], ecx
0x18000449e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800044a3  mov     [rbx+0Ch], eax
0x1800044a6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800044ad  jnz     short loc_1800044D4
0x1800044af  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800044b6  test    rax, rax
0x1800044b9  jz      short loc_1800044C4
0x1800044bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044c0  test    al, al
0x1800044c2  jmp     short loc_1800044D2
0x1800044c4  call    cs:__imp_IsDebuggerPresent
0x1800044cb  nop     dword ptr [rax+rax+00h]
0x1800044d0  test    eax, eax
0x1800044d2  jz      short loc_1800044DA
0x1800044d4  test    byte ptr [rbx+4], 2
0x1800044d8  jz      short loc_1800044FE
0x1800044da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800044e1  test    rax, rax
0x1800044e4  jz      short loc_180004548
0x1800044e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800044ed  jnz     short loc_180004548
0x1800044ef  xor     r8d, r8d
0x1800044f2  xor     edx, edx
0x1800044f4  mov     rcx, rbx
0x1800044f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800044fc  jmp     short loc_180004548
0x1800044fe  mov     ebp, 800h
0x180004503  mov     rax, cs:g_pfnResultLoggingCallback
0x18000450a  test    rax, rax
0x18000450d  jz      short loc_180004526
0x18000450f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180004516  jnz     short loc_180004526
0x180004518  mov     r8d, ebp
0x18000451b  mov     rdx, rsi
0x18000451e  mov     rcx, rbx
0x180004521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004526  cmp     [rsi], di
0x180004529  jnz     short loc_180004539
0x18000452b  mov     r8, rbx; unsigned __int64
0x18000452e  mov     rdx, rbp; unsigned __int16 *
0x180004531  mov     rcx, rsi; this
0x180004534  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180004539  mov     rcx, rsi; lpOutputString
0x18000453c  call    cs:__imp_OutputDebugStringW
0x180004543  nop     dword ptr [rax+rax+00h]
0x180004548  test    byte ptr [rbx+4], 4
0x18000454c  jnz     short loc_180004557
0x18000454e  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004555  jz      short loc_180004569
0x180004557  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000455e  test    rax, rax
0x180004561  jz      short loc_180004569
0x180004563  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004568  nop
0x180004569  mov     rbx, [rsp+78h+arg_10]
0x180004571  add     rsp, 40h
0x180004575  pop     r15
0x180004577  pop     r14
0x180004579  pop     r13
0x18000457b  pop     r12
0x18000457d  pop     rdi
0x18000457e  pop     rsi
0x18000457f  pop     rbp
0x180004580  retn
0x180004582  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
