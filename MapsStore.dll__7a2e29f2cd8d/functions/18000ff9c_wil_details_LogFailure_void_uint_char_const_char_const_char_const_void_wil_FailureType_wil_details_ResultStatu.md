# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000ff9c`
- end: `0x180010295`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x18000e6c8`
- `0x18000ea14`
- `0x1800142f4`

## callees

- `0x18000e608`
- `0x18000f604`
- `0x18000fdd8`
- `0x18000ff9c`
- `0x18001065c`
- `0x180010680`
- `0x180010694`
- `0x1800106b0`
- `0x1800113c0`
- `0x180098010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800100bf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800100bf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010250`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010250`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800101de`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800101de`

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
0x18000ff9c  mov     [rsp+arg_10], rbx
0x18000ffa1  mov     [rsp+arg_8], edx
0x18000ffa5  mov     [rsp+arg_0], rcx
0x18000ffaa  push    rbp
0x18000ffab  push    rsi
0x18000ffac  push    rdi
0x18000ffad  push    r12
0x18000ffaf  push    r13
0x18000ffb1  push    r14
0x18000ffb3  push    r15
0x18000ffb5  sub     rsp, 40h
0x18000ffb9  mov     r12, r9
0x18000ffbc  mov     r13, r8
0x18000ffbf  mov     r10, rcx
0x18000ffc2  xor     eax, eax
0x18000ffc4  mov     rsi, [rsp+78h+lpOutputString]
0x18000ffcc  mov     [rsi], ax
0x18000ffcf  mov     rax, [rsp+78h+arg_60]
0x18000ffd7  mov     byte ptr [rax], 0
0x18000ffda  mov     r14, [rsp+78h+arg_38]
0x18000ffe2  mov     edi, [r14]
0x18000ffe5  mov     rbx, [rsp+78h+arg_78]
0x18000ffed  mov     [rbx+8], edi
0x18000fff0  mov     eax, [r14+4]
0x18000fff4  mov     [rbx+0Ch], eax
0x18000fff7  xor     ebp, ebp
0x18000fff9  mov     r15d, [rsp+78h+arg_30]
0x180010001  mov     ecx, r15d
0x180010004  test    r15d, r15d
0x180010007  jz      short loc_18001006F
0x180010009  sub     ecx, 1
0x18001000c  jz      short loc_180010066
0x18001000e  sub     ecx, 1
0x180010011  jz      short loc_180010021
0x180010013  cmp     ecx, 1
0x180010016  jnz     short loc_180010078
0x180010018  mov     ecx, edi; this
0x18001001a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001001f  jmp     short loc_180010076
0x180010021  test    edi, edi
0x180010023  js      short loc_18001005D
0x180010025  mov     edi, 8007029Ch
0x18001002a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001002e  mov     rax, [rsp+78h+arg_28]
0x180010036  mov     [rsp+78h+var_50], rax; __int64
0x18001003b  mov     rax, [rsp+78h+arg_20]
0x180010043  mov     [rsp+78h+var_58], rax; __int64
0x180010048  mov     rcx, r10; int
0x18001004b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180010050  mov     [rbx+8], edi
0x180010053  mov     ecx, edi; this
0x180010055  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001005a  mov     [rbx+0Ch], eax
0x18001005d  mov     ecx, edi; this
0x18001005f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180010064  jmp     short loc_180010076
0x180010066  mov     ecx, edi; this
0x180010068  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001006d  jmp     short loc_180010076
0x18001006f  mov     ecx, edi; this
0x180010071  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180010076  mov     ebp, eax
0x180010078  mov     [rbx], r15d
0x18001007b  mov     eax, [rsp+78h+arg_70]
0x180010082  mov     [rbx+4], eax
0x180010085  cmp     dword ptr [r14+8], 1
0x18001008a  jnz     short loc_180010092
0x18001008c  or      eax, 8
0x18001008f  mov     [rbx+4], eax
0x180010092  mov     eax, 1
0x180010097  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001009f  inc     eax
0x1800100a1  mov     [rbx+10h], eax
0x1800100a4  mov     rax, [rsp+78h+arg_40]
0x1800100ac  xor     edi, edi
0x1800100ae  test    rax, rax
0x1800100b1  jz      short loc_1800100B8
0x1800100b3  cmp     [rax], di
0x1800100b6  jnz     short loc_1800100BB
0x1800100b8  mov     rax, rdi
0x1800100bb  mov     [rbx+18h], rax
0x1800100bf  call    cs:__imp_GetCurrentThreadId
0x1800100c5  mov     [rbx+20h], eax
0x1800100c8  mov     [rbx+38h], r13
0x1800100cc  mov     eax, [rsp+78h+arg_8]
0x1800100d3  mov     [rbx+40h], eax
0x1800100d6  mov     [rbx+44h], ebp
0x1800100d9  mov     rax, [rsp+78h+arg_20]
0x1800100e1  mov     [rbx+28h], rax
0x1800100e5  mov     [rbx+30h], r12
0x1800100e9  mov     rax, [rsp+78h+arg_28]
0x1800100f1  mov     [rbx+88h], rax
0x1800100f8  mov     rax, [rsp+78h+arg_0]
0x180010100  mov     [rbx+90h], rax
0x180010107  mov     [rbx+48h], rdi
0x18001010b  xorps   xmm0, xmm0
0x18001010e  xor     eax, eax
0x180010110  movups  xmmword ptr [rbx+68h], xmm0
0x180010114  mov     [rbx+78h], rax
0x180010118  movups  xmmword ptr [rbx+50h], xmm0
0x18001011c  mov     [rbx+60h], rax
0x180010120  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010127  test    rax, rax
0x18001012a  jz      short loc_180010133
0x18001012c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010131  jmp     short loc_180010136
0x180010133  mov     rax, rdi
0x180010136  mov     [rbx+80h], rax
0x18001013d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010144  test    rax, rax
0x180010147  jz      short loc_180010151
0x180010149  mov     rcx, rbx
0x18001014c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010151  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010158  test    rax, rax
0x18001015b  jz      short loc_180010173
0x18001015d  mov     r8d, 400h
0x180010163  mov     rdx, [rsp+78h+arg_60]
0x18001016b  mov     rcx, rbx
0x18001016e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010173  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001017a  test    rax, rax
0x18001017d  jz      short loc_180010187
0x18001017f  mov     rcx, rbx
0x180010182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010187  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001018e  test    rax, rax
0x180010191  jz      short loc_1800101A1
0x180010193  test    byte ptr [rbx+4], 2
0x180010197  jnz     short loc_1800101A1
0x180010199  mov     rcx, rbx
0x18001019c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101a1  cmp     [rbx+8], edi
0x1800101a4  jl      short loc_1800101C0
0x1800101a6  cmp     r15d, 3
0x1800101aa  jnz     loc_18001028F
0x1800101b0  mov     ecx, 8000FFFFh; this
0x1800101b5  mov     [rbx+8], ecx
0x1800101b8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800101bd  mov     [rbx+0Ch], eax
0x1800101c0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800101c7  jnz     short loc_1800101E8
0x1800101c9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800101d0  test    rax, rax
0x1800101d3  jz      short loc_1800101DE
0x1800101d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800101da  test    al, al
0x1800101dc  jmp     short loc_1800101E6
0x1800101de  call    cs:__imp_IsDebuggerPresent
0x1800101e4  test    eax, eax
0x1800101e6  jz      short loc_1800101EE
0x1800101e8  test    byte ptr [rbx+4], 2
0x1800101ec  jz      short loc_180010212
0x1800101ee  mov     rax, cs:g_pfnResultLoggingCallback
0x1800101f5  test    rax, rax
0x1800101f8  jz      short loc_180010256
0x1800101fa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010201  jnz     short loc_180010256
0x180010203  xor     r8d, r8d
0x180010206  xor     edx, edx
0x180010208  mov     rcx, rbx
0x18001020b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010210  jmp     short loc_180010256
0x180010212  mov     ebp, 800h
0x180010217  mov     rax, cs:g_pfnResultLoggingCallback
0x18001021e  test    rax, rax
0x180010221  jz      short loc_18001023A
0x180010223  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001022a  jnz     short loc_18001023A
0x18001022c  mov     r8d, ebp
0x18001022f  mov     rdx, rsi
0x180010232  mov     rcx, rbx
0x180010235  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001023a  cmp     [rsi], di
0x18001023d  jnz     short loc_18001024D
0x18001023f  mov     r8, rbx; unsigned __int64
0x180010242  mov     rdx, rbp; unsigned __int16 *
0x180010245  mov     rcx, rsi; this
0x180010248  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001024d  mov     rcx, rsi; lpOutputString
0x180010250  call    cs:__imp_OutputDebugStringW
0x180010256  test    byte ptr [rbx+4], 4
0x18001025a  jnz     short loc_180010265
0x18001025c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180010263  jz      short loc_180010277
0x180010265  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001026c  test    rax, rax
0x18001026f  jz      short loc_180010277
0x180010271  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010276  nop
0x180010277  mov     rbx, [rsp+78h+arg_10]
0x18001027f  add     rsp, 40h
0x180010283  pop     r15
0x180010285  pop     r14
0x180010287  pop     r13
0x180010289  pop     r12
0x18001028b  pop     rdi
0x18001028c  pop     rsi
0x18001028d  pop     rbp
0x18001028e  retn
0x18001028f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
