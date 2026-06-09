# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005d60`
- end: `0x180006059`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003184`

## callees

- `0x180002bc8`
- `0x180005294`
- `0x180005a34`
- `0x180005d60`
- `0x1800066d8`
- `0x180006700`
- `0x180006714`
- `0x180006730`
- `0x1800088e4`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e83`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005e83`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005fa2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005fa2`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006014`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180006014`

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
0x180005d60  mov     [rsp+arg_10], rbx
0x180005d65  mov     [rsp+arg_8], edx
0x180005d69  mov     [rsp+arg_0], rcx
0x180005d6e  push    rbp
0x180005d6f  push    rsi
0x180005d70  push    rdi
0x180005d71  push    r12
0x180005d73  push    r13
0x180005d75  push    r14
0x180005d77  push    r15
0x180005d79  sub     rsp, 40h
0x180005d7d  mov     r12, r9
0x180005d80  mov     r13, r8
0x180005d83  mov     r10, rcx
0x180005d86  xor     eax, eax
0x180005d88  mov     rsi, [rsp+78h+lpOutputString]
0x180005d90  mov     [rsi], ax
0x180005d93  mov     rax, [rsp+78h+arg_60]
0x180005d9b  mov     byte ptr [rax], 0
0x180005d9e  mov     r14, [rsp+78h+arg_38]
0x180005da6  mov     edi, [r14]
0x180005da9  mov     rbx, [rsp+78h+arg_78]
0x180005db1  mov     [rbx+8], edi
0x180005db4  mov     eax, [r14+4]
0x180005db8  mov     [rbx+0Ch], eax
0x180005dbb  xor     ebp, ebp
0x180005dbd  mov     r15d, [rsp+78h+arg_30]
0x180005dc5  mov     ecx, r15d
0x180005dc8  test    r15d, r15d
0x180005dcb  jz      short loc_180005E33
0x180005dcd  sub     ecx, 1
0x180005dd0  jz      short loc_180005E2A
0x180005dd2  sub     ecx, 1
0x180005dd5  jz      short loc_180005DE5
0x180005dd7  cmp     ecx, 1
0x180005dda  jnz     short loc_180005E3C
0x180005ddc  mov     ecx, edi; this
0x180005dde  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005de3  jmp     short loc_180005E3A
0x180005de5  test    edi, edi
0x180005de7  js      short loc_180005E21
0x180005de9  mov     edi, 8007029Ch
0x180005dee  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005df2  mov     rax, [rsp+78h+arg_28]
0x180005dfa  mov     [rsp+78h+var_50], rax; __int64
0x180005dff  mov     rax, [rsp+78h+arg_20]
0x180005e07  mov     [rsp+78h+var_58], rax; __int64
0x180005e0c  mov     rcx, r10; int
0x180005e0f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005e14  mov     [rbx+8], edi
0x180005e17  mov     ecx, edi; this
0x180005e19  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e1e  mov     [rbx+0Ch], eax
0x180005e21  mov     ecx, edi; this
0x180005e23  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005e28  jmp     short loc_180005E3A
0x180005e2a  mov     ecx, edi; this
0x180005e2c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005e31  jmp     short loc_180005E3A
0x180005e33  mov     ecx, edi; this
0x180005e35  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005e3a  mov     ebp, eax
0x180005e3c  mov     [rbx], r15d
0x180005e3f  mov     eax, [rsp+78h+arg_70]
0x180005e46  mov     [rbx+4], eax
0x180005e49  cmp     dword ptr [r14+8], 1
0x180005e4e  jnz     short loc_180005E56
0x180005e50  or      eax, 8
0x180005e53  mov     [rbx+4], eax
0x180005e56  mov     eax, 1
0x180005e5b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005e63  inc     eax
0x180005e65  mov     [rbx+10h], eax
0x180005e68  mov     rax, [rsp+78h+arg_40]
0x180005e70  xor     edi, edi
0x180005e72  test    rax, rax
0x180005e75  jz      short loc_180005E7C
0x180005e77  cmp     [rax], di
0x180005e7a  jnz     short loc_180005E7F
0x180005e7c  mov     rax, rdi
0x180005e7f  mov     [rbx+18h], rax
0x180005e83  call    cs:__imp_GetCurrentThreadId
0x180005e89  mov     [rbx+20h], eax
0x180005e8c  mov     [rbx+38h], r13
0x180005e90  mov     eax, [rsp+78h+arg_8]
0x180005e97  mov     [rbx+40h], eax
0x180005e9a  mov     [rbx+44h], ebp
0x180005e9d  mov     rax, [rsp+78h+arg_20]
0x180005ea5  mov     [rbx+28h], rax
0x180005ea9  mov     [rbx+30h], r12
0x180005ead  mov     rax, [rsp+78h+arg_28]
0x180005eb5  mov     [rbx+88h], rax
0x180005ebc  mov     rax, [rsp+78h+arg_0]
0x180005ec4  mov     [rbx+90h], rax
0x180005ecb  mov     [rbx+48h], rdi
0x180005ecf  xorps   xmm0, xmm0
0x180005ed2  xor     eax, eax
0x180005ed4  movups  xmmword ptr [rbx+68h], xmm0
0x180005ed8  mov     [rbx+78h], rax
0x180005edc  movups  xmmword ptr [rbx+50h], xmm0
0x180005ee0  mov     [rbx+60h], rax
0x180005ee4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005eeb  test    rax, rax
0x180005eee  jz      short loc_180005EF7
0x180005ef0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ef5  jmp     short loc_180005EFA
0x180005ef7  mov     rax, rdi
0x180005efa  mov     [rbx+80h], rax
0x180005f01  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005f08  test    rax, rax
0x180005f0b  jz      short loc_180005F15
0x180005f0d  mov     rcx, rbx
0x180005f10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f15  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005f1c  test    rax, rax
0x180005f1f  jz      short loc_180005F37
0x180005f21  mov     r8d, 400h
0x180005f27  mov     rdx, [rsp+78h+arg_60]
0x180005f2f  mov     rcx, rbx
0x180005f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f37  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f3e  test    rax, rax
0x180005f41  jz      short loc_180005F4B
0x180005f43  mov     rcx, rbx
0x180005f46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f4b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005f52  test    rax, rax
0x180005f55  jz      short loc_180005F65
0x180005f57  test    byte ptr [rbx+4], 2
0x180005f5b  jnz     short loc_180005F65
0x180005f5d  mov     rcx, rbx
0x180005f60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f65  cmp     [rbx+8], edi
0x180005f68  jl      short loc_180005F84
0x180005f6a  cmp     r15d, 3
0x180005f6e  jnz     loc_180006053
0x180005f74  mov     ecx, 8000FFFFh; this
0x180005f79  mov     [rbx+8], ecx
0x180005f7c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005f81  mov     [rbx+0Ch], eax
0x180005f84  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005f8b  jnz     short loc_180005FAC
0x180005f8d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005f94  test    rax, rax
0x180005f97  jz      short loc_180005FA2
0x180005f99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f9e  test    al, al
0x180005fa0  jmp     short loc_180005FAA
0x180005fa2  call    cs:__imp_IsDebuggerPresent
0x180005fa8  test    eax, eax
0x180005faa  jz      short loc_180005FB2
0x180005fac  test    byte ptr [rbx+4], 2
0x180005fb0  jz      short loc_180005FD6
0x180005fb2  mov     rax, cs:g_pfnResultLoggingCallback
0x180005fb9  test    rax, rax
0x180005fbc  jz      short loc_18000601A
0x180005fbe  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005fc5  jnz     short loc_18000601A
0x180005fc7  xor     r8d, r8d
0x180005fca  xor     edx, edx
0x180005fcc  mov     rcx, rbx
0x180005fcf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005fd4  jmp     short loc_18000601A
0x180005fd6  mov     ebp, 800h
0x180005fdb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005fe2  test    rax, rax
0x180005fe5  jz      short loc_180005FFE
0x180005fe7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005fee  jnz     short loc_180005FFE
0x180005ff0  mov     r8d, ebp
0x180005ff3  mov     rdx, rsi
0x180005ff6  mov     rcx, rbx
0x180005ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ffe  cmp     [rsi], di
0x180006001  jnz     short loc_180006011
0x180006003  mov     r8, rbx; unsigned __int64
0x180006006  mov     rdx, rbp; unsigned __int16 *
0x180006009  mov     rcx, rsi; this
0x18000600c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180006011  mov     rcx, rsi; lpOutputString
0x180006014  call    cs:__imp_OutputDebugStringW
0x18000601a  test    byte ptr [rbx+4], 4
0x18000601e  jnz     short loc_180006029
0x180006020  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180006027  jz      short loc_18000603B
0x180006029  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180006030  test    rax, rax
0x180006033  jz      short loc_18000603B
0x180006035  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000603a  nop
0x18000603b  mov     rbx, [rsp+78h+arg_10]
0x180006043  add     rsp, 40h
0x180006047  pop     r15
0x180006049  pop     r14
0x18000604b  pop     r13
0x18000604d  pop     r12
0x18000604f  pop     rdi
0x180006050  pop     rsi
0x180006051  pop     rbp
0x180006052  retn
0x180006053  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
