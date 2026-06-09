# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140006fb0`
- end: `0x1400072a9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140004620`

## callees

- `0x140004064`
- `0x140006464`
- `0x140006dc0`
- `0x140006fb0`
- `0x140007888`
- `0x1400078b0`
- `0x1400078c4`
- `0x1400078e0`
- `0x1400093e8`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400070d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400070d3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007264`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140007264`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400071f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400071f2`

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
0x140006fb0  mov     [rsp+arg_10], rbx
0x140006fb5  mov     [rsp+arg_8], edx
0x140006fb9  mov     [rsp+arg_0], rcx
0x140006fbe  push    rbp
0x140006fbf  push    rsi
0x140006fc0  push    rdi
0x140006fc1  push    r12
0x140006fc3  push    r13
0x140006fc5  push    r14
0x140006fc7  push    r15
0x140006fc9  sub     rsp, 40h
0x140006fcd  mov     r12, r9
0x140006fd0  mov     r13, r8
0x140006fd3  mov     r10, rcx
0x140006fd6  xor     eax, eax
0x140006fd8  mov     rsi, [rsp+78h+lpOutputString]
0x140006fe0  mov     [rsi], ax
0x140006fe3  mov     rax, [rsp+78h+arg_60]
0x140006feb  mov     byte ptr [rax], 0
0x140006fee  mov     r14, [rsp+78h+arg_38]
0x140006ff6  mov     edi, [r14]
0x140006ff9  mov     rbx, [rsp+78h+arg_78]
0x140007001  mov     [rbx+8], edi
0x140007004  mov     eax, [r14+4]
0x140007008  mov     [rbx+0Ch], eax
0x14000700b  xor     ebp, ebp
0x14000700d  mov     r15d, [rsp+78h+arg_30]
0x140007015  mov     ecx, r15d
0x140007018  test    r15d, r15d
0x14000701b  jz      short loc_140007083
0x14000701d  sub     ecx, 1
0x140007020  jz      short loc_14000707A
0x140007022  sub     ecx, 1
0x140007025  jz      short loc_140007035
0x140007027  cmp     ecx, 1
0x14000702a  jnz     short loc_14000708C
0x14000702c  mov     ecx, edi; this
0x14000702e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140007033  jmp     short loc_14000708A
0x140007035  test    edi, edi
0x140007037  js      short loc_140007071
0x140007039  mov     edi, 8007029Ch
0x14000703e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140007042  mov     rax, [rsp+78h+arg_28]
0x14000704a  mov     [rsp+78h+var_50], rax; __int64
0x14000704f  mov     rax, [rsp+78h+arg_20]
0x140007057  mov     [rsp+78h+var_58], rax; __int64
0x14000705c  mov     rcx, r10; int
0x14000705f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140007064  mov     [rbx+8], edi
0x140007067  mov     ecx, edi; this
0x140007069  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000706e  mov     [rbx+0Ch], eax
0x140007071  mov     ecx, edi; this
0x140007073  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140007078  jmp     short loc_14000708A
0x14000707a  mov     ecx, edi; this
0x14000707c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140007081  jmp     short loc_14000708A
0x140007083  mov     ecx, edi; this
0x140007085  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000708a  mov     ebp, eax
0x14000708c  mov     [rbx], r15d
0x14000708f  mov     eax, [rsp+78h+arg_70]
0x140007096  mov     [rbx+4], eax
0x140007099  cmp     dword ptr [r14+8], 1
0x14000709e  jnz     short loc_1400070A6
0x1400070a0  or      eax, 8
0x1400070a3  mov     [rbx+4], eax
0x1400070a6  mov     eax, 1
0x1400070ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400070b3  inc     eax
0x1400070b5  mov     [rbx+10h], eax
0x1400070b8  mov     rax, [rsp+78h+arg_40]
0x1400070c0  xor     edi, edi
0x1400070c2  test    rax, rax
0x1400070c5  jz      short loc_1400070CC
0x1400070c7  cmp     [rax], di
0x1400070ca  jnz     short loc_1400070CF
0x1400070cc  mov     rax, rdi
0x1400070cf  mov     [rbx+18h], rax
0x1400070d3  call    cs:__imp_GetCurrentThreadId
0x1400070d9  mov     [rbx+20h], eax
0x1400070dc  mov     [rbx+38h], r13
0x1400070e0  mov     eax, [rsp+78h+arg_8]
0x1400070e7  mov     [rbx+40h], eax
0x1400070ea  mov     [rbx+44h], ebp
0x1400070ed  mov     rax, [rsp+78h+arg_20]
0x1400070f5  mov     [rbx+28h], rax
0x1400070f9  mov     [rbx+30h], r12
0x1400070fd  mov     rax, [rsp+78h+arg_28]
0x140007105  mov     [rbx+88h], rax
0x14000710c  mov     rax, [rsp+78h+arg_0]
0x140007114  mov     [rbx+90h], rax
0x14000711b  mov     [rbx+48h], rdi
0x14000711f  xorps   xmm0, xmm0
0x140007122  xor     eax, eax
0x140007124  movups  xmmword ptr [rbx+68h], xmm0
0x140007128  mov     [rbx+78h], rax
0x14000712c  movups  xmmword ptr [rbx+50h], xmm0
0x140007130  mov     [rbx+60h], rax
0x140007134  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000713b  test    rax, rax
0x14000713e  jz      short loc_140007147
0x140007140  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007145  jmp     short loc_14000714A
0x140007147  mov     rax, rdi
0x14000714a  mov     [rbx+80h], rax
0x140007151  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140007158  test    rax, rax
0x14000715b  jz      short loc_140007165
0x14000715d  mov     rcx, rbx
0x140007160  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007165  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000716c  test    rax, rax
0x14000716f  jz      short loc_140007187
0x140007171  mov     r8d, 400h
0x140007177  mov     rdx, [rsp+78h+arg_60]
0x14000717f  mov     rcx, rbx
0x140007182  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007187  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000718e  test    rax, rax
0x140007191  jz      short loc_14000719B
0x140007193  mov     rcx, rbx
0x140007196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000719b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1400071a2  test    rax, rax
0x1400071a5  jz      short loc_1400071B5
0x1400071a7  test    byte ptr [rbx+4], 2
0x1400071ab  jnz     short loc_1400071B5
0x1400071ad  mov     rcx, rbx
0x1400071b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071b5  cmp     [rbx+8], edi
0x1400071b8  jl      short loc_1400071D4
0x1400071ba  cmp     r15d, 3
0x1400071be  jnz     loc_1400072A3
0x1400071c4  mov     ecx, 8000FFFFh; this
0x1400071c9  mov     [rbx+8], ecx
0x1400071cc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400071d1  mov     [rbx+0Ch], eax
0x1400071d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400071db  jnz     short loc_1400071FC
0x1400071dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400071e4  test    rax, rax
0x1400071e7  jz      short loc_1400071F2
0x1400071e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400071ee  test    al, al
0x1400071f0  jmp     short loc_1400071FA
0x1400071f2  call    cs:__imp_IsDebuggerPresent
0x1400071f8  test    eax, eax
0x1400071fa  jz      short loc_140007202
0x1400071fc  test    byte ptr [rbx+4], 2
0x140007200  jz      short loc_140007226
0x140007202  mov     rax, cs:g_pfnResultLoggingCallback
0x140007209  test    rax, rax
0x14000720c  jz      short loc_14000726A
0x14000720e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140007215  jnz     short loc_14000726A
0x140007217  xor     r8d, r8d
0x14000721a  xor     edx, edx
0x14000721c  mov     rcx, rbx
0x14000721f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007224  jmp     short loc_14000726A
0x140007226  mov     ebp, 800h
0x14000722b  mov     rax, cs:g_pfnResultLoggingCallback
0x140007232  test    rax, rax
0x140007235  jz      short loc_14000724E
0x140007237  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000723e  jnz     short loc_14000724E
0x140007240  mov     r8d, ebp
0x140007243  mov     rdx, rsi
0x140007246  mov     rcx, rbx
0x140007249  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000724e  cmp     [rsi], di
0x140007251  jnz     short loc_140007261
0x140007253  mov     r8, rbx; unsigned __int64
0x140007256  mov     rdx, rbp; unsigned __int16 *
0x140007259  mov     rcx, rsi; this
0x14000725c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140007261  mov     rcx, rsi; lpOutputString
0x140007264  call    cs:__imp_OutputDebugStringW
0x14000726a  test    byte ptr [rbx+4], 4
0x14000726e  jnz     short loc_140007279
0x140007270  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140007277  jz      short loc_14000728B
0x140007279  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140007280  test    rax, rax
0x140007283  jz      short loc_14000728B
0x140007285  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000728a  nop
0x14000728b  mov     rbx, [rsp+78h+arg_10]
0x140007293  add     rsp, 40h
0x140007297  pop     r15
0x140007299  pop     r14
0x14000729b  pop     r13
0x14000729d  pop     r12
0x14000729f  pop     rdi
0x1400072a0  pop     rsi
0x1400072a1  pop     rbp
0x1400072a2  retn
0x1400072a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
