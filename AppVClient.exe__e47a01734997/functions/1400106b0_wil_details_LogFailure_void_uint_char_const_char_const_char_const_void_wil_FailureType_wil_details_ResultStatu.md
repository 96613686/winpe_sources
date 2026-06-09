# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400106b0`
- end: `0x1400109a9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400072dc`

## callees

- `0x140006d18`
- `0x14000c664`
- `0x14000df30`
- `0x1400106b0`
- `0x140011108`
- `0x140011130`
- `0x140011144`
- `0x140011160`
- `0x140013c48`
- `0x14006a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x1400108f2`
- `KERNEL32!IsDebuggerPresent` at `0x1400108f2`
- `KERNEL32!OutputDebugStringW` at `0x140010964`
- `KERNEL32!OutputDebugStringW` at `0x140010964`
- `KERNEL32!GetCurrentThreadId` at `0x1400107d3`
- `KERNEL32!GetCurrentThreadId` at `0x1400107d3`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x1400106b0  mov     [rsp+arg_10], rbx
0x1400106b5  mov     [rsp+arg_8], edx
0x1400106b9  mov     [rsp+arg_0], rcx
0x1400106be  push    rbp
0x1400106bf  push    rsi
0x1400106c0  push    rdi
0x1400106c1  push    r12
0x1400106c3  push    r13
0x1400106c5  push    r14
0x1400106c7  push    r15
0x1400106c9  sub     rsp, 40h
0x1400106cd  mov     r12, r9
0x1400106d0  mov     r13, r8
0x1400106d3  mov     r10, rcx
0x1400106d6  xor     eax, eax
0x1400106d8  mov     rsi, [rsp+78h+lpOutputString]
0x1400106e0  mov     [rsi], ax
0x1400106e3  mov     rax, [rsp+78h+arg_60]
0x1400106eb  mov     byte ptr [rax], 0
0x1400106ee  mov     r14, [rsp+78h+arg_38]
0x1400106f6  mov     edi, [r14]
0x1400106f9  mov     rbx, [rsp+78h+arg_78]
0x140010701  mov     [rbx+8], edi
0x140010704  mov     eax, [r14+4]
0x140010708  mov     [rbx+0Ch], eax
0x14001070b  xor     ebp, ebp
0x14001070d  mov     r15d, [rsp+78h+arg_30]
0x140010715  mov     ecx, r15d
0x140010718  test    r15d, r15d
0x14001071b  jz      short loc_140010783
0x14001071d  sub     ecx, 1
0x140010720  jz      short loc_14001077A
0x140010722  sub     ecx, 1
0x140010725  jz      short loc_140010735
0x140010727  cmp     ecx, 1
0x14001072a  jnz     short loc_14001078C
0x14001072c  mov     ecx, edi; this
0x14001072e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140010733  jmp     short loc_14001078A
0x140010735  test    edi, edi
0x140010737  js      short loc_140010771
0x140010739  mov     edi, 8007029Ch
0x14001073e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140010742  mov     rax, [rsp+78h+arg_28]
0x14001074a  mov     [rsp+78h+var_50], rax; __int64
0x14001074f  mov     rax, [rsp+78h+arg_20]
0x140010757  mov     [rsp+78h+var_58], rax; __int64
0x14001075c  mov     rcx, r10; int
0x14001075f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140010764  mov     [rbx+8], edi
0x140010767  mov     ecx, edi; this
0x140010769  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001076e  mov     [rbx+0Ch], eax
0x140010771  mov     ecx, edi; this
0x140010773  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140010778  jmp     short loc_14001078A
0x14001077a  mov     ecx, edi; this
0x14001077c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140010781  jmp     short loc_14001078A
0x140010783  mov     ecx, edi; this
0x140010785  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14001078a  mov     ebp, eax
0x14001078c  mov     [rbx], r15d
0x14001078f  mov     eax, [rsp+78h+arg_70]
0x140010796  mov     [rbx+4], eax
0x140010799  cmp     dword ptr [r14+8], 1
0x14001079e  jnz     short loc_1400107A6
0x1400107a0  or      eax, 8
0x1400107a3  mov     [rbx+4], eax
0x1400107a6  mov     eax, 1
0x1400107ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400107b3  inc     eax
0x1400107b5  mov     [rbx+10h], eax
0x1400107b8  mov     rax, [rsp+78h+arg_40]
0x1400107c0  xor     edi, edi
0x1400107c2  test    rax, rax
0x1400107c5  jz      short loc_1400107CC
0x1400107c7  cmp     [rax], di
0x1400107ca  jnz     short loc_1400107CF
0x1400107cc  mov     rax, rdi
0x1400107cf  mov     [rbx+18h], rax
0x1400107d3  call    cs:__imp_GetCurrentThreadId
0x1400107d9  mov     [rbx+20h], eax
0x1400107dc  mov     [rbx+38h], r13
0x1400107e0  mov     eax, [rsp+78h+arg_8]
0x1400107e7  mov     [rbx+40h], eax
0x1400107ea  mov     [rbx+44h], ebp
0x1400107ed  mov     rax, [rsp+78h+arg_20]
0x1400107f5  mov     [rbx+28h], rax
0x1400107f9  mov     [rbx+30h], r12
0x1400107fd  mov     rax, [rsp+78h+arg_28]
0x140010805  mov     [rbx+88h], rax
0x14001080c  mov     rax, [rsp+78h+arg_0]
0x140010814  mov     [rbx+90h], rax
0x14001081b  mov     [rbx+48h], rdi
0x14001081f  xorps   xmm0, xmm0
0x140010822  xor     eax, eax
0x140010824  movups  xmmword ptr [rbx+68h], xmm0
0x140010828  mov     [rbx+78h], rax
0x14001082c  movups  xmmword ptr [rbx+50h], xmm0
0x140010830  mov     [rbx+60h], rax
0x140010834  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001083b  test    rax, rax
0x14001083e  jz      short loc_140010847
0x140010840  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010845  jmp     short loc_14001084A
0x140010847  mov     rax, rdi
0x14001084a  mov     [rbx+80h], rax
0x140010851  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140010858  test    rax, rax
0x14001085b  jz      short loc_140010865
0x14001085d  mov     rcx, rbx
0x140010860  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010865  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14001086c  test    rax, rax
0x14001086f  jz      short loc_140010887
0x140010871  mov     r8d, 400h
0x140010877  mov     rdx, [rsp+78h+arg_60]
0x14001087f  mov     rcx, rbx
0x140010882  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010887  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001088e  test    rax, rax
0x140010891  jz      short loc_14001089B
0x140010893  mov     rcx, rbx
0x140010896  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001089b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400108a2  test    rax, rax
0x1400108a5  jz      short loc_1400108B5
0x1400108a7  test    byte ptr [rbx+4], 2
0x1400108ab  jnz     short loc_1400108B5
0x1400108ad  mov     rcx, rbx
0x1400108b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108b5  cmp     [rbx+8], edi
0x1400108b8  jl      short loc_1400108D4
0x1400108ba  cmp     r15d, 3
0x1400108be  jnz     loc_1400109A3
0x1400108c4  mov     ecx, 8000FFFFh; this
0x1400108c9  mov     [rbx+8], ecx
0x1400108cc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400108d1  mov     [rbx+0Ch], eax
0x1400108d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400108db  jnz     short loc_1400108FC
0x1400108dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400108e4  test    rax, rax
0x1400108e7  jz      short loc_1400108F2
0x1400108e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400108ee  test    al, al
0x1400108f0  jmp     short loc_1400108FA
0x1400108f2  call    cs:__imp_IsDebuggerPresent
0x1400108f8  test    eax, eax
0x1400108fa  jz      short loc_140010902
0x1400108fc  test    byte ptr [rbx+4], 2
0x140010900  jz      short loc_140010926
0x140010902  mov     rax, cs:g_pfnResultLoggingCallback
0x140010909  test    rax, rax
0x14001090c  jz      short loc_14001096A
0x14001090e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140010915  jnz     short loc_14001096A
0x140010917  xor     r8d, r8d
0x14001091a  xor     edx, edx
0x14001091c  mov     rcx, rbx
0x14001091f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010924  jmp     short loc_14001096A
0x140010926  mov     ebp, 800h
0x14001092b  mov     rax, cs:g_pfnResultLoggingCallback
0x140010932  test    rax, rax
0x140010935  jz      short loc_14001094E
0x140010937  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001093e  jnz     short loc_14001094E
0x140010940  mov     r8d, ebp
0x140010943  mov     rdx, rsi
0x140010946  mov     rcx, rbx
0x140010949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001094e  cmp     [rsi], di
0x140010951  jnz     short loc_140010961
0x140010953  mov     r8, rbx; unsigned __int64
0x140010956  mov     rdx, rbp; wchar_t *
0x140010959  mov     rcx, rsi; Buffer
0x14001095c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140010961  mov     rcx, rsi; lpOutputString
0x140010964  call    cs:__imp_OutputDebugStringW
0x14001096a  test    byte ptr [rbx+4], 4
0x14001096e  jnz     short loc_140010979
0x140010970  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140010977  jz      short loc_14001098B
0x140010979  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140010980  test    rax, rax
0x140010983  jz      short loc_14001098B
0x140010985  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001098a  nop
0x14001098b  mov     rbx, [rsp+78h+arg_10]
0x140010993  add     rsp, 40h
0x140010997  pop     r15
0x140010999  pop     r14
0x14001099b  pop     r13
0x14001099d  pop     r12
0x14001099f  pop     rdi
0x1400109a0  pop     rsi
0x1400109a1  pop     rbp
0x1400109a2  retn
0x1400109a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
