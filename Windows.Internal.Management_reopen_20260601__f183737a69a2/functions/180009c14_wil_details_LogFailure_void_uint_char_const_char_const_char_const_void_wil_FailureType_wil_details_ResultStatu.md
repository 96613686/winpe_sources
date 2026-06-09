# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180009c14`
- end: `0x180009f20`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800080fc`
- `0x18000847c`
- `0x18001c664`

## callees

- `0x180008034`
- `0x1800091d4`
- `0x180009a20`
- `0x180009c14`
- `0x18000a334`
- `0x18000a360`
- `0x18000a374`
- `0x18000a394`
- `0x18000b294`
- `0x1800bb010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d37`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180009d37`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009ed4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180009ed4`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009e5c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180009e5c`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v24);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v23);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v27 = !IsDebuggerPresent())
      : (v27 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::details::g_pfnDebugBreak();
  }
}

```

## disassembly

```asm
0x180009c14  mov     [rsp+arg_10], rbx
0x180009c19  mov     [rsp+arg_8], edx
0x180009c1d  mov     [rsp+arg_0], rcx
0x180009c22  push    rbp
0x180009c23  push    rsi
0x180009c24  push    rdi
0x180009c25  push    r12
0x180009c27  push    r13
0x180009c29  push    r14
0x180009c2b  push    r15
0x180009c2d  sub     rsp, 40h
0x180009c31  mov     r12, r9
0x180009c34  mov     r13, r8
0x180009c37  mov     r10, rcx
0x180009c3a  xor     eax, eax
0x180009c3c  mov     rsi, [rsp+78h+lpOutputString]
0x180009c44  mov     [rsi], ax
0x180009c47  mov     rax, [rsp+78h+arg_60]
0x180009c4f  mov     byte ptr [rax], 0
0x180009c52  mov     r14, [rsp+78h+arg_38]
0x180009c5a  mov     edi, [r14]
0x180009c5d  mov     rbx, [rsp+78h+arg_78]
0x180009c65  mov     [rbx+8], edi
0x180009c68  mov     eax, [r14+4]
0x180009c6c  mov     [rbx+0Ch], eax
0x180009c6f  xor     ebp, ebp
0x180009c71  mov     r15d, [rsp+78h+arg_30]
0x180009c79  mov     ecx, r15d
0x180009c7c  test    r15d, r15d
0x180009c7f  jz      short loc_180009CE7
0x180009c81  sub     ecx, 1
0x180009c84  jz      short loc_180009CDE
0x180009c86  sub     ecx, 1
0x180009c89  jz      short loc_180009C99
0x180009c8b  cmp     ecx, 1
0x180009c8e  jnz     short loc_180009CF0
0x180009c90  mov     ecx, edi; this
0x180009c92  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180009c97  jmp     short loc_180009CEE
0x180009c99  test    edi, edi
0x180009c9b  js      short loc_180009CD5
0x180009c9d  mov     edi, 8007029Ch
0x180009ca2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180009ca6  mov     rax, [rsp+78h+arg_28]
0x180009cae  mov     [rsp+78h+var_50], rax; __int64
0x180009cb3  mov     rax, [rsp+78h+arg_20]
0x180009cbb  mov     [rsp+78h+var_58], rax; __int64
0x180009cc0  mov     rcx, r10; int
0x180009cc3  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180009cc8  mov     [rbx+8], edi
0x180009ccb  mov     ecx, edi; this
0x180009ccd  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009cd2  mov     [rbx+0Ch], eax
0x180009cd5  mov     ecx, edi; this
0x180009cd7  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180009cdc  jmp     short loc_180009CEE
0x180009cde  mov     ecx, edi; this
0x180009ce0  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180009ce5  jmp     short loc_180009CEE
0x180009ce7  mov     ecx, edi; this
0x180009ce9  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180009cee  mov     ebp, eax
0x180009cf0  mov     [rbx], r15d
0x180009cf3  mov     eax, [rsp+78h+arg_70]
0x180009cfa  mov     [rbx+4], eax
0x180009cfd  cmp     dword ptr [r14+8], 1
0x180009d02  jnz     short loc_180009D0A
0x180009d04  or      eax, 8
0x180009d07  mov     [rbx+4], eax
0x180009d0a  mov     eax, 1
0x180009d0f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180009d17  inc     eax
0x180009d19  mov     [rbx+10h], eax
0x180009d1c  mov     rax, [rsp+78h+arg_40]
0x180009d24  xor     edi, edi
0x180009d26  test    rax, rax
0x180009d29  jz      short loc_180009D30
0x180009d2b  cmp     [rax], di
0x180009d2e  jnz     short loc_180009D33
0x180009d30  mov     rax, rdi
0x180009d33  mov     [rbx+18h], rax
0x180009d37  call    cs:__imp_GetCurrentThreadId
0x180009d3e  nop     dword ptr [rax+rax+00h]
0x180009d43  mov     [rbx+20h], eax
0x180009d46  mov     [rbx+38h], r13
0x180009d4a  mov     eax, [rsp+78h+arg_8]
0x180009d51  mov     [rbx+40h], eax
0x180009d54  mov     [rbx+44h], ebp
0x180009d57  mov     rax, [rsp+78h+arg_20]
0x180009d5f  mov     [rbx+28h], rax
0x180009d63  mov     [rbx+30h], r12
0x180009d67  mov     rax, [rsp+78h+arg_28]
0x180009d6f  mov     [rbx+88h], rax
0x180009d76  mov     rax, [rsp+78h+arg_0]
0x180009d7e  mov     [rbx+90h], rax
0x180009d85  mov     [rbx+48h], rdi
0x180009d89  xorps   xmm0, xmm0
0x180009d8c  xor     eax, eax
0x180009d8e  movups  xmmword ptr [rbx+68h], xmm0
0x180009d92  mov     [rbx+78h], rax
0x180009d96  movups  xmmword ptr [rbx+50h], xmm0
0x180009d9a  mov     [rbx+60h], rax
0x180009d9e  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180009da5  test    rax, rax
0x180009da8  jz      short loc_180009DB1
0x180009daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009daf  jmp     short loc_180009DB4
0x180009db1  mov     rax, rdi
0x180009db4  mov     [rbx+80h], rax
0x180009dbb  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180009dc2  test    rax, rax
0x180009dc5  jz      short loc_180009DCF
0x180009dc7  mov     rcx, rbx
0x180009dca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009dcf  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180009dd6  test    rax, rax
0x180009dd9  jz      short loc_180009DF1
0x180009ddb  mov     r8d, 400h
0x180009de1  mov     rdx, [rsp+78h+arg_60]
0x180009de9  mov     rcx, rbx
0x180009dec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df1  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009df8  test    rax, rax
0x180009dfb  jz      short loc_180009E05
0x180009dfd  mov     rcx, rbx
0x180009e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e05  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180009e0c  test    rax, rax
0x180009e0f  jz      short loc_180009E1F
0x180009e11  test    byte ptr [rbx+4], 2
0x180009e15  jnz     short loc_180009E1F
0x180009e17  mov     rcx, rbx
0x180009e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e1f  cmp     [rbx+8], edi
0x180009e22  jl      short loc_180009E3E
0x180009e24  cmp     r15d, 3
0x180009e28  jnz     loc_180009F1A
0x180009e2e  mov     ecx, 8000FFFFh; this
0x180009e33  mov     [rbx+8], ecx
0x180009e36  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180009e3b  mov     [rbx+0Ch], eax
0x180009e3e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180009e45  jnz     short loc_180009E6C
0x180009e47  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180009e4e  test    rax, rax
0x180009e51  jz      short loc_180009E5C
0x180009e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e58  test    al, al
0x180009e5a  jmp     short loc_180009E6A
0x180009e5c  call    cs:__imp_IsDebuggerPresent
0x180009e63  nop     dword ptr [rax+rax+00h]
0x180009e68  test    eax, eax
0x180009e6a  jz      short loc_180009E72
0x180009e6c  test    byte ptr [rbx+4], 2
0x180009e70  jz      short loc_180009E96
0x180009e72  mov     rax, cs:g_pfnResultLoggingCallback
0x180009e79  test    rax, rax
0x180009e7c  jz      short loc_180009EE0
0x180009e7e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009e85  jnz     short loc_180009EE0
0x180009e87  xor     r8d, r8d
0x180009e8a  xor     edx, edx
0x180009e8c  mov     rcx, rbx
0x180009e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e94  jmp     short loc_180009EE0
0x180009e96  mov     ebp, 800h
0x180009e9b  mov     rax, cs:g_pfnResultLoggingCallback
0x180009ea2  test    rax, rax
0x180009ea5  jz      short loc_180009EBE
0x180009ea7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180009eae  jnz     short loc_180009EBE
0x180009eb0  mov     r8d, ebp
0x180009eb3  mov     rdx, rsi
0x180009eb6  mov     rcx, rbx
0x180009eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ebe  cmp     [rsi], di
0x180009ec1  jnz     short loc_180009ED1
0x180009ec3  mov     r8, rbx; unsigned __int64
0x180009ec6  mov     rdx, rbp; unsigned __int16 *
0x180009ec9  mov     rcx, rsi; this
0x180009ecc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180009ed1  mov     rcx, rsi; lpOutputString
0x180009ed4  call    cs:__imp_OutputDebugStringW
0x180009edb  nop     dword ptr [rax+rax+00h]
0x180009ee0  test    byte ptr [rbx+4], 4
0x180009ee4  jnz     short loc_180009EEF
0x180009ee6  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180009eed  jz      short loc_180009F01
0x180009eef  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180009ef6  test    rax, rax
0x180009ef9  jz      short loc_180009F01
0x180009efb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f00  nop
0x180009f01  mov     rbx, [rsp+78h+arg_10]
0x180009f09  add     rsp, 40h
0x180009f0d  pop     r15
0x180009f0f  pop     r14
0x180009f11  pop     r13
0x180009f13  pop     r12
0x180009f15  pop     rdi
0x180009f16  pop     rsi
0x180009f17  pop     rbp
0x180009f18  retn
0x180009f1a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
