# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180007c10`
- end: `0x180007f09`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x18000503c`

## callees

- `0x180004a48`
- `0x180007144`
- `0x1800078e4`
- `0x180007c10`
- `0x1800085d0`
- `0x1800085f0`
- `0x180008604`
- `0x180008620`
- `0x18000a924`
- `0x180021010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d33`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180007d33`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007e52`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180007e52`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ec4`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180007ec4`

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
      g_pfnResultLoggingCallback(a16, 0, 0, v25);
  }
  else
  {
    if ( g_pfnResultLoggingCallback && !wil::details::g_resultMessageCallbackSet )
      g_pfnResultLoggingCallback(a16, lpOutputString, 2048, v25);
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
0x180007c10  mov     [rsp+arg_10], rbx
0x180007c15  mov     [rsp+arg_8], edx
0x180007c19  mov     [rsp+arg_0], rcx
0x180007c1e  push    rbp
0x180007c1f  push    rsi
0x180007c20  push    rdi
0x180007c21  push    r12
0x180007c23  push    r13
0x180007c25  push    r14
0x180007c27  push    r15
0x180007c29  sub     rsp, 40h
0x180007c2d  mov     r12, r9
0x180007c30  mov     r13, r8
0x180007c33  mov     r10, rcx
0x180007c36  xor     eax, eax
0x180007c38  mov     rsi, [rsp+78h+lpOutputString]
0x180007c40  mov     [rsi], ax
0x180007c43  mov     rax, [rsp+78h+arg_60]
0x180007c4b  mov     byte ptr [rax], 0
0x180007c4e  mov     r14, [rsp+78h+arg_38]
0x180007c56  mov     edi, [r14]
0x180007c59  mov     rbx, [rsp+78h+arg_78]
0x180007c61  mov     [rbx+8], edi
0x180007c64  mov     eax, [r14+4]
0x180007c68  mov     [rbx+0Ch], eax
0x180007c6b  xor     ebp, ebp
0x180007c6d  mov     r15d, [rsp+78h+arg_30]
0x180007c75  mov     ecx, r15d
0x180007c78  test    r15d, r15d
0x180007c7b  jz      short loc_180007CE3
0x180007c7d  sub     ecx, 1
0x180007c80  jz      short loc_180007CDA
0x180007c82  sub     ecx, 1
0x180007c85  jz      short loc_180007C95
0x180007c87  cmp     ecx, 1
0x180007c8a  jnz     short loc_180007CEC
0x180007c8c  mov     ecx, edi; this
0x180007c8e  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180007c93  jmp     short loc_180007CEA
0x180007c95  test    edi, edi
0x180007c97  js      short loc_180007CD1
0x180007c99  mov     edi, 8007029Ch
0x180007c9e  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180007ca2  mov     rax, [rsp+78h+arg_28]
0x180007caa  mov     [rsp+78h+var_50], rax; __int64
0x180007caf  mov     rax, [rsp+78h+arg_20]
0x180007cb7  mov     [rsp+78h+var_58], rax; __int64
0x180007cbc  mov     rcx, r10; int
0x180007cbf  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180007cc4  mov     [rbx+8], edi
0x180007cc7  mov     ecx, edi; this
0x180007cc9  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007cce  mov     [rbx+0Ch], eax
0x180007cd1  mov     ecx, edi; this
0x180007cd3  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180007cd8  jmp     short loc_180007CEA
0x180007cda  mov     ecx, edi; this
0x180007cdc  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180007ce1  jmp     short loc_180007CEA
0x180007ce3  mov     ecx, edi; this
0x180007ce5  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180007cea  mov     ebp, eax
0x180007cec  mov     [rbx], r15d
0x180007cef  mov     eax, [rsp+78h+arg_70]
0x180007cf6  mov     [rbx+4], eax
0x180007cf9  cmp     dword ptr [r14+8], 1
0x180007cfe  jnz     short loc_180007D06
0x180007d00  or      eax, 8
0x180007d03  mov     [rbx+4], eax
0x180007d06  mov     eax, 1
0x180007d0b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180007d13  inc     eax
0x180007d15  mov     [rbx+10h], eax
0x180007d18  mov     rax, [rsp+78h+arg_40]
0x180007d20  xor     edi, edi
0x180007d22  test    rax, rax
0x180007d25  jz      short loc_180007D2C
0x180007d27  cmp     [rax], di
0x180007d2a  jnz     short loc_180007D2F
0x180007d2c  mov     rax, rdi
0x180007d2f  mov     [rbx+18h], rax
0x180007d33  call    cs:__imp_GetCurrentThreadId
0x180007d39  mov     [rbx+20h], eax
0x180007d3c  mov     [rbx+38h], r13
0x180007d40  mov     eax, [rsp+78h+arg_8]
0x180007d47  mov     [rbx+40h], eax
0x180007d4a  mov     [rbx+44h], ebp
0x180007d4d  mov     rax, [rsp+78h+arg_20]
0x180007d55  mov     [rbx+28h], rax
0x180007d59  mov     [rbx+30h], r12
0x180007d5d  mov     rax, [rsp+78h+arg_28]
0x180007d65  mov     [rbx+88h], rax
0x180007d6c  mov     rax, [rsp+78h+arg_0]
0x180007d74  mov     [rbx+90h], rax
0x180007d7b  mov     [rbx+48h], rdi
0x180007d7f  xorps   xmm0, xmm0
0x180007d82  xor     eax, eax
0x180007d84  movups  xmmword ptr [rbx+68h], xmm0
0x180007d88  mov     [rbx+78h], rax
0x180007d8c  movups  xmmword ptr [rbx+50h], xmm0
0x180007d90  mov     [rbx+60h], rax
0x180007d94  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180007d9b  test    rax, rax
0x180007d9e  jz      short loc_180007DA7
0x180007da0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007da5  jmp     short loc_180007DAA
0x180007da7  mov     rax, rdi
0x180007daa  mov     [rbx+80h], rax
0x180007db1  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180007db8  test    rax, rax
0x180007dbb  jz      short loc_180007DC5
0x180007dbd  mov     rcx, rbx
0x180007dc0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc5  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180007dcc  test    rax, rax
0x180007dcf  jz      short loc_180007DE7
0x180007dd1  mov     r8d, 400h
0x180007dd7  mov     rdx, [rsp+78h+arg_60]
0x180007ddf  mov     rcx, rbx
0x180007de2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007de7  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007dee  test    rax, rax
0x180007df1  jz      short loc_180007DFB
0x180007df3  mov     rcx, rbx
0x180007df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dfb  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180007e02  test    rax, rax
0x180007e05  jz      short loc_180007E15
0x180007e07  test    byte ptr [rbx+4], 2
0x180007e0b  jnz     short loc_180007E15
0x180007e0d  mov     rcx, rbx
0x180007e10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e15  cmp     [rbx+8], edi
0x180007e18  jl      short loc_180007E34
0x180007e1a  cmp     r15d, 3
0x180007e1e  jnz     loc_180007F03
0x180007e24  mov     ecx, 8000FFFFh; this
0x180007e29  mov     [rbx+8], ecx
0x180007e2c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180007e31  mov     [rbx+0Ch], eax
0x180007e34  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180007e3b  jnz     short loc_180007E5C
0x180007e3d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180007e44  test    rax, rax
0x180007e47  jz      short loc_180007E52
0x180007e49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e4e  test    al, al
0x180007e50  jmp     short loc_180007E5A
0x180007e52  call    cs:__imp_IsDebuggerPresent
0x180007e58  test    eax, eax
0x180007e5a  jz      short loc_180007E62
0x180007e5c  test    byte ptr [rbx+4], 2
0x180007e60  jz      short loc_180007E86
0x180007e62  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e69  test    rax, rax
0x180007e6c  jz      short loc_180007ECA
0x180007e6e  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007e75  jnz     short loc_180007ECA
0x180007e77  xor     r8d, r8d
0x180007e7a  xor     edx, edx
0x180007e7c  mov     rcx, rbx
0x180007e7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e84  jmp     short loc_180007ECA
0x180007e86  mov     ebp, 800h
0x180007e8b  mov     rax, cs:g_pfnResultLoggingCallback
0x180007e92  test    rax, rax
0x180007e95  jz      short loc_180007EAE
0x180007e97  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180007e9e  jnz     short loc_180007EAE
0x180007ea0  mov     r8d, ebp
0x180007ea3  mov     rdx, rsi
0x180007ea6  mov     rcx, rbx
0x180007ea9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eae  cmp     [rsi], di
0x180007eb1  jnz     short loc_180007EC1
0x180007eb3  mov     r8, rbx; unsigned __int64
0x180007eb6  mov     rdx, rbp; unsigned __int16 *
0x180007eb9  mov     rcx, rsi; this
0x180007ebc  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180007ec1  mov     rcx, rsi; lpOutputString
0x180007ec4  call    cs:__imp_OutputDebugStringW
0x180007eca  test    byte ptr [rbx+4], 4
0x180007ece  jnz     short loc_180007ED9
0x180007ed0  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180007ed7  jz      short loc_180007EEB
0x180007ed9  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180007ee0  test    rax, rax
0x180007ee3  jz      short loc_180007EEB
0x180007ee5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007eea  nop
0x180007eeb  mov     rbx, [rsp+78h+arg_10]
0x180007ef3  add     rsp, 40h
0x180007ef7  pop     r15
0x180007ef9  pop     r14
0x180007efb  pop     r13
0x180007efd  pop     r12
0x180007eff  pop     rdi
0x180007f00  pop     rsi
0x180007f01  pop     rbp
0x180007f02  retn
0x180007f03  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
