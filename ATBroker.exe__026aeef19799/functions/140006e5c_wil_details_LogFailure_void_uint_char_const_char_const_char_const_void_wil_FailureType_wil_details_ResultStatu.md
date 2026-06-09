# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006e5c`
- end: `0x140007154`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140003538`

## callees

- `0x140002f7c`
- `0x140005c44`
- `0x140006608`
- `0x140006e5c`
- `0x140007ed8`
- `0x140007f00`
- `0x140008028`
- `0x140008044`
- `0x14000a764`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140006f7f`
- `KERNEL32!GetCurrentThreadId` at `0x140006f7f`
- `KERNEL32!OutputDebugStringW` at `0x140007110`
- `KERNEL32!OutputDebugStringW` at `0x140007110`
- `KERNEL32!IsDebuggerPresent` at `0x14000709e`
- `KERNEL32!IsDebuggerPresent` at `0x14000709e`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x140006e5c  mov     [rsp+arg_10], rbx
0x140006e61  mov     [rsp+arg_8], edx
0x140006e65  mov     [rsp+arg_0], rcx
0x140006e6a  push    rbp
0x140006e6b  push    rsi
0x140006e6c  push    rdi
0x140006e6d  push    r12
0x140006e6f  push    r13
0x140006e71  push    r14
0x140006e73  push    r15
0x140006e75  sub     rsp, 40h
0x140006e79  mov     r14, [rsp+78h+arg_38]
0x140006e81  xor     eax, eax
0x140006e83  mov     rbx, [rsp+78h+arg_78]
0x140006e8b  xor     ebp, ebp
0x140006e8d  mov     r15d, [rsp+78h+arg_30]
0x140006e95  mov     r10, rcx
0x140006e98  mov     rsi, [rsp+78h+lpOutputString]
0x140006ea0  mov     r12, r9
0x140006ea3  mov     r13, r8
0x140006ea6  mov     ecx, r15d
0x140006ea9  mov     [rsi], ax
0x140006eac  mov     rax, [rsp+78h+arg_60]
0x140006eb4  mov     byte ptr [rax], 0
0x140006eb7  mov     edi, [r14]
0x140006eba  mov     [rbx+8], edi
0x140006ebd  mov     eax, [r14+4]
0x140006ec1  mov     [rbx+0Ch], eax
0x140006ec4  test    r15d, r15d
0x140006ec7  jz      short loc_140006F2F
0x140006ec9  sub     ecx, 1
0x140006ecc  jz      short loc_140006F26
0x140006ece  sub     ecx, 1
0x140006ed1  jz      short loc_140006EE1
0x140006ed3  cmp     ecx, 1
0x140006ed6  jnz     short loc_140006F38
0x140006ed8  mov     ecx, edi; this
0x140006eda  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006edf  jmp     short loc_140006F36
0x140006ee1  test    edi, edi
0x140006ee3  js      short loc_140006F1D
0x140006ee5  mov     rax, [rsp+78h+arg_28]
0x140006eed  mov     edi, 8007029Ch
0x140006ef2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006ef6  mov     rcx, r10; int
0x140006ef9  mov     [rsp+78h+var_50], rax; __int64
0x140006efe  mov     rax, [rsp+78h+arg_20]
0x140006f06  mov     [rsp+78h+var_58], rax; __int64
0x140006f0b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006f10  mov     ecx, edi; this
0x140006f12  mov     [rbx+8], edi
0x140006f15  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006f1a  mov     [rbx+0Ch], eax
0x140006f1d  mov     ecx, edi; this
0x140006f1f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006f24  jmp     short loc_140006F36
0x140006f26  mov     ecx, edi; this
0x140006f28  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006f2d  jmp     short loc_140006F36
0x140006f2f  mov     ecx, edi; this
0x140006f31  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140006f36  mov     ebp, eax
0x140006f38  mov     eax, [rsp+78h+arg_70]
0x140006f3f  mov     [rbx+4], eax
0x140006f42  mov     [rbx], r15d
0x140006f45  cmp     dword ptr [r14+8], 1
0x140006f4a  jnz     short loc_140006F52
0x140006f4c  or      eax, 8
0x140006f4f  mov     [rbx+4], eax
0x140006f52  mov     eax, 1
0x140006f57  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006f5f  inc     eax
0x140006f61  xor     edi, edi
0x140006f63  mov     [rbx+10h], eax
0x140006f66  mov     rax, [rsp+78h+arg_40]
0x140006f6e  test    rax, rax
0x140006f71  jz      short loc_140006F78
0x140006f73  cmp     [rax], di
0x140006f76  jnz     short loc_140006F7B
0x140006f78  mov     rax, rdi
0x140006f7b  mov     [rbx+18h], rax
0x140006f7f  call    cs:__imp_GetCurrentThreadId
0x140006f85  mov     [rbx+38h], r13
0x140006f89  xorps   xmm0, xmm0
0x140006f8c  mov     [rbx+20h], eax
0x140006f8f  mov     eax, [rsp+78h+arg_8]
0x140006f96  mov     [rbx+40h], eax
0x140006f99  mov     rax, [rsp+78h+arg_20]
0x140006fa1  mov     [rbx+28h], rax
0x140006fa5  mov     rax, [rsp+78h+arg_28]
0x140006fad  mov     [rbx+88h], rax
0x140006fb4  mov     rax, [rsp+78h+arg_0]
0x140006fbc  mov     [rbx+90h], rax
0x140006fc3  xor     eax, eax
0x140006fc5  mov     [rbx+44h], ebp
0x140006fc8  mov     [rbx+30h], r12
0x140006fcc  mov     [rbx+48h], rdi
0x140006fd0  movups  xmmword ptr [rbx+68h], xmm0
0x140006fd4  mov     [rbx+78h], rax
0x140006fd8  movups  xmmword ptr [rbx+50h], xmm0
0x140006fdc  mov     [rbx+60h], rax
0x140006fe0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006fe7  test    rax, rax
0x140006fea  jz      short loc_140006FF3
0x140006fec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ff1  jmp     short loc_140006FF6
0x140006ff3  mov     rax, rdi
0x140006ff6  mov     [rbx+80h], rax
0x140006ffd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007004  test    rax, rax
0x140007007  jz      short loc_140007011
0x140007009  mov     rcx, rbx
0x14000700c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007011  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007018  test    rax, rax
0x14000701b  jz      short loc_140007033
0x14000701d  mov     rdx, [rsp+78h+arg_60]
0x140007025  mov     r8d, 400h
0x14000702b  mov     rcx, rbx
0x14000702e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007033  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000703a  test    rax, rax
0x14000703d  jz      short loc_140007047
0x14000703f  mov     rcx, rbx
0x140007042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007047  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000704e  test    rax, rax
0x140007051  jz      short loc_140007061
0x140007053  test    byte ptr [rbx+4], 2
0x140007057  jnz     short loc_140007061
0x140007059  mov     rcx, rbx
0x14000705c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007061  cmp     [rbx+8], edi
0x140007064  jl      short loc_140007080
0x140007066  cmp     r15d, 3
0x14000706a  jnz     loc_14000714E
0x140007070  mov     ecx, 8000FFFFh; this
0x140007075  mov     [rbx+8], ecx
0x140007078  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000707d  mov     [rbx+0Ch], eax
0x140007080  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007087  jnz     short loc_1400070A8
0x140007089  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007090  test    rax, rax
0x140007093  jz      short loc_14000709E
0x140007095  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000709a  test    al, al
0x14000709c  jmp     short loc_1400070A6
0x14000709e  call    cs:__imp_IsDebuggerPresent
0x1400070a4  test    eax, eax
0x1400070a6  jz      short loc_1400070AE
0x1400070a8  test    byte ptr [rbx+4], 2
0x1400070ac  jz      short loc_1400070D2
0x1400070ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1400070b5  test    rax, rax
0x1400070b8  jz      short loc_140007116
0x1400070ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400070c1  jnz     short loc_140007116
0x1400070c3  xor     r8d, r8d
0x1400070c6  xor     edx, edx
0x1400070c8  mov     rcx, rbx
0x1400070cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070d0  jmp     short loc_140007116
0x1400070d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400070d9  mov     ebp, 800h
0x1400070de  test    rax, rax
0x1400070e1  jz      short loc_1400070FA
0x1400070e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400070ea  jnz     short loc_1400070FA
0x1400070ec  mov     r8d, ebp
0x1400070ef  mov     rdx, rsi
0x1400070f2  mov     rcx, rbx
0x1400070f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400070fa  cmp     [rsi], di
0x1400070fd  jnz     short loc_14000710D
0x1400070ff  mov     r8, rbx; unsigned __int64
0x140007102  mov     rdx, rbp; unsigned __int16 *
0x140007105  mov     rcx, rsi; this
0x140007108  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x14000710d  mov     rcx, rsi; lpOutputString
0x140007110  call    cs:__imp_OutputDebugStringW
0x140007116  test    byte ptr [rbx+4], 4
0x14000711a  jnz     short loc_140007125
0x14000711c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007123  jz      short loc_140007136
0x140007125  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14000712c  test    rax, rax
0x14000712f  jz      short loc_140007136
0x140007131  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007136  mov     rbx, [rsp+78h+arg_10]
0x14000713e  add     rsp, 40h
0x140007142  pop     r15
0x140007144  pop     r14
0x140007146  pop     r13
0x140007148  pop     r12
0x14000714a  pop     rdi
0x14000714b  pop     rsi
0x14000714c  pop     rbp
0x14000714d  retn
0x14000714e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
