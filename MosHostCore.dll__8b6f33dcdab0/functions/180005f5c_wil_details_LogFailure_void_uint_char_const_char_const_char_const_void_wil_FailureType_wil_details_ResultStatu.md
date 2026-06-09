# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005f5c`
- end: `0x180006255`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800046a0`
- `0x1800049ec`

## callees

- `0x1800045e0`
- `0x1800055c4`
- `0x180005d98`
- `0x180005f5c`
- `0x180006624`
- `0x180006640`
- `0x180006654`
- `0x180006670`
- `0x1800073c0`
- `0x180025010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000607f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000607f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006210`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006210`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000619e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000619e`

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
0x180005f5c  mov     [rsp+arg_10], rbx
0x180005f61  mov     [rsp+arg_8], edx
0x180005f65  mov     [rsp+arg_0], rcx
0x180005f6a  push    rbp
0x180005f6b  push    rsi
0x180005f6c  push    rdi
0x180005f6d  push    r12
0x180005f6f  push    r13
0x180005f71  push    r14
0x180005f73  push    r15
0x180005f75  sub     rsp, 40h
0x180005f79  mov     r12, r9
0x180005f7c  mov     r13, r8
0x180005f7f  mov     r10, rcx
0x180005f82  xor     eax, eax
0x180005f84  mov     rsi, [rsp+78h+lpOutputString]
0x180005f8c  mov     [rsi], ax
0x180005f8f  mov     rax, [rsp+78h+arg_60]
0x180005f97  mov     byte ptr [rax], 0
0x180005f9a  mov     r14, [rsp+78h+arg_38]
0x180005fa2  mov     edi, [r14]
0x180005fa5  mov     rbx, [rsp+78h+arg_78]
0x180005fad  mov     [rbx+8], edi
0x180005fb0  mov     eax, [r14+4]
0x180005fb4  mov     [rbx+0Ch], eax
0x180005fb7  xor     ebp, ebp
0x180005fb9  mov     r15d, [rsp+78h+arg_30]
0x180005fc1  mov     ecx, r15d
0x180005fc4  test    r15d, r15d
0x180005fc7  jz      short loc_18000602F
0x180005fc9  sub     ecx, 1
0x180005fcc  jz      short loc_180006026
0x180005fce  sub     ecx, 1
0x180005fd1  jz      short loc_180005FE1
0x180005fd3  cmp     ecx, 1
0x180005fd6  jnz     short loc_180006038
0x180005fd8  mov     ecx, edi; this
0x180005fda  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005fdf  jmp     short loc_180006036
0x180005fe1  test    edi, edi
0x180005fe3  js      short loc_18000601D
0x180005fe5  mov     edi, 8007029Ch
0x180005fea  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005fee  mov     rax, [rsp+78h+arg_28]
0x180005ff6  mov     [rsp+78h+var_50], rax; __int64
0x180005ffb  mov     rax, [rsp+78h+arg_20]
0x180006003  mov     [rsp+78h+var_58], rax; __int64
0x180006008  mov     rcx, r10; int
0x18000600b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006010  mov     [rbx+8], edi
0x180006013  mov     ecx, edi; this
0x180006015  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000601a  mov     [rbx+0Ch], eax
0x18000601d  mov     ecx, edi; this
0x18000601f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006024  jmp     short loc_180006036
0x180006026  mov     ecx, edi; this
0x180006028  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000602d  jmp     short loc_180006036
0x18000602f  mov     ecx, edi; this
0x180006031  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006036  mov     ebp, eax
0x180006038  mov     [rbx], r15d
0x18000603b  mov     eax, [rsp+78h+arg_70]
0x180006042  mov     [rbx+4], eax
0x180006045  cmp     dword ptr [r14+8], 1
0x18000604a  jnz     short loc_180006052
0x18000604c  or      eax, 8
0x18000604f  mov     [rbx+4], eax
0x180006052  mov     eax, 1
0x180006057  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000605f  inc     eax
0x180006061  mov     [rbx+10h], eax
0x180006064  mov     rax, [rsp+78h+arg_40]
0x18000606c  xor     edi, edi
0x18000606e  test    rax, rax
0x180006071  jz      short loc_180006078
0x180006073  cmp     [rax], di
0x180006076  jnz     short loc_18000607B
0x180006078  mov     rax, rdi
0x18000607b  mov     [rbx+18h], rax
0x18000607f  call    cs:__imp_GetCurrentThreadId
0x180006085  mov     [rbx+20h], eax
0x180006088  mov     [rbx+38h], r13
0x18000608c  mov     eax, [rsp+78h+arg_8]
0x180006093  mov     [rbx+40h], eax
0x180006096  mov     [rbx+44h], ebp
0x180006099  mov     rax, [rsp+78h+arg_20]
0x1800060a1  mov     [rbx+28h], rax
0x1800060a5  mov     [rbx+30h], r12
0x1800060a9  mov     rax, [rsp+78h+arg_28]
0x1800060b1  mov     [rbx+88h], rax
0x1800060b8  mov     rax, [rsp+78h+arg_0]
0x1800060c0  mov     [rbx+90h], rax
0x1800060c7  mov     [rbx+48h], rdi
0x1800060cb  xorps   xmm0, xmm0
0x1800060ce  xor     eax, eax
0x1800060d0  movups  xmmword ptr [rbx+68h], xmm0
0x1800060d4  mov     [rbx+78h], rax
0x1800060d8  movups  xmmword ptr [rbx+50h], xmm0
0x1800060dc  mov     [rbx+60h], rax
0x1800060e0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800060e7  test    rax, rax
0x1800060ea  jz      short loc_1800060F3
0x1800060ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f1  jmp     short loc_1800060F6
0x1800060f3  mov     rax, rdi
0x1800060f6  mov     [rbx+80h], rax
0x1800060fd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006104  test    rax, rax
0x180006107  jz      short loc_180006111
0x180006109  mov     rcx, rbx
0x18000610c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006111  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006118  test    rax, rax
0x18000611b  jz      short loc_180006133
0x18000611d  mov     r8d, 400h
0x180006123  mov     rdx, [rsp+78h+arg_60]
0x18000612b  mov     rcx, rbx
0x18000612e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006133  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000613a  test    rax, rax
0x18000613d  jz      short loc_180006147
0x18000613f  mov     rcx, rbx
0x180006142  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006147  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000614e  test    rax, rax
0x180006151  jz      short loc_180006161
0x180006153  test    byte ptr [rbx+4], 2
0x180006157  jnz     short loc_180006161
0x180006159  mov     rcx, rbx
0x18000615c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006161  cmp     [rbx+8], edi
0x180006164  jl      short loc_180006180
0x180006166  cmp     r15d, 3
0x18000616a  jnz     loc_18000624F
0x180006170  mov     ecx, 8000FFFFh; this
0x180006175  mov     [rbx+8], ecx
0x180006178  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000617d  mov     [rbx+0Ch], eax
0x180006180  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006187  jnz     short loc_1800061A8
0x180006189  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006190  test    rax, rax
0x180006193  jz      short loc_18000619E
0x180006195  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000619a  test    al, al
0x18000619c  jmp     short loc_1800061A6
0x18000619e  call    cs:__imp_IsDebuggerPresent
0x1800061a4  test    eax, eax
0x1800061a6  jz      short loc_1800061AE
0x1800061a8  test    byte ptr [rbx+4], 2
0x1800061ac  jz      short loc_1800061D2
0x1800061ae  mov     rax, cs:g_pfnResultLoggingCallback
0x1800061b5  test    rax, rax
0x1800061b8  jz      short loc_180006216
0x1800061ba  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800061c1  jnz     short loc_180006216
0x1800061c3  xor     r8d, r8d
0x1800061c6  xor     edx, edx
0x1800061c8  mov     rcx, rbx
0x1800061cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061d0  jmp     short loc_180006216
0x1800061d2  mov     ebp, 800h
0x1800061d7  mov     rax, cs:g_pfnResultLoggingCallback
0x1800061de  test    rax, rax
0x1800061e1  jz      short loc_1800061FA
0x1800061e3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800061ea  jnz     short loc_1800061FA
0x1800061ec  mov     r8d, ebp
0x1800061ef  mov     rdx, rsi
0x1800061f2  mov     rcx, rbx
0x1800061f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061fa  cmp     [rsi], di
0x1800061fd  jnz     short loc_18000620D
0x1800061ff  mov     r8, rbx; unsigned __int64
0x180006202  mov     rdx, rbp; unsigned __int16 *
0x180006205  mov     rcx, rsi; this
0x180006208  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000620d  mov     rcx, rsi; lpOutputString
0x180006210  call    cs:__imp_OutputDebugStringW
0x180006216  test    byte ptr [rbx+4], 4
0x18000621a  jnz     short loc_180006225
0x18000621c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006223  jz      short loc_180006237
0x180006225  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000622c  test    rax, rax
0x18000622f  jz      short loc_180006237
0x180006231  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006236  nop
0x180006237  mov     rbx, [rsp+78h+arg_10]
0x18000623f  add     rsp, 40h
0x180006243  pop     r15
0x180006245  pop     r14
0x180006247  pop     r13
0x180006249  pop     r12
0x18000624b  pop     rdi
0x18000624c  pop     rsi
0x18000624d  pop     rbp
0x18000624e  retn
0x18000624f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
