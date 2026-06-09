# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005e70`
- end: `0x180006169`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003294`

## callees

- `0x180002cd8`
- `0x1800053a4`
- `0x180005b44`
- `0x180005e70`
- `0x1800067e8`
- `0x180006810`
- `0x180006824`
- `0x180006840`
- `0x180008a04`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005f93`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006124`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006124`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800060b2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800060b2`

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
0x180005e70  mov     [rsp+arg_10], rbx
0x180005e75  mov     [rsp+arg_8], edx
0x180005e79  mov     [rsp+arg_0], rcx
0x180005e7e  push    rbp
0x180005e7f  push    rsi
0x180005e80  push    rdi
0x180005e81  push    r12
0x180005e83  push    r13
0x180005e85  push    r14
0x180005e87  push    r15
0x180005e89  sub     rsp, 40h
0x180005e8d  mov     r12, r9
0x180005e90  mov     r13, r8
0x180005e93  mov     r10, rcx
0x180005e96  xor     eax, eax
0x180005e98  mov     rsi, [rsp+78h+lpOutputString]
0x180005ea0  mov     [rsi], ax
0x180005ea3  mov     rax, [rsp+78h+arg_60]
0x180005eab  mov     byte ptr [rax], 0
0x180005eae  mov     r14, [rsp+78h+arg_38]
0x180005eb6  mov     edi, [r14]
0x180005eb9  mov     rbx, [rsp+78h+arg_78]
0x180005ec1  mov     [rbx+8], edi
0x180005ec4  mov     eax, [r14+4]
0x180005ec8  mov     [rbx+0Ch], eax
0x180005ecb  xor     ebp, ebp
0x180005ecd  mov     r15d, [rsp+78h+arg_30]
0x180005ed5  mov     ecx, r15d
0x180005ed8  test    r15d, r15d
0x180005edb  jz      short loc_180005F43
0x180005edd  sub     ecx, 1
0x180005ee0  jz      short loc_180005F3A
0x180005ee2  sub     ecx, 1
0x180005ee5  jz      short loc_180005EF5
0x180005ee7  cmp     ecx, 1
0x180005eea  jnz     short loc_180005F4C
0x180005eec  mov     ecx, edi; this
0x180005eee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005ef3  jmp     short loc_180005F4A
0x180005ef5  test    edi, edi
0x180005ef7  js      short loc_180005F31
0x180005ef9  mov     edi, 8007029Ch
0x180005efe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005f02  mov     rax, [rsp+78h+arg_28]
0x180005f0a  mov     [rsp+78h+var_50], rax; __int64
0x180005f0f  mov     rax, [rsp+78h+arg_20]
0x180005f17  mov     [rsp+78h+var_58], rax; __int64
0x180005f1c  mov     rcx, r10; int
0x180005f1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005f24  mov     [rbx+8], edi
0x180005f27  mov     ecx, edi; this
0x180005f29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005f2e  mov     [rbx+0Ch], eax
0x180005f31  mov     ecx, edi; this
0x180005f33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005f38  jmp     short loc_180005F4A
0x180005f3a  mov     ecx, edi; this
0x180005f3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005f41  jmp     short loc_180005F4A
0x180005f43  mov     ecx, edi; this
0x180005f45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005f4a  mov     ebp, eax
0x180005f4c  mov     [rbx], r15d
0x180005f4f  mov     eax, [rsp+78h+arg_70]
0x180005f56  mov     [rbx+4], eax
0x180005f59  cmp     dword ptr [r14+8], 1
0x180005f5e  jnz     short loc_180005F66
0x180005f60  or      eax, 8
0x180005f63  mov     [rbx+4], eax
0x180005f66  mov     eax, 1
0x180005f6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005f73  inc     eax
0x180005f75  mov     [rbx+10h], eax
0x180005f78  mov     rax, [rsp+78h+arg_40]
0x180005f80  xor     edi, edi
0x180005f82  test    rax, rax
0x180005f85  jz      short loc_180005F8C
0x180005f87  cmp     [rax], di
0x180005f8a  jnz     short loc_180005F8F
0x180005f8c  mov     rax, rdi
0x180005f8f  mov     [rbx+18h], rax
0x180005f93  call    cs:__imp_GetCurrentThreadId
0x180005f99  mov     [rbx+20h], eax
0x180005f9c  mov     [rbx+38h], r13
0x180005fa0  mov     eax, [rsp+78h+arg_8]
0x180005fa7  mov     [rbx+40h], eax
0x180005faa  mov     [rbx+44h], ebp
0x180005fad  mov     rax, [rsp+78h+arg_20]
0x180005fb5  mov     [rbx+28h], rax
0x180005fb9  mov     [rbx+30h], r12
0x180005fbd  mov     rax, [rsp+78h+arg_28]
0x180005fc5  mov     [rbx+88h], rax
0x180005fcc  mov     rax, [rsp+78h+arg_0]
0x180005fd4  mov     [rbx+90h], rax
0x180005fdb  mov     [rbx+48h], rdi
0x180005fdf  xorps   xmm0, xmm0
0x180005fe2  xor     eax, eax
0x180005fe4  movups  xmmword ptr [rbx+68h], xmm0
0x180005fe8  mov     [rbx+78h], rax
0x180005fec  movups  xmmword ptr [rbx+50h], xmm0
0x180005ff0  mov     [rbx+60h], rax
0x180005ff4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005ffb  test    rax, rax
0x180005ffe  jz      short loc_180006007
0x180006000  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006005  jmp     short loc_18000600A
0x180006007  mov     rax, rdi
0x18000600a  mov     [rbx+80h], rax
0x180006011  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006018  test    rax, rax
0x18000601b  jz      short loc_180006025
0x18000601d  mov     rcx, rbx
0x180006020  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006025  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000602c  test    rax, rax
0x18000602f  jz      short loc_180006047
0x180006031  mov     r8d, 400h
0x180006037  mov     rdx, [rsp+78h+arg_60]
0x18000603f  mov     rcx, rbx
0x180006042  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006047  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000604e  test    rax, rax
0x180006051  jz      short loc_18000605B
0x180006053  mov     rcx, rbx
0x180006056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000605b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006062  test    rax, rax
0x180006065  jz      short loc_180006075
0x180006067  test    byte ptr [rbx+4], 2
0x18000606b  jnz     short loc_180006075
0x18000606d  mov     rcx, rbx
0x180006070  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006075  cmp     [rbx+8], edi
0x180006078  jl      short loc_180006094
0x18000607a  cmp     r15d, 3
0x18000607e  jnz     loc_180006163
0x180006084  mov     ecx, 8000FFFFh; this
0x180006089  mov     [rbx+8], ecx
0x18000608c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006091  mov     [rbx+0Ch], eax
0x180006094  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000609b  jnz     short loc_1800060BC
0x18000609d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800060a4  test    rax, rax
0x1800060a7  jz      short loc_1800060B2
0x1800060a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060ae  test    al, al
0x1800060b0  jmp     short loc_1800060BA
0x1800060b2  call    cs:__imp_IsDebuggerPresent
0x1800060b8  test    eax, eax
0x1800060ba  jz      short loc_1800060C2
0x1800060bc  test    byte ptr [rbx+4], 2
0x1800060c0  jz      short loc_1800060E6
0x1800060c2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800060c9  test    rax, rax
0x1800060cc  jz      short loc_18000612A
0x1800060ce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800060d5  jnz     short loc_18000612A
0x1800060d7  xor     r8d, r8d
0x1800060da  xor     edx, edx
0x1800060dc  mov     rcx, rbx
0x1800060df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e4  jmp     short loc_18000612A
0x1800060e6  mov     ebp, 800h
0x1800060eb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800060f2  test    rax, rax
0x1800060f5  jz      short loc_18000610E
0x1800060f7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800060fe  jnz     short loc_18000610E
0x180006100  mov     r8d, ebp
0x180006103  mov     rdx, rsi
0x180006106  mov     rcx, rbx
0x180006109  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000610e  cmp     [rsi], di
0x180006111  jnz     short loc_180006121
0x180006113  mov     r8, rbx; unsigned __int64
0x180006116  mov     rdx, rbp; unsigned __int16 *
0x180006119  mov     rcx, rsi; this
0x18000611c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006121  mov     rcx, rsi; lpOutputString
0x180006124  call    cs:__imp_OutputDebugStringW
0x18000612a  test    byte ptr [rbx+4], 4
0x18000612e  jnz     short loc_180006139
0x180006130  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006137  jz      short loc_18000614B
0x180006139  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006140  test    rax, rax
0x180006143  jz      short loc_18000614B
0x180006145  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000614a  nop
0x18000614b  mov     rbx, [rsp+78h+arg_10]
0x180006153  add     rsp, 40h
0x180006157  pop     r15
0x180006159  pop     r14
0x18000615b  pop     r13
0x18000615d  pop     r12
0x18000615f  pop     rdi
0x180006160  pop     rsi
0x180006161  pop     rbp
0x180006162  retn
0x180006163  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
