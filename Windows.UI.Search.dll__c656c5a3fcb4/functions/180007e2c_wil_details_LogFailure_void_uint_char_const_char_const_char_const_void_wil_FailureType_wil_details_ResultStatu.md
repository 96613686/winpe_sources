# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007e2c`
- end: `0x180008106`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEB_W_NPEA_W_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `730`
- prototype: ``
- caller_count: `2`
- callee_count: `11`
- tags: ``

## callers

- `0x1800048b8`
- `0x180004bdc`

## callees

- `0x1800047f4`
- `0x180006f94`
- `0x180007920`
- `0x180007b94`
- `0x180007e2c`
- `0x180008ef4`
- `0x180008f10`
- `0x18000905c`
- `0x180009078`
- `0x18000b444`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007f4f`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000809d`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000809d`

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
  __int64 ModuleName; // rax
  __int64 v26; // rcx
  const struct wil::FailureInfo *v27; // r9
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
  if ( !wil::details::IsDebuggerPresent(v24) || (*(_BYTE *)(a16 + 4) & 2) != 0 )
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, 0, 0);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048);
    if ( !*(_WORD *)lpOutputString )
      wil::GetFailureLogString(lpOutputString, (wchar_t *)0x800, a16, v27);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v26);
  }
}

```

## disassembly

```asm
0x180007e2c  mov     [rsp+arg_10], rbx
0x180007e31  mov     [rsp+arg_8], edx
0x180007e35  mov     [rsp+arg_0], rcx
0x180007e3a  push    rbp
0x180007e3b  push    rsi
0x180007e3c  push    rdi
0x180007e3d  push    r12
0x180007e3f  push    r13
0x180007e41  push    r14
0x180007e43  push    r15
0x180007e45  sub     rsp, 40h
0x180007e49  mov     r12, r9
0x180007e4c  mov     r13, r8
0x180007e4f  mov     r10, rcx
0x180007e52  xor     eax, eax
0x180007e54  mov     rsi, [rsp+78h+lpOutputString]
0x180007e5c  mov     [rsi], ax
0x180007e5f  mov     rax, [rsp+78h+arg_60]
0x180007e67  mov     byte ptr [rax], 0
0x180007e6a  mov     r14, [rsp+78h+arg_38]
0x180007e72  mov     edi, [r14]
0x180007e75  mov     rbx, [rsp+78h+arg_78]
0x180007e7d  mov     [rbx+8], edi
0x180007e80  mov     eax, [r14+4]
0x180007e84  mov     [rbx+0Ch], eax
0x180007e87  xor     ebp, ebp
0x180007e89  mov     r15d, [rsp+78h+arg_30]
0x180007e91  mov     ecx, r15d
0x180007e94  test    r15d, r15d
0x180007e97  jz      short loc_180007EFF
0x180007e99  sub     ecx, 1
0x180007e9c  jz      short loc_180007EF6
0x180007e9e  sub     ecx, 1
0x180007ea1  jz      short loc_180007EB1
0x180007ea3  cmp     ecx, 1
0x180007ea6  jnz     short loc_180007F08
0x180007ea8  mov     ecx, edi; this
0x180007eaa  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007eaf  jmp     short loc_180007F06
0x180007eb1  test    edi, edi
0x180007eb3  js      short loc_180007EED
0x180007eb5  mov     edi, 8007029Ch
0x180007eba  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007ebe  mov     rax, [rsp+78h+arg_28]
0x180007ec6  mov     [rsp+78h+var_50], rax; __int64
0x180007ecb  mov     rax, [rsp+78h+arg_20]
0x180007ed3  mov     [rsp+78h+var_58], rax; __int64
0x180007ed8  mov     rcx, r10; int
0x180007edb  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007ee0  mov     [rbx+8], edi
0x180007ee3  mov     ecx, edi; this
0x180007ee5  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007eea  mov     [rbx+0Ch], eax
0x180007eed  mov     ecx, edi; this
0x180007eef  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007ef4  jmp     short loc_180007F06
0x180007ef6  mov     ecx, edi; this
0x180007ef8  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007efd  jmp     short loc_180007F06
0x180007eff  mov     ecx, edi; this
0x180007f01  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007f06  mov     ebp, eax
0x180007f08  mov     [rbx], r15d
0x180007f0b  mov     eax, [rsp+78h+arg_70]
0x180007f12  mov     [rbx+4], eax
0x180007f15  cmp     dword ptr [r14+8], 1
0x180007f1a  jnz     short loc_180007F22
0x180007f1c  or      eax, 8
0x180007f1f  mov     [rbx+4], eax
0x180007f22  mov     eax, 1
0x180007f27  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEB_W_NPEA_W_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,wchar_t const *,bool,wchar_t *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007f2f  inc     eax
0x180007f31  mov     [rbx+10h], eax
0x180007f34  mov     rax, [rsp+78h+arg_40]
0x180007f3c  xor     edi, edi
0x180007f3e  test    rax, rax
0x180007f41  jz      short loc_180007F48
0x180007f43  cmp     [rax], di
0x180007f46  jnz     short loc_180007F4B
0x180007f48  mov     rax, rdi
0x180007f4b  mov     [rbx+18h], rax
0x180007f4f  call    cs:__imp_GetCurrentThreadId
0x180007f55  mov     [rbx+20h], eax
0x180007f58  mov     [rbx+38h], r13
0x180007f5c  mov     eax, [rsp+78h+arg_8]
0x180007f63  mov     [rbx+40h], eax
0x180007f66  mov     [rbx+44h], ebp
0x180007f69  mov     rax, [rsp+78h+arg_20]
0x180007f71  mov     [rbx+28h], rax
0x180007f75  mov     [rbx+30h], r12
0x180007f79  mov     rax, [rsp+78h+arg_28]
0x180007f81  mov     [rbx+88h], rax
0x180007f88  mov     rax, [rsp+78h+arg_0]
0x180007f90  mov     [rbx+90h], rax
0x180007f97  mov     [rbx+48h], rdi
0x180007f9b  xorps   xmm0, xmm0
0x180007f9e  xor     eax, eax
0x180007fa0  movups  xmmword ptr [rbx+68h], xmm0
0x180007fa4  mov     [rbx+78h], rax
0x180007fa8  movups  xmmword ptr [rbx+50h], xmm0
0x180007fac  mov     [rbx+60h], rax
0x180007fb0  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007fb7  test    rax, rax
0x180007fba  jz      short loc_180007FC3
0x180007fbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fc1  jmp     short loc_180007FC6
0x180007fc3  mov     rax, rdi
0x180007fc6  mov     [rbx+80h], rax
0x180007fcd  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007fd4  test    rax, rax
0x180007fd7  jz      short loc_180007FE1
0x180007fd9  mov     rcx, rbx
0x180007fdc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007fe1  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007fe8  test    rax, rax
0x180007feb  jz      short loc_180008003
0x180007fed  mov     r8d, 400h
0x180007ff3  mov     rdx, [rsp+78h+arg_60]
0x180007ffb  mov     rcx, rbx
0x180007ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008003  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000800a  test    rax, rax
0x18000800d  jz      short loc_180008017
0x18000800f  mov     rcx, rbx
0x180008012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008017  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000801e  test    rax, rax
0x180008021  jz      short loc_180008031
0x180008023  test    byte ptr [rbx+4], 2
0x180008027  jnz     short loc_180008031
0x180008029  mov     rcx, rbx
0x18000802c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008031  cmp     [rbx+8], edi
0x180008034  jl      short loc_180008050
0x180008036  cmp     r15d, 3
0x18000803a  jnz     loc_180008100
0x180008040  mov     ecx, 8000FFFFh; this
0x180008045  mov     [rbx+8], ecx
0x180008048  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000804d  mov     [rbx+0Ch], eax
0x180008050  call    ?IsDebuggerPresent@details@wil@@YA_NXZ; wil::details::IsDebuggerPresent(void)
0x180008055  test    al, al
0x180008057  jz      short loc_1800080A5
0x180008059  test    byte ptr [rbx+4], 2
0x18000805d  jnz     short loc_1800080A5
0x18000805f  mov     ebp, 800h
0x180008064  mov     rax, cs:g_pfnResultLoggingCallback
0x18000806b  test    rax, rax
0x18000806e  jz      short loc_180008087
0x180008070  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180008077  jnz     short loc_180008087
0x180008079  mov     r8d, ebp
0x18000807c  mov     rdx, rsi
0x18000807f  mov     rcx, rbx
0x180008082  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008087  cmp     [rsi], di
0x18000808a  jnz     short loc_18000809A
0x18000808c  mov     r8, rbx; unsigned __int64
0x18000808f  mov     rdx, rbp; wchar_t *
0x180008092  mov     rcx, rsi; this
0x180008095  call    ?GetFailureLogString@wil@@YAJPEA_W_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(wchar_t *,unsigned __int64,wil::FailureInfo const &)
0x18000809a  mov     rcx, rsi; lpOutputString
0x18000809d  call    cs:__imp_OutputDebugStringW
0x1800080a3  jmp     short loc_1800080C7
0x1800080a5  mov     rax, cs:g_pfnResultLoggingCallback
0x1800080ac  test    rax, rax
0x1800080af  jz      short loc_1800080C7
0x1800080b1  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x1800080b8  jnz     short loc_1800080C7
0x1800080ba  xor     r8d, r8d
0x1800080bd  xor     edx, edx
0x1800080bf  mov     rcx, rbx
0x1800080c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080c7  test    byte ptr [rbx+4], 4
0x1800080cb  jnz     short loc_1800080D6
0x1800080cd  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x1800080d4  jz      short loc_1800080E8
0x1800080d6  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x1800080dd  test    rax, rax
0x1800080e0  jz      short loc_1800080E8
0x1800080e2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800080e7  nop
0x1800080e8  mov     rbx, [rsp+78h+arg_10]
0x1800080f0  add     rsp, 40h
0x1800080f4  pop     r15
0x1800080f6  pop     r14
0x1800080f8  pop     r13
0x1800080fa  pop     r12
0x1800080fc  pop     rdi
0x1800080fd  pop     rsi
0x1800080fe  pop     rbp
0x1800080ff  retn
0x180008100  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
