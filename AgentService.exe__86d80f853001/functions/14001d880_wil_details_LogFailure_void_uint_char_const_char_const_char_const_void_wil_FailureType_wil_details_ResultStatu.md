# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x14001d880`
- end: `0x14001db79`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x14001c0dc`

## callees

- `0x14001bb18`
- `0x14001cf14`
- `0x14001d6bc`
- `0x14001d880`
- `0x14001ddbc`
- `0x14001dde0`
- `0x14001ddf4`
- `0x14001de10`
- `0x14001ee5c`
- `0x14009b010`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x14001db34`
- `KERNEL32!OutputDebugStringW` at `0x14001db34`
- `KERNEL32!GetCurrentThreadId` at `0x14001d9a3`
- `KERNEL32!GetCurrentThreadId` at `0x14001d9a3`
- `KERNEL32!IsDebuggerPresent` at `0x14001dac2`
- `KERNEL32!IsDebuggerPresent` at `0x14001dac2`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
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
0x14001d880  mov     [rsp+arg_10], rbx
0x14001d885  mov     [rsp+arg_8], edx
0x14001d889  mov     [rsp+arg_0], rcx
0x14001d88e  push    rbp
0x14001d88f  push    rsi
0x14001d890  push    rdi
0x14001d891  push    r12
0x14001d893  push    r13
0x14001d895  push    r14
0x14001d897  push    r15
0x14001d899  sub     rsp, 40h
0x14001d89d  mov     r12, r9
0x14001d8a0  mov     r13, r8
0x14001d8a3  mov     r10, rcx
0x14001d8a6  xor     eax, eax
0x14001d8a8  mov     rsi, [rsp+78h+lpOutputString]
0x14001d8b0  mov     [rsi], ax
0x14001d8b3  mov     rax, [rsp+78h+arg_60]
0x14001d8bb  mov     byte ptr [rax], 0
0x14001d8be  mov     r14, [rsp+78h+arg_38]
0x14001d8c6  mov     edi, [r14]
0x14001d8c9  mov     rbx, [rsp+78h+arg_78]
0x14001d8d1  mov     [rbx+8], edi
0x14001d8d4  mov     eax, [r14+4]
0x14001d8d8  mov     [rbx+0Ch], eax
0x14001d8db  xor     ebp, ebp
0x14001d8dd  mov     r15d, [rsp+78h+arg_30]
0x14001d8e5  mov     ecx, r15d
0x14001d8e8  test    r15d, r15d
0x14001d8eb  jz      short loc_14001D953
0x14001d8ed  sub     ecx, 1
0x14001d8f0  jz      short loc_14001D94A
0x14001d8f2  sub     ecx, 1
0x14001d8f5  jz      short loc_14001D905
0x14001d8f7  cmp     ecx, 1
0x14001d8fa  jnz     short loc_14001D95C
0x14001d8fc  mov     ecx, edi; this
0x14001d8fe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14001d903  jmp     short loc_14001D95A
0x14001d905  test    edi, edi
0x14001d907  js      short loc_14001D941
0x14001d909  mov     edi, 8007029Ch
0x14001d90e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14001d912  mov     rax, [rsp+78h+arg_28]
0x14001d91a  mov     [rsp+78h+var_50], rax; __int64
0x14001d91f  mov     rax, [rsp+78h+arg_20]
0x14001d927  mov     [rsp+78h+var_58], rax; __int64
0x14001d92c  mov     rcx, r10; int
0x14001d92f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x14001d934  mov     [rbx+8], edi
0x14001d937  mov     ecx, edi; this
0x14001d939  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001d93e  mov     [rbx+0Ch], eax
0x14001d941  mov     ecx, edi; this
0x14001d943  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x14001d948  jmp     short loc_14001D95A
0x14001d94a  mov     ecx, edi; this
0x14001d94c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14001d951  jmp     short loc_14001D95A
0x14001d953  mov     ecx, edi; this
0x14001d955  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14001d95a  mov     ebp, eax
0x14001d95c  mov     [rbx], r15d
0x14001d95f  mov     eax, [rsp+78h+arg_70]
0x14001d966  mov     [rbx+4], eax
0x14001d969  cmp     dword ptr [r14+8], 1
0x14001d96e  jnz     short loc_14001D976
0x14001d970  or      eax, 8
0x14001d973  mov     [rbx+4], eax
0x14001d976  mov     eax, 1
0x14001d97b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x14001d983  inc     eax
0x14001d985  mov     [rbx+10h], eax
0x14001d988  mov     rax, [rsp+78h+arg_40]
0x14001d990  xor     edi, edi
0x14001d992  test    rax, rax
0x14001d995  jz      short loc_14001D99C
0x14001d997  cmp     [rax], di
0x14001d99a  jnz     short loc_14001D99F
0x14001d99c  mov     rax, rdi
0x14001d99f  mov     [rbx+18h], rax
0x14001d9a3  call    cs:__imp_GetCurrentThreadId
0x14001d9a9  mov     [rbx+20h], eax
0x14001d9ac  mov     [rbx+38h], r13
0x14001d9b0  mov     eax, [rsp+78h+arg_8]
0x14001d9b7  mov     [rbx+40h], eax
0x14001d9ba  mov     [rbx+44h], ebp
0x14001d9bd  mov     rax, [rsp+78h+arg_20]
0x14001d9c5  mov     [rbx+28h], rax
0x14001d9c9  mov     [rbx+30h], r12
0x14001d9cd  mov     rax, [rsp+78h+arg_28]
0x14001d9d5  mov     [rbx+88h], rax
0x14001d9dc  mov     rax, [rsp+78h+arg_0]
0x14001d9e4  mov     [rbx+90h], rax
0x14001d9eb  mov     [rbx+48h], rdi
0x14001d9ef  xorps   xmm0, xmm0
0x14001d9f2  xor     eax, eax
0x14001d9f4  movups  xmmword ptr [rbx+68h], xmm0
0x14001d9f8  mov     [rbx+78h], rax
0x14001d9fc  movups  xmmword ptr [rbx+50h], xmm0
0x14001da00  mov     [rbx+60h], rax
0x14001da04  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14001da0b  test    rax, rax
0x14001da0e  jz      short loc_14001DA17
0x14001da10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da15  jmp     short loc_14001DA1A
0x14001da17  mov     rax, rdi
0x14001da1a  mov     [rbx+80h], rax
0x14001da21  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x14001da28  test    rax, rax
0x14001da2b  jz      short loc_14001DA35
0x14001da2d  mov     rcx, rbx
0x14001da30  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da35  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14001da3c  test    rax, rax
0x14001da3f  jz      short loc_14001DA57
0x14001da41  mov     r8d, 400h
0x14001da47  mov     rdx, [rsp+78h+arg_60]
0x14001da4f  mov     rcx, rbx
0x14001da52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da57  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001da5e  test    rax, rax
0x14001da61  jz      short loc_14001DA6B
0x14001da63  mov     rcx, rbx
0x14001da66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da6b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14001da72  test    rax, rax
0x14001da75  jz      short loc_14001DA85
0x14001da77  test    byte ptr [rbx+4], 2
0x14001da7b  jnz     short loc_14001DA85
0x14001da7d  mov     rcx, rbx
0x14001da80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001da85  cmp     [rbx+8], edi
0x14001da88  jl      short loc_14001DAA4
0x14001da8a  cmp     r15d, 3
0x14001da8e  jnz     loc_14001DB73
0x14001da94  mov     ecx, 8000FFFFh; this
0x14001da99  mov     [rbx+8], ecx
0x14001da9c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14001daa1  mov     [rbx+0Ch], eax
0x14001daa4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x14001daab  jnz     short loc_14001DACC
0x14001daad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x14001dab4  test    rax, rax
0x14001dab7  jz      short loc_14001DAC2
0x14001dab9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001dabe  test    al, al
0x14001dac0  jmp     short loc_14001DACA
0x14001dac2  call    cs:__imp_IsDebuggerPresent
0x14001dac8  test    eax, eax
0x14001daca  jz      short loc_14001DAD2
0x14001dacc  test    byte ptr [rbx+4], 2
0x14001dad0  jz      short loc_14001DAF6
0x14001dad2  mov     rax, cs:g_pfnResultLoggingCallback
0x14001dad9  test    rax, rax
0x14001dadc  jz      short loc_14001DB3A
0x14001dade  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001dae5  jnz     short loc_14001DB3A
0x14001dae7  xor     r8d, r8d
0x14001daea  xor     edx, edx
0x14001daec  mov     rcx, rbx
0x14001daef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001daf4  jmp     short loc_14001DB3A
0x14001daf6  mov     ebp, 800h
0x14001dafb  mov     rax, cs:g_pfnResultLoggingCallback
0x14001db02  test    rax, rax
0x14001db05  jz      short loc_14001DB1E
0x14001db07  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14001db0e  jnz     short loc_14001DB1E
0x14001db10  mov     r8d, ebp
0x14001db13  mov     rdx, rsi
0x14001db16  mov     rcx, rbx
0x14001db19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001db1e  cmp     [rsi], di
0x14001db21  jnz     short loc_14001DB31
0x14001db23  mov     r8, rbx; unsigned __int64
0x14001db26  mov     rdx, rbp; wchar_t *
0x14001db29  mov     rcx, rsi; this
0x14001db2c  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x14001db31  mov     rcx, rsi; lpOutputString
0x14001db34  call    cs:__imp_OutputDebugStringW
0x14001db3a  test    byte ptr [rbx+4], 4
0x14001db3e  jnz     short loc_14001DB49
0x14001db40  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x14001db47  jz      short loc_14001DB5B
0x14001db49  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x14001db50  test    rax, rax
0x14001db53  jz      short loc_14001DB5B
0x14001db55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001db5a  nop
0x14001db5b  mov     rbx, [rsp+78h+arg_10]
0x14001db63  add     rsp, 40h
0x14001db67  pop     r15
0x14001db69  pop     r14
0x14001db6b  pop     r13
0x14001db6d  pop     r12
0x14001db6f  pop     rdi
0x14001db70  pop     rsi
0x14001db71  pop     rbp
0x14001db72  retn
0x14001db73  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
