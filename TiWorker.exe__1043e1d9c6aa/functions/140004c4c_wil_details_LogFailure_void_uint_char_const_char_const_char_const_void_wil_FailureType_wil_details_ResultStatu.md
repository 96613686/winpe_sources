# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x140004c4c`
- end: `0x140004f44`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1400035c0`
- `0x140003904`

## callees

- `0x140003500`
- `0x140004294`
- `0x140004a88`
- `0x140004c4c`
- `0x1400052c0`
- `0x1400052e0`
- `0x1400052f4`
- `0x140005310`
- `0x140005cc8`
- `0x14002b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004d6f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x140004d6f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f00`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x140004f00`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004e8e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x140004e8e`

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
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v24);
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
0x140004c4c  mov     [rsp+arg_10], rbx
0x140004c51  mov     [rsp+arg_8], edx
0x140004c55  mov     [rsp+arg_0], rcx
0x140004c5a  push    rbp
0x140004c5b  push    rsi
0x140004c5c  push    rdi
0x140004c5d  push    r12
0x140004c5f  push    r13
0x140004c61  push    r14
0x140004c63  push    r15
0x140004c65  sub     rsp, 40h
0x140004c69  mov     r14, [rsp+78h+arg_38]
0x140004c71  xor     eax, eax
0x140004c73  mov     rbx, [rsp+78h+arg_78]
0x140004c7b  xor     ebp, ebp
0x140004c7d  mov     r15d, [rsp+78h+arg_30]
0x140004c85  mov     r10, rcx
0x140004c88  mov     rsi, [rsp+78h+lpOutputString]
0x140004c90  mov     r12, r9
0x140004c93  mov     r13, r8
0x140004c96  mov     ecx, r15d
0x140004c99  mov     [rsi], ax
0x140004c9c  mov     rax, [rsp+78h+arg_60]
0x140004ca4  mov     byte ptr [rax], 0
0x140004ca7  mov     edi, [r14]
0x140004caa  mov     [rbx+8], edi
0x140004cad  mov     eax, [r14+4]
0x140004cb1  mov     [rbx+0Ch], eax
0x140004cb4  test    r15d, r15d
0x140004cb7  jz      short loc_140004D1F
0x140004cb9  sub     ecx, 1
0x140004cbc  jz      short loc_140004D16
0x140004cbe  sub     ecx, 1
0x140004cc1  jz      short loc_140004CD1
0x140004cc3  cmp     ecx, 1
0x140004cc6  jnz     short loc_140004D28
0x140004cc8  mov     ecx, edi; this
0x140004cca  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140004ccf  jmp     short loc_140004D26
0x140004cd1  test    edi, edi
0x140004cd3  js      short loc_140004D0D
0x140004cd5  mov     rax, [rsp+78h+arg_28]
0x140004cdd  mov     edi, 8007029Ch
0x140004ce2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140004ce6  mov     rcx, r10; int
0x140004ce9  mov     [rsp+78h+var_50], rax; __int64
0x140004cee  mov     rax, [rsp+78h+arg_20]
0x140004cf6  mov     [rsp+78h+var_58], rax; __int64
0x140004cfb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140004d00  mov     ecx, edi; this
0x140004d02  mov     [rbx+8], edi
0x140004d05  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004d0a  mov     [rbx+0Ch], eax
0x140004d0d  mov     ecx, edi; this
0x140004d0f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140004d14  jmp     short loc_140004D26
0x140004d16  mov     ecx, edi; this
0x140004d18  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140004d1d  jmp     short loc_140004D26
0x140004d1f  mov     ecx, edi; this
0x140004d21  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140004d26  mov     ebp, eax
0x140004d28  mov     eax, [rsp+78h+arg_70]
0x140004d2f  mov     [rbx+4], eax
0x140004d32  mov     [rbx], r15d
0x140004d35  cmp     dword ptr [r14+8], 1
0x140004d3a  jnz     short loc_140004D42
0x140004d3c  or      eax, 8
0x140004d3f  mov     [rbx+4], eax
0x140004d42  mov     eax, 1
0x140004d47  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140004d4f  inc     eax
0x140004d51  xor     edi, edi
0x140004d53  mov     [rbx+10h], eax
0x140004d56  mov     rax, [rsp+78h+arg_40]
0x140004d5e  test    rax, rax
0x140004d61  jz      short loc_140004D68
0x140004d63  cmp     [rax], di
0x140004d66  jnz     short loc_140004D6B
0x140004d68  mov     rax, rdi
0x140004d6b  mov     [rbx+18h], rax
0x140004d6f  call    cs:__imp_GetCurrentThreadId
0x140004d75  mov     [rbx+38h], r13
0x140004d79  xorps   xmm0, xmm0
0x140004d7c  mov     [rbx+20h], eax
0x140004d7f  mov     eax, [rsp+78h+arg_8]
0x140004d86  mov     [rbx+40h], eax
0x140004d89  mov     rax, [rsp+78h+arg_20]
0x140004d91  mov     [rbx+28h], rax
0x140004d95  mov     rax, [rsp+78h+arg_28]
0x140004d9d  mov     [rbx+88h], rax
0x140004da4  mov     rax, [rsp+78h+arg_0]
0x140004dac  mov     [rbx+90h], rax
0x140004db3  xor     eax, eax
0x140004db5  mov     [rbx+44h], ebp
0x140004db8  mov     [rbx+30h], r12
0x140004dbc  mov     [rbx+48h], rdi
0x140004dc0  movups  xmmword ptr [rbx+68h], xmm0
0x140004dc4  mov     [rbx+78h], rax
0x140004dc8  movups  xmmword ptr [rbx+50h], xmm0
0x140004dcc  mov     [rbx+60h], rax
0x140004dd0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140004dd7  test    rax, rax
0x140004dda  jz      short loc_140004DE3
0x140004ddc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004de1  jmp     short loc_140004DE6
0x140004de3  mov     rax, rdi
0x140004de6  mov     [rbx+80h], rax
0x140004ded  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140004df4  test    rax, rax
0x140004df7  jz      short loc_140004E01
0x140004df9  mov     rcx, rbx
0x140004dfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e01  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140004e08  test    rax, rax
0x140004e0b  jz      short loc_140004E23
0x140004e0d  mov     rdx, [rsp+78h+arg_60]
0x140004e15  mov     r8d, 400h
0x140004e1b  mov     rcx, rbx
0x140004e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e23  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004e2a  test    rax, rax
0x140004e2d  jz      short loc_140004E37
0x140004e2f  mov     rcx, rbx
0x140004e32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e37  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140004e3e  test    rax, rax
0x140004e41  jz      short loc_140004E51
0x140004e43  test    byte ptr [rbx+4], 2
0x140004e47  jnz     short loc_140004E51
0x140004e49  mov     rcx, rbx
0x140004e4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e51  cmp     [rbx+8], edi
0x140004e54  jl      short loc_140004E70
0x140004e56  cmp     r15d, 3
0x140004e5a  jnz     loc_140004F3E
0x140004e60  mov     ecx, 8000FFFFh; this
0x140004e65  mov     [rbx+8], ecx
0x140004e68  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140004e6d  mov     [rbx+0Ch], eax
0x140004e70  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140004e77  jnz     short loc_140004E98
0x140004e79  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140004e80  test    rax, rax
0x140004e83  jz      short loc_140004E8E
0x140004e85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004e8a  test    al, al
0x140004e8c  jmp     short loc_140004E96
0x140004e8e  call    cs:__imp_IsDebuggerPresent
0x140004e94  test    eax, eax
0x140004e96  jz      short loc_140004E9E
0x140004e98  test    byte ptr [rbx+4], 2
0x140004e9c  jz      short loc_140004EC2
0x140004e9e  mov     rax, cs:g_pfnResultLoggingCallback
0x140004ea5  test    rax, rax
0x140004ea8  jz      short loc_140004F06
0x140004eaa  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004eb1  jnz     short loc_140004F06
0x140004eb3  xor     r8d, r8d
0x140004eb6  xor     edx, edx
0x140004eb8  mov     rcx, rbx
0x140004ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004ec0  jmp     short loc_140004F06
0x140004ec2  mov     rax, cs:g_pfnResultLoggingCallback
0x140004ec9  mov     ebp, 800h
0x140004ece  test    rax, rax
0x140004ed1  jz      short loc_140004EEA
0x140004ed3  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140004eda  jnz     short loc_140004EEA
0x140004edc  mov     r8d, ebp
0x140004edf  mov     rdx, rsi
0x140004ee2  mov     rcx, rbx
0x140004ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004eea  cmp     [rsi], di
0x140004eed  jnz     short loc_140004EFD
0x140004eef  mov     r8, rbx; unsigned __int64
0x140004ef2  mov     rdx, rbp; wchar_t *
0x140004ef5  mov     rcx, rsi; this
0x140004ef8  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x140004efd  mov     rcx, rsi; lpOutputString
0x140004f00  call    cs:__imp_OutputDebugStringW
0x140004f06  test    byte ptr [rbx+4], 4
0x140004f0a  jnz     short loc_140004F15
0x140004f0c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140004f13  jz      short loc_140004F26
0x140004f15  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140004f1c  test    rax, rax
0x140004f1f  jz      short loc_140004F26
0x140004f21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140004f26  mov     rbx, [rsp+78h+arg_10]
0x140004f2e  add     rsp, 40h
0x140004f32  pop     r15
0x140004f34  pop     r14
0x140004f36  pop     r13
0x140004f38  pop     r12
0x140004f3a  pop     rdi
0x140004f3b  pop     rsi
0x140004f3c  pop     rbp
0x140004f3d  retn
0x140004f3e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
