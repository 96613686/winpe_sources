# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800074a0`
- end: `0x180007798`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180005134`

## callees

- `0x180004b70`
- `0x180006b44`
- `0x1800072dc`
- `0x1800074a0`
- `0x180007e88`
- `0x180007eb0`
- `0x180007fd8`
- `0x180007ff4`
- `0x180009c9c`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075c3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800075c3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076e2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800076e2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007754`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007754`

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
  _WORD *v21; // rax
  DWORD CurrentThreadId; // eax
  wil::details::in1diag3 *v23; // rcx
  const struct wil::FailureInfo *v24; // r9
  __int64 ModuleName; // rax
  bool v26; // zf
  wil::details *v27; // [rsp+30h] [rbp-48h]

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
          LODWORD(v27) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v27);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v23);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v23) == 0),
        v26)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v23);
  }
}

```

## disassembly

```asm
0x1800074a0  mov     [rsp+arg_10], rbx
0x1800074a5  mov     [rsp+arg_8], edx
0x1800074a9  mov     [rsp+arg_0], rcx
0x1800074ae  push    rbp
0x1800074af  push    rsi
0x1800074b0  push    rdi
0x1800074b1  push    r12
0x1800074b3  push    r13
0x1800074b5  push    r14
0x1800074b7  push    r15
0x1800074b9  sub     rsp, 40h
0x1800074bd  mov     r14, [rsp+78h+arg_38]
0x1800074c5  xor     eax, eax
0x1800074c7  mov     rbx, [rsp+78h+arg_78]
0x1800074cf  xor     ebp, ebp
0x1800074d1  mov     r15d, [rsp+78h+arg_30]
0x1800074d9  mov     r10, rcx
0x1800074dc  mov     rsi, [rsp+78h+lpOutputString]
0x1800074e4  mov     r12, r9
0x1800074e7  mov     r13, r8
0x1800074ea  mov     ecx, r15d
0x1800074ed  mov     [rsi], ax
0x1800074f0  mov     rax, [rsp+78h+arg_60]
0x1800074f8  mov     byte ptr [rax], 0
0x1800074fb  mov     edi, [r14]
0x1800074fe  mov     [rbx+8], edi
0x180007501  mov     eax, [r14+4]
0x180007505  mov     [rbx+0Ch], eax
0x180007508  test    r15d, r15d
0x18000750b  jz      short loc_180007573
0x18000750d  sub     ecx, 1
0x180007510  jz      short loc_18000756A
0x180007512  sub     ecx, 1
0x180007515  jz      short loc_180007525
0x180007517  cmp     ecx, 1
0x18000751a  jnz     short loc_18000757C
0x18000751c  mov     ecx, edi; this
0x18000751e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007523  jmp     short loc_18000757A
0x180007525  test    edi, edi
0x180007527  js      short loc_180007561
0x180007529  mov     rax, [rsp+78h+arg_28]
0x180007531  mov     edi, 8007029Ch
0x180007536  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000753a  mov     rcx, r10; int
0x18000753d  mov     [rsp+78h+var_50], rax; __int64
0x180007542  mov     rax, [rsp+78h+arg_20]
0x18000754a  mov     [rsp+78h+var_58], rax; __int64
0x18000754f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007554  mov     ecx, edi; this
0x180007556  mov     [rbx+8], edi
0x180007559  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000755e  mov     [rbx+0Ch], eax
0x180007561  mov     ecx, edi; this
0x180007563  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007568  jmp     short loc_18000757A
0x18000756a  mov     ecx, edi; this
0x18000756c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007571  jmp     short loc_18000757A
0x180007573  mov     ecx, edi; this
0x180007575  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000757a  mov     ebp, eax
0x18000757c  mov     eax, [rsp+78h+arg_70]
0x180007583  mov     [rbx+4], eax
0x180007586  mov     [rbx], r15d
0x180007589  cmp     dword ptr [r14+8], 1
0x18000758e  jnz     short loc_180007596
0x180007590  or      eax, 8
0x180007593  mov     [rbx+4], eax
0x180007596  mov     eax, 1
0x18000759b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800075a3  inc     eax
0x1800075a5  xor     edi, edi
0x1800075a7  mov     [rbx+10h], eax
0x1800075aa  mov     rax, [rsp+78h+arg_40]
0x1800075b2  test    rax, rax
0x1800075b5  jz      short loc_1800075BC
0x1800075b7  cmp     [rax], di
0x1800075ba  jnz     short loc_1800075BF
0x1800075bc  mov     rax, rdi
0x1800075bf  mov     [rbx+18h], rax
0x1800075c3  call    cs:__imp_GetCurrentThreadId
0x1800075c9  mov     [rbx+38h], r13
0x1800075cd  xorps   xmm0, xmm0
0x1800075d0  mov     [rbx+20h], eax
0x1800075d3  mov     eax, [rsp+78h+arg_8]
0x1800075da  mov     [rbx+40h], eax
0x1800075dd  mov     rax, [rsp+78h+arg_20]
0x1800075e5  mov     [rbx+28h], rax
0x1800075e9  mov     rax, [rsp+78h+arg_28]
0x1800075f1  mov     [rbx+88h], rax
0x1800075f8  mov     rax, [rsp+78h+arg_0]
0x180007600  mov     [rbx+90h], rax
0x180007607  xor     eax, eax
0x180007609  mov     [rbx+44h], ebp
0x18000760c  mov     [rbx+30h], r12
0x180007610  mov     [rbx+48h], rdi
0x180007614  movups  xmmword ptr [rbx+68h], xmm0
0x180007618  mov     [rbx+78h], rax
0x18000761c  movups  xmmword ptr [rbx+50h], xmm0
0x180007620  mov     [rbx+60h], rax
0x180007624  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000762b  test    rax, rax
0x18000762e  jz      short loc_180007637
0x180007630  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007635  jmp     short loc_18000763A
0x180007637  mov     rax, rdi
0x18000763a  mov     [rbx+80h], rax
0x180007641  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007648  test    rax, rax
0x18000764b  jz      short loc_180007655
0x18000764d  mov     rcx, rbx
0x180007650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007655  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000765c  test    rax, rax
0x18000765f  jz      short loc_180007677
0x180007661  mov     rdx, [rsp+78h+arg_60]
0x180007669  mov     r8d, 400h
0x18000766f  mov     rcx, rbx
0x180007672  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007677  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000767e  test    rax, rax
0x180007681  jz      short loc_18000768B
0x180007683  mov     rcx, rbx
0x180007686  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000768b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007692  test    rax, rax
0x180007695  jz      short loc_1800076A5
0x180007697  test    byte ptr [rbx+4], 2
0x18000769b  jnz     short loc_1800076A5
0x18000769d  mov     rcx, rbx
0x1800076a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076a5  cmp     [rbx+8], edi
0x1800076a8  jl      short loc_1800076C4
0x1800076aa  cmp     r15d, 3
0x1800076ae  jnz     loc_180007792
0x1800076b4  mov     ecx, 8000FFFFh; this
0x1800076b9  mov     [rbx+8], ecx
0x1800076bc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800076c1  mov     [rbx+0Ch], eax
0x1800076c4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800076cb  jnz     short loc_1800076EC
0x1800076cd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800076d4  test    rax, rax
0x1800076d7  jz      short loc_1800076E2
0x1800076d9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076de  test    al, al
0x1800076e0  jmp     short loc_1800076EA
0x1800076e2  call    cs:__imp_IsDebuggerPresent
0x1800076e8  test    eax, eax
0x1800076ea  jz      short loc_1800076F2
0x1800076ec  test    byte ptr [rbx+4], 2
0x1800076f0  jz      short loc_180007716
0x1800076f2  mov     rax, cs:g_pfnResultLoggingCallback
0x1800076f9  test    rax, rax
0x1800076fc  jz      short loc_18000775A
0x1800076fe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007705  jnz     short loc_18000775A
0x180007707  xor     r8d, r8d
0x18000770a  xor     edx, edx
0x18000770c  mov     rcx, rbx
0x18000770f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007714  jmp     short loc_18000775A
0x180007716  mov     rax, cs:g_pfnResultLoggingCallback
0x18000771d  mov     ebp, 800h
0x180007722  test    rax, rax
0x180007725  jz      short loc_18000773E
0x180007727  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000772e  jnz     short loc_18000773E
0x180007730  mov     r8d, ebp
0x180007733  mov     rdx, rsi
0x180007736  mov     rcx, rbx
0x180007739  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000773e  cmp     [rsi], di
0x180007741  jnz     short loc_180007751
0x180007743  mov     r8, rbx; unsigned __int64
0x180007746  mov     rdx, rbp; unsigned __int16 *
0x180007749  mov     rcx, rsi; this
0x18000774c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007751  mov     rcx, rsi; lpOutputString
0x180007754  call    cs:__imp_OutputDebugStringW
0x18000775a  test    byte ptr [rbx+4], 4
0x18000775e  jnz     short loc_180007769
0x180007760  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007767  jz      short loc_18000777A
0x180007769  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007770  test    rax, rax
0x180007773  jz      short loc_18000777A
0x180007775  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000777a  mov     rbx, [rsp+78h+arg_10]
0x180007782  add     rsp, 40h
0x180007786  pop     r15
0x180007788  pop     r14
0x18000778a  pop     r13
0x18000778c  pop     r12
0x18000778e  pop     rdi
0x18000778f  pop     rsi
0x180007790  pop     rbp
0x180007791  retn
0x180007792  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
