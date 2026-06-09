# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x1800107ac`
- end: `0x180010aa5`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: ``
- caller_count: `4`
- callee_count: `10`
- tags: ``

## callers

- `0x18000d60c`
- `0x18000d978`
- `0x18002cde8`
- `0x18003bdd0`

## callees

- `0x18000d544`
- `0x18000fae4`
- `0x180010398`
- `0x1800107ac`
- `0x18001167c`
- `0x1800116a0`
- `0x1800117f0`
- `0x18001180c`
- `0x1800137fc`
- `0x18005c010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108cf`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x1800108cf`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800109ee`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x1800109ee`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010a60`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180010a60`

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
0x1800107ac  mov     [rsp+arg_10], rbx
0x1800107b1  mov     [rsp+arg_8], edx
0x1800107b5  mov     [rsp+arg_0], rcx
0x1800107ba  push    rbp
0x1800107bb  push    rsi
0x1800107bc  push    rdi
0x1800107bd  push    r12
0x1800107bf  push    r13
0x1800107c1  push    r14
0x1800107c3  push    r15
0x1800107c5  sub     rsp, 40h
0x1800107c9  mov     r12, r9
0x1800107cc  mov     r13, r8
0x1800107cf  mov     r10, rcx
0x1800107d2  xor     eax, eax
0x1800107d4  mov     rsi, [rsp+78h+lpOutputString]
0x1800107dc  mov     [rsi], ax
0x1800107df  mov     rax, [rsp+78h+arg_60]
0x1800107e7  mov     byte ptr [rax], 0
0x1800107ea  mov     r14, [rsp+78h+arg_38]
0x1800107f2  mov     edi, [r14]
0x1800107f5  mov     rbx, [rsp+78h+arg_78]
0x1800107fd  mov     [rbx+8], edi
0x180010800  mov     eax, [r14+4]
0x180010804  mov     [rbx+0Ch], eax
0x180010807  xor     ebp, ebp
0x180010809  mov     r15d, [rsp+78h+arg_30]
0x180010811  mov     ecx, r15d
0x180010814  test    r15d, r15d
0x180010817  jz      short loc_18001087F
0x180010819  sub     ecx, 1
0x18001081c  jz      short loc_180010876
0x18001081e  sub     ecx, 1
0x180010821  jz      short loc_180010831
0x180010823  cmp     ecx, 1
0x180010826  jnz     short loc_180010888
0x180010828  mov     ecx, edi; this
0x18001082a  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x18001082f  jmp     short loc_180010886
0x180010831  test    edi, edi
0x180010833  js      short loc_18001086D
0x180010835  mov     edi, 8007029Ch
0x18001083a  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x18001083e  mov     rax, [rsp+78h+arg_28]
0x180010846  mov     [rsp+78h+var_50], rax; __int64
0x18001084b  mov     rax, [rsp+78h+arg_20]
0x180010853  mov     [rsp+78h+var_58], rax; __int64
0x180010858  mov     rcx, r10; int
0x18001085b  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180010860  mov     [rbx+8], edi
0x180010863  mov     ecx, edi; this
0x180010865  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x18001086a  mov     [rbx+0Ch], eax
0x18001086d  mov     ecx, edi; this
0x18001086f  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180010874  jmp     short loc_180010886
0x180010876  mov     ecx, edi; this
0x180010878  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x18001087d  jmp     short loc_180010886
0x18001087f  mov     ecx, edi; this
0x180010881  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180010886  mov     ebp, eax
0x180010888  mov     [rbx], r15d
0x18001088b  mov     eax, [rsp+78h+arg_70]
0x180010892  mov     [rbx+4], eax
0x180010895  cmp     dword ptr [r14+8], 1
0x18001089a  jnz     short loc_1800108A2
0x18001089c  or      eax, 8
0x18001089f  mov     [rbx+4], eax
0x1800108a2  mov     eax, 1
0x1800108a7  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x1800108af  inc     eax
0x1800108b1  mov     [rbx+10h], eax
0x1800108b4  mov     rax, [rsp+78h+arg_40]
0x1800108bc  xor     edi, edi
0x1800108be  test    rax, rax
0x1800108c1  jz      short loc_1800108C8
0x1800108c3  cmp     [rax], di
0x1800108c6  jnz     short loc_1800108CB
0x1800108c8  mov     rax, rdi
0x1800108cb  mov     [rbx+18h], rax
0x1800108cf  call    cs:__imp_GetCurrentThreadId
0x1800108d5  mov     [rbx+20h], eax
0x1800108d8  mov     [rbx+38h], r13
0x1800108dc  mov     eax, [rsp+78h+arg_8]
0x1800108e3  mov     [rbx+40h], eax
0x1800108e6  mov     [rbx+44h], ebp
0x1800108e9  mov     rax, [rsp+78h+arg_20]
0x1800108f1  mov     [rbx+28h], rax
0x1800108f5  mov     [rbx+30h], r12
0x1800108f9  mov     rax, [rsp+78h+arg_28]
0x180010901  mov     [rbx+88h], rax
0x180010908  mov     rax, [rsp+78h+arg_0]
0x180010910  mov     [rbx+90h], rax
0x180010917  mov     [rbx+48h], rdi
0x18001091b  xorps   xmm0, xmm0
0x18001091e  xor     eax, eax
0x180010920  movups  xmmword ptr [rbx+68h], xmm0
0x180010924  mov     [rbx+78h], rax
0x180010928  movups  xmmword ptr [rbx+50h], xmm0
0x18001092c  mov     [rbx+60h], rax
0x180010930  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180010937  test    rax, rax
0x18001093a  jz      short loc_180010943
0x18001093c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010941  jmp     short loc_180010946
0x180010943  mov     rax, rdi
0x180010946  mov     [rbx+80h], rax
0x18001094d  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180010954  test    rax, rax
0x180010957  jz      short loc_180010961
0x180010959  mov     rcx, rbx
0x18001095c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010961  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180010968  test    rax, rax
0x18001096b  jz      short loc_180010983
0x18001096d  mov     r8d, 400h
0x180010973  mov     rdx, [rsp+78h+arg_60]
0x18001097b  mov     rcx, rbx
0x18001097e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010983  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001098a  test    rax, rax
0x18001098d  jz      short loc_180010997
0x18001098f  mov     rcx, rbx
0x180010992  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010997  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18001099e  test    rax, rax
0x1800109a1  jz      short loc_1800109B1
0x1800109a3  test    byte ptr [rbx+4], 2
0x1800109a7  jnz     short loc_1800109B1
0x1800109a9  mov     rcx, rbx
0x1800109ac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109b1  cmp     [rbx+8], edi
0x1800109b4  jl      short loc_1800109D0
0x1800109b6  cmp     r15d, 3
0x1800109ba  jnz     loc_180010A9F
0x1800109c0  mov     ecx, 8000FFFFh; this
0x1800109c5  mov     [rbx+8], ecx
0x1800109c8  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x1800109cd  mov     [rbx+0Ch], eax
0x1800109d0  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x1800109d7  jnz     short loc_1800109F8
0x1800109d9  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x1800109e0  test    rax, rax
0x1800109e3  jz      short loc_1800109EE
0x1800109e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109ea  test    al, al
0x1800109ec  jmp     short loc_1800109F6
0x1800109ee  call    cs:__imp_IsDebuggerPresent
0x1800109f4  test    eax, eax
0x1800109f6  jz      short loc_1800109FE
0x1800109f8  test    byte ptr [rbx+4], 2
0x1800109fc  jz      short loc_180010A22
0x1800109fe  mov     rax, cs:g_pfnResultLoggingCallback
0x180010a05  test    rax, rax
0x180010a08  jz      short loc_180010A66
0x180010a0a  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010a11  jnz     short loc_180010A66
0x180010a13  xor     r8d, r8d
0x180010a16  xor     edx, edx
0x180010a18  mov     rcx, rbx
0x180010a1b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a20  jmp     short loc_180010A66
0x180010a22  mov     ebp, 800h
0x180010a27  mov     rax, cs:g_pfnResultLoggingCallback
0x180010a2e  test    rax, rax
0x180010a31  jz      short loc_180010A4A
0x180010a33  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180010a3a  jnz     short loc_180010A4A
0x180010a3c  mov     r8d, ebp
0x180010a3f  mov     rdx, rsi
0x180010a42  mov     rcx, rbx
0x180010a45  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a4a  cmp     [rsi], di
0x180010a4d  jnz     short loc_180010A5D
0x180010a4f  mov     r8, rbx; unsigned __int64
0x180010a52  mov     rdx, rbp; unsigned __int16 *
0x180010a55  mov     rcx, rsi; this
0x180010a58  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180010a5d  mov     rcx, rsi; lpOutputString
0x180010a60  call    cs:__imp_OutputDebugStringW
0x180010a66  test    byte ptr [rbx+4], 4
0x180010a6a  jnz     short loc_180010A75
0x180010a6c  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180010a73  jz      short loc_180010A87
0x180010a75  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180010a7c  test    rax, rax
0x180010a7f  jz      short loc_180010A87
0x180010a81  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a86  nop
0x180010a87  mov     rbx, [rsp+78h+arg_10]
0x180010a8f  add     rsp, 40h
0x180010a93  pop     r15
0x180010a95  pop     r14
0x180010a97  pop     r13
0x180010a99  pop     r12
0x180010a9b  pop     rdi
0x180010a9c  pop     rsi
0x180010a9d  pop     rbp
0x180010a9e  retn
0x180010a9f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
