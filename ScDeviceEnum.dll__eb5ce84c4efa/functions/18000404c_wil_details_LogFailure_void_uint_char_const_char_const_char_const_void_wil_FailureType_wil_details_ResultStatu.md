# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000404c`
- end: `0x180004345`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18000278c`
- `0x180002ae8`

## callees

- `0x1800026c4`
- `0x1800036b4`
- `0x180003e88`
- `0x18000404c`
- `0x180004714`
- `0x180004730`
- `0x180004744`
- `0x180004760`
- `0x180005560`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000416f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000416f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000428e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000428e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004300`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180004300`

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
0x18000404c  mov     [rsp+arg_10], rbx
0x180004051  mov     [rsp+arg_8], edx
0x180004055  mov     [rsp+arg_0], rcx
0x18000405a  push    rbp
0x18000405b  push    rsi
0x18000405c  push    rdi
0x18000405d  push    r12
0x18000405f  push    r13
0x180004061  push    r14
0x180004063  push    r15
0x180004065  sub     rsp, 40h
0x180004069  mov     r12, r9
0x18000406c  mov     r13, r8
0x18000406f  mov     r10, rcx
0x180004072  xor     eax, eax
0x180004074  mov     rsi, [rsp+78h+lpOutputString]
0x18000407c  mov     [rsi], ax
0x18000407f  mov     rax, [rsp+78h+arg_60]
0x180004087  mov     byte ptr [rax], 0
0x18000408a  mov     r14, [rsp+78h+arg_38]
0x180004092  mov     edi, [r14]
0x180004095  mov     rbx, [rsp+78h+arg_78]
0x18000409d  mov     [rbx+8], edi
0x1800040a0  mov     eax, [r14+4]
0x1800040a4  mov     [rbx+0Ch], eax
0x1800040a7  xor     ebp, ebp
0x1800040a9  mov     r15d, [rsp+78h+arg_30]
0x1800040b1  mov     ecx, r15d
0x1800040b4  test    r15d, r15d
0x1800040b7  jz      short loc_18000411F
0x1800040b9  sub     ecx, 1
0x1800040bc  jz      short loc_180004116
0x1800040be  sub     ecx, 1
0x1800040c1  jz      short loc_1800040D1
0x1800040c3  cmp     ecx, 1
0x1800040c6  jnz     short loc_180004128
0x1800040c8  mov     ecx, edi; this
0x1800040ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800040cf  jmp     short loc_180004126
0x1800040d1  test    edi, edi
0x1800040d3  js      short loc_18000410D
0x1800040d5  mov     edi, 8007029Ch
0x1800040da  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800040de  mov     rax, [rsp+78h+arg_28]
0x1800040e6  mov     [rsp+78h+var_50], rax; __int64
0x1800040eb  mov     rax, [rsp+78h+arg_20]
0x1800040f3  mov     [rsp+78h+var_58], rax; __int64
0x1800040f8  mov     rcx, r10; int
0x1800040fb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180004100  mov     [rbx+8], edi
0x180004103  mov     ecx, edi; this
0x180004105  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000410a  mov     [rbx+0Ch], eax
0x18000410d  mov     ecx, edi; this
0x18000410f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180004114  jmp     short loc_180004126
0x180004116  mov     ecx, edi; this
0x180004118  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000411d  jmp     short loc_180004126
0x18000411f  mov     ecx, edi; this
0x180004121  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180004126  mov     ebp, eax
0x180004128  mov     [rbx], r15d
0x18000412b  mov     eax, [rsp+78h+arg_70]
0x180004132  mov     [rbx+4], eax
0x180004135  cmp     dword ptr [r14+8], 1
0x18000413a  jnz     short loc_180004142
0x18000413c  or      eax, 8
0x18000413f  mov     [rbx+4], eax
0x180004142  mov     eax, 1
0x180004147  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000414f  inc     eax
0x180004151  mov     [rbx+10h], eax
0x180004154  mov     rax, [rsp+78h+arg_40]
0x18000415c  xor     edi, edi
0x18000415e  test    rax, rax
0x180004161  jz      short loc_180004168
0x180004163  cmp     [rax], di
0x180004166  jnz     short loc_18000416B
0x180004168  mov     rax, rdi
0x18000416b  mov     [rbx+18h], rax
0x18000416f  call    cs:__imp_GetCurrentThreadId
0x180004175  mov     [rbx+20h], eax
0x180004178  mov     [rbx+38h], r13
0x18000417c  mov     eax, [rsp+78h+arg_8]
0x180004183  mov     [rbx+40h], eax
0x180004186  mov     [rbx+44h], ebp
0x180004189  mov     rax, [rsp+78h+arg_20]
0x180004191  mov     [rbx+28h], rax
0x180004195  mov     [rbx+30h], r12
0x180004199  mov     rax, [rsp+78h+arg_28]
0x1800041a1  mov     [rbx+88h], rax
0x1800041a8  mov     rax, [rsp+78h+arg_0]
0x1800041b0  mov     [rbx+90h], rax
0x1800041b7  mov     [rbx+48h], rdi
0x1800041bb  xorps   xmm0, xmm0
0x1800041be  xor     eax, eax
0x1800041c0  movups  xmmword ptr [rbx+68h], xmm0
0x1800041c4  mov     [rbx+78h], rax
0x1800041c8  movups  xmmword ptr [rbx+50h], xmm0
0x1800041cc  mov     [rbx+60h], rax
0x1800041d0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800041d7  test    rax, rax
0x1800041da  jz      short loc_1800041E3
0x1800041dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800041e1  jmp     short loc_1800041E6
0x1800041e3  mov     rax, rdi
0x1800041e6  mov     [rbx+80h], rax
0x1800041ed  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800041f4  test    rax, rax
0x1800041f7  jz      short loc_180004201
0x1800041f9  mov     rcx, rbx
0x1800041fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004201  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180004208  test    rax, rax
0x18000420b  jz      short loc_180004223
0x18000420d  mov     r8d, 400h
0x180004213  mov     rdx, [rsp+78h+arg_60]
0x18000421b  mov     rcx, rbx
0x18000421e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004223  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000422a  test    rax, rax
0x18000422d  jz      short loc_180004237
0x18000422f  mov     rcx, rbx
0x180004232  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004237  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000423e  test    rax, rax
0x180004241  jz      short loc_180004251
0x180004243  test    byte ptr [rbx+4], 2
0x180004247  jnz     short loc_180004251
0x180004249  mov     rcx, rbx
0x18000424c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004251  cmp     [rbx+8], edi
0x180004254  jl      short loc_180004270
0x180004256  cmp     r15d, 3
0x18000425a  jnz     loc_18000433F
0x180004260  mov     ecx, 8000FFFFh; this
0x180004265  mov     [rbx+8], ecx
0x180004268  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000426d  mov     [rbx+0Ch], eax
0x180004270  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180004277  jnz     short loc_180004298
0x180004279  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180004280  test    rax, rax
0x180004283  jz      short loc_18000428E
0x180004285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000428a  test    al, al
0x18000428c  jmp     short loc_180004296
0x18000428e  call    cs:__imp_IsDebuggerPresent
0x180004294  test    eax, eax
0x180004296  jz      short loc_18000429E
0x180004298  test    byte ptr [rbx+4], 2
0x18000429c  jz      short loc_1800042C2
0x18000429e  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042a5  test    rax, rax
0x1800042a8  jz      short loc_180004306
0x1800042aa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800042b1  jnz     short loc_180004306
0x1800042b3  xor     r8d, r8d
0x1800042b6  xor     edx, edx
0x1800042b8  mov     rcx, rbx
0x1800042bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042c0  jmp     short loc_180004306
0x1800042c2  mov     ebp, 800h
0x1800042c7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800042ce  test    rax, rax
0x1800042d1  jz      short loc_1800042EA
0x1800042d3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800042da  jnz     short loc_1800042EA
0x1800042dc  mov     r8d, ebp
0x1800042df  mov     rdx, rsi
0x1800042e2  mov     rcx, rbx
0x1800042e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800042ea  cmp     [rsi], di
0x1800042ed  jnz     short loc_1800042FD
0x1800042ef  mov     r8, rbx; unsigned __int64
0x1800042f2  mov     rdx, rbp; unsigned __int16 *
0x1800042f5  mov     rcx, rsi; this
0x1800042f8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800042fd  mov     rcx, rsi; lpOutputString
0x180004300  call    cs:__imp_OutputDebugStringW
0x180004306  test    byte ptr [rbx+4], 4
0x18000430a  jnz     short loc_180004315
0x18000430c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180004313  jz      short loc_180004327
0x180004315  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000431c  test    rax, rax
0x18000431f  jz      short loc_180004327
0x180004321  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004326  nop
0x180004327  mov     rbx, [rsp+78h+arg_10]
0x18000432f  add     rsp, 40h
0x180004333  pop     r15
0x180004335  pop     r14
0x180004337  pop     r13
0x180004339  pop     r12
0x18000433b  pop     rdi
0x18000433c  pop     rsi
0x18000433d  pop     rbp
0x18000433e  retn
0x18000433f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
