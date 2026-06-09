# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180035cf8`
- end: `0x180035fff`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `775`
- prototype: ``
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800353d0`
- `0x1800354c0`
- `0x1800397bc`

## callees

- `0x1800334f0`
- `0x18003536c`
- `0x180035704`
- `0x180035cf8`
- `0x180036170`
- `0x180036190`
- `0x1800361a4`
- `0x1800361c4`
- `0x180036b88`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035e1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180035e1b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180035fba`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180035fba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180035f42`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180035f42`

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
0x180035cf8  mov     [rsp+arg_10], rbx
0x180035cfd  mov     [rsp+arg_8], edx
0x180035d01  mov     [rsp+arg_0], rcx
0x180035d06  push    rbp
0x180035d07  push    rsi
0x180035d08  push    rdi
0x180035d09  push    r12
0x180035d0b  push    r13
0x180035d0d  push    r14
0x180035d0f  push    r15
0x180035d11  sub     rsp, 40h
0x180035d15  mov     r14, [rsp+78h+arg_38]
0x180035d1d  xor     eax, eax
0x180035d1f  mov     rbx, [rsp+78h+arg_78]
0x180035d27  xor     ebp, ebp
0x180035d29  mov     r15d, [rsp+78h+arg_30]
0x180035d31  mov     r10, rcx
0x180035d34  mov     rsi, [rsp+78h+lpOutputString]
0x180035d3c  mov     r12, r9
0x180035d3f  mov     r13, r8
0x180035d42  mov     ecx, r15d
0x180035d45  mov     [rsi], ax
0x180035d48  mov     rax, [rsp+78h+arg_60]
0x180035d50  mov     byte ptr [rax], 0
0x180035d53  mov     edi, [r14]
0x180035d56  mov     [rbx+8], edi
0x180035d59  mov     eax, [r14+4]
0x180035d5d  mov     [rbx+0Ch], eax
0x180035d60  test    r15d, r15d
0x180035d63  jz      short loc_180035DCB
0x180035d65  sub     ecx, 1
0x180035d68  jz      short loc_180035DC2
0x180035d6a  sub     ecx, 1
0x180035d6d  jz      short loc_180035D7D
0x180035d6f  cmp     ecx, 1
0x180035d72  jnz     short loc_180035DD4
0x180035d74  mov     ecx, edi; this
0x180035d76  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180035d7b  jmp     short loc_180035DD2
0x180035d7d  test    edi, edi
0x180035d7f  js      short loc_180035DB9
0x180035d81  mov     rax, [rsp+78h+arg_28]
0x180035d89  mov     edi, 8007029Ch
0x180035d8e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180035d92  mov     rcx, r10; int
0x180035d95  mov     [rsp+78h+var_50], rax; __int64
0x180035d9a  mov     rax, [rsp+78h+arg_20]
0x180035da2  mov     [rsp+78h+var_58], rax; __int64
0x180035da7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180035dac  mov     ecx, edi; this
0x180035dae  mov     [rbx+8], edi
0x180035db1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180035db6  mov     [rbx+0Ch], eax
0x180035db9  mov     ecx, edi; this
0x180035dbb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180035dc0  jmp     short loc_180035DD2
0x180035dc2  mov     ecx, edi; this
0x180035dc4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180035dc9  jmp     short loc_180035DD2
0x180035dcb  mov     ecx, edi; this
0x180035dcd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180035dd2  mov     ebp, eax
0x180035dd4  mov     eax, [rsp+78h+arg_70]
0x180035ddb  mov     [rbx+4], eax
0x180035dde  mov     [rbx], r15d
0x180035de1  cmp     dword ptr [r14+8], 1
0x180035de6  jnz     short loc_180035DEE
0x180035de8  or      eax, 8
0x180035deb  mov     [rbx+4], eax
0x180035dee  mov     eax, 1
0x180035df3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180035dfb  inc     eax
0x180035dfd  xor     edi, edi
0x180035dff  mov     [rbx+10h], eax
0x180035e02  mov     rax, [rsp+78h+arg_40]
0x180035e0a  test    rax, rax
0x180035e0d  jz      short loc_180035E14
0x180035e0f  cmp     [rax], di
0x180035e12  jnz     short loc_180035E17
0x180035e14  mov     rax, rdi
0x180035e17  mov     [rbx+18h], rax
0x180035e1b  call    cs:__imp_GetCurrentThreadId
0x180035e22  nop     dword ptr [rax+rax+00h]
0x180035e27  mov     [rbx+38h], r13
0x180035e2b  xorps   xmm0, xmm0
0x180035e2e  mov     [rbx+20h], eax
0x180035e31  mov     eax, [rsp+78h+arg_8]
0x180035e38  mov     [rbx+40h], eax
0x180035e3b  mov     rax, [rsp+78h+arg_20]
0x180035e43  mov     [rbx+28h], rax
0x180035e47  mov     rax, [rsp+78h+arg_28]
0x180035e4f  mov     [rbx+88h], rax
0x180035e56  mov     rax, [rsp+78h+arg_0]
0x180035e5e  mov     [rbx+90h], rax
0x180035e65  xor     eax, eax
0x180035e67  mov     [rbx+44h], ebp
0x180035e6a  mov     [rbx+30h], r12
0x180035e6e  mov     [rbx+48h], rdi
0x180035e72  movups  xmmword ptr [rbx+68h], xmm0
0x180035e76  mov     [rbx+78h], rax
0x180035e7a  movups  xmmword ptr [rbx+50h], xmm0
0x180035e7e  mov     [rbx+60h], rax
0x180035e82  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180035e89  test    rax, rax
0x180035e8c  jz      short loc_180035E95
0x180035e8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035e93  jmp     short loc_180035E98
0x180035e95  mov     rax, rdi
0x180035e98  mov     [rbx+80h], rax
0x180035e9f  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180035ea6  test    rax, rax
0x180035ea9  jz      short loc_180035EB3
0x180035eab  mov     rcx, rbx
0x180035eae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035eb3  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180035eba  test    rax, rax
0x180035ebd  jz      short loc_180035ED5
0x180035ebf  mov     rdx, [rsp+78h+arg_60]
0x180035ec7  mov     r8d, 400h
0x180035ecd  mov     rcx, rbx
0x180035ed0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ed5  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180035edc  test    rax, rax
0x180035edf  jz      short loc_180035EE9
0x180035ee1  mov     rcx, rbx
0x180035ee4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035ee9  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180035ef0  test    rax, rax
0x180035ef3  jz      short loc_180035F03
0x180035ef5  test    byte ptr [rbx+4], 2
0x180035ef9  jnz     short loc_180035F03
0x180035efb  mov     rcx, rbx
0x180035efe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f03  cmp     [rbx+8], edi
0x180035f06  jl      short loc_180035F24
0x180035f08  cmp     r15d, 3
0x180035f0c  jz      short loc_180035F14
0x180035f0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180035f14  mov     ecx, 8000FFFFh; this
0x180035f19  mov     [rbx+8], ecx
0x180035f1c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180035f21  mov     [rbx+0Ch], eax
0x180035f24  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180035f2b  jnz     short loc_180035F52
0x180035f2d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180035f34  test    rax, rax
0x180035f37  jz      short loc_180035F42
0x180035f39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f3e  test    al, al
0x180035f40  jmp     short loc_180035F50
0x180035f42  call    cs:__imp_IsDebuggerPresent
0x180035f49  nop     dword ptr [rax+rax+00h]
0x180035f4e  test    eax, eax
0x180035f50  jz      short loc_180035F58
0x180035f52  test    byte ptr [rbx+4], 2
0x180035f56  jz      short loc_180035F7C
0x180035f58  mov     rax, cs:g_pfnResultLoggingCallback
0x180035f5f  test    rax, rax
0x180035f62  jz      short loc_180035FC6
0x180035f64  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180035f6b  jnz     short loc_180035FC6
0x180035f6d  xor     r8d, r8d
0x180035f70  xor     edx, edx
0x180035f72  mov     rcx, rbx
0x180035f75  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035f7a  jmp     short loc_180035FC6
0x180035f7c  mov     rax, cs:g_pfnResultLoggingCallback
0x180035f83  mov     ebp, 800h
0x180035f88  test    rax, rax
0x180035f8b  jz      short loc_180035FA4
0x180035f8d  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180035f94  jnz     short loc_180035FA4
0x180035f96  mov     r8d, ebp
0x180035f99  mov     rdx, rsi
0x180035f9c  mov     rcx, rbx
0x180035f9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fa4  cmp     [rsi], di
0x180035fa7  jnz     short loc_180035FB7
0x180035fa9  mov     r8, rbx; unsigned __int64
0x180035fac  mov     rdx, rbp; unsigned __int16 *
0x180035faf  mov     rcx, rsi; this
0x180035fb2  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180035fb7  mov     rcx, rsi; lpOutputString
0x180035fba  call    cs:__imp_OutputDebugStringW
0x180035fc1  nop     dword ptr [rax+rax+00h]
0x180035fc6  test    byte ptr [rbx+4], 4
0x180035fca  jnz     short loc_180035FD5
0x180035fcc  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180035fd3  jz      short loc_180035FE6
0x180035fd5  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180035fdc  test    rax, rax
0x180035fdf  jz      short loc_180035FE6
0x180035fe1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180035fe6  mov     rbx, [rsp+78h+arg_10]
0x180035fee  add     rsp, 40h
0x180035ff2  pop     r15
0x180035ff4  pop     r14
0x180035ff6  pop     r13
0x180035ff8  pop     r12
0x180035ffa  pop     rdi
0x180035ffb  pop     rsi
0x180035ffc  pop     rbp
0x180035ffd  retn
```
