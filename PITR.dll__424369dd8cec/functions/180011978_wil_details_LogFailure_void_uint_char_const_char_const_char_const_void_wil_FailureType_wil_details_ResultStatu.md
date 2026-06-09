# wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)

- ea: `0x180011978`
- end: `0x180011c71`
- name: `?LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@2@AEBUResultStatus@12@PEBG_NPEAG_KPEAD7W4FailureFlags@2@PEAUFailureInfo@2@@Z`
- size: `761`
- prototype: `void __fastcall(__int64, int, __int64, __int64, __int64, __int64, int, unsigned int *, _WORD *, __int64, wil *lpOutputString, __int64, _BYTE *, __int64, int, unsigned __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: ``

## callers

- `0x180003468`

## callees

- `0x180002ea4`
- `0x18000e76c`
- `0x180010a08`
- `0x180011978`
- `0x180013a40`
- `0x180013a60`
- `0x180013b90`
- `0x180013bac`
- `0x18001dd64`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a9b`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180011a9b`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c2c`
- `api-ms-win-core-debug-l1-1-0!OutputDebugStringW` at `0x180011c2c`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011bba`
- `api-ms-win-core-debug-l1-1-0!IsDebuggerPresent` at `0x180011bba`

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
0x180011978  mov     [rsp+arg_10], rbx
0x18001197d  mov     [rsp+arg_8], edx
0x180011981  mov     [rsp+arg_0], rcx
0x180011986  push    rbp
0x180011987  push    rsi
0x180011988  push    rdi
0x180011989  push    r12
0x18001198b  push    r13
0x18001198d  push    r14
0x18001198f  push    r15
0x180011991  sub     rsp, 40h
0x180011995  mov     r12, r9
0x180011998  mov     r13, r8
0x18001199b  mov     r10, rcx
0x18001199e  xor     eax, eax
0x1800119a0  mov     rsi, [rsp+78h+lpOutputString]
0x1800119a8  mov     [rsi], ax
0x1800119ab  mov     rax, [rsp+78h+arg_60]
0x1800119b3  mov     byte ptr [rax], 0
0x1800119b6  mov     r14, [rsp+78h+arg_38]
0x1800119be  mov     edi, [r14]
0x1800119c1  mov     rbx, [rsp+78h+arg_78]
0x1800119c9  mov     [rbx+8], edi
0x1800119cc  mov     eax, [r14+4]
0x1800119d0  mov     [rbx+0Ch], eax
0x1800119d3  xor     ebp, ebp
0x1800119d5  mov     r15d, [rsp+78h+arg_30]
0x1800119dd  mov     ecx, r15d
0x1800119e0  test    r15d, r15d
0x1800119e3  jz      short loc_180011A4B
0x1800119e5  sub     ecx, 1
0x1800119e8  jz      short loc_180011A42
0x1800119ea  sub     ecx, 1
0x1800119ed  jz      short loc_1800119FD
0x1800119ef  cmp     ecx, 1
0x1800119f2  jnz     short loc_180011A54
0x1800119f4  mov     ecx, edi; this
0x1800119f6  call    ?RecordFailFast@details@wil@@YAHJ@Z; wil::details::RecordFailFast(long)
0x1800119fb  jmp     short loc_180011A52
0x1800119fd  test    edi, edi
0x1800119ff  js      short loc_180011A39
0x180011a01  mov     edi, 8007029Ch
0x180011a06  mov     dword ptr [rsp+78h+var_48], edi; wil::details *
0x180011a0a  mov     rax, [rsp+78h+arg_28]
0x180011a12  mov     [rsp+78h+var_50], rax; __int64
0x180011a17  mov     rax, [rsp+78h+arg_20]
0x180011a1f  mov     [rsp+78h+var_58], rax; __int64
0x180011a24  mov     rcx, r10; int
0x180011a27  call    ??$ReportFailure_Hr@$01@details@wil@@YAXPEAXIPEBD110JW4FailureFlags@1@@Z; wil::details::ReportFailure_Hr<2>(void *,uint,char const *,char const *,char const *,void *,long,wil::FailureFlags)
0x180011a2c  mov     [rbx+8], edi
0x180011a2f  mov     ecx, edi; this
0x180011a31  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011a36  mov     [rbx+0Ch], eax
0x180011a39  mov     ecx, edi; this
0x180011a3b  call    ?RecordLog@details@wil@@YAHJ@Z; wil::details::RecordLog(long)
0x180011a40  jmp     short loc_180011A52
0x180011a42  mov     ecx, edi; this
0x180011a44  call    ?RecordReturn@details@wil@@YAHJ@Z; wil::details::RecordReturn(long)
0x180011a49  jmp     short loc_180011A52
0x180011a4b  mov     ecx, edi; this
0x180011a4d  call    ?RecordException@details@wil@@YAHJ@Z; wil::details::RecordException(long)
0x180011a52  mov     ebp, eax
0x180011a54  mov     [rbx], r15d
0x180011a57  mov     eax, [rsp+78h+arg_70]
0x180011a5e  mov     [rbx+4], eax
0x180011a61  cmp     dword ptr [r14+8], 1
0x180011a66  jnz     short loc_180011A6E
0x180011a68  or      eax, 8
0x180011a6b  mov     [rbx+4], eax
0x180011a6e  mov     eax, 1
0x180011a73  lock xadd cs:?s_failureId@?1??LogFailure@details@wil@@YAXPEAXIPEBD110W4FailureType@3@AEBUResultStatus@23@PEBG_NPEAG_KPEAD7W4FailureFlags@3@PEAUFailureInfo@3@@Z@4JC, eax; long volatile `wil::details::LogFailure(void *,uint,char const *,char const *,char const *,void *,wil::FailureType,wil::details::ResultStatus const &,ushort const *,bool,ushort *,unsigned __int64,char *,unsigned __int64,wil::FailureFlags,wil::FailureInfo *)'::`2'::s_failureId
0x180011a7b  inc     eax
0x180011a7d  mov     [rbx+10h], eax
0x180011a80  mov     rax, [rsp+78h+arg_40]
0x180011a88  xor     edi, edi
0x180011a8a  test    rax, rax
0x180011a8d  jz      short loc_180011A94
0x180011a8f  cmp     [rax], di
0x180011a92  jnz     short loc_180011A97
0x180011a94  mov     rax, rdi
0x180011a97  mov     [rbx+18h], rax
0x180011a9b  call    cs:__imp_GetCurrentThreadId
0x180011aa1  mov     [rbx+20h], eax
0x180011aa4  mov     [rbx+38h], r13
0x180011aa8  mov     eax, [rsp+78h+arg_8]
0x180011aaf  mov     [rbx+40h], eax
0x180011ab2  mov     [rbx+44h], ebp
0x180011ab5  mov     rax, [rsp+78h+arg_20]
0x180011abd  mov     [rbx+28h], rax
0x180011ac1  mov     [rbx+30h], r12
0x180011ac5  mov     rax, [rsp+78h+arg_28]
0x180011acd  mov     [rbx+88h], rax
0x180011ad4  mov     rax, [rsp+78h+arg_0]
0x180011adc  mov     [rbx+90h], rax
0x180011ae3  mov     [rbx+48h], rdi
0x180011ae7  xorps   xmm0, xmm0
0x180011aea  xor     eax, eax
0x180011aec  movups  xmmword ptr [rbx+68h], xmm0
0x180011af0  mov     [rbx+78h], rax
0x180011af4  movups  xmmword ptr [rbx+50h], xmm0
0x180011af8  mov     [rbx+60h], rax
0x180011afc  mov     rax, cs:?g_pfnGetModuleName@details@wil@@3P6APEBDX_EEA
0x180011b03  test    rax, rax
0x180011b06  jz      short loc_180011B0F
0x180011b08  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b0d  jmp     short loc_180011B12
0x180011b0f  mov     rax, rdi
0x180011b12  mov     [rbx+80h], rax
0x180011b19  mov     rax, cs:?g_pfnNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@@_EEA
0x180011b20  test    rax, rax
0x180011b23  jz      short loc_180011B2D
0x180011b25  mov     rcx, rbx
0x180011b28  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b2d  mov     rax, cs:?g_pfnGetContextAndNotifyFailure@details@wil@@3P6AXPEAUFailureInfo@2@PEAD_K@_EEA
0x180011b34  test    rax, rax
0x180011b37  jz      short loc_180011B4F
0x180011b39  mov     r8d, 400h
0x180011b3f  mov     rdx, [rsp+78h+arg_60]
0x180011b47  mov     rcx, rbx
0x180011b4a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b4f  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011b56  test    rax, rax
0x180011b59  jz      short loc_180011B63
0x180011b5b  mov     rcx, rbx
0x180011b5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b63  mov     rax, cs:?g_pfnOriginateCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x180011b6a  test    rax, rax
0x180011b6d  jz      short loc_180011B7D
0x180011b6f  test    byte ptr [rbx+4], 2
0x180011b73  jnz     short loc_180011B7D
0x180011b75  mov     rcx, rbx
0x180011b78  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011b7d  cmp     [rbx+8], edi
0x180011b80  jl      short loc_180011B9C
0x180011b82  cmp     r15d, 3
0x180011b86  jnz     loc_180011C6B
0x180011b8c  mov     ecx, 8000FFFFh; this
0x180011b91  mov     [rbx+8], ecx
0x180011b94  call    ?HrToNtStatus@details@wil@@YAJJ@Z; wil::details::HrToNtStatus(long)
0x180011b99  mov     [rbx+0Ch], eax
0x180011b9c  cmp     cs:?g_fIsDebuggerPresent@wil@@3_NA, dil; bool wil::g_fIsDebuggerPresent
0x180011ba3  jnz     short loc_180011BC4
0x180011ba5  mov     rax, cs:?g_pfnIsDebuggerPresent@wil@@3P6A_NX_EEA
0x180011bac  test    rax, rax
0x180011baf  jz      short loc_180011BBA
0x180011bb1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bb6  test    al, al
0x180011bb8  jmp     short loc_180011BC2
0x180011bba  call    cs:__imp_IsDebuggerPresent
0x180011bc0  test    eax, eax
0x180011bc2  jz      short loc_180011BCA
0x180011bc4  test    byte ptr [rbx+4], 2
0x180011bc8  jz      short loc_180011BEE
0x180011bca  mov     rax, cs:g_pfnResultLoggingCallback
0x180011bd1  test    rax, rax
0x180011bd4  jz      short loc_180011C32
0x180011bd6  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011bdd  jnz     short loc_180011C32
0x180011bdf  xor     r8d, r8d
0x180011be2  xor     edx, edx
0x180011be4  mov     rcx, rbx
0x180011be7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011bec  jmp     short loc_180011C32
0x180011bee  mov     ebp, 800h
0x180011bf3  mov     rax, cs:g_pfnResultLoggingCallback
0x180011bfa  test    rax, rax
0x180011bfd  jz      short loc_180011C16
0x180011bff  cmp     cs:?g_resultMessageCallbackSet@details@wil@@3_NA, dil; bool wil::details::g_resultMessageCallbackSet
0x180011c06  jnz     short loc_180011C16
0x180011c08  mov     r8d, ebp
0x180011c0b  mov     rdx, rsi
0x180011c0e  mov     rcx, rbx
0x180011c11  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c16  cmp     [rsi], di
0x180011c19  jnz     short loc_180011C29
0x180011c1b  mov     r8, rbx; unsigned __int64
0x180011c1e  mov     rdx, rbp; unsigned __int16 *
0x180011c21  mov     rcx, rsi; this
0x180011c24  call    ?GetFailureLogString@wil@@YAJPEAG_KAEBUFailureInfo@1@@Z; wil::GetFailureLogString(ushort *,unsigned __int64,wil::FailureInfo const &)
0x180011c29  mov     rcx, rsi; lpOutputString
0x180011c2c  call    cs:__imp_OutputDebugStringW
0x180011c32  test    byte ptr [rbx+4], 4
0x180011c36  jnz     short loc_180011C41
0x180011c38  cmp     cs:?g_fBreakOnFailure@wil@@3_NA, dil; bool wil::g_fBreakOnFailure
0x180011c3f  jz      short loc_180011C53
0x180011c41  mov     rax, cs:?g_pfnDebugBreak@details@wil@@3P6AXX_EEA
0x180011c48  test    rax, rax
0x180011c4b  jz      short loc_180011C53
0x180011c4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c52  nop
0x180011c53  mov     rbx, [rsp+78h+arg_10]
0x180011c5b  add     rsp, 40h
0x180011c5f  pop     r15
0x180011c61  pop     r14
0x180011c63  pop     r13
0x180011c65  pop     r12
0x180011c67  pop     rdi
0x180011c68  pop     rsi
0x180011c69  pop     rbp
0x180011c6a  retn
0x180011c6b  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
