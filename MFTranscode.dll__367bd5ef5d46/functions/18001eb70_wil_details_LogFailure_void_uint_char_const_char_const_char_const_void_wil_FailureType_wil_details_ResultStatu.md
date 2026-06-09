# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x18001eb70`
- end: `0x18001ee68`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `760`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: ``

## callers

- `0x18001c4f8`
- `0x18001c848`

## callees

- `0x180015c50`
- `0x18001c440`
- `0x18001e154`
- `0x18001eb70`
- `0x180020ff8`
- `0x180021020`
- `0x180021034`
- `0x180021050`
- `0x180027c34`
- `0x18005a010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ec93`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18001ec93`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ee24`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x18001ee24`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001edb2`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x18001edb2`

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
0x18001eb70  mov     [rsp+arg_10], rbx
0x18001eb75  mov     [rsp+arg_8], edx
0x18001eb79  mov     [rsp+arg_0], rcx
0x18001eb7e  push    rbp
0x18001eb7f  push    rsi
0x18001eb80  push    rdi
0x18001eb81  push    r12
0x18001eb83  push    r13
0x18001eb85  push    r14
0x18001eb87  push    r15
0x18001eb89  sub     rsp, 40h
0x18001eb8d  mov     r14, [rsp+78h+arg_38]
0x18001eb95  xor     eax, eax
0x18001eb97  mov     rbx, [rsp+78h+arg_78]
0x18001eb9f  xor     ebp, ebp
0x18001eba1  mov     r15d, [rsp+78h+arg_30]
0x18001eba9  mov     r10, rcx
0x18001ebac  mov     rsi, [rsp+78h+lpOutputString]
0x18001ebb4  mov     r12, r9
0x18001ebb7  mov     r13, r8
0x18001ebba  mov     ecx, r15d
0x18001ebbd  mov     [rsi], ax
0x18001ebc0  mov     rax, [rsp+78h+arg_60]
0x18001ebc8  mov     byte ptr [rax], 0
0x18001ebcb  mov     edi, [r14]
0x18001ebce  mov     [rbx+8], edi
0x18001ebd1  mov     eax, [r14+4]
0x18001ebd5  mov     [rbx+0Ch], eax
0x18001ebd8  test    r15d, r15d
0x18001ebdb  jz      short loc_18001EC43
0x18001ebdd  sub     ecx, 1
0x18001ebe0  jz      short loc_18001EC3A
0x18001ebe2  sub     ecx, 1
0x18001ebe5  jz      short loc_18001EBF5
0x18001ebe7  cmp     ecx, 1
0x18001ebea  jnz     short loc_18001EC4C
0x18001ebec  mov     ecx, edi; this
0x18001ebee  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001ebf3  jmp     short loc_18001EC4A
0x18001ebf5  test    edi, edi
0x18001ebf7  js      short loc_18001EC31
0x18001ebf9  mov     rax, [rsp+78h+arg_28]
0x18001ec01  mov     edi, 8007029Ch
0x18001ec06  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001ec0a  mov     rcx, r10; int
0x18001ec0d  mov     [rsp+78h+var_50], rax; __int64
0x18001ec12  mov     rax, [rsp+78h+arg_20]
0x18001ec1a  mov     [rsp+78h+var_58], rax; __int64
0x18001ec1f  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x18001ec24  mov     ecx, edi; this
0x18001ec26  mov     [rbx+8], edi
0x18001ec29  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ec2e  mov     [rbx+0Ch], eax
0x18001ec31  mov     ecx, edi; this
0x18001ec33  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x18001ec38  jmp     short loc_18001EC4A
0x18001ec3a  mov     ecx, edi; this
0x18001ec3c  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001ec41  jmp     short loc_18001EC4A
0x18001ec43  mov     ecx, edi; this
0x18001ec45  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x18001ec4a  mov     ebp, eax
0x18001ec4c  mov     eax, [rsp+78h+arg_70]
0x18001ec53  mov     [rbx+4], eax
0x18001ec56  mov     [rbx], r15d
0x18001ec59  cmp     dword ptr [r14+8], 1
0x18001ec5e  jnz     short loc_18001EC66
0x18001ec60  or      eax, 8
0x18001ec63  mov     [rbx+4], eax
0x18001ec66  mov     eax, 1
0x18001ec6b  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x18001ec73  inc     eax
0x18001ec75  xor     edi, edi
0x18001ec77  mov     [rbx+10h], eax
0x18001ec7a  mov     rax, [rsp+78h+arg_40]
0x18001ec82  test    rax, rax
0x18001ec85  jz      short loc_18001EC8C
0x18001ec87  cmp     [rax], di
0x18001ec8a  jnz     short loc_18001EC8F
0x18001ec8c  mov     rax, rdi
0x18001ec8f  mov     [rbx+18h], rax
0x18001ec93  call    cs:__imp_GetCurrentThreadId
0x18001ec99  mov     [rbx+38h], r13
0x18001ec9d  xorps   xmm0, xmm0
0x18001eca0  mov     [rbx+20h], eax
0x18001eca3  mov     eax, [rsp+78h+arg_8]
0x18001ecaa  mov     [rbx+40h], eax
0x18001ecad  mov     rax, [rsp+78h+arg_20]
0x18001ecb5  mov     [rbx+28h], rax
0x18001ecb9  mov     rax, [rsp+78h+arg_28]
0x18001ecc1  mov     [rbx+88h], rax
0x18001ecc8  mov     rax, [rsp+78h+arg_0]
0x18001ecd0  mov     [rbx+90h], rax
0x18001ecd7  xor     eax, eax
0x18001ecd9  mov     [rbx+44h], ebp
0x18001ecdc  mov     [rbx+30h], r12
0x18001ece0  mov     [rbx+48h], rdi
0x18001ece4  movups  xmmword ptr [rbx+68h], xmm0
0x18001ece8  mov     [rbx+78h], rax
0x18001ecec  movups  xmmword ptr [rbx+50h], xmm0
0x18001ecf0  mov     [rbx+60h], rax
0x18001ecf4  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x18001ecfb  test    rax, rax
0x18001ecfe  jz      short loc_18001ED07
0x18001ed00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed05  jmp     short loc_18001ED0A
0x18001ed07  mov     rax, rdi
0x18001ed0a  mov     [rbx+80h], rax
0x18001ed11  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x18001ed18  test    rax, rax
0x18001ed1b  jz      short loc_18001ED25
0x18001ed1d  mov     rcx, rbx
0x18001ed20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed25  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x18001ed2c  test    rax, rax
0x18001ed2f  jz      short loc_18001ED47
0x18001ed31  mov     rdx, [rsp+78h+arg_60]
0x18001ed39  mov     r8d, 400h
0x18001ed3f  mov     rcx, rbx
0x18001ed42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed47  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ed4e  test    rax, rax
0x18001ed51  jz      short loc_18001ED5B
0x18001ed53  mov     rcx, rbx
0x18001ed56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed5b  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001ed62  test    rax, rax
0x18001ed65  jz      short loc_18001ED75
0x18001ed67  test    byte ptr [rbx+4], 2
0x18001ed6b  jnz     short loc_18001ED75
0x18001ed6d  mov     rcx, rbx
0x18001ed70  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ed75  cmp     [rbx+8], edi
0x18001ed78  jl      short loc_18001ED94
0x18001ed7a  cmp     r15d, 3
0x18001ed7e  jnz     loc_18001EE62
0x18001ed84  mov     ecx, 8000FFFFh; this
0x18001ed89  mov     [rbx+8], ecx
0x18001ed8c  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001ed91  mov     [rbx+0Ch], eax
0x18001ed94  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x18001ed9b  jnz     short loc_18001EDBC
0x18001ed9d  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x18001eda4  test    rax, rax
0x18001eda7  jz      short loc_18001EDB2
0x18001eda9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001edae  test    al, al
0x18001edb0  jmp     short loc_18001EDBA
0x18001edb2  call    cs:__imp_IsDebuggerPresent
0x18001edb8  test    eax, eax
0x18001edba  jz      short loc_18001EDC2
0x18001edbc  test    byte ptr [rbx+4], 2
0x18001edc0  jz      short loc_18001EDE6
0x18001edc2  mov     rax, cs:g_pfnResultLoggingCallback
0x18001edc9  test    rax, rax
0x18001edcc  jz      short loc_18001EE2A
0x18001edce  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001edd5  jnz     short loc_18001EE2A
0x18001edd7  xor     r8d, r8d
0x18001edda  xor     edx, edx
0x18001eddc  mov     rcx, rbx
0x18001eddf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ede4  jmp     short loc_18001EE2A
0x18001ede6  mov     rax, cs:g_pfnResultLoggingCallback
0x18001eded  mov     ebp, 800h
0x18001edf2  test    rax, rax
0x18001edf5  jz      short loc_18001EE0E
0x18001edf7  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x18001edfe  jnz     short loc_18001EE0E
0x18001ee00  mov     r8d, ebp
0x18001ee03  mov     rdx, rsi
0x18001ee06  mov     rcx, rbx
0x18001ee09  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee0e  cmp     [rsi], di
0x18001ee11  jnz     short loc_18001EE21
0x18001ee13  mov     r8, rbx; unsigned __int64
0x18001ee16  mov     rdx, rbp; unsigned __int16 *
0x18001ee19  mov     rcx, rsi; this
0x18001ee1c  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x18001ee21  mov     rcx, rsi; lpOutputString
0x18001ee24  call    cs:__imp_OutputDebugStringW
0x18001ee2a  test    byte ptr [rbx+4], 4
0x18001ee2e  jnz     short loc_18001EE39
0x18001ee30  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x18001ee37  jz      short loc_18001EE4A
0x18001ee39  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x18001ee40  test    rax, rax
0x18001ee43  jz      short loc_18001EE4A
0x18001ee45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ee4a  mov     rbx, [rsp+78h+arg_10]
0x18001ee52  add     rsp, 40h
0x18001ee56  pop     r15
0x18001ee58  pop     r14
0x18001ee5a  pop     r13
0x18001ee5c  pop     r12
0x18001ee5e  pop     rdi
0x18001ee5f  pop     rsi
0x18001ee60  pop     rbp
0x18001ee61  retn
0x18001ee62  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
