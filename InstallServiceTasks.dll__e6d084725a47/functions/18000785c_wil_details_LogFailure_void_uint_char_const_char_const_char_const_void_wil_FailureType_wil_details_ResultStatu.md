# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000785c`
- end: `0x180007b55`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180004ff0`
- `0x18000535c`
- `0x18000c2c0`

## callees

- `0x180004f28`
- `0x180006be4`
- `0x180007448`
- `0x18000785c`
- `0x180008724`
- `0x180008740`
- `0x180008890`
- `0x1800088ac`
- `0x18000a5a4`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000797f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000797f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007a9e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007a9e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b10`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007b10`

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
0x18000785c  mov     [rsp+arg_10], rbx
0x180007861  mov     [rsp+arg_8], edx
0x180007865  mov     [rsp+arg_0], rcx
0x18000786a  push    rbp
0x18000786b  push    rsi
0x18000786c  push    rdi
0x18000786d  push    r12
0x18000786f  push    r13
0x180007871  push    r14
0x180007873  push    r15
0x180007875  sub     rsp, 40h
0x180007879  mov     r12, r9
0x18000787c  mov     r13, r8
0x18000787f  mov     r10, rcx
0x180007882  xor     eax, eax
0x180007884  mov     rsi, [rsp+78h+lpOutputString]
0x18000788c  mov     [rsi], ax
0x18000788f  mov     rax, [rsp+78h+arg_60]
0x180007897  mov     byte ptr [rax], 0
0x18000789a  mov     r14, [rsp+78h+arg_38]
0x1800078a2  mov     edi, [r14]
0x1800078a5  mov     rbx, [rsp+78h+arg_78]
0x1800078ad  mov     [rbx+8], edi
0x1800078b0  mov     eax, [r14+4]
0x1800078b4  mov     [rbx+0Ch], eax
0x1800078b7  xor     ebp, ebp
0x1800078b9  mov     r15d, [rsp+78h+arg_30]
0x1800078c1  mov     ecx, r15d
0x1800078c4  test    r15d, r15d
0x1800078c7  jz      short loc_18000792F
0x1800078c9  sub     ecx, 1
0x1800078cc  jz      short loc_180007926
0x1800078ce  sub     ecx, 1
0x1800078d1  jz      short loc_1800078E1
0x1800078d3  cmp     ecx, 1
0x1800078d6  jnz     short loc_180007938
0x1800078d8  mov     ecx, edi; this
0x1800078da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800078df  jmp     short loc_180007936
0x1800078e1  test    edi, edi
0x1800078e3  js      short loc_18000791D
0x1800078e5  mov     edi, 8007029Ch
0x1800078ea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800078ee  mov     rax, [rsp+78h+arg_28]
0x1800078f6  mov     [rsp+78h+var_50], rax; __int64
0x1800078fb  mov     rax, [rsp+78h+arg_20]
0x180007903  mov     [rsp+78h+var_58], rax; __int64
0x180007908  mov     rcx, r10; int
0x18000790b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007910  mov     [rbx+8], edi
0x180007913  mov     ecx, edi; this
0x180007915  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000791a  mov     [rbx+0Ch], eax
0x18000791d  mov     ecx, edi; this
0x18000791f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007924  jmp     short loc_180007936
0x180007926  mov     ecx, edi; this
0x180007928  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000792d  jmp     short loc_180007936
0x18000792f  mov     ecx, edi; this
0x180007931  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007936  mov     ebp, eax
0x180007938  mov     [rbx], r15d
0x18000793b  mov     eax, [rsp+78h+arg_70]
0x180007942  mov     [rbx+4], eax
0x180007945  cmp     dword ptr [r14+8], 1
0x18000794a  jnz     short loc_180007952
0x18000794c  or      eax, 8
0x18000794f  mov     [rbx+4], eax
0x180007952  mov     eax, 1
0x180007957  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000795f  inc     eax
0x180007961  mov     [rbx+10h], eax
0x180007964  mov     rax, [rsp+78h+arg_40]
0x18000796c  xor     edi, edi
0x18000796e  test    rax, rax
0x180007971  jz      short loc_180007978
0x180007973  cmp     [rax], di
0x180007976  jnz     short loc_18000797B
0x180007978  mov     rax, rdi
0x18000797b  mov     [rbx+18h], rax
0x18000797f  call    cs:__imp_GetCurrentThreadId
0x180007985  mov     [rbx+20h], eax
0x180007988  mov     [rbx+38h], r13
0x18000798c  mov     eax, [rsp+78h+arg_8]
0x180007993  mov     [rbx+40h], eax
0x180007996  mov     [rbx+44h], ebp
0x180007999  mov     rax, [rsp+78h+arg_20]
0x1800079a1  mov     [rbx+28h], rax
0x1800079a5  mov     [rbx+30h], r12
0x1800079a9  mov     rax, [rsp+78h+arg_28]
0x1800079b1  mov     [rbx+88h], rax
0x1800079b8  mov     rax, [rsp+78h+arg_0]
0x1800079c0  mov     [rbx+90h], rax
0x1800079c7  mov     [rbx+48h], rdi
0x1800079cb  xorps   xmm0, xmm0
0x1800079ce  xor     eax, eax
0x1800079d0  movups  xmmword ptr [rbx+68h], xmm0
0x1800079d4  mov     [rbx+78h], rax
0x1800079d8  movups  xmmword ptr [rbx+50h], xmm0
0x1800079dc  mov     [rbx+60h], rax
0x1800079e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800079e7  test    rax, rax
0x1800079ea  jz      short loc_1800079F3
0x1800079ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800079f1  jmp     short loc_1800079F6
0x1800079f3  mov     rax, rdi
0x1800079f6  mov     [rbx+80h], rax
0x1800079fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007a04  test    rax, rax
0x180007a07  jz      short loc_180007A11
0x180007a09  mov     rcx, rbx
0x180007a0c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a11  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007a18  test    rax, rax
0x180007a1b  jz      short loc_180007A33
0x180007a1d  mov     r8d, 400h
0x180007a23  mov     rdx, [rsp+78h+arg_60]
0x180007a2b  mov     rcx, rbx
0x180007a2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a33  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007a3a  test    rax, rax
0x180007a3d  jz      short loc_180007A47
0x180007a3f  mov     rcx, rbx
0x180007a42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a47  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007a4e  test    rax, rax
0x180007a51  jz      short loc_180007A61
0x180007a53  test    byte ptr [rbx+4], 2
0x180007a57  jnz     short loc_180007A61
0x180007a59  mov     rcx, rbx
0x180007a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a61  cmp     [rbx+8], edi
0x180007a64  jl      short loc_180007A80
0x180007a66  cmp     r15d, 3
0x180007a6a  jnz     loc_180007B4F
0x180007a70  mov     ecx, 8000FFFFh; this
0x180007a75  mov     [rbx+8], ecx
0x180007a78  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007a7d  mov     [rbx+0Ch], eax
0x180007a80  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007a87  jnz     short loc_180007AA8
0x180007a89  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007a90  test    rax, rax
0x180007a93  jz      short loc_180007A9E
0x180007a95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007a9a  test    al, al
0x180007a9c  jmp     short loc_180007AA6
0x180007a9e  call    cs:__imp_IsDebuggerPresent
0x180007aa4  test    eax, eax
0x180007aa6  jz      short loc_180007AAE
0x180007aa8  test    byte ptr [rbx+4], 2
0x180007aac  jz      short loc_180007AD2
0x180007aae  mov     rax, cs:g_pfnResultLoggingCallback
0x180007ab5  test    rax, rax
0x180007ab8  jz      short loc_180007B16
0x180007aba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007ac1  jnz     short loc_180007B16
0x180007ac3  xor     r8d, r8d
0x180007ac6  xor     edx, edx
0x180007ac8  mov     rcx, rbx
0x180007acb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ad0  jmp     short loc_180007B16
0x180007ad2  mov     ebp, 800h
0x180007ad7  mov     rax, cs:g_pfnResultLoggingCallback
0x180007ade  test    rax, rax
0x180007ae1  jz      short loc_180007AFA
0x180007ae3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007aea  jnz     short loc_180007AFA
0x180007aec  mov     r8d, ebp
0x180007aef  mov     rdx, rsi
0x180007af2  mov     rcx, rbx
0x180007af5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007afa  cmp     [rsi], di
0x180007afd  jnz     short loc_180007B0D
0x180007aff  mov     r8, rbx; unsigned __int64
0x180007b02  mov     rdx, rbp; unsigned __int16 *
0x180007b05  mov     rcx, rsi; this
0x180007b08  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007b0d  mov     rcx, rsi; lpOutputString
0x180007b10  call    cs:__imp_OutputDebugStringW
0x180007b16  test    byte ptr [rbx+4], 4
0x180007b1a  jnz     short loc_180007B25
0x180007b1c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007b23  jz      short loc_180007B37
0x180007b25  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007b2c  test    rax, rax
0x180007b2f  jz      short loc_180007B37
0x180007b31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b36  nop
0x180007b37  mov     rbx, [rsp+78h+arg_10]
0x180007b3f  add     rsp, 40h
0x180007b43  pop     r15
0x180007b45  pop     r14
0x180007b47  pop     r13
0x180007b49  pop     r12
0x180007b4b  pop     rdi
0x180007b4c  pop     rsi
0x180007b4d  pop     rbp
0x180007b4e  retn
0x180007b4f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
