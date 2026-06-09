# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000691c`
- end: `0x180006c15`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x180003d70`
- `0x1800040dc`
- `0x18000aadc`

## callees

- `0x180003ca8`
- `0x180005cd4`
- `0x180006538`
- `0x18000691c`
- `0x18000780c`
- `0x180007830`
- `0x1800079b4`
- `0x1800079d0`
- `0x180009754`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a3f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006a3f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006bd0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006bd0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b5e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006b5e`

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
0x18000691c  mov     [rsp+arg_10], rbx
0x180006921  mov     [rsp+arg_8], edx
0x180006925  mov     [rsp+arg_0], rcx
0x18000692a  push    rbp
0x18000692b  push    rsi
0x18000692c  push    rdi
0x18000692d  push    r12
0x18000692f  push    r13
0x180006931  push    r14
0x180006933  push    r15
0x180006935  sub     rsp, 40h
0x180006939  mov     r12, r9
0x18000693c  mov     r13, r8
0x18000693f  mov     r10, rcx
0x180006942  xor     eax, eax
0x180006944  mov     rsi, [rsp+78h+lpOutputString]
0x18000694c  mov     [rsi], ax
0x18000694f  mov     rax, [rsp+78h+arg_60]
0x180006957  mov     byte ptr [rax], 0
0x18000695a  mov     r14, [rsp+78h+arg_38]
0x180006962  mov     edi, [r14]
0x180006965  mov     rbx, [rsp+78h+arg_78]
0x18000696d  mov     [rbx+8], edi
0x180006970  mov     eax, [r14+4]
0x180006974  mov     [rbx+0Ch], eax
0x180006977  xor     ebp, ebp
0x180006979  mov     r15d, [rsp+78h+arg_30]
0x180006981  mov     ecx, r15d
0x180006984  test    r15d, r15d
0x180006987  jz      short loc_1800069EF
0x180006989  sub     ecx, 1
0x18000698c  jz      short loc_1800069E6
0x18000698e  sub     ecx, 1
0x180006991  jz      short loc_1800069A1
0x180006993  cmp     ecx, 1
0x180006996  jnz     short loc_1800069F8
0x180006998  mov     ecx, edi; this
0x18000699a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000699f  jmp     short loc_1800069F6
0x1800069a1  test    edi, edi
0x1800069a3  js      short loc_1800069DD
0x1800069a5  mov     edi, 8007029Ch
0x1800069aa  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800069ae  mov     rax, [rsp+78h+arg_28]
0x1800069b6  mov     [rsp+78h+var_50], rax; __int64
0x1800069bb  mov     rax, [rsp+78h+arg_20]
0x1800069c3  mov     [rsp+78h+var_58], rax; __int64
0x1800069c8  mov     rcx, r10; int
0x1800069cb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800069d0  mov     [rbx+8], edi
0x1800069d3  mov     ecx, edi; this
0x1800069d5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800069da  mov     [rbx+0Ch], eax
0x1800069dd  mov     ecx, edi; this
0x1800069df  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800069e4  jmp     short loc_1800069F6
0x1800069e6  mov     ecx, edi; this
0x1800069e8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800069ed  jmp     short loc_1800069F6
0x1800069ef  mov     ecx, edi; this
0x1800069f1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800069f6  mov     ebp, eax
0x1800069f8  mov     [rbx], r15d
0x1800069fb  mov     eax, [rsp+78h+arg_70]
0x180006a02  mov     [rbx+4], eax
0x180006a05  cmp     dword ptr [r14+8], 1
0x180006a0a  jnz     short loc_180006A12
0x180006a0c  or      eax, 8
0x180006a0f  mov     [rbx+4], eax
0x180006a12  mov     eax, 1
0x180006a17  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006a1f  inc     eax
0x180006a21  mov     [rbx+10h], eax
0x180006a24  mov     rax, [rsp+78h+arg_40]
0x180006a2c  xor     edi, edi
0x180006a2e  test    rax, rax
0x180006a31  jz      short loc_180006A38
0x180006a33  cmp     [rax], di
0x180006a36  jnz     short loc_180006A3B
0x180006a38  mov     rax, rdi
0x180006a3b  mov     [rbx+18h], rax
0x180006a3f  call    cs:__imp_GetCurrentThreadId
0x180006a45  mov     [rbx+20h], eax
0x180006a48  mov     [rbx+38h], r13
0x180006a4c  mov     eax, [rsp+78h+arg_8]
0x180006a53  mov     [rbx+40h], eax
0x180006a56  mov     [rbx+44h], ebp
0x180006a59  mov     rax, [rsp+78h+arg_20]
0x180006a61  mov     [rbx+28h], rax
0x180006a65  mov     [rbx+30h], r12
0x180006a69  mov     rax, [rsp+78h+arg_28]
0x180006a71  mov     [rbx+88h], rax
0x180006a78  mov     rax, [rsp+78h+arg_0]
0x180006a80  mov     [rbx+90h], rax
0x180006a87  mov     [rbx+48h], rdi
0x180006a8b  xorps   xmm0, xmm0
0x180006a8e  xor     eax, eax
0x180006a90  movups  xmmword ptr [rbx+68h], xmm0
0x180006a94  mov     [rbx+78h], rax
0x180006a98  movups  xmmword ptr [rbx+50h], xmm0
0x180006a9c  mov     [rbx+60h], rax
0x180006aa0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006aa7  test    rax, rax
0x180006aaa  jz      short loc_180006AB3
0x180006aac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ab1  jmp     short loc_180006AB6
0x180006ab3  mov     rax, rdi
0x180006ab6  mov     [rbx+80h], rax
0x180006abd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006ac4  test    rax, rax
0x180006ac7  jz      short loc_180006AD1
0x180006ac9  mov     rcx, rbx
0x180006acc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ad1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006ad8  test    rax, rax
0x180006adb  jz      short loc_180006AF3
0x180006add  mov     r8d, 400h
0x180006ae3  mov     rdx, [rsp+78h+arg_60]
0x180006aeb  mov     rcx, rbx
0x180006aee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006af3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006afa  test    rax, rax
0x180006afd  jz      short loc_180006B07
0x180006aff  mov     rcx, rbx
0x180006b02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b07  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006b0e  test    rax, rax
0x180006b11  jz      short loc_180006B21
0x180006b13  test    byte ptr [rbx+4], 2
0x180006b17  jnz     short loc_180006B21
0x180006b19  mov     rcx, rbx
0x180006b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b21  cmp     [rbx+8], edi
0x180006b24  jl      short loc_180006B40
0x180006b26  cmp     r15d, 3
0x180006b2a  jnz     loc_180006C0F
0x180006b30  mov     ecx, 8000FFFFh; this
0x180006b35  mov     [rbx+8], ecx
0x180006b38  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006b3d  mov     [rbx+0Ch], eax
0x180006b40  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006b47  jnz     short loc_180006B68
0x180006b49  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006b50  test    rax, rax
0x180006b53  jz      short loc_180006B5E
0x180006b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b5a  test    al, al
0x180006b5c  jmp     short loc_180006B66
0x180006b5e  call    cs:__imp_IsDebuggerPresent
0x180006b64  test    eax, eax
0x180006b66  jz      short loc_180006B6E
0x180006b68  test    byte ptr [rbx+4], 2
0x180006b6c  jz      short loc_180006B92
0x180006b6e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b75  test    rax, rax
0x180006b78  jz      short loc_180006BD6
0x180006b7a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006b81  jnz     short loc_180006BD6
0x180006b83  xor     r8d, r8d
0x180006b86  xor     edx, edx
0x180006b88  mov     rcx, rbx
0x180006b8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b90  jmp     short loc_180006BD6
0x180006b92  mov     ebp, 800h
0x180006b97  mov     rax, cs:g_pfnResultLoggingCallback
0x180006b9e  test    rax, rax
0x180006ba1  jz      short loc_180006BBA
0x180006ba3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006baa  jnz     short loc_180006BBA
0x180006bac  mov     r8d, ebp
0x180006baf  mov     rdx, rsi
0x180006bb2  mov     rcx, rbx
0x180006bb5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bba  cmp     [rsi], di
0x180006bbd  jnz     short loc_180006BCD
0x180006bbf  mov     r8, rbx; unsigned __int64
0x180006bc2  mov     rdx, rbp; wchar_t *
0x180006bc5  mov     rcx, rsi; this
0x180006bc8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x180006bcd  mov     rcx, rsi; lpOutputString
0x180006bd0  call    cs:__imp_OutputDebugStringW
0x180006bd6  test    byte ptr [rbx+4], 4
0x180006bda  jnz     short loc_180006BE5
0x180006bdc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006be3  jz      short loc_180006BF7
0x180006be5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006bec  test    rax, rax
0x180006bef  jz      short loc_180006BF7
0x180006bf1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006bf6  nop
0x180006bf7  mov     rbx, [rsp+78h+arg_10]
0x180006bff  add     rsp, 40h
0x180006c03  pop     r15
0x180006c05  pop     r14
0x180006c07  pop     r13
0x180006c09  pop     r12
0x180006c0b  pop     rdi
0x180006c0c  pop     rsi
0x180006c0d  pop     rbp
0x180006c0e  retn
0x180006c0f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
