# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180042c68`
- end: `0x180042f73`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `779`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180041824`
- `0x180043f48`

## callees

- `0x18001b7e8`
- `0x18004151c`
- `0x180042784`
- `0x180042c68`
- `0x180043088`
- `0x1800430b0`
- `0x1800430c4`
- `0x1800430e4`
- `0x180043840`
- `0x18009e020`

## import_xrefs

- `KERNEL32!OutputDebugStringW` at `0x180042f28`
- `KERNEL32!OutputDebugStringW` at `0x180042f28`
- `KERNEL32!GetCurrentThreadId` at `0x180042d8b`
- `KERNEL32!GetCurrentThreadId` at `0x180042d8b`
- `KERNEL32!IsDebuggerPresent` at `0x180042eb0`
- `KERNEL32!IsDebuggerPresent` at `0x180042eb0`

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
0x180042c68  mov     [rsp+arg_10], rbx
0x180042c6d  mov     [rsp+arg_8], edx
0x180042c71  mov     [rsp+arg_0], rcx
0x180042c76  push    rbp
0x180042c77  push    rsi
0x180042c78  push    rdi
0x180042c79  push    r12
0x180042c7b  push    r13
0x180042c7d  push    r14
0x180042c7f  push    r15
0x180042c81  sub     rsp, 40h
0x180042c85  mov     r14, [rsp+78h+arg_38]
0x180042c8d  xor     eax, eax
0x180042c8f  mov     rbx, [rsp+78h+arg_78]
0x180042c97  xor     ebp, ebp
0x180042c99  mov     r15d, [rsp+78h+arg_30]
0x180042ca1  mov     r10, rcx
0x180042ca4  mov     rsi, [rsp+78h+lpOutputString]
0x180042cac  mov     r12, r9
0x180042caf  mov     r13, r8
0x180042cb2  mov     ecx, r15d
0x180042cb5  mov     [rsi], ax
0x180042cb8  mov     rax, [rsp+78h+arg_60]
0x180042cc0  mov     byte ptr [rax], 0
0x180042cc3  mov     edi, [r14]
0x180042cc6  mov     [rbx+8], edi
0x180042cc9  mov     eax, [r14+4]
0x180042ccd  mov     [rbx+0Ch], eax
0x180042cd0  test    r15d, r15d
0x180042cd3  jz      short loc_180042D3B
0x180042cd5  sub     ecx, 1
0x180042cd8  jz      short loc_180042D32
0x180042cda  sub     ecx, 1
0x180042cdd  jz      short loc_180042CED
0x180042cdf  cmp     ecx, 1
0x180042ce2  jnz     short loc_180042D44
0x180042ce4  mov     ecx, edi; this
0x180042ce6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180042ceb  jmp     short loc_180042D42
0x180042ced  test    edi, edi
0x180042cef  js      short loc_180042D29
0x180042cf1  mov     rax, [rsp+78h+arg_28]
0x180042cf9  mov     edi, 8007029Ch
0x180042cfe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180042d02  mov     rcx, r10; int
0x180042d05  mov     [rsp+78h+var_50], rax; __int64
0x180042d0a  mov     rax, [rsp+78h+arg_20]
0x180042d12  mov     [rsp+78h+var_58], rax; __int64
0x180042d17  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180042d1c  mov     ecx, edi; this
0x180042d1e  mov     [rbx+8], edi
0x180042d21  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180042d26  mov     [rbx+0Ch], eax
0x180042d29  mov     ecx, edi; this
0x180042d2b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180042d30  jmp     short loc_180042D42
0x180042d32  mov     ecx, edi; this
0x180042d34  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180042d39  jmp     short loc_180042D42
0x180042d3b  mov     ecx, edi; this
0x180042d3d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180042d42  mov     ebp, eax
0x180042d44  mov     eax, [rsp+78h+arg_70]
0x180042d4b  mov     [rbx+4], eax
0x180042d4e  mov     [rbx], r15d
0x180042d51  cmp     dword ptr [r14+8], 1
0x180042d56  jnz     short loc_180042D5E
0x180042d58  or      eax, 8
0x180042d5b  mov     [rbx+4], eax
0x180042d5e  mov     eax, 1
0x180042d63  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180042d6b  inc     eax
0x180042d6d  xor     edi, edi
0x180042d6f  mov     [rbx+10h], eax
0x180042d72  mov     rax, [rsp+78h+arg_40]
0x180042d7a  test    rax, rax
0x180042d7d  jz      short loc_180042D84
0x180042d7f  cmp     [rax], di
0x180042d82  jnz     short loc_180042D87
0x180042d84  mov     rax, rdi
0x180042d87  mov     [rbx+18h], rax
0x180042d8b  call    cs:__imp_GetCurrentThreadId
0x180042d92  nop     dword ptr [rax+rax+00h]
0x180042d97  mov     [rbx+38h], r13
0x180042d9b  xorps   xmm0, xmm0
0x180042d9e  mov     [rbx+20h], eax
0x180042da1  mov     eax, [rsp+78h+arg_8]
0x180042da8  mov     [rbx+40h], eax
0x180042dab  mov     rax, [rsp+78h+arg_20]
0x180042db3  mov     [rbx+28h], rax
0x180042db7  mov     rax, [rsp+78h+arg_28]
0x180042dbf  mov     [rbx+88h], rax
0x180042dc6  mov     rax, [rsp+78h+arg_0]
0x180042dce  mov     [rbx+90h], rax
0x180042dd5  xor     eax, eax
0x180042dd7  mov     [rbx+44h], ebp
0x180042dda  mov     [rbx+30h], r12
0x180042dde  mov     [rbx+48h], rdi
0x180042de2  movups  xmmword ptr [rbx+68h], xmm0
0x180042de6  mov     [rbx+78h], rax
0x180042dea  movups  xmmword ptr [rbx+50h], xmm0
0x180042dee  mov     [rbx+60h], rax
0x180042df2  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180042df9  test    rax, rax
0x180042dfc  jz      short loc_180042E05
0x180042dfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e03  jmp     short loc_180042E08
0x180042e05  mov     rax, rdi
0x180042e08  mov     [rbx+80h], rax
0x180042e0f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180042e16  test    rax, rax
0x180042e19  jz      short loc_180042E23
0x180042e1b  mov     rcx, rbx
0x180042e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e23  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180042e2a  test    rax, rax
0x180042e2d  jz      short loc_180042E45
0x180042e2f  mov     rdx, [rsp+78h+arg_60]
0x180042e37  mov     r8d, 400h
0x180042e3d  mov     rcx, rbx
0x180042e40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e45  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180042e4c  test    rax, rax
0x180042e4f  jz      short loc_180042E59
0x180042e51  mov     rcx, rbx
0x180042e54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e59  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180042e60  test    rax, rax
0x180042e63  jz      short loc_180042E73
0x180042e65  test    byte ptr [rbx+4], 2
0x180042e69  jnz     short loc_180042E73
0x180042e6b  mov     rcx, rbx
0x180042e6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042e73  cmp     [rbx+8], edi
0x180042e76  jl      short loc_180042E92
0x180042e78  cmp     r15d, 3
0x180042e7c  jnz     loc_180042F6D
0x180042e82  mov     ecx, 8000FFFFh; this
0x180042e87  mov     [rbx+8], ecx
0x180042e8a  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180042e8f  mov     [rbx+0Ch], eax
0x180042e92  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180042e99  jnz     short loc_180042EC0
0x180042e9b  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180042ea2  test    rax, rax
0x180042ea5  jz      short loc_180042EB0
0x180042ea7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042eac  test    al, al
0x180042eae  jmp     short loc_180042EBE
0x180042eb0  call    cs:__imp_IsDebuggerPresent
0x180042eb7  nop     dword ptr [rax+rax+00h]
0x180042ebc  test    eax, eax
0x180042ebe  jz      short loc_180042EC6
0x180042ec0  test    byte ptr [rbx+4], 2
0x180042ec4  jz      short loc_180042EEA
0x180042ec6  mov     rax, cs:g_pfnResultLoggingCallback
0x180042ecd  test    rax, rax
0x180042ed0  jz      short loc_180042F34
0x180042ed2  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180042ed9  jnz     short loc_180042F34
0x180042edb  xor     r8d, r8d
0x180042ede  xor     edx, edx
0x180042ee0  mov     rcx, rbx
0x180042ee3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042ee8  jmp     short loc_180042F34
0x180042eea  mov     rax, cs:g_pfnResultLoggingCallback
0x180042ef1  mov     ebp, 800h
0x180042ef6  test    rax, rax
0x180042ef9  jz      short loc_180042F12
0x180042efb  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180042f02  jnz     short loc_180042F12
0x180042f04  mov     r8d, ebp
0x180042f07  mov     rdx, rsi
0x180042f0a  mov     rcx, rbx
0x180042f0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f12  cmp     [rsi], di
0x180042f15  jnz     short loc_180042F25
0x180042f17  mov     r8, rbx; unsigned __int64
0x180042f1a  mov     rdx, rbp; wchar_t *
0x180042f1d  mov     rcx, rsi; this
0x180042f20  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180042f25  mov     rcx, rsi; lpOutputString
0x180042f28  call    cs:__imp_OutputDebugStringW
0x180042f2f  nop     dword ptr [rax+rax+00h]
0x180042f34  test    byte ptr [rbx+4], 4
0x180042f38  jnz     short loc_180042F43
0x180042f3a  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180042f41  jz      short loc_180042F54
0x180042f43  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180042f4a  test    rax, rax
0x180042f4d  jz      short loc_180042F54
0x180042f4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180042f54  mov     rbx, [rsp+78h+arg_10]
0x180042f5c  add     rsp, 40h
0x180042f60  pop     r15
0x180042f62  pop     r14
0x180042f64  pop     r13
0x180042f66  pop     r12
0x180042f68  pop     rdi
0x180042f69  pop     rsi
0x180042f6a  pop     rbp
0x180042f6b  retn
0x180042f6d  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
