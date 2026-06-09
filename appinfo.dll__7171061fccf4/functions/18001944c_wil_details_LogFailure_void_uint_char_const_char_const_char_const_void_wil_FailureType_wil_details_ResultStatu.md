# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001944c`
- end: `0x180019744`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180019350`
- `0x1800210c8`
- `0x180021188`

## callees

- `0x180010f1c`
- `0x180011bf8`
- `0x18001944c`
- `0x180019750`
- `0x180021014`
- `0x1800237e4`
- `0x1800246cc`
- `0x180024790`
- `0x1800265a4`
- `0x180048010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019573`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180019573`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019706`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180019706`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019694`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180019694`

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
0x18001944c  mov     [rsp+arg_10], rbx
0x180019451  mov     [rsp+arg_8], edx
0x180019455  mov     [rsp+arg_0], rcx
0x18001945a  push    rbp
0x18001945b  push    rsi
0x18001945c  push    rdi
0x18001945d  push    r12
0x18001945f  push    r13
0x180019461  push    r14
0x180019463  push    r15
0x180019465  sub     rsp, 40h
0x180019469  mov     r14, [rsp+78h+arg_38]
0x180019471  xor     eax, eax
0x180019473  mov     rbx, [rsp+78h+arg_78]
0x18001947b  xor     ebp, ebp
0x18001947d  mov     r15d, [rsp+78h+arg_30]
0x180019485  mov     r10, rcx
0x180019488  mov     rsi, [rsp+78h+lpOutputString]
0x180019490  mov     r12, r9
0x180019493  mov     r13, r8
0x180019496  mov     ecx, r15d
0x180019499  mov     [rsi], ax
0x18001949c  mov     rax, [rsp+78h+arg_60]
0x1800194a4  mov     byte ptr [rax], 0
0x1800194a7  mov     edi, [r14]
0x1800194aa  mov     [rbx+8], edi
0x1800194ad  mov     eax, [r14+4]
0x1800194b1  mov     [rbx+0Ch], eax
0x1800194b4  test    r15d, r15d
0x1800194b7  jz      short loc_180019523
0x1800194b9  sub     ecx, 1
0x1800194bc  jz      short loc_18001951A
0x1800194be  sub     ecx, 1
0x1800194c1  jz      short loc_1800194D1
0x1800194c3  cmp     ecx, 1
0x1800194c6  jnz     short loc_18001952C
0x1800194c8  mov     ecx, edi; this
0x1800194ca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800194cf  jmp     short loc_18001952A
0x1800194d1  test    edi, edi
0x1800194d3  js      short loc_180019511
0x1800194d5  mov     rax, [rsp+78h+arg_28]
0x1800194dd  mov     edi, 8007029Ch
0x1800194e2  mov     [rsp+78h+var_40], ebp
0x1800194e6  mov     rcx, r10; int
0x1800194e9  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800194ed  mov     [rsp+78h+var_50], rax; __int64
0x1800194f2  mov     rax, [rsp+78h+arg_20]
0x1800194fa  mov     [rsp+78h+var_58], rax; __int64
0x1800194ff  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180019504  mov     ecx, edi; this
0x180019506  mov     [rbx+8], edi
0x180019509  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001950e  mov     [rbx+0Ch], eax
0x180019511  mov     ecx, edi; this
0x180019513  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180019518  jmp     short loc_18001952A
0x18001951a  mov     ecx, edi; this
0x18001951c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180019521  jmp     short loc_18001952A
0x180019523  mov     ecx, edi; this
0x180019525  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001952a  mov     ebp, eax
0x18001952c  mov     eax, [rsp+78h+arg_70]
0x180019533  mov     [rbx+4], eax
0x180019536  mov     [rbx], r15d
0x180019539  cmp     dword ptr [r14+8], 1
0x18001953e  jnz     short loc_180019546
0x180019540  or      eax, 8
0x180019543  mov     [rbx+4], eax
0x180019546  mov     eax, 1
0x18001954b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180019553  inc     eax
0x180019555  xor     edi, edi
0x180019557  mov     [rbx+10h], eax
0x18001955a  mov     rax, [rsp+78h+arg_40]
0x180019562  test    rax, rax
0x180019565  jz      short loc_18001956C
0x180019567  cmp     [rax], di
0x18001956a  jnz     short loc_18001956F
0x18001956c  mov     rax, rdi
0x18001956f  mov     [rbx+18h], rax
0x180019573  call    cs:__imp_GetCurrentThreadId
0x180019579  mov     [rbx+38h], r13
0x18001957d  xorps   xmm0, xmm0
0x180019580  mov     [rbx+20h], eax
0x180019583  mov     eax, [rsp+78h+arg_8]
0x18001958a  mov     [rbx+40h], eax
0x18001958d  mov     rax, [rsp+78h+arg_20]
0x180019595  mov     [rbx+28h], rax
0x180019599  mov     rax, [rsp+78h+arg_28]
0x1800195a1  mov     [rbx+88h], rax
0x1800195a8  mov     rax, [rsp+78h+arg_0]
0x1800195b0  mov     [rbx+90h], rax
0x1800195b7  xor     eax, eax
0x1800195b9  mov     [rbx+44h], ebp
0x1800195bc  mov     [rbx+30h], r12
0x1800195c0  mov     [rbx+48h], rdi
0x1800195c4  movups  xmmword ptr [rbx+68h], xmm0
0x1800195c8  mov     [rbx+78h], rax
0x1800195cc  movups  xmmword ptr [rbx+50h], xmm0
0x1800195d0  mov     [rbx+60h], rax
0x1800195d4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800195db  test    rax, rax
0x1800195de  jz      short loc_1800195E7
0x1800195e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800195e5  jmp     short loc_1800195EA
0x1800195e7  mov     rax, rdi
0x1800195ea  mov     [rbx+80h], rax
0x1800195f1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800195f8  test    rax, rax
0x1800195fb  jz      short loc_180019605
0x1800195fd  mov     rcx, rbx
0x180019600  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019605  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001960c  test    rax, rax
0x18001960f  jz      short loc_180019627
0x180019611  mov     rdx, [rsp+78h+arg_60]
0x180019619  mov     r8d, 400h
0x18001961f  mov     rcx, rbx
0x180019622  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019627  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001962e  test    rax, rax
0x180019631  jz      short loc_18001963B
0x180019633  mov     rcx, rbx
0x180019636  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001963b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180019642  test    rax, rax
0x180019645  jz      short loc_180019655
0x180019647  test    byte ptr [rbx+4], 2
0x18001964b  jnz     short loc_180019655
0x18001964d  mov     rcx, rbx
0x180019650  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019655  cmp     [rbx+8], edi
0x180019658  jl      short loc_180019676
0x18001965a  cmp     r15d, 3
0x18001965e  jz      short loc_180019666
0x180019660  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180019666  mov     ecx, 8000FFFFh; this
0x18001966b  mov     [rbx+8], ecx
0x18001966e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180019673  mov     [rbx+0Ch], eax
0x180019676  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001967d  jnz     short loc_18001969E
0x18001967f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180019686  test    rax, rax
0x180019689  jz      short loc_180019694
0x18001968b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019690  test    al, al
0x180019692  jmp     short loc_18001969C
0x180019694  call    cs:__imp_IsDebuggerPresent
0x18001969a  test    eax, eax
0x18001969c  jz      short loc_1800196A4
0x18001969e  test    byte ptr [rbx+4], 2
0x1800196a2  jz      short loc_1800196C8
0x1800196a4  mov     rax, cs:g_pfnResultLoggingCallback
0x1800196ab  test    rax, rax
0x1800196ae  jz      short loc_18001970C
0x1800196b0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800196b7  jnz     short loc_18001970C
0x1800196b9  xor     r8d, r8d
0x1800196bc  xor     edx, edx
0x1800196be  mov     rcx, rbx
0x1800196c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196c6  jmp     short loc_18001970C
0x1800196c8  mov     rax, cs:g_pfnResultLoggingCallback
0x1800196cf  mov     ebp, 800h
0x1800196d4  test    rax, rax
0x1800196d7  jz      short loc_1800196F0
0x1800196d9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800196e0  jnz     short loc_1800196F0
0x1800196e2  mov     r8d, ebp
0x1800196e5  mov     rdx, rsi
0x1800196e8  mov     rcx, rbx
0x1800196eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800196f0  cmp     [rsi], di
0x1800196f3  jnz     short loc_180019703
0x1800196f5  mov     r8, rbx; unsigned __int64
0x1800196f8  mov     rdx, rbp; unsigned __int16 *
0x1800196fb  mov     rcx, rsi; this
0x1800196fe  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180019703  mov     rcx, rsi; lpOutputString
0x180019706  call    cs:__imp_OutputDebugStringW
0x18001970c  test    byte ptr [rbx+4], 4
0x180019710  jnz     short loc_18001971B
0x180019712  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180019719  jz      short loc_18001972C
0x18001971b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180019722  test    rax, rax
0x180019725  jz      short loc_18001972C
0x180019727  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001972c  mov     rbx, [rsp+78h+arg_10]
0x180019734  add     rsp, 40h
0x180019738  pop     r15
0x18001973a  pop     r14
0x18001973c  pop     r13
0x18001973e  pop     r12
0x180019740  pop     rdi
0x180019741  pop     rsi
0x180019742  pop     rbp
0x180019743  retn
```
