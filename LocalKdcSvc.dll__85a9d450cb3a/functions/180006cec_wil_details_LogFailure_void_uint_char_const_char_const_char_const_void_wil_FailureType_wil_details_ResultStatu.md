# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006cec`
- end: `0x180006fe5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x180004510`
- `0x180004854`

## callees

- `0x180004450`
- `0x1800060d4`
- `0x180006904`
- `0x180006cec`
- `0x180007a58`
- `0x180007a80`
- `0x180007bcc`
- `0x180007be8`
- `0x180009714`
- `0x18009c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e0f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006e0f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006fa0`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006fa0`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006f2e`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180006f2e`

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
        WCHAR *lpOutputString,
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

  *lpOutputString = 0;
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
    if ( !*lpOutputString )
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v25);
    OutputDebugStringW(lpOutputString);
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
0x180006cec  mov     [rsp+arg_10], rbx
0x180006cf1  mov     [rsp+arg_8], edx
0x180006cf5  mov     [rsp+arg_0], rcx
0x180006cfa  push    rbp
0x180006cfb  push    rsi
0x180006cfc  push    rdi
0x180006cfd  push    r12
0x180006cff  push    r13
0x180006d01  push    r14
0x180006d03  push    r15
0x180006d05  sub     rsp, 40h
0x180006d09  mov     r12, r9
0x180006d0c  mov     r13, r8
0x180006d0f  mov     r10, rcx
0x180006d12  xor     eax, eax
0x180006d14  mov     rsi, [rsp+78h+lpOutputString]
0x180006d1c  mov     [rsi], ax
0x180006d1f  mov     rax, [rsp+78h+arg_60]
0x180006d27  mov     byte ptr [rax], 0
0x180006d2a  mov     r14, [rsp+78h+arg_38]
0x180006d32  mov     edi, [r14]
0x180006d35  mov     rbx, [rsp+78h+arg_78]
0x180006d3d  mov     [rbx+8], edi
0x180006d40  mov     eax, [r14+4]
0x180006d44  mov     [rbx+0Ch], eax
0x180006d47  xor     ebp, ebp
0x180006d49  mov     r15d, [rsp+78h+arg_30]
0x180006d51  mov     ecx, r15d
0x180006d54  test    r15d, r15d
0x180006d57  jz      short loc_180006DBF
0x180006d59  sub     ecx, 1
0x180006d5c  jz      short loc_180006DB6
0x180006d5e  sub     ecx, 1
0x180006d61  jz      short loc_180006D71
0x180006d63  cmp     ecx, 1
0x180006d66  jnz     short loc_180006DC8
0x180006d68  mov     ecx, edi; this
0x180006d6a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006d6f  jmp     short loc_180006DC6
0x180006d71  test    edi, edi
0x180006d73  js      short loc_180006DAD
0x180006d75  mov     edi, 8007029Ch
0x180006d7a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006d7e  mov     rax, [rsp+78h+arg_28]
0x180006d86  mov     [rsp+78h+var_50], rax; __int64
0x180006d8b  mov     rax, [rsp+78h+arg_20]
0x180006d93  mov     [rsp+78h+var_58], rax; __int64
0x180006d98  mov     rcx, r10; int
0x180006d9b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006da0  mov     [rbx+8], edi
0x180006da3  mov     ecx, edi; this
0x180006da5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006daa  mov     [rbx+0Ch], eax
0x180006dad  mov     ecx, edi; this
0x180006daf  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006db4  jmp     short loc_180006DC6
0x180006db6  mov     ecx, edi; this
0x180006db8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006dbd  jmp     short loc_180006DC6
0x180006dbf  mov     ecx, edi; this
0x180006dc1  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006dc6  mov     ebp, eax
0x180006dc8  mov     [rbx], r15d
0x180006dcb  mov     eax, [rsp+78h+arg_70]
0x180006dd2  mov     [rbx+4], eax
0x180006dd5  cmp     dword ptr [r14+8], 1
0x180006dda  jnz     short loc_180006DE2
0x180006ddc  or      eax, 8
0x180006ddf  mov     [rbx+4], eax
0x180006de2  mov     eax, 1
0x180006de7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006def  inc     eax
0x180006df1  mov     [rbx+10h], eax
0x180006df4  mov     rax, [rsp+78h+arg_40]
0x180006dfc  xor     edi, edi
0x180006dfe  test    rax, rax
0x180006e01  jz      short loc_180006E08
0x180006e03  cmp     [rax], di
0x180006e06  jnz     short loc_180006E0B
0x180006e08  mov     rax, rdi
0x180006e0b  mov     [rbx+18h], rax
0x180006e0f  call    cs:__imp_GetCurrentThreadId
0x180006e15  mov     [rbx+20h], eax
0x180006e18  mov     [rbx+38h], r13
0x180006e1c  mov     eax, [rsp+78h+arg_8]
0x180006e23  mov     [rbx+40h], eax
0x180006e26  mov     [rbx+44h], ebp
0x180006e29  mov     rax, [rsp+78h+arg_20]
0x180006e31  mov     [rbx+28h], rax
0x180006e35  mov     [rbx+30h], r12
0x180006e39  mov     rax, [rsp+78h+arg_28]
0x180006e41  mov     [rbx+88h], rax
0x180006e48  mov     rax, [rsp+78h+arg_0]
0x180006e50  mov     [rbx+90h], rax
0x180006e57  mov     [rbx+48h], rdi
0x180006e5b  xorps   xmm0, xmm0
0x180006e5e  xor     eax, eax
0x180006e60  movups  xmmword ptr [rbx+68h], xmm0
0x180006e64  mov     [rbx+78h], rax
0x180006e68  movups  xmmword ptr [rbx+50h], xmm0
0x180006e6c  mov     [rbx+60h], rax
0x180006e70  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006e77  test    rax, rax
0x180006e7a  jz      short loc_180006E83
0x180006e7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e81  jmp     short loc_180006E86
0x180006e83  mov     rax, rdi
0x180006e86  mov     [rbx+80h], rax
0x180006e8d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006e94  test    rax, rax
0x180006e97  jz      short loc_180006EA1
0x180006e99  mov     rcx, rbx
0x180006e9c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ea1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006ea8  test    rax, rax
0x180006eab  jz      short loc_180006EC3
0x180006ead  mov     r8d, 400h
0x180006eb3  mov     rdx, [rsp+78h+arg_60]
0x180006ebb  mov     rcx, rbx
0x180006ebe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec3  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006eca  test    rax, rax
0x180006ecd  jz      short loc_180006ED7
0x180006ecf  mov     rcx, rbx
0x180006ed2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ed7  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ede  test    rax, rax
0x180006ee1  jz      short loc_180006EF1
0x180006ee3  test    byte ptr [rbx+4], 2
0x180006ee7  jnz     short loc_180006EF1
0x180006ee9  mov     rcx, rbx
0x180006eec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ef1  cmp     [rbx+8], edi
0x180006ef4  jl      short loc_180006F10
0x180006ef6  cmp     r15d, 3
0x180006efa  jnz     loc_180006FDF
0x180006f00  mov     ecx, 8000FFFFh; this
0x180006f05  mov     [rbx+8], ecx
0x180006f08  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006f0d  mov     [rbx+0Ch], eax
0x180006f10  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180006f17  jnz     short loc_180006F38
0x180006f19  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180006f20  test    rax, rax
0x180006f23  jz      short loc_180006F2E
0x180006f25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f2a  test    al, al
0x180006f2c  jmp     short loc_180006F36
0x180006f2e  call    cs:__imp_IsDebuggerPresent
0x180006f34  test    eax, eax
0x180006f36  jz      short loc_180006F3E
0x180006f38  test    byte ptr [rbx+4], 2
0x180006f3c  jz      short loc_180006F62
0x180006f3e  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f45  test    rax, rax
0x180006f48  jz      short loc_180006FA6
0x180006f4a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006f51  jnz     short loc_180006FA6
0x180006f53  xor     r8d, r8d
0x180006f56  xor     edx, edx
0x180006f58  mov     rcx, rbx
0x180006f5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f60  jmp     short loc_180006FA6
0x180006f62  mov     ebp, 800h
0x180006f67  mov     rax, cs:g_pfnResultLoggingCallback
0x180006f6e  test    rax, rax
0x180006f71  jz      short loc_180006F8A
0x180006f73  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180006f7a  jnz     short loc_180006F8A
0x180006f7c  mov     r8d, ebp
0x180006f7f  mov     rdx, rsi
0x180006f82  mov     rcx, rbx
0x180006f85  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f8a  cmp     [rsi], di
0x180006f8d  jnz     short loc_180006F9D
0x180006f8f  mov     r8, rbx; unsigned __int64
0x180006f92  mov     rdx, rbp; unsigned __int16 *
0x180006f95  mov     rcx, rsi; pszDest
0x180006f98  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006f9d  mov     rcx, rsi; lpOutputString
0x180006fa0  call    cs:__imp_OutputDebugStringW
0x180006fa6  test    byte ptr [rbx+4], 4
0x180006faa  jnz     short loc_180006FB5
0x180006fac  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006fb3  jz      short loc_180006FC7
0x180006fb5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006fbc  test    rax, rax
0x180006fbf  jz      short loc_180006FC7
0x180006fc1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fc6  nop
0x180006fc7  mov     rbx, [rsp+78h+arg_10]
0x180006fcf  add     rsp, 40h
0x180006fd3  pop     r15
0x180006fd5  pop     r14
0x180006fd7  pop     r13
0x180006fd9  pop     r12
0x180006fdb  pop     rdi
0x180006fdc  pop     rsi
0x180006fdd  pop     rbp
0x180006fde  retn
0x180006fdf  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
