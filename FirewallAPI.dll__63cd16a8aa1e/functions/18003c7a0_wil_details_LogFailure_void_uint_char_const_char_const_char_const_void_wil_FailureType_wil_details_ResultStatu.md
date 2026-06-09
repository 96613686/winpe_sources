# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18003c7a0`
- end: `0x18003ca9c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18003a6bc`
- `0x18003aa30`

## callees

- `0x180021cc4`
- `0x18003a600`
- `0x18003c194`
- `0x18003c7a0`
- `0x18003d214`
- `0x18003d230`
- `0x18003d244`
- `0x18003d260`
- `0x18003e530`
- `0x18005e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c8c1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18003c8c1`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003ca57`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18003ca57`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c9e4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18003c9e4`

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
  __int64 (*ModuleName)(void); // rax
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
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (*)(void))wil::details::g_pfnGetModuleName();
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
0x18003c7a0  mov     [rsp+arg_10], rbx
0x18003c7a5  mov     [rsp+arg_8], edx
0x18003c7a9  mov     [rsp+arg_0], rcx
0x18003c7ae  push    rbp
0x18003c7af  push    rsi
0x18003c7b0  push    rdi
0x18003c7b1  push    r12
0x18003c7b3  push    r13
0x18003c7b5  push    r14
0x18003c7b7  push    r15
0x18003c7b9  sub     rsp, 40h
0x18003c7bd  mov     r12, r9
0x18003c7c0  mov     r13, r8
0x18003c7c3  mov     r10, rcx
0x18003c7c6  xor     eax, eax
0x18003c7c8  mov     rsi, [rsp+78h+lpOutputString]
0x18003c7d0  mov     [rsi], ax
0x18003c7d3  mov     rax, [rsp+78h+arg_60]
0x18003c7db  mov     byte ptr [rax], 0
0x18003c7de  mov     r14, [rsp+78h+arg_38]
0x18003c7e6  mov     edi, [r14]
0x18003c7e9  mov     rbx, [rsp+78h+arg_78]
0x18003c7f1  mov     [rbx+8], edi
0x18003c7f4  mov     eax, [r14+4]
0x18003c7f8  mov     [rbx+0Ch], eax
0x18003c7fb  xor     ebp, ebp
0x18003c7fd  mov     r15d, [rsp+78h+arg_30]
0x18003c805  mov     ecx, r15d
0x18003c808  test    r15d, r15d
0x18003c80b  jz      short loc_18003C873
0x18003c80d  sub     ecx, 1
0x18003c810  jz      short loc_18003C86A
0x18003c812  sub     ecx, 1
0x18003c815  jz      short loc_18003C825
0x18003c817  cmp     ecx, 1
0x18003c81a  jnz     short loc_18003C87C
0x18003c81c  mov     ecx, edi; this
0x18003c81e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18003c823  jmp     short loc_18003C87A
0x18003c825  test    edi, edi
0x18003c827  js      short loc_18003C861
0x18003c829  mov     edi, 8007029Ch
0x18003c82e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18003c832  mov     rax, [rsp+78h+arg_28]
0x18003c83a  mov     [rsp+78h+var_50], rax; __int64
0x18003c83f  mov     rax, [rsp+78h+arg_20]
0x18003c847  mov     [rsp+78h+var_58], rax; __int64
0x18003c84c  mov     rcx, r10; int
0x18003c84f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18003c854  mov     [rbx+8], edi
0x18003c857  mov     ecx, edi; this
0x18003c859  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c85e  mov     [rbx+0Ch], eax
0x18003c861  mov     ecx, edi; this
0x18003c863  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18003c868  jmp     short loc_18003C87A
0x18003c86a  mov     ecx, edi; this
0x18003c86c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18003c871  jmp     short loc_18003C87A
0x18003c873  mov     ecx, edi; this
0x18003c875  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18003c87a  mov     ebp, eax
0x18003c87c  mov     [rbx], r15d
0x18003c87f  mov     eax, [rsp+78h+arg_70]
0x18003c886  mov     [rbx+4], eax
0x18003c889  cmp     dword ptr [r14+8], 1
0x18003c88e  jnz     short loc_18003C896
0x18003c890  or      eax, 8
0x18003c893  mov     [rbx+4], eax
0x18003c896  mov     eax, 1
0x18003c89b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18003c8a3  inc     eax
0x18003c8a5  mov     [rbx+10h], eax
0x18003c8a8  mov     rax, [rsp+78h+arg_40]
0x18003c8b0  test    rax, rax
0x18003c8b3  jz      short loc_18003C8BB
0x18003c8b5  cmp     word ptr [rax], 0
0x18003c8b9  jnz     short loc_18003C8BD
0x18003c8bb  xor     eax, eax
0x18003c8bd  mov     [rbx+18h], rax
0x18003c8c1  call    cs:__imp_GetCurrentThreadId
0x18003c8c7  mov     [rbx+20h], eax
0x18003c8ca  mov     [rbx+38h], r13
0x18003c8ce  mov     eax, [rsp+78h+arg_8]
0x18003c8d5  mov     [rbx+40h], eax
0x18003c8d8  mov     [rbx+44h], ebp
0x18003c8db  mov     rax, [rsp+78h+arg_20]
0x18003c8e3  mov     [rbx+28h], rax
0x18003c8e7  mov     [rbx+30h], r12
0x18003c8eb  mov     rax, [rsp+78h+arg_28]
0x18003c8f3  mov     [rbx+88h], rax
0x18003c8fa  mov     rax, [rsp+78h+arg_0]
0x18003c902  mov     [rbx+90h], rax
0x18003c909  mov     qword ptr [rbx+48h], 0
0x18003c911  xorps   xmm0, xmm0
0x18003c914  xor     eax, eax
0x18003c916  movups  xmmword ptr [rbx+68h], xmm0
0x18003c91a  mov     [rbx+78h], rax
0x18003c91e  movups  xmmword ptr [rbx+50h], xmm0
0x18003c922  mov     [rbx+60h], rax
0x18003c926  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18003c92d  test    rax, rax
0x18003c930  jz      short loc_18003C937
0x18003c932  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c937  mov     [rbx+80h], rax
0x18003c93e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18003c945  test    rax, rax
0x18003c948  jz      short loc_18003C952
0x18003c94a  mov     rcx, rbx
0x18003c94d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c952  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18003c959  test    rax, rax
0x18003c95c  jz      short loc_18003C974
0x18003c95e  mov     r8d, 400h
0x18003c964  mov     rdx, [rsp+78h+arg_60]
0x18003c96c  mov     rcx, rbx
0x18003c96f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c974  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c97b  test    rax, rax
0x18003c97e  jz      short loc_18003C988
0x18003c980  mov     rcx, rbx
0x18003c983  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c988  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18003c98f  test    rax, rax
0x18003c992  jz      short loc_18003C9A2
0x18003c994  test    byte ptr [rbx+4], 2
0x18003c998  jnz     short loc_18003C9A2
0x18003c99a  mov     rcx, rbx
0x18003c99d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9a2  cmp     dword ptr [rbx+8], 0
0x18003c9a6  jl      short loc_18003C9C6
0x18003c9a8  cmp     r15d, 3
0x18003c9ac  jnz     loc_18003CA96
0x18003c9b2  mov     dword ptr [rbx+8], 8000FFFFh
0x18003c9b9  mov     ecx, 8000FFFFh; this
0x18003c9be  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18003c9c3  mov     [rbx+0Ch], eax
0x18003c9c6  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x18003c9cd  jnz     short loc_18003C9EE
0x18003c9cf  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18003c9d6  test    rax, rax
0x18003c9d9  jz      short loc_18003C9E4
0x18003c9db  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c9e0  test    al, al
0x18003c9e2  jmp     short loc_18003C9EC
0x18003c9e4  call    cs:__imp_IsDebuggerPresent
0x18003c9ea  test    eax, eax
0x18003c9ec  jz      short loc_18003C9F4
0x18003c9ee  test    byte ptr [rbx+4], 2
0x18003c9f2  jz      short loc_18003CA18
0x18003c9f4  mov     rax, cs:g_pfnResultLoggingCallback
0x18003c9fb  test    rax, rax
0x18003c9fe  jz      short loc_18003CA5D
0x18003ca00  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18003ca07  jnz     short loc_18003CA5D
0x18003ca09  xor     r8d, r8d
0x18003ca0c  xor     edx, edx
0x18003ca0e  mov     rcx, rbx
0x18003ca11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca16  jmp     short loc_18003CA5D
0x18003ca18  mov     rax, cs:g_pfnResultLoggingCallback
0x18003ca1f  test    rax, rax
0x18003ca22  jz      short loc_18003CA3E
0x18003ca24  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18003ca2b  jnz     short loc_18003CA3E
0x18003ca2d  mov     r8d, 800h
0x18003ca33  mov     rdx, rsi
0x18003ca36  mov     rcx, rbx
0x18003ca39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca3e  cmp     word ptr [rsi], 0
0x18003ca42  jnz     short loc_18003CA54
0x18003ca44  mov     r8, rbx; unsigned __int64
0x18003ca47  mov     edx, 800h; unsigned __int16 *
0x18003ca4c  mov     rcx, rsi; this
0x18003ca4f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18003ca54  mov     rcx, rsi; lpOutputString
0x18003ca57  call    cs:__imp_OutputDebugStringW
0x18003ca5d  test    byte ptr [rbx+4], 4
0x18003ca61  jnz     short loc_18003CA6C
0x18003ca63  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x18003ca6a  jz      short loc_18003CA7E
0x18003ca6c  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18003ca73  test    rax, rax
0x18003ca76  jz      short loc_18003CA7E
0x18003ca78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ca7d  nop
0x18003ca7e  mov     rbx, [rsp+78h+arg_10]
0x18003ca86  add     rsp, 40h
0x18003ca8a  pop     r15
0x18003ca8c  pop     r14
0x18003ca8e  pop     r13
0x18003ca90  pop     r12
0x18003ca92  pop     rdi
0x18003ca93  pop     rsi
0x18003ca94  pop     rbp
0x18003ca95  retn
0x18003ca96  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
