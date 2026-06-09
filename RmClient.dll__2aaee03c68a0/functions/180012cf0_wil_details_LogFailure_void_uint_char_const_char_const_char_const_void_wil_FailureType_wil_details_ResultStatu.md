# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180012cf0`
- end: `0x180012fe4`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `756`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `3`
- callee_count: `10`
- tags: ``

## callers

- `0x1800114ac`
- `0x180012bfc`
- `0x180015d10`

## callees

- `0x18001119c`
- `0x180012cf0`
- `0x180012ff0`
- `0x180015cac`
- `0x1800163b4`
- `0x180016e30`
- `0x180016e4c`
- `0x180016e68`
- `0x1800174d0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012e13`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180012e13`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012f34`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180012f34`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012fa6`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180012fa6`

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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v23);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v26 = !IsDebuggerPresent())
      : (v26 = (unsigned __int8)wil::g_pfnIsDebuggerPresent() == 0),
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v24);
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
0x180012cf0  mov     [rsp+arg_10], rbx
0x180012cf5  mov     [rsp+arg_8], edx
0x180012cf9  mov     [rsp+arg_0], rcx
0x180012cfe  push    rbp
0x180012cff  push    rsi
0x180012d00  push    rdi
0x180012d01  push    r12
0x180012d03  push    r13
0x180012d05  push    r14
0x180012d07  push    r15
0x180012d09  sub     rsp, 40h
0x180012d0d  mov     r14, [rsp+78h+arg_38]
0x180012d15  xor     eax, eax
0x180012d17  mov     rbx, [rsp+78h+arg_78]
0x180012d1f  xor     ebp, ebp
0x180012d21  mov     r15d, [rsp+78h+arg_30]
0x180012d29  mov     r10, rcx
0x180012d2c  mov     rsi, [rsp+78h+lpOutputString]
0x180012d34  mov     r12, r9
0x180012d37  mov     r13, r8
0x180012d3a  mov     ecx, r15d
0x180012d3d  mov     [rsi], ax
0x180012d40  mov     rax, [rsp+78h+arg_60]
0x180012d48  mov     byte ptr [rax], 0
0x180012d4b  mov     edi, [r14]
0x180012d4e  mov     [rbx+8], edi
0x180012d51  mov     eax, [r14+4]
0x180012d55  mov     [rbx+0Ch], eax
0x180012d58  test    r15d, r15d
0x180012d5b  jz      short loc_180012DC3
0x180012d5d  sub     ecx, 1
0x180012d60  jz      short loc_180012DBA
0x180012d62  sub     ecx, 1
0x180012d65  jz      short loc_180012D75
0x180012d67  cmp     ecx, 1
0x180012d6a  jnz     short loc_180012DCC
0x180012d6c  mov     ecx, edi; this
0x180012d6e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180012d73  jmp     short loc_180012DCA
0x180012d75  test    edi, edi
0x180012d77  js      short loc_180012DB1
0x180012d79  mov     rax, [rsp+78h+arg_28]
0x180012d81  mov     edi, 8007029Ch
0x180012d86  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180012d8a  mov     rcx, r10; int
0x180012d8d  mov     [rsp+78h+var_50], rax; __int64
0x180012d92  mov     rax, [rsp+78h+arg_20]
0x180012d9a  mov     [rsp+78h+var_58], rax; __int64
0x180012d9f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180012da4  mov     ecx, edi; this
0x180012da6  mov     [rbx+8], edi
0x180012da9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012dae  mov     [rbx+0Ch], eax
0x180012db1  mov     ecx, edi; this
0x180012db3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180012db8  jmp     short loc_180012DCA
0x180012dba  mov     ecx, edi; this
0x180012dbc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180012dc1  jmp     short loc_180012DCA
0x180012dc3  mov     ecx, edi; this
0x180012dc5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180012dca  mov     ebp, eax
0x180012dcc  mov     eax, [rsp+78h+arg_70]
0x180012dd3  mov     [rbx+4], eax
0x180012dd6  mov     [rbx], r15d
0x180012dd9  cmp     dword ptr [r14+8], 1
0x180012dde  jnz     short loc_180012DE6
0x180012de0  or      eax, 8
0x180012de3  mov     [rbx+4], eax
0x180012de6  mov     eax, 1
0x180012deb  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180012df3  inc     eax
0x180012df5  xor     edi, edi
0x180012df7  mov     [rbx+10h], eax
0x180012dfa  mov     rax, [rsp+78h+arg_40]
0x180012e02  test    rax, rax
0x180012e05  jz      short loc_180012E0C
0x180012e07  cmp     [rax], di
0x180012e0a  jnz     short loc_180012E0F
0x180012e0c  mov     rax, rdi
0x180012e0f  mov     [rbx+18h], rax
0x180012e13  call    cs:__imp_GetCurrentThreadId
0x180012e19  mov     [rbx+38h], r13
0x180012e1d  xorps   xmm0, xmm0
0x180012e20  mov     [rbx+20h], eax
0x180012e23  mov     eax, [rsp+78h+arg_8]
0x180012e2a  mov     [rbx+40h], eax
0x180012e2d  mov     rax, [rsp+78h+arg_20]
0x180012e35  mov     [rbx+28h], rax
0x180012e39  mov     rax, [rsp+78h+arg_28]
0x180012e41  mov     [rbx+88h], rax
0x180012e48  mov     rax, [rsp+78h+arg_0]
0x180012e50  mov     [rbx+90h], rax
0x180012e57  xor     eax, eax
0x180012e59  mov     [rbx+44h], ebp
0x180012e5c  mov     [rbx+30h], r12
0x180012e60  mov     [rbx+48h], rdi
0x180012e64  movups  xmmword ptr [rbx+68h], xmm0
0x180012e68  mov     [rbx+78h], rax
0x180012e6c  movups  xmmword ptr [rbx+50h], xmm0
0x180012e70  mov     [rbx+60h], rax
0x180012e74  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180012e7b  test    rax, rax
0x180012e7e  jz      short loc_180012E87
0x180012e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012e85  jmp     short loc_180012E8A
0x180012e87  mov     rax, rdi
0x180012e8a  mov     [rbx+80h], rax
0x180012e91  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180012e98  test    rax, rax
0x180012e9b  jz      short loc_180012EA5
0x180012e9d  mov     rcx, rbx
0x180012ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ea5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180012eac  test    rax, rax
0x180012eaf  jz      short loc_180012EC7
0x180012eb1  mov     rdx, [rsp+78h+arg_60]
0x180012eb9  mov     r8d, 400h
0x180012ebf  mov     rcx, rbx
0x180012ec2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ec7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012ece  test    rax, rax
0x180012ed1  jz      short loc_180012EDB
0x180012ed3  mov     rcx, rbx
0x180012ed6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012edb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180012ee2  test    rax, rax
0x180012ee5  jz      short loc_180012EF5
0x180012ee7  test    byte ptr [rbx+4], 2
0x180012eeb  jnz     short loc_180012EF5
0x180012eed  mov     rcx, rbx
0x180012ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012ef5  cmp     [rbx+8], edi
0x180012ef8  jl      short loc_180012F16
0x180012efa  cmp     r15d, 3
0x180012efe  jz      short loc_180012F06
0x180012f00  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
0x180012f06  mov     ecx, 8000FFFFh; this
0x180012f0b  mov     [rbx+8], ecx
0x180012f0e  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180012f13  mov     [rbx+0Ch], eax
0x180012f16  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180012f1d  jnz     short loc_180012F3E
0x180012f1f  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180012f26  test    rax, rax
0x180012f29  jz      short loc_180012F34
0x180012f2b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f30  test    al, al
0x180012f32  jmp     short loc_180012F3C
0x180012f34  call    cs:__imp_IsDebuggerPresent
0x180012f3a  test    eax, eax
0x180012f3c  jz      short loc_180012F44
0x180012f3e  test    byte ptr [rbx+4], 2
0x180012f42  jz      short loc_180012F68
0x180012f44  mov     rax, cs:g_pfnResultLoggingCallback
0x180012f4b  test    rax, rax
0x180012f4e  jz      short loc_180012FAC
0x180012f50  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012f57  jnz     short loc_180012FAC
0x180012f59  xor     r8d, r8d
0x180012f5c  xor     edx, edx
0x180012f5e  mov     rcx, rbx
0x180012f61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f66  jmp     short loc_180012FAC
0x180012f68  mov     rax, cs:g_pfnResultLoggingCallback
0x180012f6f  mov     ebp, 800h
0x180012f74  test    rax, rax
0x180012f77  jz      short loc_180012F90
0x180012f79  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180012f80  jnz     short loc_180012F90
0x180012f82  mov     r8d, ebp
0x180012f85  mov     rdx, rsi
0x180012f88  mov     rcx, rbx
0x180012f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012f90  cmp     [rsi], di
0x180012f93  jnz     short loc_180012FA3
0x180012f95  mov     r8, rbx; unsigned __int64
0x180012f98  mov     rdx, rbp; unsigned __int16 *
0x180012f9b  mov     rcx, rsi; this
0x180012f9e  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180012fa3  mov     rcx, rsi; lpOutputString
0x180012fa6  call    cs:__imp_OutputDebugStringW
0x180012fac  test    byte ptr [rbx+4], 4
0x180012fb0  jnz     short loc_180012FBB
0x180012fb2  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180012fb9  jz      short loc_180012FCC
0x180012fbb  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180012fc2  test    rax, rax
0x180012fc5  jz      short loc_180012FCC
0x180012fc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012fcc  mov     rbx, [rsp+78h+arg_10]
0x180012fd4  add     rsp, 40h
0x180012fd8  pop     r15
0x180012fda  pop     r14
0x180012fdc  pop     r13
0x180012fde  pop     r12
0x180012fe0  pop     rdi
0x180012fe1  pop     rsi
0x180012fe2  pop     rbp
0x180012fe3  retn
```
