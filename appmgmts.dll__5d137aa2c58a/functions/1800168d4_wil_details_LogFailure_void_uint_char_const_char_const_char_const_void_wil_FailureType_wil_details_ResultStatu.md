# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800168d4`
- end: `0x180016bcd`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800141f4`

## callees

- `0x180013c30`
- `0x180015f74`
- `0x180016710`
- `0x1800168d4`
- `0x1800172dc`
- `0x180017300`
- `0x18001742c`
- `0x180017448`
- `0x1800196ac`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800169f7`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800169f7`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016b88`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180016b88`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016b16`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180016b16`

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
0x1800168d4  mov     [rsp+arg_10], rbx
0x1800168d9  mov     [rsp+arg_8], edx
0x1800168dd  mov     [rsp+arg_0], rcx
0x1800168e2  push    rbp
0x1800168e3  push    rsi
0x1800168e4  push    rdi
0x1800168e5  push    r12
0x1800168e7  push    r13
0x1800168e9  push    r14
0x1800168eb  push    r15
0x1800168ed  sub     rsp, 40h
0x1800168f1  mov     r12, r9
0x1800168f4  mov     r13, r8
0x1800168f7  mov     r10, rcx
0x1800168fa  xor     eax, eax
0x1800168fc  mov     rsi, [rsp+78h+lpOutputString]
0x180016904  mov     [rsi], ax
0x180016907  mov     rax, [rsp+78h+arg_60]
0x18001690f  mov     byte ptr [rax], 0
0x180016912  mov     r14, [rsp+78h+arg_38]
0x18001691a  mov     edi, [r14]
0x18001691d  mov     rbx, [rsp+78h+arg_78]
0x180016925  mov     [rbx+8], edi
0x180016928  mov     eax, [r14+4]
0x18001692c  mov     [rbx+0Ch], eax
0x18001692f  xor     ebp, ebp
0x180016931  mov     r15d, [rsp+78h+arg_30]
0x180016939  mov     ecx, r15d
0x18001693c  test    r15d, r15d
0x18001693f  jz      short loc_1800169A7
0x180016941  sub     ecx, 1
0x180016944  jz      short loc_18001699E
0x180016946  sub     ecx, 1
0x180016949  jz      short loc_180016959
0x18001694b  cmp     ecx, 1
0x18001694e  jnz     short loc_1800169B0
0x180016950  mov     ecx, edi; this
0x180016952  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180016957  jmp     short loc_1800169AE
0x180016959  test    edi, edi
0x18001695b  js      short loc_180016995
0x18001695d  mov     edi, 8007029Ch
0x180016962  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180016966  mov     rax, [rsp+78h+arg_28]
0x18001696e  mov     [rsp+78h+var_50], rax; __int64
0x180016973  mov     rax, [rsp+78h+arg_20]
0x18001697b  mov     [rsp+78h+var_58], rax; __int64
0x180016980  mov     rcx, r10; int
0x180016983  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180016988  mov     [rbx+8], edi
0x18001698b  mov     ecx, edi; this
0x18001698d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016992  mov     [rbx+0Ch], eax
0x180016995  mov     ecx, edi; this
0x180016997  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001699c  jmp     short loc_1800169AE
0x18001699e  mov     ecx, edi; this
0x1800169a0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800169a5  jmp     short loc_1800169AE
0x1800169a7  mov     ecx, edi; this
0x1800169a9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800169ae  mov     ebp, eax
0x1800169b0  mov     [rbx], r15d
0x1800169b3  mov     eax, [rsp+78h+arg_70]
0x1800169ba  mov     [rbx+4], eax
0x1800169bd  cmp     dword ptr [r14+8], 1
0x1800169c2  jnz     short loc_1800169CA
0x1800169c4  or      eax, 8
0x1800169c7  mov     [rbx+4], eax
0x1800169ca  mov     eax, 1
0x1800169cf  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800169d7  inc     eax
0x1800169d9  mov     [rbx+10h], eax
0x1800169dc  mov     rax, [rsp+78h+arg_40]
0x1800169e4  xor     edi, edi
0x1800169e6  test    rax, rax
0x1800169e9  jz      short loc_1800169F0
0x1800169eb  cmp     [rax], di
0x1800169ee  jnz     short loc_1800169F3
0x1800169f0  mov     rax, rdi
0x1800169f3  mov     [rbx+18h], rax
0x1800169f7  call    cs:__imp_GetCurrentThreadId
0x1800169fd  mov     [rbx+20h], eax
0x180016a00  mov     [rbx+38h], r13
0x180016a04  mov     eax, [rsp+78h+arg_8]
0x180016a0b  mov     [rbx+40h], eax
0x180016a0e  mov     [rbx+44h], ebp
0x180016a11  mov     rax, [rsp+78h+arg_20]
0x180016a19  mov     [rbx+28h], rax
0x180016a1d  mov     [rbx+30h], r12
0x180016a21  mov     rax, [rsp+78h+arg_28]
0x180016a29  mov     [rbx+88h], rax
0x180016a30  mov     rax, [rsp+78h+arg_0]
0x180016a38  mov     [rbx+90h], rax
0x180016a3f  mov     [rbx+48h], rdi
0x180016a43  xorps   xmm0, xmm0
0x180016a46  xor     eax, eax
0x180016a48  movups  xmmword ptr [rbx+68h], xmm0
0x180016a4c  mov     [rbx+78h], rax
0x180016a50  movups  xmmword ptr [rbx+50h], xmm0
0x180016a54  mov     [rbx+60h], rax
0x180016a58  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180016a5f  test    rax, rax
0x180016a62  jz      short loc_180016A6B
0x180016a64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a69  jmp     short loc_180016A6E
0x180016a6b  mov     rax, rdi
0x180016a6e  mov     [rbx+80h], rax
0x180016a75  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180016a7c  test    rax, rax
0x180016a7f  jz      short loc_180016A89
0x180016a81  mov     rcx, rbx
0x180016a84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016a89  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180016a90  test    rax, rax
0x180016a93  jz      short loc_180016AAB
0x180016a95  mov     r8d, 400h
0x180016a9b  mov     rdx, [rsp+78h+arg_60]
0x180016aa3  mov     rcx, rbx
0x180016aa6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016aab  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016ab2  test    rax, rax
0x180016ab5  jz      short loc_180016ABF
0x180016ab7  mov     rcx, rbx
0x180016aba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016abf  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180016ac6  test    rax, rax
0x180016ac9  jz      short loc_180016AD9
0x180016acb  test    byte ptr [rbx+4], 2
0x180016acf  jnz     short loc_180016AD9
0x180016ad1  mov     rcx, rbx
0x180016ad4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ad9  cmp     [rbx+8], edi
0x180016adc  jl      short loc_180016AF8
0x180016ade  cmp     r15d, 3
0x180016ae2  jnz     loc_180016BC7
0x180016ae8  mov     ecx, 8000FFFFh; this
0x180016aed  mov     [rbx+8], ecx
0x180016af0  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180016af5  mov     [rbx+0Ch], eax
0x180016af8  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180016aff  jnz     short loc_180016B20
0x180016b01  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180016b08  test    rax, rax
0x180016b0b  jz      short loc_180016B16
0x180016b0d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b12  test    al, al
0x180016b14  jmp     short loc_180016B1E
0x180016b16  call    cs:__imp_IsDebuggerPresent
0x180016b1c  test    eax, eax
0x180016b1e  jz      short loc_180016B26
0x180016b20  test    byte ptr [rbx+4], 2
0x180016b24  jz      short loc_180016B4A
0x180016b26  mov     rax, cs:g_pfnResultLoggingCallback
0x180016b2d  test    rax, rax
0x180016b30  jz      short loc_180016B8E
0x180016b32  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016b39  jnz     short loc_180016B8E
0x180016b3b  xor     r8d, r8d
0x180016b3e  xor     edx, edx
0x180016b40  mov     rcx, rbx
0x180016b43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b48  jmp     short loc_180016B8E
0x180016b4a  mov     ebp, 800h
0x180016b4f  mov     rax, cs:g_pfnResultLoggingCallback
0x180016b56  test    rax, rax
0x180016b59  jz      short loc_180016B72
0x180016b5b  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180016b62  jnz     short loc_180016B72
0x180016b64  mov     r8d, ebp
0x180016b67  mov     rdx, rsi
0x180016b6a  mov     rcx, rbx
0x180016b6d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016b72  cmp     [rsi], di
0x180016b75  jnz     short loc_180016B85
0x180016b77  mov     r8, rbx; unsigned __int64
0x180016b7a  mov     rdx, rbp; unsigned __int16 *
0x180016b7d  mov     rcx, rsi; this
0x180016b80  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180016b85  mov     rcx, rsi; lpOutputString
0x180016b88  call    cs:__imp_OutputDebugStringW
0x180016b8e  test    byte ptr [rbx+4], 4
0x180016b92  jnz     short loc_180016B9D
0x180016b94  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180016b9b  jz      short loc_180016BAF
0x180016b9d  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180016ba4  test    rax, rax
0x180016ba7  jz      short loc_180016BAF
0x180016ba9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016bae  nop
0x180016baf  mov     rbx, [rsp+78h+arg_10]
0x180016bb7  add     rsp, 40h
0x180016bbb  pop     r15
0x180016bbd  pop     r14
0x180016bbf  pop     r13
0x180016bc1  pop     r12
0x180016bc3  pop     rdi
0x180016bc4  pop     rsi
0x180016bc5  pop     rbp
0x180016bc6  retn
0x180016bc7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
