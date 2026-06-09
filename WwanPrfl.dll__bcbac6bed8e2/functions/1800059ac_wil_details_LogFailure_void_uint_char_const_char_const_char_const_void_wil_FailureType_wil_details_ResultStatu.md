# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800059ac`
- end: `0x180005ca5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180002d3c`

## callees

- `0x180002778`
- `0x180004f64`
- `0x180005700`
- `0x1800059ac`
- `0x1800067d4`
- `0x1800067f0`
- `0x18000691c`
- `0x180006938`
- `0x18000916c`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005acf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180005acf`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005c60`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180005c60`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005bee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180005bee`

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
  _WORD *v21; // rax
  wil::details::in1diag3 *v22; // rcx
  const struct wil::FailureInfo *v23; // r9
  __int64 ModuleName; // rax
  bool v25; // zf
  wil::details *v26; // [rsp+30h] [rbp-48h]

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
          LODWORD(v26) = -2147024228;
          wil::details::ReportFailure_Hr<2>(a1, a2, a3, a4, a5, a6, v26);
          *(_DWORD *)(a16 + 8) = -2147024228;
          *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8007029CLL);
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
  v21 = a9;
  if ( !a9 || !*a9 )
    v21 = 0;
  *(_QWORD *)(a16 + 24) = v21;
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
    ModuleName = wil::details::g_pfnGetModuleName(v22);
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
      wil::details::in1diag3::_FailFastImmediate_Unexpected(v22);
    *(_DWORD *)(a16 + 8) = -2147418113;
    *(_DWORD *)(a16 + 12) = wil::details::HrToNtStatus((wil::details *)0x8000FFFFLL);
  }
  if ( !wil::g_fIsDebuggerPresent
    && (!wil::g_pfnIsDebuggerPresent
      ? (v25 = !IsDebuggerPresent())
      : (v25 = (unsigned __int8)wil::g_pfnIsDebuggerPresent(v22) == 0),
        v25)
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
      wil::GetFailureLogString(lpOutputString, (unsigned __int16 *)0x800, a16, v23);
    OutputDebugStringW((LPCWSTR)lpOutputString);
  }
  if ( (*(_BYTE *)(a16 + 4) & 4) != 0 || wil::g_fBreakOnFailure )
  {
    if ( wil::details::g_pfnDebugBreak )
      wil::details::g_pfnDebugBreak(v22);
  }
}

```

## disassembly

```asm
0x1800059ac  mov     [rsp+arg_10], rbx
0x1800059b1  mov     [rsp+arg_8], edx
0x1800059b5  mov     [rsp+arg_0], rcx
0x1800059ba  push    rbp
0x1800059bb  push    rsi
0x1800059bc  push    rdi
0x1800059bd  push    r12
0x1800059bf  push    r13
0x1800059c1  push    r14
0x1800059c3  push    r15
0x1800059c5  sub     rsp, 40h
0x1800059c9  mov     r12, r9
0x1800059cc  mov     r13, r8
0x1800059cf  mov     r10, rcx
0x1800059d2  xor     eax, eax
0x1800059d4  mov     rsi, [rsp+78h+lpOutputString]
0x1800059dc  mov     [rsi], ax
0x1800059df  mov     rax, [rsp+78h+arg_60]
0x1800059e7  mov     byte ptr [rax], 0
0x1800059ea  mov     r14, [rsp+78h+arg_38]
0x1800059f2  mov     edi, [r14]
0x1800059f5  mov     rbx, [rsp+78h+arg_78]
0x1800059fd  mov     [rbx+8], edi
0x180005a00  mov     eax, [r14+4]
0x180005a04  mov     [rbx+0Ch], eax
0x180005a07  xor     ebp, ebp
0x180005a09  mov     r15d, [rsp+78h+arg_30]
0x180005a11  mov     ecx, r15d
0x180005a14  test    r15d, r15d
0x180005a17  jz      short loc_180005A7F
0x180005a19  sub     ecx, 1
0x180005a1c  jz      short loc_180005A76
0x180005a1e  sub     ecx, 1
0x180005a21  jz      short loc_180005A31
0x180005a23  cmp     ecx, 1
0x180005a26  jnz     short loc_180005A88
0x180005a28  mov     ecx, edi; this
0x180005a2a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x180005a2f  jmp     short loc_180005A86
0x180005a31  test    edi, edi
0x180005a33  js      short loc_180005A6D
0x180005a35  mov     edi, 8007029Ch
0x180005a3a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180005a3e  mov     rax, [rsp+78h+arg_28]
0x180005a46  mov     [rsp+78h+var_50], rax; __int64
0x180005a4b  mov     rax, [rsp+78h+arg_20]
0x180005a53  mov     [rsp+78h+var_58], rax; __int64
0x180005a58  mov     rcx, r10; int
0x180005a5b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180005a60  mov     [rbx+8], edi
0x180005a63  mov     ecx, edi; this
0x180005a65  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005a6a  mov     [rbx+0Ch], eax
0x180005a6d  mov     ecx, edi; this
0x180005a6f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180005a74  jmp     short loc_180005A86
0x180005a76  mov     ecx, edi; this
0x180005a78  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180005a7d  jmp     short loc_180005A86
0x180005a7f  mov     ecx, edi; this
0x180005a81  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180005a86  mov     ebp, eax
0x180005a88  mov     [rbx], r15d
0x180005a8b  mov     eax, [rsp+78h+arg_70]
0x180005a92  mov     [rbx+4], eax
0x180005a95  cmp     dword ptr [r14+8], 1
0x180005a9a  jnz     short loc_180005AA2
0x180005a9c  or      eax, 8
0x180005a9f  mov     [rbx+4], eax
0x180005aa2  mov     eax, 1
0x180005aa7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180005aaf  inc     eax
0x180005ab1  mov     [rbx+10h], eax
0x180005ab4  mov     rax, [rsp+78h+arg_40]
0x180005abc  xor     edi, edi
0x180005abe  test    rax, rax
0x180005ac1  jz      short loc_180005AC8
0x180005ac3  cmp     [rax], di
0x180005ac6  jnz     short loc_180005ACB
0x180005ac8  mov     rax, rdi
0x180005acb  mov     [rbx+18h], rax
0x180005acf  call    cs:__imp_GetCurrentThreadId
0x180005ad5  mov     [rbx+20h], eax
0x180005ad8  mov     [rbx+38h], r13
0x180005adc  mov     eax, [rsp+78h+arg_8]
0x180005ae3  mov     [rbx+40h], eax
0x180005ae6  mov     [rbx+44h], ebp
0x180005ae9  mov     rax, [rsp+78h+arg_20]
0x180005af1  mov     [rbx+28h], rax
0x180005af5  mov     [rbx+30h], r12
0x180005af9  mov     rax, [rsp+78h+arg_28]
0x180005b01  mov     [rbx+88h], rax
0x180005b08  mov     rax, [rsp+78h+arg_0]
0x180005b10  mov     [rbx+90h], rax
0x180005b17  mov     [rbx+48h], rdi
0x180005b1b  xorps   xmm0, xmm0
0x180005b1e  xor     eax, eax
0x180005b20  movups  xmmword ptr [rbx+68h], xmm0
0x180005b24  mov     [rbx+78h], rax
0x180005b28  movups  xmmword ptr [rbx+50h], xmm0
0x180005b2c  mov     [rbx+60h], rax
0x180005b30  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180005b37  test    rax, rax
0x180005b3a  jz      short loc_180005B43
0x180005b3c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b41  jmp     short loc_180005B46
0x180005b43  mov     rax, rdi
0x180005b46  mov     [rbx+80h], rax
0x180005b4d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180005b54  test    rax, rax
0x180005b57  jz      short loc_180005B61
0x180005b59  mov     rcx, rbx
0x180005b5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b61  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180005b68  test    rax, rax
0x180005b6b  jz      short loc_180005B83
0x180005b6d  mov     r8d, 400h
0x180005b73  mov     rdx, [rsp+78h+arg_60]
0x180005b7b  mov     rcx, rbx
0x180005b7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b83  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b8a  test    rax, rax
0x180005b8d  jz      short loc_180005B97
0x180005b8f  mov     rcx, rbx
0x180005b92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005b97  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180005b9e  test    rax, rax
0x180005ba1  jz      short loc_180005BB1
0x180005ba3  test    byte ptr [rbx+4], 2
0x180005ba7  jnz     short loc_180005BB1
0x180005ba9  mov     rcx, rbx
0x180005bac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bb1  cmp     [rbx+8], edi
0x180005bb4  jl      short loc_180005BD0
0x180005bb6  cmp     r15d, 3
0x180005bba  jnz     loc_180005C9F
0x180005bc0  mov     ecx, 8000FFFFh; this
0x180005bc5  mov     [rbx+8], ecx
0x180005bc8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180005bcd  mov     [rbx+0Ch], eax
0x180005bd0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180005bd7  jnz     short loc_180005BF8
0x180005bd9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180005be0  test    rax, rax
0x180005be3  jz      short loc_180005BEE
0x180005be5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005bea  test    al, al
0x180005bec  jmp     short loc_180005BF6
0x180005bee  call    cs:__imp_IsDebuggerPresent
0x180005bf4  test    eax, eax
0x180005bf6  jz      short loc_180005BFE
0x180005bf8  test    byte ptr [rbx+4], 2
0x180005bfc  jz      short loc_180005C22
0x180005bfe  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c05  test    rax, rax
0x180005c08  jz      short loc_180005C66
0x180005c0a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005c11  jnz     short loc_180005C66
0x180005c13  xor     r8d, r8d
0x180005c16  xor     edx, edx
0x180005c18  mov     rcx, rbx
0x180005c1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c20  jmp     short loc_180005C66
0x180005c22  mov     ebp, 800h
0x180005c27  mov     rax, cs:g_pfnResultLoggingCallback
0x180005c2e  test    rax, rax
0x180005c31  jz      short loc_180005C4A
0x180005c33  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180005c3a  jnz     short loc_180005C4A
0x180005c3c  mov     r8d, ebp
0x180005c3f  mov     rdx, rsi
0x180005c42  mov     rcx, rbx
0x180005c45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c4a  cmp     [rsi], di
0x180005c4d  jnz     short loc_180005C5D
0x180005c4f  mov     r8, rbx; unsigned __int64
0x180005c52  mov     rdx, rbp; unsigned __int16 *
0x180005c55  mov     rcx, rsi; this
0x180005c58  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180005c5d  mov     rcx, rsi; lpOutputString
0x180005c60  call    cs:__imp_OutputDebugStringW
0x180005c66  test    byte ptr [rbx+4], 4
0x180005c6a  jnz     short loc_180005C75
0x180005c6c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180005c73  jz      short loc_180005C87
0x180005c75  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180005c7c  test    rax, rax
0x180005c7f  jz      short loc_180005C87
0x180005c81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005c86  nop
0x180005c87  mov     rbx, [rsp+78h+arg_10]
0x180005c8f  add     rsp, 40h
0x180005c93  pop     r15
0x180005c95  pop     r14
0x180005c97  pop     r13
0x180005c99  pop     r12
0x180005c9b  pop     rdi
0x180005c9c  pop     rsi
0x180005c9d  pop     rbp
0x180005c9e  retn
0x180005c9f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
