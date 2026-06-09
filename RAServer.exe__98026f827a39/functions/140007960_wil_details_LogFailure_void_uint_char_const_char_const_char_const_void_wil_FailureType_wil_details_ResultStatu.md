# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140007960`
- end: `0x140007c59`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140002a0c`
- `0x140002d58`

## callees

- `0x14000294c`
- `0x1400063d4`
- `0x140007118`
- `0x140007960`
- `0x140008bd0`
- `0x140008bf0`
- `0x140008d40`
- `0x140008d5c`
- `0x14000ba28`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x140007a83`
- `KERNEL32!GetCurrentThreadId` at `0x140007a83`
- `KERNEL32!OutputDebugStringW` at `0x140007c14`
- `KERNEL32!OutputDebugStringW` at `0x140007c14`
- `KERNEL32!IsDebuggerPresent` at `0x140007ba2`
- `KERNEL32!IsDebuggerPresent` at `0x140007ba2`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x140007960  mov     [rsp+arg_10], rbx
0x140007965  mov     [rsp+arg_8], edx
0x140007969  mov     [rsp+arg_0], rcx
0x14000796e  push    rbp
0x14000796f  push    rsi
0x140007970  push    rdi
0x140007971  push    r12
0x140007973  push    r13
0x140007975  push    r14
0x140007977  push    r15
0x140007979  sub     rsp, 40h
0x14000797d  mov     r12, r9
0x140007980  mov     r13, r8
0x140007983  mov     r10, rcx
0x140007986  xor     eax, eax
0x140007988  mov     rsi, [rsp+78h+lpOutputString]
0x140007990  mov     [rsi], ax
0x140007993  mov     rax, [rsp+78h+arg_60]
0x14000799b  mov     byte ptr [rax], 0
0x14000799e  mov     r14, [rsp+78h+arg_38]
0x1400079a6  mov     edi, [r14]
0x1400079a9  mov     rbx, [rsp+78h+arg_78]
0x1400079b1  mov     [rbx+8], edi
0x1400079b4  mov     eax, [r14+4]
0x1400079b8  mov     [rbx+0Ch], eax
0x1400079bb  xor     ebp, ebp
0x1400079bd  mov     r15d, [rsp+78h+arg_30]
0x1400079c5  mov     ecx, r15d
0x1400079c8  test    r15d, r15d
0x1400079cb  jz      short loc_140007A33
0x1400079cd  sub     ecx, 1
0x1400079d0  jz      short loc_140007A2A
0x1400079d2  sub     ecx, 1
0x1400079d5  jz      short loc_1400079E5
0x1400079d7  cmp     ecx, 1
0x1400079da  jnz     short loc_140007A3C
0x1400079dc  mov     ecx, edi; this
0x1400079de  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1400079e3  jmp     short loc_140007A3A
0x1400079e5  test    edi, edi
0x1400079e7  js      short loc_140007A21
0x1400079e9  mov     edi, 8007029Ch
0x1400079ee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1400079f2  mov     rax, [rsp+78h+arg_28]
0x1400079fa  mov     [rsp+78h+var_50], rax; __int64
0x1400079ff  mov     rax, [rsp+78h+arg_20]
0x140007a07  mov     [rsp+78h+var_58], rax; __int64
0x140007a0c  mov     rcx, r10; int
0x140007a0f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007a14  mov     [rbx+8], edi
0x140007a17  mov     ecx, edi; this
0x140007a19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007a1e  mov     [rbx+0Ch], eax
0x140007a21  mov     ecx, edi; this
0x140007a23  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007a28  jmp     short loc_140007A3A
0x140007a2a  mov     ecx, edi; this
0x140007a2c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007a31  jmp     short loc_140007A3A
0x140007a33  mov     ecx, edi; this
0x140007a35  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140007a3a  mov     ebp, eax
0x140007a3c  mov     [rbx], r15d
0x140007a3f  mov     eax, [rsp+78h+arg_70]
0x140007a46  mov     [rbx+4], eax
0x140007a49  cmp     dword ptr [r14+8], 1
0x140007a4e  jnz     short loc_140007A56
0x140007a50  or      eax, 8
0x140007a53  mov     [rbx+4], eax
0x140007a56  mov     eax, 1
0x140007a5b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140007a63  inc     eax
0x140007a65  mov     [rbx+10h], eax
0x140007a68  mov     rax, [rsp+78h+arg_40]
0x140007a70  xor     edi, edi
0x140007a72  test    rax, rax
0x140007a75  jz      short loc_140007A7C
0x140007a77  cmp     [rax], di
0x140007a7a  jnz     short loc_140007A7F
0x140007a7c  mov     rax, rdi
0x140007a7f  mov     [rbx+18h], rax
0x140007a83  call    cs:__imp_GetCurrentThreadId
0x140007a89  mov     [rbx+20h], eax
0x140007a8c  mov     [rbx+38h], r13
0x140007a90  mov     eax, [rsp+78h+arg_8]
0x140007a97  mov     [rbx+40h], eax
0x140007a9a  mov     [rbx+44h], ebp
0x140007a9d  mov     rax, [rsp+78h+arg_20]
0x140007aa5  mov     [rbx+28h], rax
0x140007aa9  mov     [rbx+30h], r12
0x140007aad  mov     rax, [rsp+78h+arg_28]
0x140007ab5  mov     [rbx+88h], rax
0x140007abc  mov     rax, [rsp+78h+arg_0]
0x140007ac4  mov     [rbx+90h], rax
0x140007acb  mov     [rbx+48h], rdi
0x140007acf  xorps   xmm0, xmm0
0x140007ad2  xor     eax, eax
0x140007ad4  movups  xmmword ptr [rbx+68h], xmm0
0x140007ad8  mov     [rbx+78h], rax
0x140007adc  movups  xmmword ptr [rbx+50h], xmm0
0x140007ae0  mov     [rbx+60h], rax
0x140007ae4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140007aeb  test    rax, rax
0x140007aee  jz      short loc_140007AF7
0x140007af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007af5  jmp     short loc_140007AFA
0x140007af7  mov     rax, rdi
0x140007afa  mov     [rbx+80h], rax
0x140007b01  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007b08  test    rax, rax
0x140007b0b  jz      short loc_140007B15
0x140007b0d  mov     rcx, rbx
0x140007b10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b15  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140007b1c  test    rax, rax
0x140007b1f  jz      short loc_140007B37
0x140007b21  mov     r8d, 400h
0x140007b27  mov     rdx, [rsp+78h+arg_60]
0x140007b2f  mov     rcx, rbx
0x140007b32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007b3e  test    rax, rax
0x140007b41  jz      short loc_140007B4B
0x140007b43  mov     rcx, rbx
0x140007b46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b4b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140007b52  test    rax, rax
0x140007b55  jz      short loc_140007B65
0x140007b57  test    byte ptr [rbx+4], 2
0x140007b5b  jnz     short loc_140007B65
0x140007b5d  mov     rcx, rbx
0x140007b60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b65  cmp     [rbx+8], edi
0x140007b68  jl      short loc_140007B84
0x140007b6a  cmp     r15d, 3
0x140007b6e  jnz     loc_140007C53
0x140007b74  mov     ecx, 8000FFFFh; this
0x140007b79  mov     [rbx+8], ecx
0x140007b7c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140007b81  mov     [rbx+0Ch], eax
0x140007b84  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140007b8b  jnz     short loc_140007BAC
0x140007b8d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140007b94  test    rax, rax
0x140007b97  jz      short loc_140007BA2
0x140007b99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007b9e  test    al, al
0x140007ba0  jmp     short loc_140007BAA
0x140007ba2  call    cs:__imp_IsDebuggerPresent
0x140007ba8  test    eax, eax
0x140007baa  jz      short loc_140007BB2
0x140007bac  test    byte ptr [rbx+4], 2
0x140007bb0  jz      short loc_140007BD6
0x140007bb2  mov     rax, cs:g_pfnResultLoggingCallback
0x140007bb9  test    rax, rax
0x140007bbc  jz      short loc_140007C1A
0x140007bbe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007bc5  jnz     short loc_140007C1A
0x140007bc7  xor     r8d, r8d
0x140007bca  xor     edx, edx
0x140007bcc  mov     rcx, rbx
0x140007bcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bd4  jmp     short loc_140007C1A
0x140007bd6  mov     ebp, 800h
0x140007bdb  mov     rax, cs:g_pfnResultLoggingCallback
0x140007be2  test    rax, rax
0x140007be5  jz      short loc_140007BFE
0x140007be7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007bee  jnz     short loc_140007BFE
0x140007bf0  mov     r8d, ebp
0x140007bf3  mov     rdx, rsi
0x140007bf6  mov     rcx, rbx
0x140007bf9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007bfe  cmp     [rsi], di
0x140007c01  jnz     short loc_140007C11
0x140007c03  mov     r8, rbx; unsigned __int64
0x140007c06  mov     rdx, rbp; unsigned __int16 *
0x140007c09  mov     rcx, rsi; this
0x140007c0c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007c11  mov     rcx, rsi; lpOutputString
0x140007c14  call    cs:__imp_OutputDebugStringW
0x140007c1a  test    byte ptr [rbx+4], 4
0x140007c1e  jnz     short loc_140007C29
0x140007c20  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007c27  jz      short loc_140007C3B
0x140007c29  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007c30  test    rax, rax
0x140007c33  jz      short loc_140007C3B
0x140007c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007c3a  nop
0x140007c3b  mov     rbx, [rsp+78h+arg_10]
0x140007c43  add     rsp, 40h
0x140007c47  pop     r15
0x140007c49  pop     r14
0x140007c4b  pop     r13
0x140007c4d  pop     r12
0x140007c4f  pop     rdi
0x140007c50  pop     rsi
0x140007c51  pop     rbp
0x140007c52  retn
0x140007c53  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
