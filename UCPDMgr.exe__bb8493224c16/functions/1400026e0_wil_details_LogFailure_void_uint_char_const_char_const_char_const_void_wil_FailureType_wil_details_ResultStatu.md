# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400026e0`
- end: `0x1400029f4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `788`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004c6c`

## callees

- `0x14000142c`
- `0x140001898`
- `0x1400018b4`
- `0x1400018d0`
- `0x1400018f0`
- `0x140001b30`
- `0x1400026e0`
- `0x140002c20`
- `0x14000463c`
- `0x14000f4d0`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x14000280e`
- `KERNEL32!GetCurrentThreadId` at `0x14000280e`
- `KERNEL32!OutputDebugStringW` at `0x1400029af`
- `KERNEL32!OutputDebugStringW` at `0x1400029af`
- `KERNEL32!IsDebuggerPresent` at `0x140002936`
- `KERNEL32!IsDebuggerPresent` at `0x140002936`

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
  unsigned int v17; // edi
  int v18; // ebp
  int v19; // eax
  _WORD *v20; // rax
  unsigned __int64 IsDebuggerPresent; // rcx
  const struct wil::FailureInfo *v22; // r9
  __int64 ModuleName; // rax
  wil::details *v24; // [rsp+30h] [rbp-48h]

  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v17 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  v18 = 0;
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v19 = wil::details::RecordReturn((wil::details *)v17, a2);
        break;
      case 2:
        if ( (v17 & 0x80000000) == 0 )
        {
          v17 = -2147024228;
          LODWORD(v24) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v24);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
        }
        v19 = wil::details::RecordLog((wil::details *)v17, a2);
        break;
      case 3:
        v19 = wil::details::RecordFailFast((wil::details *)v17, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v19 = wil::details::RecordException((wil::details *)v17, a2);
  }
  v18 = v19;
LABEL_12:
  *(_DWORD *)a16 = a7;
  *(_DWORD *)(a16 + 4) = a15;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v20 = a9;
  if ( !a9 || !*a9 )
    v20 = 0;
  *(_QWORD *)(a16 + 24) = v20;
  *(_DWORD *)(a16 + 32) = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 64) = a2;
  *(_DWORD *)(a16 + 68) = v18;
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
    ModuleName = wil::details::g_pfnGetModuleName(IsDebuggerPresent);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected((wil::details::in1diag3 *)IsDebuggerPresent);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( (wil::g_fIsDebuggerPresent
     || (!wil::g_pfnIsDebuggerPresent
       ? (IsDebuggerPresent = ::IsDebuggerPresent())
       : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent(IsDebuggerPresent)),
         (_DWORD)IsDebuggerPresent))
    && (*(_BYTE *)(a16 + 4) & 2) == 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v22);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(IsDebuggerPresent);
  }
}

```

## disassembly

```asm
0x1400026e0  mov     rax, rsp
0x1400026e3  mov     [rax+20h], rbx
0x1400026e7  mov     [rax+18h], r8
0x1400026eb  mov     [rax+10h], edx
0x1400026ee  mov     [rax+8], rcx
0x1400026f2  push    rbp
0x1400026f3  push    rsi
0x1400026f4  push    rdi
0x1400026f5  push    r12
0x1400026f7  push    r13
0x1400026f9  push    r14
0x1400026fb  push    r15
0x1400026fd  sub     rsp, 40h
0x140002701  mov     r13, r9
0x140002704  mov     r10, rcx
0x140002707  mov     r14d, [rsp+78h+arg_70]
0x14000270f  xor     r9d, r9d
0x140002712  mov     rsi, [rsp+78h+lpOutputString]
0x14000271a  mov     [rsi], r9w
0x14000271e  mov     rax, [rsp+78h+arg_60]
0x140002726  mov     [rax], r9b
0x140002729  mov     r15, [rsp+78h+arg_38]
0x140002731  mov     edi, [r15]
0x140002734  mov     rbx, [rsp+78h+arg_78]
0x14000273c  mov     [rbx+8], edi
0x14000273f  mov     eax, [r15+4]
0x140002743  mov     [rbx+0Ch], eax
0x140002746  mov     ebp, r9d
0x140002749  mov     r12d, [rsp+78h+arg_30]
0x140002751  mov     ecx, r12d
0x140002754  test    r12d, r12d
0x140002757  jz      short loc_1400027C2
0x140002759  sub     ecx, 1
0x14000275c  jz      short loc_1400027B9
0x14000275e  sub     ecx, 1
0x140002761  jz      short loc_140002771
0x140002763  cmp     ecx, 1
0x140002766  jnz     short loc_1400027CB
0x140002768  mov     ecx, edi; this
0x14000276a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000276f  jmp     short loc_1400027C9
0x140002771  test    edi, edi
0x140002773  js      short loc_1400027B0
0x140002775  mov     edi, 8007029Ch
0x14000277a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000277e  mov     rax, [rsp+78h+arg_28]
0x140002786  mov     [rsp+78h+var_50], rax; __int64
0x14000278b  mov     rax, [rsp+78h+arg_20]
0x140002793  mov     [rsp+78h+var_58], rax; __int64
0x140002798  mov     r9, r13; int
0x14000279b  mov     rcx, r10; int
0x14000279e  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1400027a3  mov     [rbx+8], edi
0x1400027a6  mov     ecx, edi; this
0x1400027a8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400027ad  mov     [rbx+0Ch], eax
0x1400027b0  mov     ecx, edi; this
0x1400027b2  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400027b7  jmp     short loc_1400027C9
0x1400027b9  mov     ecx, edi; this
0x1400027bb  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400027c0  jmp     short loc_1400027C9
0x1400027c2  mov     ecx, edi; this
0x1400027c4  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400027c9  mov     ebp, eax
0x1400027cb  mov     [rbx], r12d
0x1400027ce  mov     [rbx+4], r14d
0x1400027d2  cmp     dword ptr [r15+8], 1
0x1400027d7  jnz     short loc_1400027E1
0x1400027d9  or      r14d, 8
0x1400027dd  mov     [rbx+4], r14d
0x1400027e1  mov     eax, 1
0x1400027e6  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400027ee  inc     eax
0x1400027f0  mov     [rbx+10h], eax
0x1400027f3  mov     rax, [rsp+78h+arg_40]
0x1400027fb  xor     edi, edi
0x1400027fd  test    rax, rax
0x140002800  jz      short loc_140002807
0x140002802  cmp     [rax], di
0x140002805  jnz     short loc_14000280A
0x140002807  mov     rax, rdi
0x14000280a  mov     [rbx+18h], rax
0x14000280e  call    cs:__imp_GetCurrentThreadId
0x140002814  mov     [rbx+20h], eax
0x140002817  mov     rax, [rsp+78h+arg_10]
0x14000281f  mov     [rbx+38h], rax
0x140002823  mov     eax, [rsp+78h+arg_8]
0x14000282a  mov     [rbx+40h], eax
0x14000282d  mov     [rbx+44h], ebp
0x140002830  mov     rax, [rsp+78h+arg_20]
0x140002838  mov     [rbx+28h], rax
0x14000283c  mov     [rbx+30h], r13
0x140002840  mov     rax, [rsp+78h+arg_28]
0x140002848  mov     [rbx+88h], rax
0x14000284f  mov     rax, [rsp+78h+arg_0]
0x140002857  mov     [rbx+90h], rax
0x14000285e  mov     [rbx+48h], rdi
0x140002862  xorps   xmm0, xmm0
0x140002865  xor     eax, eax
0x140002867  movups  xmmword ptr [rbx+68h], xmm0
0x14000286b  mov     [rbx+78h], rax
0x14000286f  movups  xmmword ptr [rbx+50h], xmm0
0x140002873  mov     [rbx+60h], rax
0x140002877  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000287e  test    rax, rax
0x140002881  jz      short loc_14000288A
0x140002883  call    _guard_dispatch_icall
0x140002888  jmp     short loc_14000288D
0x14000288a  mov     rax, rdi
0x14000288d  mov     [rbx+80h], rax
0x140002894  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000289b  test    rax, rax
0x14000289e  jz      short loc_1400028A8
0x1400028a0  mov     rcx, rbx
0x1400028a3  call    _guard_dispatch_icall
0x1400028a8  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1400028af  test    rax, rax
0x1400028b2  jz      short loc_1400028CA
0x1400028b4  mov     r8d, 400h
0x1400028ba  mov     rdx, [rsp+78h+arg_60]
0x1400028c2  mov     rcx, rbx
0x1400028c5  call    _guard_dispatch_icall
0x1400028ca  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400028d1  test    rax, rax
0x1400028d4  jz      short loc_1400028DE
0x1400028d6  mov     rcx, rbx
0x1400028d9  call    _guard_dispatch_icall
0x1400028de  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400028e5  test    rax, rax
0x1400028e8  jz      short loc_1400028F8
0x1400028ea  test    byte ptr [rbx+4], 2
0x1400028ee  jnz     short loc_1400028F8
0x1400028f0  mov     rcx, rbx
0x1400028f3  call    _guard_dispatch_icall
0x1400028f8  cmp     [rbx+8], edi
0x1400028fb  jl      short loc_140002917
0x1400028fd  cmp     r12d, 3
0x140002901  jnz     loc_1400029EE
0x140002907  mov     ecx, 8000FFFFh; this
0x14000290c  mov     [rbx+8], ecx
0x14000290f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140002914  mov     [rbx+0Ch], eax
0x140002917  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000291e  jnz     short loc_140002947
0x140002920  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140002927  test    rax, rax
0x14000292a  jz      short loc_140002936
0x14000292c  call    _guard_dispatch_icall
0x140002931  movzx   ecx, al
0x140002934  jmp     short loc_140002943
0x140002936  call    cs:__imp_IsDebuggerPresent
0x14000293c  mov     ecx, edi
0x14000293e  test    eax, eax
0x140002940  setnz   cl
0x140002943  test    ecx, ecx
0x140002945  jz      short loc_14000294D
0x140002947  test    byte ptr [rbx+4], 2
0x14000294b  jz      short loc_140002971
0x14000294d  mov     rax, cs:g_pfnResultLoggingCallback
0x140002954  test    rax, rax
0x140002957  jz      short loc_1400029B5
0x140002959  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140002960  jnz     short loc_1400029B5
0x140002962  xor     r8d, r8d
0x140002965  xor     edx, edx
0x140002967  mov     rcx, rbx
0x14000296a  call    _guard_dispatch_icall
0x14000296f  jmp     short loc_1400029B5
0x140002971  mov     ebp, 800h
0x140002976  mov     rax, cs:g_pfnResultLoggingCallback
0x14000297d  test    rax, rax
0x140002980  jz      short loc_140002999
0x140002982  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140002989  jnz     short loc_140002999
0x14000298b  mov     r8d, ebp
0x14000298e  mov     rdx, rsi
0x140002991  mov     rcx, rbx
0x140002994  call    _guard_dispatch_icall
0x140002999  cmp     [rsi], di
0x14000299c  jnz     short loc_1400029AC
0x14000299e  mov     r8, rbx; unsigned __int64
0x1400029a1  mov     rdx, rbp; wchar_t *
0x1400029a4  mov     rcx, rsi; this
0x1400029a7  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1400029ac  mov     rcx, rsi; lpOutputString
0x1400029af  call    cs:__imp_OutputDebugStringW
0x1400029b5  test    byte ptr [rbx+4], 4
0x1400029b9  jnz     short loc_1400029C4
0x1400029bb  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1400029c2  jz      short loc_1400029D6
0x1400029c4  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400029cb  test    rax, rax
0x1400029ce  jz      short loc_1400029D6
0x1400029d0  call    _guard_dispatch_icall
0x1400029d5  nop
0x1400029d6  mov     rbx, [rsp+78h+arg_18]
0x1400029de  add     rsp, 40h
0x1400029e2  pop     r15
0x1400029e4  pop     r14
0x1400029e6  pop     r13
0x1400029e8  pop     r12
0x1400029ea  pop     rdi
0x1400029eb  pop     rsi
0x1400029ec  pop     rbp
0x1400029ed  retn
0x1400029ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
