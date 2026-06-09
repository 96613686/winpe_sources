# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180008e5c`
- end: `0x180009159`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `765`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180007354`
- `0x1800076c0`
- `0x18000e764`

## callees

- `0x18000728c`
- `0x180008444`
- `0x180008c6c`
- `0x180008e5c`
- `0x180009550`
- `0x180009570`
- `0x180009584`
- `0x1800095a0`
- `0x18000a394`
- `0x18008e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180008f83`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800090a2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800090a2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009114`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009114`

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
0x180008e5c  mov     [rsp+arg_10], rbx
0x180008e61  mov     [rsp+arg_8], edx
0x180008e65  mov     [rsp+arg_0], rcx
0x180008e6a  push    rbp
0x180008e6b  push    rsi
0x180008e6c  push    rdi
0x180008e6d  push    r12
0x180008e6f  push    r13
0x180008e71  push    r14
0x180008e73  push    r15
0x180008e75  sub     rsp, 40h
0x180008e79  mov     r12, r9
0x180008e7c  mov     r13, r8
0x180008e7f  mov     r10, rcx
0x180008e82  xor     eax, eax
0x180008e84  mov     rsi, [rsp+78h+lpOutputString]
0x180008e8c  mov     [rsi], ax
0x180008e8f  mov     rax, [rsp+78h+arg_60]
0x180008e97  mov     byte ptr [rax], 0
0x180008e9a  mov     r14, [rsp+78h+arg_38]
0x180008ea2  mov     edi, [r14]
0x180008ea5  mov     rbx, [rsp+78h+arg_78]
0x180008ead  mov     [rbx+8], edi
0x180008eb0  mov     eax, [r14+4]
0x180008eb4  mov     [rbx+0Ch], eax
0x180008eb7  xor     ebp, ebp
0x180008eb9  mov     r15d, [rsp+78h+arg_30]
0x180008ec1  mov     ecx, r15d
0x180008ec4  test    r15d, r15d
0x180008ec7  jz      short loc_180008F33
0x180008ec9  sub     ecx, 1
0x180008ecc  jz      short loc_180008F2A
0x180008ece  sub     ecx, 1
0x180008ed1  jz      short loc_180008EE1
0x180008ed3  cmp     ecx, 1
0x180008ed6  jnz     short loc_180008F3C
0x180008ed8  mov     ecx, edi; this
0x180008eda  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180008edf  jmp     short loc_180008F3A
0x180008ee1  test    edi, edi
0x180008ee3  js      short loc_180008F21
0x180008ee5  mov     [rsp+78h+var_40], ebp
0x180008ee9  mov     edi, 8007029Ch
0x180008eee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180008ef2  mov     rax, [rsp+78h+arg_28]
0x180008efa  mov     [rsp+78h+var_50], rax; __int64
0x180008eff  mov     rax, [rsp+78h+arg_20]
0x180008f07  mov     [rsp+78h+var_58], rax; __int64
0x180008f0c  mov     rcx, r10; int
0x180008f0f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180008f14  mov     [rbx+8], edi
0x180008f17  mov     ecx, edi; this
0x180008f19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180008f1e  mov     [rbx+0Ch], eax
0x180008f21  mov     ecx, edi; this
0x180008f23  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180008f28  jmp     short loc_180008F3A
0x180008f2a  mov     ecx, edi; this
0x180008f2c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180008f31  jmp     short loc_180008F3A
0x180008f33  mov     ecx, edi; this
0x180008f35  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180008f3a  mov     ebp, eax
0x180008f3c  mov     [rbx], r15d
0x180008f3f  mov     eax, [rsp+78h+arg_70]
0x180008f46  mov     [rbx+4], eax
0x180008f49  cmp     dword ptr [r14+8], 1
0x180008f4e  jnz     short loc_180008F56
0x180008f50  or      eax, 8
0x180008f53  mov     [rbx+4], eax
0x180008f56  mov     eax, 1
0x180008f5b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180008f63  inc     eax
0x180008f65  mov     [rbx+10h], eax
0x180008f68  mov     rax, [rsp+78h+arg_40]
0x180008f70  xor     edi, edi
0x180008f72  test    rax, rax
0x180008f75  jz      short loc_180008F7C
0x180008f77  cmp     [rax], di
0x180008f7a  jnz     short loc_180008F7F
0x180008f7c  mov     rax, rdi
0x180008f7f  mov     [rbx+18h], rax
0x180008f83  call    cs:__imp_GetCurrentThreadId
0x180008f89  mov     [rbx+20h], eax
0x180008f8c  mov     [rbx+38h], r13
0x180008f90  mov     eax, [rsp+78h+arg_8]
0x180008f97  mov     [rbx+40h], eax
0x180008f9a  mov     [rbx+44h], ebp
0x180008f9d  mov     rax, [rsp+78h+arg_20]
0x180008fa5  mov     [rbx+28h], rax
0x180008fa9  mov     [rbx+30h], r12
0x180008fad  mov     rax, [rsp+78h+arg_28]
0x180008fb5  mov     [rbx+88h], rax
0x180008fbc  mov     rax, [rsp+78h+arg_0]
0x180008fc4  mov     [rbx+90h], rax
0x180008fcb  mov     [rbx+48h], rdi
0x180008fcf  xorps   xmm0, xmm0
0x180008fd2  xor     eax, eax
0x180008fd4  movups  xmmword ptr [rbx+68h], xmm0
0x180008fd8  mov     [rbx+78h], rax
0x180008fdc  movups  xmmword ptr [rbx+50h], xmm0
0x180008fe0  mov     [rbx+60h], rax
0x180008fe4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180008feb  test    rax, rax
0x180008fee  jz      short loc_180008FF7
0x180008ff0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ff5  jmp     short loc_180008FFA
0x180008ff7  mov     rax, rdi
0x180008ffa  mov     [rbx+80h], rax
0x180009001  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009008  test    rax, rax
0x18000900b  jz      short loc_180009015
0x18000900d  mov     rcx, rbx
0x180009010  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009015  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000901c  test    rax, rax
0x18000901f  jz      short loc_180009037
0x180009021  mov     r8d, 400h
0x180009027  mov     rdx, [rsp+78h+arg_60]
0x18000902f  mov     rcx, rbx
0x180009032  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009037  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000903e  test    rax, rax
0x180009041  jz      short loc_18000904B
0x180009043  mov     rcx, rbx
0x180009046  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000904b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009052  test    rax, rax
0x180009055  jz      short loc_180009065
0x180009057  test    byte ptr [rbx+4], 2
0x18000905b  jnz     short loc_180009065
0x18000905d  mov     rcx, rbx
0x180009060  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009065  cmp     [rbx+8], edi
0x180009068  jl      short loc_180009084
0x18000906a  cmp     r15d, 3
0x18000906e  jnz     loc_180009153
0x180009074  mov     ecx, 8000FFFFh; this
0x180009079  mov     [rbx+8], ecx
0x18000907c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009081  mov     [rbx+0Ch], eax
0x180009084  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000908b  jnz     short loc_1800090AC
0x18000908d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009094  test    rax, rax
0x180009097  jz      short loc_1800090A2
0x180009099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000909e  test    al, al
0x1800090a0  jmp     short loc_1800090AA
0x1800090a2  call    cs:__imp_IsDebuggerPresent
0x1800090a8  test    eax, eax
0x1800090aa  jz      short loc_1800090B2
0x1800090ac  test    byte ptr [rbx+4], 2
0x1800090b0  jz      short loc_1800090D6
0x1800090b2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090b9  test    rax, rax
0x1800090bc  jz      short loc_18000911A
0x1800090be  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800090c5  jnz     short loc_18000911A
0x1800090c7  xor     r8d, r8d
0x1800090ca  xor     edx, edx
0x1800090cc  mov     rcx, rbx
0x1800090cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d4  jmp     short loc_18000911A
0x1800090d6  mov     ebp, 800h
0x1800090db  mov     rax, cs:g_pfnResultLoggingCallback
0x1800090e2  test    rax, rax
0x1800090e5  jz      short loc_1800090FE
0x1800090e7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800090ee  jnz     short loc_1800090FE
0x1800090f0  mov     r8d, ebp
0x1800090f3  mov     rdx, rsi
0x1800090f6  mov     rcx, rbx
0x1800090f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090fe  cmp     [rsi], di
0x180009101  jnz     short loc_180009111
0x180009103  mov     r8, rbx; unsigned __int64
0x180009106  mov     rdx, rbp; unsigned __int16 *
0x180009109  mov     rcx, rsi; this
0x18000910c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009111  mov     rcx, rsi; lpOutputString
0x180009114  call    cs:__imp_OutputDebugStringW
0x18000911a  test    byte ptr [rbx+4], 4
0x18000911e  jnz     short loc_180009129
0x180009120  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009127  jz      short loc_18000913B
0x180009129  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009130  test    rax, rax
0x180009133  jz      short loc_18000913B
0x180009135  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000913a  nop
0x18000913b  mov     rbx, [rsp+78h+arg_10]
0x180009143  add     rsp, 40h
0x180009147  pop     r15
0x180009149  pop     r14
0x18000914b  pop     r13
0x18000914d  pop     r12
0x18000914f  pop     rdi
0x180009150  pop     rsi
0x180009151  pop     rbp
0x180009152  retn
0x180009153  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
