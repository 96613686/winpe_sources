# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400068cc`
- end: `0x140006bc5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1400038e8`

## callees

- `0x140003324`
- `0x140005e84`
- `0x140006620`
- `0x1400068cc`
- `0x1400076f8`
- `0x140007720`
- `0x14000784c`
- `0x140007868`
- `0x14000a11c`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400069ef`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1400069ef`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006b0e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140006b0e`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006b80`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140006b80`

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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
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
0x1400068cc  mov     [rsp+arg_10], rbx
0x1400068d1  mov     [rsp+arg_8], edx
0x1400068d5  mov     [rsp+arg_0], rcx
0x1400068da  push    rbp
0x1400068db  push    rsi
0x1400068dc  push    rdi
0x1400068dd  push    r12
0x1400068df  push    r13
0x1400068e1  push    r14
0x1400068e3  push    r15
0x1400068e5  sub     rsp, 40h
0x1400068e9  mov     r12, r9
0x1400068ec  mov     r13, r8
0x1400068ef  mov     r10, rcx
0x1400068f2  xor     eax, eax
0x1400068f4  mov     rsi, [rsp+78h+lpOutputString]
0x1400068fc  mov     [rsi], ax
0x1400068ff  mov     rax, [rsp+78h+arg_60]
0x140006907  mov     byte ptr [rax], 0
0x14000690a  mov     r14, [rsp+78h+arg_38]
0x140006912  mov     edi, [r14]
0x140006915  mov     rbx, [rsp+78h+arg_78]
0x14000691d  mov     [rbx+8], edi
0x140006920  mov     eax, [r14+4]
0x140006924  mov     [rbx+0Ch], eax
0x140006927  xor     ebp, ebp
0x140006929  mov     r15d, [rsp+78h+arg_30]
0x140006931  mov     ecx, r15d
0x140006934  test    r15d, r15d
0x140006937  jz      short loc_14000699F
0x140006939  sub     ecx, 1
0x14000693c  jz      short loc_140006996
0x14000693e  sub     ecx, 1
0x140006941  jz      short loc_140006951
0x140006943  cmp     ecx, 1
0x140006946  jnz     short loc_1400069A8
0x140006948  mov     ecx, edi; this
0x14000694a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x14000694f  jmp     short loc_1400069A6
0x140006951  test    edi, edi
0x140006953  js      short loc_14000698D
0x140006955  mov     edi, 8007029Ch
0x14000695a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x14000695e  mov     rax, [rsp+78h+arg_28]
0x140006966  mov     [rsp+78h+var_50], rax; __int64
0x14000696b  mov     rax, [rsp+78h+arg_20]
0x140006973  mov     [rsp+78h+var_58], rax; __int64
0x140006978  mov     rcx, r10; int
0x14000697b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140006980  mov     [rbx+8], edi
0x140006983  mov     ecx, edi; this
0x140006985  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x14000698a  mov     [rbx+0Ch], eax
0x14000698d  mov     ecx, edi; this
0x14000698f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140006994  jmp     short loc_1400069A6
0x140006996  mov     ecx, edi; this
0x140006998  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x14000699d  jmp     short loc_1400069A6
0x14000699f  mov     ecx, edi; this
0x1400069a1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1400069a6  mov     ebp, eax
0x1400069a8  mov     [rbx], r15d
0x1400069ab  mov     eax, [rsp+78h+arg_70]
0x1400069b2  mov     [rbx+4], eax
0x1400069b5  cmp     dword ptr [r14+8], 1
0x1400069ba  jnz     short loc_1400069C2
0x1400069bc  or      eax, 8
0x1400069bf  mov     [rbx+4], eax
0x1400069c2  mov     eax, 1
0x1400069c7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1400069cf  inc     eax
0x1400069d1  mov     [rbx+10h], eax
0x1400069d4  mov     rax, [rsp+78h+arg_40]
0x1400069dc  xor     edi, edi
0x1400069de  test    rax, rax
0x1400069e1  jz      short loc_1400069E8
0x1400069e3  cmp     [rax], di
0x1400069e6  jnz     short loc_1400069EB
0x1400069e8  mov     rax, rdi
0x1400069eb  mov     [rbx+18h], rax
0x1400069ef  call    cs:__imp_GetCurrentThreadId
0x1400069f5  mov     [rbx+20h], eax
0x1400069f8  mov     [rbx+38h], r13
0x1400069fc  mov     eax, [rsp+78h+arg_8]
0x140006a03  mov     [rbx+40h], eax
0x140006a06  mov     [rbx+44h], ebp
0x140006a09  mov     rax, [rsp+78h+arg_20]
0x140006a11  mov     [rbx+28h], rax
0x140006a15  mov     [rbx+30h], r12
0x140006a19  mov     rax, [rsp+78h+arg_28]
0x140006a21  mov     [rbx+88h], rax
0x140006a28  mov     rax, [rsp+78h+arg_0]
0x140006a30  mov     [rbx+90h], rax
0x140006a37  mov     [rbx+48h], rdi
0x140006a3b  xorps   xmm0, xmm0
0x140006a3e  xor     eax, eax
0x140006a40  movups  xmmword ptr [rbx+68h], xmm0
0x140006a44  mov     [rbx+78h], rax
0x140006a48  movups  xmmword ptr [rbx+50h], xmm0
0x140006a4c  mov     [rbx+60h], rax
0x140006a50  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140006a57  test    rax, rax
0x140006a5a  jz      short loc_140006A63
0x140006a5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a61  jmp     short loc_140006A66
0x140006a63  mov     rax, rdi
0x140006a66  mov     [rbx+80h], rax
0x140006a6d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140006a74  test    rax, rax
0x140006a77  jz      short loc_140006A81
0x140006a79  mov     rcx, rbx
0x140006a7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006a81  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140006a88  test    rax, rax
0x140006a8b  jz      short loc_140006AA3
0x140006a8d  mov     r8d, 400h
0x140006a93  mov     rdx, [rsp+78h+arg_60]
0x140006a9b  mov     rcx, rbx
0x140006a9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006aa3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006aaa  test    rax, rax
0x140006aad  jz      short loc_140006AB7
0x140006aaf  mov     rcx, rbx
0x140006ab2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ab7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140006abe  test    rax, rax
0x140006ac1  jz      short loc_140006AD1
0x140006ac3  test    byte ptr [rbx+4], 2
0x140006ac7  jnz     short loc_140006AD1
0x140006ac9  mov     rcx, rbx
0x140006acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ad1  cmp     [rbx+8], edi
0x140006ad4  jl      short loc_140006AF0
0x140006ad6  cmp     r15d, 3
0x140006ada  jnz     loc_140006BBF
0x140006ae0  mov     ecx, 8000FFFFh; this
0x140006ae5  mov     [rbx+8], ecx
0x140006ae8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140006aed  mov     [rbx+0Ch], eax
0x140006af0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140006af7  jnz     short loc_140006B18
0x140006af9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140006b00  test    rax, rax
0x140006b03  jz      short loc_140006B0E
0x140006b05  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b0a  test    al, al
0x140006b0c  jmp     short loc_140006B16
0x140006b0e  call    cs:__imp_IsDebuggerPresent
0x140006b14  test    eax, eax
0x140006b16  jz      short loc_140006B1E
0x140006b18  test    byte ptr [rbx+4], 2
0x140006b1c  jz      short loc_140006B42
0x140006b1e  mov     rax, cs:g_pfnResultLoggingCallback
0x140006b25  test    rax, rax
0x140006b28  jz      short loc_140006B86
0x140006b2a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006b31  jnz     short loc_140006B86
0x140006b33  xor     r8d, r8d
0x140006b36  xor     edx, edx
0x140006b38  mov     rcx, rbx
0x140006b3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b40  jmp     short loc_140006B86
0x140006b42  mov     ebp, 800h
0x140006b47  mov     rax, cs:g_pfnResultLoggingCallback
0x140006b4e  test    rax, rax
0x140006b51  jz      short loc_140006B6A
0x140006b53  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140006b5a  jnz     short loc_140006B6A
0x140006b5c  mov     r8d, ebp
0x140006b5f  mov     rdx, rsi
0x140006b62  mov     rcx, rbx
0x140006b65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006b6a  cmp     [rsi], di
0x140006b6d  jnz     short loc_140006B7D
0x140006b6f  mov     r8, rbx; unsigned __int64
0x140006b72  mov     rdx, rbp; unsigned __int16 *
0x140006b75  mov     rcx, rsi; this
0x140006b78  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140006b7d  mov     rcx, rsi; lpOutputString
0x140006b80  call    cs:__imp_OutputDebugStringW
0x140006b86  test    byte ptr [rbx+4], 4
0x140006b8a  jnz     short loc_140006B95
0x140006b8c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140006b93  jz      short loc_140006BA7
0x140006b95  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140006b9c  test    rax, rax
0x140006b9f  jz      short loc_140006BA7
0x140006ba1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ba6  nop
0x140006ba7  mov     rbx, [rsp+78h+arg_10]
0x140006baf  add     rsp, 40h
0x140006bb3  pop     r15
0x140006bb5  pop     r14
0x140006bb7  pop     r13
0x140006bb9  pop     r12
0x140006bbb  pop     rdi
0x140006bbc  pop     rsi
0x140006bbd  pop     rbp
0x140006bbe  retn
0x140006bbf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
