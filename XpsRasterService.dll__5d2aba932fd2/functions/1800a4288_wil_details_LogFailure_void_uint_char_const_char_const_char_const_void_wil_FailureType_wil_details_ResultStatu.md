# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800a4288`
- end: `0x1800a4581`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800a21c4`
- `0x1800a2530`

## callees

- `0x1800a2160`
- `0x1800a3be4`
- `0x1800a3fcc`
- `0x1800a4288`
- `0x1800a4988`
- `0x1800a49b0`
- `0x1800a49c4`
- `0x1800a49e0`
- `0x1800a52d0`
- `0x1800c3010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a43ab`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800a43ab`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a453c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800a453c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a44ca`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800a44ca`

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
0x1800a4288  mov     [rsp+arg_10], rbx
0x1800a428d  mov     [rsp+arg_8], edx
0x1800a4291  mov     [rsp+arg_0], rcx
0x1800a4296  push    rbp
0x1800a4297  push    rsi
0x1800a4298  push    rdi
0x1800a4299  push    r12
0x1800a429b  push    r13
0x1800a429d  push    r14
0x1800a429f  push    r15
0x1800a42a1  sub     rsp, 40h
0x1800a42a5  mov     r12, r9
0x1800a42a8  mov     r13, r8
0x1800a42ab  mov     r10, rcx
0x1800a42ae  xor     eax, eax
0x1800a42b0  mov     rsi, [rsp+78h+lpOutputString]
0x1800a42b8  mov     [rsi], ax
0x1800a42bb  mov     rax, [rsp+78h+arg_60]
0x1800a42c3  mov     byte ptr [rax], 0
0x1800a42c6  mov     r14, [rsp+78h+arg_38]
0x1800a42ce  mov     edi, [r14]
0x1800a42d1  mov     rbx, [rsp+78h+arg_78]
0x1800a42d9  mov     [rbx+8], edi
0x1800a42dc  mov     eax, [r14+4]
0x1800a42e0  mov     [rbx+0Ch], eax
0x1800a42e3  xor     ebp, ebp
0x1800a42e5  mov     r15d, [rsp+78h+arg_30]
0x1800a42ed  mov     ecx, r15d
0x1800a42f0  test    r15d, r15d
0x1800a42f3  jz      short loc_1800A435B
0x1800a42f5  sub     ecx, 1
0x1800a42f8  jz      short loc_1800A4352
0x1800a42fa  sub     ecx, 1
0x1800a42fd  jz      short loc_1800A430D
0x1800a42ff  cmp     ecx, 1
0x1800a4302  jnz     short loc_1800A4364
0x1800a4304  mov     ecx, edi; this
0x1800a4306  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800a430b  jmp     short loc_1800A4362
0x1800a430d  test    edi, edi
0x1800a430f  js      short loc_1800A4349
0x1800a4311  mov     edi, 8007029Ch
0x1800a4316  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x1800a431a  mov     rax, [rsp+78h+arg_28]
0x1800a4322  mov     [rsp+78h+var_50], rax; __int64
0x1800a4327  mov     rax, [rsp+78h+arg_20]
0x1800a432f  mov     [rsp+78h+var_58], rax; __int64
0x1800a4334  mov     rcx, r10; int
0x1800a4337  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x1800a433c  mov     [rbx+8], edi
0x1800a433f  mov     ecx, edi; this
0x1800a4341  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a4346  mov     [rbx+0Ch], eax
0x1800a4349  mov     ecx, edi; this
0x1800a434b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x1800a4350  jmp     short loc_1800A4362
0x1800a4352  mov     ecx, edi; this
0x1800a4354  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x1800a4359  jmp     short loc_1800A4362
0x1800a435b  mov     ecx, edi; this
0x1800a435d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x1800a4362  mov     ebp, eax
0x1800a4364  mov     [rbx], r15d
0x1800a4367  mov     eax, [rsp+78h+arg_70]
0x1800a436e  mov     [rbx+4], eax
0x1800a4371  cmp     dword ptr [r14+8], 1
0x1800a4376  jnz     short loc_1800A437E
0x1800a4378  or      eax, 8
0x1800a437b  mov     [rbx+4], eax
0x1800a437e  mov     eax, 1
0x1800a4383  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800a438b  inc     eax
0x1800a438d  mov     [rbx+10h], eax
0x1800a4390  mov     rax, [rsp+78h+arg_40]
0x1800a4398  xor     edi, edi
0x1800a439a  test    rax, rax
0x1800a439d  jz      short loc_1800A43A4
0x1800a439f  cmp     [rax], di
0x1800a43a2  jnz     short loc_1800A43A7
0x1800a43a4  mov     rax, rdi
0x1800a43a7  mov     [rbx+18h], rax
0x1800a43ab  call    cs:__imp_GetCurrentThreadId
0x1800a43b1  mov     [rbx+20h], eax
0x1800a43b4  mov     [rbx+38h], r13
0x1800a43b8  mov     eax, [rsp+78h+arg_8]
0x1800a43bf  mov     [rbx+40h], eax
0x1800a43c2  mov     [rbx+44h], ebp
0x1800a43c5  mov     rax, [rsp+78h+arg_20]
0x1800a43cd  mov     [rbx+28h], rax
0x1800a43d1  mov     [rbx+30h], r12
0x1800a43d5  mov     rax, [rsp+78h+arg_28]
0x1800a43dd  mov     [rbx+88h], rax
0x1800a43e4  mov     rax, [rsp+78h+arg_0]
0x1800a43ec  mov     [rbx+90h], rax
0x1800a43f3  mov     [rbx+48h], rdi
0x1800a43f7  xorps   xmm0, xmm0
0x1800a43fa  xor     eax, eax
0x1800a43fc  movups  xmmword ptr [rbx+68h], xmm0
0x1800a4400  mov     [rbx+78h], rax
0x1800a4404  movups  xmmword ptr [rbx+50h], xmm0
0x1800a4408  mov     [rbx+60h], rax
0x1800a440c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x1800a4413  test    rax, rax
0x1800a4416  jz      short loc_1800A441F
0x1800a4418  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a441d  jmp     short loc_1800A4422
0x1800a441f  mov     rax, rdi
0x1800a4422  mov     [rbx+80h], rax
0x1800a4429  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x1800a4430  test    rax, rax
0x1800a4433  jz      short loc_1800A443D
0x1800a4435  mov     rcx, rbx
0x1800a4438  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a443d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x1800a4444  test    rax, rax
0x1800a4447  jz      short loc_1800A445F
0x1800a4449  mov     r8d, 400h
0x1800a444f  mov     rdx, [rsp+78h+arg_60]
0x1800a4457  mov     rcx, rbx
0x1800a445a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a445f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a4466  test    rax, rax
0x1800a4469  jz      short loc_1800A4473
0x1800a446b  mov     rcx, rbx
0x1800a446e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4473  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x1800a447a  test    rax, rax
0x1800a447d  jz      short loc_1800A448D
0x1800a447f  test    byte ptr [rbx+4], 2
0x1800a4483  jnz     short loc_1800A448D
0x1800a4485  mov     rcx, rbx
0x1800a4488  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a448d  cmp     [rbx+8], edi
0x1800a4490  jl      short loc_1800A44AC
0x1800a4492  cmp     r15d, 3
0x1800a4496  jnz     loc_1800A457B
0x1800a449c  mov     ecx, 8000FFFFh; this
0x1800a44a1  mov     [rbx+8], ecx
0x1800a44a4  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800a44a9  mov     [rbx+0Ch], eax
0x1800a44ac  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800a44b3  jnz     short loc_1800A44D4
0x1800a44b5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800a44bc  test    rax, rax
0x1800a44bf  jz      short loc_1800A44CA
0x1800a44c1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a44c6  test    al, al
0x1800a44c8  jmp     short loc_1800A44D2
0x1800a44ca  call    cs:__imp_IsDebuggerPresent
0x1800a44d0  test    eax, eax
0x1800a44d2  jz      short loc_1800A44DA
0x1800a44d4  test    byte ptr [rbx+4], 2
0x1800a44d8  jz      short loc_1800A44FE
0x1800a44da  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a44e1  test    rax, rax
0x1800a44e4  jz      short loc_1800A4542
0x1800a44e6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a44ed  jnz     short loc_1800A4542
0x1800a44ef  xor     r8d, r8d
0x1800a44f2  xor     edx, edx
0x1800a44f4  mov     rcx, rbx
0x1800a44f7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a44fc  jmp     short loc_1800A4542
0x1800a44fe  mov     ebp, 800h
0x1800a4503  mov     rax, cs:g_pfnResultLoggingCallback
0x1800a450a  test    rax, rax
0x1800a450d  jz      short loc_1800A4526
0x1800a450f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800a4516  jnz     short loc_1800A4526
0x1800a4518  mov     r8d, ebp
0x1800a451b  mov     rdx, rsi
0x1800a451e  mov     rcx, rbx
0x1800a4521  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4526  cmp     [rsi], di
0x1800a4529  jnz     short loc_1800A4539
0x1800a452b  mov     r8, rbx; unsigned __int64
0x1800a452e  mov     rdx, rbp; wchar_t *
0x1800a4531  mov     rcx, rsi; this
0x1800a4534  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x1800a4539  mov     rcx, rsi; lpOutputString
0x1800a453c  call    cs:__imp_OutputDebugStringW
0x1800a4542  test    byte ptr [rbx+4], 4
0x1800a4546  jnz     short loc_1800A4551
0x1800a4548  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800a454f  jz      short loc_1800A4563
0x1800a4551  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800a4558  test    rax, rax
0x1800a455b  jz      short loc_1800A4563
0x1800a455d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800a4562  nop
0x1800a4563  mov     rbx, [rsp+78h+arg_10]
0x1800a456b  add     rsp, 40h
0x1800a456f  pop     r15
0x1800a4571  pop     r14
0x1800a4573  pop     r13
0x1800a4575  pop     r12
0x1800a4577  pop     rdi
0x1800a4578  pop     rsi
0x1800a4579  pop     rbp
0x1800a457a  retn
0x1800a457b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
