# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140003fd8`
- end: `0x1400042d1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14000278c`

## callees

- `0x1400021b8`
- `0x140003674`
- `0x140003e14`
- `0x140003fd8`
- `0x140004564`
- `0x140004580`
- `0x140004594`
- `0x1400045b0`
- `0x14000572c`
- `0x140008010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x1400040fb`
- `KERNEL32!GetCurrentThreadId` at `0x1400040fb`
- `KERNEL32!OutputDebugStringW` at `0x14000428c`
- `KERNEL32!OutputDebugStringW` at `0x14000428c`
- `KERNEL32!IsDebuggerPresent` at `0x14000421a`
- `KERNEL32!IsDebuggerPresent` at `0x14000421a`

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
0x140003fd8  mov     [rsp+arg_10], rbx
0x140003fdd  mov     [rsp+arg_8], edx
0x140003fe1  mov     [rsp+arg_0], rcx
0x140003fe6  push    rbp
0x140003fe7  push    rsi
0x140003fe8  push    rdi
0x140003fe9  push    r12
0x140003feb  push    r13
0x140003fed  push    r14
0x140003fef  push    r15
0x140003ff1  sub     rsp, 40h
0x140003ff5  mov     r12, r9
0x140003ff8  mov     r13, r8
0x140003ffb  mov     r10, rcx
0x140003ffe  xor     eax, eax
0x140004000  mov     rsi, [rsp+78h+lpOutputString]
0x140004008  mov     [rsi], ax
0x14000400b  mov     rax, [rsp+78h+arg_60]
0x140004013  mov     byte ptr [rax], 0
0x140004016  mov     r14, [rsp+78h+arg_38]
0x14000401e  mov     edi, [r14]
0x140004021  mov     rbx, [rsp+78h+arg_78]
0x140004029  mov     [rbx+8], edi
0x14000402c  mov     eax, [r14+4]
0x140004030  mov     [rbx+0Ch], eax
0x140004033  xor     ebp, ebp
0x140004035  mov     r15d, [rsp+78h+arg_30]
0x14000403d  mov     ecx, r15d
0x140004040  test    r15d, r15d
0x140004043  jz      short loc_1400040AB
0x140004045  sub     ecx, 1
0x140004048  jz      short loc_1400040A2
0x14000404a  sub     ecx, 1
0x14000404d  jz      short loc_14000405D
0x14000404f  cmp     ecx, 1
0x140004052  jnz     short loc_1400040B4
0x140004054  mov     ecx, edi; this
0x140004056  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000405b  jmp     short loc_1400040B2
0x14000405d  test    edi, edi
0x14000405f  js      short loc_140004099
0x140004061  mov     edi, 8007029Ch
0x140004066  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000406a  mov     rax, [rsp+78h+arg_28]
0x140004072  mov     [rsp+78h+var_50], rax; __int64
0x140004077  mov     rax, [rsp+78h+arg_20]
0x14000407f  mov     [rsp+78h+var_58], rax; __int64
0x140004084  mov     rcx, r10; int
0x140004087  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000408c  mov     [rbx+8], edi
0x14000408f  mov     ecx, edi; this
0x140004091  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004096  mov     [rbx+0Ch], eax
0x140004099  mov     ecx, edi; this
0x14000409b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1400040a0  jmp     short loc_1400040B2
0x1400040a2  mov     ecx, edi; this
0x1400040a4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1400040a9  jmp     short loc_1400040B2
0x1400040ab  mov     ecx, edi; this
0x1400040ad  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400040b2  mov     ebp, eax
0x1400040b4  mov     [rbx], r15d
0x1400040b7  mov     eax, [rsp+78h+arg_70]
0x1400040be  mov     [rbx+4], eax
0x1400040c1  cmp     dword ptr [r14+8], 1
0x1400040c6  jnz     short loc_1400040CE
0x1400040c8  or      eax, 8
0x1400040cb  mov     [rbx+4], eax
0x1400040ce  mov     eax, 1
0x1400040d3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400040db  inc     eax
0x1400040dd  mov     [rbx+10h], eax
0x1400040e0  mov     rax, [rsp+78h+arg_40]
0x1400040e8  xor     edi, edi
0x1400040ea  test    rax, rax
0x1400040ed  jz      short loc_1400040F4
0x1400040ef  cmp     [rax], di
0x1400040f2  jnz     short loc_1400040F7
0x1400040f4  mov     rax, rdi
0x1400040f7  mov     [rbx+18h], rax
0x1400040fb  call    cs:__imp_GetCurrentThreadId
0x140004101  mov     [rbx+20h], eax
0x140004104  mov     [rbx+38h], r13
0x140004108  mov     eax, [rsp+78h+arg_8]
0x14000410f  mov     [rbx+40h], eax
0x140004112  mov     [rbx+44h], ebp
0x140004115  mov     rax, [rsp+78h+arg_20]
0x14000411d  mov     [rbx+28h], rax
0x140004121  mov     [rbx+30h], r12
0x140004125  mov     rax, [rsp+78h+arg_28]
0x14000412d  mov     [rbx+88h], rax
0x140004134  mov     rax, [rsp+78h+arg_0]
0x14000413c  mov     [rbx+90h], rax
0x140004143  mov     [rbx+48h], rdi
0x140004147  xorps   xmm0, xmm0
0x14000414a  xor     eax, eax
0x14000414c  movups  xmmword ptr [rbx+68h], xmm0
0x140004150  mov     [rbx+78h], rax
0x140004154  movups  xmmword ptr [rbx+50h], xmm0
0x140004158  mov     [rbx+60h], rax
0x14000415c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004163  test    rax, rax
0x140004166  jz      short loc_14000416F
0x140004168  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000416d  jmp     short loc_140004172
0x14000416f  mov     rax, rdi
0x140004172  mov     [rbx+80h], rax
0x140004179  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004180  test    rax, rax
0x140004183  jz      short loc_14000418D
0x140004185  mov     rcx, rbx
0x140004188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000418d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004194  test    rax, rax
0x140004197  jz      short loc_1400041AF
0x140004199  mov     r8d, 400h
0x14000419f  mov     rdx, [rsp+78h+arg_60]
0x1400041a7  mov     rcx, rbx
0x1400041aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041af  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400041b6  test    rax, rax
0x1400041b9  jz      short loc_1400041C3
0x1400041bb  mov     rcx, rbx
0x1400041be  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041c3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400041ca  test    rax, rax
0x1400041cd  jz      short loc_1400041DD
0x1400041cf  test    byte ptr [rbx+4], 2
0x1400041d3  jnz     short loc_1400041DD
0x1400041d5  mov     rcx, rbx
0x1400041d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400041dd  cmp     [rbx+8], edi
0x1400041e0  jl      short loc_1400041FC
0x1400041e2  cmp     r15d, 3
0x1400041e6  jnz     loc_1400042CB
0x1400041ec  mov     ecx, 8000FFFFh; this
0x1400041f1  mov     [rbx+8], ecx
0x1400041f4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400041f9  mov     [rbx+0Ch], eax
0x1400041fc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004203  jnz     short loc_140004224
0x140004205  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000420c  test    rax, rax
0x14000420f  jz      short loc_14000421A
0x140004211  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004216  test    al, al
0x140004218  jmp     short loc_140004222
0x14000421a  call    cs:__imp_IsDebuggerPresent
0x140004220  test    eax, eax
0x140004222  jz      short loc_14000422A
0x140004224  test    byte ptr [rbx+4], 2
0x140004228  jz      short loc_14000424E
0x14000422a  mov     rax, cs:g_pfnResultLoggingCallback
0x140004231  test    rax, rax
0x140004234  jz      short loc_140004292
0x140004236  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000423d  jnz     short loc_140004292
0x14000423f  xor     r8d, r8d
0x140004242  xor     edx, edx
0x140004244  mov     rcx, rbx
0x140004247  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000424c  jmp     short loc_140004292
0x14000424e  mov     ebp, 800h
0x140004253  mov     rax, cs:g_pfnResultLoggingCallback
0x14000425a  test    rax, rax
0x14000425d  jz      short loc_140004276
0x14000425f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004266  jnz     short loc_140004276
0x140004268  mov     r8d, ebp
0x14000426b  mov     rdx, rsi
0x14000426e  mov     rcx, rbx
0x140004271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004276  cmp     [rsi], di
0x140004279  jnz     short loc_140004289
0x14000427b  mov     r8, rbx; unsigned __int64
0x14000427e  mov     rdx, rbp; unsigned __int16 *
0x140004281  mov     rcx, rsi; this
0x140004284  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140004289  mov     rcx, rsi; lpOutputString
0x14000428c  call    cs:__imp_OutputDebugStringW
0x140004292  test    byte ptr [rbx+4], 4
0x140004296  jnz     short loc_1400042A1
0x140004298  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000429f  jz      short loc_1400042B3
0x1400042a1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1400042a8  test    rax, rax
0x1400042ab  jz      short loc_1400042B3
0x1400042ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400042b2  nop
0x1400042b3  mov     rbx, [rsp+78h+arg_10]
0x1400042bb  add     rsp, 40h
0x1400042bf  pop     r15
0x1400042c1  pop     r14
0x1400042c3  pop     r13
0x1400042c5  pop     r12
0x1400042c7  pop     rdi
0x1400042c8  pop     rsi
0x1400042c9  pop     rbp
0x1400042ca  retn
0x1400042cb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
