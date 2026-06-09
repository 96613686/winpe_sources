# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000d850`
- end: `0x18000db99`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `841`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d2f0`

## callees

- `0x18000d2b0`
- `0x18000d2d0`
- `0x18000d3e0`
- `0x18000d480`
- `0x18000d4a0`
- `0x18000d4b0`
- `0x18000d590`
- `0x18000d850`
- `0x18000dfd0`
- `0x180242120`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x18000db53`
- `KERNEL32!OutputDebugStringW` at `0x18000db53`
- `KERNEL32!GetCurrentThreadId` at `0x18000d978`
- `KERNEL32!GetCurrentThreadId` at `0x18000d978`
- `KERNEL32!IsDebuggerPresent` at `0x18000dab7`
- `KERNEL32!IsDebuggerPresent` at `0x18000dab7`

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
        char a10,
        WCHAR *lpOutputString,
        __int64 a12,
        _BYTE *a13,
        __int64 a14,
        int a15,
        unsigned __int64 a16)
{
  int IsDebuggerPresent; // esi
  unsigned int v18; // edi
  int v19; // ebp
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  int v23; // edx
  wil::details::in1diag3 *v24; // rcx
  const struct wil::FailureInfo *v25; // r9
  __int64 ModuleName; // rax
  bool v27; // di
  wil::details *v28; // [rsp+30h] [rbp-48h]

  IsDebuggerPresent = 0;
  *lpOutputString = 0;
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
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v28, 0);
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
  if ( wil::details::g_pfnOriginateCallback && !a10 && (*(_BYTE *)(a16 + 4) & 2) == 0 )
    wil::details::g_pfnOriginateCallback(a16);
  if ( *(int *)(a16 + 8) >= 0 )
  {
    if ( a7 != 3 )
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  v27 = (wil::g_fIsDebuggerPresent
      || (!wil::g_pfnIsDebuggerPresent
        ? (LOBYTE(IsDebuggerPresent) = ::IsDebuggerPresent())
        : (IsDebuggerPresent = (unsigned __int8)wil::g_pfnIsDebuggerPresent()),
          IsDebuggerPresent))
     && wil::g_fResultOutputDebugString
     && (*(_BYTE *)(a16 + 4) & 2) == 0;
  if ( a10 || v27 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    if ( v27 )
      OutputDebugStringW(lpOutputString);
  }
  else if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
  {
    g_pfnResultLoggingCallback(a16, 0, 0, v25);
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
0x18000d850  mov     [rsp+arg_18], rbx
0x18000d855  mov     [rsp+arg_10], r8
0x18000d85a  mov     [rsp+arg_8], edx
0x18000d85e  mov     [rsp+arg_0], rcx
0x18000d863  push    rbp
0x18000d864  push    rsi
0x18000d865  push    rdi
0x18000d866  push    r12
0x18000d868  push    r13
0x18000d86a  push    r14
0x18000d86c  push    r15
0x18000d86e  sub     rsp, 40h
0x18000d872  mov     r13, r9
0x18000d875  mov     r10, rcx
0x18000d878  xor     esi, esi
0x18000d87a  mov     r14, [rsp+78h+lpOutputString]
0x18000d882  mov     [r14], si
0x18000d886  mov     rax, [rsp+78h+arg_60]
0x18000d88e  mov     [rax], sil
0x18000d891  mov     r15, [rsp+78h+arg_38]
0x18000d899  mov     edi, [r15]
0x18000d89c  mov     rbx, [rsp+78h+arg_78]
0x18000d8a4  mov     [rbx+8], edi
0x18000d8a7  mov     eax, [r15+4]
0x18000d8ab  mov     [rbx+0Ch], eax
0x18000d8ae  mov     ebp, esi
0x18000d8b0  mov     r12d, [rsp+78h+arg_30]
0x18000d8b8  mov     ecx, r12d
0x18000d8bb  test    r12d, r12d
0x18000d8be  jz      short loc_18000D92A
0x18000d8c0  sub     ecx, 1
0x18000d8c3  jz      short loc_18000D921
0x18000d8c5  sub     ecx, 1
0x18000d8c8  jz      short loc_18000D8D8
0x18000d8ca  cmp     ecx, 1
0x18000d8cd  jnz     short loc_18000D933
0x18000d8cf  mov     ecx, edi; this
0x18000d8d1  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000d8d6  jmp     short loc_18000D931
0x18000d8d8  test    edi, edi
0x18000d8da  js      short loc_18000D918
0x18000d8dc  mov     [rsp+78h+var_40], esi; int
0x18000d8e0  mov     edi, 8007029Ch
0x18000d8e5  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000d8e9  mov     rax, [rsp+78h+arg_28]
0x18000d8f1  mov     [rsp+78h+var_50], rax; __int64
0x18000d8f6  mov     rax, [rsp+78h+arg_20]
0x18000d8fe  mov     [rsp+78h+var_58], rax; __int64
0x18000d903  mov     rcx, r10; int
0x18000d906  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000d90b  mov     [rbx+8], edi
0x18000d90e  mov     ecx, edi; this
0x18000d910  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000d915  mov     [rbx+0Ch], eax
0x18000d918  mov     ecx, edi; this
0x18000d91a  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000d91f  jmp     short loc_18000D931
0x18000d921  mov     ecx, edi; this
0x18000d923  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000d928  jmp     short loc_18000D931
0x18000d92a  mov     ecx, edi; this
0x18000d92c  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000d931  mov     ebp, eax
0x18000d933  mov     [rbx], r12d
0x18000d936  mov     eax, [rsp+78h+arg_70]
0x18000d93d  mov     [rbx+4], eax
0x18000d940  cmp     dword ptr [r15+8], 1
0x18000d945  jnz     short loc_18000D94D
0x18000d947  or      eax, 8
0x18000d94a  mov     [rbx+4], eax
0x18000d94d  mov     eax, 1
0x18000d952  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000d95a  inc     eax
0x18000d95c  mov     [rbx+10h], eax
0x18000d95f  mov     rax, [rsp+78h+arg_40]
0x18000d967  test    rax, rax
0x18000d96a  jz      short loc_18000D971
0x18000d96c  cmp     [rax], si
0x18000d96f  jnz     short loc_18000D974
0x18000d971  mov     rax, rsi
0x18000d974  mov     [rbx+18h], rax
0x18000d978  call    cs:__imp_GetCurrentThreadId
0x18000d97e  mov     [rbx+20h], eax
0x18000d981  mov     rax, [rsp+78h+arg_10]
0x18000d989  mov     [rbx+38h], rax
0x18000d98d  mov     eax, [rsp+78h+arg_8]
0x18000d994  mov     [rbx+40h], eax
0x18000d997  mov     [rbx+44h], ebp
0x18000d99a  mov     rax, [rsp+78h+arg_20]
0x18000d9a2  mov     [rbx+28h], rax
0x18000d9a6  mov     [rbx+30h], r13
0x18000d9aa  mov     rax, [rsp+78h+arg_28]
0x18000d9b2  mov     [rbx+88h], rax
0x18000d9b9  mov     rax, [rsp+78h+arg_0]
0x18000d9c1  mov     [rbx+90h], rax
0x18000d9c8  mov     [rbx+48h], rsi
0x18000d9cc  xorps   xmm0, xmm0
0x18000d9cf  xor     eax, eax
0x18000d9d1  movups  xmmword ptr [rbx+68h], xmm0
0x18000d9d5  mov     [rbx+78h], rax
0x18000d9d9  movups  xmmword ptr [rbx+50h], xmm0
0x18000d9dd  mov     [rbx+60h], rax
0x18000d9e1  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000d9e8  test    rax, rax
0x18000d9eb  jz      short loc_18000D9F5
0x18000d9ed  call    cs:__guard_dispatch_icall_fptr
0x18000d9f3  jmp     short loc_18000D9F8
0x18000d9f5  mov     rax, rsi
0x18000d9f8  mov     [rbx+80h], rax
0x18000d9ff  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000da06  test    rax, rax
0x18000da09  jz      short loc_18000DA14
0x18000da0b  mov     rcx, rbx
0x18000da0e  call    cs:__guard_dispatch_icall_fptr
0x18000da14  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000da1b  test    rax, rax
0x18000da1e  jz      short loc_18000DA37
0x18000da20  mov     r8d, 400h
0x18000da26  mov     rdx, [rsp+78h+arg_60]
0x18000da2e  mov     rcx, rbx
0x18000da31  call    cs:__guard_dispatch_icall_fptr
0x18000da37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000da3e  test    rax, rax
0x18000da41  jz      short loc_18000DA4C
0x18000da43  mov     rcx, rbx
0x18000da46  call    cs:__guard_dispatch_icall_fptr
0x18000da4c  movzx   ebp, [rsp+78h+arg_48]
0x18000da54  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000da5b  test    rax, rax
0x18000da5e  jz      short loc_18000DA74
0x18000da60  test    bpl, bpl
0x18000da63  jnz     short loc_18000DA74
0x18000da65  test    byte ptr [rbx+4], 2
0x18000da69  jnz     short loc_18000DA74
0x18000da6b  mov     rcx, rbx
0x18000da6e  call    cs:__guard_dispatch_icall_fptr
0x18000da74  cmp     [rbx+8], esi
0x18000da77  jl      short loc_18000DA97
0x18000da79  cmp     r12d, 3
0x18000da7d  jnz     loc_18000DB93
0x18000da83  mov     dword ptr [rbx+8], 8000FFFFh
0x18000da8a  mov     ecx, 8000FFFFh; this
0x18000da8f  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000da94  mov     [rbx+0Ch], eax
0x18000da97  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, sil; bool wil::g_fIsDebuggerPresent
0x18000da9e  jnz     short loc_18000DAC7
0x18000daa0  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000daa7  test    rax, rax
0x18000daaa  jz      short loc_18000DAB7
0x18000daac  call    cs:__guard_dispatch_icall_fptr
0x18000dab2  movzx   esi, al
0x18000dab5  jmp     short loc_18000DAC3
0x18000dab7  call    cs:__imp_IsDebuggerPresent
0x18000dabd  test    eax, eax
0x18000dabf  setnz   sil
0x18000dac3  test    esi, esi
0x18000dac5  jz      short loc_18000DADB
0x18000dac7  cmp     cs:?g_fResultOutputDebugString@wil@@3_NA, 0; bool wil::g_fResultOutputDebugString
0x18000dace  jz      short loc_18000DADB
0x18000dad0  test    byte ptr [rbx+4], 2
0x18000dad4  jnz     short loc_18000DADB
0x18000dad6  mov     dil, 1
0x18000dad9  jmp     short loc_18000DADE
0x18000dadb  xor     dil, dil
0x18000dade  test    bpl, bpl
0x18000dae1  jnz     short loc_18000DB0D
0x18000dae3  test    dil, dil
0x18000dae6  jnz     short loc_18000DB0D
0x18000dae8  mov     rax, cs:g_pfnResultLoggingCallback
0x18000daef  test    rax, rax
0x18000daf2  jz      short loc_18000DB59
0x18000daf4  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000dafb  jnz     short loc_18000DB59
0x18000dafd  xor     r8d, r8d
0x18000db00  xor     edx, edx
0x18000db02  mov     rcx, rbx
0x18000db05  call    cs:__guard_dispatch_icall_fptr
0x18000db0b  jmp     short loc_18000DB59
0x18000db0d  mov     rax, cs:g_pfnResultLoggingCallback
0x18000db14  test    rax, rax
0x18000db17  jz      short loc_18000DB34
0x18000db19  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18000db20  jnz     short loc_18000DB34
0x18000db22  mov     r8d, 800h
0x18000db28  mov     rdx, r14
0x18000db2b  mov     rcx, rbx
0x18000db2e  call    cs:__guard_dispatch_icall_fptr
0x18000db34  cmp     word ptr [r14], 0
0x18000db39  jnz     short loc_18000DB4B
0x18000db3b  mov     r8, rbx; unsigned __int64
0x18000db3e  mov     edx, 800h; wchar_t *
0x18000db43  mov     rcx, r14; Buffer
0x18000db46  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000db4b  test    dil, dil
0x18000db4e  jz      short loc_18000DB59
0x18000db50  mov     rcx, r14; lpOutputString
0x18000db53  call    cs:__imp_OutputDebugStringW
0x18000db59  test    byte ptr [rbx+4], 4
0x18000db5d  jnz     short loc_18000DB68
0x18000db5f  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18000db66  jz      short loc_18000DB7B
0x18000db68  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000db6f  test    rax, rax
0x18000db72  jz      short loc_18000DB7B
0x18000db74  call    cs:__guard_dispatch_icall_fptr
0x18000db7a  nop
0x18000db7b  mov     rbx, [rsp+78h+arg_18]
0x18000db83  add     rsp, 40h
0x18000db87  pop     r15
0x18000db89  pop     r14
0x18000db8b  pop     r13
0x18000db8d  pop     r12
0x18000db8f  pop     rdi
0x18000db90  pop     rsi
0x18000db91  pop     rbp
0x18000db92  retn
0x18000db93  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
