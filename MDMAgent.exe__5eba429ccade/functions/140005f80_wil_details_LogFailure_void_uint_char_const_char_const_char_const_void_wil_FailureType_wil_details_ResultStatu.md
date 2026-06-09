# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140005f80`
- end: `0x140006279`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x140003d44`
- `0x1400040b0`

## callees

- `0x140003c7c`
- `0x1400053a4`
- `0x140005cd0`
- `0x140005f80`
- `0x140006688`
- `0x1400066b0`
- `0x1400066c4`
- `0x1400066e0`
- `0x140007994`
- `0x140019010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400060a3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400060a3`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400061c2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1400061c2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006234`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006234`

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
0x140005f80  mov     [rsp+arg_10], rbx
0x140005f85  mov     [rsp+arg_8], edx
0x140005f89  mov     [rsp+arg_0], rcx
0x140005f8e  push    rbp
0x140005f8f  push    rsi
0x140005f90  push    rdi
0x140005f91  push    r12
0x140005f93  push    r13
0x140005f95  push    r14
0x140005f97  push    r15
0x140005f99  sub     rsp, 40h
0x140005f9d  mov     r12, r9
0x140005fa0  mov     r13, r8
0x140005fa3  mov     r10, rcx
0x140005fa6  xor     eax, eax
0x140005fa8  mov     rsi, [rsp+78h+lpOutputString]
0x140005fb0  mov     [rsi], ax
0x140005fb3  mov     rax, [rsp+78h+arg_60]
0x140005fbb  mov     byte ptr [rax], 0
0x140005fbe  mov     r14, [rsp+78h+arg_38]
0x140005fc6  mov     edi, [r14]
0x140005fc9  mov     rbx, [rsp+78h+arg_78]
0x140005fd1  mov     [rbx+8], edi
0x140005fd4  mov     eax, [r14+4]
0x140005fd8  mov     [rbx+0Ch], eax
0x140005fdb  xor     ebp, ebp
0x140005fdd  mov     r15d, [rsp+78h+arg_30]
0x140005fe5  mov     ecx, r15d
0x140005fe8  test    r15d, r15d
0x140005feb  jz      short loc_140006053
0x140005fed  sub     ecx, 1
0x140005ff0  jz      short loc_14000604A
0x140005ff2  sub     ecx, 1
0x140005ff5  jz      short loc_140006005
0x140005ff7  cmp     ecx, 1
0x140005ffa  jnz     short loc_14000605C
0x140005ffc  mov     ecx, edi; this
0x140005ffe  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140006003  jmp     short loc_14000605A
0x140006005  test    edi, edi
0x140006007  js      short loc_140006041
0x140006009  mov     edi, 8007029Ch
0x14000600e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140006012  mov     rax, [rsp+78h+arg_28]
0x14000601a  mov     [rsp+78h+var_50], rax; __int64
0x14000601f  mov     rax, [rsp+78h+arg_20]
0x140006027  mov     [rsp+78h+var_58], rax; __int64
0x14000602c  mov     rcx, r10; int
0x14000602f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006034  mov     [rbx+8], edi
0x140006037  mov     ecx, edi; this
0x140006039  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000603e  mov     [rbx+0Ch], eax
0x140006041  mov     ecx, edi; this
0x140006043  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006048  jmp     short loc_14000605A
0x14000604a  mov     ecx, edi; this
0x14000604c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140006051  jmp     short loc_14000605A
0x140006053  mov     ecx, edi; this
0x140006055  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x14000605a  mov     ebp, eax
0x14000605c  mov     [rbx], r15d
0x14000605f  mov     eax, [rsp+78h+arg_70]
0x140006066  mov     [rbx+4], eax
0x140006069  cmp     dword ptr [r14+8], 1
0x14000606e  jnz     short loc_140006076
0x140006070  or      eax, 8
0x140006073  mov     [rbx+4], eax
0x140006076  mov     eax, 1
0x14000607b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140006083  inc     eax
0x140006085  mov     [rbx+10h], eax
0x140006088  mov     rax, [rsp+78h+arg_40]
0x140006090  xor     edi, edi
0x140006092  test    rax, rax
0x140006095  jz      short loc_14000609C
0x140006097  cmp     [rax], di
0x14000609a  jnz     short loc_14000609F
0x14000609c  mov     rax, rdi
0x14000609f  mov     [rbx+18h], rax
0x1400060a3  call    cs:__imp_GetCurrentThreadId
0x1400060a9  mov     [rbx+20h], eax
0x1400060ac  mov     [rbx+38h], r13
0x1400060b0  mov     eax, [rsp+78h+arg_8]
0x1400060b7  mov     [rbx+40h], eax
0x1400060ba  mov     [rbx+44h], ebp
0x1400060bd  mov     rax, [rsp+78h+arg_20]
0x1400060c5  mov     [rbx+28h], rax
0x1400060c9  mov     [rbx+30h], r12
0x1400060cd  mov     rax, [rsp+78h+arg_28]
0x1400060d5  mov     [rbx+88h], rax
0x1400060dc  mov     rax, [rsp+78h+arg_0]
0x1400060e4  mov     [rbx+90h], rax
0x1400060eb  mov     [rbx+48h], rdi
0x1400060ef  xorps   xmm0, xmm0
0x1400060f2  xor     eax, eax
0x1400060f4  movups  xmmword ptr [rbx+68h], xmm0
0x1400060f8  mov     [rbx+78h], rax
0x1400060fc  movups  xmmword ptr [rbx+50h], xmm0
0x140006100  mov     [rbx+60h], rax
0x140006104  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x14000610b  test    rax, rax
0x14000610e  jz      short loc_140006117
0x140006110  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006115  jmp     short loc_14000611A
0x140006117  mov     rax, rdi
0x14000611a  mov     [rbx+80h], rax
0x140006121  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006128  test    rax, rax
0x14000612b  jz      short loc_140006135
0x14000612d  mov     rcx, rbx
0x140006130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006135  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x14000613c  test    rax, rax
0x14000613f  jz      short loc_140006157
0x140006141  mov     r8d, 400h
0x140006147  mov     rdx, [rsp+78h+arg_60]
0x14000614f  mov     rcx, rbx
0x140006152  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006157  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x14000615e  test    rax, rax
0x140006161  jz      short loc_14000616B
0x140006163  mov     rcx, rbx
0x140006166  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000616b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006172  test    rax, rax
0x140006175  jz      short loc_140006185
0x140006177  test    byte ptr [rbx+4], 2
0x14000617b  jnz     short loc_140006185
0x14000617d  mov     rcx, rbx
0x140006180  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006185  cmp     [rbx+8], edi
0x140006188  jl      short loc_1400061A4
0x14000618a  cmp     r15d, 3
0x14000618e  jnz     loc_140006273
0x140006194  mov     ecx, 8000FFFFh; this
0x140006199  mov     [rbx+8], ecx
0x14000619c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1400061a1  mov     [rbx+0Ch], eax
0x1400061a4  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1400061ab  jnz     short loc_1400061CC
0x1400061ad  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1400061b4  test    rax, rax
0x1400061b7  jz      short loc_1400061C2
0x1400061b9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061be  test    al, al
0x1400061c0  jmp     short loc_1400061CA
0x1400061c2  call    cs:__imp_IsDebuggerPresent
0x1400061c8  test    eax, eax
0x1400061ca  jz      short loc_1400061D2
0x1400061cc  test    byte ptr [rbx+4], 2
0x1400061d0  jz      short loc_1400061F6
0x1400061d2  mov     rax, cs:g_pfnResultLoggingCallback
0x1400061d9  test    rax, rax
0x1400061dc  jz      short loc_14000623A
0x1400061de  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1400061e5  jnz     short loc_14000623A
0x1400061e7  xor     r8d, r8d
0x1400061ea  xor     edx, edx
0x1400061ec  mov     rcx, rbx
0x1400061ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400061f4  jmp     short loc_14000623A
0x1400061f6  mov     ebp, 800h
0x1400061fb  mov     rax, cs:g_pfnResultLoggingCallback
0x140006202  test    rax, rax
0x140006205  jz      short loc_14000621E
0x140006207  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x14000620e  jnz     short loc_14000621E
0x140006210  mov     r8d, ebp
0x140006213  mov     rdx, rsi
0x140006216  mov     rcx, rbx
0x140006219  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000621e  cmp     [rsi], di
0x140006221  jnz     short loc_140006231
0x140006223  mov     r8, rbx; unsigned __int64
0x140006226  mov     rdx, rbp; unsigned __int16 *
0x140006229  mov     rcx, rsi; this
0x14000622c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006231  mov     rcx, rsi; lpOutputString
0x140006234  call    cs:__imp_OutputDebugStringW
0x14000623a  test    byte ptr [rbx+4], 4
0x14000623e  jnz     short loc_140006249
0x140006240  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006247  jz      short loc_14000625B
0x140006249  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006250  test    rax, rax
0x140006253  jz      short loc_14000625B
0x140006255  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000625a  nop
0x14000625b  mov     rbx, [rsp+78h+arg_10]
0x140006263  add     rsp, 40h
0x140006267  pop     r15
0x140006269  pop     r14
0x14000626b  pop     r13
0x14000626d  pop     r12
0x14000626f  pop     rdi
0x140006270  pop     rsi
0x140006271  pop     rbp
0x140006272  retn
0x140006273  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
