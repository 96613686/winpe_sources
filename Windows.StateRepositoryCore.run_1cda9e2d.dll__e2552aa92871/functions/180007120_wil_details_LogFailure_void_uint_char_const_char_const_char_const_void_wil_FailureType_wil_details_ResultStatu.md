# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007120`
- end: `0x180007419`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180003164`
- `0x1800034a8`

## callees

- `0x1800030a4`
- `0x1800064b4`
- `0x180006d20`
- `0x180007120`
- `0x180008098`
- `0x1800080c0`
- `0x18000820c`
- `0x180008228`
- `0x18000a884`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007243`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007243`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800073d4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800073d4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007362`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007362`

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
0x180007120  mov     [rsp+arg_10], rbx
0x180007125  mov     [rsp+arg_8], edx
0x180007129  mov     [rsp+arg_0], rcx
0x18000712e  push    rbp
0x18000712f  push    rsi
0x180007130  push    rdi
0x180007131  push    r12
0x180007133  push    r13
0x180007135  push    r14
0x180007137  push    r15
0x180007139  sub     rsp, 40h
0x18000713d  mov     r12, r9
0x180007140  mov     r13, r8
0x180007143  mov     r10, rcx
0x180007146  xor     eax, eax
0x180007148  mov     rsi, [rsp+78h+lpOutputString]
0x180007150  mov     [rsi], ax
0x180007153  mov     rax, [rsp+78h+arg_60]
0x18000715b  mov     byte ptr [rax], 0
0x18000715e  mov     r14, [rsp+78h+arg_38]
0x180007166  mov     edi, [r14]
0x180007169  mov     rbx, [rsp+78h+arg_78]
0x180007171  mov     [rbx+8], edi
0x180007174  mov     eax, [r14+4]
0x180007178  mov     [rbx+0Ch], eax
0x18000717b  xor     ebp, ebp
0x18000717d  mov     r15d, [rsp+78h+arg_30]
0x180007185  mov     ecx, r15d
0x180007188  test    r15d, r15d
0x18000718b  jz      short loc_1800071F3
0x18000718d  sub     ecx, 1
0x180007190  jz      short loc_1800071EA
0x180007192  sub     ecx, 1
0x180007195  jz      short loc_1800071A5
0x180007197  cmp     ecx, 1
0x18000719a  jnz     short loc_1800071FC
0x18000719c  mov     ecx, edi; this
0x18000719e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800071a3  jmp     short loc_1800071FA
0x1800071a5  test    edi, edi
0x1800071a7  js      short loc_1800071E1
0x1800071a9  mov     edi, 8007029Ch
0x1800071ae  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800071b2  mov     rax, [rsp+78h+arg_28]
0x1800071ba  mov     [rsp+78h+var_50], rax; __int64
0x1800071bf  mov     rax, [rsp+78h+arg_20]
0x1800071c7  mov     [rsp+78h+var_58], rax; __int64
0x1800071cc  mov     rcx, r10; int
0x1800071cf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800071d4  mov     [rbx+8], edi
0x1800071d7  mov     ecx, edi; this
0x1800071d9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800071de  mov     [rbx+0Ch], eax
0x1800071e1  mov     ecx, edi; this
0x1800071e3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800071e8  jmp     short loc_1800071FA
0x1800071ea  mov     ecx, edi; this
0x1800071ec  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800071f1  jmp     short loc_1800071FA
0x1800071f3  mov     ecx, edi; this
0x1800071f5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800071fa  mov     ebp, eax
0x1800071fc  mov     [rbx], r15d
0x1800071ff  mov     eax, [rsp+78h+arg_70]
0x180007206  mov     [rbx+4], eax
0x180007209  cmp     dword ptr [r14+8], 1
0x18000720e  jnz     short loc_180007216
0x180007210  or      eax, 8
0x180007213  mov     [rbx+4], eax
0x180007216  mov     eax, 1
0x18000721b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007223  inc     eax
0x180007225  mov     [rbx+10h], eax
0x180007228  mov     rax, [rsp+78h+arg_40]
0x180007230  xor     edi, edi
0x180007232  test    rax, rax
0x180007235  jz      short loc_18000723C
0x180007237  cmp     [rax], di
0x18000723a  jnz     short loc_18000723F
0x18000723c  mov     rax, rdi
0x18000723f  mov     [rbx+18h], rax
0x180007243  call    cs:__imp_GetCurrentThreadId
0x180007249  mov     [rbx+20h], eax
0x18000724c  mov     [rbx+38h], r13
0x180007250  mov     eax, [rsp+78h+arg_8]
0x180007257  mov     [rbx+40h], eax
0x18000725a  mov     [rbx+44h], ebp
0x18000725d  mov     rax, [rsp+78h+arg_20]
0x180007265  mov     [rbx+28h], rax
0x180007269  mov     [rbx+30h], r12
0x18000726d  mov     rax, [rsp+78h+arg_28]
0x180007275  mov     [rbx+88h], rax
0x18000727c  mov     rax, [rsp+78h+arg_0]
0x180007284  mov     [rbx+90h], rax
0x18000728b  mov     [rbx+48h], rdi
0x18000728f  xorps   xmm0, xmm0
0x180007292  xor     eax, eax
0x180007294  movups  xmmword ptr [rbx+68h], xmm0
0x180007298  mov     [rbx+78h], rax
0x18000729c  movups  xmmword ptr [rbx+50h], xmm0
0x1800072a0  mov     [rbx+60h], rax
0x1800072a4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800072ab  test    rax, rax
0x1800072ae  jz      short loc_1800072B7
0x1800072b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072b5  jmp     short loc_1800072BA
0x1800072b7  mov     rax, rdi
0x1800072ba  mov     [rbx+80h], rax
0x1800072c1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800072c8  test    rax, rax
0x1800072cb  jz      short loc_1800072D5
0x1800072cd  mov     rcx, rbx
0x1800072d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072d5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800072dc  test    rax, rax
0x1800072df  jz      short loc_1800072F7
0x1800072e1  mov     r8d, 400h
0x1800072e7  mov     rdx, [rsp+78h+arg_60]
0x1800072ef  mov     rcx, rbx
0x1800072f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072f7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800072fe  test    rax, rax
0x180007301  jz      short loc_18000730B
0x180007303  mov     rcx, rbx
0x180007306  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000730b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007312  test    rax, rax
0x180007315  jz      short loc_180007325
0x180007317  test    byte ptr [rbx+4], 2
0x18000731b  jnz     short loc_180007325
0x18000731d  mov     rcx, rbx
0x180007320  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007325  cmp     [rbx+8], edi
0x180007328  jl      short loc_180007344
0x18000732a  cmp     r15d, 3
0x18000732e  jnz     loc_180007413
0x180007334  mov     ecx, 8000FFFFh; this
0x180007339  mov     [rbx+8], ecx
0x18000733c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007341  mov     [rbx+0Ch], eax
0x180007344  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000734b  jnz     short loc_18000736C
0x18000734d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007354  test    rax, rax
0x180007357  jz      short loc_180007362
0x180007359  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000735e  test    al, al
0x180007360  jmp     short loc_18000736A
0x180007362  call    cs:__imp_IsDebuggerPresent
0x180007368  test    eax, eax
0x18000736a  jz      short loc_180007372
0x18000736c  test    byte ptr [rbx+4], 2
0x180007370  jz      short loc_180007396
0x180007372  mov     rax, cs:g_pfnResultLoggingCallback
0x180007379  test    rax, rax
0x18000737c  jz      short loc_1800073DA
0x18000737e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007385  jnz     short loc_1800073DA
0x180007387  xor     r8d, r8d
0x18000738a  xor     edx, edx
0x18000738c  mov     rcx, rbx
0x18000738f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007394  jmp     short loc_1800073DA
0x180007396  mov     ebp, 800h
0x18000739b  mov     rax, cs:g_pfnResultLoggingCallback
0x1800073a2  test    rax, rax
0x1800073a5  jz      short loc_1800073BE
0x1800073a7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800073ae  jnz     short loc_1800073BE
0x1800073b0  mov     r8d, ebp
0x1800073b3  mov     rdx, rsi
0x1800073b6  mov     rcx, rbx
0x1800073b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073be  cmp     [rsi], di
0x1800073c1  jnz     short loc_1800073D1
0x1800073c3  mov     r8, rbx; unsigned __int64
0x1800073c6  mov     rdx, rbp; unsigned __int16 *
0x1800073c9  mov     rcx, rsi; this
0x1800073cc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800073d1  mov     rcx, rsi; lpOutputString
0x1800073d4  call    cs:__imp_OutputDebugStringW
0x1800073da  test    byte ptr [rbx+4], 4
0x1800073de  jnz     short loc_1800073E9
0x1800073e0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800073e7  jz      short loc_1800073FB
0x1800073e9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800073f0  test    rax, rax
0x1800073f3  jz      short loc_1800073FB
0x1800073f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073fa  nop
0x1800073fb  mov     rbx, [rsp+78h+arg_10]
0x180007403  add     rsp, 40h
0x180007407  pop     r15
0x180007409  pop     r14
0x18000740b  pop     r13
0x18000740d  pop     r12
0x18000740f  pop     rdi
0x180007410  pop     rsi
0x180007411  pop     rbp
0x180007412  retn
0x180007413  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
