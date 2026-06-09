# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003da3c`
- end: `0x18003dd30`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18003d94c`
- `0x1800461e8`
- `0x18004629c`

## callees

- `0x18003b150`
- `0x18003da3c`
- `0x18003dd40`
- `0x18004613c`
- `0x180046884`
- `0x180047194`
- `0x1800471b0`
- `0x1800471cc`
- `0x18004770c`
- `0x180077010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003db5f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003db5f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003dcf2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003dcf2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003dc80`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003dc80`

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
0x18003da3c  mov     [rsp+arg_10], rbx
0x18003da41  mov     [rsp+arg_8], edx
0x18003da45  mov     [rsp+arg_0], rcx
0x18003da4a  push    rbp
0x18003da4b  push    rsi
0x18003da4c  push    rdi
0x18003da4d  push    r12
0x18003da4f  push    r13
0x18003da51  push    r14
0x18003da53  push    r15
0x18003da55  sub     rsp, 40h
0x18003da59  mov     r14, [rsp+78h+arg_38]
0x18003da61  xor     eax, eax
0x18003da63  mov     rbx, [rsp+78h+arg_78]
0x18003da6b  xor     ebp, ebp
0x18003da6d  mov     r15d, [rsp+78h+arg_30]
0x18003da75  mov     r10, rcx
0x18003da78  mov     rsi, [rsp+78h+lpOutputString]
0x18003da80  mov     r12, r9
0x18003da83  mov     r13, r8
0x18003da86  mov     ecx, r15d
0x18003da89  mov     [rsi], ax
0x18003da8c  mov     rax, [rsp+78h+arg_60]
0x18003da94  mov     byte ptr [rax], 0
0x18003da97  mov     edi, [r14]
0x18003da9a  mov     [rbx+8], edi
0x18003da9d  mov     eax, [r14+4]
0x18003daa1  mov     [rbx+0Ch], eax
0x18003daa4  test    r15d, r15d
0x18003daa7  jz      short loc_18003DB0F
0x18003daa9  sub     ecx, 1
0x18003daac  jz      short loc_18003DB06
0x18003daae  sub     ecx, 1
0x18003dab1  jz      short loc_18003DAC1
0x18003dab3  cmp     ecx, 1
0x18003dab6  jnz     short loc_18003DB18
0x18003dab8  mov     ecx, edi; this
0x18003daba  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003dabf  jmp     short loc_18003DB16
0x18003dac1  test    edi, edi
0x18003dac3  js      short loc_18003DAFD
0x18003dac5  mov     rax, [rsp+78h+arg_28]
0x18003dacd  mov     edi, 8007029Ch
0x18003dad2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003dad6  mov     rcx, r10; int
0x18003dad9  mov     [rsp+78h+var_50], rax; __int64
0x18003dade  mov     rax, [rsp+78h+arg_20]
0x18003dae6  mov     [rsp+78h+var_58], rax; __int64
0x18003daeb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003daf0  mov     ecx, edi; this
0x18003daf2  mov     [rbx+8], edi
0x18003daf5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003dafa  mov     [rbx+0Ch], eax
0x18003dafd  mov     ecx, edi; this
0x18003daff  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003db04  jmp     short loc_18003DB16
0x18003db06  mov     ecx, edi; this
0x18003db08  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003db0d  jmp     short loc_18003DB16
0x18003db0f  mov     ecx, edi; this
0x18003db11  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003db16  mov     ebp, eax
0x18003db18  mov     eax, [rsp+78h+arg_70]
0x18003db1f  mov     [rbx+4], eax
0x18003db22  mov     [rbx], r15d
0x18003db25  cmp     dword ptr [r14+8], 1
0x18003db2a  jnz     short loc_18003DB32
0x18003db2c  or      eax, 8
0x18003db2f  mov     [rbx+4], eax
0x18003db32  mov     eax, 1
0x18003db37  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003db3f  inc     eax
0x18003db41  xor     edi, edi
0x18003db43  mov     [rbx+10h], eax
0x18003db46  mov     rax, [rsp+78h+arg_40]
0x18003db4e  test    rax, rax
0x18003db51  jz      short loc_18003DB58
0x18003db53  cmp     [rax], di
0x18003db56  jnz     short loc_18003DB5B
0x18003db58  mov     rax, rdi
0x18003db5b  mov     [rbx+18h], rax
0x18003db5f  call    cs:__imp_GetCurrentThreadId
0x18003db65  mov     [rbx+38h], r13
0x18003db69  xorps   xmm0, xmm0
0x18003db6c  mov     [rbx+20h], eax
0x18003db6f  mov     eax, [rsp+78h+arg_8]
0x18003db76  mov     [rbx+40h], eax
0x18003db79  mov     rax, [rsp+78h+arg_20]
0x18003db81  mov     [rbx+28h], rax
0x18003db85  mov     rax, [rsp+78h+arg_28]
0x18003db8d  mov     [rbx+88h], rax
0x18003db94  mov     rax, [rsp+78h+arg_0]
0x18003db9c  mov     [rbx+90h], rax
0x18003dba3  xor     eax, eax
0x18003dba5  mov     [rbx+44h], ebp
0x18003dba8  mov     [rbx+30h], r12
0x18003dbac  mov     [rbx+48h], rdi
0x18003dbb0  movups  xmmword ptr [rbx+68h], xmm0
0x18003dbb4  mov     [rbx+78h], rax
0x18003dbb8  movups  xmmword ptr [rbx+50h], xmm0
0x18003dbbc  mov     [rbx+60h], rax
0x18003dbc0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003dbc7  test    rax, rax
0x18003dbca  jz      short loc_18003DBD3
0x18003dbcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbd1  jmp     short loc_18003DBD6
0x18003dbd3  mov     rax, rdi
0x18003dbd6  mov     [rbx+80h], rax
0x18003dbdd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003dbe4  test    rax, rax
0x18003dbe7  jz      short loc_18003DBF1
0x18003dbe9  mov     rcx, rbx
0x18003dbec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dbf1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003dbf8  test    rax, rax
0x18003dbfb  jz      short loc_18003DC13
0x18003dbfd  mov     rdx, [rsp+78h+arg_60]
0x18003dc05  mov     r8d, 400h
0x18003dc0b  mov     rcx, rbx
0x18003dc0e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc13  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003dc1a  test    rax, rax
0x18003dc1d  jz      short loc_18003DC27
0x18003dc1f  mov     rcx, rbx
0x18003dc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc27  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003dc2e  test    rax, rax
0x18003dc31  jz      short loc_18003DC41
0x18003dc33  test    byte ptr [rbx+4], 2
0x18003dc37  jnz     short loc_18003DC41
0x18003dc39  mov     rcx, rbx
0x18003dc3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc41  cmp     [rbx+8], edi
0x18003dc44  jl      short loc_18003DC62
0x18003dc46  cmp     r15d, 3
0x18003dc4a  jz      short loc_18003DC52
0x18003dc4c  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18003dc52  mov     ecx, 8000FFFFh; this
0x18003dc57  mov     [rbx+8], ecx
0x18003dc5a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003dc5f  mov     [rbx+0Ch], eax
0x18003dc62  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18003dc69  jnz     short loc_18003DC8A
0x18003dc6b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003dc72  test    rax, rax
0x18003dc75  jz      short loc_18003DC80
0x18003dc77  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dc7c  test    al, al
0x18003dc7e  jmp     short loc_18003DC88
0x18003dc80  call    cs:__imp_IsDebuggerPresent
0x18003dc86  test    eax, eax
0x18003dc88  jz      short loc_18003DC90
0x18003dc8a  test    byte ptr [rbx+4], 2
0x18003dc8e  jz      short loc_18003DCB4
0x18003dc90  mov     rax, cs:g_pfnResultLoggingCallback
0x18003dc97  test    rax, rax
0x18003dc9a  jz      short loc_18003DCF8
0x18003dc9c  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003dca3  jnz     short loc_18003DCF8
0x18003dca5  xor     r8d, r8d
0x18003dca8  xor     edx, edx
0x18003dcaa  mov     rcx, rbx
0x18003dcad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcb2  jmp     short loc_18003DCF8
0x18003dcb4  mov     rax, cs:g_pfnResultLoggingCallback
0x18003dcbb  mov     ebp, 800h
0x18003dcc0  test    rax, rax
0x18003dcc3  jz      short loc_18003DCDC
0x18003dcc5  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18003dccc  jnz     short loc_18003DCDC
0x18003dcce  mov     r8d, ebp
0x18003dcd1  mov     rdx, rsi
0x18003dcd4  mov     rcx, rbx
0x18003dcd7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dcdc  cmp     [rsi], di
0x18003dcdf  jnz     short loc_18003DCEF
0x18003dce1  mov     r8, rbx; unsigned __int64
0x18003dce4  mov     rdx, rbp; unsigned __int16 *
0x18003dce7  mov     rcx, rsi; this
0x18003dcea  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003dcef  mov     rcx, rsi; lpOutputString
0x18003dcf2  call    cs:__imp_OutputDebugStringW
0x18003dcf8  test    byte ptr [rbx+4], 4
0x18003dcfc  jnz     short loc_18003DD07
0x18003dcfe  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18003dd05  jz      short loc_18003DD18
0x18003dd07  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003dd0e  test    rax, rax
0x18003dd11  jz      short loc_18003DD18
0x18003dd13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003dd18  mov     rbx, [rsp+78h+arg_10]
0x18003dd20  add     rsp, 40h
0x18003dd24  pop     r15
0x18003dd26  pop     r14
0x18003dd28  pop     r13
0x18003dd2a  pop     r12
0x18003dd2c  pop     rdi
0x18003dd2d  pop     rsi
0x18003dd2e  pop     rbp
0x18003dd2f  retn
```
