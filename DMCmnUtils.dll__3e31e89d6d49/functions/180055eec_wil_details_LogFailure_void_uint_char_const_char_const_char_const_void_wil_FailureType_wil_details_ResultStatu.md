# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180055eec`
- end: `0x1800561f8`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180053400`
- `0x180053780`
- `0x18005b1b4`

## callees

- `0x180053338`
- `0x180055274`
- `0x180055b04`
- `0x180055eec`
- `0x180056f68`
- `0x180056f90`
- `0x1800570f4`
- `0x180057114`
- `0x180059220`
- `0x1800c0010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005600f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005600f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800561ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800561ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180056134`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180056134`

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
0x180055eec  mov     [rsp+arg_10], rbx
0x180055ef1  mov     [rsp+arg_8], edx
0x180055ef5  mov     [rsp+arg_0], rcx
0x180055efa  push    rbp
0x180055efb  push    rsi
0x180055efc  push    rdi
0x180055efd  push    r12
0x180055eff  push    r13
0x180055f01  push    r14
0x180055f03  push    r15
0x180055f05  sub     rsp, 40h
0x180055f09  mov     r12, r9
0x180055f0c  mov     r13, r8
0x180055f0f  mov     r10, rcx
0x180055f12  xor     eax, eax
0x180055f14  mov     rsi, [rsp+78h+lpOutputString]
0x180055f1c  mov     [rsi], ax
0x180055f1f  mov     rax, [rsp+78h+arg_60]
0x180055f27  mov     byte ptr [rax], 0
0x180055f2a  mov     r14, [rsp+78h+arg_38]
0x180055f32  mov     edi, [r14]
0x180055f35  mov     rbx, [rsp+78h+arg_78]
0x180055f3d  mov     [rbx+8], edi
0x180055f40  mov     eax, [r14+4]
0x180055f44  mov     [rbx+0Ch], eax
0x180055f47  xor     ebp, ebp
0x180055f49  mov     r15d, [rsp+78h+arg_30]
0x180055f51  mov     ecx, r15d
0x180055f54  test    r15d, r15d
0x180055f57  jz      short loc_180055FBF
0x180055f59  sub     ecx, 1
0x180055f5c  jz      short loc_180055FB6
0x180055f5e  sub     ecx, 1
0x180055f61  jz      short loc_180055F71
0x180055f63  cmp     ecx, 1
0x180055f66  jnz     short loc_180055FC8
0x180055f68  mov     ecx, edi; this
0x180055f6a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180055f6f  jmp     short loc_180055FC6
0x180055f71  test    edi, edi
0x180055f73  js      short loc_180055FAD
0x180055f75  mov     edi, 8007029Ch
0x180055f7a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180055f7e  mov     rax, [rsp+78h+arg_28]
0x180055f86  mov     [rsp+78h+var_50], rax; __int64
0x180055f8b  mov     rax, [rsp+78h+arg_20]
0x180055f93  mov     [rsp+78h+var_58], rax; __int64
0x180055f98  mov     rcx, r10; int
0x180055f9b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180055fa0  mov     [rbx+8], edi
0x180055fa3  mov     ecx, edi; this
0x180055fa5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180055faa  mov     [rbx+0Ch], eax
0x180055fad  mov     ecx, edi; this
0x180055faf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180055fb4  jmp     short loc_180055FC6
0x180055fb6  mov     ecx, edi; this
0x180055fb8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180055fbd  jmp     short loc_180055FC6
0x180055fbf  mov     ecx, edi; this
0x180055fc1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180055fc6  mov     ebp, eax
0x180055fc8  mov     [rbx], r15d
0x180055fcb  mov     eax, [rsp+78h+arg_70]
0x180055fd2  mov     [rbx+4], eax
0x180055fd5  cmp     dword ptr [r14+8], 1
0x180055fda  jnz     short loc_180055FE2
0x180055fdc  or      eax, 8
0x180055fdf  mov     [rbx+4], eax
0x180055fe2  mov     eax, 1
0x180055fe7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180055fef  inc     eax
0x180055ff1  mov     [rbx+10h], eax
0x180055ff4  mov     rax, [rsp+78h+arg_40]
0x180055ffc  xor     edi, edi
0x180055ffe  test    rax, rax
0x180056001  jz      short loc_180056008
0x180056003  cmp     [rax], di
0x180056006  jnz     short loc_18005600B
0x180056008  mov     rax, rdi
0x18005600b  mov     [rbx+18h], rax
0x18005600f  call    cs:__imp_GetCurrentThreadId
0x180056016  nop     dword ptr [rax+rax+00h]
0x18005601b  mov     [rbx+20h], eax
0x18005601e  mov     [rbx+38h], r13
0x180056022  mov     eax, [rsp+78h+arg_8]
0x180056029  mov     [rbx+40h], eax
0x18005602c  mov     [rbx+44h], ebp
0x18005602f  mov     rax, [rsp+78h+arg_20]
0x180056037  mov     [rbx+28h], rax
0x18005603b  mov     [rbx+30h], r12
0x18005603f  mov     rax, [rsp+78h+arg_28]
0x180056047  mov     [rbx+88h], rax
0x18005604e  mov     rax, [rsp+78h+arg_0]
0x180056056  mov     [rbx+90h], rax
0x18005605d  mov     [rbx+48h], rdi
0x180056061  xorps   xmm0, xmm0
0x180056064  xor     eax, eax
0x180056066  movups  xmmword ptr [rbx+68h], xmm0
0x18005606a  mov     [rbx+78h], rax
0x18005606e  movups  xmmword ptr [rbx+50h], xmm0
0x180056072  mov     [rbx+60h], rax
0x180056076  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005607d  test    rax, rax
0x180056080  jz      short loc_180056089
0x180056082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056087  jmp     short loc_18005608C
0x180056089  mov     rax, rdi
0x18005608c  mov     [rbx+80h], rax
0x180056093  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005609a  test    rax, rax
0x18005609d  jz      short loc_1800560A7
0x18005609f  mov     rcx, rbx
0x1800560a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560a7  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800560ae  test    rax, rax
0x1800560b1  jz      short loc_1800560C9
0x1800560b3  mov     r8d, 400h
0x1800560b9  mov     rdx, [rsp+78h+arg_60]
0x1800560c1  mov     rcx, rbx
0x1800560c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560c9  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800560d0  test    rax, rax
0x1800560d3  jz      short loc_1800560DD
0x1800560d5  mov     rcx, rbx
0x1800560d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560dd  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800560e4  test    rax, rax
0x1800560e7  jz      short loc_1800560F7
0x1800560e9  test    byte ptr [rbx+4], 2
0x1800560ed  jnz     short loc_1800560F7
0x1800560ef  mov     rcx, rbx
0x1800560f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800560f7  cmp     [rbx+8], edi
0x1800560fa  jl      short loc_180056116
0x1800560fc  cmp     r15d, 3
0x180056100  jnz     loc_1800561F2
0x180056106  mov     ecx, 8000FFFFh; this
0x18005610b  mov     [rbx+8], ecx
0x18005610e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180056113  mov     [rbx+0Ch], eax
0x180056116  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005611d  jnz     short loc_180056144
0x18005611f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180056126  test    rax, rax
0x180056129  jz      short loc_180056134
0x18005612b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056130  test    al, al
0x180056132  jmp     short loc_180056142
0x180056134  call    cs:__imp_IsDebuggerPresent
0x18005613b  nop     dword ptr [rax+rax+00h]
0x180056140  test    eax, eax
0x180056142  jz      short loc_18005614A
0x180056144  test    byte ptr [rbx+4], 2
0x180056148  jz      short loc_18005616E
0x18005614a  mov     rax, cs:g_pfnResultLoggingCallback
0x180056151  test    rax, rax
0x180056154  jz      short loc_1800561B8
0x180056156  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005615d  jnz     short loc_1800561B8
0x18005615f  xor     r8d, r8d
0x180056162  xor     edx, edx
0x180056164  mov     rcx, rbx
0x180056167  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005616c  jmp     short loc_1800561B8
0x18005616e  mov     ebp, 800h
0x180056173  mov     rax, cs:g_pfnResultLoggingCallback
0x18005617a  test    rax, rax
0x18005617d  jz      short loc_180056196
0x18005617f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180056186  jnz     short loc_180056196
0x180056188  mov     r8d, ebp
0x18005618b  mov     rdx, rsi
0x18005618e  mov     rcx, rbx
0x180056191  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180056196  cmp     [rsi], di
0x180056199  jnz     short loc_1800561A9
0x18005619b  mov     r8, rbx; unsigned __int64
0x18005619e  mov     rdx, rbp; unsigned __int16 *
0x1800561a1  mov     rcx, rsi; this
0x1800561a4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800561a9  mov     rcx, rsi; lpOutputString
0x1800561ac  call    cs:__imp_OutputDebugStringW
0x1800561b3  nop     dword ptr [rax+rax+00h]
0x1800561b8  test    byte ptr [rbx+4], 4
0x1800561bc  jnz     short loc_1800561C7
0x1800561be  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800561c5  jz      short loc_1800561D9
0x1800561c7  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800561ce  test    rax, rax
0x1800561d1  jz      short loc_1800561D9
0x1800561d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800561d8  nop
0x1800561d9  mov     rbx, [rsp+78h+arg_10]
0x1800561e1  add     rsp, 40h
0x1800561e5  pop     r15
0x1800561e7  pop     r14
0x1800561e9  pop     r13
0x1800561eb  pop     r12
0x1800561ed  pop     rdi
0x1800561ee  pop     rsi
0x1800561ef  pop     rbp
0x1800561f0  retn
0x1800561f2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
