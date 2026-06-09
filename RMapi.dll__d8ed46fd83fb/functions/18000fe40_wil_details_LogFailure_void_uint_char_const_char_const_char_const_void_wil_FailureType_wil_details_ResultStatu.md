# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000fe40`
- end: `0x180010139`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000816c`
- `0x18000f2a0`
- `0x18000f5e4`

## callees

- `0x180007a58`
- `0x1800092a0`
- `0x18000e694`
- `0x18000ec70`
- `0x18000f1e0`
- `0x18000fe40`
- `0x18001037c`
- `0x180010398`
- `0x180010728`
- `0x180028010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ff63`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010082`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180010082`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800100f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800100f4`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x18000fe40  mov     [rsp+arg_10], rbx
0x18000fe45  mov     [rsp+arg_8], edx
0x18000fe49  mov     [rsp+arg_0], rcx
0x18000fe4e  push    rbp
0x18000fe4f  push    rsi
0x18000fe50  push    rdi
0x18000fe51  push    r12
0x18000fe53  push    r13
0x18000fe55  push    r14
0x18000fe57  push    r15
0x18000fe59  sub     rsp, 40h
0x18000fe5d  mov     r12, r9
0x18000fe60  mov     r13, r8
0x18000fe63  mov     r10, rcx
0x18000fe66  xor     eax, eax
0x18000fe68  mov     rsi, [rsp+78h+lpOutputString]
0x18000fe70  mov     [rsi], ax
0x18000fe73  mov     rax, [rsp+78h+arg_60]
0x18000fe7b  mov     byte ptr [rax], 0
0x18000fe7e  mov     r14, [rsp+78h+arg_38]
0x18000fe86  mov     edi, [r14]
0x18000fe89  mov     rbx, [rsp+78h+arg_78]
0x18000fe91  mov     [rbx+8], edi
0x18000fe94  mov     eax, [r14+4]
0x18000fe98  mov     [rbx+0Ch], eax
0x18000fe9b  xor     ebp, ebp
0x18000fe9d  mov     r15d, [rsp+78h+arg_30]
0x18000fea5  mov     ecx, r15d
0x18000fea8  test    r15d, r15d
0x18000feab  jz      short loc_18000FF13
0x18000fead  sub     ecx, 1
0x18000feb0  jz      short loc_18000FF0A
0x18000feb2  sub     ecx, 1
0x18000feb5  jz      short loc_18000FEC5
0x18000feb7  cmp     ecx, 1
0x18000feba  jnz     short loc_18000FF1C
0x18000febc  mov     ecx, edi; this
0x18000febe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000fec3  jmp     short loc_18000FF1A
0x18000fec5  test    edi, edi
0x18000fec7  js      short loc_18000FF01
0x18000fec9  mov     edi, 8007029Ch
0x18000fece  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000fed2  mov     rax, [rsp+78h+arg_28]
0x18000feda  mov     [rsp+78h+var_50], rax; __int64
0x18000fedf  mov     rax, [rsp+78h+arg_20]
0x18000fee7  mov     [rsp+78h+var_58], rax; __int64
0x18000feec  mov     rcx, r10; int
0x18000feef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000fef4  mov     [rbx+8], edi
0x18000fef7  mov     ecx, edi; this
0x18000fef9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000fefe  mov     [rbx+0Ch], eax
0x18000ff01  mov     ecx, edi; this
0x18000ff03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000ff08  jmp     short loc_18000FF1A
0x18000ff0a  mov     ecx, edi; this
0x18000ff0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000ff11  jmp     short loc_18000FF1A
0x18000ff13  mov     ecx, edi; this
0x18000ff15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000ff1a  mov     ebp, eax
0x18000ff1c  mov     [rbx], r15d
0x18000ff1f  mov     eax, [rsp+78h+arg_70]
0x18000ff26  mov     [rbx+4], eax
0x18000ff29  cmp     dword ptr [r14+8], 1
0x18000ff2e  jnz     short loc_18000FF36
0x18000ff30  or      eax, 8
0x18000ff33  mov     [rbx+4], eax
0x18000ff36  mov     eax, 1
0x18000ff3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000ff43  inc     eax
0x18000ff45  mov     [rbx+10h], eax
0x18000ff48  mov     rax, [rsp+78h+arg_40]
0x18000ff50  xor     edi, edi
0x18000ff52  test    rax, rax
0x18000ff55  jz      short loc_18000FF5C
0x18000ff57  cmp     [rax], di
0x18000ff5a  jnz     short loc_18000FF5F
0x18000ff5c  mov     rax, rdi
0x18000ff5f  mov     [rbx+18h], rax
0x18000ff63  call    cs:__imp_GetCurrentThreadId
0x18000ff69  mov     [rbx+20h], eax
0x18000ff6c  mov     [rbx+38h], r13
0x18000ff70  mov     eax, [rsp+78h+arg_8]
0x18000ff77  mov     [rbx+40h], eax
0x18000ff7a  mov     [rbx+44h], ebp
0x18000ff7d  mov     rax, [rsp+78h+arg_20]
0x18000ff85  mov     [rbx+28h], rax
0x18000ff89  mov     [rbx+30h], r12
0x18000ff8d  mov     rax, [rsp+78h+arg_28]
0x18000ff95  mov     [rbx+88h], rax
0x18000ff9c  mov     rax, [rsp+78h+arg_0]
0x18000ffa4  mov     [rbx+90h], rax
0x18000ffab  mov     [rbx+48h], rdi
0x18000ffaf  xorps   xmm0, xmm0
0x18000ffb2  xor     eax, eax
0x18000ffb4  movups  xmmword ptr [rbx+68h], xmm0
0x18000ffb8  mov     [rbx+78h], rax
0x18000ffbc  movups  xmmword ptr [rbx+50h], xmm0
0x18000ffc0  mov     [rbx+60h], rax
0x18000ffc4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ffcb  test    rax, rax
0x18000ffce  jz      short loc_18000FFD7
0x18000ffd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffd5  jmp     short loc_18000FFDA
0x18000ffd7  mov     rax, rdi
0x18000ffda  mov     [rbx+80h], rax
0x18000ffe1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000ffe8  test    rax, rax
0x18000ffeb  jz      short loc_18000FFF5
0x18000ffed  mov     rcx, rbx
0x18000fff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fff5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000fffc  test    rax, rax
0x18000ffff  jz      short loc_180010017
0x180010001  mov     r8d, 400h
0x180010007  mov     rdx, [rsp+78h+arg_60]
0x18001000f  mov     rcx, rbx
0x180010012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010017  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001001e  test    rax, rax
0x180010021  jz      short loc_18001002B
0x180010023  mov     rcx, rbx
0x180010026  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001002b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180010032  test    rax, rax
0x180010035  jz      short loc_180010045
0x180010037  test    byte ptr [rbx+4], 2
0x18001003b  jnz     short loc_180010045
0x18001003d  mov     rcx, rbx
0x180010040  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010045  cmp     [rbx+8], edi
0x180010048  jl      short loc_180010064
0x18001004a  cmp     r15d, 3
0x18001004e  jnz     loc_180010133
0x180010054  mov     ecx, 8000FFFFh; this
0x180010059  mov     [rbx+8], ecx
0x18001005c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180010061  mov     [rbx+0Ch], eax
0x180010064  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001006b  jnz     short loc_18001008C
0x18001006d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180010074  test    rax, rax
0x180010077  jz      short loc_180010082
0x180010079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001007e  test    al, al
0x180010080  jmp     short loc_18001008A
0x180010082  call    cs:__imp_IsDebuggerPresent
0x180010088  test    eax, eax
0x18001008a  jz      short loc_180010092
0x18001008c  test    byte ptr [rbx+4], 2
0x180010090  jz      short loc_1800100B6
0x180010092  mov     rax, cs:g_pfnResultLoggingCallback
0x180010099  test    rax, rax
0x18001009c  jz      short loc_1800100FA
0x18001009e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800100a5  jnz     short loc_1800100FA
0x1800100a7  xor     r8d, r8d
0x1800100aa  xor     edx, edx
0x1800100ac  mov     rcx, rbx
0x1800100af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100b4  jmp     short loc_1800100FA
0x1800100b6  mov     ebp, 800h
0x1800100bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800100c2  test    rax, rax
0x1800100c5  jz      short loc_1800100DE
0x1800100c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800100ce  jnz     short loc_1800100DE
0x1800100d0  mov     r8d, ebp
0x1800100d3  mov     rdx, rsi
0x1800100d6  mov     rcx, rbx
0x1800100d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800100de  cmp     [rsi], di
0x1800100e1  jnz     short loc_1800100F1
0x1800100e3  mov     r8, rbx; unsigned __int64
0x1800100e6  mov     rdx, rbp; wchar_t *
0x1800100e9  mov     rcx, rsi; this
0x1800100ec  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800100f1  mov     rcx, rsi; lpOutputString
0x1800100f4  call    cs:__imp_OutputDebugStringW
0x1800100fa  test    byte ptr [rbx+4], 4
0x1800100fe  jnz     short loc_180010109
0x180010100  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180010107  jz      short loc_18001011B
0x180010109  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010110  test    rax, rax
0x180010113  jz      short loc_18001011B
0x180010115  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001011a  nop
0x18001011b  mov     rbx, [rsp+78h+arg_10]
0x180010123  add     rsp, 40h
0x180010127  pop     r15
0x180010129  pop     r14
0x18001012b  pop     r13
0x18001012d  pop     r12
0x18001012f  pop     rdi
0x180010130  pop     rsi
0x180010131  pop     rbp
0x180010132  retn
0x180010133  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
