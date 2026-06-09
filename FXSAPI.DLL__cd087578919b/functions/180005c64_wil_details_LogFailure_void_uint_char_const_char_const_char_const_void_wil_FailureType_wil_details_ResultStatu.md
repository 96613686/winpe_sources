# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180005c64`
- end: `0x180005f70`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `780`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x1800029e8`

## callees

- `0x1800023fc`
- `0x180005294`
- `0x180005aa0`
- `0x180005c64`
- `0x180006b18`
- `0x180006b40`
- `0x180006c88`
- `0x180006ca8`
- `0x1800094f0`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetCurrentThreadId` at `0x180005d87`
- `KERNEL32!GetCurrentThreadId` at `0x180005d87`
- `KERNEL32!OutputDebugStringW` at `0x180005f24`
- `KERNEL32!OutputDebugStringW` at `0x180005f24`
- `KERNEL32!IsDebuggerPresent` at `0x180005eac`
- `KERNEL32!IsDebuggerPresent` at `0x180005eac`

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
0x180005c64  mov     [rsp+arg_10], rbx
0x180005c69  mov     [rsp+arg_8], edx
0x180005c6d  mov     [rsp+arg_0], rcx
0x180005c72  push    rbp
0x180005c73  push    rsi
0x180005c74  push    rdi
0x180005c75  push    r12
0x180005c77  push    r13
0x180005c79  push    r14
0x180005c7b  push    r15
0x180005c7d  sub     rsp, 40h
0x180005c81  mov     r12, r9
0x180005c84  mov     r13, r8
0x180005c87  mov     r10, rcx
0x180005c8a  xor     eax, eax
0x180005c8c  mov     rsi, [rsp+78h+lpOutputString]
0x180005c94  mov     [rsi], ax
0x180005c97  mov     rax, [rsp+78h+arg_60]
0x180005c9f  mov     byte ptr [rax], 0
0x180005ca2  mov     r14, [rsp+78h+arg_38]
0x180005caa  mov     edi, [r14]
0x180005cad  mov     rbx, [rsp+78h+arg_78]
0x180005cb5  mov     [rbx+8], edi
0x180005cb8  mov     eax, [r14+4]
0x180005cbc  mov     [rbx+0Ch], eax
0x180005cbf  xor     ebp, ebp
0x180005cc1  mov     r15d, [rsp+78h+arg_30]
0x180005cc9  mov     ecx, r15d
0x180005ccc  test    r15d, r15d
0x180005ccf  jz      short loc_180005D37
0x180005cd1  sub     ecx, 1
0x180005cd4  jz      short loc_180005D2E
0x180005cd6  sub     ecx, 1
0x180005cd9  jz      short loc_180005CE9
0x180005cdb  cmp     ecx, 1
0x180005cde  jnz     short loc_180005D40
0x180005ce0  mov     ecx, edi; this
0x180005ce2  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005ce7  jmp     short loc_180005D3E
0x180005ce9  test    edi, edi
0x180005ceb  js      short loc_180005D25
0x180005ced  mov     edi, 8007029Ch
0x180005cf2  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005cf6  mov     rax, [rsp+78h+arg_28]
0x180005cfe  mov     [rsp+78h+var_50], rax; __int64
0x180005d03  mov     rax, [rsp+78h+arg_20]
0x180005d0b  mov     [rsp+78h+var_58], rax; __int64
0x180005d10  mov     rcx, r10; int
0x180005d13  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005d18  mov     [rbx+8], edi
0x180005d1b  mov     ecx, edi; this
0x180005d1d  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005d22  mov     [rbx+0Ch], eax
0x180005d25  mov     ecx, edi; this
0x180005d27  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005d2c  jmp     short loc_180005D3E
0x180005d2e  mov     ecx, edi; this
0x180005d30  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005d35  jmp     short loc_180005D3E
0x180005d37  mov     ecx, edi; this
0x180005d39  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005d3e  mov     ebp, eax
0x180005d40  mov     [rbx], r15d
0x180005d43  mov     eax, [rsp+78h+arg_70]
0x180005d4a  mov     [rbx+4], eax
0x180005d4d  cmp     dword ptr [r14+8], 1
0x180005d52  jnz     short loc_180005D5A
0x180005d54  or      eax, 8
0x180005d57  mov     [rbx+4], eax
0x180005d5a  mov     eax, 1
0x180005d5f  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005d67  inc     eax
0x180005d69  mov     [rbx+10h], eax
0x180005d6c  mov     rax, [rsp+78h+arg_40]
0x180005d74  xor     edi, edi
0x180005d76  test    rax, rax
0x180005d79  jz      short loc_180005D80
0x180005d7b  cmp     [rax], di
0x180005d7e  jnz     short loc_180005D83
0x180005d80  mov     rax, rdi
0x180005d83  mov     [rbx+18h], rax
0x180005d87  call    cs:__imp_GetCurrentThreadId
0x180005d8e  nop     dword ptr [rax+rax+00h]
0x180005d93  mov     [rbx+20h], eax
0x180005d96  mov     [rbx+38h], r13
0x180005d9a  mov     eax, [rsp+78h+arg_8]
0x180005da1  mov     [rbx+40h], eax
0x180005da4  mov     [rbx+44h], ebp
0x180005da7  mov     rax, [rsp+78h+arg_20]
0x180005daf  mov     [rbx+28h], rax
0x180005db3  mov     [rbx+30h], r12
0x180005db7  mov     rax, [rsp+78h+arg_28]
0x180005dbf  mov     [rbx+88h], rax
0x180005dc6  mov     rax, [rsp+78h+arg_0]
0x180005dce  mov     [rbx+90h], rax
0x180005dd5  mov     [rbx+48h], rdi
0x180005dd9  xorps   xmm0, xmm0
0x180005ddc  xor     eax, eax
0x180005dde  movups  xmmword ptr [rbx+68h], xmm0
0x180005de2  mov     [rbx+78h], rax
0x180005de6  movups  xmmword ptr [rbx+50h], xmm0
0x180005dea  mov     [rbx+60h], rax
0x180005dee  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005df5  test    rax, rax
0x180005df8  jz      short loc_180005E01
0x180005dfa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005dff  jmp     short loc_180005E04
0x180005e01  mov     rax, rdi
0x180005e04  mov     [rbx+80h], rax
0x180005e0b  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005e12  test    rax, rax
0x180005e15  jz      short loc_180005E1F
0x180005e17  mov     rcx, rbx
0x180005e1a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e1f  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005e26  test    rax, rax
0x180005e29  jz      short loc_180005E41
0x180005e2b  mov     r8d, 400h
0x180005e31  mov     rdx, [rsp+78h+arg_60]
0x180005e39  mov     rcx, rbx
0x180005e3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e41  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e48  test    rax, rax
0x180005e4b  jz      short loc_180005E55
0x180005e4d  mov     rcx, rbx
0x180005e50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e55  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005e5c  test    rax, rax
0x180005e5f  jz      short loc_180005E6F
0x180005e61  test    byte ptr [rbx+4], 2
0x180005e65  jnz     short loc_180005E6F
0x180005e67  mov     rcx, rbx
0x180005e6a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005e6f  cmp     [rbx+8], edi
0x180005e72  jl      short loc_180005E8E
0x180005e74  cmp     r15d, 3
0x180005e78  jnz     loc_180005F6A
0x180005e7e  mov     ecx, 8000FFFFh; this
0x180005e83  mov     [rbx+8], ecx
0x180005e86  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005e8b  mov     [rbx+0Ch], eax
0x180005e8e  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005e95  jnz     short loc_180005EBC
0x180005e97  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005e9e  test    rax, rax
0x180005ea1  jz      short loc_180005EAC
0x180005ea3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ea8  test    al, al
0x180005eaa  jmp     short loc_180005EBA
0x180005eac  call    cs:__imp_IsDebuggerPresent
0x180005eb3  nop     dword ptr [rax+rax+00h]
0x180005eb8  test    eax, eax
0x180005eba  jz      short loc_180005EC2
0x180005ebc  test    byte ptr [rbx+4], 2
0x180005ec0  jz      short loc_180005EE6
0x180005ec2  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ec9  test    rax, rax
0x180005ecc  jz      short loc_180005F30
0x180005ece  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005ed5  jnz     short loc_180005F30
0x180005ed7  xor     r8d, r8d
0x180005eda  xor     edx, edx
0x180005edc  mov     rcx, rbx
0x180005edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005ee4  jmp     short loc_180005F30
0x180005ee6  mov     ebp, 800h
0x180005eeb  mov     rax, cs:g_pfnResultLoggingCallback
0x180005ef2  test    rax, rax
0x180005ef5  jz      short loc_180005F0E
0x180005ef7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005efe  jnz     short loc_180005F0E
0x180005f00  mov     r8d, ebp
0x180005f03  mov     rdx, rsi
0x180005f06  mov     rcx, rbx
0x180005f09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f0e  cmp     [rsi], di
0x180005f11  jnz     short loc_180005F21
0x180005f13  mov     r8, rbx; unsigned __int64
0x180005f16  mov     rdx, rbp; unsigned __int16 *
0x180005f19  mov     rcx, rsi; this
0x180005f1c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005f21  mov     rcx, rsi; lpOutputString
0x180005f24  call    cs:__imp_OutputDebugStringW
0x180005f2b  nop     dword ptr [rax+rax+00h]
0x180005f30  test    byte ptr [rbx+4], 4
0x180005f34  jnz     short loc_180005F3F
0x180005f36  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005f3d  jz      short loc_180005F51
0x180005f3f  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005f46  test    rax, rax
0x180005f49  jz      short loc_180005F51
0x180005f4b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005f50  nop
0x180005f51  mov     rbx, [rsp+78h+arg_10]
0x180005f59  add     rsp, 40h
0x180005f5d  pop     r15
0x180005f5f  pop     r14
0x180005f61  pop     r13
0x180005f63  pop     r12
0x180005f65  pop     rdi
0x180005f66  pop     rsi
0x180005f67  pop     rbp
0x180005f68  retn
0x180005f6a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
