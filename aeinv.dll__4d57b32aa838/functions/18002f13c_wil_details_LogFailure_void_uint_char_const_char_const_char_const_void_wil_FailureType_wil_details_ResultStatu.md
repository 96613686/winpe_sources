# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18002f13c`
- end: `0x18002f439`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18002ef40`
- `0x18002f030`
- `0x18005d028`
- `0x18005d0d8`

## callees

- `0x18002f13c`
- `0x180030dfc`
- `0x18005bc24`
- `0x18005cf24`
- `0x1800656f0`
- `0x180065710`
- `0x180065724`
- `0x180065740`
- `0x1800679c4`
- `0x180130010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x18002f388`
- `KERNEL32!IsDebuggerPresent` at `0x18002f388`
- `KERNEL32!OutputDebugStringW` at `0x18002f3fa`
- `KERNEL32!OutputDebugStringW` at `0x18002f3fa`
- `KERNEL32!GetCurrentThreadId` at `0x18002f267`
- `KERNEL32!GetCurrentThreadId` at `0x18002f267`

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
  wil::details *v28; // [rsp+30h] [rbp-58h]

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x18002f13c  mov     rax, rsp
0x18002f13f  mov     [rax+10h], edx
0x18002f142  mov     [rax+8], rcx
0x18002f146  push    rbp
0x18002f147  push    rsi
0x18002f148  push    rdi
0x18002f149  push    r12
0x18002f14b  push    r13
0x18002f14d  push    r14
0x18002f14f  push    r15
0x18002f151  sub     rsp, 50h
0x18002f155  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x18002f15d  mov     [rax+18h], rbx
0x18002f161  mov     r12, r9
0x18002f164  mov     r13, r8
0x18002f167  mov     r10, rcx
0x18002f16a  xor     eax, eax
0x18002f16c  mov     rsi, [rsp+88h+lpOutputString]
0x18002f174  mov     [rsi], ax
0x18002f177  mov     rax, [rsp+88h+arg_60]
0x18002f17f  mov     byte ptr [rax], 0
0x18002f182  mov     r14, [rsp+88h+arg_38]
0x18002f18a  mov     edi, [r14]
0x18002f18d  mov     rbx, [rsp+88h+arg_78]
0x18002f195  mov     [rbx+8], edi
0x18002f198  mov     eax, [r14+4]
0x18002f19c  mov     [rbx+0Ch], eax
0x18002f19f  xor     ebp, ebp
0x18002f1a1  mov     r15d, [rsp+88h+arg_30]
0x18002f1a9  mov     ecx, r15d
0x18002f1ac  test    r15d, r15d
0x18002f1af  jz      short loc_18002F217
0x18002f1b1  sub     ecx, 1
0x18002f1b4  jz      short loc_18002F20E
0x18002f1b6  sub     ecx, 1
0x18002f1b9  jz      short loc_18002F1C9
0x18002f1bb  cmp     ecx, 1
0x18002f1be  jnz     short loc_18002F220
0x18002f1c0  mov     ecx, edi; this
0x18002f1c2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18002f1c7  jmp     short loc_18002F21E
0x18002f1c9  test    edi, edi
0x18002f1cb  js      short loc_18002F205
0x18002f1cd  mov     edi, 8007029Ch
0x18002f1d2  mov     dword ptr [rsp+88h+var_58], edi; wil::details *
0x18002f1d6  mov     rax, [rsp+88h+arg_28]
0x18002f1de  mov     [rsp+88h+var_60], rax; __int64
0x18002f1e3  mov     rax, [rsp+88h+arg_20]
0x18002f1eb  mov     [rsp+88h+var_68], rax; __int64
0x18002f1f0  mov     rcx, r10; int
0x18002f1f3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18002f1f8  mov     [rbx+8], edi
0x18002f1fb  mov     ecx, edi; this
0x18002f1fd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002f202  mov     [rbx+0Ch], eax
0x18002f205  mov     ecx, edi; this
0x18002f207  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18002f20c  jmp     short loc_18002F21E
0x18002f20e  mov     ecx, edi; this
0x18002f210  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18002f215  jmp     short loc_18002F21E
0x18002f217  mov     ecx, edi; this
0x18002f219  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18002f21e  mov     ebp, eax
0x18002f220  mov     [rbx], r15d
0x18002f223  mov     eax, [rsp+88h+arg_70]
0x18002f22a  mov     [rbx+4], eax
0x18002f22d  cmp     dword ptr [r14+8], 1
0x18002f232  jnz     short loc_18002F23A
0x18002f234  or      eax, 8
0x18002f237  mov     [rbx+4], eax
0x18002f23a  mov     eax, 1
0x18002f23f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18002f247  inc     eax
0x18002f249  mov     [rbx+10h], eax
0x18002f24c  mov     rax, [rsp+88h+arg_40]
0x18002f254  xor     edi, edi
0x18002f256  test    rax, rax
0x18002f259  jz      short loc_18002F260
0x18002f25b  cmp     [rax], di
0x18002f25e  jnz     short loc_18002F263
0x18002f260  mov     rax, rdi
0x18002f263  mov     [rbx+18h], rax
0x18002f267  call    cs:__imp_GetCurrentThreadId
0x18002f26d  mov     [rbx+20h], eax
0x18002f270  mov     [rbx+38h], r13
0x18002f274  mov     eax, [rsp+88h+arg_8]
0x18002f27b  mov     [rbx+40h], eax
0x18002f27e  mov     [rbx+44h], ebp
0x18002f281  mov     rax, [rsp+88h+arg_20]
0x18002f289  mov     [rbx+28h], rax
0x18002f28d  mov     [rbx+30h], r12
0x18002f291  mov     rax, [rsp+88h+arg_28]
0x18002f299  mov     [rbx+88h], rax
0x18002f2a0  mov     rax, [rsp+88h+arg_0]
0x18002f2a8  mov     [rbx+90h], rax
0x18002f2af  mov     [rbx+48h], rdi
0x18002f2b3  xorps   xmm0, xmm0
0x18002f2b6  xor     eax, eax
0x18002f2b8  movups  xmmword ptr [rbx+68h], xmm0
0x18002f2bc  mov     [rbx+78h], rax
0x18002f2c0  movups  xmmword ptr [rbx+50h], xmm0
0x18002f2c4  mov     [rbx+60h], rax
0x18002f2c8  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002f2cf  test    rax, rax
0x18002f2d2  jz      short loc_18002F2DB
0x18002f2d4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2d9  jmp     short loc_18002F2DE
0x18002f2db  mov     rax, rdi
0x18002f2de  mov     [rbx+80h], rax
0x18002f2e5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18002f2ec  test    rax, rax
0x18002f2ef  jz      short loc_18002F2F9
0x18002f2f1  mov     rcx, rbx
0x18002f2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f2f9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18002f300  test    rax, rax
0x18002f303  jz      short loc_18002F31B
0x18002f305  mov     r8d, 400h
0x18002f30b  mov     rdx, [rsp+88h+arg_60]
0x18002f313  mov     rcx, rbx
0x18002f316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f31b  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002f322  test    rax, rax
0x18002f325  jz      short loc_18002F32F
0x18002f327  mov     rcx, rbx
0x18002f32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f32f  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18002f336  test    rax, rax
0x18002f339  jz      short loc_18002F349
0x18002f33b  test    byte ptr [rbx+4], 2
0x18002f33f  jnz     short loc_18002F349
0x18002f341  mov     rcx, rbx
0x18002f344  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f349  cmp     [rbx+8], edi
0x18002f34c  jl      short loc_18002F36A
0x18002f34e  cmp     r15d, 3
0x18002f352  jz      short loc_18002F35A
0x18002f354  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18002f35a  mov     ecx, 8000FFFFh; this
0x18002f35f  mov     [rbx+8], ecx
0x18002f362  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18002f367  mov     [rbx+0Ch], eax
0x18002f36a  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18002f371  jnz     short loc_18002F392
0x18002f373  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18002f37a  test    rax, rax
0x18002f37d  jz      short loc_18002F388
0x18002f37f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f384  test    al, al
0x18002f386  jmp     short loc_18002F390
0x18002f388  call    cs:__imp_IsDebuggerPresent
0x18002f38e  test    eax, eax
0x18002f390  jz      short loc_18002F398
0x18002f392  test    byte ptr [rbx+4], 2
0x18002f396  jz      short loc_18002F3BC
0x18002f398  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f39f  test    rax, rax
0x18002f3a2  jz      short loc_18002F400
0x18002f3a4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002f3ab  jnz     short loc_18002F400
0x18002f3ad  xor     r8d, r8d
0x18002f3b0  xor     edx, edx
0x18002f3b2  mov     rcx, rbx
0x18002f3b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3ba  jmp     short loc_18002F400
0x18002f3bc  mov     ebp, 800h
0x18002f3c1  mov     rax, cs:g_pfnResultLoggingCallback
0x18002f3c8  test    rax, rax
0x18002f3cb  jz      short loc_18002F3E4
0x18002f3cd  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18002f3d4  jnz     short loc_18002F3E4
0x18002f3d6  mov     r8d, ebp
0x18002f3d9  mov     rdx, rsi
0x18002f3dc  mov     rcx, rbx
0x18002f3df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f3e4  cmp     [rsi], di
0x18002f3e7  jnz     short loc_18002F3F7
0x18002f3e9  mov     r8, rbx; unsigned __int64
0x18002f3ec  mov     rdx, rbp; unsigned __int16 *
0x18002f3ef  mov     rcx, rsi; this
0x18002f3f2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18002f3f7  mov     rcx, rsi; lpOutputString
0x18002f3fa  call    cs:__imp_OutputDebugStringW
0x18002f400  test    byte ptr [rbx+4], 4
0x18002f404  jnz     short loc_18002F40F
0x18002f406  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18002f40d  jz      short loc_18002F421
0x18002f40f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18002f416  test    rax, rax
0x18002f419  jz      short loc_18002F421
0x18002f41b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002f420  nop
0x18002f421  mov     rbx, [rsp+88h+arg_10]
0x18002f429  add     rsp, 50h
0x18002f42d  pop     r15
0x18002f42f  pop     r14
0x18002f431  pop     r13
0x18002f433  pop     r12
0x18002f435  pop     rdi
0x18002f436  pop     rsi
0x18002f437  pop     rbp
0x18002f438  retn
```
