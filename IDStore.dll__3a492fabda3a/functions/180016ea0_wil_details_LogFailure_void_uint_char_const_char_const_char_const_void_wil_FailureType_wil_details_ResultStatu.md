# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180016ea0`
- end: `0x180017195`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800155d0`
- `0x180015684`
- `0x180015790`

## callees

- `0x180011074`
- `0x1800114d8`
- `0x180011a40`
- `0x1800154dc`
- `0x180016ea0`
- `0x1800172d4`
- `0x1800172f0`
- `0x18001730c`
- `0x1800175f4`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fc3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180016fc3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017156`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180017156`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800170e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800170e4`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180016ea0  mov     [rsp+arg_10], rbx
0x180016ea5  mov     [rsp+arg_8], edx
0x180016ea9  mov     [rsp+arg_0], rcx
0x180016eae  push    rbp
0x180016eaf  push    rsi
0x180016eb0  push    rdi
0x180016eb1  push    r12
0x180016eb3  push    r13
0x180016eb5  push    r14
0x180016eb7  push    r15
0x180016eb9  sub     rsp, 40h
0x180016ebd  mov     r12, r9
0x180016ec0  mov     r13, r8
0x180016ec3  mov     r10, rcx
0x180016ec6  xor     eax, eax
0x180016ec8  mov     rsi, [rsp+78h+lpOutputString]
0x180016ed0  mov     [rsi], ax
0x180016ed3  mov     rax, [rsp+78h+arg_60]
0x180016edb  mov     byte ptr [rax], 0
0x180016ede  mov     r14, [rsp+78h+arg_38]
0x180016ee6  mov     edi, [r14]
0x180016ee9  mov     rbx, [rsp+78h+arg_78]
0x180016ef1  mov     [rbx+8], edi
0x180016ef4  mov     eax, [r14+4]
0x180016ef8  mov     [rbx+0Ch], eax
0x180016efb  xor     ebp, ebp
0x180016efd  mov     r15d, [rsp+78h+arg_30]
0x180016f05  mov     ecx, r15d
0x180016f08  test    r15d, r15d
0x180016f0b  jz      short loc_180016F73
0x180016f0d  sub     ecx, 1
0x180016f10  jz      short loc_180016F6A
0x180016f12  sub     ecx, 1
0x180016f15  jz      short loc_180016F25
0x180016f17  cmp     ecx, 1
0x180016f1a  jnz     short loc_180016F7C
0x180016f1c  mov     ecx, edi; this
0x180016f1e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016f23  jmp     short loc_180016F7A
0x180016f25  test    edi, edi
0x180016f27  js      short loc_180016F61
0x180016f29  mov     edi, 8007029Ch
0x180016f2e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180016f32  mov     rax, [rsp+78h+arg_28]
0x180016f3a  mov     [rsp+78h+var_50], rax; __int64
0x180016f3f  mov     rax, [rsp+78h+arg_20]
0x180016f47  mov     [rsp+78h+var_58], rax; __int64
0x180016f4c  mov     rcx, r10; int
0x180016f4f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016f54  mov     [rbx+8], edi
0x180016f57  mov     ecx, edi; this
0x180016f59  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016f5e  mov     [rbx+0Ch], eax
0x180016f61  mov     ecx, edi; this
0x180016f63  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180016f68  jmp     short loc_180016F7A
0x180016f6a  mov     ecx, edi; this
0x180016f6c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180016f71  jmp     short loc_180016F7A
0x180016f73  mov     ecx, edi; this
0x180016f75  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180016f7a  mov     ebp, eax
0x180016f7c  mov     [rbx], r15d
0x180016f7f  mov     eax, [rsp+78h+arg_70]
0x180016f86  mov     [rbx+4], eax
0x180016f89  cmp     dword ptr [r14+8], 1
0x180016f8e  jnz     short loc_180016F96
0x180016f90  or      eax, 8
0x180016f93  mov     [rbx+4], eax
0x180016f96  mov     eax, 1
0x180016f9b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180016fa3  inc     eax
0x180016fa5  mov     [rbx+10h], eax
0x180016fa8  mov     rax, [rsp+78h+arg_40]
0x180016fb0  xor     edi, edi
0x180016fb2  test    rax, rax
0x180016fb5  jz      short loc_180016FBC
0x180016fb7  cmp     [rax], di
0x180016fba  jnz     short loc_180016FBF
0x180016fbc  mov     rax, rdi
0x180016fbf  mov     [rbx+18h], rax
0x180016fc3  call    cs:__imp_GetCurrentThreadId
0x180016fc9  mov     [rbx+20h], eax
0x180016fcc  mov     [rbx+38h], r13
0x180016fd0  mov     eax, [rsp+78h+arg_8]
0x180016fd7  mov     [rbx+40h], eax
0x180016fda  mov     [rbx+44h], ebp
0x180016fdd  mov     rax, [rsp+78h+arg_20]
0x180016fe5  mov     [rbx+28h], rax
0x180016fe9  mov     [rbx+30h], r12
0x180016fed  mov     rax, [rsp+78h+arg_28]
0x180016ff5  mov     [rbx+88h], rax
0x180016ffc  mov     rax, [rsp+78h+arg_0]
0x180017004  mov     [rbx+90h], rax
0x18001700b  mov     [rbx+48h], rdi
0x18001700f  xorps   xmm0, xmm0
0x180017012  xor     eax, eax
0x180017014  movups  xmmword ptr [rbx+68h], xmm0
0x180017018  mov     [rbx+78h], rax
0x18001701c  movups  xmmword ptr [rbx+50h], xmm0
0x180017020  mov     [rbx+60h], rax
0x180017024  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001702b  test    rax, rax
0x18001702e  jz      short loc_180017037
0x180017030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017035  jmp     short loc_18001703A
0x180017037  mov     rax, rdi
0x18001703a  mov     [rbx+80h], rax
0x180017041  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180017048  test    rax, rax
0x18001704b  jz      short loc_180017055
0x18001704d  mov     rcx, rbx
0x180017050  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017055  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001705c  test    rax, rax
0x18001705f  jz      short loc_180017077
0x180017061  mov     r8d, 400h
0x180017067  mov     rdx, [rsp+78h+arg_60]
0x18001706f  mov     rcx, rbx
0x180017072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017077  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001707e  test    rax, rax
0x180017081  jz      short loc_18001708B
0x180017083  mov     rcx, rbx
0x180017086  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001708b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180017092  test    rax, rax
0x180017095  jz      short loc_1800170A5
0x180017097  test    byte ptr [rbx+4], 2
0x18001709b  jnz     short loc_1800170A5
0x18001709d  mov     rcx, rbx
0x1800170a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170a5  cmp     [rbx+8], edi
0x1800170a8  jl      short loc_1800170C6
0x1800170aa  cmp     r15d, 3
0x1800170ae  jz      short loc_1800170B6
0x1800170b0  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x1800170b6  mov     ecx, 8000FFFFh; this
0x1800170bb  mov     [rbx+8], ecx
0x1800170be  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800170c3  mov     [rbx+0Ch], eax
0x1800170c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800170cd  jnz     short loc_1800170EE
0x1800170cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800170d6  test    rax, rax
0x1800170d9  jz      short loc_1800170E4
0x1800170db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800170e0  test    al, al
0x1800170e2  jmp     short loc_1800170EC
0x1800170e4  call    cs:__imp_IsDebuggerPresent
0x1800170ea  test    eax, eax
0x1800170ec  jz      short loc_1800170F4
0x1800170ee  test    byte ptr [rbx+4], 2
0x1800170f2  jz      short loc_180017118
0x1800170f4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800170fb  test    rax, rax
0x1800170fe  jz      short loc_18001715C
0x180017100  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180017107  jnz     short loc_18001715C
0x180017109  xor     r8d, r8d
0x18001710c  xor     edx, edx
0x18001710e  mov     rcx, rbx
0x180017111  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017116  jmp     short loc_18001715C
0x180017118  mov     ebp, 800h
0x18001711d  mov     rax, cs:g_pfnResultLoggingCallback
0x180017124  test    rax, rax
0x180017127  jz      short loc_180017140
0x180017129  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180017130  jnz     short loc_180017140
0x180017132  mov     r8d, ebp
0x180017135  mov     rdx, rsi
0x180017138  mov     rcx, rbx
0x18001713b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180017140  cmp     [rsi], di
0x180017143  jnz     short loc_180017153
0x180017145  mov     r8, rbx; unsigned __int64
0x180017148  mov     rdx, rbp; unsigned __int16 *
0x18001714b  mov     rcx, rsi; this
0x18001714e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180017153  mov     rcx, rsi; lpOutputString
0x180017156  call    cs:__imp_OutputDebugStringW
0x18001715c  test    byte ptr [rbx+4], 4
0x180017160  jnz     short loc_18001716B
0x180017162  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180017169  jz      short loc_18001717D
0x18001716b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180017172  test    rax, rax
0x180017175  jz      short loc_18001717D
0x180017177  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001717c  nop
0x18001717d  mov     rbx, [rsp+78h+arg_10]
0x180017185  add     rsp, 40h
0x180017189  pop     r15
0x18001718b  pop     r14
0x18001718d  pop     r13
0x18001718f  pop     r12
0x180017191  pop     rdi
0x180017192  pop     rsi
0x180017193  pop     rbp
0x180017194  retn
```
