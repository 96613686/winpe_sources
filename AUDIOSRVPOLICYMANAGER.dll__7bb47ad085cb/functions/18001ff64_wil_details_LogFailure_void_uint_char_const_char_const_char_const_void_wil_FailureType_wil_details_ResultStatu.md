# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001ff64`
- end: `0x180020259`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18001fe68`
- `0x180033600`
- `0x1800336c0`
- `0x180037bb8`

## callees

- `0x18001ff64`
- `0x180027840`
- `0x18002785c`
- `0x18002ae04`
- `0x180033548`
- `0x180034454`
- `0x180035404`
- `0x180035420`
- `0x180036968`
- `0x18004c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020087`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180020087`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002021a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18002021a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800201a8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800201a8`

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
0x18001ff64  mov     [rsp+arg_10], rbx
0x18001ff69  mov     [rsp+arg_8], edx
0x18001ff6d  mov     [rsp+arg_0], rcx
0x18001ff72  push    rbp
0x18001ff73  push    rsi
0x18001ff74  push    rdi
0x18001ff75  push    r12
0x18001ff77  push    r13
0x18001ff79  push    r14
0x18001ff7b  push    r15
0x18001ff7d  sub     rsp, 40h
0x18001ff81  mov     r12, r9
0x18001ff84  mov     r13, r8
0x18001ff87  mov     r10, rcx
0x18001ff8a  xor     eax, eax
0x18001ff8c  mov     rsi, [rsp+78h+lpOutputString]
0x18001ff94  mov     [rsi], ax
0x18001ff97  mov     rax, [rsp+78h+arg_60]
0x18001ff9f  mov     byte ptr [rax], 0
0x18001ffa2  mov     r14, [rsp+78h+arg_38]
0x18001ffaa  mov     edi, [r14]
0x18001ffad  mov     rbx, [rsp+78h+arg_78]
0x18001ffb5  mov     [rbx+8], edi
0x18001ffb8  mov     eax, [r14+4]
0x18001ffbc  mov     [rbx+0Ch], eax
0x18001ffbf  xor     ebp, ebp
0x18001ffc1  mov     r15d, [rsp+78h+arg_30]
0x18001ffc9  mov     ecx, r15d
0x18001ffcc  test    r15d, r15d
0x18001ffcf  jz      short loc_180020037
0x18001ffd1  sub     ecx, 1
0x18001ffd4  jz      short loc_18002002E
0x18001ffd6  sub     ecx, 1
0x18001ffd9  jz      short loc_18001FFE9
0x18001ffdb  cmp     ecx, 1
0x18001ffde  jnz     short loc_180020040
0x18001ffe0  mov     ecx, edi; this
0x18001ffe2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001ffe7  jmp     short loc_18002003E
0x18001ffe9  test    edi, edi
0x18001ffeb  js      short loc_180020025
0x18001ffed  mov     edi, 8007029Ch
0x18001fff2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001fff6  mov     rax, [rsp+78h+arg_28]
0x18001fffe  mov     [rsp+78h+var_50], rax; __int64
0x180020003  mov     rax, [rsp+78h+arg_20]
0x18002000b  mov     [rsp+78h+var_58], rax; __int64
0x180020010  mov     rcx, r10; int
0x180020013  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180020018  mov     [rbx+8], edi
0x18002001b  mov     ecx, edi; this
0x18002001d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180020022  mov     [rbx+0Ch], eax
0x180020025  mov     ecx, edi; this
0x180020027  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002002c  jmp     short loc_18002003E
0x18002002e  mov     ecx, edi; this
0x180020030  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180020035  jmp     short loc_18002003E
0x180020037  mov     ecx, edi; this
0x180020039  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002003e  mov     ebp, eax
0x180020040  mov     [rbx], r15d
0x180020043  mov     eax, [rsp+78h+arg_70]
0x18002004a  mov     [rbx+4], eax
0x18002004d  cmp     dword ptr [r14+8], 1
0x180020052  jnz     short loc_18002005A
0x180020054  or      eax, 8
0x180020057  mov     [rbx+4], eax
0x18002005a  mov     eax, 1
0x18002005f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180020067  inc     eax
0x180020069  mov     [rbx+10h], eax
0x18002006c  mov     rax, [rsp+78h+arg_40]
0x180020074  xor     edi, edi
0x180020076  test    rax, rax
0x180020079  jz      short loc_180020080
0x18002007b  cmp     [rax], di
0x18002007e  jnz     short loc_180020083
0x180020080  mov     rax, rdi
0x180020083  mov     [rbx+18h], rax
0x180020087  call    cs:__imp_GetCurrentThreadId
0x18002008d  mov     [rbx+20h], eax
0x180020090  mov     [rbx+38h], r13
0x180020094  mov     eax, [rsp+78h+arg_8]
0x18002009b  mov     [rbx+40h], eax
0x18002009e  mov     [rbx+44h], ebp
0x1800200a1  mov     rax, [rsp+78h+arg_20]
0x1800200a9  mov     [rbx+28h], rax
0x1800200ad  mov     [rbx+30h], r12
0x1800200b1  mov     rax, [rsp+78h+arg_28]
0x1800200b9  mov     [rbx+88h], rax
0x1800200c0  mov     rax, [rsp+78h+arg_0]
0x1800200c8  mov     [rbx+90h], rax
0x1800200cf  mov     [rbx+48h], rdi
0x1800200d3  xorps   xmm0, xmm0
0x1800200d6  xor     eax, eax
0x1800200d8  movups  xmmword ptr [rbx+68h], xmm0
0x1800200dc  mov     [rbx+78h], rax
0x1800200e0  movups  xmmword ptr [rbx+50h], xmm0
0x1800200e4  mov     [rbx+60h], rax
0x1800200e8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800200ef  test    rax, rax
0x1800200f2  jz      short loc_1800200FB
0x1800200f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800200f9  jmp     short loc_1800200FE
0x1800200fb  mov     rax, rdi
0x1800200fe  mov     [rbx+80h], rax
0x180020105  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002010c  test    rax, rax
0x18002010f  jz      short loc_180020119
0x180020111  mov     rcx, rbx
0x180020114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020119  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180020120  test    rax, rax
0x180020123  jz      short loc_18002013B
0x180020125  mov     r8d, 400h
0x18002012b  mov     rdx, [rsp+78h+arg_60]
0x180020133  mov     rcx, rbx
0x180020136  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002013b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020142  test    rax, rax
0x180020145  jz      short loc_18002014F
0x180020147  mov     rcx, rbx
0x18002014a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002014f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180020156  test    rax, rax
0x180020159  jz      short loc_180020169
0x18002015b  test    byte ptr [rbx+4], 2
0x18002015f  jnz     short loc_180020169
0x180020161  mov     rcx, rbx
0x180020164  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020169  cmp     [rbx+8], edi
0x18002016c  jl      short loc_18002018A
0x18002016e  cmp     r15d, 3
0x180020172  jz      short loc_18002017A
0x180020174  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002017a  mov     ecx, 8000FFFFh; this
0x18002017f  mov     [rbx+8], ecx
0x180020182  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180020187  mov     [rbx+0Ch], eax
0x18002018a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180020191  jnz     short loc_1800201B2
0x180020193  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002019a  test    rax, rax
0x18002019d  jz      short loc_1800201A8
0x18002019f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201a4  test    al, al
0x1800201a6  jmp     short loc_1800201B0
0x1800201a8  call    cs:__imp_IsDebuggerPresent
0x1800201ae  test    eax, eax
0x1800201b0  jz      short loc_1800201B8
0x1800201b2  test    byte ptr [rbx+4], 2
0x1800201b6  jz      short loc_1800201DC
0x1800201b8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800201bf  test    rax, rax
0x1800201c2  jz      short loc_180020220
0x1800201c4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800201cb  jnz     short loc_180020220
0x1800201cd  xor     r8d, r8d
0x1800201d0  xor     edx, edx
0x1800201d2  mov     rcx, rbx
0x1800201d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800201da  jmp     short loc_180020220
0x1800201dc  mov     ebp, 800h
0x1800201e1  mov     rax, cs:g_pfnResultLoggingCallback
0x1800201e8  test    rax, rax
0x1800201eb  jz      short loc_180020204
0x1800201ed  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800201f4  jnz     short loc_180020204
0x1800201f6  mov     r8d, ebp
0x1800201f9  mov     rdx, rsi
0x1800201fc  mov     rcx, rbx
0x1800201ff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020204  cmp     [rsi], di
0x180020207  jnz     short loc_180020217
0x180020209  mov     r8, rbx; unsigned __int64
0x18002020c  mov     rdx, rbp; unsigned __int16 *
0x18002020f  mov     rcx, rsi; this
0x180020212  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180020217  mov     rcx, rsi; lpOutputString
0x18002021a  call    cs:__imp_OutputDebugStringW
0x180020220  test    byte ptr [rbx+4], 4
0x180020224  jnz     short loc_18002022F
0x180020226  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002022d  jz      short loc_180020241
0x18002022f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180020236  test    rax, rax
0x180020239  jz      short loc_180020241
0x18002023b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020240  nop
0x180020241  mov     rbx, [rsp+78h+arg_10]
0x180020249  add     rsp, 40h
0x18002024d  pop     r15
0x18002024f  pop     r14
0x180020251  pop     r13
0x180020253  pop     r12
0x180020255  pop     rdi
0x180020256  pop     rsi
0x180020257  pop     rbp
0x180020258  retn
```
