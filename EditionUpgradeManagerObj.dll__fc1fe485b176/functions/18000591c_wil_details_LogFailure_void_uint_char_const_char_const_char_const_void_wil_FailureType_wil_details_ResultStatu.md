# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000591c`
- end: `0x180005c14`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800031f8`

## callees

- `0x180002c3c`
- `0x180004ed4`
- `0x180005670`
- `0x18000591c`
- `0x180006550`
- `0x180006570`
- `0x180006698`
- `0x1800066b4`
- `0x1800086ec`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a3f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bd0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bd0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b5e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b5e`

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
0x18000591c  mov     [rsp+arg_10], rbx
0x180005921  mov     [rsp+arg_8], edx
0x180005925  mov     [rsp+arg_0], rcx
0x18000592a  push    rbp
0x18000592b  push    rsi
0x18000592c  push    rdi
0x18000592d  push    r12
0x18000592f  push    r13
0x180005931  push    r14
0x180005933  push    r15
0x180005935  sub     rsp, 40h
0x180005939  mov     r14, [rsp+78h+arg_38]
0x180005941  xor     eax, eax
0x180005943  mov     rbx, [rsp+78h+arg_78]
0x18000594b  xor     ebp, ebp
0x18000594d  mov     r15d, [rsp+78h+arg_30]
0x180005955  mov     r10, rcx
0x180005958  mov     rsi, [rsp+78h+lpOutputString]
0x180005960  mov     r12, r9
0x180005963  mov     r13, r8
0x180005966  mov     ecx, r15d
0x180005969  mov     [rsi], ax
0x18000596c  mov     rax, [rsp+78h+arg_60]
0x180005974  mov     byte ptr [rax], 0
0x180005977  mov     edi, [r14]
0x18000597a  mov     [rbx+8], edi
0x18000597d  mov     eax, [r14+4]
0x180005981  mov     [rbx+0Ch], eax
0x180005984  test    r15d, r15d
0x180005987  jz      short loc_1800059EF
0x180005989  sub     ecx, 1
0x18000598c  jz      short loc_1800059E6
0x18000598e  sub     ecx, 1
0x180005991  jz      short loc_1800059A1
0x180005993  cmp     ecx, 1
0x180005996  jnz     short loc_1800059F8
0x180005998  mov     ecx, edi; this
0x18000599a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000599f  jmp     short loc_1800059F6
0x1800059a1  test    edi, edi
0x1800059a3  js      short loc_1800059DD
0x1800059a5  mov     rax, [rsp+78h+arg_28]
0x1800059ad  mov     edi, 8007029Ch
0x1800059b2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800059b6  mov     rcx, r10; int
0x1800059b9  mov     [rsp+78h+var_50], rax; __int64
0x1800059be  mov     rax, [rsp+78h+arg_20]
0x1800059c6  mov     [rsp+78h+var_58], rax; __int64
0x1800059cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800059d0  mov     ecx, edi; this
0x1800059d2  mov     [rbx+8], edi
0x1800059d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800059da  mov     [rbx+0Ch], eax
0x1800059dd  mov     ecx, edi; this
0x1800059df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800059e4  jmp     short loc_1800059F6
0x1800059e6  mov     ecx, edi; this
0x1800059e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800059ed  jmp     short loc_1800059F6
0x1800059ef  mov     ecx, edi; this
0x1800059f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800059f6  mov     ebp, eax
0x1800059f8  mov     eax, [rsp+78h+arg_70]
0x1800059ff  mov     [rbx+4], eax
0x180005a02  mov     [rbx], r15d
0x180005a05  cmp     dword ptr [r14+8], 1
0x180005a0a  jnz     short loc_180005A12
0x180005a0c  or      eax, 8
0x180005a0f  mov     [rbx+4], eax
0x180005a12  mov     eax, 1
0x180005a17  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005a1f  inc     eax
0x180005a21  xor     edi, edi
0x180005a23  mov     [rbx+10h], eax
0x180005a26  mov     rax, [rsp+78h+arg_40]
0x180005a2e  test    rax, rax
0x180005a31  jz      short loc_180005A38
0x180005a33  cmp     [rax], di
0x180005a36  jnz     short loc_180005A3B
0x180005a38  mov     rax, rdi
0x180005a3b  mov     [rbx+18h], rax
0x180005a3f  call    cs:__imp_GetCurrentThreadId
0x180005a45  mov     [rbx+38h], r13
0x180005a49  xorps   xmm0, xmm0
0x180005a4c  mov     [rbx+20h], eax
0x180005a4f  mov     eax, [rsp+78h+arg_8]
0x180005a56  mov     [rbx+40h], eax
0x180005a59  mov     rax, [rsp+78h+arg_20]
0x180005a61  mov     [rbx+28h], rax
0x180005a65  mov     rax, [rsp+78h+arg_28]
0x180005a6d  mov     [rbx+88h], rax
0x180005a74  mov     rax, [rsp+78h+arg_0]
0x180005a7c  mov     [rbx+90h], rax
0x180005a83  xor     eax, eax
0x180005a85  mov     [rbx+44h], ebp
0x180005a88  mov     [rbx+30h], r12
0x180005a8c  mov     [rbx+48h], rdi
0x180005a90  movups  xmmword ptr [rbx+68h], xmm0
0x180005a94  mov     [rbx+78h], rax
0x180005a98  movups  xmmword ptr [rbx+50h], xmm0
0x180005a9c  mov     [rbx+60h], rax
0x180005aa0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005aa7  test    rax, rax
0x180005aaa  jz      short loc_180005AB3
0x180005aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ab1  jmp     short loc_180005AB6
0x180005ab3  mov     rax, rdi
0x180005ab6  mov     [rbx+80h], rax
0x180005abd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ac4  test    rax, rax
0x180005ac7  jz      short loc_180005AD1
0x180005ac9  mov     rcx, rbx
0x180005acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005ad8  test    rax, rax
0x180005adb  jz      short loc_180005AF3
0x180005add  mov     rdx, [rsp+78h+arg_60]
0x180005ae5  mov     r8d, 400h
0x180005aeb  mov     rcx, rbx
0x180005aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005afa  test    rax, rax
0x180005afd  jz      short loc_180005B07
0x180005aff  mov     rcx, rbx
0x180005b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b07  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b0e  test    rax, rax
0x180005b11  jz      short loc_180005B21
0x180005b13  test    byte ptr [rbx+4], 2
0x180005b17  jnz     short loc_180005B21
0x180005b19  mov     rcx, rbx
0x180005b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b21  cmp     [rbx+8], edi
0x180005b24  jl      short loc_180005B40
0x180005b26  cmp     r15d, 3
0x180005b2a  jnz     loc_180005C0E
0x180005b30  mov     ecx, 8000FFFFh; this
0x180005b35  mov     [rbx+8], ecx
0x180005b38  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005b3d  mov     [rbx+0Ch], eax
0x180005b40  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005b47  jnz     short loc_180005B68
0x180005b49  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b50  test    rax, rax
0x180005b53  jz      short loc_180005B5E
0x180005b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b5a  test    al, al
0x180005b5c  jmp     short loc_180005B66
0x180005b5e  call    cs:__imp_IsDebuggerPresent
0x180005b64  test    eax, eax
0x180005b66  jz      short loc_180005B6E
0x180005b68  test    byte ptr [rbx+4], 2
0x180005b6c  jz      short loc_180005B92
0x180005b6e  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b75  test    rax, rax
0x180005b78  jz      short loc_180005BD6
0x180005b7a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005b81  jnz     short loc_180005BD6
0x180005b83  xor     r8d, r8d
0x180005b86  xor     edx, edx
0x180005b88  mov     rcx, rbx
0x180005b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b90  jmp     short loc_180005BD6
0x180005b92  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b99  mov     ebp, 800h
0x180005b9e  test    rax, rax
0x180005ba1  jz      short loc_180005BBA
0x180005ba3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005baa  jnz     short loc_180005BBA
0x180005bac  mov     r8d, ebp
0x180005baf  mov     rdx, rsi
0x180005bb2  mov     rcx, rbx
0x180005bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bba  cmp     [rsi], di
0x180005bbd  jnz     short loc_180005BCD
0x180005bbf  mov     r8, rbx; unsigned __int64
0x180005bc2  mov     rdx, rbp; unsigned __int16 *
0x180005bc5  mov     rcx, rsi; this
0x180005bc8  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005bcd  mov     rcx, rsi; lpOutputString
0x180005bd0  call    cs:__imp_OutputDebugStringW
0x180005bd6  test    byte ptr [rbx+4], 4
0x180005bda  jnz     short loc_180005BE5
0x180005bdc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005be3  jz      short loc_180005BF6
0x180005be5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005bec  test    rax, rax
0x180005bef  jz      short loc_180005BF6
0x180005bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bf6  mov     rbx, [rsp+78h+arg_10]
0x180005bfe  add     rsp, 40h
0x180005c02  pop     r15
0x180005c04  pop     r14
0x180005c06  pop     r13
0x180005c08  pop     r12
0x180005c0a  pop     rdi
0x180005c0b  pop     rsi
0x180005c0c  pop     rbp
0x180005c0d  retn
0x180005c0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
