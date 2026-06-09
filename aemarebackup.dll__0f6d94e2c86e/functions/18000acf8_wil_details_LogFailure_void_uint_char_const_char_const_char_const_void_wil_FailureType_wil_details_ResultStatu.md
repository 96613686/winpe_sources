# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18000acf8`
- end: `0x18000aff1`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180007e38`

## callees

- `0x18000787c`
- `0x180009f84`
- `0x18000a72c`
- `0x18000acf8`
- `0x18000ba60`
- `0x18000ba80`
- `0x18000bbac`
- `0x18000bbc8`
- `0x18000e53c`
- `0x1800ec010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae1b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000ae1b`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000af3a`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18000af3a`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000afac`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18000afac`

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
0x18000acf8  mov     [rsp+arg_10], rbx
0x18000acfd  mov     [rsp+arg_8], edx
0x18000ad01  mov     [rsp+arg_0], rcx
0x18000ad06  push    rbp
0x18000ad07  push    rsi
0x18000ad08  push    rdi
0x18000ad09  push    r12
0x18000ad0b  push    r13
0x18000ad0d  push    r14
0x18000ad0f  push    r15
0x18000ad11  sub     rsp, 40h
0x18000ad15  mov     r12, r9
0x18000ad18  mov     r13, r8
0x18000ad1b  mov     r10, rcx
0x18000ad1e  xor     eax, eax
0x18000ad20  mov     rsi, [rsp+78h+lpOutputString]
0x18000ad28  mov     [rsi], ax
0x18000ad2b  mov     rax, [rsp+78h+arg_60]
0x18000ad33  mov     byte ptr [rax], 0
0x18000ad36  mov     r14, [rsp+78h+arg_38]
0x18000ad3e  mov     edi, [r14]
0x18000ad41  mov     rbx, [rsp+78h+arg_78]
0x18000ad49  mov     [rbx+8], edi
0x18000ad4c  mov     eax, [r14+4]
0x18000ad50  mov     [rbx+0Ch], eax
0x18000ad53  xor     ebp, ebp
0x18000ad55  mov     r15d, [rsp+78h+arg_30]
0x18000ad5d  mov     ecx, r15d
0x18000ad60  test    r15d, r15d
0x18000ad63  jz      short loc_18000ADCB
0x18000ad65  sub     ecx, 1
0x18000ad68  jz      short loc_18000ADC2
0x18000ad6a  sub     ecx, 1
0x18000ad6d  jz      short loc_18000AD7D
0x18000ad6f  cmp     ecx, 1
0x18000ad72  jnz     short loc_18000ADD4
0x18000ad74  mov     ecx, edi; this
0x18000ad76  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18000ad7b  jmp     short loc_18000ADD2
0x18000ad7d  test    edi, edi
0x18000ad7f  js      short loc_18000ADB9
0x18000ad81  mov     edi, 8007029Ch
0x18000ad86  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18000ad8a  mov     rax, [rsp+78h+arg_28]
0x18000ad92  mov     [rsp+78h+var_50], rax; __int64
0x18000ad97  mov     rax, [rsp+78h+arg_20]
0x18000ad9f  mov     [rsp+78h+var_58], rax; __int64
0x18000ada4  mov     rcx, r10; int
0x18000ada7  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18000adac  mov     [rbx+8], edi
0x18000adaf  mov     ecx, edi; this
0x18000adb1  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000adb6  mov     [rbx+0Ch], eax
0x18000adb9  mov     ecx, edi; this
0x18000adbb  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18000adc0  jmp     short loc_18000ADD2
0x18000adc2  mov     ecx, edi; this
0x18000adc4  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18000adc9  jmp     short loc_18000ADD2
0x18000adcb  mov     ecx, edi; this
0x18000adcd  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18000add2  mov     ebp, eax
0x18000add4  mov     [rbx], r15d
0x18000add7  mov     eax, [rsp+78h+arg_70]
0x18000adde  mov     [rbx+4], eax
0x18000ade1  cmp     dword ptr [r14+8], 1
0x18000ade6  jnz     short loc_18000ADEE
0x18000ade8  or      eax, 8
0x18000adeb  mov     [rbx+4], eax
0x18000adee  mov     eax, 1
0x18000adf3  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18000adfb  inc     eax
0x18000adfd  mov     [rbx+10h], eax
0x18000ae00  mov     rax, [rsp+78h+arg_40]
0x18000ae08  xor     edi, edi
0x18000ae0a  test    rax, rax
0x18000ae0d  jz      short loc_18000AE14
0x18000ae0f  cmp     [rax], di
0x18000ae12  jnz     short loc_18000AE17
0x18000ae14  mov     rax, rdi
0x18000ae17  mov     [rbx+18h], rax
0x18000ae1b  call    cs:__imp_GetCurrentThreadId
0x18000ae21  mov     [rbx+20h], eax
0x18000ae24  mov     [rbx+38h], r13
0x18000ae28  mov     eax, [rsp+78h+arg_8]
0x18000ae2f  mov     [rbx+40h], eax
0x18000ae32  mov     [rbx+44h], ebp
0x18000ae35  mov     rax, [rsp+78h+arg_20]
0x18000ae3d  mov     [rbx+28h], rax
0x18000ae41  mov     [rbx+30h], r12
0x18000ae45  mov     rax, [rsp+78h+arg_28]
0x18000ae4d  mov     [rbx+88h], rax
0x18000ae54  mov     rax, [rsp+78h+arg_0]
0x18000ae5c  mov     [rbx+90h], rax
0x18000ae63  mov     [rbx+48h], rdi
0x18000ae67  xorps   xmm0, xmm0
0x18000ae6a  xor     eax, eax
0x18000ae6c  movups  xmmword ptr [rbx+68h], xmm0
0x18000ae70  mov     [rbx+78h], rax
0x18000ae74  movups  xmmword ptr [rbx+50h], xmm0
0x18000ae78  mov     [rbx+60h], rax
0x18000ae7c  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18000ae83  test    rax, rax
0x18000ae86  jz      short loc_18000AE8F
0x18000ae88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ae8d  jmp     short loc_18000AE92
0x18000ae8f  mov     rax, rdi
0x18000ae92  mov     [rbx+80h], rax
0x18000ae99  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18000aea0  test    rax, rax
0x18000aea3  jz      short loc_18000AEAD
0x18000aea5  mov     rcx, rbx
0x18000aea8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aead  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18000aeb4  test    rax, rax
0x18000aeb7  jz      short loc_18000AECF
0x18000aeb9  mov     r8d, 400h
0x18000aebf  mov     rdx, [rsp+78h+arg_60]
0x18000aec7  mov     rcx, rbx
0x18000aeca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aecf  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000aed6  test    rax, rax
0x18000aed9  jz      short loc_18000AEE3
0x18000aedb  mov     rcx, rbx
0x18000aede  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee3  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000aeea  test    rax, rax
0x18000aeed  jz      short loc_18000AEFD
0x18000aeef  test    byte ptr [rbx+4], 2
0x18000aef3  jnz     short loc_18000AEFD
0x18000aef5  mov     rcx, rbx
0x18000aef8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aefd  cmp     [rbx+8], edi
0x18000af00  jl      short loc_18000AF1C
0x18000af02  cmp     r15d, 3
0x18000af06  jnz     loc_18000AFEB
0x18000af0c  mov     ecx, 8000FFFFh; this
0x18000af11  mov     [rbx+8], ecx
0x18000af14  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18000af19  mov     [rbx+0Ch], eax
0x18000af1c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18000af23  jnz     short loc_18000AF44
0x18000af25  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18000af2c  test    rax, rax
0x18000af2f  jz      short loc_18000AF3A
0x18000af31  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af36  test    al, al
0x18000af38  jmp     short loc_18000AF42
0x18000af3a  call    cs:__imp_IsDebuggerPresent
0x18000af40  test    eax, eax
0x18000af42  jz      short loc_18000AF4A
0x18000af44  test    byte ptr [rbx+4], 2
0x18000af48  jz      short loc_18000AF6E
0x18000af4a  mov     rax, cs:g_pfnResultLoggingCallback
0x18000af51  test    rax, rax
0x18000af54  jz      short loc_18000AFB2
0x18000af56  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000af5d  jnz     short loc_18000AFB2
0x18000af5f  xor     r8d, r8d
0x18000af62  xor     edx, edx
0x18000af64  mov     rcx, rbx
0x18000af67  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af6c  jmp     short loc_18000AFB2
0x18000af6e  mov     ebp, 800h
0x18000af73  mov     rax, cs:g_pfnResultLoggingCallback
0x18000af7a  test    rax, rax
0x18000af7d  jz      short loc_18000AF96
0x18000af7f  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18000af86  jnz     short loc_18000AF96
0x18000af88  mov     r8d, ebp
0x18000af8b  mov     rdx, rsi
0x18000af8e  mov     rcx, rbx
0x18000af91  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af96  cmp     [rsi], di
0x18000af99  jnz     short loc_18000AFA9
0x18000af9b  mov     r8, rbx; unsigned __int64
0x18000af9e  mov     rdx, rbp; unsigned __int16 *
0x18000afa1  mov     rcx, rsi; this
0x18000afa4  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18000afa9  mov     rcx, rsi; lpOutputString
0x18000afac  call    cs:__imp_OutputDebugStringW
0x18000afb2  test    byte ptr [rbx+4], 4
0x18000afb6  jnz     short loc_18000AFC1
0x18000afb8  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18000afbf  jz      short loc_18000AFD3
0x18000afc1  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18000afc8  test    rax, rax
0x18000afcb  jz      short loc_18000AFD3
0x18000afcd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afd2  nop
0x18000afd3  mov     rbx, [rsp+78h+arg_10]
0x18000afdb  add     rsp, 40h
0x18000afdf  pop     r15
0x18000afe1  pop     r14
0x18000afe3  pop     r13
0x18000afe5  pop     r12
0x18000afe7  pop     rdi
0x18000afe8  pop     rsi
0x18000afe9  pop     rbp
0x18000afea  retn
0x18000afeb  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
