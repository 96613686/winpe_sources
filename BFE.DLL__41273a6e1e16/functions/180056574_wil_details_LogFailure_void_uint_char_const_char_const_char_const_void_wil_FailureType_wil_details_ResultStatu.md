# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180056574`
- end: `0x18005687c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `776`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180056484`
- `0x18005c2b0`
- `0x18005c360`

## callees

- `0x18004c1a8`
- `0x180056574`
- `0x180056890`
- `0x18005c200`
- `0x18005db64`
- `0x18005ecf0`
- `0x18005edc8`
- `0x18005ede8`
- `0x1800609ec`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056697`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180056697`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800567be`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800567be`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180056836`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180056836`

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
0x180056574  mov     [rsp+arg_10], rbx
0x180056579  mov     [rsp+arg_8], edx
0x18005657d  mov     [rsp+arg_0], rcx
0x180056582  push    rbp
0x180056583  push    rsi
0x180056584  push    rdi
0x180056585  push    r12
0x180056587  push    r13
0x180056589  push    r14
0x18005658b  push    r15
0x18005658d  sub     rsp, 40h
0x180056591  mov     r12, r9
0x180056594  mov     r13, r8
0x180056597  mov     r10, rcx
0x18005659a  xor     eax, eax
0x18005659c  mov     rsi, [rsp+78h+lpOutputString]
0x1800565a4  mov     [rsi], ax
0x1800565a7  mov     rax, [rsp+78h+arg_60]
0x1800565af  mov     byte ptr [rax], 0
0x1800565b2  mov     r14, [rsp+78h+arg_38]
0x1800565ba  mov     edi, [r14]
0x1800565bd  mov     rbx, [rsp+78h+arg_78]
0x1800565c5  mov     [rbx+8], edi
0x1800565c8  mov     eax, [r14+4]
0x1800565cc  mov     [rbx+0Ch], eax
0x1800565cf  xor     ebp, ebp
0x1800565d1  mov     r15d, [rsp+78h+arg_30]
0x1800565d9  mov     ecx, r15d
0x1800565dc  test    r15d, r15d
0x1800565df  jz      short loc_180056647
0x1800565e1  sub     ecx, 1
0x1800565e4  jz      short loc_18005663E
0x1800565e6  sub     ecx, 1
0x1800565e9  jz      short loc_1800565F9
0x1800565eb  cmp     ecx, 1
0x1800565ee  jnz     short loc_180056650
0x1800565f0  mov     ecx, edi; this
0x1800565f2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800565f7  jmp     short loc_18005664E
0x1800565f9  test    edi, edi
0x1800565fb  js      short loc_180056635
0x1800565fd  mov     edi, 8007029Ch
0x180056602  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180056606  mov     rax, [rsp+78h+arg_28]
0x18005660e  mov     [rsp+78h+var_50], rax; __int64
0x180056613  mov     rax, [rsp+78h+arg_20]
0x18005661b  mov     [rsp+78h+var_58], rax; __int64
0x180056620  mov     rcx, r10; int
0x180056623  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180056628  mov     [rbx+8], edi
0x18005662b  mov     ecx, edi; this
0x18005662d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180056632  mov     [rbx+0Ch], eax
0x180056635  mov     ecx, edi; this
0x180056637  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005663c  jmp     short loc_18005664E
0x18005663e  mov     ecx, edi; this
0x180056640  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180056645  jmp     short loc_18005664E
0x180056647  mov     ecx, edi; this
0x180056649  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005664e  mov     ebp, eax
0x180056650  mov     [rbx], r15d
0x180056653  mov     eax, [rsp+78h+arg_70]
0x18005665a  mov     [rbx+4], eax
0x18005665d  cmp     dword ptr [r14+8], 1
0x180056662  jnz     short loc_18005666A
0x180056664  or      eax, 8
0x180056667  mov     [rbx+4], eax
0x18005666a  mov     eax, 1
0x18005666f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180056677  inc     eax
0x180056679  mov     [rbx+10h], eax
0x18005667c  mov     rax, [rsp+78h+arg_40]
0x180056684  xor     edi, edi
0x180056686  test    rax, rax
0x180056689  jz      short loc_180056690
0x18005668b  cmp     [rax], di
0x18005668e  jnz     short loc_180056693
0x180056690  mov     rax, rdi
0x180056693  mov     [rbx+18h], rax
0x180056697  call    cs:__imp_GetCurrentThreadId
0x18005669e  nop     dword ptr [rax+rax+00h]
0x1800566a3  mov     [rbx+20h], eax
0x1800566a6  mov     [rbx+38h], r13
0x1800566aa  mov     eax, [rsp+78h+arg_8]
0x1800566b1  mov     [rbx+40h], eax
0x1800566b4  mov     [rbx+44h], ebp
0x1800566b7  mov     rax, [rsp+78h+arg_20]
0x1800566bf  mov     [rbx+28h], rax
0x1800566c3  mov     [rbx+30h], r12
0x1800566c7  mov     rax, [rsp+78h+arg_28]
0x1800566cf  mov     [rbx+88h], rax
0x1800566d6  mov     rax, [rsp+78h+arg_0]
0x1800566de  mov     [rbx+90h], rax
0x1800566e5  mov     [rbx+48h], rdi
0x1800566e9  xorps   xmm0, xmm0
0x1800566ec  xor     eax, eax
0x1800566ee  movups  xmmword ptr [rbx+68h], xmm0
0x1800566f2  mov     [rbx+78h], rax
0x1800566f6  movups  xmmword ptr [rbx+50h], xmm0
0x1800566fa  mov     [rbx+60h], rax
0x1800566fe  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180056705  test    rax, rax
0x180056708  jz      short loc_180056711
0x18005670a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005670f  jmp     short loc_180056714
0x180056711  mov     rax, rdi
0x180056714  mov     [rbx+80h], rax
0x18005671b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180056722  test    rax, rax
0x180056725  jz      short loc_18005672F
0x180056727  mov     rcx, rbx
0x18005672a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005672f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180056736  test    rax, rax
0x180056739  jz      short loc_180056751
0x18005673b  mov     r8d, 400h
0x180056741  mov     rdx, [rsp+78h+arg_60]
0x180056749  mov     rcx, rbx
0x18005674c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056751  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180056758  test    rax, rax
0x18005675b  jz      short loc_180056765
0x18005675d  mov     rcx, rbx
0x180056760  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056765  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005676c  test    rax, rax
0x18005676f  jz      short loc_18005677F
0x180056771  test    byte ptr [rbx+4], 2
0x180056775  jnz     short loc_18005677F
0x180056777  mov     rcx, rbx
0x18005677a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005677f  cmp     [rbx+8], edi
0x180056782  jl      short loc_1800567A0
0x180056784  cmp     r15d, 3
0x180056788  jz      short loc_180056790
0x18005678a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180056790  mov     ecx, 8000FFFFh; this
0x180056795  mov     [rbx+8], ecx
0x180056798  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005679d  mov     [rbx+0Ch], eax
0x1800567a0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800567a7  jnz     short loc_1800567CE
0x1800567a9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800567b0  test    rax, rax
0x1800567b3  jz      short loc_1800567BE
0x1800567b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567ba  test    al, al
0x1800567bc  jmp     short loc_1800567CC
0x1800567be  call    cs:__imp_IsDebuggerPresent
0x1800567c5  nop     dword ptr [rax+rax+00h]
0x1800567ca  test    eax, eax
0x1800567cc  jz      short loc_1800567D4
0x1800567ce  test    byte ptr [rbx+4], 2
0x1800567d2  jz      short loc_1800567F8
0x1800567d4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800567db  test    rax, rax
0x1800567de  jz      short loc_180056842
0x1800567e0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800567e7  jnz     short loc_180056842
0x1800567e9  xor     r8d, r8d
0x1800567ec  xor     edx, edx
0x1800567ee  mov     rcx, rbx
0x1800567f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800567f6  jmp     short loc_180056842
0x1800567f8  mov     ebp, 800h
0x1800567fd  mov     rax, cs:g_pfnResultLoggingCallback
0x180056804  test    rax, rax
0x180056807  jz      short loc_180056820
0x180056809  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180056810  jnz     short loc_180056820
0x180056812  mov     r8d, ebp
0x180056815  mov     rdx, rsi
0x180056818  mov     rcx, rbx
0x18005681b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056820  cmp     [rsi], di
0x180056823  jnz     short loc_180056833
0x180056825  mov     r8, rbx; unsigned __int64
0x180056828  mov     rdx, rbp; unsigned __int16 *
0x18005682b  mov     rcx, rsi; this
0x18005682e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180056833  mov     rcx, rsi; lpOutputString
0x180056836  call    cs:__imp_OutputDebugStringW
0x18005683d  nop     dword ptr [rax+rax+00h]
0x180056842  test    byte ptr [rbx+4], 4
0x180056846  jnz     short loc_180056851
0x180056848  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005684f  jz      short loc_180056863
0x180056851  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180056858  test    rax, rax
0x18005685b  jz      short loc_180056863
0x18005685d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056862  nop
0x180056863  mov     rbx, [rsp+78h+arg_10]
0x18005686b  add     rsp, 40h
0x18005686f  pop     r15
0x180056871  pop     r14
0x180056873  pop     r13
0x180056875  pop     r12
0x180056877  pop     rdi
0x180056878  pop     rsi
0x180056879  pop     rbp
0x18005687a  retn
```
