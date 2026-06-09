# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005db0`
- end: `0x1800060a9`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003844`

## callees

- `0x180003250`
- `0x1800052f4`
- `0x180005b68`
- `0x180005db0`
- `0x180006368`
- `0x180006390`
- `0x1800063a4`
- `0x1800063c0`
- `0x180007d0c`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ed3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005ed3`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006064`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006064`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005ff2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005ff2`

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
0x180005db0  mov     [rsp+arg_10], rbx
0x180005db5  mov     [rsp+arg_8], edx
0x180005db9  mov     [rsp+arg_0], rcx
0x180005dbe  push    rbp
0x180005dbf  push    rsi
0x180005dc0  push    rdi
0x180005dc1  push    r12
0x180005dc3  push    r13
0x180005dc5  push    r14
0x180005dc7  push    r15
0x180005dc9  sub     rsp, 40h
0x180005dcd  mov     r12, r9
0x180005dd0  mov     r13, r8
0x180005dd3  mov     r10, rcx
0x180005dd6  xor     eax, eax
0x180005dd8  mov     rsi, [rsp+78h+lpOutputString]
0x180005de0  mov     [rsi], ax
0x180005de3  mov     rax, [rsp+78h+arg_60]
0x180005deb  mov     byte ptr [rax], 0
0x180005dee  mov     r14, [rsp+78h+arg_38]
0x180005df6  mov     edi, [r14]
0x180005df9  mov     rbx, [rsp+78h+arg_78]
0x180005e01  mov     [rbx+8], edi
0x180005e04  mov     eax, [r14+4]
0x180005e08  mov     [rbx+0Ch], eax
0x180005e0b  xor     ebp, ebp
0x180005e0d  mov     r15d, [rsp+78h+arg_30]
0x180005e15  mov     ecx, r15d
0x180005e18  test    r15d, r15d
0x180005e1b  jz      short loc_180005E83
0x180005e1d  sub     ecx, 1
0x180005e20  jz      short loc_180005E7A
0x180005e22  sub     ecx, 1
0x180005e25  jz      short loc_180005E35
0x180005e27  cmp     ecx, 1
0x180005e2a  jnz     short loc_180005E8C
0x180005e2c  mov     ecx, edi; this
0x180005e2e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005e33  jmp     short loc_180005E8A
0x180005e35  test    edi, edi
0x180005e37  js      short loc_180005E71
0x180005e39  mov     edi, 8007029Ch
0x180005e3e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005e42  mov     rax, [rsp+78h+arg_28]
0x180005e4a  mov     [rsp+78h+var_50], rax; __int64
0x180005e4f  mov     rax, [rsp+78h+arg_20]
0x180005e57  mov     [rsp+78h+var_58], rax; __int64
0x180005e5c  mov     rcx, r10; int
0x180005e5f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005e64  mov     [rbx+8], edi
0x180005e67  mov     ecx, edi; this
0x180005e69  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e6e  mov     [rbx+0Ch], eax
0x180005e71  mov     ecx, edi; this
0x180005e73  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005e78  jmp     short loc_180005E8A
0x180005e7a  mov     ecx, edi; this
0x180005e7c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005e81  jmp     short loc_180005E8A
0x180005e83  mov     ecx, edi; this
0x180005e85  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005e8a  mov     ebp, eax
0x180005e8c  mov     [rbx], r15d
0x180005e8f  mov     eax, [rsp+78h+arg_70]
0x180005e96  mov     [rbx+4], eax
0x180005e99  cmp     dword ptr [r14+8], 1
0x180005e9e  jnz     short loc_180005EA6
0x180005ea0  or      eax, 8
0x180005ea3  mov     [rbx+4], eax
0x180005ea6  mov     eax, 1
0x180005eab  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005eb3  inc     eax
0x180005eb5  mov     [rbx+10h], eax
0x180005eb8  mov     rax, [rsp+78h+arg_40]
0x180005ec0  xor     edi, edi
0x180005ec2  test    rax, rax
0x180005ec5  jz      short loc_180005ECC
0x180005ec7  cmp     [rax], di
0x180005eca  jnz     short loc_180005ECF
0x180005ecc  mov     rax, rdi
0x180005ecf  mov     [rbx+18h], rax
0x180005ed3  call    cs:__imp_GetCurrentThreadId
0x180005ed9  mov     [rbx+20h], eax
0x180005edc  mov     [rbx+38h], r13
0x180005ee0  mov     eax, [rsp+78h+arg_8]
0x180005ee7  mov     [rbx+40h], eax
0x180005eea  mov     [rbx+44h], ebp
0x180005eed  mov     rax, [rsp+78h+arg_20]
0x180005ef5  mov     [rbx+28h], rax
0x180005ef9  mov     [rbx+30h], r12
0x180005efd  mov     rax, [rsp+78h+arg_28]
0x180005f05  mov     [rbx+88h], rax
0x180005f0c  mov     rax, [rsp+78h+arg_0]
0x180005f14  mov     [rbx+90h], rax
0x180005f1b  mov     [rbx+48h], rdi
0x180005f1f  xorps   xmm0, xmm0
0x180005f22  xor     eax, eax
0x180005f24  movups  xmmword ptr [rbx+68h], xmm0
0x180005f28  mov     [rbx+78h], rax
0x180005f2c  movups  xmmword ptr [rbx+50h], xmm0
0x180005f30  mov     [rbx+60h], rax
0x180005f34  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005f3b  test    rax, rax
0x180005f3e  jz      short loc_180005F47
0x180005f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f45  jmp     short loc_180005F4A
0x180005f47  mov     rax, rdi
0x180005f4a  mov     [rbx+80h], rax
0x180005f51  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005f58  test    rax, rax
0x180005f5b  jz      short loc_180005F65
0x180005f5d  mov     rcx, rbx
0x180005f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f65  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005f6c  test    rax, rax
0x180005f6f  jz      short loc_180005F87
0x180005f71  mov     r8d, 400h
0x180005f77  mov     rdx, [rsp+78h+arg_60]
0x180005f7f  mov     rcx, rbx
0x180005f82  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f87  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f8e  test    rax, rax
0x180005f91  jz      short loc_180005F9B
0x180005f93  mov     rcx, rbx
0x180005f96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005fa2  test    rax, rax
0x180005fa5  jz      short loc_180005FB5
0x180005fa7  test    byte ptr [rbx+4], 2
0x180005fab  jnz     short loc_180005FB5
0x180005fad  mov     rcx, rbx
0x180005fb0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fb5  cmp     [rbx+8], edi
0x180005fb8  jl      short loc_180005FD4
0x180005fba  cmp     r15d, 3
0x180005fbe  jnz     loc_1800060A3
0x180005fc4  mov     ecx, 8000FFFFh; this
0x180005fc9  mov     [rbx+8], ecx
0x180005fcc  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005fd1  mov     [rbx+0Ch], eax
0x180005fd4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005fdb  jnz     short loc_180005FFC
0x180005fdd  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005fe4  test    rax, rax
0x180005fe7  jz      short loc_180005FF2
0x180005fe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fee  test    al, al
0x180005ff0  jmp     short loc_180005FFA
0x180005ff2  call    cs:__imp_IsDebuggerPresent
0x180005ff8  test    eax, eax
0x180005ffa  jz      short loc_180006002
0x180005ffc  test    byte ptr [rbx+4], 2
0x180006000  jz      short loc_180006026
0x180006002  mov     rax, cs:g_pfnResultLoggingCallback
0x180006009  test    rax, rax
0x18000600c  jz      short loc_18000606A
0x18000600e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006015  jnz     short loc_18000606A
0x180006017  xor     r8d, r8d
0x18000601a  xor     edx, edx
0x18000601c  mov     rcx, rbx
0x18000601f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006024  jmp     short loc_18000606A
0x180006026  mov     ebp, 800h
0x18000602b  mov     rax, cs:g_pfnResultLoggingCallback
0x180006032  test    rax, rax
0x180006035  jz      short loc_18000604E
0x180006037  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000603e  jnz     short loc_18000604E
0x180006040  mov     r8d, ebp
0x180006043  mov     rdx, rsi
0x180006046  mov     rcx, rbx
0x180006049  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604e  cmp     [rsi], di
0x180006051  jnz     short loc_180006061
0x180006053  mov     r8, rbx; unsigned __int64
0x180006056  mov     rdx, rbp; unsigned __int16 *
0x180006059  mov     rcx, rsi; this
0x18000605c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006061  mov     rcx, rsi; lpOutputString
0x180006064  call    cs:__imp_OutputDebugStringW
0x18000606a  test    byte ptr [rbx+4], 4
0x18000606e  jnz     short loc_180006079
0x180006070  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006077  jz      short loc_18000608B
0x180006079  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006080  test    rax, rax
0x180006083  jz      short loc_18000608B
0x180006085  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608a  nop
0x18000608b  mov     rbx, [rsp+78h+arg_10]
0x180006093  add     rsp, 40h
0x180006097  pop     r15
0x180006099  pop     r14
0x18000609b  pop     r13
0x18000609d  pop     r12
0x18000609f  pop     rdi
0x1800060a0  pop     rsi
0x1800060a1  pop     rbp
0x1800060a2  retn
0x1800060a3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
