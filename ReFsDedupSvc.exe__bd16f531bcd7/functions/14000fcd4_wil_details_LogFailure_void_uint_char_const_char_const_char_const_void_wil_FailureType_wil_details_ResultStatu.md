# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14000fcd4`
- end: `0x14000ffe0`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x14000d240`
- `0x14000d5c0`
- `0x140014ea4`

## callees

- `0x14000d174`
- `0x14000efd0`
- `0x14000f8ec`
- `0x14000fcd4`
- `0x140010c60`
- `0x140010c80`
- `0x140010de4`
- `0x140010e04`
- `0x140012d64`
- `0x1401b9010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fdf7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x14000fdf7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ff94`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x14000ff94`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000ff1c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x14000ff1c`

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
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
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
0x14000fcd4  mov     [rsp+arg_10], rbx
0x14000fcd9  mov     [rsp+arg_8], edx
0x14000fcdd  mov     [rsp+arg_0], rcx
0x14000fce2  push    rbp
0x14000fce3  push    rsi
0x14000fce4  push    rdi
0x14000fce5  push    r12
0x14000fce7  push    r13
0x14000fce9  push    r14
0x14000fceb  push    r15
0x14000fced  sub     rsp, 40h
0x14000fcf1  mov     r12, r9
0x14000fcf4  mov     r13, r8
0x14000fcf7  mov     r10, rcx
0x14000fcfa  xor     eax, eax
0x14000fcfc  mov     rsi, [rsp+78h+lpOutputString]
0x14000fd04  mov     [rsi], ax
0x14000fd07  mov     rax, [rsp+78h+arg_60]
0x14000fd0f  mov     byte ptr [rax], 0
0x14000fd12  mov     r14, [rsp+78h+arg_38]
0x14000fd1a  mov     edi, [r14]
0x14000fd1d  mov     rbx, [rsp+78h+arg_78]
0x14000fd25  mov     [rbx+8], edi
0x14000fd28  mov     eax, [r14+4]
0x14000fd2c  mov     [rbx+0Ch], eax
0x14000fd2f  xor     ebp, ebp
0x14000fd31  mov     r15d, [rsp+78h+arg_30]
0x14000fd39  mov     ecx, r15d
0x14000fd3c  test    r15d, r15d
0x14000fd3f  jz      short loc_14000FDA7
0x14000fd41  sub     ecx, 1
0x14000fd44  jz      short loc_14000FD9E
0x14000fd46  sub     ecx, 1
0x14000fd49  jz      short loc_14000FD59
0x14000fd4b  cmp     ecx, 1
0x14000fd4e  jnz     short loc_14000FDB0
0x14000fd50  mov     ecx, edi; this
0x14000fd52  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000fd57  jmp     short loc_14000FDAE
0x14000fd59  test    edi, edi
0x14000fd5b  js      short loc_14000FD95
0x14000fd5d  mov     edi, 8007029Ch
0x14000fd62  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000fd66  mov     rax, [rsp+78h+arg_28]
0x14000fd6e  mov     [rsp+78h+var_50], rax; __int64
0x14000fd73  mov     rax, [rsp+78h+arg_20]
0x14000fd7b  mov     [rsp+78h+var_58], rax; __int64
0x14000fd80  mov     rcx, r10; int
0x14000fd83  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14000fd88  mov     [rbx+8], edi
0x14000fd8b  mov     ecx, edi; this
0x14000fd8d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000fd92  mov     [rbx+0Ch], eax
0x14000fd95  mov     ecx, edi; this
0x14000fd97  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14000fd9c  jmp     short loc_14000FDAE
0x14000fd9e  mov     ecx, edi; this
0x14000fda0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000fda5  jmp     short loc_14000FDAE
0x14000fda7  mov     ecx, edi; this
0x14000fda9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000fdae  mov     ebp, eax
0x14000fdb0  mov     [rbx], r15d
0x14000fdb3  mov     eax, [rsp+78h+arg_70]
0x14000fdba  mov     [rbx+4], eax
0x14000fdbd  cmp     dword ptr [r14+8], 1
0x14000fdc2  jnz     short loc_14000FDCA
0x14000fdc4  or      eax, 8
0x14000fdc7  mov     [rbx+4], eax
0x14000fdca  mov     eax, 1
0x14000fdcf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14000fdd7  inc     eax
0x14000fdd9  mov     [rbx+10h], eax
0x14000fddc  mov     rax, [rsp+78h+arg_40]
0x14000fde4  xor     edi, edi
0x14000fde6  test    rax, rax
0x14000fde9  jz      short loc_14000FDF0
0x14000fdeb  cmp     [rax], di
0x14000fdee  jnz     short loc_14000FDF3
0x14000fdf0  mov     rax, rdi
0x14000fdf3  mov     [rbx+18h], rax
0x14000fdf7  call    cs:__imp_GetCurrentThreadId
0x14000fdfe  nop     dword ptr [rax+rax+00h]
0x14000fe03  mov     [rbx+20h], eax
0x14000fe06  mov     [rbx+38h], r13
0x14000fe0a  mov     eax, [rsp+78h+arg_8]
0x14000fe11  mov     [rbx+40h], eax
0x14000fe14  mov     [rbx+44h], ebp
0x14000fe17  mov     rax, [rsp+78h+arg_20]
0x14000fe1f  mov     [rbx+28h], rax
0x14000fe23  mov     [rbx+30h], r12
0x14000fe27  mov     rax, [rsp+78h+arg_28]
0x14000fe2f  mov     [rbx+88h], rax
0x14000fe36  mov     rax, [rsp+78h+arg_0]
0x14000fe3e  mov     [rbx+90h], rax
0x14000fe45  mov     [rbx+48h], rdi
0x14000fe49  xorps   xmm0, xmm0
0x14000fe4c  xor     eax, eax
0x14000fe4e  movups  xmmword ptr [rbx+68h], xmm0
0x14000fe52  mov     [rbx+78h], rax
0x14000fe56  movups  xmmword ptr [rbx+50h], xmm0
0x14000fe5a  mov     [rbx+60h], rax
0x14000fe5e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000fe65  test    rax, rax
0x14000fe68  jz      short loc_14000FE71
0x14000fe6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe6f  jmp     short loc_14000FE74
0x14000fe71  mov     rax, rdi
0x14000fe74  mov     [rbx+80h], rax
0x14000fe7b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14000fe82  test    rax, rax
0x14000fe85  jz      short loc_14000FE8F
0x14000fe87  mov     rcx, rbx
0x14000fe8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fe8f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000fe96  test    rax, rax
0x14000fe99  jz      short loc_14000FEB1
0x14000fe9b  mov     r8d, 400h
0x14000fea1  mov     rdx, [rsp+78h+arg_60]
0x14000fea9  mov     rcx, rbx
0x14000feac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000feb1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000feb8  test    rax, rax
0x14000febb  jz      short loc_14000FEC5
0x14000febd  mov     rcx, rbx
0x14000fec0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fec5  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000fecc  test    rax, rax
0x14000fecf  jz      short loc_14000FEDF
0x14000fed1  test    byte ptr [rbx+4], 2
0x14000fed5  jnz     short loc_14000FEDF
0x14000fed7  mov     rcx, rbx
0x14000feda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fedf  cmp     [rbx+8], edi
0x14000fee2  jl      short loc_14000FEFE
0x14000fee4  cmp     r15d, 3
0x14000fee8  jnz     loc_14000FFDA
0x14000feee  mov     ecx, 8000FFFFh; this
0x14000fef3  mov     [rbx+8], ecx
0x14000fef6  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000fefb  mov     [rbx+0Ch], eax
0x14000fefe  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14000ff05  jnz     short loc_14000FF2C
0x14000ff07  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14000ff0e  test    rax, rax
0x14000ff11  jz      short loc_14000FF1C
0x14000ff13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff18  test    al, al
0x14000ff1a  jmp     short loc_14000FF2A
0x14000ff1c  call    cs:__imp_IsDebuggerPresent
0x14000ff23  nop     dword ptr [rax+rax+00h]
0x14000ff28  test    eax, eax
0x14000ff2a  jz      short loc_14000FF32
0x14000ff2c  test    byte ptr [rbx+4], 2
0x14000ff30  jz      short loc_14000FF56
0x14000ff32  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ff39  test    rax, rax
0x14000ff3c  jz      short loc_14000FFA0
0x14000ff3e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000ff45  jnz     short loc_14000FFA0
0x14000ff47  xor     r8d, r8d
0x14000ff4a  xor     edx, edx
0x14000ff4c  mov     rcx, rbx
0x14000ff4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff54  jmp     short loc_14000FFA0
0x14000ff56  mov     ebp, 800h
0x14000ff5b  mov     rax, cs:g_pfnResultLoggingCallback
0x14000ff62  test    rax, rax
0x14000ff65  jz      short loc_14000FF7E
0x14000ff67  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000ff6e  jnz     short loc_14000FF7E
0x14000ff70  mov     r8d, ebp
0x14000ff73  mov     rdx, rsi
0x14000ff76  mov     rcx, rbx
0x14000ff79  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ff7e  cmp     [rsi], di
0x14000ff81  jnz     short loc_14000FF91
0x14000ff83  mov     r8, rbx; unsigned __int64
0x14000ff86  mov     rdx, rbp; unsigned __int16 *
0x14000ff89  mov     rcx, rsi; this
0x14000ff8c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000ff91  mov     rcx, rsi; lpOutputString
0x14000ff94  call    cs:__imp_OutputDebugStringW
0x14000ff9b  nop     dword ptr [rax+rax+00h]
0x14000ffa0  test    byte ptr [rbx+4], 4
0x14000ffa4  jnz     short loc_14000FFAF
0x14000ffa6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14000ffad  jz      short loc_14000FFC1
0x14000ffaf  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000ffb6  test    rax, rax
0x14000ffb9  jz      short loc_14000FFC1
0x14000ffbb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ffc0  nop
0x14000ffc1  mov     rbx, [rsp+78h+arg_10]
0x14000ffc9  add     rsp, 40h
0x14000ffcd  pop     r15
0x14000ffcf  pop     r14
0x14000ffd1  pop     r13
0x14000ffd3  pop     r12
0x14000ffd5  pop     rdi
0x14000ffd6  pop     rsi
0x14000ffd7  pop     rbp
0x14000ffd8  retn
0x14000ffda  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
