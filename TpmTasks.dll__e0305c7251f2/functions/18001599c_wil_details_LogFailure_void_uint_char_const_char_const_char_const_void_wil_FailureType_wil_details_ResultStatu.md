# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001599c`
- end: `0x180015c95`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000aa70`
- `0x18000ab30`
- `0x18000aee8`

## callees

- `0x18000a874`
- `0x180013e18`
- `0x180014ef0`
- `0x18001599c`
- `0x1800182bc`
- `0x1800182e0`
- `0x180018464`
- `0x180018480`
- `0x180023250`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015abf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180015abf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015c50`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180015c50`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015bde`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180015bde`

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
0x18001599c  mov     [rsp+arg_10], rbx
0x1800159a1  mov     [rsp+arg_8], edx
0x1800159a5  mov     [rsp+arg_0], rcx
0x1800159aa  push    rbp
0x1800159ab  push    rsi
0x1800159ac  push    rdi
0x1800159ad  push    r12
0x1800159af  push    r13
0x1800159b1  push    r14
0x1800159b3  push    r15
0x1800159b5  sub     rsp, 40h
0x1800159b9  mov     r12, r9
0x1800159bc  mov     r13, r8
0x1800159bf  mov     r10, rcx
0x1800159c2  xor     eax, eax
0x1800159c4  mov     rsi, [rsp+78h+lpOutputString]
0x1800159cc  mov     [rsi], ax
0x1800159cf  mov     rax, [rsp+78h+arg_60]
0x1800159d7  mov     byte ptr [rax], 0
0x1800159da  mov     r14, [rsp+78h+arg_38]
0x1800159e2  mov     edi, [r14]
0x1800159e5  mov     rbx, [rsp+78h+arg_78]
0x1800159ed  mov     [rbx+8], edi
0x1800159f0  mov     eax, [r14+4]
0x1800159f4  mov     [rbx+0Ch], eax
0x1800159f7  xor     ebp, ebp
0x1800159f9  mov     r15d, [rsp+78h+arg_30]
0x180015a01  mov     ecx, r15d
0x180015a04  test    r15d, r15d
0x180015a07  jz      short loc_180015A6F
0x180015a09  sub     ecx, 1
0x180015a0c  jz      short loc_180015A66
0x180015a0e  sub     ecx, 1
0x180015a11  jz      short loc_180015A21
0x180015a13  cmp     ecx, 1
0x180015a16  jnz     short loc_180015A78
0x180015a18  mov     ecx, edi; this
0x180015a1a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180015a1f  jmp     short loc_180015A76
0x180015a21  test    edi, edi
0x180015a23  js      short loc_180015A5D
0x180015a25  mov     edi, 8007029Ch
0x180015a2a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180015a2e  mov     rax, [rsp+78h+arg_28]
0x180015a36  mov     [rsp+78h+var_50], rax; __int64
0x180015a3b  mov     rax, [rsp+78h+arg_20]
0x180015a43  mov     [rsp+78h+var_58], rax; __int64
0x180015a48  mov     rcx, r10; int
0x180015a4b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180015a50  mov     [rbx+8], edi
0x180015a53  mov     ecx, edi; this
0x180015a55  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015a5a  mov     [rbx+0Ch], eax
0x180015a5d  mov     ecx, edi; this
0x180015a5f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180015a64  jmp     short loc_180015A76
0x180015a66  mov     ecx, edi; this
0x180015a68  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180015a6d  jmp     short loc_180015A76
0x180015a6f  mov     ecx, edi; this
0x180015a71  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180015a76  mov     ebp, eax
0x180015a78  mov     [rbx], r15d
0x180015a7b  mov     eax, [rsp+78h+arg_70]
0x180015a82  mov     [rbx+4], eax
0x180015a85  cmp     dword ptr [r14+8], 1
0x180015a8a  jnz     short loc_180015A92
0x180015a8c  or      eax, 8
0x180015a8f  mov     [rbx+4], eax
0x180015a92  mov     eax, 1
0x180015a97  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180015a9f  inc     eax
0x180015aa1  mov     [rbx+10h], eax
0x180015aa4  mov     rax, [rsp+78h+arg_40]
0x180015aac  xor     edi, edi
0x180015aae  test    rax, rax
0x180015ab1  jz      short loc_180015AB8
0x180015ab3  cmp     [rax], di
0x180015ab6  jnz     short loc_180015ABB
0x180015ab8  mov     rax, rdi
0x180015abb  mov     [rbx+18h], rax
0x180015abf  call    cs:__imp_GetCurrentThreadId
0x180015ac5  mov     [rbx+20h], eax
0x180015ac8  mov     [rbx+38h], r13
0x180015acc  mov     eax, [rsp+78h+arg_8]
0x180015ad3  mov     [rbx+40h], eax
0x180015ad6  mov     [rbx+44h], ebp
0x180015ad9  mov     rax, [rsp+78h+arg_20]
0x180015ae1  mov     [rbx+28h], rax
0x180015ae5  mov     [rbx+30h], r12
0x180015ae9  mov     rax, [rsp+78h+arg_28]
0x180015af1  mov     [rbx+88h], rax
0x180015af8  mov     rax, [rsp+78h+arg_0]
0x180015b00  mov     [rbx+90h], rax
0x180015b07  mov     [rbx+48h], rdi
0x180015b0b  xorps   xmm0, xmm0
0x180015b0e  xor     eax, eax
0x180015b10  movups  xmmword ptr [rbx+68h], xmm0
0x180015b14  mov     [rbx+78h], rax
0x180015b18  movups  xmmword ptr [rbx+50h], xmm0
0x180015b1c  mov     [rbx+60h], rax
0x180015b20  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180015b27  test    rax, rax
0x180015b2a  jz      short loc_180015B33
0x180015b2c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b31  jmp     short loc_180015B36
0x180015b33  mov     rax, rdi
0x180015b36  mov     [rbx+80h], rax
0x180015b3d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180015b44  test    rax, rax
0x180015b47  jz      short loc_180015B51
0x180015b49  mov     rcx, rbx
0x180015b4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b51  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180015b58  test    rax, rax
0x180015b5b  jz      short loc_180015B73
0x180015b5d  mov     r8d, 400h
0x180015b63  mov     rdx, [rsp+78h+arg_60]
0x180015b6b  mov     rcx, rbx
0x180015b6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b73  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015b7a  test    rax, rax
0x180015b7d  jz      short loc_180015B87
0x180015b7f  mov     rcx, rbx
0x180015b82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b87  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180015b8e  test    rax, rax
0x180015b91  jz      short loc_180015BA1
0x180015b93  test    byte ptr [rbx+4], 2
0x180015b97  jnz     short loc_180015BA1
0x180015b99  mov     rcx, rbx
0x180015b9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ba1  cmp     [rbx+8], edi
0x180015ba4  jl      short loc_180015BC0
0x180015ba6  cmp     r15d, 3
0x180015baa  jnz     loc_180015C8F
0x180015bb0  mov     ecx, 8000FFFFh; this
0x180015bb5  mov     [rbx+8], ecx
0x180015bb8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180015bbd  mov     [rbx+0Ch], eax
0x180015bc0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180015bc7  jnz     short loc_180015BE8
0x180015bc9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180015bd0  test    rax, rax
0x180015bd3  jz      short loc_180015BDE
0x180015bd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015bda  test    al, al
0x180015bdc  jmp     short loc_180015BE6
0x180015bde  call    cs:__imp_IsDebuggerPresent
0x180015be4  test    eax, eax
0x180015be6  jz      short loc_180015BEE
0x180015be8  test    byte ptr [rbx+4], 2
0x180015bec  jz      short loc_180015C12
0x180015bee  mov     rax, cs:g_pfnResultLoggingCallback
0x180015bf5  test    rax, rax
0x180015bf8  jz      short loc_180015C56
0x180015bfa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015c01  jnz     short loc_180015C56
0x180015c03  xor     r8d, r8d
0x180015c06  xor     edx, edx
0x180015c08  mov     rcx, rbx
0x180015c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c10  jmp     short loc_180015C56
0x180015c12  mov     ebp, 800h
0x180015c17  mov     rax, cs:g_pfnResultLoggingCallback
0x180015c1e  test    rax, rax
0x180015c21  jz      short loc_180015C3A
0x180015c23  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180015c2a  jnz     short loc_180015C3A
0x180015c2c  mov     r8d, ebp
0x180015c2f  mov     rdx, rsi
0x180015c32  mov     rcx, rbx
0x180015c35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c3a  cmp     [rsi], di
0x180015c3d  jnz     short loc_180015C4D
0x180015c3f  mov     r8, rbx; unsigned __int64
0x180015c42  mov     rdx, rbp; unsigned __int16 *
0x180015c45  mov     rcx, rsi; this
0x180015c48  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180015c4d  mov     rcx, rsi; lpOutputString
0x180015c50  call    cs:__imp_OutputDebugStringW
0x180015c56  test    byte ptr [rbx+4], 4
0x180015c5a  jnz     short loc_180015C65
0x180015c5c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180015c63  jz      short loc_180015C77
0x180015c65  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180015c6c  test    rax, rax
0x180015c6f  jz      short loc_180015C77
0x180015c71  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015c76  nop
0x180015c77  mov     rbx, [rsp+78h+arg_10]
0x180015c7f  add     rsp, 40h
0x180015c83  pop     r15
0x180015c85  pop     r14
0x180015c87  pop     r13
0x180015c89  pop     r12
0x180015c8b  pop     rdi
0x180015c8c  pop     rsi
0x180015c8d  pop     rbp
0x180015c8e  retn
0x180015c8f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
