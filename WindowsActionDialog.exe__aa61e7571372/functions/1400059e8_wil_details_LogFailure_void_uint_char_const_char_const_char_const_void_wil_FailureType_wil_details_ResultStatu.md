# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1400059e8`
- end: `0x140005ce1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x140002a48`

## callees

- `0x1400023c0`
- `0x1400046a4`
- `0x1400057fc`
- `0x1400059e8`
- `0x14000601c`
- `0x140006040`
- `0x140006054`
- `0x140006070`
- `0x1400076dc`
- `0x14000a010`

## import_xrefs

- `KERNEL32!IsDebuggerPresent` at `0x140005c2a`
- `KERNEL32!IsDebuggerPresent` at `0x140005c2a`
- `KERNEL32!OutputDebugStringW` at `0x140005c9c`
- `KERNEL32!OutputDebugStringW` at `0x140005c9c`
- `KERNEL32!GetCurrentThreadId` at `0x140005b0b`
- `KERNEL32!GetCurrentThreadId` at `0x140005b0b`

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
  wil::details::in1diag5 *v24; // rcx
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
      wil::details::in1diag5::_FailFastImmediate_Unexpected(v24);
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
0x1400059e8  mov     [rsp+arg_10], rbx
0x1400059ed  mov     [rsp+arg_8], edx
0x1400059f1  mov     [rsp+arg_0], rcx
0x1400059f6  push    rbp
0x1400059f7  push    rsi
0x1400059f8  push    rdi
0x1400059f9  push    r12
0x1400059fb  push    r13
0x1400059fd  push    r14
0x1400059ff  push    r15
0x140005a01  sub     rsp, 40h
0x140005a05  mov     r12, r9
0x140005a08  mov     r13, r8
0x140005a0b  mov     r10, rcx
0x140005a0e  xor     eax, eax
0x140005a10  mov     rsi, [rsp+78h+lpOutputString]
0x140005a18  mov     [rsi], ax
0x140005a1b  mov     rax, [rsp+78h+arg_60]
0x140005a23  mov     byte ptr [rax], 0
0x140005a26  mov     r14, [rsp+78h+arg_38]
0x140005a2e  mov     edi, [r14]
0x140005a31  mov     rbx, [rsp+78h+arg_78]
0x140005a39  mov     [rbx+8], edi
0x140005a3c  mov     eax, [r14+4]
0x140005a40  mov     [rbx+0Ch], eax
0x140005a43  xor     ebp, ebp
0x140005a45  mov     r15d, [rsp+78h+arg_30]
0x140005a4d  mov     ecx, r15d
0x140005a50  test    r15d, r15d
0x140005a53  jz      short loc_140005ABB
0x140005a55  sub     ecx, 1
0x140005a58  jz      short loc_140005AB2
0x140005a5a  sub     ecx, 1
0x140005a5d  jz      short loc_140005A6D
0x140005a5f  cmp     ecx, 1
0x140005a62  jnz     short loc_140005AC4
0x140005a64  mov     ecx, edi; this
0x140005a66  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x140005a6b  jmp     short loc_140005AC2
0x140005a6d  test    edi, edi
0x140005a6f  js      short loc_140005AA9
0x140005a71  mov     edi, 8007029Ch
0x140005a76  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x140005a7a  mov     rax, [rsp+78h+arg_28]
0x140005a82  mov     [rsp+78h+var_50], rax; __int64
0x140005a87  mov     rax, [rsp+78h+arg_20]
0x140005a8f  mov     [rsp+78h+var_58], rax; __int64
0x140005a94  mov     rcx, r10; int
0x140005a97  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x140005a9c  mov     [rbx+8], edi
0x140005a9f  mov     ecx, edi; this
0x140005aa1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005aa6  mov     [rbx+0Ch], eax
0x140005aa9  mov     ecx, edi; this
0x140005aab  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x140005ab0  jmp     short loc_140005AC2
0x140005ab2  mov     ecx, edi; this
0x140005ab4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x140005ab9  jmp     short loc_140005AC2
0x140005abb  mov     ecx, edi; this
0x140005abd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x140005ac2  mov     ebp, eax
0x140005ac4  mov     [rbx], r15d
0x140005ac7  mov     eax, [rsp+78h+arg_70]
0x140005ace  mov     [rbx+4], eax
0x140005ad1  cmp     dword ptr [r14+8], 1
0x140005ad6  jnz     short loc_140005ADE
0x140005ad8  or      eax, 8
0x140005adb  mov     [rbx+4], eax
0x140005ade  mov     eax, 1
0x140005ae3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x140005aeb  inc     eax
0x140005aed  mov     [rbx+10h], eax
0x140005af0  mov     rax, [rsp+78h+arg_40]
0x140005af8  xor     edi, edi
0x140005afa  test    rax, rax
0x140005afd  jz      short loc_140005B04
0x140005aff  cmp     [rax], di
0x140005b02  jnz     short loc_140005B07
0x140005b04  mov     rax, rdi
0x140005b07  mov     [rbx+18h], rax
0x140005b0b  call    cs:__imp_GetCurrentThreadId
0x140005b11  mov     [rbx+20h], eax
0x140005b14  mov     [rbx+38h], r13
0x140005b18  mov     eax, [rsp+78h+arg_8]
0x140005b1f  mov     [rbx+40h], eax
0x140005b22  mov     [rbx+44h], ebp
0x140005b25  mov     rax, [rsp+78h+arg_20]
0x140005b2d  mov     [rbx+28h], rax
0x140005b31  mov     [rbx+30h], r12
0x140005b35  mov     rax, [rsp+78h+arg_28]
0x140005b3d  mov     [rbx+88h], rax
0x140005b44  mov     rax, [rsp+78h+arg_0]
0x140005b4c  mov     [rbx+90h], rax
0x140005b53  mov     [rbx+48h], rdi
0x140005b57  xorps   xmm0, xmm0
0x140005b5a  xor     eax, eax
0x140005b5c  movups  xmmword ptr [rbx+68h], xmm0
0x140005b60  mov     [rbx+78h], rax
0x140005b64  movups  xmmword ptr [rbx+50h], xmm0
0x140005b68  mov     [rbx+60h], rax
0x140005b6c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x140005b73  test    rax, rax
0x140005b76  jz      short loc_140005B7F
0x140005b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b7d  jmp     short loc_140005B82
0x140005b7f  mov     rax, rdi
0x140005b82  mov     [rbx+80h], rax
0x140005b89  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x140005b90  test    rax, rax
0x140005b93  jz      short loc_140005B9D
0x140005b95  mov     rcx, rbx
0x140005b98  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005b9d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x140005ba4  test    rax, rax
0x140005ba7  jz      short loc_140005BBF
0x140005ba9  mov     r8d, 400h
0x140005baf  mov     rdx, [rsp+78h+arg_60]
0x140005bb7  mov     rcx, rbx
0x140005bba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bbf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005bc6  test    rax, rax
0x140005bc9  jz      short loc_140005BD3
0x140005bcb  mov     rcx, rbx
0x140005bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bd3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x140005bda  test    rax, rax
0x140005bdd  jz      short loc_140005BED
0x140005bdf  test    byte ptr [rbx+4], 2
0x140005be3  jnz     short loc_140005BED
0x140005be5  mov     rcx, rbx
0x140005be8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005bed  cmp     [rbx+8], edi
0x140005bf0  jl      short loc_140005C0C
0x140005bf2  cmp     r15d, 3
0x140005bf6  jnz     loc_140005CDB
0x140005bfc  mov     ecx, 8000FFFFh; this
0x140005c01  mov     [rbx+8], ecx
0x140005c04  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x140005c09  mov     [rbx+0Ch], eax
0x140005c0c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x140005c13  jnz     short loc_140005C34
0x140005c15  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x140005c1c  test    rax, rax
0x140005c1f  jz      short loc_140005C2A
0x140005c21  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c26  test    al, al
0x140005c28  jmp     short loc_140005C32
0x140005c2a  call    cs:__imp_IsDebuggerPresent
0x140005c30  test    eax, eax
0x140005c32  jz      short loc_140005C3A
0x140005c34  test    byte ptr [rbx+4], 2
0x140005c38  jz      short loc_140005C5E
0x140005c3a  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c41  test    rax, rax
0x140005c44  jz      short loc_140005CA2
0x140005c46  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005c4d  jnz     short loc_140005CA2
0x140005c4f  xor     r8d, r8d
0x140005c52  xor     edx, edx
0x140005c54  mov     rcx, rbx
0x140005c57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c5c  jmp     short loc_140005CA2
0x140005c5e  mov     ebp, 800h
0x140005c63  mov     rax, cs:g_pfnResultLoggingCallback
0x140005c6a  test    rax, rax
0x140005c6d  jz      short loc_140005C86
0x140005c6f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x140005c76  jnz     short loc_140005C86
0x140005c78  mov     r8d, ebp
0x140005c7b  mov     rdx, rsi
0x140005c7e  mov     rcx, rbx
0x140005c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005c86  cmp     [rsi], di
0x140005c89  jnz     short loc_140005C99
0x140005c8b  mov     r8, rbx; unsigned __int64
0x140005c8e  mov     rdx, rbp; unsigned __int16 *
0x140005c91  mov     rcx, rsi; this
0x140005c94  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x140005c99  mov     rcx, rsi; lpOutputString
0x140005c9c  call    cs:__imp_OutputDebugStringW
0x140005ca2  test    byte ptr [rbx+4], 4
0x140005ca6  jnz     short loc_140005CB1
0x140005ca8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x140005caf  jz      short loc_140005CC3
0x140005cb1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x140005cb8  test    rax, rax
0x140005cbb  jz      short loc_140005CC3
0x140005cbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140005cc2  nop
0x140005cc3  mov     rbx, [rsp+78h+arg_10]
0x140005ccb  add     rsp, 40h
0x140005ccf  pop     r15
0x140005cd1  pop     r14
0x140005cd3  pop     r13
0x140005cd5  pop     r12
0x140005cd7  pop     rdi
0x140005cd8  pop     rsi
0x140005cd9  pop     rbp
0x140005cda  retn
0x140005cdb  call    ?_FailFastImmediate_Unexpected@in1diag5@details@wil@@YAXXZ; wil::details::in1diag5::_FailFastImmediate_Unexpected(void)
```
