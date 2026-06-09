# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005eb8`
- end: `0x1800061b1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003378`

## callees

- `0x180002d84`
- `0x180005464`
- `0x180005c0c`
- `0x180005eb8`
- `0x180006b70`
- `0x180006b90`
- `0x180006cbc`
- `0x180006cd8`
- `0x18000943c`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fdb`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005fdb`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000616c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000616c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800060fa`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800060fa`

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
0x180005eb8  mov     [rsp+arg_10], rbx
0x180005ebd  mov     [rsp+arg_8], edx
0x180005ec1  mov     [rsp+arg_0], rcx
0x180005ec6  push    rbp
0x180005ec7  push    rsi
0x180005ec8  push    rdi
0x180005ec9  push    r12
0x180005ecb  push    r13
0x180005ecd  push    r14
0x180005ecf  push    r15
0x180005ed1  sub     rsp, 40h
0x180005ed5  mov     r12, r9
0x180005ed8  mov     r13, r8
0x180005edb  mov     r10, rcx
0x180005ede  xor     eax, eax
0x180005ee0  mov     rsi, [rsp+78h+lpOutputString]
0x180005ee8  mov     [rsi], ax
0x180005eeb  mov     rax, [rsp+78h+arg_60]
0x180005ef3  mov     byte ptr [rax], 0
0x180005ef6  mov     r14, [rsp+78h+arg_38]
0x180005efe  mov     edi, [r14]
0x180005f01  mov     rbx, [rsp+78h+arg_78]
0x180005f09  mov     [rbx+8], edi
0x180005f0c  mov     eax, [r14+4]
0x180005f10  mov     [rbx+0Ch], eax
0x180005f13  xor     ebp, ebp
0x180005f15  mov     r15d, [rsp+78h+arg_30]
0x180005f1d  mov     ecx, r15d
0x180005f20  test    r15d, r15d
0x180005f23  jz      short loc_180005F8B
0x180005f25  sub     ecx, 1
0x180005f28  jz      short loc_180005F82
0x180005f2a  sub     ecx, 1
0x180005f2d  jz      short loc_180005F3D
0x180005f2f  cmp     ecx, 1
0x180005f32  jnz     short loc_180005F94
0x180005f34  mov     ecx, edi; this
0x180005f36  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005f3b  jmp     short loc_180005F92
0x180005f3d  test    edi, edi
0x180005f3f  js      short loc_180005F79
0x180005f41  mov     edi, 8007029Ch
0x180005f46  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005f4a  mov     rax, [rsp+78h+arg_28]
0x180005f52  mov     [rsp+78h+var_50], rax; __int64
0x180005f57  mov     rax, [rsp+78h+arg_20]
0x180005f5f  mov     [rsp+78h+var_58], rax; __int64
0x180005f64  mov     rcx, r10; int
0x180005f67  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005f6c  mov     [rbx+8], edi
0x180005f6f  mov     ecx, edi; this
0x180005f71  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005f76  mov     [rbx+0Ch], eax
0x180005f79  mov     ecx, edi; this
0x180005f7b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005f80  jmp     short loc_180005F92
0x180005f82  mov     ecx, edi; this
0x180005f84  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005f89  jmp     short loc_180005F92
0x180005f8b  mov     ecx, edi; this
0x180005f8d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005f92  mov     ebp, eax
0x180005f94  mov     [rbx], r15d
0x180005f97  mov     eax, [rsp+78h+arg_70]
0x180005f9e  mov     [rbx+4], eax
0x180005fa1  cmp     dword ptr [r14+8], 1
0x180005fa6  jnz     short loc_180005FAE
0x180005fa8  or      eax, 8
0x180005fab  mov     [rbx+4], eax
0x180005fae  mov     eax, 1
0x180005fb3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005fbb  inc     eax
0x180005fbd  mov     [rbx+10h], eax
0x180005fc0  mov     rax, [rsp+78h+arg_40]
0x180005fc8  xor     edi, edi
0x180005fca  test    rax, rax
0x180005fcd  jz      short loc_180005FD4
0x180005fcf  cmp     [rax], di
0x180005fd2  jnz     short loc_180005FD7
0x180005fd4  mov     rax, rdi
0x180005fd7  mov     [rbx+18h], rax
0x180005fdb  call    cs:__imp_GetCurrentThreadId
0x180005fe1  mov     [rbx+20h], eax
0x180005fe4  mov     [rbx+38h], r13
0x180005fe8  mov     eax, [rsp+78h+arg_8]
0x180005fef  mov     [rbx+40h], eax
0x180005ff2  mov     [rbx+44h], ebp
0x180005ff5  mov     rax, [rsp+78h+arg_20]
0x180005ffd  mov     [rbx+28h], rax
0x180006001  mov     [rbx+30h], r12
0x180006005  mov     rax, [rsp+78h+arg_28]
0x18000600d  mov     [rbx+88h], rax
0x180006014  mov     rax, [rsp+78h+arg_0]
0x18000601c  mov     [rbx+90h], rax
0x180006023  mov     [rbx+48h], rdi
0x180006027  xorps   xmm0, xmm0
0x18000602a  xor     eax, eax
0x18000602c  movups  xmmword ptr [rbx+68h], xmm0
0x180006030  mov     [rbx+78h], rax
0x180006034  movups  xmmword ptr [rbx+50h], xmm0
0x180006038  mov     [rbx+60h], rax
0x18000603c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006043  test    rax, rax
0x180006046  jz      short loc_18000604F
0x180006048  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000604d  jmp     short loc_180006052
0x18000604f  mov     rax, rdi
0x180006052  mov     [rbx+80h], rax
0x180006059  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006060  test    rax, rax
0x180006063  jz      short loc_18000606D
0x180006065  mov     rcx, rbx
0x180006068  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000606d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006074  test    rax, rax
0x180006077  jz      short loc_18000608F
0x180006079  mov     r8d, 400h
0x18000607f  mov     rdx, [rsp+78h+arg_60]
0x180006087  mov     rcx, rbx
0x18000608a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000608f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006096  test    rax, rax
0x180006099  jz      short loc_1800060A3
0x18000609b  mov     rcx, rbx
0x18000609e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060a3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800060aa  test    rax, rax
0x1800060ad  jz      short loc_1800060BD
0x1800060af  test    byte ptr [rbx+4], 2
0x1800060b3  jnz     short loc_1800060BD
0x1800060b5  mov     rcx, rbx
0x1800060b8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060bd  cmp     [rbx+8], edi
0x1800060c0  jl      short loc_1800060DC
0x1800060c2  cmp     r15d, 3
0x1800060c6  jnz     loc_1800061AB
0x1800060cc  mov     ecx, 8000FFFFh; this
0x1800060d1  mov     [rbx+8], ecx
0x1800060d4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800060d9  mov     [rbx+0Ch], eax
0x1800060dc  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800060e3  jnz     short loc_180006104
0x1800060e5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800060ec  test    rax, rax
0x1800060ef  jz      short loc_1800060FA
0x1800060f1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060f6  test    al, al
0x1800060f8  jmp     short loc_180006102
0x1800060fa  call    cs:__imp_IsDebuggerPresent
0x180006100  test    eax, eax
0x180006102  jz      short loc_18000610A
0x180006104  test    byte ptr [rbx+4], 2
0x180006108  jz      short loc_18000612E
0x18000610a  mov     rax, cs:g_pfnResultLoggingCallback
0x180006111  test    rax, rax
0x180006114  jz      short loc_180006172
0x180006116  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000611d  jnz     short loc_180006172
0x18000611f  xor     r8d, r8d
0x180006122  xor     edx, edx
0x180006124  mov     rcx, rbx
0x180006127  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000612c  jmp     short loc_180006172
0x18000612e  mov     ebp, 800h
0x180006133  mov     rax, cs:g_pfnResultLoggingCallback
0x18000613a  test    rax, rax
0x18000613d  jz      short loc_180006156
0x18000613f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006146  jnz     short loc_180006156
0x180006148  mov     r8d, ebp
0x18000614b  mov     rdx, rsi
0x18000614e  mov     rcx, rbx
0x180006151  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006156  cmp     [rsi], di
0x180006159  jnz     short loc_180006169
0x18000615b  mov     r8, rbx; unsigned __int64
0x18000615e  mov     rdx, rbp; unsigned __int16 *
0x180006161  mov     rcx, rsi; this
0x180006164  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006169  mov     rcx, rsi; lpOutputString
0x18000616c  call    cs:__imp_OutputDebugStringW
0x180006172  test    byte ptr [rbx+4], 4
0x180006176  jnz     short loc_180006181
0x180006178  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000617f  jz      short loc_180006193
0x180006181  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006188  test    rax, rax
0x18000618b  jz      short loc_180006193
0x18000618d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006192  nop
0x180006193  mov     rbx, [rsp+78h+arg_10]
0x18000619b  add     rsp, 40h
0x18000619f  pop     r15
0x1800061a1  pop     r14
0x1800061a3  pop     r13
0x1800061a5  pop     r12
0x1800061a7  pop     rdi
0x1800061a8  pop     rsi
0x1800061a9  pop     rbp
0x1800061aa  retn
0x1800061ab  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
