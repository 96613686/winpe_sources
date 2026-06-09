# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180024730`
- end: `0x180024a2c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800235f0`
- `0x18002394c`

## callees

- `0x1800182c4`
- `0x18001a890`
- `0x180024144`
- `0x180024730`
- `0x180024c58`
- `0x180024c80`
- `0x180024c94`
- `0x180024cb0`
- `0x180025674`
- `0x18004d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024857`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180024857`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024976`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180024976`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800249e8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800249e8`

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
    ModuleName = wil::details::g_pfnGetModuleName(v25);
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
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v25) == 0),
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
      wil::details::g_pfnDebugBreak(v25);
  }
}

```

## disassembly

```asm
0x180024730  mov     [rsp+arg_10], rbx
0x180024735  mov     [rsp+arg_8], edx
0x180024739  mov     [rsp+arg_0], rcx
0x18002473e  push    rbp
0x18002473f  push    rsi
0x180024740  push    rdi
0x180024741  push    r12
0x180024743  push    r13
0x180024745  push    r14
0x180024747  push    r15
0x180024749  sub     rsp, 40h
0x18002474d  mov     r14, [rsp+78h+arg_38]
0x180024755  xor     eax, eax
0x180024757  mov     rbx, [rsp+78h+arg_78]
0x18002475f  xor     ebp, ebp
0x180024761  mov     r15d, [rsp+78h+arg_30]
0x180024769  mov     r10, rcx
0x18002476c  mov     rsi, [rsp+78h+lpOutputString]
0x180024774  mov     r12, r9
0x180024777  mov     r13, r8
0x18002477a  mov     ecx, r15d
0x18002477d  mov     [rsi], ax
0x180024780  mov     rax, [rsp+78h+arg_60]
0x180024788  mov     byte ptr [rax], 0
0x18002478b  mov     edi, [r14]
0x18002478e  mov     [rbx+8], edi
0x180024791  mov     eax, [r14+4]
0x180024795  mov     [rbx+0Ch], eax
0x180024798  test    r15d, r15d
0x18002479b  jz      short loc_180024807
0x18002479d  sub     ecx, 1
0x1800247a0  jz      short loc_1800247FE
0x1800247a2  sub     ecx, 1
0x1800247a5  jz      short loc_1800247B5
0x1800247a7  cmp     ecx, 1
0x1800247aa  jnz     short loc_180024810
0x1800247ac  mov     ecx, edi; this
0x1800247ae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800247b3  jmp     short loc_18002480E
0x1800247b5  test    edi, edi
0x1800247b7  js      short loc_1800247F5
0x1800247b9  mov     rax, [rsp+78h+arg_28]
0x1800247c1  mov     edi, 8007029Ch
0x1800247c6  mov     [rsp+78h+var_40], ebp
0x1800247ca  mov     rcx, r10; int
0x1800247cd  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800247d1  mov     [rsp+78h+var_50], rax; __int64
0x1800247d6  mov     rax, [rsp+78h+arg_20]
0x1800247de  mov     [rsp+78h+var_58], rax; __int64
0x1800247e3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800247e8  mov     ecx, edi; this
0x1800247ea  mov     [rbx+8], edi
0x1800247ed  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800247f2  mov     [rbx+0Ch], eax
0x1800247f5  mov     ecx, edi; this
0x1800247f7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800247fc  jmp     short loc_18002480E
0x1800247fe  mov     ecx, edi; this
0x180024800  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180024805  jmp     short loc_18002480E
0x180024807  mov     ecx, edi; this
0x180024809  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002480e  mov     ebp, eax
0x180024810  mov     eax, [rsp+78h+arg_70]
0x180024817  mov     [rbx+4], eax
0x18002481a  mov     [rbx], r15d
0x18002481d  cmp     dword ptr [r14+8], 1
0x180024822  jnz     short loc_18002482A
0x180024824  or      eax, 8
0x180024827  mov     [rbx+4], eax
0x18002482a  mov     eax, 1
0x18002482f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180024837  inc     eax
0x180024839  xor     edi, edi
0x18002483b  mov     [rbx+10h], eax
0x18002483e  mov     rax, [rsp+78h+arg_40]
0x180024846  test    rax, rax
0x180024849  jz      short loc_180024850
0x18002484b  cmp     [rax], di
0x18002484e  jnz     short loc_180024853
0x180024850  mov     rax, rdi
0x180024853  mov     [rbx+18h], rax
0x180024857  call    cs:__imp_GetCurrentThreadId
0x18002485d  mov     [rbx+38h], r13
0x180024861  xorps   xmm0, xmm0
0x180024864  mov     [rbx+20h], eax
0x180024867  mov     eax, [rsp+78h+arg_8]
0x18002486e  mov     [rbx+40h], eax
0x180024871  mov     rax, [rsp+78h+arg_20]
0x180024879  mov     [rbx+28h], rax
0x18002487d  mov     rax, [rsp+78h+arg_28]
0x180024885  mov     [rbx+88h], rax
0x18002488c  mov     rax, [rsp+78h+arg_0]
0x180024894  mov     [rbx+90h], rax
0x18002489b  xor     eax, eax
0x18002489d  mov     [rbx+44h], ebp
0x1800248a0  mov     [rbx+30h], r12
0x1800248a4  mov     [rbx+48h], rdi
0x1800248a8  movups  xmmword ptr [rbx+68h], xmm0
0x1800248ac  mov     [rbx+78h], rax
0x1800248b0  movups  xmmword ptr [rbx+50h], xmm0
0x1800248b4  mov     [rbx+60h], rax
0x1800248b8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800248bf  test    rax, rax
0x1800248c2  jz      short loc_1800248CB
0x1800248c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248c9  jmp     short loc_1800248CE
0x1800248cb  mov     rax, rdi
0x1800248ce  mov     [rbx+80h], rax
0x1800248d5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800248dc  test    rax, rax
0x1800248df  jz      short loc_1800248E9
0x1800248e1  mov     rcx, rbx
0x1800248e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800248e9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800248f0  test    rax, rax
0x1800248f3  jz      short loc_18002490B
0x1800248f5  mov     rdx, [rsp+78h+arg_60]
0x1800248fd  mov     r8d, 400h
0x180024903  mov     rcx, rbx
0x180024906  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002490b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024912  test    rax, rax
0x180024915  jz      short loc_18002491F
0x180024917  mov     rcx, rbx
0x18002491a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002491f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180024926  test    rax, rax
0x180024929  jz      short loc_180024939
0x18002492b  test    byte ptr [rbx+4], 2
0x18002492f  jnz     short loc_180024939
0x180024931  mov     rcx, rbx
0x180024934  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024939  cmp     [rbx+8], edi
0x18002493c  jl      short loc_180024958
0x18002493e  cmp     r15d, 3
0x180024942  jnz     loc_180024A26
0x180024948  mov     ecx, 8000FFFFh; this
0x18002494d  mov     [rbx+8], ecx
0x180024950  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180024955  mov     [rbx+0Ch], eax
0x180024958  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002495f  jnz     short loc_180024980
0x180024961  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180024968  test    rax, rax
0x18002496b  jz      short loc_180024976
0x18002496d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024972  test    al, al
0x180024974  jmp     short loc_18002497E
0x180024976  call    cs:__imp_IsDebuggerPresent
0x18002497c  test    eax, eax
0x18002497e  jz      short loc_180024986
0x180024980  test    byte ptr [rbx+4], 2
0x180024984  jz      short loc_1800249AA
0x180024986  mov     rax, cs:g_pfnResultLoggingCallback
0x18002498d  test    rax, rax
0x180024990  jz      short loc_1800249EE
0x180024992  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180024999  jnz     short loc_1800249EE
0x18002499b  xor     r8d, r8d
0x18002499e  xor     edx, edx
0x1800249a0  mov     rcx, rbx
0x1800249a3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249a8  jmp     short loc_1800249EE
0x1800249aa  mov     rax, cs:g_pfnResultLoggingCallback
0x1800249b1  mov     ebp, 800h
0x1800249b6  test    rax, rax
0x1800249b9  jz      short loc_1800249D2
0x1800249bb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800249c2  jnz     short loc_1800249D2
0x1800249c4  mov     r8d, ebp
0x1800249c7  mov     rdx, rsi
0x1800249ca  mov     rcx, rbx
0x1800249cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800249d2  cmp     [rsi], di
0x1800249d5  jnz     short loc_1800249E5
0x1800249d7  mov     r8, rbx; unsigned __int64
0x1800249da  mov     rdx, rbp; unsigned __int16 *
0x1800249dd  mov     rcx, rsi; this
0x1800249e0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800249e5  mov     rcx, rsi; lpOutputString
0x1800249e8  call    cs:__imp_OutputDebugStringW
0x1800249ee  test    byte ptr [rbx+4], 4
0x1800249f2  jnz     short loc_1800249FD
0x1800249f4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800249fb  jz      short loc_180024A0E
0x1800249fd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180024a04  test    rax, rax
0x180024a07  jz      short loc_180024A0E
0x180024a09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024a0e  mov     rbx, [rsp+78h+arg_10]
0x180024a16  add     rsp, 40h
0x180024a1a  pop     r15
0x180024a1c  pop     r14
0x180024a1e  pop     r13
0x180024a20  pop     r12
0x180024a22  pop     rdi
0x180024a23  pop     rsi
0x180024a24  pop     rbp
0x180024a25  retn
0x180024a26  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
