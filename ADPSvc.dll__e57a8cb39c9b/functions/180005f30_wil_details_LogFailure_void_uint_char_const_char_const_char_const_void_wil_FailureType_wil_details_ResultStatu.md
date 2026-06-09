# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005f30`
- end: `0x180006229`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180004444`

## callees

- `0x180003e50`
- `0x1800055c4`
- `0x180005d6c`
- `0x180005f30`
- `0x1800064b4`
- `0x1800064d0`
- `0x1800064e4`
- `0x180006500`
- `0x18000770c`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006053`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006053`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006172`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006172`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061e4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800061e4`

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
    ModuleName = wil::details::g_pfnGetModuleName(v24);
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
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v24) == 0),
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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v25);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v24);
  }
}

```

## disassembly

```asm
0x180005f30  mov     [rsp+arg_10], rbx
0x180005f35  mov     [rsp+arg_8], edx
0x180005f39  mov     [rsp+arg_0], rcx
0x180005f3e  push    rbp
0x180005f3f  push    rsi
0x180005f40  push    rdi
0x180005f41  push    r12
0x180005f43  push    r13
0x180005f45  push    r14
0x180005f47  push    r15
0x180005f49  sub     rsp, 40h
0x180005f4d  mov     r12, r9
0x180005f50  mov     r13, r8
0x180005f53  mov     r10, rcx
0x180005f56  xor     eax, eax
0x180005f58  mov     rsi, [rsp+78h+lpOutputString]
0x180005f60  mov     [rsi], ax
0x180005f63  mov     rax, [rsp+78h+arg_60]
0x180005f6b  mov     byte ptr [rax], 0
0x180005f6e  mov     r14, [rsp+78h+arg_38]
0x180005f76  mov     edi, [r14]
0x180005f79  mov     rbx, [rsp+78h+arg_78]
0x180005f81  mov     [rbx+8], edi
0x180005f84  mov     eax, [r14+4]
0x180005f88  mov     [rbx+0Ch], eax
0x180005f8b  xor     ebp, ebp
0x180005f8d  mov     r15d, [rsp+78h+arg_30]
0x180005f95  mov     ecx, r15d
0x180005f98  test    r15d, r15d
0x180005f9b  jz      short loc_180006003
0x180005f9d  sub     ecx, 1
0x180005fa0  jz      short loc_180005FFA
0x180005fa2  sub     ecx, 1
0x180005fa5  jz      short loc_180005FB5
0x180005fa7  cmp     ecx, 1
0x180005faa  jnz     short loc_18000600C
0x180005fac  mov     ecx, edi; this
0x180005fae  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005fb3  jmp     short loc_18000600A
0x180005fb5  test    edi, edi
0x180005fb7  js      short loc_180005FF1
0x180005fb9  mov     edi, 8007029Ch
0x180005fbe  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005fc2  mov     rax, [rsp+78h+arg_28]
0x180005fca  mov     [rsp+78h+var_50], rax; __int64
0x180005fcf  mov     rax, [rsp+78h+arg_20]
0x180005fd7  mov     [rsp+78h+var_58], rax; __int64
0x180005fdc  mov     rcx, r10; int
0x180005fdf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005fe4  mov     [rbx+8], edi
0x180005fe7  mov     ecx, edi; this
0x180005fe9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005fee  mov     [rbx+0Ch], eax
0x180005ff1  mov     ecx, edi; this
0x180005ff3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005ff8  jmp     short loc_18000600A
0x180005ffa  mov     ecx, edi; this
0x180005ffc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006001  jmp     short loc_18000600A
0x180006003  mov     ecx, edi; this
0x180006005  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000600a  mov     ebp, eax
0x18000600c  mov     [rbx], r15d
0x18000600f  mov     eax, [rsp+78h+arg_70]
0x180006016  mov     [rbx+4], eax
0x180006019  cmp     dword ptr [r14+8], 1
0x18000601e  jnz     short loc_180006026
0x180006020  or      eax, 8
0x180006023  mov     [rbx+4], eax
0x180006026  mov     eax, 1
0x18000602b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006033  inc     eax
0x180006035  mov     [rbx+10h], eax
0x180006038  mov     rax, [rsp+78h+arg_40]
0x180006040  xor     edi, edi
0x180006042  test    rax, rax
0x180006045  jz      short loc_18000604C
0x180006047  cmp     [rax], di
0x18000604a  jnz     short loc_18000604F
0x18000604c  mov     rax, rdi
0x18000604f  mov     [rbx+18h], rax
0x180006053  call    cs:__imp_GetCurrentThreadId
0x180006059  mov     [rbx+20h], eax
0x18000605c  mov     [rbx+38h], r13
0x180006060  mov     eax, [rsp+78h+arg_8]
0x180006067  mov     [rbx+40h], eax
0x18000606a  mov     [rbx+44h], ebp
0x18000606d  mov     rax, [rsp+78h+arg_20]
0x180006075  mov     [rbx+28h], rax
0x180006079  mov     [rbx+30h], r12
0x18000607d  mov     rax, [rsp+78h+arg_28]
0x180006085  mov     [rbx+88h], rax
0x18000608c  mov     rax, [rsp+78h+arg_0]
0x180006094  mov     [rbx+90h], rax
0x18000609b  mov     [rbx+48h], rdi
0x18000609f  xorps   xmm0, xmm0
0x1800060a2  xor     eax, eax
0x1800060a4  movups  xmmword ptr [rbx+68h], xmm0
0x1800060a8  mov     [rbx+78h], rax
0x1800060ac  movups  xmmword ptr [rbx+50h], xmm0
0x1800060b0  mov     [rbx+60h], rax
0x1800060b4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800060bb  test    rax, rax
0x1800060be  jz      short loc_1800060C7
0x1800060c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060c5  jmp     short loc_1800060CA
0x1800060c7  mov     rax, rdi
0x1800060ca  mov     [rbx+80h], rax
0x1800060d1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800060d8  test    rax, rax
0x1800060db  jz      short loc_1800060E5
0x1800060dd  mov     rcx, rbx
0x1800060e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800060e5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800060ec  test    rax, rax
0x1800060ef  jz      short loc_180006107
0x1800060f1  mov     r8d, 400h
0x1800060f7  mov     rdx, [rsp+78h+arg_60]
0x1800060ff  mov     rcx, rbx
0x180006102  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006107  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000610e  test    rax, rax
0x180006111  jz      short loc_18000611B
0x180006113  mov     rcx, rbx
0x180006116  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000611b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006122  test    rax, rax
0x180006125  jz      short loc_180006135
0x180006127  test    byte ptr [rbx+4], 2
0x18000612b  jnz     short loc_180006135
0x18000612d  mov     rcx, rbx
0x180006130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006135  cmp     [rbx+8], edi
0x180006138  jl      short loc_180006154
0x18000613a  cmp     r15d, 3
0x18000613e  jnz     loc_180006223
0x180006144  mov     ecx, 8000FFFFh; this
0x180006149  mov     [rbx+8], ecx
0x18000614c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006151  mov     [rbx+0Ch], eax
0x180006154  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000615b  jnz     short loc_18000617C
0x18000615d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006164  test    rax, rax
0x180006167  jz      short loc_180006172
0x180006169  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000616e  test    al, al
0x180006170  jmp     short loc_18000617A
0x180006172  call    cs:__imp_IsDebuggerPresent
0x180006178  test    eax, eax
0x18000617a  jz      short loc_180006182
0x18000617c  test    byte ptr [rbx+4], 2
0x180006180  jz      short loc_1800061A6
0x180006182  mov     rax, cs:g_pfnResultLoggingCallback
0x180006189  test    rax, rax
0x18000618c  jz      short loc_1800061EA
0x18000618e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006195  jnz     short loc_1800061EA
0x180006197  xor     r8d, r8d
0x18000619a  xor     edx, edx
0x18000619c  mov     rcx, rbx
0x18000619f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061a4  jmp     short loc_1800061EA
0x1800061a6  mov     ebp, 800h
0x1800061ab  mov     rax, cs:g_pfnResultLoggingCallback
0x1800061b2  test    rax, rax
0x1800061b5  jz      short loc_1800061CE
0x1800061b7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800061be  jnz     short loc_1800061CE
0x1800061c0  mov     r8d, ebp
0x1800061c3  mov     rdx, rsi
0x1800061c6  mov     rcx, rbx
0x1800061c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800061ce  cmp     [rsi], di
0x1800061d1  jnz     short loc_1800061E1
0x1800061d3  mov     r8, rbx; unsigned __int64
0x1800061d6  mov     rdx, rbp; wchar_t *
0x1800061d9  mov     rcx, rsi; this
0x1800061dc  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800061e1  mov     rcx, rsi; lpOutputString
0x1800061e4  call    cs:__imp_OutputDebugStringW
0x1800061ea  test    byte ptr [rbx+4], 4
0x1800061ee  jnz     short loc_1800061F9
0x1800061f0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800061f7  jz      short loc_18000620B
0x1800061f9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006200  test    rax, rax
0x180006203  jz      short loc_18000620B
0x180006205  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000620a  nop
0x18000620b  mov     rbx, [rsp+78h+arg_10]
0x180006213  add     rsp, 40h
0x180006217  pop     r15
0x180006219  pop     r14
0x18000621b  pop     r13
0x18000621d  pop     r12
0x18000621f  pop     rdi
0x180006220  pop     rsi
0x180006221  pop     rbp
0x180006222  retn
0x180006223  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
