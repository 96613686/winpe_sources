# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180027ee0`
- end: `0x1800281dc`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `764`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, WCHAR *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18002461c`
- `0x180024990`

## callees

- `0x18001f02c`
- `0x180024560`
- `0x180027604`
- `0x180027ee0`
- `0x180028964`
- `0x180028980`
- `0x180028994`
- `0x1800289b0`
- `0x180029b2c`
- `0x18003b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028001`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180028001`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180028197`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180028197`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180028124`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180028124`

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
        WCHAR *lpOutputString,
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
  __int64 (__fastcall *ModuleName)(_QWORD); // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
  ModuleName = wil::details::g_pfnGetModuleName;
  if ( wil::details::g_pfnGetModuleName )
    ModuleName = (__int64 (__fastcall *)(_QWORD))wil::details::g_pfnGetModuleName(v22);
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW(lpOutputString);
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
0x180027ee0  mov     [rsp+arg_10], rbx
0x180027ee5  mov     [rsp+arg_8], edx
0x180027ee9  mov     [rsp+arg_0], rcx
0x180027eee  push    rbp
0x180027eef  push    rsi
0x180027ef0  push    rdi
0x180027ef1  push    r12
0x180027ef3  push    r13
0x180027ef5  push    r14
0x180027ef7  push    r15
0x180027ef9  sub     rsp, 40h
0x180027efd  mov     r12, r9
0x180027f00  mov     r13, r8
0x180027f03  mov     r10, rcx
0x180027f06  xor     eax, eax
0x180027f08  mov     rsi, [rsp+78h+lpOutputString]
0x180027f10  mov     [rsi], ax
0x180027f13  mov     rax, [rsp+78h+arg_60]
0x180027f1b  mov     byte ptr [rax], 0
0x180027f1e  mov     r14, [rsp+78h+arg_38]
0x180027f26  mov     edi, [r14]
0x180027f29  mov     rbx, [rsp+78h+arg_78]
0x180027f31  mov     [rbx+8], edi
0x180027f34  mov     eax, [r14+4]
0x180027f38  mov     [rbx+0Ch], eax
0x180027f3b  xor     ebp, ebp
0x180027f3d  mov     r15d, [rsp+78h+arg_30]
0x180027f45  mov     ecx, r15d
0x180027f48  test    r15d, r15d
0x180027f4b  jz      short loc_180027FB3
0x180027f4d  sub     ecx, 1
0x180027f50  jz      short loc_180027FAA
0x180027f52  sub     ecx, 1
0x180027f55  jz      short loc_180027F65
0x180027f57  cmp     ecx, 1
0x180027f5a  jnz     short loc_180027FBC
0x180027f5c  mov     ecx, edi; this
0x180027f5e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180027f63  jmp     short loc_180027FBA
0x180027f65  test    edi, edi
0x180027f67  js      short loc_180027FA1
0x180027f69  mov     edi, 8007029Ch
0x180027f6e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180027f72  mov     rax, [rsp+78h+arg_28]
0x180027f7a  mov     [rsp+78h+var_50], rax; __int64
0x180027f7f  mov     rax, [rsp+78h+arg_20]
0x180027f87  mov     [rsp+78h+var_58], rax; __int64
0x180027f8c  mov     rcx, r10; int
0x180027f8f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180027f94  mov     [rbx+8], edi
0x180027f97  mov     ecx, edi; this
0x180027f99  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180027f9e  mov     [rbx+0Ch], eax
0x180027fa1  mov     ecx, edi; this
0x180027fa3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180027fa8  jmp     short loc_180027FBA
0x180027faa  mov     ecx, edi; this
0x180027fac  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180027fb1  jmp     short loc_180027FBA
0x180027fb3  mov     ecx, edi; this
0x180027fb5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180027fba  mov     ebp, eax
0x180027fbc  mov     [rbx], r15d
0x180027fbf  mov     eax, [rsp+78h+arg_70]
0x180027fc6  mov     [rbx+4], eax
0x180027fc9  cmp     dword ptr [r14+8], 1
0x180027fce  jnz     short loc_180027FD6
0x180027fd0  or      eax, 8
0x180027fd3  mov     [rbx+4], eax
0x180027fd6  mov     eax, 1
0x180027fdb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180027fe3  inc     eax
0x180027fe5  mov     [rbx+10h], eax
0x180027fe8  mov     rax, [rsp+78h+arg_40]
0x180027ff0  test    rax, rax
0x180027ff3  jz      short loc_180027FFB
0x180027ff5  cmp     word ptr [rax], 0
0x180027ff9  jnz     short loc_180027FFD
0x180027ffb  xor     eax, eax
0x180027ffd  mov     [rbx+18h], rax
0x180028001  call    cs:__imp_GetCurrentThreadId
0x180028007  mov     [rbx+20h], eax
0x18002800a  mov     [rbx+38h], r13
0x18002800e  mov     eax, [rsp+78h+arg_8]
0x180028015  mov     [rbx+40h], eax
0x180028018  mov     [rbx+44h], ebp
0x18002801b  mov     rax, [rsp+78h+arg_20]
0x180028023  mov     [rbx+28h], rax
0x180028027  mov     [rbx+30h], r12
0x18002802b  mov     rax, [rsp+78h+arg_28]
0x180028033  mov     [rbx+88h], rax
0x18002803a  mov     rax, [rsp+78h+arg_0]
0x180028042  mov     [rbx+90h], rax
0x180028049  mov     qword ptr [rbx+48h], 0
0x180028051  xorps   xmm0, xmm0
0x180028054  xor     eax, eax
0x180028056  movups  xmmword ptr [rbx+68h], xmm0
0x18002805a  mov     [rbx+78h], rax
0x18002805e  movups  xmmword ptr [rbx+50h], xmm0
0x180028062  mov     [rbx+60h], rax
0x180028066  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18002806d  test    rax, rax
0x180028070  jz      short loc_180028077
0x180028072  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028077  mov     [rbx+80h], rax
0x18002807e  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180028085  test    rax, rax
0x180028088  jz      short loc_180028092
0x18002808a  mov     rcx, rbx
0x18002808d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028092  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180028099  test    rax, rax
0x18002809c  jz      short loc_1800280B4
0x18002809e  mov     r8d, 400h
0x1800280a4  mov     rdx, [rsp+78h+arg_60]
0x1800280ac  mov     rcx, rbx
0x1800280af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280b4  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800280bb  test    rax, rax
0x1800280be  jz      short loc_1800280C8
0x1800280c0  mov     rcx, rbx
0x1800280c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280c8  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800280cf  test    rax, rax
0x1800280d2  jz      short loc_1800280E2
0x1800280d4  test    byte ptr [rbx+4], 2
0x1800280d8  jnz     short loc_1800280E2
0x1800280da  mov     rcx, rbx
0x1800280dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800280e2  cmp     dword ptr [rbx+8], 0
0x1800280e6  jl      short loc_180028106
0x1800280e8  cmp     r15d, 3
0x1800280ec  jnz     loc_1800281D6
0x1800280f2  mov     dword ptr [rbx+8], 8000FFFFh
0x1800280f9  mov     ecx, 8000FFFFh; this
0x1800280fe  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180028103  mov     [rbx+0Ch], eax
0x180028106  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x18002810d  jnz     short loc_18002812E
0x18002810f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180028116  test    rax, rax
0x180028119  jz      short loc_180028124
0x18002811b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028120  test    al, al
0x180028122  jmp     short loc_18002812C
0x180028124  call    cs:__imp_IsDebuggerPresent
0x18002812a  test    eax, eax
0x18002812c  jz      short loc_180028134
0x18002812e  test    byte ptr [rbx+4], 2
0x180028132  jz      short loc_180028158
0x180028134  mov     rax, cs:g_pfnResultLoggingCallback
0x18002813b  test    rax, rax
0x18002813e  jz      short loc_18002819D
0x180028140  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180028147  jnz     short loc_18002819D
0x180028149  xor     r8d, r8d
0x18002814c  xor     edx, edx
0x18002814e  mov     rcx, rbx
0x180028151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028156  jmp     short loc_18002819D
0x180028158  mov     rax, cs:g_pfnResultLoggingCallback
0x18002815f  test    rax, rax
0x180028162  jz      short loc_18002817E
0x180028164  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18002816b  jnz     short loc_18002817E
0x18002816d  mov     r8d, 800h
0x180028173  mov     rdx, rsi
0x180028176  mov     rcx, rbx
0x180028179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002817e  cmp     word ptr [rsi], 0
0x180028182  jnz     short loc_180028194
0x180028184  mov     r8, rbx; unsigned __int64
0x180028187  mov     edx, 800h; unsigned __int16 *
0x18002818c  mov     rcx, rsi; pszDest
0x18002818f  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180028194  mov     rcx, rsi; lpOutputString
0x180028197  call    cs:__imp_OutputDebugStringW
0x18002819d  test    byte ptr [rbx+4], 4
0x1800281a1  jnz     short loc_1800281AC
0x1800281a3  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1800281aa  jz      short loc_1800281BE
0x1800281ac  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800281b3  test    rax, rax
0x1800281b6  jz      short loc_1800281BE
0x1800281b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800281bd  nop
0x1800281be  mov     rbx, [rsp+78h+arg_10]
0x1800281c6  add     rsp, 40h
0x1800281ca  pop     r15
0x1800281cc  pop     r14
0x1800281ce  pop     r13
0x1800281d0  pop     r12
0x1800281d2  pop     rdi
0x1800281d3  pop     rsi
0x1800281d4  pop     rbp
0x1800281d5  retn
0x1800281d6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
