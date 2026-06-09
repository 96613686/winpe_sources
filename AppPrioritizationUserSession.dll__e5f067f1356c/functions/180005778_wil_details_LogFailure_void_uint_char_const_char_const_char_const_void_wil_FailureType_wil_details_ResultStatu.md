# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005778`
- end: `0x180005a71`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003cb4`

## callees

- `0x1800036c0`
- `0x180004d84`
- `0x180005590`
- `0x180005778`
- `0x180005d30`
- `0x180005d50`
- `0x180005d64`
- `0x180005d80`
- `0x18000716c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000589b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000589b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059ba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800059ba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a2c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005a2c`

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
0x180005778  mov     [rsp+arg_10], rbx
0x18000577d  mov     [rsp+arg_8], edx
0x180005781  mov     [rsp+arg_0], rcx
0x180005786  push    rbp
0x180005787  push    rsi
0x180005788  push    rdi
0x180005789  push    r12
0x18000578b  push    r13
0x18000578d  push    r14
0x18000578f  push    r15
0x180005791  sub     rsp, 40h
0x180005795  mov     r12, r9
0x180005798  mov     r13, r8
0x18000579b  mov     r10, rcx
0x18000579e  xor     eax, eax
0x1800057a0  mov     rsi, [rsp+78h+lpOutputString]
0x1800057a8  mov     [rsi], ax
0x1800057ab  mov     rax, [rsp+78h+arg_60]
0x1800057b3  mov     byte ptr [rax], 0
0x1800057b6  mov     r14, [rsp+78h+arg_38]
0x1800057be  mov     edi, [r14]
0x1800057c1  mov     rbx, [rsp+78h+arg_78]
0x1800057c9  mov     [rbx+8], edi
0x1800057cc  mov     eax, [r14+4]
0x1800057d0  mov     [rbx+0Ch], eax
0x1800057d3  xor     ebp, ebp
0x1800057d5  mov     r15d, [rsp+78h+arg_30]
0x1800057dd  mov     ecx, r15d
0x1800057e0  test    r15d, r15d
0x1800057e3  jz      short loc_18000584B
0x1800057e5  sub     ecx, 1
0x1800057e8  jz      short loc_180005842
0x1800057ea  sub     ecx, 1
0x1800057ed  jz      short loc_1800057FD
0x1800057ef  cmp     ecx, 1
0x1800057f2  jnz     short loc_180005854
0x1800057f4  mov     ecx, edi; this
0x1800057f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800057fb  jmp     short loc_180005852
0x1800057fd  test    edi, edi
0x1800057ff  js      short loc_180005839
0x180005801  mov     edi, 8007029Ch
0x180005806  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000580a  mov     rax, [rsp+78h+arg_28]
0x180005812  mov     [rsp+78h+var_50], rax; __int64
0x180005817  mov     rax, [rsp+78h+arg_20]
0x18000581f  mov     [rsp+78h+var_58], rax; __int64
0x180005824  mov     rcx, r10; int
0x180005827  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000582c  mov     [rbx+8], edi
0x18000582f  mov     ecx, edi; this
0x180005831  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005836  mov     [rbx+0Ch], eax
0x180005839  mov     ecx, edi; this
0x18000583b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005840  jmp     short loc_180005852
0x180005842  mov     ecx, edi; this
0x180005844  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005849  jmp     short loc_180005852
0x18000584b  mov     ecx, edi; this
0x18000584d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005852  mov     ebp, eax
0x180005854  mov     [rbx], r15d
0x180005857  mov     eax, [rsp+78h+arg_70]
0x18000585e  mov     [rbx+4], eax
0x180005861  cmp     dword ptr [r14+8], 1
0x180005866  jnz     short loc_18000586E
0x180005868  or      eax, 8
0x18000586b  mov     [rbx+4], eax
0x18000586e  mov     eax, 1
0x180005873  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000587b  inc     eax
0x18000587d  mov     [rbx+10h], eax
0x180005880  mov     rax, [rsp+78h+arg_40]
0x180005888  xor     edi, edi
0x18000588a  test    rax, rax
0x18000588d  jz      short loc_180005894
0x18000588f  cmp     [rax], di
0x180005892  jnz     short loc_180005897
0x180005894  mov     rax, rdi
0x180005897  mov     [rbx+18h], rax
0x18000589b  call    cs:__imp_GetCurrentThreadId
0x1800058a1  mov     [rbx+20h], eax
0x1800058a4  mov     [rbx+38h], r13
0x1800058a8  mov     eax, [rsp+78h+arg_8]
0x1800058af  mov     [rbx+40h], eax
0x1800058b2  mov     [rbx+44h], ebp
0x1800058b5  mov     rax, [rsp+78h+arg_20]
0x1800058bd  mov     [rbx+28h], rax
0x1800058c1  mov     [rbx+30h], r12
0x1800058c5  mov     rax, [rsp+78h+arg_28]
0x1800058cd  mov     [rbx+88h], rax
0x1800058d4  mov     rax, [rsp+78h+arg_0]
0x1800058dc  mov     [rbx+90h], rax
0x1800058e3  mov     [rbx+48h], rdi
0x1800058e7  xorps   xmm0, xmm0
0x1800058ea  xor     eax, eax
0x1800058ec  movups  xmmword ptr [rbx+68h], xmm0
0x1800058f0  mov     [rbx+78h], rax
0x1800058f4  movups  xmmword ptr [rbx+50h], xmm0
0x1800058f8  mov     [rbx+60h], rax
0x1800058fc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005903  test    rax, rax
0x180005906  jz      short loc_18000590F
0x180005908  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000590d  jmp     short loc_180005912
0x18000590f  mov     rax, rdi
0x180005912  mov     [rbx+80h], rax
0x180005919  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005920  test    rax, rax
0x180005923  jz      short loc_18000592D
0x180005925  mov     rcx, rbx
0x180005928  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000592d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005934  test    rax, rax
0x180005937  jz      short loc_18000594F
0x180005939  mov     r8d, 400h
0x18000593f  mov     rdx, [rsp+78h+arg_60]
0x180005947  mov     rcx, rbx
0x18000594a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000594f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005956  test    rax, rax
0x180005959  jz      short loc_180005963
0x18000595b  mov     rcx, rbx
0x18000595e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005963  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000596a  test    rax, rax
0x18000596d  jz      short loc_18000597D
0x18000596f  test    byte ptr [rbx+4], 2
0x180005973  jnz     short loc_18000597D
0x180005975  mov     rcx, rbx
0x180005978  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000597d  cmp     [rbx+8], edi
0x180005980  jl      short loc_18000599C
0x180005982  cmp     r15d, 3
0x180005986  jnz     loc_180005A6B
0x18000598c  mov     ecx, 8000FFFFh; this
0x180005991  mov     [rbx+8], ecx
0x180005994  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005999  mov     [rbx+0Ch], eax
0x18000599c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800059a3  jnz     short loc_1800059C4
0x1800059a5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800059ac  test    rax, rax
0x1800059af  jz      short loc_1800059BA
0x1800059b1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059b6  test    al, al
0x1800059b8  jmp     short loc_1800059C2
0x1800059ba  call    cs:__imp_IsDebuggerPresent
0x1800059c0  test    eax, eax
0x1800059c2  jz      short loc_1800059CA
0x1800059c4  test    byte ptr [rbx+4], 2
0x1800059c8  jz      short loc_1800059EE
0x1800059ca  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059d1  test    rax, rax
0x1800059d4  jz      short loc_180005A32
0x1800059d6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800059dd  jnz     short loc_180005A32
0x1800059df  xor     r8d, r8d
0x1800059e2  xor     edx, edx
0x1800059e4  mov     rcx, rbx
0x1800059e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800059ec  jmp     short loc_180005A32
0x1800059ee  mov     ebp, 800h
0x1800059f3  mov     rax, cs:g_pfnResultLoggingCallback
0x1800059fa  test    rax, rax
0x1800059fd  jz      short loc_180005A16
0x1800059ff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005a06  jnz     short loc_180005A16
0x180005a08  mov     r8d, ebp
0x180005a0b  mov     rdx, rsi
0x180005a0e  mov     rcx, rbx
0x180005a11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a16  cmp     [rsi], di
0x180005a19  jnz     short loc_180005A29
0x180005a1b  mov     r8, rbx; unsigned __int64
0x180005a1e  mov     rdx, rbp; unsigned __int16 *
0x180005a21  mov     rcx, rsi; this
0x180005a24  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005a29  mov     rcx, rsi; lpOutputString
0x180005a2c  call    cs:__imp_OutputDebugStringW
0x180005a32  test    byte ptr [rbx+4], 4
0x180005a36  jnz     short loc_180005A41
0x180005a38  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005a3f  jz      short loc_180005A53
0x180005a41  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005a48  test    rax, rax
0x180005a4b  jz      short loc_180005A53
0x180005a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005a52  nop
0x180005a53  mov     rbx, [rsp+78h+arg_10]
0x180005a5b  add     rsp, 40h
0x180005a5f  pop     r15
0x180005a61  pop     r14
0x180005a63  pop     r13
0x180005a65  pop     r12
0x180005a67  pop     rdi
0x180005a68  pop     rsi
0x180005a69  pop     rbp
0x180005a6a  retn
0x180005a6b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
