# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005940`
- end: `0x180005c35`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `757`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180002ce0`
- `0x180002d90`
- `0x180002e84`

## callees

- `0x180002c34`
- `0x180004d74`
- `0x1800055c4`
- `0x180005940`
- `0x1800067c8`
- `0x1800067f0`
- `0x180006974`
- `0x180006990`
- `0x180008990`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a63`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005a63`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bf6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005bf6`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b84`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005b84`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v25)
    || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0, v23);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v23);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
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
0x180005940  mov     [rsp+arg_10], rbx
0x180005945  mov     [rsp+arg_8], edx
0x180005949  mov     [rsp+arg_0], rcx
0x18000594e  push    rbp
0x18000594f  push    rsi
0x180005950  push    rdi
0x180005951  push    r12
0x180005953  push    r13
0x180005955  push    r14
0x180005957  push    r15
0x180005959  sub     rsp, 40h
0x18000595d  mov     r12, r9
0x180005960  mov     r13, r8
0x180005963  mov     r10, rcx
0x180005966  xor     eax, eax
0x180005968  mov     rsi, [rsp+78h+lpOutputString]
0x180005970  mov     [rsi], ax
0x180005973  mov     rax, [rsp+78h+arg_60]
0x18000597b  mov     byte ptr [rax], 0
0x18000597e  mov     r14, [rsp+78h+arg_38]
0x180005986  mov     edi, [r14]
0x180005989  mov     rbx, [rsp+78h+arg_78]
0x180005991  mov     [rbx+8], edi
0x180005994  mov     eax, [r14+4]
0x180005998  mov     [rbx+0Ch], eax
0x18000599b  xor     ebp, ebp
0x18000599d  mov     r15d, [rsp+78h+arg_30]
0x1800059a5  mov     ecx, r15d
0x1800059a8  test    r15d, r15d
0x1800059ab  jz      short loc_180005A13
0x1800059ad  sub     ecx, 1
0x1800059b0  jz      short loc_180005A0A
0x1800059b2  sub     ecx, 1
0x1800059b5  jz      short loc_1800059C5
0x1800059b7  cmp     ecx, 1
0x1800059ba  jnz     short loc_180005A1C
0x1800059bc  mov     ecx, edi; this
0x1800059be  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800059c3  jmp     short loc_180005A1A
0x1800059c5  test    edi, edi
0x1800059c7  js      short loc_180005A01
0x1800059c9  mov     edi, 8007029Ch
0x1800059ce  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800059d2  mov     rax, [rsp+78h+arg_28]
0x1800059da  mov     [rsp+78h+var_50], rax; __int64
0x1800059df  mov     rax, [rsp+78h+arg_20]
0x1800059e7  mov     [rsp+78h+var_58], rax; __int64
0x1800059ec  mov     rcx, r10; int
0x1800059ef  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800059f4  mov     [rbx+8], edi
0x1800059f7  mov     ecx, edi; this
0x1800059f9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800059fe  mov     [rbx+0Ch], eax
0x180005a01  mov     ecx, edi; this
0x180005a03  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005a08  jmp     short loc_180005A1A
0x180005a0a  mov     ecx, edi; this
0x180005a0c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005a11  jmp     short loc_180005A1A
0x180005a13  mov     ecx, edi; this
0x180005a15  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005a1a  mov     ebp, eax
0x180005a1c  mov     [rbx], r15d
0x180005a1f  mov     eax, [rsp+78h+arg_70]
0x180005a26  mov     [rbx+4], eax
0x180005a29  cmp     dword ptr [r14+8], 1
0x180005a2e  jnz     short loc_180005A36
0x180005a30  or      eax, 8
0x180005a33  mov     [rbx+4], eax
0x180005a36  mov     eax, 1
0x180005a3b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005a43  inc     eax
0x180005a45  mov     [rbx+10h], eax
0x180005a48  mov     rax, [rsp+78h+arg_40]
0x180005a50  xor     edi, edi
0x180005a52  test    rax, rax
0x180005a55  jz      short loc_180005A5C
0x180005a57  cmp     [rax], di
0x180005a5a  jnz     short loc_180005A5F
0x180005a5c  mov     rax, rdi
0x180005a5f  mov     [rbx+18h], rax
0x180005a63  call    cs:__imp_GetCurrentThreadId
0x180005a69  mov     [rbx+20h], eax
0x180005a6c  mov     [rbx+38h], r13
0x180005a70  mov     eax, [rsp+78h+arg_8]
0x180005a77  mov     [rbx+40h], eax
0x180005a7a  mov     [rbx+44h], ebp
0x180005a7d  mov     rax, [rsp+78h+arg_20]
0x180005a85  mov     [rbx+28h], rax
0x180005a89  mov     [rbx+30h], r12
0x180005a8d  mov     rax, [rsp+78h+arg_28]
0x180005a95  mov     [rbx+88h], rax
0x180005a9c  mov     rax, [rsp+78h+arg_0]
0x180005aa4  mov     [rbx+90h], rax
0x180005aab  mov     [rbx+48h], rdi
0x180005aaf  xorps   xmm0, xmm0
0x180005ab2  xor     eax, eax
0x180005ab4  movups  xmmword ptr [rbx+68h], xmm0
0x180005ab8  mov     [rbx+78h], rax
0x180005abc  movups  xmmword ptr [rbx+50h], xmm0
0x180005ac0  mov     [rbx+60h], rax
0x180005ac4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005acb  test    rax, rax
0x180005ace  jz      short loc_180005AD7
0x180005ad0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ad5  jmp     short loc_180005ADA
0x180005ad7  mov     rax, rdi
0x180005ada  mov     [rbx+80h], rax
0x180005ae1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005ae8  test    rax, rax
0x180005aeb  jz      short loc_180005AF5
0x180005aed  mov     rcx, rbx
0x180005af0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005af5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005afc  test    rax, rax
0x180005aff  jz      short loc_180005B17
0x180005b01  mov     r8d, 400h
0x180005b07  mov     rdx, [rsp+78h+arg_60]
0x180005b0f  mov     rcx, rbx
0x180005b12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b17  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b1e  test    rax, rax
0x180005b21  jz      short loc_180005B2B
0x180005b23  mov     rcx, rbx
0x180005b26  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b2b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b32  test    rax, rax
0x180005b35  jz      short loc_180005B45
0x180005b37  test    byte ptr [rbx+4], 2
0x180005b3b  jnz     short loc_180005B45
0x180005b3d  mov     rcx, rbx
0x180005b40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b45  cmp     [rbx+8], edi
0x180005b48  jl      short loc_180005B66
0x180005b4a  cmp     r15d, 3
0x180005b4e  jz      short loc_180005B56
0x180005b50  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180005b56  mov     ecx, 8000FFFFh; this
0x180005b5b  mov     [rbx+8], ecx
0x180005b5e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005b63  mov     [rbx+0Ch], eax
0x180005b66  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005b6d  jnz     short loc_180005B8E
0x180005b6f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005b76  test    rax, rax
0x180005b79  jz      short loc_180005B84
0x180005b7b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b80  test    al, al
0x180005b82  jmp     short loc_180005B8C
0x180005b84  call    cs:__imp_IsDebuggerPresent
0x180005b8a  test    eax, eax
0x180005b8c  jz      short loc_180005B94
0x180005b8e  test    byte ptr [rbx+4], 2
0x180005b92  jz      short loc_180005BB8
0x180005b94  mov     rax, cs:g_pfnResultLoggingCallback
0x180005b9b  test    rax, rax
0x180005b9e  jz      short loc_180005BFC
0x180005ba0  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ba7  jnz     short loc_180005BFC
0x180005ba9  xor     r8d, r8d
0x180005bac  xor     edx, edx
0x180005bae  mov     rcx, rbx
0x180005bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb6  jmp     short loc_180005BFC
0x180005bb8  mov     ebp, 800h
0x180005bbd  mov     rax, cs:g_pfnResultLoggingCallback
0x180005bc4  test    rax, rax
0x180005bc7  jz      short loc_180005BE0
0x180005bc9  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005bd0  jnz     short loc_180005BE0
0x180005bd2  mov     r8d, ebp
0x180005bd5  mov     rdx, rsi
0x180005bd8  mov     rcx, rbx
0x180005bdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005be0  cmp     [rsi], di
0x180005be3  jnz     short loc_180005BF3
0x180005be5  mov     r8, rbx; unsigned __int64
0x180005be8  mov     rdx, rbp; unsigned __int16 *
0x180005beb  mov     rcx, rsi; this
0x180005bee  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005bf3  mov     rcx, rsi; lpOutputString
0x180005bf6  call    cs:__imp_OutputDebugStringW
0x180005bfc  test    byte ptr [rbx+4], 4
0x180005c00  jnz     short loc_180005C0B
0x180005c02  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005c09  jz      short loc_180005C1D
0x180005c0b  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005c12  test    rax, rax
0x180005c15  jz      short loc_180005C1D
0x180005c17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c1c  nop
0x180005c1d  mov     rbx, [rsp+78h+arg_10]
0x180005c25  add     rsp, 40h
0x180005c29  pop     r15
0x180005c2b  pop     r14
0x180005c2d  pop     r13
0x180005c2f  pop     r12
0x180005c31  pop     rdi
0x180005c32  pop     rsi
0x180005c33  pop     rbp
0x180005c34  retn
```
