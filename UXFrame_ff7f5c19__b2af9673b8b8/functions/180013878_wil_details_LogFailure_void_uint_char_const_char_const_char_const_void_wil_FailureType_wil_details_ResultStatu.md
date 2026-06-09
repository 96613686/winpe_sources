# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180013878`
- end: `0x180013b4e`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `726`
- prototype: ``
- caller_count: `4`
- callee_count: `11`
- tags: ``

## callers

- `0x180009bec`
- `0x180009cac`
- `0x180009db8`
- `0x180009eb4`

## callees

- `0x180009ae4`
- `0x180012c30`
- `0x180013544`
- `0x180013778`
- `0x180013878`
- `0x1800146e8`
- `0x180014710`
- `0x180014724`
- `0x180014740`
- `0x180016fdc`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001399b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001399b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013aeb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180013aeb`

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
  __int64 ModuleName; // rax
  const struct wil::FailureInfo *v26; // r9
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
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
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v26);
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
0x180013878  mov     [rsp+arg_10], rbx
0x18001387d  mov     [rsp+arg_8], edx
0x180013881  mov     [rsp+arg_0], rcx
0x180013886  push    rbp
0x180013887  push    rsi
0x180013888  push    rdi
0x180013889  push    r12
0x18001388b  push    r13
0x18001388d  push    r14
0x18001388f  push    r15
0x180013891  sub     rsp, 40h
0x180013895  mov     r12, r9
0x180013898  mov     r13, r8
0x18001389b  mov     r10, rcx
0x18001389e  xor     eax, eax
0x1800138a0  mov     rsi, [rsp+78h+lpOutputString]
0x1800138a8  mov     [rsi], ax
0x1800138ab  mov     rax, [rsp+78h+arg_60]
0x1800138b3  mov     byte ptr [rax], 0
0x1800138b6  mov     r14, [rsp+78h+arg_38]
0x1800138be  mov     edi, [r14]
0x1800138c1  mov     rbx, [rsp+78h+arg_78]
0x1800138c9  mov     [rbx+8], edi
0x1800138cc  mov     eax, [r14+4]
0x1800138d0  mov     [rbx+0Ch], eax
0x1800138d3  xor     ebp, ebp
0x1800138d5  mov     r15d, [rsp+78h+arg_30]
0x1800138dd  mov     ecx, r15d
0x1800138e0  test    r15d, r15d
0x1800138e3  jz      short loc_18001394B
0x1800138e5  sub     ecx, 1
0x1800138e8  jz      short loc_180013942
0x1800138ea  sub     ecx, 1
0x1800138ed  jz      short loc_1800138FD
0x1800138ef  cmp     ecx, 1
0x1800138f2  jnz     short loc_180013954
0x1800138f4  mov     ecx, edi; this
0x1800138f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800138fb  jmp     short loc_180013952
0x1800138fd  test    edi, edi
0x1800138ff  js      short loc_180013939
0x180013901  mov     edi, 8007029Ch
0x180013906  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001390a  mov     rax, [rsp+78h+arg_28]
0x180013912  mov     [rsp+78h+var_50], rax; __int64
0x180013917  mov     rax, [rsp+78h+arg_20]
0x18001391f  mov     [rsp+78h+var_58], rax; __int64
0x180013924  mov     rcx, r10; int
0x180013927  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001392c  mov     [rbx+8], edi
0x18001392f  mov     ecx, edi; this
0x180013931  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013936  mov     [rbx+0Ch], eax
0x180013939  mov     ecx, edi; this
0x18001393b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180013940  jmp     short loc_180013952
0x180013942  mov     ecx, edi; this
0x180013944  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180013949  jmp     short loc_180013952
0x18001394b  mov     ecx, edi; this
0x18001394d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180013952  mov     ebp, eax
0x180013954  mov     [rbx], r15d
0x180013957  mov     eax, [rsp+78h+arg_70]
0x18001395e  mov     [rbx+4], eax
0x180013961  cmp     dword ptr [r14+8], 1
0x180013966  jnz     short loc_18001396E
0x180013968  or      eax, 8
0x18001396b  mov     [rbx+4], eax
0x18001396e  mov     eax, 1
0x180013973  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001397b  inc     eax
0x18001397d  mov     [rbx+10h], eax
0x180013980  mov     rax, [rsp+78h+arg_40]
0x180013988  xor     edi, edi
0x18001398a  test    rax, rax
0x18001398d  jz      short loc_180013994
0x18001398f  cmp     [rax], di
0x180013992  jnz     short loc_180013997
0x180013994  mov     rax, rdi
0x180013997  mov     [rbx+18h], rax
0x18001399b  call    cs:__imp_GetCurrentThreadId
0x1800139a1  mov     [rbx+20h], eax
0x1800139a4  mov     [rbx+38h], r13
0x1800139a8  mov     eax, [rsp+78h+arg_8]
0x1800139af  mov     [rbx+40h], eax
0x1800139b2  mov     [rbx+44h], ebp
0x1800139b5  mov     rax, [rsp+78h+arg_20]
0x1800139bd  mov     [rbx+28h], rax
0x1800139c1  mov     [rbx+30h], r12
0x1800139c5  mov     rax, [rsp+78h+arg_28]
0x1800139cd  mov     [rbx+88h], rax
0x1800139d4  mov     rax, [rsp+78h+arg_0]
0x1800139dc  mov     [rbx+90h], rax
0x1800139e3  mov     [rbx+48h], rdi
0x1800139e7  xorps   xmm0, xmm0
0x1800139ea  xor     eax, eax
0x1800139ec  movups  xmmword ptr [rbx+68h], xmm0
0x1800139f0  mov     [rbx+78h], rax
0x1800139f4  movups  xmmword ptr [rbx+50h], xmm0
0x1800139f8  mov     [rbx+60h], rax
0x1800139fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180013a03  test    rax, rax
0x180013a06  jz      short loc_180013A0F
0x180013a08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a0d  jmp     short loc_180013A12
0x180013a0f  mov     rax, rdi
0x180013a12  mov     [rbx+80h], rax
0x180013a19  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180013a20  test    rax, rax
0x180013a23  jz      short loc_180013A2D
0x180013a25  mov     rcx, rbx
0x180013a28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180013a34  test    rax, rax
0x180013a37  jz      short loc_180013A4F
0x180013a39  mov     r8d, 400h
0x180013a3f  mov     rdx, [rsp+78h+arg_60]
0x180013a47  mov     rcx, rbx
0x180013a4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a4f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013a56  test    rax, rax
0x180013a59  jz      short loc_180013A63
0x180013a5b  mov     rcx, rbx
0x180013a5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180013a6a  test    rax, rax
0x180013a6d  jz      short loc_180013A7D
0x180013a6f  test    byte ptr [rbx+4], 2
0x180013a73  jnz     short loc_180013A7D
0x180013a75  mov     rcx, rbx
0x180013a78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a7d  cmp     [rbx+8], edi
0x180013a80  jl      short loc_180013A9E
0x180013a82  cmp     r15d, 3
0x180013a86  jz      short loc_180013A8E
0x180013a88  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180013a8e  mov     ecx, 8000FFFFh; this
0x180013a93  mov     [rbx+8], ecx
0x180013a96  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180013a9b  mov     [rbx+0Ch], eax
0x180013a9e  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180013aa3  test    al, al
0x180013aa5  jz      short loc_180013AF3
0x180013aa7  test    byte ptr [rbx+4], 2
0x180013aab  jnz     short loc_180013AF3
0x180013aad  mov     ebp, 800h
0x180013ab2  mov     rax, cs:g_pfnResultLoggingCallback
0x180013ab9  test    rax, rax
0x180013abc  jz      short loc_180013AD5
0x180013abe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013ac5  jnz     short loc_180013AD5
0x180013ac7  mov     r8d, ebp
0x180013aca  mov     rdx, rsi
0x180013acd  mov     rcx, rbx
0x180013ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ad5  cmp     [rsi], di
0x180013ad8  jnz     short loc_180013AE8
0x180013ada  mov     r8, rbx; unsigned __int64
0x180013add  mov     rdx, rbp; wchar_t *
0x180013ae0  mov     rcx, rsi; this
0x180013ae3  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180013ae8  mov     rcx, rsi; lpOutputString
0x180013aeb  call    cs:__imp_OutputDebugStringW
0x180013af1  jmp     short loc_180013B15
0x180013af3  mov     rax, cs:g_pfnResultLoggingCallback
0x180013afa  test    rax, rax
0x180013afd  jz      short loc_180013B15
0x180013aff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180013b06  jnz     short loc_180013B15
0x180013b08  xor     r8d, r8d
0x180013b0b  xor     edx, edx
0x180013b0d  mov     rcx, rbx
0x180013b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b15  test    byte ptr [rbx+4], 4
0x180013b19  jnz     short loc_180013B24
0x180013b1b  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180013b22  jz      short loc_180013B36
0x180013b24  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180013b2b  test    rax, rax
0x180013b2e  jz      short loc_180013B36
0x180013b30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b35  nop
0x180013b36  mov     rbx, [rsp+78h+arg_10]
0x180013b3e  add     rsp, 40h
0x180013b42  pop     r15
0x180013b44  pop     r14
0x180013b46  pop     r13
0x180013b48  pop     r12
0x180013b4a  pop     rdi
0x180013b4b  pop     rsi
0x180013b4c  pop     rbp
0x180013b4d  retn
```
