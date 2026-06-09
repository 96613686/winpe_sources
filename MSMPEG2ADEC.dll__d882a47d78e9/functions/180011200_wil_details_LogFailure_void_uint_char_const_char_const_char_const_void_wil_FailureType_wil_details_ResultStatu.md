# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011200`
- end: `0x180011518`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `792`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180009ec0`

## callees

- `0x180009860`
- `0x18000eb60`
- `0x180010630`
- `0x180011200`
- `0x180013380`
- `0x1800133a0`
- `0x1800133c0`
- `0x1800133e0`
- `0x1800187e0`
- `0x180088750`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011321`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011321`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011450`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011450`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800114cb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800114cb`

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
  __int64 (__fastcall *ModuleName)(_QWORD); // rax
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
    ModuleName = (__int64 (__fastcall *)(_QWORD))wil::details::g_pfnGetModuleName(v24);
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
0x180011200  mov     [rsp+arg_10], rbx
0x180011205  mov     [rsp+arg_8], edx
0x180011209  mov     [rsp+arg_0], rcx
0x18001120e  push    rbp
0x18001120f  push    rsi
0x180011210  push    rdi
0x180011211  push    r12
0x180011213  push    r13
0x180011215  push    r14
0x180011217  push    r15
0x180011219  sub     rsp, 40h
0x18001121d  mov     r12, r9
0x180011220  mov     r13, r8
0x180011223  mov     r10, rcx
0x180011226  xor     eax, eax
0x180011228  mov     rsi, [rsp+78h+lpOutputString]
0x180011230  mov     [rsi], ax
0x180011233  mov     rax, [rsp+78h+arg_60]
0x18001123b  mov     byte ptr [rax], 0
0x18001123e  mov     r14, [rsp+78h+arg_38]
0x180011246  mov     edi, [r14]
0x180011249  mov     rbx, [rsp+78h+arg_78]
0x180011251  mov     [rbx+8], edi
0x180011254  mov     eax, [r14+4]
0x180011258  mov     [rbx+0Ch], eax
0x18001125b  xor     ebp, ebp
0x18001125d  mov     r15d, [rsp+78h+arg_30]
0x180011265  mov     ecx, r15d
0x180011268  test    r15d, r15d
0x18001126b  jz      short loc_1800112D3
0x18001126d  sub     ecx, 1
0x180011270  jz      short loc_1800112CA
0x180011272  sub     ecx, 1
0x180011275  jz      short loc_180011285
0x180011277  cmp     ecx, 1
0x18001127a  jnz     short loc_1800112DC
0x18001127c  mov     ecx, edi; this
0x18001127e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180011283  jmp     short loc_1800112DA
0x180011285  test    edi, edi
0x180011287  js      short loc_1800112C1
0x180011289  mov     edi, 8007029Ch
0x18001128e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011292  mov     rax, [rsp+78h+arg_28]
0x18001129a  mov     [rsp+78h+var_50], rax; __int64
0x18001129f  mov     rax, [rsp+78h+arg_20]
0x1800112a7  mov     [rsp+78h+var_58], rax; __int64
0x1800112ac  mov     rcx, r10; int
0x1800112af  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800112b4  mov     [rbx+8], edi
0x1800112b7  mov     ecx, edi; this
0x1800112b9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800112be  mov     [rbx+0Ch], eax
0x1800112c1  mov     ecx, edi; this
0x1800112c3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800112c8  jmp     short loc_1800112DA
0x1800112ca  mov     ecx, edi; this
0x1800112cc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800112d1  jmp     short loc_1800112DA
0x1800112d3  mov     ecx, edi; this
0x1800112d5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800112da  mov     ebp, eax
0x1800112dc  mov     [rbx], r15d
0x1800112df  mov     eax, [rsp+78h+arg_70]
0x1800112e6  mov     [rbx+4], eax
0x1800112e9  cmp     dword ptr [r14+8], 1
0x1800112ee  jnz     short loc_1800112F6
0x1800112f0  or      eax, 8
0x1800112f3  mov     [rbx+4], eax
0x1800112f6  mov     eax, 1
0x1800112fb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011303  inc     eax
0x180011305  mov     [rbx+10h], eax
0x180011308  mov     rax, [rsp+78h+arg_40]
0x180011310  test    rax, rax
0x180011313  jz      short loc_18001131B
0x180011315  cmp     word ptr [rax], 0
0x180011319  jnz     short loc_18001131D
0x18001131b  xor     eax, eax
0x18001131d  mov     [rbx+18h], rax
0x180011321  call    cs:__imp_GetCurrentThreadId
0x180011328  nop     dword ptr [rax+rax+00h]
0x18001132d  mov     [rbx+20h], eax
0x180011330  mov     [rbx+38h], r13
0x180011334  mov     eax, [rsp+78h+arg_8]
0x18001133b  mov     [rbx+40h], eax
0x18001133e  mov     [rbx+44h], ebp
0x180011341  mov     rax, [rsp+78h+arg_20]
0x180011349  mov     [rbx+28h], rax
0x18001134d  mov     [rbx+30h], r12
0x180011351  mov     rax, [rsp+78h+arg_28]
0x180011359  mov     [rbx+88h], rax
0x180011360  mov     rax, [rsp+78h+arg_0]
0x180011368  mov     [rbx+90h], rax
0x18001136f  mov     qword ptr [rbx+48h], 0
0x180011377  xorps   xmm0, xmm0
0x18001137a  xor     eax, eax
0x18001137c  movups  xmmword ptr [rbx+68h], xmm0
0x180011380  mov     [rbx+78h], rax
0x180011384  movups  xmmword ptr [rbx+50h], xmm0
0x180011388  mov     [rbx+60h], rax
0x18001138c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011393  test    rax, rax
0x180011396  jz      short loc_18001139E
0x180011398  call    cs:__guard_dispatch_icall_fptr
0x18001139e  mov     [rbx+80h], rax
0x1800113a5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800113ac  test    rax, rax
0x1800113af  jz      short loc_1800113BA
0x1800113b1  mov     rcx, rbx
0x1800113b4  call    cs:__guard_dispatch_icall_fptr
0x1800113ba  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800113c1  test    rax, rax
0x1800113c4  jz      short loc_1800113DD
0x1800113c6  mov     r8d, 400h
0x1800113cc  mov     rdx, [rsp+78h+arg_60]
0x1800113d4  mov     rcx, rbx
0x1800113d7  call    cs:__guard_dispatch_icall_fptr
0x1800113dd  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800113e4  test    rax, rax
0x1800113e7  jz      short loc_1800113F2
0x1800113e9  mov     rcx, rbx
0x1800113ec  call    cs:__guard_dispatch_icall_fptr
0x1800113f2  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800113f9  test    rax, rax
0x1800113fc  jz      short loc_18001140D
0x1800113fe  test    byte ptr [rbx+4], 2
0x180011402  jnz     short loc_18001140D
0x180011404  mov     rcx, rbx
0x180011407  call    cs:__guard_dispatch_icall_fptr
0x18001140d  cmp     dword ptr [rbx+8], 0
0x180011411  jl      short loc_180011431
0x180011413  cmp     r15d, 3
0x180011417  jnz     loc_180011512
0x18001141d  mov     dword ptr [rbx+8], 8000FFFFh
0x180011424  mov     ecx, 8000FFFFh; this
0x180011429  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001142e  mov     [rbx+0Ch], eax
0x180011431  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, 0; bool wil::g_fIsDebuggerPresent
0x180011438  jnz     short loc_180011460
0x18001143a  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011441  test    rax, rax
0x180011444  jz      short loc_180011450
0x180011446  call    cs:__guard_dispatch_icall_fptr
0x18001144c  test    al, al
0x18001144e  jmp     short loc_18001145E
0x180011450  call    cs:__imp_IsDebuggerPresent
0x180011457  nop     dword ptr [rax+rax+00h]
0x18001145c  test    eax, eax
0x18001145e  jz      short loc_180011466
0x180011460  test    byte ptr [rbx+4], 2
0x180011464  jz      short loc_18001148B
0x180011466  mov     rax, cs:g_pfnResultLoggingCallback
0x18001146d  test    rax, rax
0x180011470  jz      short loc_1800114D7
0x180011472  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x180011479  jnz     short loc_1800114D7
0x18001147b  xor     r8d, r8d
0x18001147e  xor     edx, edx
0x180011480  mov     rcx, rbx
0x180011483  call    cs:__guard_dispatch_icall_fptr
0x180011489  jmp     short loc_1800114D7
0x18001148b  mov     rax, cs:g_pfnResultLoggingCallback
0x180011492  test    rax, rax
0x180011495  jz      short loc_1800114B2
0x180011497  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, 0; bool wil::details::g_resultMessageCallbackSet
0x18001149e  jnz     short loc_1800114B2
0x1800114a0  mov     r8d, 800h
0x1800114a6  mov     rdx, rsi
0x1800114a9  mov     rcx, rbx
0x1800114ac  call    cs:__guard_dispatch_icall_fptr
0x1800114b2  cmp     word ptr [rsi], 0
0x1800114b6  jnz     short loc_1800114C8
0x1800114b8  mov     r8, rbx; unsigned __int64
0x1800114bb  mov     edx, 800h; unsigned __int16 *
0x1800114c0  mov     rcx, rsi; this
0x1800114c3  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800114c8  mov     rcx, rsi; lpOutputString
0x1800114cb  call    cs:__imp_OutputDebugStringW
0x1800114d2  nop     dword ptr [rax+rax+00h]
0x1800114d7  test    byte ptr [rbx+4], 4
0x1800114db  jnz     short loc_1800114E6
0x1800114dd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, 0; bool wil::g_fBreakOnFailure
0x1800114e4  jz      short loc_1800114F9
0x1800114e6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800114ed  test    rax, rax
0x1800114f0  jz      short loc_1800114F9
0x1800114f2  call    cs:__guard_dispatch_icall_fptr
0x1800114f8  nop
0x1800114f9  mov     rbx, [rsp+78h+arg_10]
0x180011501  add     rsp, 40h
0x180011505  pop     r15
0x180011507  pop     r14
0x180011509  pop     r13
0x18001150b  pop     r12
0x18001150d  pop     rdi
0x18001150e  pop     rsi
0x18001150f  pop     rbp
0x180011510  retn
0x180011512  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
