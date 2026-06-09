# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180006e08`
- end: `0x180007100`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x1800056f4`
- `0x180005a38`

## callees

- `0x180005634`
- `0x180006434`
- `0x180006c18`
- `0x180006e08`
- `0x180007458`
- `0x180007480`
- `0x180007494`
- `0x1800074b0`
- `0x180007ed4`
- `0x180059010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180006f2b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000704a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000704a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070bc`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x1800070bc`

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
  int v21; // edx
  _WORD *v22; // rax
  DWORD CurrentThreadId; // eax
  int v24; // edx
  wil::details::in1diag3 *v25; // rcx
  const struct wil::FailureInfo *v26; // r9
  __int64 ModuleName; // rax
  bool v28; // zf
  wil::details *v29; // [rsp+30h] [rbp-48h]

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
          LODWORD(v29) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v29);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL, v21);
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
  v22 = a9;
  if ( !a9 || !*a9 )
    v22 = 0;
  *(_QWORD *)(a16 + 24) = v22;
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v25);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL, v24);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v28 = !IsDebuggerPresent())
      : (v28 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
        v28)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v26);
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
0x180006e08  mov     [rsp+arg_10], rbx
0x180006e0d  mov     [rsp+arg_8], edx
0x180006e11  mov     [rsp+arg_0], rcx
0x180006e16  push    rbp
0x180006e17  push    rsi
0x180006e18  push    rdi
0x180006e19  push    r12
0x180006e1b  push    r13
0x180006e1d  push    r14
0x180006e1f  push    r15
0x180006e21  sub     rsp, 40h
0x180006e25  mov     r14, [rsp+78h+arg_38]
0x180006e2d  xor     eax, eax
0x180006e2f  mov     rbx, [rsp+78h+arg_78]
0x180006e37  xor     ebp, ebp
0x180006e39  mov     r15d, [rsp+78h+arg_30]
0x180006e41  mov     r10, rcx
0x180006e44  mov     rsi, [rsp+78h+lpOutputString]
0x180006e4c  mov     r12, r9
0x180006e4f  mov     r13, r8
0x180006e52  mov     ecx, r15d
0x180006e55  mov     [rsi], ax
0x180006e58  mov     rax, [rsp+78h+arg_60]
0x180006e60  mov     byte ptr [rax], 0
0x180006e63  mov     edi, [r14]
0x180006e66  mov     [rbx+8], edi
0x180006e69  mov     eax, [r14+4]
0x180006e6d  mov     [rbx+0Ch], eax
0x180006e70  test    r15d, r15d
0x180006e73  jz      short loc_180006EDB
0x180006e75  sub     ecx, 1
0x180006e78  jz      short loc_180006ED2
0x180006e7a  sub     ecx, 1
0x180006e7d  jz      short loc_180006E8D
0x180006e7f  cmp     ecx, 1
0x180006e82  jnz     short loc_180006EE4
0x180006e84  mov     ecx, edi; this
0x180006e86  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180006e8b  jmp     short loc_180006EE2
0x180006e8d  test    edi, edi
0x180006e8f  js      short loc_180006EC9
0x180006e91  mov     rax, [rsp+78h+arg_28]
0x180006e99  mov     edi, 8007029Ch
0x180006e9e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180006ea2  mov     rcx, r10; int
0x180006ea5  mov     [rsp+78h+var_50], rax; __int64
0x180006eaa  mov     rax, [rsp+78h+arg_20]
0x180006eb2  mov     [rsp+78h+var_58], rax; __int64
0x180006eb7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180006ebc  mov     ecx, edi; this
0x180006ebe  mov     [rbx+8], edi
0x180006ec1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180006ec6  mov     [rbx+0Ch], eax
0x180006ec9  mov     ecx, edi; this
0x180006ecb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180006ed0  jmp     short loc_180006EE2
0x180006ed2  mov     ecx, edi; this
0x180006ed4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180006ed9  jmp     short loc_180006EE2
0x180006edb  mov     ecx, edi; this
0x180006edd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180006ee2  mov     ebp, eax
0x180006ee4  mov     eax, [rsp+78h+arg_70]
0x180006eeb  mov     [rbx+4], eax
0x180006eee  mov     [rbx], r15d
0x180006ef1  cmp     dword ptr [r14+8], 1
0x180006ef6  jnz     short loc_180006EFE
0x180006ef8  or      eax, 8
0x180006efb  mov     [rbx+4], eax
0x180006efe  mov     eax, 1
0x180006f03  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180006f0b  inc     eax
0x180006f0d  xor     edi, edi
0x180006f0f  mov     [rbx+10h], eax
0x180006f12  mov     rax, [rsp+78h+arg_40]
0x180006f1a  test    rax, rax
0x180006f1d  jz      short loc_180006F24
0x180006f1f  cmp     [rax], di
0x180006f22  jnz     short loc_180006F27
0x180006f24  mov     rax, rdi
0x180006f27  mov     [rbx+18h], rax
0x180006f2b  call    cs:__imp_GetCurrentThreadId
0x180006f31  mov     [rbx+38h], r13
0x180006f35  xorps   xmm0, xmm0
0x180006f38  mov     [rbx+20h], eax
0x180006f3b  mov     eax, [rsp+78h+arg_8]
0x180006f42  mov     [rbx+40h], eax
0x180006f45  mov     rax, [rsp+78h+arg_20]
0x180006f4d  mov     [rbx+28h], rax
0x180006f51  mov     rax, [rsp+78h+arg_28]
0x180006f59  mov     [rbx+88h], rax
0x180006f60  mov     rax, [rsp+78h+arg_0]
0x180006f68  mov     [rbx+90h], rax
0x180006f6f  xor     eax, eax
0x180006f71  mov     [rbx+44h], ebp
0x180006f74  mov     [rbx+30h], r12
0x180006f78  mov     [rbx+48h], rdi
0x180006f7c  movups  xmmword ptr [rbx+68h], xmm0
0x180006f80  mov     [rbx+78h], rax
0x180006f84  movups  xmmword ptr [rbx+50h], xmm0
0x180006f88  mov     [rbx+60h], rax
0x180006f8c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180006f93  test    rax, rax
0x180006f96  jz      short loc_180006F9F
0x180006f98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006f9d  jmp     short loc_180006FA2
0x180006f9f  mov     rax, rdi
0x180006fa2  mov     [rbx+80h], rax
0x180006fa9  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180006fb0  test    rax, rax
0x180006fb3  jz      short loc_180006FBD
0x180006fb5  mov     rcx, rbx
0x180006fb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fbd  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180006fc4  test    rax, rax
0x180006fc7  jz      short loc_180006FDF
0x180006fc9  mov     rdx, [rsp+78h+arg_60]
0x180006fd1  mov     r8d, 400h
0x180006fd7  mov     rcx, rbx
0x180006fda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006fdf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006fe6  test    rax, rax
0x180006fe9  jz      short loc_180006FF3
0x180006feb  mov     rcx, rbx
0x180006fee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ff3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180006ffa  test    rax, rax
0x180006ffd  jz      short loc_18000700D
0x180006fff  test    byte ptr [rbx+4], 2
0x180007003  jnz     short loc_18000700D
0x180007005  mov     rcx, rbx
0x180007008  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000700d  cmp     [rbx+8], edi
0x180007010  jl      short loc_18000702C
0x180007012  cmp     r15d, 3
0x180007016  jnz     loc_1800070FA
0x18000701c  mov     ecx, 8000FFFFh; this
0x180007021  mov     [rbx+8], ecx
0x180007024  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007029  mov     [rbx+0Ch], eax
0x18000702c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007033  jnz     short loc_180007054
0x180007035  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000703c  test    rax, rax
0x18000703f  jz      short loc_18000704A
0x180007041  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007046  test    al, al
0x180007048  jmp     short loc_180007052
0x18000704a  call    cs:__imp_IsDebuggerPresent
0x180007050  test    eax, eax
0x180007052  jz      short loc_18000705A
0x180007054  test    byte ptr [rbx+4], 2
0x180007058  jz      short loc_18000707E
0x18000705a  mov     rax, cs:g_pfnResultLoggingCallback
0x180007061  test    rax, rax
0x180007064  jz      short loc_1800070C2
0x180007066  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000706d  jnz     short loc_1800070C2
0x18000706f  xor     r8d, r8d
0x180007072  xor     edx, edx
0x180007074  mov     rcx, rbx
0x180007077  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000707c  jmp     short loc_1800070C2
0x18000707e  mov     rax, cs:g_pfnResultLoggingCallback
0x180007085  mov     ebp, 800h
0x18000708a  test    rax, rax
0x18000708d  jz      short loc_1800070A6
0x18000708f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007096  jnz     short loc_1800070A6
0x180007098  mov     r8d, ebp
0x18000709b  mov     rdx, rsi
0x18000709e  mov     rcx, rbx
0x1800070a1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070a6  cmp     [rsi], di
0x1800070a9  jnz     short loc_1800070B9
0x1800070ab  mov     r8, rbx; unsigned __int64
0x1800070ae  mov     rdx, rbp; unsigned __int16 *
0x1800070b1  mov     rcx, rsi; this
0x1800070b4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x1800070b9  mov     rcx, rsi; lpOutputString
0x1800070bc  call    cs:__imp_OutputDebugStringW
0x1800070c2  test    byte ptr [rbx+4], 4
0x1800070c6  jnz     short loc_1800070D1
0x1800070c8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800070cf  jz      short loc_1800070E2
0x1800070d1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800070d8  test    rax, rax
0x1800070db  jz      short loc_1800070E2
0x1800070dd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070e2  mov     rbx, [rsp+78h+arg_10]
0x1800070ea  add     rsp, 40h
0x1800070ee  pop     r15
0x1800070f0  pop     r14
0x1800070f2  pop     r13
0x1800070f4  pop     r12
0x1800070f6  pop     rdi
0x1800070f7  pop     rsi
0x1800070f8  pop     rbp
0x1800070f9  retn
0x1800070fa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
