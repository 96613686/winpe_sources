# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006f14`
- end: `0x18000720c`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800055f4`
- `0x180005938`

## callees

- `0x180005534`
- `0x180006524`
- `0x180006d50`
- `0x180006f14`
- `0x180007648`
- `0x180007670`
- `0x180007684`
- `0x1800076a0`
- `0x1800080c4`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007037`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007037`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800071c8`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800071c8`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007156`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007156`

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
  int v16; // ebp
  unsigned int v19; // edi
  int v20; // eax
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

  v16 = 0;
  *(_WORD *)lpOutputString = 0;
  *a13 = 0;
  v19 = *a8;
  *(_DWORD *)(a16 + 8) = *a8;
  *(_DWORD *)(a16 + 12) = a8[1];
  if ( a7 )
  {
    switch ( a7 )
    {
      case 1:
        v20 = wil::details::RecordReturn((wil::details *)v19, a2);
        break;
      case 2:
        if ( (v19 & 0x80000000) == 0 )
        {
          v19 = -2147024228;
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
        }
        v20 = wil::details::RecordLog((wil::details *)v19, a2);
        break;
      case 3:
        v20 = wil::details::RecordFailFast((wil::details *)v19, a2);
        break;
      default:
        goto LABEL_12;
    }
  }
  else
  {
    v20 = wil::details::RecordException((wil::details *)v19, a2);
  }
  v16 = v20;
LABEL_12:
  *(_DWORD *)(a16 + 4) = a15;
  *(_DWORD *)a16 = a7;
  if ( a8[2] == 1 )
    *(_DWORD *)(a16 + 4) = a15 | 8;
  *(_DWORD *)(a16 + 16) = _InterlockedIncrement(&`wil::details::LogFailure'::`2'::s_failureId);
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
  CurrentThreadId = GetCurrentThreadId();
  *(_QWORD *)(a16 + 56) = a3;
  *(_DWORD *)(a16 + 32) = CurrentThreadId;
  *(_DWORD *)(a16 + 64) = a2;
  *(_QWORD *)(a16 + 40) = a5;
  *(_QWORD *)(a16 + 136) = a6;
  *(_QWORD *)(a16 + 144) = a1;
  *(_DWORD *)(a16 + 68) = v16;
  *(_QWORD *)(a16 + 48) = a4;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180006f14  mov     [rsp+arg_10], rbx
0x180006f19  mov     [rsp+arg_8], edx
0x180006f1d  mov     [rsp+arg_0], rcx
0x180006f22  push    rbp
0x180006f23  push    rsi
0x180006f24  push    rdi
0x180006f25  push    r12
0x180006f27  push    r13
0x180006f29  push    r14
0x180006f2b  push    r15
0x180006f2d  sub     rsp, 40h
0x180006f31  mov     r14, [rsp+78h+arg_38]
0x180006f39  xor     eax, eax
0x180006f3b  mov     rbx, [rsp+78h+arg_78]
0x180006f43  xor     ebp, ebp
0x180006f45  mov     r15d, [rsp+78h+arg_30]
0x180006f4d  mov     r10, rcx
0x180006f50  mov     rsi, [rsp+78h+lpOutputString]
0x180006f58  mov     r12, r9
0x180006f5b  mov     r13, r8
0x180006f5e  mov     ecx, r15d
0x180006f61  mov     [rsi], ax
0x180006f64  mov     rax, [rsp+78h+arg_60]
0x180006f6c  mov     byte ptr [rax], 0
0x180006f6f  mov     edi, [r14]
0x180006f72  mov     [rbx+8], edi
0x180006f75  mov     eax, [r14+4]
0x180006f79  mov     [rbx+0Ch], eax
0x180006f7c  test    r15d, r15d
0x180006f7f  jz      short loc_180006FE7
0x180006f81  sub     ecx, 1
0x180006f84  jz      short loc_180006FDE
0x180006f86  sub     ecx, 1
0x180006f89  jz      short loc_180006F99
0x180006f8b  cmp     ecx, 1
0x180006f8e  jnz     short loc_180006FF0
0x180006f90  mov     ecx, edi; this
0x180006f92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006f97  jmp     short loc_180006FEE
0x180006f99  test    edi, edi
0x180006f9b  js      short loc_180006FD5
0x180006f9d  mov     rax, [rsp+78h+arg_28]
0x180006fa5  mov     edi, 8007029Ch
0x180006faa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006fae  mov     rcx, r10; int
0x180006fb1  mov     [rsp+78h+var_50], rax; __int64
0x180006fb6  mov     rax, [rsp+78h+arg_20]
0x180006fbe  mov     [rsp+78h+var_58], rax; __int64
0x180006fc3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006fc8  mov     ecx, edi; this
0x180006fca  mov     [rbx+8], edi
0x180006fcd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006fd2  mov     [rbx+0Ch], eax
0x180006fd5  mov     ecx, edi; this
0x180006fd7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006fdc  jmp     short loc_180006FEE
0x180006fde  mov     ecx, edi; this
0x180006fe0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006fe5  jmp     short loc_180006FEE
0x180006fe7  mov     ecx, edi; this
0x180006fe9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006fee  mov     ebp, eax
0x180006ff0  mov     eax, [rsp+78h+arg_70]
0x180006ff7  mov     [rbx+4], eax
0x180006ffa  mov     [rbx], r15d
0x180006ffd  cmp     dword ptr [r14+8], 1
0x180007002  jnz     short loc_18000700A
0x180007004  or      eax, 8
0x180007007  mov     [rbx+4], eax
0x18000700a  mov     eax, 1
0x18000700f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007017  inc     eax
0x180007019  xor     edi, edi
0x18000701b  mov     [rbx+10h], eax
0x18000701e  mov     rax, [rsp+78h+arg_40]
0x180007026  test    rax, rax
0x180007029  jz      short loc_180007030
0x18000702b  cmp     [rax], di
0x18000702e  jnz     short loc_180007033
0x180007030  mov     rax, rdi
0x180007033  mov     [rbx+18h], rax
0x180007037  call    cs:__imp_GetCurrentThreadId
0x18000703d  mov     [rbx+38h], r13
0x180007041  xorps   xmm0, xmm0
0x180007044  mov     [rbx+20h], eax
0x180007047  mov     eax, [rsp+78h+arg_8]
0x18000704e  mov     [rbx+40h], eax
0x180007051  mov     rax, [rsp+78h+arg_20]
0x180007059  mov     [rbx+28h], rax
0x18000705d  mov     rax, [rsp+78h+arg_28]
0x180007065  mov     [rbx+88h], rax
0x18000706c  mov     rax, [rsp+78h+arg_0]
0x180007074  mov     [rbx+90h], rax
0x18000707b  xor     eax, eax
0x18000707d  mov     [rbx+44h], ebp
0x180007080  mov     [rbx+30h], r12
0x180007084  mov     [rbx+48h], rdi
0x180007088  movups  xmmword ptr [rbx+68h], xmm0
0x18000708c  mov     [rbx+78h], rax
0x180007090  movups  xmmword ptr [rbx+50h], xmm0
0x180007094  mov     [rbx+60h], rax
0x180007098  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000709f  test    rax, rax
0x1800070a2  jz      short loc_1800070AB
0x1800070a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a9  jmp     short loc_1800070AE
0x1800070ab  mov     rax, rdi
0x1800070ae  mov     [rbx+80h], rax
0x1800070b5  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800070bc  test    rax, rax
0x1800070bf  jz      short loc_1800070C9
0x1800070c1  mov     rcx, rbx
0x1800070c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070c9  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800070d0  test    rax, rax
0x1800070d3  jz      short loc_1800070EB
0x1800070d5  mov     rdx, [rsp+78h+arg_60]
0x1800070dd  mov     r8d, 400h
0x1800070e3  mov     rcx, rbx
0x1800070e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070eb  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800070f2  test    rax, rax
0x1800070f5  jz      short loc_1800070FF
0x1800070f7  mov     rcx, rbx
0x1800070fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070ff  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007106  test    rax, rax
0x180007109  jz      short loc_180007119
0x18000710b  test    byte ptr [rbx+4], 2
0x18000710f  jnz     short loc_180007119
0x180007111  mov     rcx, rbx
0x180007114  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007119  cmp     [rbx+8], edi
0x18000711c  jl      short loc_180007138
0x18000711e  cmp     r15d, 3
0x180007122  jnz     loc_180007206
0x180007128  mov     ecx, 8000FFFFh; this
0x18000712d  mov     [rbx+8], ecx
0x180007130  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007135  mov     [rbx+0Ch], eax
0x180007138  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000713f  jnz     short loc_180007160
0x180007141  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007148  test    rax, rax
0x18000714b  jz      short loc_180007156
0x18000714d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007152  test    al, al
0x180007154  jmp     short loc_18000715E
0x180007156  call    cs:__imp_IsDebuggerPresent
0x18000715c  test    eax, eax
0x18000715e  jz      short loc_180007166
0x180007160  test    byte ptr [rbx+4], 2
0x180007164  jz      short loc_18000718A
0x180007166  mov     rax, cs:g_pfnResultLoggingCallback
0x18000716d  test    rax, rax
0x180007170  jz      short loc_1800071CE
0x180007172  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007179  jnz     short loc_1800071CE
0x18000717b  xor     r8d, r8d
0x18000717e  xor     edx, edx
0x180007180  mov     rcx, rbx
0x180007183  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007188  jmp     short loc_1800071CE
0x18000718a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007191  mov     ebp, 800h
0x180007196  test    rax, rax
0x180007199  jz      short loc_1800071B2
0x18000719b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800071a2  jnz     short loc_1800071B2
0x1800071a4  mov     r8d, ebp
0x1800071a7  mov     rdx, rsi
0x1800071aa  mov     rcx, rbx
0x1800071ad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071b2  cmp     [rsi], di
0x1800071b5  jnz     short loc_1800071C5
0x1800071b7  mov     r8, rbx; unsigned __int64
0x1800071ba  mov     rdx, rbp; unsigned __int16 *
0x1800071bd  mov     rcx, rsi; this
0x1800071c0  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800071c5  mov     rcx, rsi; lpOutputString
0x1800071c8  call    cs:__imp_OutputDebugStringW
0x1800071ce  test    byte ptr [rbx+4], 4
0x1800071d2  jnz     short loc_1800071DD
0x1800071d4  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800071db  jz      short loc_1800071EE
0x1800071dd  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800071e4  test    rax, rax
0x1800071e7  jz      short loc_1800071EE
0x1800071e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800071ee  mov     rbx, [rsp+78h+arg_10]
0x1800071f6  add     rsp, 40h
0x1800071fa  pop     r15
0x1800071fc  pop     r14
0x1800071fe  pop     r13
0x180007200  pop     r12
0x180007202  pop     rdi
0x180007203  pop     rsi
0x180007204  pop     rbp
0x180007205  retn
0x180007206  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
