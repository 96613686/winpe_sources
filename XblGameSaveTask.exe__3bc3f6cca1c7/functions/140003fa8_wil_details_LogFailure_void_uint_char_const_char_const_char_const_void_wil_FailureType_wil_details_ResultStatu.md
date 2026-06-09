# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003fa8`
- end: `0x1400042a1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400027b8`

## callees

- `0x1400021fc`
- `0x140003644`
- `0x140003de4`
- `0x140003fa8`
- `0x1400044ec`
- `0x140004510`
- `0x140004524`
- `0x140004540`
- `0x14000553c`
- `0x140007010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400040cb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400040cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000425c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000425c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400041ea`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400041ea`

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
0x140003fa8  mov     [rsp+arg_10], rbx
0x140003fad  mov     [rsp+arg_8], edx
0x140003fb1  mov     [rsp+arg_0], rcx
0x140003fb6  push    rbp
0x140003fb7  push    rsi
0x140003fb8  push    rdi
0x140003fb9  push    r12
0x140003fbb  push    r13
0x140003fbd  push    r14
0x140003fbf  push    r15
0x140003fc1  sub     rsp, 40h
0x140003fc5  mov     r12, r9
0x140003fc8  mov     r13, r8
0x140003fcb  mov     r10, rcx
0x140003fce  xor     eax, eax
0x140003fd0  mov     rsi, [rsp+78h+lpOutputString]
0x140003fd8  mov     [rsi], ax
0x140003fdb  mov     rax, [rsp+78h+arg_60]
0x140003fe3  mov     byte ptr [rax], 0
0x140003fe6  mov     r14, [rsp+78h+arg_38]
0x140003fee  mov     edi, [r14]
0x140003ff1  mov     rbx, [rsp+78h+arg_78]
0x140003ff9  mov     [rbx+8], edi
0x140003ffc  mov     eax, [r14+4]
0x140004000  mov     [rbx+0Ch], eax
0x140004003  xor     ebp, ebp
0x140004005  mov     r15d, [rsp+78h+arg_30]
0x14000400d  mov     ecx, r15d
0x140004010  test    r15d, r15d
0x140004013  jz      short loc_14000407B
0x140004015  sub     ecx, 1
0x140004018  jz      short loc_140004072
0x14000401a  sub     ecx, 1
0x14000401d  jz      short loc_14000402D
0x14000401f  cmp     ecx, 1
0x140004022  jnz     short loc_140004084
0x140004024  mov     ecx, edi; this
0x140004026  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000402b  jmp     short loc_140004082
0x14000402d  test    edi, edi
0x14000402f  js      short loc_140004069
0x140004031  mov     edi, 8007029Ch
0x140004036  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000403a  mov     rax, [rsp+78h+arg_28]
0x140004042  mov     [rsp+78h+var_50], rax; __int64
0x140004047  mov     rax, [rsp+78h+arg_20]
0x14000404f  mov     [rsp+78h+var_58], rax; __int64
0x140004054  mov     rcx, r10; int
0x140004057  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000405c  mov     [rbx+8], edi
0x14000405f  mov     ecx, edi; this
0x140004061  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004066  mov     [rbx+0Ch], eax
0x140004069  mov     ecx, edi; this
0x14000406b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004070  jmp     short loc_140004082
0x140004072  mov     ecx, edi; this
0x140004074  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004079  jmp     short loc_140004082
0x14000407b  mov     ecx, edi; this
0x14000407d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004082  mov     ebp, eax
0x140004084  mov     [rbx], r15d
0x140004087  mov     eax, [rsp+78h+arg_70]
0x14000408e  mov     [rbx+4], eax
0x140004091  cmp     dword ptr [r14+8], 1
0x140004096  jnz     short loc_14000409E
0x140004098  or      eax, 8
0x14000409b  mov     [rbx+4], eax
0x14000409e  mov     eax, 1
0x1400040a3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400040ab  inc     eax
0x1400040ad  mov     [rbx+10h], eax
0x1400040b0  mov     rax, [rsp+78h+arg_40]
0x1400040b8  xor     edi, edi
0x1400040ba  test    rax, rax
0x1400040bd  jz      short loc_1400040C4
0x1400040bf  cmp     [rax], di
0x1400040c2  jnz     short loc_1400040C7
0x1400040c4  mov     rax, rdi
0x1400040c7  mov     [rbx+18h], rax
0x1400040cb  call    cs:__imp_GetCurrentThreadId
0x1400040d1  mov     [rbx+20h], eax
0x1400040d4  mov     [rbx+38h], r13
0x1400040d8  mov     eax, [rsp+78h+arg_8]
0x1400040df  mov     [rbx+40h], eax
0x1400040e2  mov     [rbx+44h], ebp
0x1400040e5  mov     rax, [rsp+78h+arg_20]
0x1400040ed  mov     [rbx+28h], rax
0x1400040f1  mov     [rbx+30h], r12
0x1400040f5  mov     rax, [rsp+78h+arg_28]
0x1400040fd  mov     [rbx+88h], rax
0x140004104  mov     rax, [rsp+78h+arg_0]
0x14000410c  mov     [rbx+90h], rax
0x140004113  mov     [rbx+48h], rdi
0x140004117  xorps   xmm0, xmm0
0x14000411a  xor     eax, eax
0x14000411c  movups  xmmword ptr [rbx+68h], xmm0
0x140004120  mov     [rbx+78h], rax
0x140004124  movups  xmmword ptr [rbx+50h], xmm0
0x140004128  mov     [rbx+60h], rax
0x14000412c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004133  test    rax, rax
0x140004136  jz      short loc_14000413F
0x140004138  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000413d  jmp     short loc_140004142
0x14000413f  mov     rax, rdi
0x140004142  mov     [rbx+80h], rax
0x140004149  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004150  test    rax, rax
0x140004153  jz      short loc_14000415D
0x140004155  mov     rcx, rbx
0x140004158  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000415d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004164  test    rax, rax
0x140004167  jz      short loc_14000417F
0x140004169  mov     r8d, 400h
0x14000416f  mov     rdx, [rsp+78h+arg_60]
0x140004177  mov     rcx, rbx
0x14000417a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000417f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004186  test    rax, rax
0x140004189  jz      short loc_140004193
0x14000418b  mov     rcx, rbx
0x14000418e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004193  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000419a  test    rax, rax
0x14000419d  jz      short loc_1400041AD
0x14000419f  test    byte ptr [rbx+4], 2
0x1400041a3  jnz     short loc_1400041AD
0x1400041a5  mov     rcx, rbx
0x1400041a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041ad  cmp     [rbx+8], edi
0x1400041b0  jl      short loc_1400041CC
0x1400041b2  cmp     r15d, 3
0x1400041b6  jnz     loc_14000429B
0x1400041bc  mov     ecx, 8000FFFFh; this
0x1400041c1  mov     [rbx+8], ecx
0x1400041c4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400041c9  mov     [rbx+0Ch], eax
0x1400041cc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400041d3  jnz     short loc_1400041F4
0x1400041d5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400041dc  test    rax, rax
0x1400041df  jz      short loc_1400041EA
0x1400041e1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041e6  test    al, al
0x1400041e8  jmp     short loc_1400041F2
0x1400041ea  call    cs:__imp_IsDebuggerPresent
0x1400041f0  test    eax, eax
0x1400041f2  jz      short loc_1400041FA
0x1400041f4  test    byte ptr [rbx+4], 2
0x1400041f8  jz      short loc_14000421E
0x1400041fa  mov     rax, cs:g_pfnResultLoggingCallback
0x140004201  test    rax, rax
0x140004204  jz      short loc_140004262
0x140004206  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000420d  jnz     short loc_140004262
0x14000420f  xor     r8d, r8d
0x140004212  xor     edx, edx
0x140004214  mov     rcx, rbx
0x140004217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000421c  jmp     short loc_140004262
0x14000421e  mov     ebp, 800h
0x140004223  mov     rax, cs:g_pfnResultLoggingCallback
0x14000422a  test    rax, rax
0x14000422d  jz      short loc_140004246
0x14000422f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004236  jnz     short loc_140004246
0x140004238  mov     r8d, ebp
0x14000423b  mov     rdx, rsi
0x14000423e  mov     rcx, rbx
0x140004241  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004246  cmp     [rsi], di
0x140004249  jnz     short loc_140004259
0x14000424b  mov     r8, rbx; unsigned __int64
0x14000424e  mov     rdx, rbp; unsigned __int16 *
0x140004251  mov     rcx, rsi; this
0x140004254  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004259  mov     rcx, rsi; lpOutputString
0x14000425c  call    cs:__imp_OutputDebugStringW
0x140004262  test    byte ptr [rbx+4], 4
0x140004266  jnz     short loc_140004271
0x140004268  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000426f  jz      short loc_140004283
0x140004271  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004278  test    rax, rax
0x14000427b  jz      short loc_140004283
0x14000427d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004282  nop
0x140004283  mov     rbx, [rsp+78h+arg_10]
0x14000428b  add     rsp, 40h
0x14000428f  pop     r15
0x140004291  pop     r14
0x140004293  pop     r13
0x140004295  pop     r12
0x140004297  pop     rdi
0x140004298  pop     rsi
0x140004299  pop     rbp
0x14000429a  retn
0x14000429b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
