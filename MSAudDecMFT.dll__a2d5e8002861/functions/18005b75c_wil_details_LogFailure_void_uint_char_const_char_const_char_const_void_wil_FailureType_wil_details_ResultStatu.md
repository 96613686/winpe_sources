# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18005b75c`
- end: `0x18005ba6d`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `785`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180058768`
- `0x18005881c`
- `0x180058914`

## callees

- `0x18004cbac`
- `0x180057474`
- `0x180057d00`
- `0x1800586b8`
- `0x18005b75c`
- `0x18005bfb8`
- `0x18005bfd8`
- `0x18005bff8`
- `0x18005cb18`
- `0x1800960c0`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b87f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18005b87f`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005b9ac`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18005b9ac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005ba26`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18005ba26`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x18005b75c  mov     [rsp+arg_10], rbx
0x18005b761  mov     [rsp+arg_8], edx
0x18005b765  mov     [rsp+arg_0], rcx
0x18005b76a  push    rbp
0x18005b76b  push    rsi
0x18005b76c  push    rdi
0x18005b76d  push    r12
0x18005b76f  push    r13
0x18005b771  push    r14
0x18005b773  push    r15
0x18005b775  sub     rsp, 40h
0x18005b779  mov     r12, r9
0x18005b77c  mov     r13, r8
0x18005b77f  mov     r10, rcx
0x18005b782  xor     eax, eax
0x18005b784  mov     rsi, [rsp+78h+lpOutputString]
0x18005b78c  mov     [rsi], ax
0x18005b78f  mov     rax, [rsp+78h+arg_60]
0x18005b797  mov     byte ptr [rax], 0
0x18005b79a  mov     r14, [rsp+78h+arg_38]
0x18005b7a2  mov     edi, [r14]
0x18005b7a5  mov     rbx, [rsp+78h+arg_78]
0x18005b7ad  mov     [rbx+8], edi
0x18005b7b0  mov     eax, [r14+4]
0x18005b7b4  mov     [rbx+0Ch], eax
0x18005b7b7  xor     ebp, ebp
0x18005b7b9  mov     r15d, [rsp+78h+arg_30]
0x18005b7c1  mov     ecx, r15d
0x18005b7c4  test    r15d, r15d
0x18005b7c7  jz      short loc_18005B82F
0x18005b7c9  sub     ecx, 1
0x18005b7cc  jz      short loc_18005B826
0x18005b7ce  sub     ecx, 1
0x18005b7d1  jz      short loc_18005B7E1
0x18005b7d3  cmp     ecx, 1
0x18005b7d6  jnz     short loc_18005B838
0x18005b7d8  mov     ecx, edi; this
0x18005b7da  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18005b7df  jmp     short loc_18005B836
0x18005b7e1  test    edi, edi
0x18005b7e3  js      short loc_18005B81D
0x18005b7e5  mov     edi, 8007029Ch
0x18005b7ea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18005b7ee  mov     rax, [rsp+78h+arg_28]
0x18005b7f6  mov     [rsp+78h+var_50], rax; __int64
0x18005b7fb  mov     rax, [rsp+78h+arg_20]
0x18005b803  mov     [rsp+78h+var_58], rax; __int64
0x18005b808  mov     rcx, r10; int
0x18005b80b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18005b810  mov     [rbx+8], edi
0x18005b813  mov     ecx, edi; this
0x18005b815  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005b81a  mov     [rbx+0Ch], eax
0x18005b81d  mov     ecx, edi; this
0x18005b81f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18005b824  jmp     short loc_18005B836
0x18005b826  mov     ecx, edi; this
0x18005b828  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18005b82d  jmp     short loc_18005B836
0x18005b82f  mov     ecx, edi; this
0x18005b831  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18005b836  mov     ebp, eax
0x18005b838  mov     [rbx], r15d
0x18005b83b  mov     eax, [rsp+78h+arg_70]
0x18005b842  mov     [rbx+4], eax
0x18005b845  cmp     dword ptr [r14+8], 1
0x18005b84a  jnz     short loc_18005B852
0x18005b84c  or      eax, 8
0x18005b84f  mov     [rbx+4], eax
0x18005b852  mov     eax, 1
0x18005b857  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18005b85f  inc     eax
0x18005b861  mov     [rbx+10h], eax
0x18005b864  mov     rax, [rsp+78h+arg_40]
0x18005b86c  xor     edi, edi
0x18005b86e  test    rax, rax
0x18005b871  jz      short loc_18005B878
0x18005b873  cmp     [rax], di
0x18005b876  jnz     short loc_18005B87B
0x18005b878  mov     rax, rdi
0x18005b87b  mov     [rbx+18h], rax
0x18005b87f  call    cs:__imp_GetCurrentThreadId
0x18005b886  nop     dword ptr [rax+rax+00h]
0x18005b88b  mov     [rbx+20h], eax
0x18005b88e  mov     [rbx+38h], r13
0x18005b892  mov     eax, [rsp+78h+arg_8]
0x18005b899  mov     [rbx+40h], eax
0x18005b89c  mov     [rbx+44h], ebp
0x18005b89f  mov     rax, [rsp+78h+arg_20]
0x18005b8a7  mov     [rbx+28h], rax
0x18005b8ab  mov     [rbx+30h], r12
0x18005b8af  mov     rax, [rsp+78h+arg_28]
0x18005b8b7  mov     [rbx+88h], rax
0x18005b8be  mov     rax, [rsp+78h+arg_0]
0x18005b8c6  mov     [rbx+90h], rax
0x18005b8cd  mov     [rbx+48h], rdi
0x18005b8d1  xorps   xmm0, xmm0
0x18005b8d4  xor     eax, eax
0x18005b8d6  movups  xmmword ptr [rbx+68h], xmm0
0x18005b8da  mov     [rbx+78h], rax
0x18005b8de  movups  xmmword ptr [rbx+50h], xmm0
0x18005b8e2  mov     [rbx+60h], rax
0x18005b8e6  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18005b8ed  test    rax, rax
0x18005b8f0  jz      short loc_18005B8FA
0x18005b8f2  call    cs:__guard_dispatch_icall_fptr
0x18005b8f8  jmp     short loc_18005B8FD
0x18005b8fa  mov     rax, rdi
0x18005b8fd  mov     [rbx+80h], rax
0x18005b904  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18005b90b  test    rax, rax
0x18005b90e  jz      short loc_18005B919
0x18005b910  mov     rcx, rbx
0x18005b913  call    cs:__guard_dispatch_icall_fptr
0x18005b919  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18005b920  test    rax, rax
0x18005b923  jz      short loc_18005B93C
0x18005b925  mov     r8d, 400h
0x18005b92b  mov     rdx, [rsp+78h+arg_60]
0x18005b933  mov     rcx, rbx
0x18005b936  call    cs:__guard_dispatch_icall_fptr
0x18005b93c  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005b943  test    rax, rax
0x18005b946  jz      short loc_18005B951
0x18005b948  mov     rcx, rbx
0x18005b94b  call    cs:__guard_dispatch_icall_fptr
0x18005b951  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18005b958  test    rax, rax
0x18005b95b  jz      short loc_18005B96C
0x18005b95d  test    byte ptr [rbx+4], 2
0x18005b961  jnz     short loc_18005B96C
0x18005b963  mov     rcx, rbx
0x18005b966  call    cs:__guard_dispatch_icall_fptr
0x18005b96c  cmp     [rbx+8], edi
0x18005b96f  jl      short loc_18005B98D
0x18005b971  cmp     r15d, 3
0x18005b975  jz      short loc_18005B97D
0x18005b977  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x18005b97d  mov     ecx, 8000FFFFh; this
0x18005b982  mov     [rbx+8], ecx
0x18005b985  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18005b98a  mov     [rbx+0Ch], eax
0x18005b98d  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18005b994  jnz     short loc_18005B9BC
0x18005b996  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18005b99d  test    rax, rax
0x18005b9a0  jz      short loc_18005B9AC
0x18005b9a2  call    cs:__guard_dispatch_icall_fptr
0x18005b9a8  test    al, al
0x18005b9aa  jmp     short loc_18005B9BA
0x18005b9ac  call    cs:__imp_IsDebuggerPresent
0x18005b9b3  nop     dword ptr [rax+rax+00h]
0x18005b9b8  test    eax, eax
0x18005b9ba  jz      short loc_18005B9C2
0x18005b9bc  test    byte ptr [rbx+4], 2
0x18005b9c0  jz      short loc_18005B9E7
0x18005b9c2  mov     rax, cs:g_pfnResultLoggingCallback
0x18005b9c9  test    rax, rax
0x18005b9cc  jz      short loc_18005BA32
0x18005b9ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005b9d5  jnz     short loc_18005BA32
0x18005b9d7  xor     r8d, r8d
0x18005b9da  xor     edx, edx
0x18005b9dc  mov     rcx, rbx
0x18005b9df  call    cs:__guard_dispatch_icall_fptr
0x18005b9e5  jmp     short loc_18005BA32
0x18005b9e7  mov     ebp, 800h
0x18005b9ec  mov     rax, cs:g_pfnResultLoggingCallback
0x18005b9f3  test    rax, rax
0x18005b9f6  jz      short loc_18005BA10
0x18005b9f8  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18005b9ff  jnz     short loc_18005BA10
0x18005ba01  mov     r8d, ebp
0x18005ba04  mov     rdx, rsi
0x18005ba07  mov     rcx, rbx
0x18005ba0a  call    cs:__guard_dispatch_icall_fptr
0x18005ba10  cmp     [rsi], di
0x18005ba13  jnz     short loc_18005BA23
0x18005ba15  mov     r8, rbx; unsigned __int64
0x18005ba18  mov     rdx, rbp; unsigned __int16 *
0x18005ba1b  mov     rcx, rsi; this
0x18005ba1e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18005ba23  mov     rcx, rsi; lpOutputString
0x18005ba26  call    cs:__imp_OutputDebugStringW
0x18005ba2d  nop     dword ptr [rax+rax+00h]
0x18005ba32  test    byte ptr [rbx+4], 4
0x18005ba36  jnz     short loc_18005BA41
0x18005ba38  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18005ba3f  jz      short loc_18005BA54
0x18005ba41  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18005ba48  test    rax, rax
0x18005ba4b  jz      short loc_18005BA54
0x18005ba4d  call    cs:__guard_dispatch_icall_fptr
0x18005ba53  nop
0x18005ba54  mov     rbx, [rsp+78h+arg_10]
0x18005ba5c  add     rsp, 40h
0x18005ba60  pop     r15
0x18005ba62  pop     r14
0x18005ba64  pop     r13
0x18005ba66  pop     r12
0x18005ba68  pop     rdi
0x18005ba69  pop     rsi
0x18005ba6a  pop     rbp
0x18005ba6b  retn
```
