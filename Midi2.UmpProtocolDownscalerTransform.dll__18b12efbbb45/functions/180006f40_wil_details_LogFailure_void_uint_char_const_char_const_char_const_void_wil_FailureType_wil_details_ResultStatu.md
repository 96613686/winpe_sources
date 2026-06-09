# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006f40`
- end: `0x180007239`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000436c`

## callees

- `0x180003db0`
- `0x180006474`
- `0x180006c14`
- `0x180006f40`
- `0x1800078b8`
- `0x1800078e0`
- `0x1800078f4`
- `0x180007910`
- `0x180009ac4`
- `0x180013010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007063`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007063`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007182`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007182`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800071f4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800071f4`

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
0x180006f40  mov     [rsp+arg_10], rbx
0x180006f45  mov     [rsp+arg_8], edx
0x180006f49  mov     [rsp+arg_0], rcx
0x180006f4e  push    rbp
0x180006f4f  push    rsi
0x180006f50  push    rdi
0x180006f51  push    r12
0x180006f53  push    r13
0x180006f55  push    r14
0x180006f57  push    r15
0x180006f59  sub     rsp, 40h
0x180006f5d  mov     r12, r9
0x180006f60  mov     r13, r8
0x180006f63  mov     r10, rcx
0x180006f66  xor     eax, eax
0x180006f68  mov     rsi, [rsp+78h+lpOutputString]
0x180006f70  mov     [rsi], ax
0x180006f73  mov     rax, [rsp+78h+arg_60]
0x180006f7b  mov     byte ptr [rax], 0
0x180006f7e  mov     r14, [rsp+78h+arg_38]
0x180006f86  mov     edi, [r14]
0x180006f89  mov     rbx, [rsp+78h+arg_78]
0x180006f91  mov     [rbx+8], edi
0x180006f94  mov     eax, [r14+4]
0x180006f98  mov     [rbx+0Ch], eax
0x180006f9b  xor     ebp, ebp
0x180006f9d  mov     r15d, [rsp+78h+arg_30]
0x180006fa5  mov     ecx, r15d
0x180006fa8  test    r15d, r15d
0x180006fab  jz      short loc_180007013
0x180006fad  sub     ecx, 1
0x180006fb0  jz      short loc_18000700A
0x180006fb2  sub     ecx, 1
0x180006fb5  jz      short loc_180006FC5
0x180006fb7  cmp     ecx, 1
0x180006fba  jnz     short loc_18000701C
0x180006fbc  mov     ecx, edi; this
0x180006fbe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006fc3  jmp     short loc_18000701A
0x180006fc5  test    edi, edi
0x180006fc7  js      short loc_180007001
0x180006fc9  mov     edi, 8007029Ch
0x180006fce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006fd2  mov     rax, [rsp+78h+arg_28]
0x180006fda  mov     [rsp+78h+var_50], rax; __int64
0x180006fdf  mov     rax, [rsp+78h+arg_20]
0x180006fe7  mov     [rsp+78h+var_58], rax; __int64
0x180006fec  mov     rcx, r10; int
0x180006fef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006ff4  mov     [rbx+8], edi
0x180006ff7  mov     ecx, edi; this
0x180006ff9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006ffe  mov     [rbx+0Ch], eax
0x180007001  mov     ecx, edi; this
0x180007003  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007008  jmp     short loc_18000701A
0x18000700a  mov     ecx, edi; this
0x18000700c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007011  jmp     short loc_18000701A
0x180007013  mov     ecx, edi; this
0x180007015  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000701a  mov     ebp, eax
0x18000701c  mov     [rbx], r15d
0x18000701f  mov     eax, [rsp+78h+arg_70]
0x180007026  mov     [rbx+4], eax
0x180007029  cmp     dword ptr [r14+8], 1
0x18000702e  jnz     short loc_180007036
0x180007030  or      eax, 8
0x180007033  mov     [rbx+4], eax
0x180007036  mov     eax, 1
0x18000703b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007043  inc     eax
0x180007045  mov     [rbx+10h], eax
0x180007048  mov     rax, [rsp+78h+arg_40]
0x180007050  xor     edi, edi
0x180007052  test    rax, rax
0x180007055  jz      short loc_18000705C
0x180007057  cmp     [rax], di
0x18000705a  jnz     short loc_18000705F
0x18000705c  mov     rax, rdi
0x18000705f  mov     [rbx+18h], rax
0x180007063  call    cs:__imp_GetCurrentThreadId
0x180007069  mov     [rbx+20h], eax
0x18000706c  mov     [rbx+38h], r13
0x180007070  mov     eax, [rsp+78h+arg_8]
0x180007077  mov     [rbx+40h], eax
0x18000707a  mov     [rbx+44h], ebp
0x18000707d  mov     rax, [rsp+78h+arg_20]
0x180007085  mov     [rbx+28h], rax
0x180007089  mov     [rbx+30h], r12
0x18000708d  mov     rax, [rsp+78h+arg_28]
0x180007095  mov     [rbx+88h], rax
0x18000709c  mov     rax, [rsp+78h+arg_0]
0x1800070a4  mov     [rbx+90h], rax
0x1800070ab  mov     [rbx+48h], rdi
0x1800070af  xorps   xmm0, xmm0
0x1800070b2  xor     eax, eax
0x1800070b4  movups  xmmword ptr [rbx+68h], xmm0
0x1800070b8  mov     [rbx+78h], rax
0x1800070bc  movups  xmmword ptr [rbx+50h], xmm0
0x1800070c0  mov     [rbx+60h], rax
0x1800070c4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800070cb  test    rax, rax
0x1800070ce  jz      short loc_1800070D7
0x1800070d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070d5  jmp     short loc_1800070DA
0x1800070d7  mov     rax, rdi
0x1800070da  mov     [rbx+80h], rax
0x1800070e1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800070e8  test    rax, rax
0x1800070eb  jz      short loc_1800070F5
0x1800070ed  mov     rcx, rbx
0x1800070f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070f5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800070fc  test    rax, rax
0x1800070ff  jz      short loc_180007117
0x180007101  mov     r8d, 400h
0x180007107  mov     rdx, [rsp+78h+arg_60]
0x18000710f  mov     rcx, rbx
0x180007112  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007117  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000711e  test    rax, rax
0x180007121  jz      short loc_18000712B
0x180007123  mov     rcx, rbx
0x180007126  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000712b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007132  test    rax, rax
0x180007135  jz      short loc_180007145
0x180007137  test    byte ptr [rbx+4], 2
0x18000713b  jnz     short loc_180007145
0x18000713d  mov     rcx, rbx
0x180007140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007145  cmp     [rbx+8], edi
0x180007148  jl      short loc_180007164
0x18000714a  cmp     r15d, 3
0x18000714e  jnz     loc_180007233
0x180007154  mov     ecx, 8000FFFFh; this
0x180007159  mov     [rbx+8], ecx
0x18000715c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007161  mov     [rbx+0Ch], eax
0x180007164  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000716b  jnz     short loc_18000718C
0x18000716d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007174  test    rax, rax
0x180007177  jz      short loc_180007182
0x180007179  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000717e  test    al, al
0x180007180  jmp     short loc_18000718A
0x180007182  call    cs:__imp_IsDebuggerPresent
0x180007188  test    eax, eax
0x18000718a  jz      short loc_180007192
0x18000718c  test    byte ptr [rbx+4], 2
0x180007190  jz      short loc_1800071B6
0x180007192  mov     rax, cs:g_pfnResultLoggingCallback
0x180007199  test    rax, rax
0x18000719c  jz      short loc_1800071FA
0x18000719e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800071a5  jnz     short loc_1800071FA
0x1800071a7  xor     r8d, r8d
0x1800071aa  xor     edx, edx
0x1800071ac  mov     rcx, rbx
0x1800071af  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b4  jmp     short loc_1800071FA
0x1800071b6  mov     ebp, 800h
0x1800071bb  mov     rax, cs:g_pfnResultLoggingCallback
0x1800071c2  test    rax, rax
0x1800071c5  jz      short loc_1800071DE
0x1800071c7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800071ce  jnz     short loc_1800071DE
0x1800071d0  mov     r8d, ebp
0x1800071d3  mov     rdx, rsi
0x1800071d6  mov     rcx, rbx
0x1800071d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071de  cmp     [rsi], di
0x1800071e1  jnz     short loc_1800071F1
0x1800071e3  mov     r8, rbx; unsigned __int64
0x1800071e6  mov     rdx, rbp; unsigned __int16 *
0x1800071e9  mov     rcx, rsi; this
0x1800071ec  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800071f1  mov     rcx, rsi; lpOutputString
0x1800071f4  call    cs:__imp_OutputDebugStringW
0x1800071fa  test    byte ptr [rbx+4], 4
0x1800071fe  jnz     short loc_180007209
0x180007200  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007207  jz      short loc_18000721B
0x180007209  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007210  test    rax, rax
0x180007213  jz      short loc_18000721B
0x180007215  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000721a  nop
0x18000721b  mov     rbx, [rsp+78h+arg_10]
0x180007223  add     rsp, 40h
0x180007227  pop     r15
0x180007229  pop     r14
0x18000722b  pop     r13
0x18000722d  pop     r12
0x18000722f  pop     rdi
0x180007230  pop     rsi
0x180007231  pop     rbp
0x180007232  retn
0x180007233  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
