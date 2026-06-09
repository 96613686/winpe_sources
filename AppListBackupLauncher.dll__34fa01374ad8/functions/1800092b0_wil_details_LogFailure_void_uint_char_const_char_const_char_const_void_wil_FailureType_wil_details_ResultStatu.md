# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800092b0`
- end: `0x1800095a9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004224`

## callees

- `0x180003974`
- `0x18000860c`
- `0x180008f00`
- `0x1800092b0`
- `0x18000a790`
- `0x18000a7b0`
- `0x18000a8dc`
- `0x18000a8f8`
- `0x18000e804`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093d3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800093d3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094f2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800094f2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009564`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009564`

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
0x1800092b0  mov     [rsp+arg_10], rbx
0x1800092b5  mov     [rsp+arg_8], edx
0x1800092b9  mov     [rsp+arg_0], rcx
0x1800092be  push    rbp
0x1800092bf  push    rsi
0x1800092c0  push    rdi
0x1800092c1  push    r12
0x1800092c3  push    r13
0x1800092c5  push    r14
0x1800092c7  push    r15
0x1800092c9  sub     rsp, 40h
0x1800092cd  mov     r12, r9
0x1800092d0  mov     r13, r8
0x1800092d3  mov     r10, rcx
0x1800092d6  xor     eax, eax
0x1800092d8  mov     rsi, [rsp+78h+lpOutputString]
0x1800092e0  mov     [rsi], ax
0x1800092e3  mov     rax, [rsp+78h+arg_60]
0x1800092eb  mov     byte ptr [rax], 0
0x1800092ee  mov     r14, [rsp+78h+arg_38]
0x1800092f6  mov     edi, [r14]
0x1800092f9  mov     rbx, [rsp+78h+arg_78]
0x180009301  mov     [rbx+8], edi
0x180009304  mov     eax, [r14+4]
0x180009308  mov     [rbx+0Ch], eax
0x18000930b  xor     ebp, ebp
0x18000930d  mov     r15d, [rsp+78h+arg_30]
0x180009315  mov     ecx, r15d
0x180009318  test    r15d, r15d
0x18000931b  jz      short loc_180009383
0x18000931d  sub     ecx, 1
0x180009320  jz      short loc_18000937A
0x180009322  sub     ecx, 1
0x180009325  jz      short loc_180009335
0x180009327  cmp     ecx, 1
0x18000932a  jnz     short loc_18000938C
0x18000932c  mov     ecx, edi; this
0x18000932e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009333  jmp     short loc_18000938A
0x180009335  test    edi, edi
0x180009337  js      short loc_180009371
0x180009339  mov     edi, 8007029Ch
0x18000933e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009342  mov     rax, [rsp+78h+arg_28]
0x18000934a  mov     [rsp+78h+var_50], rax; __int64
0x18000934f  mov     rax, [rsp+78h+arg_20]
0x180009357  mov     [rsp+78h+var_58], rax; __int64
0x18000935c  mov     rcx, r10; int
0x18000935f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009364  mov     [rbx+8], edi
0x180009367  mov     ecx, edi; this
0x180009369  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000936e  mov     [rbx+0Ch], eax
0x180009371  mov     ecx, edi; this
0x180009373  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009378  jmp     short loc_18000938A
0x18000937a  mov     ecx, edi; this
0x18000937c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009381  jmp     short loc_18000938A
0x180009383  mov     ecx, edi; this
0x180009385  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000938a  mov     ebp, eax
0x18000938c  mov     [rbx], r15d
0x18000938f  mov     eax, [rsp+78h+arg_70]
0x180009396  mov     [rbx+4], eax
0x180009399  cmp     dword ptr [r14+8], 1
0x18000939e  jnz     short loc_1800093A6
0x1800093a0  or      eax, 8
0x1800093a3  mov     [rbx+4], eax
0x1800093a6  mov     eax, 1
0x1800093ab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800093b3  inc     eax
0x1800093b5  mov     [rbx+10h], eax
0x1800093b8  mov     rax, [rsp+78h+arg_40]
0x1800093c0  xor     edi, edi
0x1800093c2  test    rax, rax
0x1800093c5  jz      short loc_1800093CC
0x1800093c7  cmp     [rax], di
0x1800093ca  jnz     short loc_1800093CF
0x1800093cc  mov     rax, rdi
0x1800093cf  mov     [rbx+18h], rax
0x1800093d3  call    cs:__imp_GetCurrentThreadId
0x1800093d9  mov     [rbx+20h], eax
0x1800093dc  mov     [rbx+38h], r13
0x1800093e0  mov     eax, [rsp+78h+arg_8]
0x1800093e7  mov     [rbx+40h], eax
0x1800093ea  mov     [rbx+44h], ebp
0x1800093ed  mov     rax, [rsp+78h+arg_20]
0x1800093f5  mov     [rbx+28h], rax
0x1800093f9  mov     [rbx+30h], r12
0x1800093fd  mov     rax, [rsp+78h+arg_28]
0x180009405  mov     [rbx+88h], rax
0x18000940c  mov     rax, [rsp+78h+arg_0]
0x180009414  mov     [rbx+90h], rax
0x18000941b  mov     [rbx+48h], rdi
0x18000941f  xorps   xmm0, xmm0
0x180009422  xor     eax, eax
0x180009424  movups  xmmword ptr [rbx+68h], xmm0
0x180009428  mov     [rbx+78h], rax
0x18000942c  movups  xmmword ptr [rbx+50h], xmm0
0x180009430  mov     [rbx+60h], rax
0x180009434  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000943b  test    rax, rax
0x18000943e  jz      short loc_180009447
0x180009440  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009445  jmp     short loc_18000944A
0x180009447  mov     rax, rdi
0x18000944a  mov     [rbx+80h], rax
0x180009451  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009458  test    rax, rax
0x18000945b  jz      short loc_180009465
0x18000945d  mov     rcx, rbx
0x180009460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009465  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000946c  test    rax, rax
0x18000946f  jz      short loc_180009487
0x180009471  mov     r8d, 400h
0x180009477  mov     rdx, [rsp+78h+arg_60]
0x18000947f  mov     rcx, rbx
0x180009482  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009487  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000948e  test    rax, rax
0x180009491  jz      short loc_18000949B
0x180009493  mov     rcx, rbx
0x180009496  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000949b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800094a2  test    rax, rax
0x1800094a5  jz      short loc_1800094B5
0x1800094a7  test    byte ptr [rbx+4], 2
0x1800094ab  jnz     short loc_1800094B5
0x1800094ad  mov     rcx, rbx
0x1800094b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094b5  cmp     [rbx+8], edi
0x1800094b8  jl      short loc_1800094D4
0x1800094ba  cmp     r15d, 3
0x1800094be  jnz     loc_1800095A3
0x1800094c4  mov     ecx, 8000FFFFh; this
0x1800094c9  mov     [rbx+8], ecx
0x1800094cc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800094d1  mov     [rbx+0Ch], eax
0x1800094d4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800094db  jnz     short loc_1800094FC
0x1800094dd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800094e4  test    rax, rax
0x1800094e7  jz      short loc_1800094F2
0x1800094e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800094ee  test    al, al
0x1800094f0  jmp     short loc_1800094FA
0x1800094f2  call    cs:__imp_IsDebuggerPresent
0x1800094f8  test    eax, eax
0x1800094fa  jz      short loc_180009502
0x1800094fc  test    byte ptr [rbx+4], 2
0x180009500  jz      short loc_180009526
0x180009502  mov     rax, cs:g_pfnResultLoggingCallback
0x180009509  test    rax, rax
0x18000950c  jz      short loc_18000956A
0x18000950e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009515  jnz     short loc_18000956A
0x180009517  xor     r8d, r8d
0x18000951a  xor     edx, edx
0x18000951c  mov     rcx, rbx
0x18000951f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009524  jmp     short loc_18000956A
0x180009526  mov     ebp, 800h
0x18000952b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009532  test    rax, rax
0x180009535  jz      short loc_18000954E
0x180009537  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000953e  jnz     short loc_18000954E
0x180009540  mov     r8d, ebp
0x180009543  mov     rdx, rsi
0x180009546  mov     rcx, rbx
0x180009549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000954e  cmp     [rsi], di
0x180009551  jnz     short loc_180009561
0x180009553  mov     r8, rbx; unsigned __int64
0x180009556  mov     rdx, rbp; unsigned __int16 *
0x180009559  mov     rcx, rsi; this
0x18000955c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009561  mov     rcx, rsi; lpOutputString
0x180009564  call    cs:__imp_OutputDebugStringW
0x18000956a  test    byte ptr [rbx+4], 4
0x18000956e  jnz     short loc_180009579
0x180009570  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009577  jz      short loc_18000958B
0x180009579  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009580  test    rax, rax
0x180009583  jz      short loc_18000958B
0x180009585  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000958a  nop
0x18000958b  mov     rbx, [rsp+78h+arg_10]
0x180009593  add     rsp, 40h
0x180009597  pop     r15
0x180009599  pop     r14
0x18000959b  pop     r13
0x18000959d  pop     r12
0x18000959f  pop     rdi
0x1800095a0  pop     rsi
0x1800095a1  pop     rbp
0x1800095a2  retn
0x1800095a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
